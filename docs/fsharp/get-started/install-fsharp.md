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
# <a name="install-f"></a><span data-ttu-id="d1b0d-103">安装 F\#</span><span class="sxs-lookup"><span data-stu-id="d1b0d-103">Install F\#</span></span>

<span data-ttu-id="d1b0d-104">可以通过多种方式安装 F#，具体取决于环境。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="d1b0d-105">使用 Visual Studio 安装 F#</span><span class="sxs-lookup"><span data-stu-id="d1b0d-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="d1b0d-106">如果是首次下载[Visual studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) ，它将首先安装 visual studio 安装程序。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="d1b0d-107">如果已安装它，请单击"修改"。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="d1b0d-108">如果已安装，请单击 "**修改**"。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="d1b0d-109">接下来会看到工作负荷列表。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="d1b0d-110">选择**ASP.NET 和 web 开发**，这将F#为 ASP.NET Core 项目安装支持和 .net Core 支持。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-110">Select **ASP.NET and web development** which will install F# support and .NET Core support for ASP.NET Core projects.</span></span>

<span data-ttu-id="d1b0d-111">接下来，单击右下方的 "**修改**"。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="d1b0d-112">这将安装所选的所有内容。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-112">This will install everything you have selected.</span></span> <span data-ttu-id="d1b0d-113">然后，可以通过单击 "**启动**" F# ，打开具有语言支持的 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="d1b0d-114">使用 Visual Studio Code 安装 F#</span><span class="sxs-lookup"><span data-stu-id="d1b0d-114">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="d1b0d-115">首先，请确保已[安装 git](https://git-scm.com/download)并可用于你的路径。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-115">First, ensure you have [git installed](https://git-scm.com/download) and available on your PATH.</span></span> <span data-ttu-id="d1b0d-116">可以通过在命令提示符下键入 `git --version` 并按**enter**来验证是否已正确安装它。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-116">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

<span data-ttu-id="d1b0d-117">接下来，安装[.NET Core SDK](https://dotnet.microsoft.com/download)。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-117">Next, install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="d1b0d-118">然后，需要安装[Visual Studio Code](https://code.visualstudio.com) 。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-118">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="d1b0d-119">接下来，单击 "扩展" 图标并搜索 "Ionide 入门"：</span><span class="sxs-lookup"><span data-stu-id="d1b0d-119">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="d1b0d-120">Visual Studio Code 中F#支持所需的唯一插件为[ionide 入门-fsharp.core](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-120">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="d1b0d-121">但是，你还可以安装[ionide 入门-虚设](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)以获取[虚假](https://fake.build/)支持，并[ionide 入门-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)获取[Paket](https://fsprojects.github.io/Paket/)支持。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-121">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fake.build/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="d1b0d-122">FAKE 和 Paket 是分别用于生成项目和管理依赖项的其他 F# 社区工具。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-122">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="d1b0d-123">使用 Visual Studio for Mac 安装 F#</span><span class="sxs-lookup"><span data-stu-id="d1b0d-123">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="d1b0d-124">F#默认情况下，在[Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)中安装，无论选择哪种配置。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-124">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="d1b0d-125">在安装完成后，请选择"启动 Visual Studio"。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-125">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="d1b0d-126">还可以通过 macOS 上的 Finder 启动它。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-126">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="d1b0d-127">在F#生成服务器上安装</span><span class="sxs-lookup"><span data-stu-id="d1b0d-127">Install F# on a Build Server</span></span>

<span data-ttu-id="d1b0d-128">如果通过 .NET SDK 使用 .NET Core 或 .NET Framework，只需在生成服务器上安装 .NET SDK。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-128">If you are using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="d1b0d-129">它包含你所需的一切。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-129">It has everything you need.</span></span>

<span data-ttu-id="d1b0d-130">如果使用的是 .NET Framework 而**不**是使用 .net SDK，则需要将[Visual Studio 生成工具 SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16)安装到 Windows Server 上。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-130">If you are using .NET Framework and you are **not** using the .NET SDK, then you will need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="d1b0d-131">在安装程序中，选择 " **.net 桌面生成工具**"，然后选择 "安装程序" 菜单右侧的 "  **F#编译器**" 组件。</span><span class="sxs-lookup"><span data-stu-id="d1b0d-131">In the installer, select **.NET desktop build tools** and then select the **F# compiler** component on the right side of the installer menu.</span></span>
