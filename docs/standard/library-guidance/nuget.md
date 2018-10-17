---
title: NuGet 和.NET 库
description: 最佳实践建议打包 nuget 的.NET 库。
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: d0ea462a7f52dd9a6b2f14be9ed5770160bf66b1
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374483"
---
# <a name="nuget"></a>NuGet

NuGet 是.NET 生态系统的包管理器，并且是主要方法开发人员发现，并获取.NET 开放源代码库。 [NuGet.org](https://www.nuget.org/)，为托管 NuGet 包，由 Microsoft 提供的免费服务是主要主机的公共 NuGet 包，但可以发布到自定义 NuGet 服务，如[MyGet](https://www.myget.org/)和[Azure 项目](https://azure.microsoft.com/services/devops/artifacts/).

![NuGet](./media/nuget/nuget-logo.png "NuGet")

## <a name="create-a-nuget-package"></a>创建 NuGet 包

NuGet 包 (`*.nupkg`) 是一个 zip 文件，其中包含.NET 程序集和关联的元数据。

有两种主要方法来创建 NuGet 包。 更新和推荐方法是从 SDK 样式项目创建包 (项目文件的内容开头`<Project Sdk="Microsoft.NET.Sdk">`)。 自动添加到包程序集和目标和剩余的元数据添加到 MSBuild 文件，如包名称和版本号码。 使用编译[ `dotnet pack` ](../../core/tools/dotnet-pack.md)命令输出`*.nupkg`文件而不是程序集。

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <AssemblyName>Contoso.Api</AssemblyName>
    <PackageVersion>1.1.0</PackageVersion>
    <Authors>John Doe</Authors>
  </PropertyGroup>
</Project>
```

创建 NuGet 包的较旧的方法是使用`*.nuspec`文件和`nuget.exe`命令行工具。 Nuspec 文件为您提供了更好地控制，但必须小心地指定要包含在最终的 NuGet 包中哪些程序集和目标。 很容易犯错或其他人进行更改时，更新 nuspec 忘了。 Nuspec 的优点是可以使用它创建尚不支持的 SDK 样式项目文件的框架的 NuGet 包。

**请考虑 ✔️**使用 SDK 样式项目文件创建 NuGet 包。

**请考虑 ✔️**设置 SourceLink，以将源控件元数据添加到你的程序集和 NuGet 包。

## <a name="package-dependencies"></a>包的依赖项

中详细介绍了 NuGet 包依赖项[依赖项](./dependencies.md)一文。

## <a name="important-nuget-package-metadata"></a>重要的 NuGet 包元数据

NuGet 包支持许多[元数据属性](/nuget/reference/nuspec)。 下表包含每个开放源代码项目应提供的核心元数据：

| MSBuild 属性名称              | Nuspec 名称              | 描述  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | 包标识符。 如果满足，则可以保留与标识符的前缀[条件](/nuget/reference/id-prefix-reservation)。 |
| `PackageVersion`                   | `version`                  | NuGet 包版本。 有关详细信息，请参阅[NuGet 包版本](./versioning.md#nuget-package-version)。             |
| `Title`                            | `title`                    | 包的用户友好标题。 它将默认为`PackageId`。             |
| `Description`                      | `description`              | 在 UI 中显示的包的详细说明。             |
| `Authors`                          | `authors`                  | 逗号分隔的包创建者，匹配在 nuget.org 上的配置文件名称列表。             |
| `PackageTags`                      | `tags`                     | 以空格分隔的标记和描述包的关键字列表。 搜索包时使用标记。             |
| `PackageIconUrl`                   | `iconUrl`                  | 要用作包的图标图像 URL。 URL 应当采用 https 格式和图像应为 64 x 64 和具有透明背景。             |
| `PackageProjectUrl`                | `projectUrl`               | 项目主页或源存储库的 URL。             |
| `PackageLicenseUrl`                | `licenseUrl`               | 指向项目许可证的 URL。 可以是指向 URL`LICENSE`在源代码管理中的文件。             |

**请考虑 ✔️**选择 NuGet 包名称与满足 NuGet 的前缀保留的前缀[条件](/nuget/reference/id-prefix-reservation)。

**请考虑 ✔️**使用`LICENSE`作为源代码管理中的文件`LicenseUrl`。 例如， [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md)。

> [!IMPORTANT]
> 一个项目没有许可证的默认值为[独占版权所有](https://choosealicense.com/no-permission/)，从而使其他人使用。

**✔️ 执行**使用 HTTPS href 为您的包图标。

> NuGet.org 等网站运行与启用 HTTPS 并显示一个非 HTTPS 的图像将创建混合内容警告。

**✔️ 执行**使用包图标图像，为 64 x 64 和具有透明背景地查看结果。

## <a name="pre-release-packages"></a>预发行包

具有版本后缀的 NuGet 包被视为[预发行版](/nuget/create-packages/prerelease-packages)。 默认情况下，NuGet 包管理器 UI 显示稳定版本，除非用户选择在中以预发行包，使预发行包适用于受限的用户测试。

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> 稳定的包不能依赖于预发行包。 必须使预发行版的你自己的包或依赖于较旧的稳定版本。

![NuGet 预发行包依赖项](./media/nuget/nuget-prerelease-package.png "NuGet 预发行包依赖项")

**✔️ 执行**发布时测试、 预览或试用的预发行包。

**✔️ 执行**发布稳定的包时其就绪以便其他稳定包可以引用它。

## <a name="symbol-packages"></a>符号包

NuGet 支持[生成单独的符号包](/nuget/create-packages/symbol-packages)包含调试 PDB 文件与主包包含.NET 程序集一起。 符号包的理念是它们在符号服务器上承载，并且只会由 Visual Studio 等工具创建按需下载。

当前符号的主要公共主机[SymbolSource](http://www.symbolsource.org/) -不支持创建可移植 Pdb 由 SDK 样式项目和符号包不是很有用。

**请考虑 ✔️**在主要的 NuGet 包中嵌入 Pdb。

**请避免 ❌**创建符号包包含的 Pdb。

>[!div class="step-by-step"]
[上一页](./strong-naming.md)
[下一页](./dependencies.md)
