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

## <a name="install-f-with-visual-studio"></a>使用 Visual Studio安装F#

如果在下载[Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)第一次，它将首先安装 Visual Studio 安装程序。 安装程序安装在相应 SKU 的 Visual Studio。 如果你已安装，请单击**修改**。

接下来，您将看到工作负荷列表。 选择**ASP.NET 和 web 开发**哪一项将安装F#ASP.NET Core 项目的支持和.NET Core 支持。

接下来，单击**修改**右下角中。  这将安装所选的所有内容。 然后可以打开带有 Visual Studio 2017F#语言支持通过单击**启动**。

## <a name="install-f-with-visual-studio-for-mac"></a>使用 Visual Studio for Mac安装F#

F#在默认情况下安装[Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)，无论哪种配置选择。

在安装完成后，选择"启动 Visual Studio"。 您还可以启动它通过 Finder 在 macOS 上。

## <a name="install-f-with-visual-studio-code"></a>使用 Visual Studio Code安装F#

您必须具有[安装 git](https://git-scm.com/download)且适用于你的路径以使项目模板使用。 你可以验证是否已正确安装通过键入`git --version`在命令提示符，然后按**Enter**。

### [macOS](#tab/macos)

[Mono](https://www.mono-project.com)用于[F#交互式](../tutorials/fsharp-interactive/index.md)支持。 通过 Homebrew 在 macOS 上安装 Mono 的最简单方法。 只需为你的终端中键入以下内容：

```console
brew install mono
```

此外安装[.NET Core SDK](https://www.microsoft.com/net/download)。

### [Linux](#tab/linux)

[Mono](https://www.mono-project.com)用于[F#交互式](../tutorials/fsharp-interactive/index.md)支持。 如果您在 Debian 或 Ubuntu 上，可以使用以下：

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

此外安装[.NET Core SDK](https://www.microsoft.com/net/download)。

### [Windows](#tab/windows)

安装[Visual Studio 中使用F#支持](#install-f-with-visual-studio)。 这将安装所有必要的组件来编写、 编译和执行F#代码。

此外安装[.NET Core SDK](https://www.microsoft.com/net/download/)。

---

你将需要先安装[Visual Studio Code](https://code.visualstudio.com)。

接下来，请单击扩展图标并搜索"Ionide":

[ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)是在 Visual Studio Code 中支持 F# 所需的唯一的插件。 然而，若要获取[FAKE](https://fsharp.github.io/FAKE/)支持，也可以安装[Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)、以及安装[Ionide paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)获取[paket](https://fsprojects.github.io/Paket/)支持。 FAKE 和 Paket 是其他用于生成项目并分别管理依赖项的 F# 社区工具。
