---
title: 安装F#
description: 了解如何安装F#根据你的环境。
ms.date: 08/28/2018
ms.openlocfilehash: 792c61c0522cd4d0c68a64572f2892ce33f71ea6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62017015"
---
# <a name="install-f"></a><span data-ttu-id="2301f-103">安装 F\#</span><span class="sxs-lookup"><span data-stu-id="2301f-103">Install F\#</span></span>

<span data-ttu-id="2301f-104">可以通过多种方式安装 F#，具体取决于环境。</span><span class="sxs-lookup"><span data-stu-id="2301f-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="2301f-105">使用 Visual Studio 安装 F#</span><span class="sxs-lookup"><span data-stu-id="2301f-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="2301f-106">如果是初次下载 [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)，需首先安装 Visual Studio 安装程序。请从安装程序安装 Visual Studio 的相应 SKU。</span><span class="sxs-lookup"><span data-stu-id="2301f-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="2301f-107">如果已安装它，请单击"修改"。</span><span class="sxs-lookup"><span data-stu-id="2301f-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="2301f-108">如果你已安装，请单击**修改**。</span><span class="sxs-lookup"><span data-stu-id="2301f-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="2301f-109">接下来会看到工作负荷列表。</span><span class="sxs-lookup"><span data-stu-id="2301f-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="2301f-110">请选择 **"ASP.NET 和 Web 开发"**，以便安装 F# 和 .NET Core 对 ASP.NET Core 项目的支持 。</span><span class="sxs-lookup"><span data-stu-id="2301f-110">Select **ASP.NET and web development** which will install F# support and .NET Core support for ASP.NET Core projects.</span></span>

<span data-ttu-id="2301f-111">接下来，单击右下角的 **"修改"**。</span><span class="sxs-lookup"><span data-stu-id="2301f-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="2301f-112">这将安装所选的所有内容。</span><span class="sxs-lookup"><span data-stu-id="2301f-112">This will install everything you have selected.</span></span> <span data-ttu-id="2301f-113">然后，可以通过单击 **"启动"** 打开带有 F# 语言支持的 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="2301f-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="2301f-114">使用 Visual Studio for Mac 安装 F#</span><span class="sxs-lookup"><span data-stu-id="2301f-114">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="2301f-115">在 [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) 中会默认安装 F#，无论选择哪种配置。</span><span class="sxs-lookup"><span data-stu-id="2301f-115">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="2301f-116">在安装完成后，请选择"启动 Visual Studio"。</span><span class="sxs-lookup"><span data-stu-id="2301f-116">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="2301f-117">还可以通过 macOS 上的 Finder 启动它。</span><span class="sxs-lookup"><span data-stu-id="2301f-117">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="2301f-118">使用 Visual Studio Code 安装 F#</span><span class="sxs-lookup"><span data-stu-id="2301f-118">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="2301f-119">必须先[安装 git](https://git-scm.com/download)，使之可以在 PATH 上使用，然后才能使用项目模板。</span><span class="sxs-lookup"><span data-stu-id="2301f-119">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates.</span></span> <span data-ttu-id="2301f-120">若要验证其是否已正确安装，可以在命令提示符处键入 `git --version`，然后按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="2301f-120">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="2301f-121">macOS</span><span class="sxs-lookup"><span data-stu-id="2301f-121">macOS</span></span>](#tab/macos)

<span data-ttu-id="2301f-122">[Mono](https://www.mono-project.com)用于 [F# 交互式编程](../tutorials/fsharp-interactive/index.md)支持。</span><span class="sxs-lookup"><span data-stu-id="2301f-122">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="2301f-123">在 macOS 上安装 Mono 的最简单方法是使用 Homebrew。</span><span class="sxs-lookup"><span data-stu-id="2301f-123">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="2301f-124">只需在终端中键入以下命令即可：</span><span class="sxs-lookup"><span data-stu-id="2301f-124">Simply type the following into your terminal:</span></span>

```console
brew install mono
```

<span data-ttu-id="2301f-125">此外安装[.NET Core SDK](https://www.microsoft.com/net/download)。</span><span class="sxs-lookup"><span data-stu-id="2301f-125">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="2301f-126">Linux</span><span class="sxs-lookup"><span data-stu-id="2301f-126">Linux</span></span>](#tab/linux)

<span data-ttu-id="2301f-127">[Mono](https://www.mono-project.com)用于 [F# 交互式编程](../tutorials/fsharp-interactive/index.md)支持。</span><span class="sxs-lookup"><span data-stu-id="2301f-127">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="2301f-128">如果是在 Debian 或 Ubuntu 上操作，可以使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="2301f-128">If you're on Debian or Ubuntu, you can use the following:</span></span>

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="2301f-129">此外安装[.NET Core SDK](https://www.microsoft.com/net/download)。</span><span class="sxs-lookup"><span data-stu-id="2301f-129">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="2301f-130">Windows</span><span class="sxs-lookup"><span data-stu-id="2301f-130">Windows</span></span>](#tab/windows)

<span data-ttu-id="2301f-131">安装[带 F# 支持的 Visual Studio](#install-f-with-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="2301f-131">Install [Visual Studio with F# support](#install-f-with-visual-studio).</span></span> <span data-ttu-id="2301f-132">这将安装编写、编译和执行 F# 代码所需的所有组件。</span><span class="sxs-lookup"><span data-stu-id="2301f-132">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="2301f-133">此外安装[.NET Core SDK](https://www.microsoft.com/net/download/)。</span><span class="sxs-lookup"><span data-stu-id="2301f-133">Also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

<span data-ttu-id="2301f-134">然后需安装 [Visual Studio Code](https://code.visualstudio.com)。</span><span class="sxs-lookup"><span data-stu-id="2301f-134">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="2301f-135">接下来，请单击扩展图标并搜索"Ionide":</span><span class="sxs-lookup"><span data-stu-id="2301f-135">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="2301f-136">[ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) 是在 Visual Studio Code 中支持 F# 所需的唯一插件。</span><span class="sxs-lookup"><span data-stu-id="2301f-136">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="2301f-137">然而，也可以安装[Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) 来获取[FAKE](https://fsharp.github.io/FAKE/) 支持，以及安装[Ionide paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) 来获取 [paket](https://fsprojects.github.io/Paket/) 支持。</span><span class="sxs-lookup"><span data-stu-id="2301f-137">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="2301f-138">FAKE 和 Paket 是分别用于生成项目和管理依赖项的其他 F# 社区工具。</span><span class="sxs-lookup"><span data-stu-id="2301f-138">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>
