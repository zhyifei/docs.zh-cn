---
title: 在 Windows、Linux 和 macOS 上安装 .NET Core SDK - .NET Core
description: 了解如何在 Windows、Linux 和 macOS 上安装 .NET Core。 发现开发 .NET Core 应用所需的依赖项。
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 1f7efaedaa1a0be90f7b619f954bdf78eecafa07
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2019
ms.locfileid: "74999061"
---
# <a name="install-the-net-core-sdk"></a>安装 .NET Core SDK

本文介绍如何安装 .NET Core SDK。 .NET Core SDK 用于创建 .NET Core 应用和库。 .NET Core 运行时始终随 SDK 一起安装。

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a>使用安装程序安装

Windows 具有独立的安装程序，可用于安装 .NET Core 3.1 SDK：

- [x64（64 位）CPU](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [x86（32 位）CPU](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a>使用安装程序安装

macOS 具有独立的安装程序，可用于安装 .NET Core 3.1 SDK：

- [x64（64 位）CPU](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a>使用包管理器安装

可使用许多常见的 Linux 包管理器安装 .NET Core SDK。 有关详细信息，请参阅 [Linux 包管理器 - 安装 .NET Core](linux-package-managers.md)。

## <a name="download-and-manually-install"></a>下载并手动安装

若要提取 SDK 并使命令可用于终端，请先[下载](#all-net-core-downloads) .NET Core 二进制版本。 然后，打开终端并运行以下命令。

```bash
mkdir -p $HOME/dotnet && tar zxf dotnet-sdk-3.1.100-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> 上述命令只会使 .NET SDK 命令对运行它的终端会话可用。
>
> 你可以编辑 shell 配置文件，永久地添加这些命令。 Linux 提供了许多不同的 shell，每个都有不同的配置文件。 例如:
>
> - **Bash Shell**：~/.bash_profile  、~/.bashrc 
> - **Korn Shell**：~/.kshrc  或 .profile 
> - **Z Shell**：~/.zshrc  或 .zprofile 
> 
> 为 shell 编辑相应的源文件，并将 `:$HOME/dotnet` 添加到现有 `PATH` 语句的末尾。 如果不包含 `PATH` 语句，则使用 `export PATH=$PATH:$HOME/dotnet` 添加新行。
>
> 另外，将 `export DOTNET_ROOT=$HOME/dotnet` 添加至文件的末尾。

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a>使用 Visual Studio 安装

如果你要使用 Visual Studio 开发 .NET Core 应用，请参阅下表，了解不同目标 .NET Core SDK 版本所需的 Visual Studio 最低版本。

| .NET Core SDK 版本 | Visual Studio 版本                      |
| --------------------- | ------------------------------------------ |
| 3.1                   | Visual Studio 2019 版本 16.4 或更高版本。 |
| 3.0                   | Visual Studio 2019 版本 16.3 或更高版本。 |
| 2.2                   | Visual Studio 2017 版本 15.9 或更高版本。 |
| 2.1                   | Visual Studio 2017 版本 15.7 或更高版本。 |

如果你已安装 Visual Studio，则可以使用以下步骤检查你的版本。

01. 打开 Visual Studio。
01. 选择“帮助”   > “Microsoft Visual Studio”  。
01. 从“关于”  对话框中读取版本号。

Visual Studio 可安装最新的 .NET Core SDK 和运行时。

- [下载 Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)。

### <a name="select-a-workload"></a>选择工作负载

安装或修改 Visual Studio 时，根据要生成的应用程序的类型，选择下列一种工作负载：

- “其他工具集”部分中的“.NET Core 跨平台开发”工作负荷   。
- “Web 和云”部分中的“ASP.NET 和 Web 开发”工作负荷   。
- “Web 和云”部分中的“Azure 开发”工作负载   。
- “桌面和移动”部分中的“NET 桌面开发”工作负载   。

[![具有 .NET Core 工作负载的 Windows Visual Studio 2019](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a>使用 Visual Studio for Mac 安装

在选定“.NET Core”  工作负载时，使用 Visual Studio for Mac 安装 .NET Core SDK。 若要开始在 macOS 上进行 .NET Core 开发，请参阅[安装 Visual Studio 2019 for Mac](/visualstudio/mac/installation)。 对于最新的版本 .NET Core 3.1，则必须使用 Visual Studio for Mac 8.4 预览版。

[![具有 .NET Core 工作负载功能的 macOS Visual Studio 2019 for Mac](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)

::: zone-end

## <a name="install-alongside-visual-studio-code"></a>随 Visual Studio Code 一起安装

Visual Studio Code 是一个功能强大的轻量级源代码编辑器，可在桌面上运行。 Visual Studio Code 适用于 Windows、macOS 和 Linux。

虽然 Visual Studio Code 不像 Visual Studio 一样附带自动的 .NET Core 安装程序，但添加 .NET Core 支持非常简单。

01. [下载并安装 Visual Studio Code](https://code.visualstudio.com/Download)。
01. [下载并安装 .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core)。
01. [从 Visual Studio Code 市场安装 C# 扩展](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)。

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a>使用 PowerShell 自动化安装

[dotnet-install 脚本](../tools/dotnet-install-script.md)用于 SDK 的自动化和非管理员安装。 可从 [dotnet-install 脚本引用页](../tools/dotnet-install-script.md)下载该脚本。

此脚本默认安装最新的[长期支持 (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 版本，即 .NET Core 2.1。 若要安装最新版本的 .NET Core，请使用以下开关运行脚本。

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a>使用 Bash 自动化安装

[dotnet-install 脚本](../tools/dotnet-install-script.md)用于 SDK 的自动化和非管理员安装。 可从 [dotnet-install 脚本引用页](../tools/dotnet-install-script.md)下载该脚本。

此脚本默认安装最新的[长期支持 (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 版本，即 .NET Core 2.1。 若要安装最新版本的 .NET Core，请使用以下开关运行脚本。

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a>所有 .NET Core 下载项

可直接通过以下链接之一下载和安装 .NET Core：

- [.NET Core 3.1 下载](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [.NET Core 3.0 下载](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [.NET Core 2.2 下载](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [.NET Core 2.1 下载](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a>Docker

容器提供了一种将应用程序与主机系统的其余部分隔离的轻量级方法。 同一计算机上的容器只共享内核，并使用为应用程序提供的资源。

.NET Core 可在 Docker 容器中运行。 官方 .NET Core Docker 映像发布到 Microsoft 容器注册表 (MCR)，用户可以在 [Microsoft.NET Core Docker 中心存储库](https://hub.docker.com/_/microsoft-dotnet-core/)中找到这些映像。 每个存储库包含 .NET（SDK 或运行时）和可以使用的操作系统的不同组合的映像。

Microsoft 提供适合特定场景的映像。 例如，[ASP.NET Core 存储库](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)提供针对在生产环境中运行 ASP.NET Core 应用生成的映像。

有关在 Docker 容器中使用 .NET Core 的详细信息，请参阅 [.NET 和 Docker 简介](../docker/introduction.md)和[示例](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)。

## <a name="next-steps"></a>后续步骤

::: zone pivot="os-windows"

- [教程：C# Hello World 教程](../tutorials/with-visual-studio.md)。
- [教程：Visual Basic Hello World 教程](../tutorials/vb-with-visual-studio.md)。
- [教程：使用 Visual Studio Code 创建一个新应用](../tutorials/with-visual-studio-code.md)。
- [教程：使 .NET Core 应用容器化](../docker/build-container.md)。

::: zone-end

::: zone pivot="os-macos"

- [教程：开始使用 macOS](../tutorials/using-on-mac-vs.md)。
- [教程：使用 Visual Studio Code 创建一个新应用](../tutorials/with-visual-studio-code.md)。
- [教程：使 .NET Core 应用容器化](../docker/build-container.md)。

::: zone-end

::: zone pivot="os-linux"

- [教程：使用 Visual Studio Code 创建一个新应用](../tutorials/with-visual-studio-code.md)。
- [教程：使 .NET Core 应用容器化](../docker/build-container.md)。

::: zone-end
