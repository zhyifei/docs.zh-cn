---
title: '安装 F #'
description: '了解如何安装 F # 根据您的环境。'
ms.date: 07/03/2018
ms.openlocfilehash: 142265a95e1d3ee1603a89f650a24c6a45709181
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "37878840"
---
# <a name="install-f"></a><span data-ttu-id="20d1a-103">安装 F #</span><span class="sxs-lookup"><span data-stu-id="20d1a-103">Install F#</span></span> #

<span data-ttu-id="20d1a-104">你可以安装 F # 中通过多种方式，具体取决于你的环境。</span><span class="sxs-lookup"><span data-stu-id="20d1a-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="20d1a-105">使用 Visual Studio 安装 F #</span><span class="sxs-lookup"><span data-stu-id="20d1a-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="20d1a-106">如果在下载[Visual Studio](https://visualstudio.microsoft.com/)第一次，它将首先安装 Visual Studio 安装程序。</span><span class="sxs-lookup"><span data-stu-id="20d1a-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="20d1a-107">安装程序安装在相应 SKU 的 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="20d1a-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="20d1a-108">如果你已安装，请单击**修改**。</span><span class="sxs-lookup"><span data-stu-id="20d1a-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="20d1a-109">接下来，您将看到工作负荷列表。</span><span class="sxs-lookup"><span data-stu-id="20d1a-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="20d1a-110">选择**ASP.NET 和 web 开发**，这将安装 F # 支持，.NET Core 支持和 F # 支持适用于 ASP.NET Core 项目。</span><span class="sxs-lookup"><span data-stu-id="20d1a-110">Select **ASP.NET and web development**, which will install F# support, .NET Core support, and F# support for ASP.NET Core projects.</span></span>

<span data-ttu-id="20d1a-111">接下来，单击**修改**右下角中。</span><span class="sxs-lookup"><span data-stu-id="20d1a-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="20d1a-112">这将安装所选的所有内容。</span><span class="sxs-lookup"><span data-stu-id="20d1a-112">This will install everything you have selected.</span></span> <span data-ttu-id="20d1a-113">随后可打开 Visual Studio 2017 的 F # 语言支持通过单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="20d1a-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="20d1a-114">安装 F # 与 Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="20d1a-114">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="20d1a-115">F # 中默认情况下安装[Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/)，无论是哪种配置选择。</span><span class="sxs-lookup"><span data-stu-id="20d1a-115">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/), no matter what configuration you choose.</span></span>

<span data-ttu-id="20d1a-116">在安装完成后，选择"启动 Visual Studio"。</span><span class="sxs-lookup"><span data-stu-id="20d1a-116">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="20d1a-117">您还可以启动它通过 Finder 在 macOS 上。</span><span class="sxs-lookup"><span data-stu-id="20d1a-117">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="20d1a-118">使用 Visual Studio Code 中安装 F #</span><span class="sxs-lookup"><span data-stu-id="20d1a-118">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="20d1a-119">您必须具有[安装 git](https://git-scm.com/download)且适用于你的路径以使 Ionide 中的项目模板的使用。</span><span class="sxs-lookup"><span data-stu-id="20d1a-119">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates in Ionide.</span></span> <span data-ttu-id="20d1a-120">你可以验证是否已正确安装通过键入`git --version`在命令提示符，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="20d1a-120">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="20d1a-121">macOS</span><span class="sxs-lookup"><span data-stu-id="20d1a-121">macOS</span></span>](#tab/macos)

<span data-ttu-id="20d1a-122">使用 Ionide [Mono](http://www.mono-project.com)。</span><span class="sxs-lookup"><span data-stu-id="20d1a-122">Ionide uses [Mono](http://www.mono-project.com).</span></span> <span data-ttu-id="20d1a-123">通过 Homebrew 在 macOS 上安装 Mono 的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="20d1a-123">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="20d1a-124">只需为你的终端中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="20d1a-124">Simply type the following into your terminal:</span></span>

```console
brew install mono
```

<span data-ttu-id="20d1a-125">你还必须安装[.NET Core SDK](https://www.microsoft.com/net/download)。</span><span class="sxs-lookup"><span data-stu-id="20d1a-125">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="20d1a-126">Linux</span><span class="sxs-lookup"><span data-stu-id="20d1a-126">Linux</span></span>](#tab/linux)

<span data-ttu-id="20d1a-127">在 Linux 上，Ionide 还使用[Mono](https://www.mono-project.com)。</span><span class="sxs-lookup"><span data-stu-id="20d1a-127">On Linux, Ionide also uses [Mono](https://www.mono-project.com).</span></span> <span data-ttu-id="20d1a-128">如果您在 Debian 或 Ubuntu 上，可以使用以下：</span><span class="sxs-lookup"><span data-stu-id="20d1a-128">If you're on Debian or Ubuntu, you can use the following:</span></span>

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="20d1a-129">你还必须安装[.NET Core SDK](https://www.microsoft.com/net/download)。</span><span class="sxs-lookup"><span data-stu-id="20d1a-129">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="20d1a-130">Windows</span><span class="sxs-lookup"><span data-stu-id="20d1a-130">Windows</span></span>](#tab/windows)

<span data-ttu-id="20d1a-131">如果您在 Windows 上，您必须[情况下安装 Visual Studio 的 F # 支持](#install-f-with-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="20d1a-131">If you're on Windows, you must [install Visual Studio with F# support](#install-f-with-visual-studio).</span></span> <span data-ttu-id="20d1a-132">这会安装所有必要的组件来编写、 编译和执行 F # 代码。</span><span class="sxs-lookup"><span data-stu-id="20d1a-132">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="20d1a-133">你还必须安装[.NET Core SDK](https://www.microsoft.com/net/download/)。</span><span class="sxs-lookup"><span data-stu-id="20d1a-133">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

<span data-ttu-id="20d1a-134">然后，你将需要[Visual Studio Code](https://code.visualstudio.com)安装。</span><span class="sxs-lookup"><span data-stu-id="20d1a-134">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="20d1a-135">接下来，请单击扩展图标并搜索"Ionide":</span><span class="sxs-lookup"><span data-stu-id="20d1a-135">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="20d1a-136">F # 支持在 Visual Studio Code 所需的唯一插件[ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)。</span><span class="sxs-lookup"><span data-stu-id="20d1a-136">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="20d1a-137">但是，也可以安装[Ionide 虚设](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)若要获取[FAKE](https://fsharp.github.io/FAKE/)支持并[Ionide paket 依存](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)获取[paket 依存](https://fsprojects.github.io/Paket/)支持。</span><span class="sxs-lookup"><span data-stu-id="20d1a-137">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="20d1a-138">虚设和 paket 依存是其他 F # 社区工具来生成项目并管理依赖项，分别。</span><span class="sxs-lookup"><span data-stu-id="20d1a-138">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>