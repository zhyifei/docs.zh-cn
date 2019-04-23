---
title: 安装F#
description: 了解如何安装F#根据你的环境。
ms.date: 08/28/2018
ms.openlocfilehash: 792c61c0522cd4d0c68a64572f2892ce33f71ea6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331970"
---
# <a name="install-f"></a>安装 F\#

你可以通过多种方式安装F#，具体取决于你的环境。

## <a name="install-f-with-visual-studio"></a>使用 Visual Studio安装 F#

如果你是初次下载[Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)，它将首先安装 Visual Studio 安装程序。 从 Visual Studio 安装程序安装相应的 SKU。 如果你已安装 Visual Studio，请单击**修改**。

接下来，您将看到工作负荷列表。 选择**ASP.NET 和 web 开发**，这将为您安装 F# 和 .NET Core 对 ASP.NET Core 项目的支持。

接下来，单击右下角中的**修改**。这将安装您所选的所有内容。然后可以通过单击**启动**打开带有 F# 语言支持的 Visual Studio 2017。

## <a name="install-f-with-visual-studio-for-mac"></a>使用 Visual Studio for Mac安装 F#

在[Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)中将会默认安装 F#，无论您选择哪种配置。

在安装完成后，选择"启动 Visual Studio"。 您还可以通过macOS 上的 Finder 启动它。

## <a name="install-f-with-visual-studio-code"></a>使用 Visual Studio Code安装 F#

您必须先[安装 git](https://git-scm.com/download)且适用于你的路径以使用项目模板。 你可以通过在命令提示符键入`git --version`，然后按**Enter**验证是否已正确安装。

### [macOS](#tab/macos)

[Mono](https://www.mono-project.com)用于 [F# 交互式](../tutorials/fsharp-interactive/index.md)支持。 在 macOS 上安装 Mono 的最简单方法是通过 Homebrew 进行安装。 只需在你的终端中键入以下内容：

```console
brew install mono
```

此外安装[.NET Core SDK](https://www.microsoft.com/net/download)。

### [Linux](#tab/linux)

[Mono](https://www.mono-project.com)用于[F# 交互式](../tutorials/fsharp-interactive/index.md)支持。 如果您在 Debian 或 Ubuntu 上，可以使用以下：

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

此外安装[.NET Core SDK](https://www.microsoft.com/net/download)。

### [Windows](#tab/windows)

安装[Visual Studio 上的 F# 支持](#install-f-with-visual-studio)。 这将安装所有编写、 编译和执行 F# 代码所必要的组件。

此外安装[.NET Core SDK](https://www.microsoft.com/net/download/)。

---

你将需要先安装[Visual Studio Code](https://code.visualstudio.com)。

接下来，请单击扩展图标并搜索"Ionide":

[ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)是在 Visual Studio Code 中支持 F# 所需的唯一的插件。 然而，若要获取[FAKE](https://fsharp.github.io/FAKE/)支持，也可以安装[Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)、以及安装[Ionide paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)获取[paket](https://fsprojects.github.io/Paket/)支持。 FAKE 和 Paket 是其他用于生成项目并分别管理依赖项的 F# 社区工具。
