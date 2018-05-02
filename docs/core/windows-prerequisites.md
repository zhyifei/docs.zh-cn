---
title: Windows 上 .NET Core 的先决条件
description: 了解在 Windows 计算机上开发和运行 .NET Core 应用程序所需的依赖项。
author: JRAlexander
ms.author: johalex
ms.date: 04/24/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.workload:
- dotnetcore
ms.openlocfilehash: 6f2ba8540a38f8e30d3d968f5e2c891c850053aa
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="cff6e-103">Windows 上 .NET Core 的先决条件</span><span class="sxs-lookup"><span data-stu-id="cff6e-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="cff6e-104">本文介绍了在 Windows 上开发 .NET Core 应用程序所需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="cff6e-104">This article shows the dependencies needed to develop .NET Core applications on Windows.</span></span> <span data-ttu-id="cff6e-105">支持的 OS 版本和依赖项适用于在 Windows 上开发 .NET Core 应用程序的三种方法：</span><span class="sxs-lookup"><span data-stu-id="cff6e-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="cff6e-106">命令行</span><span class="sxs-lookup"><span data-stu-id="cff6e-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="cff6e-107">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="cff6e-107">Visual Studio 2017</span></span>](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)
* [<span data-ttu-id="cff6e-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="cff6e-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a><span data-ttu-id="cff6e-109">支持 .NET Core 的 Windows 版本</span><span class="sxs-lookup"><span data-stu-id="cff6e-109">.NET Core supported Windows versions</span></span>

<span data-ttu-id="cff6e-110">以下版本支持 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="cff6e-110">.NET Core is supported on the following versions of:</span></span>

* <span data-ttu-id="cff6e-111">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="cff6e-111">Windows 7 SP1</span></span>
* <span data-ttu-id="cff6e-112">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="cff6e-112">Windows 8.1</span></span>
* <span data-ttu-id="cff6e-113">Windows 10 周年更新（版本 1607）或更高版本</span><span class="sxs-lookup"><span data-stu-id="cff6e-113">Windows 10 Anniversary Update (version 1607) or later versions</span></span>
* <span data-ttu-id="cff6e-114">Windows Server 2008 R2 SP1（完全服务器或服务器核心）</span><span class="sxs-lookup"><span data-stu-id="cff6e-114">Windows Server 2008 R2 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="cff6e-115">Windows Server 2012 SP1（完全服务器或服务器核心）</span><span class="sxs-lookup"><span data-stu-id="cff6e-115">Windows Server 2012 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="cff6e-116">Windows Server 2012 R2（完全服务器或服务器核心）</span><span class="sxs-lookup"><span data-stu-id="cff6e-116">Windows Server 2012 R2 (Full Server or Server Core)</span></span>
* <span data-ttu-id="cff6e-117">Windows Server 2016（完全服务器、服务器核心或 Nano Server）</span><span class="sxs-lookup"><span data-stu-id="cff6e-117">Windows Server 2016 (Full Server, Server Core, or Nano Server)</span></span>

<span data-ttu-id="cff6e-118">有关支持 .NET Core 2.x 的操作系统的完整列表，请参阅 [.NET Core 2.x - 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="cff6e-118">See [.NET Core 2.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems.</span></span>

<span data-ttu-id="cff6e-119">有关支持 .NET Core 1.x 的操作系统的完整列表，请参阅 [.NET Core 1.x - 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="cff6e-119">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="cff6e-120">.NET Core 依赖项</span><span class="sxs-lookup"><span data-stu-id="cff6e-120">.NET Core dependencies</span></span>

<span data-ttu-id="cff6e-121">在早于 Windows 10 和 Windows Server 2016 的 Windows 版本上运行 .NET Core 1.1 及更低版本时，需要 Visual C++ Redistributable。</span><span class="sxs-lookup"><span data-stu-id="cff6e-121">.NET Core 1.1 and earlier versions require the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="cff6e-122">.NET Core 安装程序自动安装此依赖项。</span><span class="sxs-lookup"><span data-stu-id="cff6e-122">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="cff6e-123">如果出现以下情况，必须手动安装 [Microsoft Visual C++ 2015 Redistributable 更新 3](https://www.microsoft.com/download/details.aspx?id=52685)：</span><span class="sxs-lookup"><span data-stu-id="cff6e-123">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="cff6e-124">使用[安装程序脚本](./tools/dotnet-install-script.md)安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="cff6e-124">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="cff6e-125">部署独立式 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="cff6e-125">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="cff6e-126">从源中生成产品。</span><span class="sxs-lookup"><span data-stu-id="cff6e-126">Building the product from source.</span></span>
* <span data-ttu-id="cff6e-127">通过 .zip 文件安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="cff6e-127">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="cff6e-128">这可能包括 build/CI/CD 服务器。</span><span class="sxs-lookup"><span data-stu-id="cff6e-128">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="cff6e-129">对于 Windows 8.1 和更早版本，或 Windows Server 2012 R2 和更早版本：请确保你的 Windows 安装为最新版本，并且包含可以通过 Windows 更新安装的 [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows)。</span><span class="sxs-lookup"><span data-stu-id="cff6e-129">*For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:* Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows) which can be installed through Windows Update.</span></span> <span data-ttu-id="cff6e-130">如果没有安装此更新，则在启动 .NET Core 应用程序时会看到如下错误：`The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`。</span><span class="sxs-lookup"><span data-stu-id="cff6e-130">If you don't have this update installed, you'll see an error when you launch a .NET Core application like the following: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="cff6e-131">Visual Studio 2017 的先决条件</span><span class="sxs-lookup"><span data-stu-id="cff6e-131">Prerequisites with Visual Studio 2017</span></span>

<span data-ttu-id="cff6e-132">可以使用任何编辑器，通过 .NET Core SDK 开发 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="cff6e-132">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="cff6e-133">[Visual Studio 2017](#visual-studio-2017) 提供了用于在 Windows 上开发 .NET Core 应用程序的集成开发环境。</span><span class="sxs-lookup"><span data-stu-id="cff6e-133">[Visual Studio 2017](#visual-studio-2017) provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="cff6e-134">在[发行说明](/visualstudio/releasenotes/vs2017-relnotes)中可以详细了解 Visual Studio 2017 中的更改。</span><span class="sxs-lookup"><span data-stu-id="cff6e-134">You can read more about the changes in Visual Studio 2017 in the [release notes](/visualstudio/releasenotes/vs2017-relnotes).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="cff6e-135">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="cff6e-135">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="cff6e-136">若要使用 Visual Studio 2017 开发 .NET Core 2.x 应用程序，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cff6e-136">To develop .NET Core 2.x apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="cff6e-137">[下载并安装 Visual Studio 2017 版本 15.3.0 或更高版本](/visualstudio/install/install-visual-studio)，并选择“其他工具集”部分中的“.NET Core 跨平台开发”工作负载。</span><span class="sxs-lookup"><span data-stu-id="cff6e-137">[Download and install Visual Studio 2017 version 15.3.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![选中“.NET Core 跨平台开发”工作负荷的 Visual Studio 2017 安装的屏幕截图](./media/windows-prerequisites/vs-15-3-workloads.jpg)

<span data-ttu-id="cff6e-139">安装“.NET Core 跨平台开发”工具集后，Visual Studio 2017 默认使用 .NET Core 1.x。</span><span class="sxs-lookup"><span data-stu-id="cff6e-139">After the **.NET Core cross-platform development** toolset is installed, Visual Studio 2017 uses .NET Core 1.x by default.</span></span> <span data-ttu-id="cff6e-140">安装 .NET Core 2.x SDK，以便在 Visual Studio 2017 中获取 .NET Core 2.x 支持。</span><span class="sxs-lookup"><span data-stu-id="cff6e-140">Install the .NET Core 2.x SDK to get .NET Core 2.x support in Visual Studio 2017.</span></span>

 2. <span data-ttu-id="cff6e-141">获取 [.NET Core 2.x SDK](https://www.microsoft.com/net/download/core)。</span><span class="sxs-lookup"><span data-stu-id="cff6e-141">Install the [.NET Core 2.x SDK](https://www.microsoft.com/net/download/core).</span></span>
 3. <span data-ttu-id="cff6e-142">按照下列说明操作，将现有或新的 .NET Core 1.x 项目重定目标到 .NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="cff6e-142">Retarget existing or new .NET Core 1.x projects to .NET Core 2.x using the following instructions:</span></span>
    * <span data-ttu-id="cff6e-143">在“项目”菜单上，选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="cff6e-143">On the **Project** menu, Choose **Properties**.</span></span>
    * <span data-ttu-id="cff6e-144">在“目标框架”选择菜单上，将值设置为“.NET Core 2.0”。</span><span class="sxs-lookup"><span data-stu-id="cff6e-144">In the **Target framework** selection menu, set the value to **.NET Core 2.0**.</span></span>

![已选择“.NET Core 2.0”目标框架菜单项的 Visual Studio 2017 应用程序项目属性屏幕截图](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="cff6e-146">安装 .NET Core 2.x SDK 后，Visual Studio 2017 默认使用 .NET Core SDK 2.x，并支持以下操作：</span><span class="sxs-lookup"><span data-stu-id="cff6e-146">Once the .NET Core 2.x SDK is installed, Visual Studio 2017 uses the .NET Core SDK 2.x by default, and supports the following actions:</span></span>

* <span data-ttu-id="cff6e-147">打开、生成和运行现有 .NET Core 1.x 项目。</span><span class="sxs-lookup"><span data-stu-id="cff6e-147">Open, build, and run existing .NET Core 1.x projects.</span></span>
* <span data-ttu-id="cff6e-148">将 .NET Core 1.x 项目重定目标到 .NET Core 2.x，再生成并运行。</span><span class="sxs-lookup"><span data-stu-id="cff6e-148">Retarget .NET Core 1.x projects to .NET Core 2.x, build, and run.</span></span>
* <span data-ttu-id="cff6e-149">新建 .NET Core 2.x 项目。</span><span class="sxs-lookup"><span data-stu-id="cff6e-149">Create new .NET Core 2.x projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cff6e-150">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cff6e-150">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="cff6e-151">若要使用 Visual Studio 开发 .NET Core 1.x 应用程序，请[下载并安装 Visual Studio 2017 RTM（版本 15.0.26228.4）或更高版本](/visualstudio/install/install-visual-studio)，并选择“其他工具集”部分中的“.NET Core 跨平台开发”工作负载。</span><span class="sxs-lookup"><span data-stu-id="cff6e-151">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017 RTM (version 15.0.26228.4) or higher](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>

![选中“.NET Core 跨平台开发”工作负荷的 Visual Studio 2017 安装的屏幕截图](./media/windows-prerequisites/vs_workloads.jpg)

> [!IMPORTANT]
> <span data-ttu-id="cff6e-153">可以使用 Visual Studio 2015 进行 .NET Core 1.x 开发，但不建议这么做，原因如下：</span><span class="sxs-lookup"><span data-stu-id="cff6e-153">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
  > * <span data-ttu-id="cff6e-154">.NET Core 工具是预览版，并不受支持。</span><span class="sxs-lookup"><span data-stu-id="cff6e-154">The .NET Core tooling is a preview version, which is not supported.</span></span>
  > * <span data-ttu-id="cff6e-155">项目依据的 project.json 已遭弃用。</span><span class="sxs-lookup"><span data-stu-id="cff6e-155">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="cff6e-156">若要详细了解项目格式更改，请参阅[变更的简要概览](./tools/cli-msbuild-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="cff6e-156">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>
---

> [!TIP]
> <span data-ttu-id="cff6e-157">若要验证 Visual Studio 2017 版本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cff6e-157">To verify your Visual Studio 2017 version:</span></span>
>
> * <span data-ttu-id="cff6e-158">在“帮助”菜单上，选择“关于 Microsoft Visual Studio”。</span><span class="sxs-lookup"><span data-stu-id="cff6e-158">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
> * <span data-ttu-id="cff6e-159">在“关于 Microsoft Visual Studio”对话框中，验证版本号。</span><span class="sxs-lookup"><span data-stu-id="cff6e-159">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>   * <span data-ttu-id="cff6e-160">对于 .NET Core 2.1 Preview 1 应用，Visual Studio 2017 版本应为 15.6 预览版 6 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="cff6e-160">For .NET Core 2.1 Preview 1 apps, Visual Studio 2017 version 15.6 Preview 6 or higher.</span></span>
>   * <span data-ttu-id="cff6e-161">对于 .NET Core 2.0 应用，Visual Studio 2017 版本应为 15.3 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="cff6e-161">For .NET Core 2.0 apps, Visual Studio 2017 version 15.3 or higher.</span></span>
>   * <span data-ttu-id="cff6e-162">对于 .NET Core 1.x 应用，Visual Studio 2017 版本应为 15.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="cff6e-162">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 or higher.</span></span>
