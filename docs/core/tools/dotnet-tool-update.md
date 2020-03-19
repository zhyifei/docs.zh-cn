---
title: dotnet tool update 命令
description: dotnet tool update 命令更新计算机上指定的 .NET Core 工具。
ms.date: 02/14/2020
ms.openlocfilehash: 497b052a8b9cfa9dca8d80316075fe7565d6b35a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847815"
---
# <a name="dotnet-tool-update"></a>dotnet tool update

本文适用于： ✔️ .NET Core 2.1 SDK 及更高版本

## <a name="name"></a>“属性”

`dotnet tool update` - 更新计算机上指定的 [.NET Core 工具](global-tools.md)。

## <a name="synopsis"></a>摘要

```dotnetcli
dotnet tool update <PACKAGE_NAME> <-g|--global>
    [--configfile] [--framework] [-v|--verbosity]
    [--add-source]

dotnet tool update <PACKAGE_NAME> <--tool-path>
    [--configfile] [--framework] [-v|--verbosity]
    [--add-source]

dotnet tool update <PACKAGE_NAME>
    [--configfile] [--framework] [-v|--verbosity]
    [--add-source]

dotnet tool update <-h|--help>
```

## <a name="description"></a>描述

`dotnet tool update` 命令让你可以将计算机上的 .NET Core 工具更新为包的最新稳定版。 此命令卸载并重新安装工具，有效地对工具进行更新。 若要使用命令，请指定以下选项之一：

* 若要更新安装在默认位置的全局工具，请使用 `--global` 选项
* 若要更新安装在自定义位置的全局工具，请使用 `--tool-path` 选项。
* 若要更新本地工具，请省略 `--global` 和 `--tool-path` 选项。

**本地工具从 .NET Core SDK 3.0 开始可用。**

## <a name="arguments"></a>自变量

- **`PACKAGE_NAME`**

  包含要更新的 .NET Core 全局工具的 NuGet 包的名称/ID。 你可以使用 [dotnet tool list](dotnet-tool-list.md) 命令查找包名称。

## <a name="options"></a>选项

- **`--add-source <SOURCE>`**

  添加安装过程中要使用的其他 NuGet 包源。

- **`--configfile <FILE>`**

  要使用的 NuGet 配置 (nuget.config) 文件。

- **`--framework <FRAMEWORK>`**

  指定要更新工具的[目标框架](../../standard/frameworks.md)。

- **`-g|--global`**

  指定此更新用于用户范围的工具。 不能与 `--tool-path` 选项一起使用。 省略 `--global` 和 `--tool-path` 均指定要更新的工具是本地工具。

- **`-h|--help`**

  打印出有关命令的简短帮助。

- **`--tool-path <PATH>`**

  指定全局工具的安装位置。 路径可以是绝对的，也可以是相对的。 不能与 `--global` 选项一起使用。 省略 `--global` 和 `--tool-path` 均指定要更新的工具是本地工具。

- **`-v|--verbosity <LEVEL>`**

  设置命令的详细级别。 允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。

## <a name="examples"></a>示例

- **`dotnet tool update -g dotnetsay`**

  更新 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具。

- **`dotnet tool update dotnetsay --tool-path c:\global-tools`**

  更新位于特定 Windows 目录的 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具。

- **`dotnet tool update dotnetsay --tool-path ~/bin`**

  更新位于特定 Linux/macOS 目录的 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具。

- **`dotnet tool update dotnetsay`**

  更新为当前目录安装的 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 本地工具。

## <a name="see-also"></a>请参阅

- [.NET Core 工具](global-tools.md)
- [教程：使用 .NET Core CLI 安装和使用 .NET Core 全局工具](global-tools-how-to-use.md)
- [教程：使用 .NET Core CLI 安装和使用 .NET Core 本地工具](local-tools-how-to-use.md)
