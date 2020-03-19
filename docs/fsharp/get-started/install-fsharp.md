---
title: 安装 F#
description: 了解如何以各种不同方式安装 F#。
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401093"
---
# <a name="install-f"></a>安装 F\#

您可以根据环境以多种方式安装 F#。

## <a name="install-f-with-visual-studio"></a>使用可视化工作室安装 F#

1. 如果您是首次下载[可视化工作室](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)，它将首先安装可视化工作室安装程序。 从安装程序安装相应的视觉工作室版本。

   如果已安装 Visual Studio，请选择要向其添加 F# 的版本旁边的 **"修改**"。

2. 在"工作负载"页上，选择**ASP.NET和 Web 开发**工作负载，其中包括 ASP.NET核心项目的 F# 和 .NET Core 支持。

3. 在右下角选择 **"修改"** 以安装您选择的所有内容。

   然后，您可以通过选择"在可视化工作室安装程序中**启动"** 来打开带有 F# 的可视化工作室。

## <a name="install-f-with-visual-studio-code"></a>使用可视化工作室代码安装 F#

1. 确保您已安装[git](https://git-scm.com/download)并在您的 PATH 上可用。 您可以通过在命令提示符处输入`git --version`并按**Enter**来验证其安装是否正确。

2. 安装[.NET 核心 SDK](https://dotnet.microsoft.com/download)和[可视化工作室代码](https://code.visualstudio.com)。

3. 选择"扩展"图标并搜索"Ionide"：

   在视觉工作室代码中 F# 支持的唯一插件是[Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)。 但是，您也可以安装[Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)以获得[FAKE](https://fake.build/)支持和[Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)以获得[Paket](https://fsprojects.github.io/Paket/)支持。 FAKE 和 Paket 是用于构建项目和管理依赖项的其他 F# 社区工具。

## <a name="install-f-with-visual-studio-for-mac"></a>安装 F# 与 Mac 的视觉工作室

F# 默认安装在[Mac 的 Visual Studio](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)中，无论您选择哪种配置。

安装完成后，选择 **"开始可视化工作室**"。 您还可以在 macOS 上通过 Finder 打开视觉工作室。

## <a name="install-f-on-a-build-server"></a>在生成服务器上安装 F#

如果您通过 .NET SDK 使用 .NET Core 或 .NET 框架，只需在生成服务器上安装 .NET SDK 即可。 它有你需要的一切。

如果您使用的是 .NET 框架，**并且没有**使用 .NET SDK，则需要将[可视化工作室构建工具 SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16)安装到 Windows 服务器上。 在安装程序中，选择 **.NET 桌面生成工具**，然后在安装程序菜单右侧选择**F# 编译器**组件。
