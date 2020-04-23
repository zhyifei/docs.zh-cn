---
title: Microsoft.NET.Sdk 的 MSBuild 属性
description: .NET Core SDK 可以理解的 MSBuild 属性的引用。
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: d4a204a1e0216313418d278ec3bd333f72db8751
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "81386656"
---
# <a name="msbuild-properties-for-net-core-sdk-projects"></a>.NET Core SDK 项目的 MSBuild 属性

本页介绍用于配置 .NET Core 项目的 MSBuild 属性。

> [!NOTE]
> 此页面正在运行中，未列出 .NET Core SDK 的所有有用的 MSBuild 属性。 有关通用 MSBuild 属性的列表，请参阅[通用 MSBuild 属性](/visualstudio/msbuild/common-msbuild-project-properties)。

## <a name="framework-properties"></a>框架属性

- [TargetFramework](#targetframework)
- [TargetFrameworks](#targetframeworks)
- [NetStandardImplicitPackageVersion](#netstandardimplicitpackageversion)

### <a name="targetframework"></a>TargetFramework

`TargetFramework` 属性指定应用的目标框架版本，该版本隐式引用[元包](../packages.md#metapackages)。 有关有效的目标框架名字对象的列表，请参阅 [SDK 样式项目中的目标框架](../../standard/frameworks.md#supported-target-framework-versions)。

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
</Project>
```

有关详细信息，请参阅 [SDK 样式项目中的目标框架](../../standard/frameworks.md)。

### <a name="targetframeworks"></a>TargetFrameworks

如果希望应用面向多个平台，请使用 `TargetFrameworks` 属性。 有关有效的目标框架名字对象的列表，请参阅 [SDK 样式项目中的目标框架](../../standard/frameworks.md#supported-target-framework-versions)。

> [!NOTE]
> 如果指定了 `TargetFramework`（单数），则忽略此属性。

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
  </PropertyGroup>
</Project>
```

有关详细信息，请参阅 [SDK 样式项目中的目标框架](../../standard/frameworks.md)。

### <a name="netstandardimplicitpackageversion"></a>NetStandardImplicitPackageVersion

> [!NOTE]
> 此属性仅适用于使用 `netstandard1.x` 的项目。 它不适用于使用 `netstandard2.x` 的项目。

如果要指定低于[元包](../packages.md#metapackages)版本的框架版本，请使用 `NetStandardImplicitPackageVersion` 属性。 以下示例中的项目文件以 `netstandard1.3` 为目标，但使用 `NETStandard.Library` 的 1.6.0 版本。

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.3</TargetFramework>
    <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
  </PropertyGroup>
</Project>
```

## <a name="publish-properties"></a>发布属性

- [RuntimeIdentifier](#runtimeidentifier)
- [RuntimeIdentifiers](#runtimeidentifiers)
- [UseAppHost](#useapphost)

### <a name="runtimeidentifier"></a>RuntimeIdentifier

`RuntimeIdentifier` 属性可用于指定项目的单个[运行时标识符 (RID)](../rid-catalog.md)。 RID 支持发布独立部署。

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
  </PropertyGroup>
</Project>
```

### <a name="runtimeidentifiers"></a>RuntimeIdentifiers

`RuntimeIdentifiers` 属性可用于指定项目的[运行时标识符 (RID)](../rid-catalog.md) 的列表（以分号分隔）。 如果需要为多个运行时发布，请使用此属性。 `RuntimeIdentifiers` 在还原时使用，以确保图中有适当的资产。

> [!TIP]
> `RuntimeIdentifier`（单数）可以在只需要一个运行时时提供更快的生成。

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

### <a name="useapphost"></a>UseAppHost

`UseAppHost` 属性是在 .NET Core SDK 的 2.1.400 版本中引入的。 它控制是否为部署创建本机可执行文件。 自包含部署需要本机可执行文件。

在 .NET Core3.0 及更高版本中，默认情况下会创建依赖于框架的可执行文件。 将 `UseAppHost` 属性设置为 `false` 可禁用可执行文件的生成。

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <UseAppHost>false</UseAppHost>
  </PropertyGroup>
</Project>
```

有关部署的详细信息，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。

## <a name="compile-properties"></a>编译属性

### <a name="langversion"></a>LangVersion

`LangVersion` 属性可用于指定特定的编程语言版本。 例如，如果要访问 C# 预览功能，请将 `LangVersion` 设置为 `preview`。

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <LangVersion>preview</LangVersion>
  </PropertyGroup>
</Project>
```

有关详细信息，请参阅 [C# 语言版本控制](../../csharp/language-reference/configure-language-version.md#override-a-default)。

## <a name="nuget-packages"></a>NuGet 包

- [PackageReference](#packagereference)
- [AssetTargetFallback](#assettargetfallback)

### <a name="packagereference"></a>PackageReference

`PackageReference` 项可用于指定 NuGet 依赖项。 例如，你可能想要引用单个包而不是[元包](../packages.md#metapackages)。 `Include` 属性指定包 ID。 以下示例中的项目文件片段引用 [System.Runtime](https://www.nuget.org/packages/System.Runtime/) 包。

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <ItemGroup>
    <PackageReference Include="System.Runtime" Version="4.3.0" />
  </ItemGroup>
</Project>
```

有关详细信息，请参阅[项目文件中的包引用](/nuget/consume-packages/package-references-in-project-files)。

### <a name="assettargetfallback"></a>AssetTargetFallback

`AssetTargetFallback` 属性可用于为你的项目引用的项目以及你的项目所使用的 NuGet 包指定其他兼容的框架版本。 例如，如果使用 `PackageReference` 指定包依赖项，但该包不包含与项目的 `TargetFramework` 兼容的资源，则可使用 `AssetTargetFallback` 属性。 使用 `AssetTargetFallback` 中指定的每个目标框架重新检查引用包的兼容性。

可以将 `AssetTargetFallback` 属性设置为一个或多个[目标框架版本](../../standard/frameworks.md#supported-target-framework-versions)。

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <PropertyGroup>
    <AssetTargetFallback>net461</AssetTargetFallback>
  </PropertyGroup>
</Project>
```

### <a name="pack-and-restore-targets"></a>包和还原目标

MSBuild 15.1 引入了 `pack` 和 `restore` 目标，用于创建和还原作为生成一部分的 NuGet 包。 有关这些目标（包括 `PackageTargetFallback`）的 MSBuild 属性的信息，请参阅[作为 MSBuild 目标的 NuGet 包和还原](/nuget/reference/msbuild-targets)。

## <a name="see-also"></a>请参阅

- [MSBuild 架构引用](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [通用 MSBuild 属性](/visualstudio/msbuild/common-msbuild-project-properties)
- [NuGet 包的 MSBuild 属性](/nuget/reference/msbuild-targets#pack-target)
- [NuGet 还原的 MSBuild 属性](/nuget/reference/msbuild-targets#restore-properties)
- [自定义生成](/visualstudio/msbuild/customize-your-build)
