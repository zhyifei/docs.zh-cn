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
# <a name="install-f"></a><span data-ttu-id="18a91-103">安装 F\#</span><span class="sxs-lookup"><span data-stu-id="18a91-103">Install F\#</span></span>

<span data-ttu-id="18a91-104">您可以根据环境以多种方式安装 F#。</span><span class="sxs-lookup"><span data-stu-id="18a91-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="18a91-105">使用可视化工作室安装 F#</span><span class="sxs-lookup"><span data-stu-id="18a91-105">Install F# with Visual Studio</span></span>

1. <span data-ttu-id="18a91-106">如果您是首次下载[可视化工作室](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)，它将首先安装可视化工作室安装程序。</span><span class="sxs-lookup"><span data-stu-id="18a91-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for the first time, it will first install Visual Studio Installer.</span></span> <span data-ttu-id="18a91-107">从安装程序安装相应的视觉工作室版本。</span><span class="sxs-lookup"><span data-stu-id="18a91-107">Install the appropriate edition of Visual Studio from the installer.</span></span>

   <span data-ttu-id="18a91-108">如果已安装 Visual Studio，请选择要向其添加 F# 的版本旁边的 **"修改**"。</span><span class="sxs-lookup"><span data-stu-id="18a91-108">If you already have Visual Studio installed, choose **Modify** next to the edition you want to add F# to.</span></span>

2. <span data-ttu-id="18a91-109">在"工作负载"页上，选择**ASP.NET和 Web 开发**工作负载，其中包括 ASP.NET核心项目的 F# 和 .NET Core 支持。</span><span class="sxs-lookup"><span data-stu-id="18a91-109">On the Workloads page, select the **ASP.NET and web development** workload, which includes F# and .NET Core support for ASP.NET Core projects.</span></span>

3. <span data-ttu-id="18a91-110">在右下角选择 **"修改"** 以安装您选择的所有内容。</span><span class="sxs-lookup"><span data-stu-id="18a91-110">Choose **Modify** in the lower right-hand corner to install everything you've selected.</span></span>

   <span data-ttu-id="18a91-111">然后，您可以通过选择"在可视化工作室安装程序中**启动"** 来打开带有 F# 的可视化工作室。</span><span class="sxs-lookup"><span data-stu-id="18a91-111">You can then open Visual Studio with F# by choosing **Launch** in Visual Studio Installer.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="18a91-112">使用可视化工作室代码安装 F#</span><span class="sxs-lookup"><span data-stu-id="18a91-112">Install F# with Visual Studio Code</span></span>

1. <span data-ttu-id="18a91-113">确保您已安装[git](https://git-scm.com/download)并在您的 PATH 上可用。</span><span class="sxs-lookup"><span data-stu-id="18a91-113">Ensure you have [git](https://git-scm.com/download) installed and available on your PATH.</span></span> <span data-ttu-id="18a91-114">您可以通过在命令提示符处输入`git --version`并按**Enter**来验证其安装是否正确。</span><span class="sxs-lookup"><span data-stu-id="18a91-114">You can verify that it's installed correctly by entering `git --version` at a command prompt and pressing **Enter**.</span></span>

2. <span data-ttu-id="18a91-115">安装[.NET 核心 SDK](https://dotnet.microsoft.com/download)和[可视化工作室代码](https://code.visualstudio.com)。</span><span class="sxs-lookup"><span data-stu-id="18a91-115">Install the [.NET Core SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com).</span></span>

3. <span data-ttu-id="18a91-116">选择"扩展"图标并搜索"Ionide"：</span><span class="sxs-lookup"><span data-stu-id="18a91-116">Select the Extensions icon and search for "Ionide":</span></span>

   <span data-ttu-id="18a91-117">在视觉工作室代码中 F# 支持的唯一插件是[Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)。</span><span class="sxs-lookup"><span data-stu-id="18a91-117">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="18a91-118">但是，您也可以安装[Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)以获得[FAKE](https://fake.build/)支持和[Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)以获得[Paket](https://fsprojects.github.io/Paket/)支持。</span><span class="sxs-lookup"><span data-stu-id="18a91-118">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fake.build/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="18a91-119">FAKE 和 Paket 是用于构建项目和管理依赖项的其他 F# 社区工具。</span><span class="sxs-lookup"><span data-stu-id="18a91-119">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="18a91-120">安装 F# 与 Mac 的视觉工作室</span><span class="sxs-lookup"><span data-stu-id="18a91-120">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="18a91-121">F# 默认安装在[Mac 的 Visual Studio](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)中，无论您选择哪种配置。</span><span class="sxs-lookup"><span data-stu-id="18a91-121">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="18a91-122">安装完成后，选择 **"开始可视化工作室**"。</span><span class="sxs-lookup"><span data-stu-id="18a91-122">After the install completes, choose **Start Visual Studio**.</span></span> <span data-ttu-id="18a91-123">您还可以在 macOS 上通过 Finder 打开视觉工作室。</span><span class="sxs-lookup"><span data-stu-id="18a91-123">You can also open Visual Studio through Finder on macOS.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="18a91-124">在生成服务器上安装 F#</span><span class="sxs-lookup"><span data-stu-id="18a91-124">Install F# on a build server</span></span>

<span data-ttu-id="18a91-125">如果您通过 .NET SDK 使用 .NET Core 或 .NET 框架，只需在生成服务器上安装 .NET SDK 即可。</span><span class="sxs-lookup"><span data-stu-id="18a91-125">If you're using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="18a91-126">它有你需要的一切。</span><span class="sxs-lookup"><span data-stu-id="18a91-126">It has everything you need.</span></span>

<span data-ttu-id="18a91-127">如果您使用的是 .NET 框架，**并且没有**使用 .NET SDK，则需要将[可视化工作室构建工具 SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16)安装到 Windows 服务器上。</span><span class="sxs-lookup"><span data-stu-id="18a91-127">If you're using .NET Framework and you are **not** using the .NET SDK, then you'll need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="18a91-128">在安装程序中，选择 **.NET 桌面生成工具**，然后在安装程序菜单右侧选择**F# 编译器**组件。</span><span class="sxs-lookup"><span data-stu-id="18a91-128">In the installer, select **.NET desktop build tools**, and then select the **F# compiler** component on the right-hand side of the installer menu.</span></span>
