---
title: '安装 F #'
description: '了解如何安装 F # 根据您的环境。'
ms.date: 08/28/2018
ms.openlocfilehash: d53ecdcba5411db62208cb683a0fad795711b77c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50193898"
---
# <a name="install-f"></a>安装 F # #

你可以安装 F # 中通过多种方式，具体取决于你的环境。

## <a name="install-f-with-visual-studio"></a>使用 Visual Studio 安装 F #

如果在下载[Visual Studio](https://visualstudio.microsoft.com/)第一次，它将首先安装 Visual Studio 安装程序。 安装程序安装在相应 SKU 的 Visual Studio。 如果你已安装，请单击**修改**。

接下来，您将看到工作负荷列表。 选择**ASP.NET 和 web 开发**这将安装 F # 支持和对 ASP.NET Core 项目的.NET Core 支持。

接下来，单击**修改**右下角中。  这将安装所选的所有内容。 随后可打开 Visual Studio 2017 的 F # 语言支持通过单击**启动**。

## <a name="install-f-with-visual-studio-for-mac"></a>安装 F # 与 Visual Studio for Mac

F # 中默认情况下安装[Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/)，无论哪种配置选择。

在安装完成后，选择"启动 Visual Studio"。 您还可以启动它通过 Finder 在 macOS 上。

## <a name="install-f-with-visual-studio-code"></a>使用 Visual Studio Code 中安装 F #

您必须具有[安装 git](https://git-scm.com/download)且适用于你的路径以使项目模板使用。 你可以验证是否已正确安装通过键入`git --version`在命令提示符，然后按**Enter**。

### <a name="macostabmacos"></a>[macOS](#tab/macos)

[Mono](https://www.mono-project.com)用于[F # Interactive](../tutorials/fsharp-interactive/index.md)支持。 通过 Homebrew 在 macOS 上安装 Mono 的最简单方法。 只需为你的终端中键入以下内容：

```console
brew install mono
```

此外安装[.NET Core SDK](https://www.microsoft.com/net/download)。

### <a name="linuxtablinux"></a>[Linux](#tab/linux)

[Mono](https://www.mono-project.com)用于[F # Interactive](../tutorials/fsharp-interactive/index.md)支持。 如果您在 Debian 或 Ubuntu 上，可以使用以下：

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

此外安装[.NET Core SDK](https://www.microsoft.com/net/download)。

### <a name="windowstabwindows"></a>[Windows](#tab/windows)

安装[Visual Studio 中使用 F # 支持](#install-f-with-visual-studio)。 这会安装所有必要的组件来编写、 编译和执行 F # 代码。

此外安装[.NET Core SDK](https://www.microsoft.com/net/download/)。

---

然后，你将需要[Visual Studio Code](https://code.visualstudio.com)安装。

接下来，请单击扩展图标并搜索"Ionide":

F # 支持在 Visual Studio Code 所需的唯一插件[ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)。 但是，也可以安装[Ionide 虚设](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)若要获取[FAKE](https://fsharp.github.io/FAKE/)支持并[Ionide paket 依存](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)获取[paket 依存](https://fsprojects.github.io/Paket/)支持。 虚设和 paket 依存是其他 F # 社区工具来生成项目并管理依赖项，分别。
