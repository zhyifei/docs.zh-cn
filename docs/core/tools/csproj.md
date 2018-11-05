---
title: .NET Core 的 csproj 格式的新增内容
description: 了解现有文件和 .NET Core csproj 文件之间的区别
author: blackdwarf
ms.author: mairaw
ms.date: 09/22/2017
ms.openlocfilehash: 3de168b8cebeb435a45861138aea26580663c135
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2018
ms.locfileid: "50203951"
---
# <a name="additions-to-the-csproj-format-for-net-core"></a>.NET Core 的 csproj 格式的新增内容

本文档概述了作为从 *project.json* 移动到 *csproj* 和 [MSBuild](https://github.com/Microsoft/MSBuild) 的一部分，添加到项目文件的更改。 有关常规项目文件的语法和引用的详细信息，请参阅 [MSBuild 项目文件](/visualstudio/msbuild/msbuild-project-file-schema-reference)文档。  

## <a name="implicit-package-references"></a>隐式包引用
基于项目文件的 `<TargetFramework>` 或 `<TargetFrameworks>` 属性中指定的目标框架对元包进行隐式引用。 如果指定了 `<TargetFramework>`，则忽略 `<TargetFrameworks>`，而与顺序无关。

```xml
 <PropertyGroup>
   <TargetFramework>netcoreapp2.1</TargetFramework>
 </PropertyGroup>
 ```
 
 ```xml
 <PropertyGroup>
   <TargetFrameworks>netcoreapp2.1;net462</TargetFrameworks>
 </PropertyGroup>
 ```

### <a name="recommendations"></a>建议
由于隐式引用了 `Microsoft.NETCore.App` 或 `NetStandard.Library` 元包，以下是建议的最佳做法：

* 面向 .NET Core 或 .NET Standard 时，绝不通过项目文件中的 `<PackageReference>` 项，对 `Microsoft.NETCore.App` 或 `NetStandard.Library` 元包进行显式引用。
* 面向 .NET Core 时，如果需要特定版本的运行时，应使用项目中的 `<RuntimeFrameworkVersion>` 属性（例如，`1.0.4`），而不是引用元包。
    * 例如，如果使用[独立部署](../deploying/index.md#self-contained-deployments-scd)且需要 1.0.0 LTS 运行时的特定修补程序版本，可能会发生这种情况。
* 面向 .NET Standard 时，如果需要特定版本的 `NetStandard.Library` 元包，可以使用 `<NetStandardImplicitPackageVersion>` 属性并设置所需版本。
* 请勿在 .NET Framework 项目中显式添加或更新对 `Microsoft.NETCore.App` 或 `NetStandard.Library` 元包的引用。 使用基于 .NET Standard 的 NuGet 包时，如果需要任意版本的 `NetStandard.Library`，NuGet 可自动安装该版本。

## <a name="default-compilation-includes-in-net-core-projects"></a>.NET Core 项目中默认包含的编译项
已通过移动到最新 SDK 版本中的 *csproj* 格式，将默认的编译项和嵌入资源的包含项和排除项移至 SDK 属性文件。 这意味着不需要再在项目文件中指定这些项。 

执行此操作的主要目的是减少项目文件中的混杂。 SDK 中的默认设置应涵盖最常见的用例，由此便无需在创建的每个项目中重复这些设置。 这可使项目文件更小，更易于理解和进行手动编辑（如果需要）。 

下表显示同时在 SDK 中包含和排除的元素和 [globs](https://en.wikipedia.org/wiki/Glob_(programming))： 

| 元素           | 包含 glob                              | 排除 glob                                                  | 删除 glob                |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| Compile           | \*\*/\*.cs（或其他语言扩展名） | \*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc  | 不可用                        |
| EmbeddedResource  | \*\*/\*.resx                              | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | 不可用                        |
| 无              | \*\*/\*                                   | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | - \*\*/\*.cs; \*\*/\*.resx |

如果项目中有 glob，却又尝试使用最新的 SDK 生成它，则将收到以下错误：

> 包含重复的编译项。 默认情况下，.NET SDK 包括项目目录中的编译项。 可从项目文件中删除这些项，或如果想要在项目文件中显式包括它们，则将“EnableDefaultCompileItems”属性设为“false”。 

要解决此错误，可以删除与前表中所列项匹配的显式 `Compile` 项，也可以将 `<EnableDefaultCompileItems>` 属性设置为 `false`，如下所示：

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
将此属性设置为 `false` 将替代隐式包含，且该行为将恢复到以前的 SDK，在这种情况下，必须在项目中指定默认 glob。 

此更改不会修改其他包含项的主要机制。 但是，如果要指定（例如，指定某些文件通过应用发布），仍可以使用 *csproj* 中相应的已知机制来实现（例如，`<Content>` 元素）。

`<EnableDefaultCompileItems>` 仅禁用 `Compile` glob，但不会影响其他 glob（如隐式 `None` glob），这也适用于 \*.cs 项。 因此，解决方案资源管理器继续显示在项目中作为 `None` 项的 \*.cs 项。 可按照类似的方式使用 `<EnableDefaultNoneItems>` 禁用隐式 `None` glob。

要禁用所有隐式 glob，可将 `<EnableDefaultItems>` 属性设置为 `false`，如以下示例所示：
```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

### <a name="recommendation"></a>建议
使用 csproj 时，建议从项目中删除默认 glob，且仅为应用/库需要用于各种方案（例如，运行时和 NuGet 封装）的项目添加 glob 文件路径。

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a>如何像 MSBuild 一样查看整个项目

虽然这些 csproj 更改极大地简化了项目文件，但建议查看完全展开的项目，就像 MSBuild 查看添加了 SDK 及其目标的项目一样。 使用 [`dotnet msbuild`](dotnet-msbuild.md) 命令的 [`/pp` 开关](/visualstudio/msbuild/msbuild-command-line-reference#preprocess)预处理项目，显示导入的文件、文件源及其在生成中的参与情况，而无需实际生成项目：

`dotnet msbuild -pp:fullproject.xml`

如果项目有多个目标框架，命令结果应仅侧重于框架之一，具体方法为将相应框架指定为 MSBuild 属性：

`dotnet msbuild -p:TargetFramework=netcoreapp2.0 -pp:fullproject.xml`

## <a name="additions"></a>新增内容

### <a name="sdk-attribute"></a>Sdk 特性 
*.csproj* 文件的 `<Project>` 元素具有名为 `Sdk` 的新特性。 `Sdk` 指定项目将使用的 SDK。 如[分层文档](cli-msbuild-architecture.md)中所述，SDK 是一组可生成 .NET Core 代码的 MSBuild [任务](/visualstudio/msbuild/msbuild-tasks)和[目标](/visualstudio/msbuild/msbuild-targets)。 .NET Core 工具随附了三个主要 SDK：

1. ID 为 `Microsoft.NET.Sdk` 的 .NET Core SDK
2. ID 为 `Microsoft.NET.Sdk.Web` 的 .NET Core Web SDK
3. ID 为 `Microsoft.NET.Sdk.Razor` 的 .NET Core Razor 类库 SDK

需要在 `<Project>` 元素上将 `Sdk` 属性设置为这两个 ID 之一，以使用 .NET Core 工具和生成代码。 

### <a name="packagereference"></a>PackageReference
用于指定项目中 NuGet 依赖项的项。 `Include` 属性指定包 ID。 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a>版本
`Version` 指定要还原的包的版本。 此属性遵循 [NuGet 版本控制](/nuget/create-packages/dependency-versions#version-ranges)方案规则。 默认行为是精确的版本匹配。 例如，指定 `Version="1.2.3"` 等效于包的 1.2.3 版本的 NuGet 表示法 `[1.2.3]`。

#### <a name="includeassets-excludeassets-and-privateassets"></a>IncludeAssets、ExcludeAssets 和 PrivateAssets
`IncludeAssets` 属性指定应使用 `<PackageReference>` 指定的包中的哪些资产。 

`ExcludeAssets` 属性指定不应使用 `<PackageReference>` 指定的包中的哪些资产。

`PrivateAssets` 属性指定应使用 `<PackageReference>` 指定的包中的哪些资产，但不得将这些资产传递到下一个项目。 

> [!NOTE]
> `PrivateAssets` 等效于 *project.json*/*xproj* `SuppressParent` 元素。

这些属性可以包含下列一个或多个项：

* `Compile` - 可对 lib 文件夹内容进行编译。
* `Runtime` - 分发运行时文件夹内容。
* `ContentFiles` - 使用 *contentfiles* 文件夹的内容。
* `Build` - 使用生成文件夹中的属性/目标。
* `Native` - 将本机资产内容复制到运行时输出文件夹。
* `Analyzers` - 使用分析器。

此属性也可以包含：

* `None` - 不使用任何资产。
* `All` - 使用所有资产。

### <a name="dotnetclitoolreference"></a>DotNetCliToolReference
`<DotNetCliToolReference>` 项元素指定用户想要在项目的上下文中还原的 CLI 工具。 在 *project.json* 中，它可以替换 `tools` 节点。 

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a>版本
`Version` 指定要还原的包的版本。 此属性遵循 [NuGet 版本控制](/nuget/create-packages/dependency-versions#version-ranges)方案规则。 默认行为是精确的版本匹配。 例如，指定 `Version="1.2.3"` 等效于包的 1.2.3 版本的 NuGet 表示法 `[1.2.3]`。

### <a name="runtimeidentifiers"></a>RuntimeIdentifiers
`<RuntimeIdentifiers>` 元素可用于指定项目的[运行时标识符 (RID)](../rid-catalog.md) 的列表（以分号分隔）。 使用 RID ，可发布独立部署。 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a>RuntimeIdentifier
`<RuntimeIdentifier>` 元素可用于指定项目的唯一[运行时标识符 (RID)](../rid-catalog.md)。 使用 RID ，可发布独立部署。 

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

### <a name="packagetargetfallback"></a>PackageTargetFallback 
`<PackageTargetFallback>` 元素可用于指定要在还原包时使用的一组兼容目标。 旨在允许使用 dotnet [TxM（目标 x 名字对象）](/nuget/schema/target-frameworks) 的包处理未声明 dotnet TxM 的包。 如果项目使用 dotnet TxM，那么所依赖的所有包也必须有 dotnet TxM，除非将 `<PackageTargetFallback>` 添加到项目中，以允许非 dotnet 平台与 dotnet 兼容。 

以下示例展示了项目中所有目标的回退： 

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

以下示例仅指定了 `netcoreapp2.1` 目标的回退：

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp2.1'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="nuget-metadata-properties"></a>NuGet 元数据属性
迁移到 MSbuild 后，我们已将在打包 NuGet 包时使用的输入元数据从 *project.json* 移到 *.csproj* 文件中。 输入为 MSBuild 属性，因此它们必须转到 `<PropertyGroup>` 组中。 下面列出了在使用 `dotnet pack` 命令或属于 SDK 的 `Pack` MSBuild 目标时，用作打包进程的输入的属性。 

### <a name="ispackable"></a>IsPackable
一个指定能否打包项目的布尔值。 默认值为 `true`。 

### <a name="packageversion"></a>PackageVersion
指定生成的包所具有的版本。 接受所有形式的 NuGet 版本字符串。 默认为值 `$(Version)`，即项目中 `Version` 属性的值。 

### <a name="packageid"></a>PackageId
指定生成的包的名称。 如果未指定，`pack` 操作将默认使用 `AssemblyName` 或目录名称作为包的名称。 

### <a name="title"></a>标题
明了易用的包标题，通常用在 UI 显示中，如 nuget.org 上和 Visual Studio 中包管理器上的那样。 如果未指定，则改为使用包 ID。

### <a name="authors"></a>作者
其中名称以分号分隔的包作者列表，其中名称与 nuget.org 上的配置文件名称匹配。这些信息显示在 nuget.org 上的 NuGet 库中，并用于交叉引用同一作者的包。

### <a name="description"></a>描述
用于 UI 显示的包的详细说明。

### <a name="copyright"></a>Copyright
包的版权详细信息。

### <a name="packagerequirelicenseacceptance"></a>PackageRequireLicenseAcceptance
一个布尔值，指定客户端是否必须提示使用者接受包许可证后才可安装包。 默认值为 `false`。

### <a name="packagelicenseurl"></a>PackageLicenseUrl
适用于包的许可证的 URL。

### <a name="packageprojecturl"></a>PackageProjectUrl
包的主页 URL，通常显示在 UI 中以及 nuget.org 中。

### <a name="packageiconurl"></a>PackageIconUrl
64x64 透明背景图像的 URL，用作 UI 显示中包的图标。

### <a name="packagereleasenotes"></a>PackageReleaseNotes
包的发行说明。

### <a name="packagetags"></a>PackageTags
标记的分号分隔列表，这些标记用于指定包。

### <a name="packageoutputpath"></a>PackageOutputPath
确定用于已打包的包的输出路径。 默认值为 `$(OutputPath)`。 

### <a name="includesymbols"></a>IncludeSymbols
此布尔值指示在打包项目时，包是否应创建一个附加的符号包。 此包将具有 *.symbols.nupkg* 扩展名，并将 PDB 文件连同 DLL 和其他输出文件一并复制。

### <a name="includesource"></a>IncludeSource
此布尔值指示包进程是否应创建源包。 源包中包含库的源代码以及 PDB 文件。 源文件置于生成的包文件中的 `src/ProjectName` 目录下。 

### <a name="istool"></a>IsTool
指定是否将所有输出文件复制到 *tools* 文件夹，而不是 *lib* 文件夹。 请注意，这不同于 `DotNetCliTool`，后者通过在 *.csproj* 文件中设置 `PackageType` 进行指定。

### <a name="repositoryurl"></a>RepositoryUrl
指定存储库的 URL，该存储库是包的源代码所驻留和/或生成的位置。 

### <a name="repositorytype"></a>RepositoryType
指定存储库的类型。 默认值为“git”。 

### <a name="nopackageanalysis"></a>NoPackageAnalysis
指定 pack 不应在生成包后运行包分析。

### <a name="minclientversion"></a>MinClientVersion
指定可安装此包的最低 NuGet 客户端版本，并由 nuget.exe 和 Visual Studio 程序包管理器强制实施。

### <a name="includebuildoutput"></a>IncludeBuildOutput
此布尔值指定是否应将生成输出程序集打包到 *.nupkg* 文件中。

### <a name="includecontentinpack"></a>IncludeContentInPack
此布尔值指定是否将含有 `Content` 类型的任何项自动包含在生成的包中。 默认值为 `true`。 

### <a name="buildoutputtargetfolder"></a>BuildOutputTargetFolder
指定放置输出程序集的文件夹。 输出程序集（和其他输出文件）会复制到各自的框架文件夹中。

### <a name="contenttargetfolders"></a>ContentTargetFolders
此属性指定放置所有内容文件的默认位置（如果未为其指定 `PackagePath`）。 默认值为“content;contentFiles”。

### <a name="nuspecfile"></a>NuspecFile
用于打包的 *.nuspec* 文件的相对或绝对路径。 

> [!NOTE]
> 如果指定了 *.nuspec* 文件，则**以独占方式**将其用于打包信息，并且不使用项目中的任何信息。 

### <a name="nuspecbasepath"></a>NuspecBasePath
*.nuspec* 文件的基路径。

### <a name="nuspecproperties"></a>NuspecProperties
键=值对的分号分隔列表。

## <a name="assemblyinfo-properties"></a>AssemblyInfo 属性
现在，*AssemblyInfo* 文件中通常存在的[程序集特性](../../framework/app-domains/set-assembly-attributes.md)将自动从属性生成。

### <a name="properties-per-attribute"></a>每个特性的属性

每个特性都有一个可控制其内容的属性，还有一个可以禁用其生成的属性，如下表所示：

| 特性                                                      | 属性               | 要禁用的属性                             |
|----------------------------------------------------------------|------------------------|-------------------------------------------------|
| <xref:System.Reflection.AssemblyCompanyAttribute>              | `Company`              | `GenerateAssemblyCompanyAttribute`              |
| <xref:System.Reflection.AssemblyConfigurationAttribute>        | `Configuration`        | `GenerateAssemblyConfigurationAttribute`        |
| <xref:System.Reflection.AssemblyCopyrightAttribute>            | `Copyright`            | `GenerateAssemblyCopyrightAttribute`            |
| <xref:System.Reflection.AssemblyDescriptionAttribute>          | `Description`          | `GenerateAssemblyDescriptionAttribute`          |
| <xref:System.Reflection.AssemblyFileVersionAttribute>          | `FileVersion`          | `GenerateAssemblyFileVersionAttribute`          |
| <xref:System.Reflection.AssemblyInformationalVersionAttribute> | `InformationalVersion` | `GenerateAssemblyInformationalVersionAttribute` |
| <xref:System.Reflection.AssemblyProductAttribute>              | `Product`              | `GenerateAssemblyProductAttribute`              |
| <xref:System.Reflection.AssemblyTitleAttribute>                | `AssemblyTitle`        | `GenerateAssemblyTitleAttribute`                |
| <xref:System.Reflection.AssemblyVersionAttribute>              | `AssemblyVersion`      | `GenerateAssemblyVersionAttribute`              |
| <xref:System.Resources.NeutralResourcesLanguageAttribute>      | `NeutralLanguage`      | `GenerateNeutralResourcesLanguageAttribute`     |

注意：

* `AssemblyVersion` 和 `FileVersion` 默认采用 `$(Version)` 的值而不带后缀。 例如，如果 `$(Version)` 为 `1.2.3-beta.4`，则值将为 `1.2.3`。
* `InformationalVersion` 默认是 `$(Version)` 的值。
* 如果存在此属性，则 `InformationalVersion` 附加 `$(SourceRevisionId)`。 可以使用 `IncludeSourceRevisionInInformationalVersion` 来禁用它。
* `Copyright` 和 `Description` 属性也可用于 NuGet 元数据。
* `Configuration` 与所有生成过程共享，并通过 `dotnet` 命令的 `--configuration` 参数进行设置。

### <a name="generateassemblyinfo"></a>GenerateAssemblyInfo 
一个布尔值，用于启用或禁用所有 AssemblyInfo 生成。 默认值为 `true`。 

### <a name="generatedassemblyinfofile"></a>GeneratedAssemblyInfoFile 
生成的程序集信息文件的路径。 默认为 `$(IntermediateOutputPath)` (obj) 目录中的某个文件。
