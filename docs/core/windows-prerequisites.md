---
title: "Windows 上 .NET Core 的先决条件"
description: "了解在 Windows 计算机上开发和运行 .NET Core 应用程序所需的依赖项。"
keywords: ".NET Core、Windows、先决条件、依赖项、Visual Studio"
author: mairaw
ms.author: mairaw
ms.date: 06/26/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0e414af0edbafed5b7f540eda6de2e5078eac789
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="4d93d-104">Windows 上 .NET Core 的先决条件</span><span class="sxs-lookup"><span data-stu-id="4d93d-104">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="4d93d-105">本文展示了在 Windows 计算机上部署和运行 .NET Core 应用程序并使用 Visual Studio 进行开发时所需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="4d93d-105">This article shows you what dependencies you need to deploy and run .NET Core applications on Windows machines and develop using Visual Studio.</span></span>

## <a name="supported-windows-versions"></a><span data-ttu-id="4d93d-106">受支持的 Windows 版本</span><span class="sxs-lookup"><span data-stu-id="4d93d-106">Supported Windows versions</span></span>

<span data-ttu-id="4d93d-107">以下 Windows 版本均支持 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="4d93d-107">.NET Core is supported on the following versions of Windows:</span></span>

* <span data-ttu-id="4d93d-108">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="4d93d-108">Windows 7 SP1</span></span>
* <span data-ttu-id="4d93d-109">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="4d93d-109">Windows 8.1</span></span>
* <span data-ttu-id="4d93d-110">Windows 10</span><span class="sxs-lookup"><span data-stu-id="4d93d-110">Windows 10</span></span>
* <span data-ttu-id="4d93d-111">Windows Server 2008 R2 SP1（完全服务器或服务器核心）</span><span class="sxs-lookup"><span data-stu-id="4d93d-111">Windows Server 2008 R2 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="4d93d-112">Windows Server 2012 SP1（完全服务器或服务器核心）</span><span class="sxs-lookup"><span data-stu-id="4d93d-112">Windows Server 2012 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="4d93d-113">Windows Server 2012 R2（完全服务器或服务器核心）</span><span class="sxs-lookup"><span data-stu-id="4d93d-113">Windows Server 2012 R2 (Full Server or Server Core)</span></span>
* <span data-ttu-id="4d93d-114">Windows Server 2016（完全服务器、服务器核心或 Nano Server）</span><span class="sxs-lookup"><span data-stu-id="4d93d-114">Windows Server 2016 (Full Server, Server Core or Nano Server)</span></span>

<span data-ttu-id="4d93d-115">在 [.NET Core 发行说明](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md)中查看一系列完整的受支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="4d93d-115">See the [.NET Core Release Notes](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) for the full set of supported operating systems.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="4d93d-116">.NET Core 依赖项</span><span class="sxs-lookup"><span data-stu-id="4d93d-116">.NET Core dependencies</span></span>

<span data-ttu-id="4d93d-117">在早于 Windows 10 和 Windows Server 2016 的 Windows 版本上运行 .NET Core 时，需要 Visual C++ Redistributable。</span><span class="sxs-lookup"><span data-stu-id="4d93d-117">.NET Core requires the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="4d93d-118">若使用 .NET Core 安装程序，将自动安装此依赖项。</span><span class="sxs-lookup"><span data-stu-id="4d93d-118">This dependency is automatically installed for you if you use the .NET Core installer.</span></span> <span data-ttu-id="4d93d-119">但是，如果通过[安装程序脚本](./tools/dotnet-install-script.md)安装 .NET Core 或部署独立的 .NET Core 应用程序，则需要手动安装 [Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/en-us/download/details.aspx?id=52685)。</span><span class="sxs-lookup"><span data-stu-id="4d93d-119">However, you need to manually install the [Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/en-us/download/details.aspx?id=52685) if you are installing .NET Core via the [installer script](./tools/dotnet-install-script.md) or deploying a self-contained .NET Core application.</span></span>

> [!NOTE]
> <span data-ttu-id="4d93d-120"><em>仅适用于 Windows 7 和 Windows Server 2008 计算机：</em></span><span class="sxs-lookup"><span data-stu-id="4d93d-120"><em>For Windows 7 and Windows Server 2008 machines only:</em></span></span><br>
> <span data-ttu-id="4d93d-121">确保 Windows 安装是最新版本，并且包括通过 Windows 更新安装的修补程序 [KB2533623](https://support.microsoft.com/help/2533623)。</span><span class="sxs-lookup"><span data-stu-id="4d93d-121">Make sure that your Windows installation is up-to-date and includes hotfix [KB2533623](https://support.microsoft.com/help/2533623) installed through Windows Update.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="4d93d-122">Visual Studio 2017 的先决条件</span><span class="sxs-lookup"><span data-stu-id="4d93d-122">Prerequisites with Visual Studio 2017</span></span>

<span data-ttu-id="4d93d-123">可以使用所选择的任何编辑器，使用 .NET Core SDK 开发 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="4d93d-123">You can use any editor of your choice to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="4d93d-124">但是，若要在集成的开发环境中的 Windows 上开发 .NET Core 应用程序，可以使用 [Visual Studio 2017](#visual-studio-2017)。</span><span class="sxs-lookup"><span data-stu-id="4d93d-124">However, if you want to develop .NET Core applications on Windows in an integrated development environment, you can use [Visual Studio 2017](#visual-studio-2017).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d93d-125">尽管可以在 .NET Core 工具的预览版中使用 Visual Studio 2015，但这些项目基于 *project.json* 的，现在已弃用。</span><span class="sxs-lookup"><span data-stu-id="4d93d-125">Even though, it's possible to use Visual Studio 2015 with a preview version of the .NET Core tooling, these projects will be *project.json*-based, which is now deprecated.</span></span> <span data-ttu-id="4d93d-126">Visual Studio 2017 使用基于 MSBuild 的项目文件。</span><span class="sxs-lookup"><span data-stu-id="4d93d-126">Visual Studio 2017 uses project files based on MSBuild.</span></span> <span data-ttu-id="4d93d-127">有关格式更改的详细信息，请参阅[有关更改的高级别概述](./tools/cli-msbuild-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="4d93d-127">For more information about the format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>

<span data-ttu-id="4d93d-128">若要使用 Visual Studio 2017 开发 .NET Core 应用，必须选择将 **.NET Core 跨平台开发**工具集（在“其他工具集”部分中）与最新版本的 Visual Studio 一并安装。</span><span class="sxs-lookup"><span data-stu-id="4d93d-128">To use Visual Studio 2017 to develop .NET Core apps, you'll need to have the latest version of Visual Studio installed with the **.NET Core cross-platform development** toolset (in the **Other Toolsets** section) selected.</span></span>
<span data-ttu-id="4d93d-129">![选中“.NET Core 跨平台开发”工作负荷的 Visual Studio 2017 安装的屏幕截图](./media/windows-prerequisites/vs_workloads.jpg)</span><span class="sxs-lookup"><span data-stu-id="4d93d-129">![Screenshot of Visual Studio 2017 installation with the ".NET Core cross-platform development" workload selected](./media/windows-prerequisites/vs_workloads.jpg)</span></span>

<span data-ttu-id="4d93d-130">Visual Studio 2017 有不同的版本。</span><span class="sxs-lookup"><span data-stu-id="4d93d-130">There are different editions of Visual Studio 2017.</span></span> <span data-ttu-id="4d93d-131">可以免费下载 [Visual Studio Community 2017](https://www.visualstudio.com/downloads/) 并开始使用。</span><span class="sxs-lookup"><span data-stu-id="4d93d-131">You can download [Visual Studio Community 2017](https://www.visualstudio.com/downloads/) for free to get started.</span></span>  <span data-ttu-id="4d93d-132">若要了解有关 Visual Studio 安装过程的详细信息，请参阅[安装 Visual Studo 2017](/visualstudio/install/install-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="4d93d-132">To learn more about the Visual Studio installation process, see [Install Visual Studio 2017](/visualstudio/install/install-visual-studio).</span></span>

<span data-ttu-id="4d93d-133">若要验证运行的是否是最新版本的 Visual Studio 2017，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4d93d-133">To verify that you're running the latest version of Visual Studio 2017, do the following:</span></span>

 * <span data-ttu-id="4d93d-134">在“帮助”菜单上，选择“关于 Microsoft Visual Studio”。</span><span class="sxs-lookup"><span data-stu-id="4d93d-134">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
 * <span data-ttu-id="4d93d-135">在“关于 Microsoft Visual Studio”对话框中，版本号应该是 15.0.26228.4 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="4d93d-135">In the **About Microsoft Visual Studio** dialog, the version number should be 15.0.26228.4 or higher.</span></span>

<span data-ttu-id="4d93d-136">在[发行说明](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes)中可以详细了解 Visual Studio 2017 中的更改。</span><span class="sxs-lookup"><span data-stu-id="4d93d-136">You can read more about the changes in Visual Studio 2017 in the [release notes](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes).</span></span>

