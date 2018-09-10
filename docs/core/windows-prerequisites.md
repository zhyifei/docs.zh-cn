---
title: Windows 上 .NET Core 的先决条件
description: 了解在 Windows 计算机上开发和运行 .NET Core 应用程序所需的依赖项。
author: mairaw
ms.author: mairaw
ms.date: 08/31/2018
ms.openlocfilehash: bbf54c8d215783656830f0fa035708be82a7c39c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482605"
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="429f6-103">Windows 上 .NET Core 的先决条件</span><span class="sxs-lookup"><span data-stu-id="429f6-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="429f6-104">本文介绍了在 Windows 上开发 .NET Core 应用程序所需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="429f6-104">This article shows the dependencies needed to develop .NET Core applications on Windows.</span></span> <span data-ttu-id="429f6-105">支持的 OS 版本和依赖项适用于在 Windows 上开发 .NET Core 应用程序的三种方法：</span><span class="sxs-lookup"><span data-stu-id="429f6-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="429f6-106">命令行</span><span class="sxs-lookup"><span data-stu-id="429f6-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="429f6-107">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="429f6-107">Visual Studio 2017</span></span>](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)
* [<span data-ttu-id="429f6-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="429f6-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a><span data-ttu-id="429f6-109">支持 .NET Core 的 Windows 版本</span><span class="sxs-lookup"><span data-stu-id="429f6-109">.NET Core supported Windows versions</span></span>

<span data-ttu-id="429f6-110">以下版本支持 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="429f6-110">.NET Core is supported on the following versions of:</span></span>

* <span data-ttu-id="429f6-111">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="429f6-111">Windows 7 SP1</span></span>
* <span data-ttu-id="429f6-112">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="429f6-112">Windows 8.1</span></span>
* <span data-ttu-id="429f6-113">Windows 10 周年更新（版本 1607）或更高版本</span><span class="sxs-lookup"><span data-stu-id="429f6-113">Windows 10 Anniversary Update (version 1607) or later versions</span></span>
* <span data-ttu-id="429f6-114">Windows Server 2008 R2 SP1（完全服务器或服务器核心）</span><span class="sxs-lookup"><span data-stu-id="429f6-114">Windows Server 2008 R2 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="429f6-115">Windows Server 2012 SP1（完全服务器或服务器核心）</span><span class="sxs-lookup"><span data-stu-id="429f6-115">Windows Server 2012 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="429f6-116">Windows Server 2012 R2（完全服务器或服务器核心）</span><span class="sxs-lookup"><span data-stu-id="429f6-116">Windows Server 2012 R2 (Full Server or Server Core)</span></span>
* <span data-ttu-id="429f6-117">Windows Server 2016 或更高版本（完全服务器、服务器核心或 Nano Server）</span><span class="sxs-lookup"><span data-stu-id="429f6-117">Windows Server 2016 or later versions (Full Server, Server Core, or Nano Server)</span></span>

<span data-ttu-id="429f6-118">以下文章提供了 .NET Core 针对每个版本所支持的操作系统的完整列表：</span><span class="sxs-lookup"><span data-stu-id="429f6-118">The following articles have a complete list of .NET Core supported operating systems per version:</span></span>

* [<span data-ttu-id="429f6-119">.NET Core 2.1 - 受支持的操作系统版本</span><span class="sxs-lookup"><span data-stu-id="429f6-119">.NET Core 2.1 - Supported OS Versions</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)
* [<span data-ttu-id="429f6-120">.NET Core 2.0 - 受支持的操作系统版本</span><span class="sxs-lookup"><span data-stu-id="429f6-120">.NET Core 2.0 - Supported OS Versions</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)
* [<span data-ttu-id="429f6-121">.NET Core 1.x - 受支持的操作系统版本</span><span class="sxs-lookup"><span data-stu-id="429f6-121">.NET Core 1.x - Supported OS Versions</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)

## <a name="net-core-dependencies"></a><span data-ttu-id="429f6-122">.NET Core 依赖项</span><span class="sxs-lookup"><span data-stu-id="429f6-122">.NET Core dependencies</span></span>

<span data-ttu-id="429f6-123">在早于 Windows 10 和 Windows Server 2016 的 Windows 版本上运行 .NET Core 1.1 及更低版本时，需要 Visual C++ Redistributable。</span><span class="sxs-lookup"><span data-stu-id="429f6-123">.NET Core 1.1 and earlier versions require the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="429f6-124">.NET Core 安装程序自动安装此依赖项。</span><span class="sxs-lookup"><span data-stu-id="429f6-124">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="429f6-125">如果出现以下情况，必须手动安装 [Microsoft Visual C++ 2015 Redistributable 更新 3](https://www.microsoft.com/download/details.aspx?id=52685)：</span><span class="sxs-lookup"><span data-stu-id="429f6-125">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="429f6-126">使用[安装程序脚本](./tools/dotnet-install-script.md)安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="429f6-126">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="429f6-127">部署独立式 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="429f6-127">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="429f6-128">从源中生成产品。</span><span class="sxs-lookup"><span data-stu-id="429f6-128">Building the product from source.</span></span>
* <span data-ttu-id="429f6-129">通过 .zip 文件安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="429f6-129">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="429f6-130">这可能包括 build/CI/CD 服务器。</span><span class="sxs-lookup"><span data-stu-id="429f6-130">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="429f6-131">对于 Windows 8.1 和更早版本，或 Windows Server 2012 R2 和更早版本：</span><span class="sxs-lookup"><span data-stu-id="429f6-131">**For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:**</span></span>
>
> <span data-ttu-id="429f6-132">确保 Windows 安装是最新版本，并且包括可通过 Windows 更新安装的 [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows)。</span><span class="sxs-lookup"><span data-stu-id="429f6-132">Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows), which can be installed through Windows Update.</span></span> <span data-ttu-id="429f6-133">如果没有安装此更新，则在启动 .NET Core 应用程序时会看到如下错误：`The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span><span class="sxs-lookup"><span data-stu-id="429f6-133">If you don't have this update installed, you'll see an error like the following when you launch a .NET Core application: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span></span>
>
> <span data-ttu-id="429f6-134">对于 Windows 7 或 Windows Server 2008 R2：</span><span class="sxs-lookup"><span data-stu-id="429f6-134">**For Windows 7 or Windows Server 2008 R2:**</span></span>
>
> <span data-ttu-id="429f6-135">除 KB2999226 以外，请确保还安装了 [KB2533623](https://support.microsoft.com/en-us/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)。</span><span class="sxs-lookup"><span data-stu-id="429f6-135">In addition to KB2999226, make sure you also have [KB2533623](https://support.microsoft.com/en-us/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installed.</span></span> <span data-ttu-id="429f6-136">如果没有安装此更新，则在启动 .NET Core 应用程序时会看到如下错误：`The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`。</span><span class="sxs-lookup"><span data-stu-id="429f6-136">If you don't have this update installed, you'll see an error similar to the following when you launch a .NET Core application: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="429f6-137">Visual Studio 2017 的先决条件</span><span class="sxs-lookup"><span data-stu-id="429f6-137">Prerequisites with Visual Studio 2017</span></span>

<span data-ttu-id="429f6-138">可以使用任何编辑器，通过 .NET Core SDK 开发 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="429f6-138">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="429f6-139">[Visual Studio 2017](#visual-studio-2017) 提供了用于在 Windows 上开发 .NET Core 应用程序的集成开发环境。</span><span class="sxs-lookup"><span data-stu-id="429f6-139">[Visual Studio 2017](#visual-studio-2017) provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="429f6-140">在[发行说明](/visualstudio/releasenotes/vs2017-relnotes)中可以详细了解 Visual Studio 2017 中的更改。</span><span class="sxs-lookup"><span data-stu-id="429f6-140">You can read more about the changes in Visual Studio 2017 in the [release notes](/visualstudio/releasenotes/vs2017-relnotes).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="429f6-141">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="429f6-141">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="429f6-142">在 Visual Studio 2017 中开发 .NET Core 2.1 应用：</span><span class="sxs-lookup"><span data-stu-id="429f6-142">To develop .NET Core 2.1 apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="429f6-143">[下载并安装 Visual Studio 2017 版本 15.7.0 或更高版本](/visualstudio/install/install-visual-studio)，并选择“其他工具集”部分中的“.NET Core 跨平台开发”工作负载。</span><span class="sxs-lookup"><span data-stu-id="429f6-143">[Download and install Visual Studio 2017 version 15.7.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![选中“.NET Core 跨平台开发”工作负荷的 Visual Studio 2017 安装的屏幕截图](./media/windows-prerequisites/vs-15-8-workloads.jpg)

<span data-ttu-id="429f6-145">安装“.NET Core 跨平台开发”工具集后，Visual Studio 2017 15.7 默认使用 .NET Core 2.0 SDK，而 Visual Studio 2017 15.8 则默认使用 2.1 SDK。</span><span class="sxs-lookup"><span data-stu-id="429f6-145">After the **.NET Core cross-platform development** toolset is installed, by default, Visual Studio 2017 15.7 uses .NET Core 2.0 SDK and Visual Studio 2017 15.8 uses 2.1 SDK.</span></span>

 2. <span data-ttu-id="429f6-146">如果使用的是 Visual Studio 2017 15.7，则安装 [.NET Core 2.1 SDK](https://www.microsoft.com/net/download/core) 或升级到 Visual Studio 2017 15.8。</span><span class="sxs-lookup"><span data-stu-id="429f6-146">If you're using Visual Studio 2017 15.7, install the [.NET Core 2.1 SDK](https://www.microsoft.com/net/download/core) or upgrade to Visual Studio 2017 15.8.</span></span>

 3. <span data-ttu-id="429f6-147">按照下列说明操作，将现有或新的 .NET Core 项目重定目标到 .NET Core 2.1：</span><span class="sxs-lookup"><span data-stu-id="429f6-147">Retarget existing or new .NET Core projects to .NET Core 2.1 using the following instructions:</span></span>
    * <span data-ttu-id="429f6-148">在“项目”菜单上，选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="429f6-148">On the **Project** menu, Choose **Properties**.</span></span>
    * <span data-ttu-id="429f6-149">在“目标框架”选择菜单上，将值设置为“.NET Core 2.1”。</span><span class="sxs-lookup"><span data-stu-id="429f6-149">In the **Target framework** selection menu, set the value to **.NET Core 2.1**.</span></span>

![已选择“.NET Core 2.0”目标框架菜单项的 Visual Studio 2017 应用程序项目属性屏幕截图](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="429f6-151">使用 .NET Core 2.1 SDK 配置 Visual Studio 后，可执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="429f6-151">Once you have Visual Studio configured with .NET Core 2.1 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="429f6-152">打开、生成和运行现有 .NET Core 1.x 和 2.x 项目。</span><span class="sxs-lookup"><span data-stu-id="429f6-152">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="429f6-153">将 .NET Core 1.x 和 2.0 项目重定目标到 .NET Core 2.1，再生成并运行。</span><span class="sxs-lookup"><span data-stu-id="429f6-153">Retarget .NET Core 1.x and 2.0 projects to .NET Core 2.1, build, and run.</span></span>
* <span data-ttu-id="429f6-154">新建 .NET Core 2.1 项目。</span><span class="sxs-lookup"><span data-stu-id="429f6-154">Create new .NET Core 2.1 projects.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="429f6-155">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="429f6-155">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="429f6-156">在 Visual Studio 2017 中开发 .NET Core 2.0 应用：</span><span class="sxs-lookup"><span data-stu-id="429f6-156">To develop .NET Core 2.0 apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="429f6-157">[下载并安装 Visual Studio 2017 版本 15.3.0 或更高版本](/visualstudio/install/install-visual-studio)，并选择“其他工具集”部分中的“.NET Core 跨平台开发”工作负载。</span><span class="sxs-lookup"><span data-stu-id="429f6-157">[Download and install Visual Studio 2017 version 15.3.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![选中“.NET Core 跨平台开发”工作负荷的 Visual Studio 2017 安装的屏幕截图](./media/windows-prerequisites/vs-15-3-workloads.jpg)

<span data-ttu-id="429f6-159">安装“.NET Core 跨平台开发”工具集后，Visual Studio 2017 默认使用 .NET Core 1.x。</span><span class="sxs-lookup"><span data-stu-id="429f6-159">After the **.NET Core cross-platform development** toolset is installed, Visual Studio 2017 uses .NET Core 1.x by default.</span></span> <span data-ttu-id="429f6-160">安装 .NET Core 2.0 SDK，以便在 Visual Studio 2017 中获取 .NET Core 2.0 支持。</span><span class="sxs-lookup"><span data-stu-id="429f6-160">Install the .NET Core 2.0 SDK to get .NET Core 2.0 support in Visual Studio 2017.</span></span>

 2. <span data-ttu-id="429f6-161">安装 [.NET Core 2.0 SDK](https://www.microsoft.com/net/download/dotnet-core/2.0)。</span><span class="sxs-lookup"><span data-stu-id="429f6-161">Install the [.NET Core 2.0 SDK](https://www.microsoft.com/net/download/dotnet-core/2.0).</span></span>
 3. <span data-ttu-id="429f6-162">按照下列说明操作，将现有或新的 .NET Core 1.x 项目重定目标到 .NET Core 2.0：</span><span class="sxs-lookup"><span data-stu-id="429f6-162">Retarget existing or new .NET Core 1.x projects to .NET Core 2.0 using the following instructions:</span></span>
    * <span data-ttu-id="429f6-163">在“项目”菜单上，选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="429f6-163">On the **Project** menu, Choose **Properties**.</span></span>
    * <span data-ttu-id="429f6-164">在“目标框架”选择菜单上，将值设置为“.NET Core 2.0”。</span><span class="sxs-lookup"><span data-stu-id="429f6-164">In the **Target framework** selection menu, set the value to **.NET Core 2.0**.</span></span>

![已选择“.NET Core 2.0”目标框架菜单项的 Visual Studio 2017 应用程序项目属性屏幕截图](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="429f6-166">安装 .NET Core 2.0 SDK 后，Visual Studio 2017 默认使用 .NET Core SDK 2.0，并支持以下操作：</span><span class="sxs-lookup"><span data-stu-id="429f6-166">Once the .NET Core 2.0 SDK is installed, Visual Studio 2017 uses the .NET Core SDK 2.0 by default, and supports the following actions:</span></span>

* <span data-ttu-id="429f6-167">打开、生成和运行现有 .NET Core 1.x 项目。</span><span class="sxs-lookup"><span data-stu-id="429f6-167">Open, build, and run existing .NET Core 1.x projects.</span></span>
* <span data-ttu-id="429f6-168">将 .NET Core 1.x 项目重定目标到 .NET Core 2.0，再生成并运行。</span><span class="sxs-lookup"><span data-stu-id="429f6-168">Retarget .NET Core 1.x projects to .NET Core 2.0, build, and run.</span></span>
* <span data-ttu-id="429f6-169">新建 .NET Core 2.0 项目。</span><span class="sxs-lookup"><span data-stu-id="429f6-169">Create new .NET Core 2.0 projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="429f6-170">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="429f6-170">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="429f6-171">若要在 Visual Studio 中开发 .NET Core 1.x 应用程序，请[下载并安装 Visual Studio 2017](/visualstudio/install/install-visual-studio)，并选择“其他工具集”部分中的“.NET Core 跨平台开发”工作负载。</span><span class="sxs-lookup"><span data-stu-id="429f6-171">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>

![选中“.NET Core 跨平台开发”工作负荷的 Visual Studio 2017 安装的屏幕截图](./media/windows-prerequisites/vs_workloads.jpg)

> [!IMPORTANT]
> <span data-ttu-id="429f6-173">可以使用 Visual Studio 2015 进行 .NET Core 1.x 开发，但不建议这么做，原因如下：</span><span class="sxs-lookup"><span data-stu-id="429f6-173">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
  > * <span data-ttu-id="429f6-174">.NET Core 工具是预览版，并不受支持。</span><span class="sxs-lookup"><span data-stu-id="429f6-174">The .NET Core tooling is a preview version, which is not supported.</span></span>
  > * <span data-ttu-id="429f6-175">项目依据的 project.json 已遭弃用。</span><span class="sxs-lookup"><span data-stu-id="429f6-175">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="429f6-176">若要详细了解项目格式更改，请参阅[变更的简要概览](./tools/cli-msbuild-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="429f6-176">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>
---

<a name="vs-mapping"></a>

> [!TIP]
> <span data-ttu-id="429f6-177">若要验证 Visual Studio 2017 版本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="429f6-177">To verify your Visual Studio 2017 version:</span></span>
>
> * <span data-ttu-id="429f6-178">在“帮助”菜单上，选择“关于 Microsoft Visual Studio”。</span><span class="sxs-lookup"><span data-stu-id="429f6-178">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
> * <span data-ttu-id="429f6-179">在“关于 Microsoft Visual Studio”对话框中，验证版本号。</span><span class="sxs-lookup"><span data-stu-id="429f6-179">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>   * <span data-ttu-id="429f6-180">对于 .NET Core 2.2 Preview 1 应用，Visual Studio 2017 版本应为 15.9（当前是预览版）或更高版本。</span><span class="sxs-lookup"><span data-stu-id="429f6-180">For .NET Core 2.2 Preview 1 apps, Visual Studio 2017 version 15.9 (currently in Preview) or higher.</span></span>
>   * <span data-ttu-id="429f6-181">对于 .NET Core 2.1 应用，Visual Studio 2017 版本应为 15.7 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="429f6-181">For .NET Core 2.1 apps, Visual Studio 2017 version 15.7 or higher.</span></span>
>   * <span data-ttu-id="429f6-182">对于 .NET Core 2.0 应用，Visual Studio 2017 版本应为 15.3 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="429f6-182">For .NET Core 2.0 apps, Visual Studio 2017 version 15.3 or higher.</span></span>
>   * <span data-ttu-id="429f6-183">对于 .NET Core 1.x 应用，Visual Studio 2017 版本应为 15.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="429f6-183">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 or higher.</span></span>
