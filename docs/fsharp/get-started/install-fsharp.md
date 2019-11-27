---
title: 安装 F#
description: 了解如何基于你F#的环境安装。
ms.date: 09/05/2019
ms.openlocfilehash: 592a4c7763266cee68809fca84f9604d7e96b8f1
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204876"
---
# <a name="install-f"></a>安装 F\#

可以通过多种方式安装 F#，具体取决于环境。

## <a name="install-f-with-visual-studio"></a>使用 Visual Studio 安装 F#

如果是首次下载[Visual studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) ，它将首先安装 visual studio 安装程序。 如果已安装它，请单击"修改"。 如果已安装，请单击 "**修改**"。

接下来会看到工作负荷列表。 选择**ASP.NET 和 web 开发**，这将F#为 ASP.NET Core 项目安装支持和 .net Core 支持。

接下来，单击右下方的 "**修改**"。  这将安装所选的所有内容。 然后，可以通过单击 "**启动**" F# ，打开具有语言支持的 Visual Studio 2017。

## <a name="install-f-with-visual-studio-code"></a>使用 Visual Studio Code 安装 F#

首先，请确保已[安装 git](https://git-scm.com/download)并可用于你的路径。 可以通过在命令提示符下键入 `git --version` 并按**enter**来验证是否已正确安装它。

接下来，安装[.NET Core SDK](https://dotnet.microsoft.com/download)。

然后，需要安装[Visual Studio Code](https://code.visualstudio.com) 。

接下来，单击 "扩展" 图标并搜索 "Ionide 入门"：

Visual Studio Code 中F#支持所需的唯一插件为[ionide 入门-fsharp.core](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)。 但是，你还可以安装[ionide 入门-虚设](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)以获取[虚假](https://fake.build/)支持，并[ionide 入门-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)获取[Paket](https://fsprojects.github.io/Paket/)支持。 FAKE 和 Paket 是分别用于生成项目和管理依赖项的其他 F# 社区工具。

## <a name="install-f-with-visual-studio-for-mac"></a>使用 Visual Studio for Mac 安装 F#

F#默认情况下，在[Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)中安装，无论选择哪种配置。

在安装完成后，请选择"启动 Visual Studio"。 还可以通过 macOS 上的 Finder 启动它。

## <a name="install-f-on-a-build-server"></a>在F#生成服务器上安装

如果通过 .NET SDK 使用 .NET Core 或 .NET Framework，只需在生成服务器上安装 .NET SDK。 它包含你所需的一切。

如果使用的是 .NET Framework 而**不**是使用 .net SDK，则需要将[Visual Studio 生成工具 SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16)安装到 Windows Server 上。 在安装程序中，选择 " **.net 桌面生成工具**"，然后选择 "安装程序" 菜单右侧的 "  **F#编译器**" 组件。
