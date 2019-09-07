---
title: 安装 F#
description: 了解如何基于你F#的环境安装。
ms.date: 09/05/2019
ms.openlocfilehash: 18b660ff640904119d63f57405752a14f7673e0c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400723"
---
# <a name="install-f"></a>安装 F\#

可以通过多种方式安装 F#，具体取决于环境。

## <a name="install-f-with-visual-studio"></a>使用 Visual Studio 安装 F#

如果是初次下载 [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)，需首先安装 Visual Studio 安装程序。请从安装程序安装 Visual Studio 的相应 SKU。 如果已安装它，请单击"修改"。 如果已安装，请单击 "**修改**"。

接下来会看到工作负荷列表。 请选择 **"ASP.NET 和 Web 开发"** ，以便安装 F# 和 .NET Core 对 ASP.NET Core 项目的支持 。

接下来，单击右下角的 **"修改"** 。  这将安装所选的所有内容。 然后，可以通过单击 **"启动"** 打开带有 F# 语言支持的 Visual Studio 2017。

## <a name="install-f-with-visual-studio-for-mac"></a>使用 Visual Studio for Mac 安装 F#

在 [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) 中会默认安装 F#，无论选择哪种配置。

在安装完成后，请选择"启动 Visual Studio"。 还可以通过 macOS 上的 Finder 启动它。

## <a name="install-f-with-visual-studio-code"></a>使用 Visual Studio Code 安装 F#

必须先[安装 git](https://git-scm.com/download)，使之可以在 PATH 上使用，然后才能使用项目模板。 若要验证其是否已正确安装，可以在命令提示符处键入 `git --version`，然后按 **Enter**。

### <a name="macostabmacos"></a>[macOS](#tab/macos)

[Mono](https://www.mono-project.com)用于 [F# 交互式编程](../tutorials/fsharp-interactive/index.md)支持。 在 macOS 上安装 Mono 的最简单方法是使用 Homebrew。 只需在终端中键入以下命令即可：

```console
brew install mono
```

同时安装[.NET Core SDK](https://www.microsoft.com/net/download)。

### <a name="linuxtablinux"></a>[Linux](#tab/linux)

[Mono](https://www.mono-project.com)用于 [F# 交互式编程](../tutorials/fsharp-interactive/index.md)支持。 如果是在 Debian 或 Ubuntu 上操作，可以使用以下命令：

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

同时安装[.NET Core SDK](https://www.microsoft.com/net/download)。

### <a name="windowstabwindows"></a>[Windows](#tab/windows)

安装[带 F# 支持的 Visual Studio](#install-f-with-visual-studio)。 这将安装编写、编译和执行 F# 代码所需的所有组件。

同时安装[.NET Core SDK](https://www.microsoft.com/net/download/)。

---

然后需安装 [Visual Studio Code](https://code.visualstudio.com)。

接下来，单击 "扩展" 图标并搜索 "Ionide 入门"：

[ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) 是在 Visual Studio Code 中支持 F# 所需的唯一插件。 然而，也可以安装[Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) 来获取[FAKE](https://fsharp.github.io/FAKE/) 支持，以及安装[Ionide paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) 来获取 [paket](https://fsprojects.github.io/Paket/) 支持。 FAKE 和 Paket 是分别用于生成项目和管理依赖项的其他 F# 社区工具。

## <a name="install-f-on-a-build-server"></a>在F#生成服务器上安装

如果通过 .NET SDK 使用 .NET Core 或 .NET Framework，只需在生成服务器上安装 .NET SDK。 它包含你所需的一切。

如果使用的是 .NET Framework 而**不**是使用 .net SDK，则需要将[Visual Studio 生成工具 SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16)安装到 Windows Server 上。 在安装程序中，选择 " **.net 桌面生成工具**"，然后选择 "安装程序" 菜单右侧的 "  **F#编译器**" 组件。
