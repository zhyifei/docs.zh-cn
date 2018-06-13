---
title: Windows 上 .NET Core 的先决条件
description: 了解在 Windows 计算机上开发和运行 .NET Core 应用程序所需的依赖项。
author: JRAlexander
ms.author: johalex
ms.date: 05/18/2018
ms.openlocfilehash: 3d172c83f0a79744afbaeeff52d7fea62d9b98b6
ms.sourcegitcommit: 895c7602386a6dfe7ca4facce3d965b27e5c6e87
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2018
ms.locfileid: "34311983"
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="259b2-103">Windows 上 .NET Core 的先决条件</span><span class="sxs-lookup"><span data-stu-id="259b2-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="259b2-104">本文介绍了在 Windows 上开发 .NET Core 应用程序所需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="259b2-104">This article shows the dependencies needed to develop .NET Core applications on Windows.</span></span> <span data-ttu-id="259b2-105">支持的 OS 版本和依赖项适用于在 Windows 上开发 .NET Core 应用程序的三种方法：</span><span class="sxs-lookup"><span data-stu-id="259b2-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="259b2-106">命令行</span><span class="sxs-lookup"><span data-stu-id="259b2-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="259b2-107">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="259b2-107">Visual Studio 2017</span></span>](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)
* [<span data-ttu-id="259b2-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="259b2-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a><span data-ttu-id="259b2-109">支持 .NET Core 的 Windows 版本</span><span class="sxs-lookup"><span data-stu-id="259b2-109">.NET Core supported Windows versions</span></span>

<span data-ttu-id="259b2-110">以下版本支持 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="259b2-110">.NET Core is supported on the following versions of:</span></span>

* <span data-ttu-id="259b2-111">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="259b2-111">Windows 7 SP1</span></span>
* <span data-ttu-id="259b2-112">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="259b2-112">Windows 8.1</span></span>
* <span data-ttu-id="259b2-113">Windows 10 周年更新（版本 1607）或更高版本</span><span class="sxs-lookup"><span data-stu-id="259b2-113">Windows 10 Anniversary Update (version 1607) or later versions</span></span>
* <span data-ttu-id="259b2-114">Windows Server 2008 R2 SP1（完全服务器或服务器核心）</span><span class="sxs-lookup"><span data-stu-id="259b2-114">Windows Server 2008 R2 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="259b2-115">Windows Server 2012 SP1（完全服务器或服务器核心）</span><span class="sxs-lookup"><span data-stu-id="259b2-115">Windows Server 2012 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="259b2-116">Windows Server 2012 R2（完全服务器或服务器核心）</span><span class="sxs-lookup"><span data-stu-id="259b2-116">Windows Server 2012 R2 (Full Server or Server Core)</span></span>
* <span data-ttu-id="259b2-117">Windows Server 2016 或更高版本（完全服务器、服务器核心或 Nano Server）</span><span class="sxs-lookup"><span data-stu-id="259b2-117">Windows Server 2016 or later versions (Full Server, Server Core, or Nano Server)</span></span>

<span data-ttu-id="259b2-118">以下文章提供了 .NET Core 针对每个版本所支持的操作系统的完整列表：</span><span class="sxs-lookup"><span data-stu-id="259b2-118">The following articles have a complete list of .NET Core supported operating systems per version:</span></span>

* [<span data-ttu-id="259b2-119">.NET Core 2.1 - 受支持的操作系统版本</span><span class="sxs-lookup"><span data-stu-id="259b2-119">.NET Core 2.1 - Supported OS Versions</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)
* [<span data-ttu-id="259b2-120">.NET Core 2.0 - 受支持的操作系统版本</span><span class="sxs-lookup"><span data-stu-id="259b2-120">.NET Core 2.0 - Supported OS Versions</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)
* [<span data-ttu-id="259b2-121">.NET Core 1.x - 受支持的操作系统版本</span><span class="sxs-lookup"><span data-stu-id="259b2-121">.NET Core 1.x - Supported OS Versions</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)

## <a name="net-core-dependencies"></a><span data-ttu-id="259b2-122">.NET Core 依赖项</span><span class="sxs-lookup"><span data-stu-id="259b2-122">.NET Core dependencies</span></span>

<span data-ttu-id="259b2-123">在早于 Windows 10 和 Windows Server 2016 的 Windows 版本上运行 .NET Core 1.1 及更低版本时，需要 Visual C++ Redistributable。</span><span class="sxs-lookup"><span data-stu-id="259b2-123">.NET Core 1.1 and earlier versions require the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="259b2-124">.NET Core 安装程序自动安装此依赖项。</span><span class="sxs-lookup"><span data-stu-id="259b2-124">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="259b2-125">如果出现以下情况，必须手动安装 [Microsoft Visual C++ 2015 Redistributable 更新 3](https://www.microsoft.com/download/details.aspx?id=52685)：</span><span class="sxs-lookup"><span data-stu-id="259b2-125">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="259b2-126">使用[安装程序脚本](./tools/dotnet-install-script.md)安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="259b2-126">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="259b2-127">部署独立式 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="259b2-127">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="259b2-128">从源中生成产品。</span><span class="sxs-lookup"><span data-stu-id="259b2-128">Building the product from source.</span></span>
* <span data-ttu-id="259b2-129">通过 .zip 文件安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="259b2-129">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="259b2-130">这可能包括 build/CI/CD 服务器。</span><span class="sxs-lookup"><span data-stu-id="259b2-130">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="259b2-131">对于 Windows 8.1 和更早版本，或 Windows Server 2012 R2 和更早版本：</span><span class="sxs-lookup"><span data-stu-id="259b2-131">**For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:**</span></span>
>
> <span data-ttu-id="259b2-132">确保 Windows 安装是最新版本，并且包括可通过 Windows 更新安装的 [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows)。</span><span class="sxs-lookup"><span data-stu-id="259b2-132">Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows), which can be installed through Windows Update.</span></span> <span data-ttu-id="259b2-133">如果没有安装此更新，则在启动 .NET Core 应用程序时会看到如下错误：`The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span><span class="sxs-lookup"><span data-stu-id="259b2-133">If you don't have this update installed, you'll see an error like the following when you launch a .NET Core application: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span></span>
>
> <span data-ttu-id="259b2-134">对于 Windows 7 或 Windows Server 2008 R2：</span><span class="sxs-lookup"><span data-stu-id="259b2-134">**For Windows 7 or Windows Server 2008 R2:**</span></span>
>
> <span data-ttu-id="259b2-135">除 KB2999226 以外，请确保还安装了 [KB2533623](https://support.microsoft.com/en-us/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)。</span><span class="sxs-lookup"><span data-stu-id="259b2-135">In addition to KB2999226, make sure you also have [KB2533623](https://support.microsoft.com/en-us/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installed.</span></span> <span data-ttu-id="259b2-136">如果没有安装此更新，则在启动 .NET Core 应用程序时会看到如下错误：`The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`。</span><span class="sxs-lookup"><span data-stu-id="259b2-136">If you don't have this update installed, you'll see an error similar to the following when you launch a .NET Core application: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="259b2-137">Visual Studio 2017 的先决条件</span><span class="sxs-lookup"><span data-stu-id="259b2-137">Prerequisites with Visual Studio 2017</span></span>

<span data-ttu-id="259b2-138">可以使用任何编辑器，通过 .NET Core SDK 开发 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="259b2-138">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="259b2-139">[Visual Studio 2017](#visual-studio-2017) 提供了用于在 Windows 上开发 .NET Core 应用程序的集成开发环境。</span><span class="sxs-lookup"><span data-stu-id="259b2-139">[Visual Studio 2017](#visual-studio-2017) provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="259b2-140">在[发行说明](/visualstudio/releasenotes/vs2017-relnotes)中可以详细了解 Visual Studio 2017 中的更改。</span><span class="sxs-lookup"><span data-stu-id="259b2-140">You can read more about the changes in Visual Studio 2017 in the [release notes](/visualstudio/releasenotes/vs2017-relnotes).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="259b2-141">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="259b2-141">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="259b2-142">若要使用 Visual Studio 2017 开发 .NET Core 2.x 应用程序，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="259b2-142">To develop .NET Core 2.x apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="259b2-143">[下载并安装 Visual Studio 2017 版本 15.3.0 或更高版本](/visualstudio/install/install-visual-studio)，并选择“其他工具集”部分中的“.NET Core 跨平台开发”工作负载。</span><span class="sxs-lookup"><span data-stu-id="259b2-143">[Download and install Visual Studio 2017 version 15.3.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![选中“.NET Core 跨平台开发”工作负荷的 Visual Studio 2017 安装的屏幕截图](./media/windows-prerequisites/vs-15-3-workloads.jpg)

<span data-ttu-id="259b2-145">安装“.NET Core 跨平台开发”工具集后，Visual Studio 2017 默认使用 .NET Core 1.x。</span><span class="sxs-lookup"><span data-stu-id="259b2-145">After the **.NET Core cross-platform development** toolset is installed, Visual Studio 2017 uses .NET Core 1.x by default.</span></span> <span data-ttu-id="259b2-146">安装 .NET Core 2.x SDK，以便在 Visual Studio 2017 中获取 .NET Core 2.x 支持。</span><span class="sxs-lookup"><span data-stu-id="259b2-146">Install the .NET Core 2.x SDK to get .NET Core 2.x support in Visual Studio 2017.</span></span>

 2. <span data-ttu-id="259b2-147">获取 [.NET Core 2.x SDK](https://www.microsoft.com/net/download/core)。</span><span class="sxs-lookup"><span data-stu-id="259b2-147">Install the [.NET Core 2.x SDK](https://www.microsoft.com/net/download/core).</span></span>
 3. <span data-ttu-id="259b2-148">按照下列说明操作，将现有或新的 .NET Core 1.x 项目重定目标到 .NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="259b2-148">Retarget existing or new .NET Core 1.x projects to .NET Core 2.x using the following instructions:</span></span>
    * <span data-ttu-id="259b2-149">在“项目”菜单上，选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="259b2-149">On the **Project** menu, Choose **Properties**.</span></span>
    * <span data-ttu-id="259b2-150">在“目标框架”选择菜单上，将值设置为“.NET Core 2.0”。</span><span class="sxs-lookup"><span data-stu-id="259b2-150">In the **Target framework** selection menu, set the value to **.NET Core 2.0**.</span></span>

![已选择“.NET Core 2.0”目标框架菜单项的 Visual Studio 2017 应用程序项目属性屏幕截图](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="259b2-152">安装 .NET Core 2.x SDK 后，Visual Studio 2017 默认使用 .NET Core SDK 2.x，并支持以下操作：</span><span class="sxs-lookup"><span data-stu-id="259b2-152">Once the .NET Core 2.x SDK is installed, Visual Studio 2017 uses the .NET Core SDK 2.x by default, and supports the following actions:</span></span>

* <span data-ttu-id="259b2-153">打开、生成和运行现有 .NET Core 1.x 项目。</span><span class="sxs-lookup"><span data-stu-id="259b2-153">Open, build, and run existing .NET Core 1.x projects.</span></span>
* <span data-ttu-id="259b2-154">将 .NET Core 1.x 项目重定目标到 .NET Core 2.x，再生成并运行。</span><span class="sxs-lookup"><span data-stu-id="259b2-154">Retarget .NET Core 1.x projects to .NET Core 2.x, build, and run.</span></span>
* <span data-ttu-id="259b2-155">新建 .NET Core 2.x 项目。</span><span class="sxs-lookup"><span data-stu-id="259b2-155">Create new .NET Core 2.x projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="259b2-156">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="259b2-156">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="259b2-157">若要使用 Visual Studio 开发 .NET Core 1.x 应用程序，请[下载并安装 Visual Studio 2017 RTM（版本 15.0.26228.4）或更高版本](/visualstudio/install/install-visual-studio)，并选择“其他工具集”部分中的“.NET Core 跨平台开发”工作负载。</span><span class="sxs-lookup"><span data-stu-id="259b2-157">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017 RTM (version 15.0.26228.4) or higher](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>

![选中“.NET Core 跨平台开发”工作负荷的 Visual Studio 2017 安装的屏幕截图](./media/windows-prerequisites/vs_workloads.jpg)

> [!IMPORTANT]
> <span data-ttu-id="259b2-159">可以使用 Visual Studio 2015 进行 .NET Core 1.x 开发，但不建议这么做，原因如下：</span><span class="sxs-lookup"><span data-stu-id="259b2-159">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
  > * <span data-ttu-id="259b2-160">.NET Core 工具是预览版，并不受支持。</span><span class="sxs-lookup"><span data-stu-id="259b2-160">The .NET Core tooling is a preview version, which is not supported.</span></span>
  > * <span data-ttu-id="259b2-161">项目依据的 project.json 已遭弃用。</span><span class="sxs-lookup"><span data-stu-id="259b2-161">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="259b2-162">若要详细了解项目格式更改，请参阅[变更的简要概览](./tools/cli-msbuild-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="259b2-162">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>
---

> [!TIP]
> <span data-ttu-id="259b2-163">若要验证 Visual Studio 2017 版本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="259b2-163">To verify your Visual Studio 2017 version:</span></span>
>
> * <span data-ttu-id="259b2-164">在“帮助”菜单上，选择“关于 Microsoft Visual Studio”。</span><span class="sxs-lookup"><span data-stu-id="259b2-164">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
> * <span data-ttu-id="259b2-165">在“关于 Microsoft Visual Studio”对话框中，验证版本号。</span><span class="sxs-lookup"><span data-stu-id="259b2-165">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>   * <span data-ttu-id="259b2-166">对于 .NET Core 2.1 RC 应用，Visual Studio 2017 版本应为 15.7 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="259b2-166">For .NET Core 2.1 RC apps, Visual Studio 2017 version 15.7 or higher.</span></span>
>   * <span data-ttu-id="259b2-167">对于 .NET Core 2.0 应用，Visual Studio 2017 版本应为 15.3 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="259b2-167">For .NET Core 2.0 apps, Visual Studio 2017 version 15.3 or higher.</span></span>
>   * <span data-ttu-id="259b2-168">对于 .NET Core 1.x 应用，Visual Studio 2017 版本应为 15.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="259b2-168">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 or higher.</span></span>
