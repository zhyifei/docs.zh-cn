---
title: Windows 上 .NET Core 的先决条件
description: 了解在 Windows 计算机上开发和运行 .NET Core 应用程序所需的依赖项。
f1_keywords:
- NETSDK1045
ms.custom: updateeachvsrelease
ms.date: 09/20/2019
ms.openlocfilehash: 6885f6c853efb0dcb2cb64b83f07e12b1dc2e3cf
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771955"
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="51ed6-103">Windows 上 .NET Core 的先决条件</span><span class="sxs-lookup"><span data-stu-id="51ed6-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="51ed6-104">本文介绍在 Windows 上运行 .NET Core 应用程序所支持的 OS 版本。</span><span class="sxs-lookup"><span data-stu-id="51ed6-104">This article shows the supported OS versions in order to run .NET Core applications on Windows.</span></span> <span data-ttu-id="51ed6-105">支持的 OS 版本和依赖项适用于在 Windows 上开发 .NET Core 应用程序的三种方法：</span><span class="sxs-lookup"><span data-stu-id="51ed6-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="51ed6-106">命令行</span><span class="sxs-lookup"><span data-stu-id="51ed6-106">Command line</span></span>](./tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="51ed6-107">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="51ed6-107">Visual Studio</span></span>](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)
* [<span data-ttu-id="51ed6-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="51ed6-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

<span data-ttu-id="51ed6-109">此外，如果你正在使用 Visual Studio 开发 Windows，请查看[有关使用 Visual Studio 开发 .NET Core 应用的先决条件](#prerequisites-to-develop-net-core-apps-with-visual-studio)部分，更详细地了解支持 .NET Core 开发的最低版本。</span><span class="sxs-lookup"><span data-stu-id="51ed6-109">Also, if you're developing on Windows using Visual Studio, the [Prerequisites to develop .NET Core apps with Visual Studio](#prerequisites-to-develop-net-core-apps-with-visual-studio) section goes in more detail about minimum versions supported for .NET Core development.</span></span>

## <a name="net-core-supported-operating-systems"></a><span data-ttu-id="51ed6-110">.NET Core 支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="51ed6-110">.NET Core supported operating systems</span></span>

<span data-ttu-id="51ed6-111">以下文章提供了 .NET Core 针对每个版本所支持的操作系统的完整列表：</span><span class="sxs-lookup"><span data-stu-id="51ed6-111">The following articles have a complete list of .NET Core supported operating systems per version:</span></span>

* [<span data-ttu-id="51ed6-112">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="51ed6-112">.NET Core 3.0</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [<span data-ttu-id="51ed6-113">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="51ed6-113">.NET Core 2.2</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [<span data-ttu-id="51ed6-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="51ed6-114">.NET Core 2.1</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)

<span data-ttu-id="51ed6-115">有关下载链接和详细信息，请参阅 [.NET 下载](https://dotnet.microsoft.com/download)下载最新版本或 [.NET 下载存档](https://dotnet.microsoft.com/download/archives#dotnet-core)下载较旧版本。</span><span class="sxs-lookup"><span data-stu-id="51ed6-115">For download links and more information, see [.NET downloads](https://dotnet.microsoft.com/download) to download the latest version or [.NET downloads archive](https://dotnet.microsoft.com/download/archives#dotnet-core) for older versions.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="51ed6-116">.NET Core 依赖项</span><span class="sxs-lookup"><span data-stu-id="51ed6-116">.NET Core dependencies</span></span>

<span data-ttu-id="51ed6-117">如果出现以下情况，必须手动安装 [Microsoft Visual C++ 2015 Redistributable 更新 3](https://www.microsoft.com/download/details.aspx?id=52685)：</span><span class="sxs-lookup"><span data-stu-id="51ed6-117">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="51ed6-118">使用[安装程序脚本](./tools/dotnet-install-script.md)安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="51ed6-118">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="51ed6-119">部署独立式 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="51ed6-119">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="51ed6-120">从源中生成产品。</span><span class="sxs-lookup"><span data-stu-id="51ed6-120">Building the product from source.</span></span>
* <span data-ttu-id="51ed6-121">通过 .zip 文件  安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="51ed6-121">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="51ed6-122">这可能包括 build/CI/CD 服务器。</span><span class="sxs-lookup"><span data-stu-id="51ed6-122">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="51ed6-123">对于 Windows 8.1 和更早版本，或 Windows Server 2012 R2 和更早版本： </span><span class="sxs-lookup"><span data-stu-id="51ed6-123">**For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:**</span></span>
>
> <span data-ttu-id="51ed6-124">确保 Windows 安装是最新版本，并且包括可通过 Windows 更新安装的 [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)。</span><span class="sxs-lookup"><span data-stu-id="51ed6-124">Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), which can be installed through Windows Update.</span></span> <span data-ttu-id="51ed6-125">如果没有安装此更新，则在启动 .NET Core 应用程序时会看到如下错误：`The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span><span class="sxs-lookup"><span data-stu-id="51ed6-125">If you don't have this update installed, you'll see an error like the following when you launch a .NET Core application: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span></span>
>
> <span data-ttu-id="51ed6-126">对于 Windows 7 或 Windows Server 2008 R2： </span><span class="sxs-lookup"><span data-stu-id="51ed6-126">**For Windows 7 or Windows Server 2008 R2:**</span></span>
>
> <span data-ttu-id="51ed6-127">除 KB2999226 以外，请确保还安装了 [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)。</span><span class="sxs-lookup"><span data-stu-id="51ed6-127">In addition to KB2999226, make sure you also have [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installed.</span></span> <span data-ttu-id="51ed6-128">如果没有安装此更新，则在启动 .NET Core 应用程序时会看到如下错误：`The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`。</span><span class="sxs-lookup"><span data-stu-id="51ed6-128">If you don't have this update installed, you'll see an error similar to the following when you launch a .NET Core application: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span></span>

## <a name="prerequisites-to-develop-net-core-apps-with-visual-studio"></a><span data-ttu-id="51ed6-129">有关使用 Visual Studio 开发 .NET Core 应用的先决条件</span><span class="sxs-lookup"><span data-stu-id="51ed6-129">Prerequisites to develop .NET Core apps with Visual Studio</span></span>

<span data-ttu-id="51ed6-130">尽管可使用任意编辑器结合 .NET Core SDK 来开发 .NET Core 应用程序，但 Visual Studio 2017 及更高版本对 Windows 上的 .NET Core 应用提供了一个集成开发环境。</span><span class="sxs-lookup"><span data-stu-id="51ed6-130">Even though you can use any editor to develop .NET Core applications using the .NET Core SDK, Visual Studio 2017 and later versions provide an integrated development environment for .NET Core apps on Windows.</span></span>

<a name="vs-mapping"></a>

<span data-ttu-id="51ed6-131">每个 .NET Core 版本都有 Visual Studio 最低版本的要求。</span><span class="sxs-lookup"><span data-stu-id="51ed6-131">Each .NET Core version has a minimum version of Visual Studio required.</span></span> <span data-ttu-id="51ed6-132">若要验证 Visual Studio 版本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="51ed6-132">To verify your Visual Studio version:</span></span>

* <span data-ttu-id="51ed6-133">在“帮助”  菜单上，选择“关于 Microsoft Visual Studio”  。</span><span class="sxs-lookup"><span data-stu-id="51ed6-133">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
* <span data-ttu-id="51ed6-134">在“关于 Microsoft Visual Studio”  对话框中，验证版本号。</span><span class="sxs-lookup"><span data-stu-id="51ed6-134">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>

<span data-ttu-id="51ed6-135">下表列出了每个 SDK 的最低版本：</span><span class="sxs-lookup"><span data-stu-id="51ed6-135">The following table lists the minimum version for each SDK:</span></span>

| <span data-ttu-id="51ed6-136">.NET Core SDK 版本</span><span class="sxs-lookup"><span data-stu-id="51ed6-136">.NET Core SDK version</span></span> | <span data-ttu-id="51ed6-137">Visual Studio 版本</span><span class="sxs-lookup"><span data-stu-id="51ed6-137">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="51ed6-138">3.0</span><span class="sxs-lookup"><span data-stu-id="51ed6-138">3.0</span></span>                   | <span data-ttu-id="51ed6-139">Visual Studio 2019 版本 16.3 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="51ed6-139">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="51ed6-140">2.2</span><span class="sxs-lookup"><span data-stu-id="51ed6-140">2.2</span></span>                   | <span data-ttu-id="51ed6-141">Visual Studio 2017 版本 15.9 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="51ed6-141">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="51ed6-142">2.1</span><span class="sxs-lookup"><span data-stu-id="51ed6-142">2.1</span></span>                   | <span data-ttu-id="51ed6-143">Visual Studio 2017 版本 15.7 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="51ed6-143">Visual Studio 2017 version 15.7 or higher.</span></span> |
| <span data-ttu-id="51ed6-144">1.x</span><span class="sxs-lookup"><span data-stu-id="51ed6-144">1.x</span></span>                   | <span data-ttu-id="51ed6-145">Visual Studio 2017 版本 15.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="51ed6-145">Visual Studio 2017 version 15.0 or higher.</span></span> |

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="51ed6-146">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="51ed6-146">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="51ed6-147">要使用 .NET Core 3.0 SDK 在 Visual Studio 2019 中开发 .NET Core 应用：</span><span class="sxs-lookup"><span data-stu-id="51ed6-147">To develop .NET Core apps in Visual Studio 2019 using the .NET Core 3.0 SDK:</span></span>

* <span data-ttu-id="51ed6-148">[下载并安装 Visual Studio 2019 版本 16.3 或更高版本](/visualstudio/install/install-visual-studio)，然后选择下述其中一个包含 .NET Core SDK 的工作负荷（具体取决于你要构建的应用程序类型）：</span><span class="sxs-lookup"><span data-stu-id="51ed6-148">[Download and install Visual Studio 2019 version 16.3 or higher](/visualstudio/install/install-visual-studio) and select one of the following workloads that includes the .NET Core SDK, depending on the kind of application you're building:</span></span>

  * <span data-ttu-id="51ed6-149">“其他工具集”部分中的“.NET Core 跨平台开发”工作负荷   。</span><span class="sxs-lookup"><span data-stu-id="51ed6-149">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
  * <span data-ttu-id="51ed6-150">“Web 和云”部分中的“ASP.NET 和 Web 开发”工作负荷   。</span><span class="sxs-lookup"><span data-stu-id="51ed6-150">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
  * <span data-ttu-id="51ed6-151">“Windows”部分中的“NET 桌面开发”工作负荷   。</span><span class="sxs-lookup"><span data-stu-id="51ed6-151">The **NET desktop development** workload in the **Windows** section.</span></span>

<span data-ttu-id="51ed6-152">下图显示了已在 Visual Studio UI 中选择“.NET Core 跨平台开发”工作负荷  ：</span><span class="sxs-lookup"><span data-stu-id="51ed6-152">The following image shows the **.NET Core cross-platform development** workload selected in the Visual Studio UI:</span></span>

![Visual Studio 2019 安装的屏幕截图，其中勾选了“.NET Core 跨平台开发”工作负荷](./media/windows-prerequisites/vs-2019-workloads.jpg)

<span data-ttu-id="51ed6-154">在安装上述任何工作负载后，Visual Studio 2019 版本 16.3 默认使用 .NET Core 3.0 SDK。</span><span class="sxs-lookup"><span data-stu-id="51ed6-154">Visual Studio 2019 version 16.3 uses .NET Core 3.0 SDK by default after any of these workloads are installed.</span></span>

<span data-ttu-id="51ed6-155">如果希望现有项目使用最新的 .NET Core 运行时，请按照下述说明将每个现有的 .NET Core 项目重定目标到 .NET Core 3.0：</span><span class="sxs-lookup"><span data-stu-id="51ed6-155">If you want your existing projects to use the latest .NET Core runtime, retarget each existing .NET Core project to .NET Core 3.0 using the following instructions:</span></span>

* <span data-ttu-id="51ed6-156">在 **“项目”** 菜单上，选择 **“属性”** 。</span><span class="sxs-lookup"><span data-stu-id="51ed6-156">On the **Project** menu, choose **Properties**.</span></span>
* <span data-ttu-id="51ed6-157">在“目标框架”选择菜单上，将值设置为“.NET Core 3.0”   。</span><span class="sxs-lookup"><span data-stu-id="51ed6-157">In the **Target framework** selection menu, set the value to **.NET Core 3.0**.</span></span>

![Visual Studio 2019 应用程序项目属性的屏幕截图，其中已勾选“.NET Core 3.0”目标框架菜单项](./media/windows-prerequisites/target-dotnet-core-3-0.jpg)

<span data-ttu-id="51ed6-159">使用 .NET Core 3.0 SDK 配置 Visual Studio 后，可执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="51ed6-159">Once you have Visual Studio configured with .NET Core 3.0 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="51ed6-160">打开、生成和运行现有 .NET Core 1.x 和 2.x 项目。</span><span class="sxs-lookup"><span data-stu-id="51ed6-160">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="51ed6-161">将 .NET Core 1.x 和 2.x 项目重定目标到 .NET Core 3.0，进行生成，然后运行。</span><span class="sxs-lookup"><span data-stu-id="51ed6-161">Retarget .NET Core 1.x and 2.x projects to .NET Core 3.0, build, and run.</span></span>
* <span data-ttu-id="51ed6-162">新建 .NET Core 3.0 项目。</span><span class="sxs-lookup"><span data-stu-id="51ed6-162">Create new .NET Core 3.0 projects.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="51ed6-163">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="51ed6-163">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="51ed6-164">若要使用 .NET Core 2.2 SDK 在 Visual Studio 2017 中开发 .NET Core 应用：</span><span class="sxs-lookup"><span data-stu-id="51ed6-164">To develop .NET Core apps in Visual Studio 2017 using the .NET Core 2.2 SDK:</span></span>

* <span data-ttu-id="51ed6-165">[下载并安装 Visual Studio 2019 版本 16.3 或更高版本](/visualstudio/install/install-visual-studio)，并选择“其他工具集”部分中的“.NET Core 跨平台开发”工作负荷   。</span><span class="sxs-lookup"><span data-stu-id="51ed6-165">[Download and install Visual Studio 2019 version 16.3 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>
* <span data-ttu-id="51ed6-166">[下载并安装 Visual Studio 2017 版本 15.9.0 或更高版本](/visualstudio/install/install-visual-studio)，并选择“其他工具集”  部分中的“.NET Core 跨平台开发”  工作负载。</span><span class="sxs-lookup"><span data-stu-id="51ed6-166">[Download and install Visual Studio 2017 version 15.9.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![选中“.NET Core 跨平台开发”工作负荷的 Visual Studio 2017 安装的屏幕截图](./media/windows-prerequisites/vs-2017-workloads.jpg)

<span data-ttu-id="51ed6-168">安装“.NET Core 跨平台开发”  工具集后，Visual Studio 通常会安装以前版本的 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="51ed6-168">After the **.NET Core cross-platform development** toolset is installed, Visual Studio usually installs a previous version of the .NET Core SDK.</span></span>
<span data-ttu-id="51ed6-169">例如，Visual Studio 2017 版本 15.9 在安装工作负载后默认使用 .NET Core 2.1 SDK。</span><span class="sxs-lookup"><span data-stu-id="51ed6-169">For example, Visual Studio 2017 version 15.9 uses .NET Core 2.1 SDK by default after the workload is installed.</span></span>

<span data-ttu-id="51ed6-170">若要更新 Visual Studio 以使用 .NET Core 2.2 SDK：</span><span class="sxs-lookup"><span data-stu-id="51ed6-170">To update Visual Studio to use .NET Core 2.2 SDK:</span></span>

 1. <span data-ttu-id="51ed6-171">安装 [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)。</span><span class="sxs-lookup"><span data-stu-id="51ed6-171">Install the [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).</span></span>

 1. <span data-ttu-id="51ed6-172">如果希望项目使用最新的 .NET Core 运行时，请按照以下说明将每个现有或新的 .NET Core 项目重定目标到 .NET Core 2.2：</span><span class="sxs-lookup"><span data-stu-id="51ed6-172">If you want your project to use the latest .NET Core runtime, retarget each existing or new .NET Core project to .NET Core 2.2 using the following instructions:</span></span>

    * <span data-ttu-id="51ed6-173">在 **“项目”** 菜单上，选择 **“属性”** 。</span><span class="sxs-lookup"><span data-stu-id="51ed6-173">On the **Project** menu, choose **Properties**.</span></span>
    * <span data-ttu-id="51ed6-174">在“目标框架”  选择菜单上，将值设置为“.NET Core 2.2”  。</span><span class="sxs-lookup"><span data-stu-id="51ed6-174">In the **Target framework** selection menu, set the value to **.NET Core 2.2**.</span></span>

![已选择“.NET Core 2.2”目标框架菜单项的 Visual Studio 2017 应用程序项目属性屏幕截图](./media/windows-prerequisites/targeting-dotnet-core.jpg)

<span data-ttu-id="51ed6-176">使用 .NET Core 2.2 SDK 配置 Visual Studio 后，可执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="51ed6-176">Once you have Visual Studio configured with .NET Core 2.2 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="51ed6-177">打开、生成和运行现有 .NET Core 1.x 和 2.x 项目。</span><span class="sxs-lookup"><span data-stu-id="51ed6-177">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="51ed6-178">将 .NET Core 1.x 和 2.x 项目重定目标到 .NET Core 2.2，再生成并运行。</span><span class="sxs-lookup"><span data-stu-id="51ed6-178">Retarget .NET Core 1.x and 2.x projects to .NET Core 2.2, build, and run.</span></span>
* <span data-ttu-id="51ed6-179">新建 .NET Core 2.2 项目。</span><span class="sxs-lookup"><span data-stu-id="51ed6-179">Create new .NET Core 2.2 projects.</span></span>

---
