---
title: Windows 上 .NET Core 的先决条件
description: 了解在 Windows 计算机上开发和运行 .NET Core 应用程序所需的依赖项。
ms.custom: updateeachvsrelease
ms.date: 04/08/2019
ms.openlocfilehash: 7b2bf2b8353c4f02fa11e9e7531e0d936007be0b
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2019
ms.locfileid: "70970289"
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="c7a7b-103">Windows 上 .NET Core 的先决条件</span><span class="sxs-lookup"><span data-stu-id="c7a7b-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="c7a7b-104">本文介绍在 Windows 上运行 .NET Core 应用程序所支持的 OS 版本。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-104">This article shows the supported OS versions in order to run .NET Core applications on Windows.</span></span> <span data-ttu-id="c7a7b-105">支持的 OS 版本和依赖项适用于在 Windows 上开发 .NET Core 应用程序的三种方法：</span><span class="sxs-lookup"><span data-stu-id="c7a7b-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="c7a7b-106">命令行</span><span class="sxs-lookup"><span data-stu-id="c7a7b-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="c7a7b-107">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c7a7b-107">Visual Studio</span></span>](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)
* [<span data-ttu-id="c7a7b-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c7a7b-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

<span data-ttu-id="c7a7b-109">此外，如果你正在使用 Visual Studio 2017 开发 Windows，[使用 Visual Studio 2017 的先决条件](#prerequisites-with-visual-studio-2017)部分更详细地介绍了有关支持 .NET Core 开发的最小版本。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-109">Also, if you're developing on Windows using Visual Studio 2017, the [Prerequisites with Visual Studio 2017](#prerequisites-with-visual-studio-2017) section goes in more detail about minimum versions supported for .NET Core development.</span></span>

## <a name="net-core-supported-operating-systems"></a><span data-ttu-id="c7a7b-110">.NET Core 支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="c7a7b-110">.NET Core supported operating systems</span></span>

<span data-ttu-id="c7a7b-111">以下文章提供了 .NET Core 针对每个版本所支持的操作系统的完整列表：</span><span class="sxs-lookup"><span data-stu-id="c7a7b-111">The following articles have a complete list of .NET Core supported operating systems per version:</span></span>

* [<span data-ttu-id="c7a7b-112">.NET Core 3.0（预览版）</span><span class="sxs-lookup"><span data-stu-id="c7a7b-112">.NET Core 3.0 (Preview)</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [<span data-ttu-id="c7a7b-113">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="c7a7b-113">.NET Core 2.2</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [<span data-ttu-id="c7a7b-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c7a7b-114">.NET Core 2.1</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)
* [<span data-ttu-id="c7a7b-115">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c7a7b-115">.NET Core 1.0</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)

<span data-ttu-id="c7a7b-116">有关下载链接和详细信息，请参阅 [.NET 下载](https://dotnet.microsoft.com/download)下载最新版本或 [.NET 下载存档](https://dotnet.microsoft.com/download/archives#dotnet-core)下载较旧版本。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-116">For download links and more information, see [.NET downloads](https://dotnet.microsoft.com/download) to download the latest version or [.NET downloads archive](https://dotnet.microsoft.com/download/archives#dotnet-core) for older versions.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="c7a7b-117">.NET Core 依赖项</span><span class="sxs-lookup"><span data-stu-id="c7a7b-117">.NET Core dependencies</span></span>

<span data-ttu-id="c7a7b-118">在早于 Windows 10 和 Windows Server 2016 的 Windows 版本上运行 .NET Core 1.1 及更低版本时，需要 Visual C++ Redistributable。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-118">.NET Core 1.1 and earlier versions require the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="c7a7b-119">.NET Core 安装程序自动安装此依赖项。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-119">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="c7a7b-120">如果出现以下情况，必须手动安装 [Microsoft Visual C++ 2015 Redistributable 更新 3](https://www.microsoft.com/download/details.aspx?id=52685)：</span><span class="sxs-lookup"><span data-stu-id="c7a7b-120">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="c7a7b-121">使用[安装程序脚本](./tools/dotnet-install-script.md)安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-121">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="c7a7b-122">部署独立式 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-122">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="c7a7b-123">从源中生成产品。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-123">Building the product from source.</span></span>
* <span data-ttu-id="c7a7b-124">通过 .zip 文件  安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-124">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="c7a7b-125">这可能包括 build/CI/CD 服务器。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-125">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="c7a7b-126">对于 Windows 8.1 和更早版本，或 Windows Server 2012 R2 和更早版本： </span><span class="sxs-lookup"><span data-stu-id="c7a7b-126">**For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:**</span></span>
>
> <span data-ttu-id="c7a7b-127">确保 Windows 安装是最新版本，并且包括可通过 Windows 更新安装的 [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-127">Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), which can be installed through Windows Update.</span></span> <span data-ttu-id="c7a7b-128">如果没有安装此更新，则在启动 .NET Core 应用程序时会看到如下错误：`The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span><span class="sxs-lookup"><span data-stu-id="c7a7b-128">If you don't have this update installed, you'll see an error like the following when you launch a .NET Core application: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span></span>
>
> <span data-ttu-id="c7a7b-129">对于 Windows 7 或 Windows Server 2008 R2： </span><span class="sxs-lookup"><span data-stu-id="c7a7b-129">**For Windows 7 or Windows Server 2008 R2:**</span></span>
>
> <span data-ttu-id="c7a7b-130">除 KB2999226 以外，请确保还安装了 [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-130">In addition to KB2999226, make sure you also have [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installed.</span></span> <span data-ttu-id="c7a7b-131">如果没有安装此更新，则在启动 .NET Core 应用程序时会看到如下错误：`The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-131">If you don't have this update installed, you'll see an error similar to the following when you launch a .NET Core application: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span></span>

## <a name="prerequisites-for-net-core-30-preview-3"></a><span data-ttu-id="c7a7b-132">.NET Core 3.0 预览版 3 的先决条件</span><span class="sxs-lookup"><span data-stu-id="c7a7b-132">Prerequisites for .NET Core 3.0 Preview 3</span></span>

<span data-ttu-id="c7a7b-133">.NET core 3.0 预览版 3 的先决条件与其他 .NET Core 版本相同。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-133">.NET Core 3.0 Preview 3 has the same prerequisites as other versions of .NET Core.</span></span> <span data-ttu-id="c7a7b-134">不过，若要使用 Visual Studio 创建 .NET Core 3.0 项目，必须使用 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-134">However, if you want to use Visual Studio to create .NET Core 3.0 projects, you must use the [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span></span> <span data-ttu-id="c7a7b-135">Visual Studio 2019 可以与其他 Visual studio 版本并行安装，而不会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-135">Visual Studio 2019 can be installed side-by-side with other versions of Visual Studio without conflict.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="c7a7b-136">Visual Studio 2017 的先决条件</span><span class="sxs-lookup"><span data-stu-id="c7a7b-136">Prerequisites with Visual Studio 2017</span></span>
    
<span data-ttu-id="c7a7b-137">可以使用任何编辑器，通过 .NET Core SDK 开发 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-137">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="c7a7b-138">Visual Studio 2017 提供了用于在 Windows 上开发 .NET Core 应用程序的集成开发环境。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-138">Visual Studio 2017 provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="c7a7b-139">在[发行说明](/visualstudio/releasenotes/vs2017-relnotes)中可以详细了解 Visual Studio 2017 中的更改。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-139">You can read more about the changes in Visual Studio 2017 in the [release notes](/visualstudio/releasenotes/vs2017-relnotes).</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c7a7b-140">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c7a7b-140">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="c7a7b-141">若要使用 .NET Core 2.2 SDK 在 Visual Studio 2017 中开发 .NET Core 应用：</span><span class="sxs-lookup"><span data-stu-id="c7a7b-141">To develop .NET Core apps in Visual Studio 2017 using the .NET Core 2.2 SDK:</span></span>

 1. <span data-ttu-id="c7a7b-142">[下载并安装 Visual Studio 2017 版本 15.9.0 或更高版本](/visualstudio/install/install-visual-studio)，并选择“其他工具集”  部分中的“.NET Core 跨平台开发”  工作负载。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-142">[Download and install Visual Studio 2017 version 15.9.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![选中“.NET Core 跨平台开发”工作负荷的 Visual Studio 2017 安装的屏幕截图](./media/windows-prerequisites/vs-2017-workloads.jpg)

<span data-ttu-id="c7a7b-144">安装“.NET Core 跨平台开发”  工具集后，Visual Studio 通常会安装以前版本的 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-144">After the **.NET Core cross-platform development** toolset is installed, Visual Studio usually installs a previous version of the .NET Core SDK.</span></span>
<span data-ttu-id="c7a7b-145">例如，Visual Studio 2017 15.9 在安装工作负载后默认使用 .NET Core 2.1 SDK。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-145">For example, Visual Studio 2017 15.9 uses .NET Core 2.1 SDK by default after the workload is installed.</span></span>

<span data-ttu-id="c7a7b-146">若要更新 Visual Studio 以使用 .NET Core 2.2 SDK：</span><span class="sxs-lookup"><span data-stu-id="c7a7b-146">To update Visual Studio to use .NET Core 2.2 SDK:</span></span>

 1. <span data-ttu-id="c7a7b-147">安装 [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-147">Install the [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).</span></span>

 1. <span data-ttu-id="c7a7b-148">如果希望项目使用最新的 .NET Core 运行时，请使用以下说明将现有或新的 .NET Core 项目重定目标到 .NET Core 2.2：</span><span class="sxs-lookup"><span data-stu-id="c7a7b-148">If you want your project to use the latest .NET Core runtime, retarget existing or new .NET Core projects to .NET Core 2.2 using the following instructions:</span></span>

    * <span data-ttu-id="c7a7b-149">在 **“项目”** 菜单上，选择 **“属性”** 。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-149">On the **Project** menu, choose **Properties**.</span></span>
    * <span data-ttu-id="c7a7b-150">在“目标框架”  选择菜单上，将值设置为“.NET Core 2.2”  。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-150">In the **Target framework** selection menu, set the value to **.NET Core 2.2**.</span></span>

![已选择“.NET Core 2.2”目标框架菜单项的 Visual Studio 2017 应用程序项目属性屏幕截图](./media/windows-prerequisites/targeting-dotnet-core.jpg)

<span data-ttu-id="c7a7b-152">使用 .NET Core 2.2 SDK 配置 Visual Studio 后，可执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c7a7b-152">Once you have Visual Studio configured with .NET Core 2.2 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="c7a7b-153">打开、生成和运行现有 .NET Core 1.x 和 2.x 项目。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-153">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="c7a7b-154">将 .NET Core 1.x 和 2.x 项目重定目标到 .NET Core 2.2，再生成并运行。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-154">Retarget .NET Core 1.x and 2.x projects to .NET Core 2.2, build, and run.</span></span>
* <span data-ttu-id="c7a7b-155">新建 .NET Core 2.2 项目。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-155">Create new .NET Core 2.2 projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c7a7b-156">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c7a7b-156">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="c7a7b-157">若要在 Visual Studio 中开发 .NET Core 1.x 应用程序，请[下载并安装 Visual Studio 2017](/visualstudio/install/install-visual-studio)，并选择“其他工具集”  部分中的“.NET Core 跨平台开发”  工作负载。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-157">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>

![选中“.NET Core 跨平台开发”工作负荷的 Visual Studio 2017 安装的屏幕截图](./media/windows-prerequisites/vs-workloads.jpg)

> [!IMPORTANT]
> <span data-ttu-id="c7a7b-159">可以使用 Visual Studio 2015 进行 .NET Core 1.x 开发，但不建议这么做，原因如下：</span><span class="sxs-lookup"><span data-stu-id="c7a7b-159">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
>
> * <span data-ttu-id="c7a7b-160">.NET Core 工具是预览版，并不受支持。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-160">The .NET Core tooling is a preview version, which is not supported.</span></span>
> * <span data-ttu-id="c7a7b-161">项目依据的 project.json 已遭弃用。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-161">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="c7a7b-162">若要详细了解项目格式更改，请参阅[变更的简要概览](./tools/cli-msbuild-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-162">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>

---

<a name="vs-mapping"></a>

> [!TIP]
> <span data-ttu-id="c7a7b-163">若要验证 Visual Studio 版本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c7a7b-163">To verify your Visual Studio version:</span></span>
>
> * <span data-ttu-id="c7a7b-164">在“帮助”  菜单上，选择“关于 Microsoft Visual Studio”  。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-164">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
> * <span data-ttu-id="c7a7b-165">在“关于 Microsoft Visual Studio”  对话框中，验证版本号。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-165">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>   * <span data-ttu-id="c7a7b-166">对于 .NET Core 3.0 预览版 3 应用，Visual Studio 2019 版本应为 16.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-166">For .NET Core 3.0 Preview 3 apps, Visual Studio 2019 version 16.0 or higher.</span></span>
>   * <span data-ttu-id="c7a7b-167">对于 .NET Core 2.2 应用，Visual Studio 2017 版本应为 15.9 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-167">For .NET Core 2.2 apps, Visual Studio 2017 version 15.9 or higher.</span></span>
>   * <span data-ttu-id="c7a7b-168">对于 .NET Core 2.1 应用，Visual Studio 2017 版本应为 15.7 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-168">For .NET Core 2.1 apps, Visual Studio 2017 version 15.7 or higher.</span></span>
>   * <span data-ttu-id="c7a7b-169">对于 .NET Core 1.x 应用，Visual Studio 2017 版本应为 15.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="c7a7b-169">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 or higher.</span></span>
