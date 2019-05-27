---
title: dotnet list package 命令
description: 使用“dotnet list package”命令，可以方便地列出项目或解决方案的包引用。
ms.date: 04/09/2019
ms.openlocfilehash: 88ef3302a955eadc4167384312e4eb721dd496fb
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631773"
---
# <a name="dotnet-list-package"></a>dotnet list package

[!INCLUDE [topic-appliesto-net-core-22plus](../../../includes/topic-appliesto-net-core-22plus.md)]

## <a name="name"></a>name

`dotnet list package` - 列出项目或解决方案的包引用。

## <a name="synopsis"></a>摘要

```
dotnet list [<PROJECT | SOLUTION>] package [--config] [--framework] [--highest-minor] [--highest-patch] 
   [--include-prerelease] [--include-transitive] [--outdated] [--source]
dotnet list package [-h|--help]
```

## <a name="description"></a>说明

使用 `dotnet list package` 命令，可以方便地列出特定项目或解决方案的所有 NuGet 包引用。 首先，需要生成项目，以提供必需资产以供此命令处理。 下面的示例展示了 [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 项目的 `dotnet list package` 命令输出：

```output
Project 'SentimentAnalysis' has the following package references
   [netcoreapp2.1]:
   Top-level Package               Requested   Resolved
   > Microsoft.ML                  0.11.0      0.11.0
   > Microsoft.NETCore.App   (A)   [2.1.0, )   2.1.0

(A) : Auto-referenced package.
```

“已请求”列是指项目文件中指定的包版本，可以是一个范围。 “已解析”列列出了项目当前使用的版本，始终都是一个值。 紧靠名称旁边显示 `(A)` 的包表示从项目设置（`Sdk` 类型、`<TargetFramework>` 或 `<TargetFrameworks>` 属性等）推断出的[隐式包引用](csproj.md#implicit-package-references)。

使用 `--outdated` 选项，可以确定项目中正在使用的包是否有更高版本。 默认情况下，`--outdated` 列出最新稳定包，除非已解析版本也是预发行版本。 若要在列出更高版本时包含预发行版本，还请指定 `--include-prerelease` 选项。 下面的示例展示了上一个示例中相同项目的 `dotnet list package --outdated --include-prerelease` 命令输出：

```output
The following sources were used:
   https://api.nuget.org/v3/index.json

Project `SentimentAnalysis` has the following updates to its packages
   [netcoreapp2.1]:
   Top-level Package      Requested   Resolved   Latest
   > Microsoft.ML         0.11.0      0.11.0     1.0.0-preview
```

如果需要确定项目是否有可传递依赖关系，请使用 `--include-transitive` 选项。 如果在项目中添加包，它转而又依赖另一个包，就会出现可传递依赖关系。 下面的示例展示了 [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin) 项目的 `dotnet list package --include-transitive` 命令运行输出，其中显示顶级包及其依赖的包：

```output
Project 'HelloPlugin' has the following package references
   [netcoreapp3.0]:
   Top-level Package                      Requested                    Resolved
   > Microsoft.NETCore.Platforms    (A)   [3.0.0-preview3.19128.7, )   3.0.0-preview3.19128.7
   > Microsoft.WindowsDesktop.App   (A)   [3.0.0-preview3-27504-2, )   3.0.0-preview3-27504-2

   Transitive Package               Resolved
   > Microsoft.NETCore.Targets      2.0.0
   > PluginBase                     1.0.0

(A) : Auto-referenced package.
```

## <a name="arguments"></a>自变量

`PROJECT | SOLUTION`

要对其运行命令的项目或解决方案文件。 如果未指定，此命令会搜索当前目录来获取一个项目文件。 如果找到多个解决方案或项目，便会抛出错误。

## <a name="options"></a>选项

* **`--config <SOURCE>`**

  在搜索版本更高的包时，要使用的 NuGet 源。 需要使用 `--outdated` 选项。

* **`--framework <FRAMEWORK>`**

  只显示适用于指定[目标框架](../../standard/frameworks.md)的包。 若要指定多个框架，请多次重复此选项。 例如：`--framework netcoreapp2.2 --framework netstandard2.0`。

* **`-h|--help`**

  打印出有关命令的简短帮助。

* **`--highest-minor`**

  在搜索版本更高的包时，仅考虑有匹配的主版本号的包。 需要使用 `--outdated` 选项。

* **`--highest-patch`**

  在搜索版本更高的包时，仅考虑有匹配的主版本号和次要版本号的包。 需要使用 `--outdated` 选项。

* **`--include-prerelease`**

  在搜索版本更高的包时，考虑有预发行版本的包。 需要使用 `--outdated` 选项。

* **`--include-transitive`**

  除了顶级包之外，还列出可传递包。 如果指定此选项，可以获取顶级包所依赖的包列表。

* **`--outdated`**

  列出版本更高的包。

* **`-s|--source <SOURCE>`**

  在搜索版本更高的包时，要使用的 NuGet 源。 需要使用 `--outdated` 选项。

## <a name="examples"></a>示例

* 列出特定项目的包引用：

  ```console
  dotnet list SentimentAnalysis.csproj package
  ```

* 列出有更高版本（包括预发行版本）的包引用：

  ```console
  dotnet list package --outdated --include-prerelease
  ```

* 列出特定目标框架的包引用：

  ```console
  dotnet list package --framework netcoreapp3.0
  ```
