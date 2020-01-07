---
title: 安装 F#
description: 了解如何以各种F#不同的方式安装。
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346566"
---
# <a name="install-f"></a><span data-ttu-id="aa8ac-103">安装 F\#</span><span class="sxs-lookup"><span data-stu-id="aa8ac-103">Install F\#</span></span>

<span data-ttu-id="aa8ac-104">可以通过多种方式安装 F#，具体取决于环境。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="aa8ac-105">使用 Visual Studio 安装 F#</span><span class="sxs-lookup"><span data-stu-id="aa8ac-105">Install F# with Visual Studio</span></span>

1. <span data-ttu-id="aa8ac-106">如果是首次下载[Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) ，则会先安装 Visual Studio 安装程序。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for the first time, it will first install Visual Studio Installer.</span></span> <span data-ttu-id="aa8ac-107">从安装程序安装适当版本的 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-107">Install the appropriate edition of Visual Studio from the installer.</span></span>

   <span data-ttu-id="aa8ac-108">如果已安装 Visual Studio，请选择要添加F#到的版本旁边的 "修改"。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-108">If you already have Visual Studio installed, choose **Modify** next to the edition you want to add F# to.</span></span>

2. <span data-ttu-id="aa8ac-109">在 "工作负荷" 页上，选择 " **ASP.NET" 和 "web 开发**" 工作负载，其中包括F#和 .net Core 对 ASP.NET Core 项目的支持。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-109">On the Workloads page, select the **ASP.NET and web development** workload, which includes F# and .NET Core support for ASP.NET Core projects.</span></span>

3. <span data-ttu-id="aa8ac-110">选择右下角的 "**修改**"，安装所选的所有内容。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-110">Choose **Modify** in the lower right-hand corner to install everything you've selected.</span></span>

   <span data-ttu-id="aa8ac-111">然后，可以F#通过选择 "在 Visual Studio 安装程序中**启动**" 打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-111">You can then open Visual Studio with F# by choosing **Launch** in Visual Studio Installer.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="aa8ac-112">使用 Visual Studio Code 安装 F#</span><span class="sxs-lookup"><span data-stu-id="aa8ac-112">Install F# with Visual Studio Code</span></span>

1. <span data-ttu-id="aa8ac-113">确保已安装[git](https://git-scm.com/download)并可用于你的路径。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-113">Ensure you have [git](https://git-scm.com/download) installed and available on your PATH.</span></span> <span data-ttu-id="aa8ac-114">可以通过在命令提示符下输入 `git --version` 并按**enter**来验证它是否已正确安装。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-114">You can verify that it's installed correctly by entering `git --version` at a command prompt and pressing **Enter**.</span></span>

2. <span data-ttu-id="aa8ac-115">安装[.NET Core SDK](https://dotnet.microsoft.com/download)和[Visual Studio Code](https://code.visualstudio.com)。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-115">Install the [.NET Core SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com).</span></span>

3. <span data-ttu-id="aa8ac-116">选择扩展图标，然后搜索 "Ionide 入门"：</span><span class="sxs-lookup"><span data-stu-id="aa8ac-116">Select the Extensions icon and search for "Ionide":</span></span>

   <span data-ttu-id="aa8ac-117">[ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) 是在 Visual Studio Code 中支持 F# 所需的唯一插件。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-117">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="aa8ac-118">然而，也可以安装[Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) 来获取[FAKE](https://fake.build/) 支持，以及安装[Ionide paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) 来获取 [paket](https://fsprojects.github.io/Paket/) 支持。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-118">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fake.build/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="aa8ac-119">FAKE 和 Paket 是分别用于生成项目和管理依赖项的其他 F# 社区工具。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-119">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="aa8ac-120">使用 Visual Studio for Mac 安装 F#</span><span class="sxs-lookup"><span data-stu-id="aa8ac-120">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="aa8ac-121">在 [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) 中会默认安装 F#，无论选择哪种配置。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-121">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="aa8ac-122">安装完成后，选择 "**启动 Visual Studio**"。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-122">After the install completes, choose **Start Visual Studio**.</span></span> <span data-ttu-id="aa8ac-123">还可以通过 macOS 上的查找器打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-123">You can also open Visual Studio through Finder on macOS.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="aa8ac-124">在F#生成服务器上安装</span><span class="sxs-lookup"><span data-stu-id="aa8ac-124">Install F# on a build server</span></span>

<span data-ttu-id="aa8ac-125">如果通过 .NET SDK 使用 .NET Core 或 .NET Framework，只需在生成服务器上安装 .NET SDK。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-125">If you're using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="aa8ac-126">它包含你所需的一切。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-126">It has everything you need.</span></span>

<span data-ttu-id="aa8ac-127">如果使用的是 .NET Framework 而**不**是使用 .net SDK，则需要将[Visual Studio 生成工具 SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16)安装到 Windows Server 上。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-127">If you're using .NET Framework and you are **not** using the .NET SDK, then you'll need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="aa8ac-128">在安装程序中，选择 " **.net 桌面生成工具**"，然后选择 "安装程序" 菜单右侧的 "  **F#编译器**" 组件。</span><span class="sxs-lookup"><span data-stu-id="aa8ac-128">In the installer, select **.NET desktop build tools**, and then select the **F# compiler** component on the right-hand side of the installer menu.</span></span>
