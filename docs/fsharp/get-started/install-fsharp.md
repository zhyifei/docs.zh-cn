---
title: 安装F#
description: 了解如何安装F#根据你的环境。
ms.date: 08/28/2018
ms.openlocfilehash: 792c61c0522cd4d0c68a64572f2892ce33f71ea6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331970"
---
# <a name="install-f"></a><span data-ttu-id="8e4e2-103">安装 F\#</span><span class="sxs-lookup"><span data-stu-id="8e4e2-103">Install F\#</span></span>

<span data-ttu-id="8e4e2-104">你可以安装F#在多个方面，具体取决于你的环境。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="8e4e2-105">安装F#使用 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8e4e2-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="8e4e2-106">如果在下载[Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)第一次，它将首先安装 Visual Studio 安装程序。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="8e4e2-107">安装程序安装在相应 SKU 的 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="8e4e2-108">如果你已安装，请单击**修改**。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="8e4e2-109">接下来，您将看到工作负荷列表。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="8e4e2-110">选择**ASP.NET 和 web 开发**哪一项将安装F#ASP.NET Core 项目的支持和.NET Core 支持。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-110">Select **ASP.NET and web development** which will install F# support and .NET Core support for ASP.NET Core projects.</span></span>

<span data-ttu-id="8e4e2-111">接下来，单击**修改**右下角中。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="8e4e2-112">这将安装所选的所有内容。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-112">This will install everything you have selected.</span></span> <span data-ttu-id="8e4e2-113">然后可以打开带有 Visual Studio 2017F#语言支持通过单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="8e4e2-114">安装F#使用 Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="8e4e2-114">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="8e4e2-115">F#在默认情况下安装[Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)，无论哪种配置选择。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-115">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="8e4e2-116">在安装完成后，选择"启动 Visual Studio"。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-116">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="8e4e2-117">您还可以启动它通过 Finder 在 macOS 上。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-117">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="8e4e2-118">安装F#使用 Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8e4e2-118">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="8e4e2-119">您必须具有[安装 git](https://git-scm.com/download)且适用于你的路径以使项目模板使用。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-119">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates.</span></span> <span data-ttu-id="8e4e2-120">你可以验证是否已正确安装通过键入`git --version`在命令提示符，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-120">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="8e4e2-121">macOS</span><span class="sxs-lookup"><span data-stu-id="8e4e2-121">macOS</span></span>](#tab/macos)

<span data-ttu-id="8e4e2-122">[Mono](https://www.mono-project.com)用于[F#交互式](../tutorials/fsharp-interactive/index.md)支持。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-122">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="8e4e2-123">通过 Homebrew 在 macOS 上安装 Mono 的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-123">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="8e4e2-124">只需为你的终端中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="8e4e2-124">Simply type the following into your terminal:</span></span>

```console
brew install mono
```

<span data-ttu-id="8e4e2-125">此外安装[.NET Core SDK](https://www.microsoft.com/net/download)。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-125">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="8e4e2-126">Linux</span><span class="sxs-lookup"><span data-stu-id="8e4e2-126">Linux</span></span>](#tab/linux)

<span data-ttu-id="8e4e2-127">[Mono](https://www.mono-project.com)用于[F#交互式](../tutorials/fsharp-interactive/index.md)支持。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-127">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="8e4e2-128">如果您在 Debian 或 Ubuntu 上，可以使用以下：</span><span class="sxs-lookup"><span data-stu-id="8e4e2-128">If you're on Debian or Ubuntu, you can use the following:</span></span>

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="8e4e2-129">此外安装[.NET Core SDK](https://www.microsoft.com/net/download)。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-129">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="8e4e2-130">Windows</span><span class="sxs-lookup"><span data-stu-id="8e4e2-130">Windows</span></span>](#tab/windows)

<span data-ttu-id="8e4e2-131">安装[Visual Studio 中使用F#支持](#install-f-with-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-131">Install [Visual Studio with F# support](#install-f-with-visual-studio).</span></span> <span data-ttu-id="8e4e2-132">这将安装所有必要的组件来编写、 编译和执行F#代码。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-132">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="8e4e2-133">此外安装[.NET Core SDK](https://www.microsoft.com/net/download/)。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-133">Also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

<span data-ttu-id="8e4e2-134">然后，你将需要[Visual Studio Code](https://code.visualstudio.com)安装。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-134">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="8e4e2-135">接下来，请单击扩展图标并搜索"Ionide":</span><span class="sxs-lookup"><span data-stu-id="8e4e2-135">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="8e4e2-136">唯一的插件所需的F#支持在 Visual Studio Code [ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-136">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="8e4e2-137">但是，也可以安装[Ionide 虚设](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)若要获取[FAKE](https://fsharp.github.io/FAKE/)支持并[Ionide paket 依存](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)获取[paket 依存](https://fsprojects.github.io/Paket/)支持。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-137">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="8e4e2-138">虚设和 paket 依存是其他F#用于生成项目并分别管理依赖项的社区工具。</span><span class="sxs-lookup"><span data-stu-id="8e4e2-138">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>
