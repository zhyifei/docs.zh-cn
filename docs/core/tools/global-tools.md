---
title: .NET Core 全局工具
description: 概述：介绍 .NET Core 全局工具及其适用的 .NET Core CLI 命令。
author: KathleenDollard
ms.date: 05/29/2018
ms.openlocfilehash: 0df3c1b615adfeaaf41542dc8252a8f14f49f6f9
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899868"
---
# <a name="net-core-global-tools-overview"></a>.NET Core 全局工具概述

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

.NET Core 全局工具是一种特殊的 NuGet 包，其中包含控制台应用程序。 全局工具可安装在计算机上的默认位置（包含在 PATH 环境变量中）或自定义位置。

若要使用 .NET Core 全局工具，请执行以下操作：

* 查找该工具的相关信息（通常是一个网站或 GitHub 页面）。
* 在源的主页（通常为 NuGet.org）查看作者和统计信息。
* 安装该工具。
* 调用该工具。
* 更新该工具。
* 卸载该工具。

> [!IMPORTANT]
> .NET Core 全局工具在路径中显示，且以完全信任的方式运行。 除非你信任工具作者，否则请勿安装 .NET Core 全局工具。

## <a name="find-a-net-core-global-tool"></a>查找 .NET Core 全局工具

目前，.NET Core 命令行接口 (CLI) 中没有全局工具搜索功能。 下面提供有关如何查找工具的一些建议：

* 可在 [NuGet](https://www.nuget.org) 上查找 .NET Core 全局工具。 但是 NuGet 尚不能专门针对 .NET Core 全局工具进行搜索。
* 可在博客文章或 [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub 存储库中找到工具建议。
* 可以在 [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/tree/master/src/Tools) GitHub 存储库查看 ASP.NET 团队创建的全局工具的源代码。
* 可以在 [.NET Core dotnet 诊断全局工具](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools)中了解诊断工具。

## <a name="check-the-author-and-statistics"></a>查看作者和统计信息

由于 .NET Core 全局工具以完全信任的方式运行且通常安装在你的路径中，所以它们的作用会很强大。 请勿下载不信任的人提供的工具。

如果该工具在 NuGet 中托管，可以通过搜索该工具来查看作者和统计信息。

## <a name="install-a-global-tool"></a>安装全局工具

若要安装全局工具，请使用 [dotnet tool install](dotnet-tool-install.md) .NET Core CLI 命令。 下面的示例演示如何在默认位置安装全局工具：

```dotnetcli
dotnet tool install -g dotnetsay
```

如果无法安装该工具，则会显示错误消息。 检查所需源是否正在被检查。

如果想安装工具的预发布版本或特定版本，可以采用以下格式指定版本号：

```dotnetcli
dotnet tool install -g <package-name> --version <version-number>
```

如果安装成功，会出现一条消息，显示用于调用工具的命令以及所安装的版本，类似于以下示例：

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.0.0') was successfully installed.
```

全局工具可安装在默认目录或特定位置中。 默认目录为：

| (OS)          | 路径                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

这些位置在首次运行 SDK 时添加到用户的路径，所以可以直接调用安装在这里的全局工具。

请注意，全局工具是特定于用户的，而不是针对计算机全局的。 特定于用户的意思是无法在一台计算机上安装所有用户都可用的全局工具。 只有安装了该工具的用户配置文件才能使用它。

也可在特定目录安装全局工具。 如果在特定目录安装全局工具，用户必须确保命令是可用的，方法是将该目录添加至路径、使用指定目录调用命令或从特定目录调用该工具。
在这种情况下，.NET Core CLI 不将此地址自动添加至 PATH 环境变量。

## <a name="use-the-tool"></a>使用该工具

安装工具后，可以使用它的命令来调用它。 注意，该命令可能和包名称不同。

如果该命令为 `dotnetsay`，可以使用以下内容调用它：

```console
dotnetsay
```

如果工具作者希望工具出现在 `dotnet` 提示符的上下文中，他们可能采用称为 `dotnet <command>` 的方式进行编写，例如：

```dotnetcli
dotnet doc
```

若要查找安装的全局工具包中包含哪些工具，可以使用 [dotnet tool list](dotnet-tool-list.md) 命令列出安装的包。

若要查看使用说明，可以访问工具的网站或键入下列命令之一：

```console
<command> --help
dotnet <command> --help
```

## <a name="other-cli-commands"></a>其他 CLI 命令

.NET Core SDK 包含支持 .NET Core 全局工具的其他命令。 将 `dotnet tool` 命令用于以下选项之一：

* `--global` 或 `-g` 指定命令用于用户范围的全局工具。
* `--tool-path` 指定全局工具的自定义位置。

若要了解哪些命令可用于全局工具：

```dotnetcli
dotnet tool --help
```

更新全局工具涉及卸载该工具并重新安装它的最新稳定版。 若要更新全局工具，请使用 [dotnet tool update](dotnet-tool-update.md) 命令：

```dotnetcli
dotnet tool update -g <packagename>
```

使用 [dotnet tool uninstall](dotnet-tool-uninstall.md) 命令删除全局工具：

```dotnetcli
dotnet tool uninstall -g <packagename>
```

若要显示计算机上目前安装的所有全局工具及其版本和命令，请使用 [dotnet tool list](dotnet-tool-list.md) 命令：

```dotnetcli
dotnet tool list -g
```

## <a name="see-also"></a>请参阅

* [排查 .NET Core 工具使用问题](troubleshoot-usage-issues.md)
