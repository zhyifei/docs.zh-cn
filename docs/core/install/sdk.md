---
title: 在 Windows、Linux 和 macOS 上安装 .NET Core SDK - .NET Core
description: 了解如何在 Windows、Linux 和 macOS 上安装 .NET Core。 发现开发 .NET Core 应用所需的依赖项。
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 0aa323533dd9136372c2bbc330c9c3056fdf428c
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157566"
---
# <a name="install-the-net-core-sdk"></a><span data-ttu-id="d1020-104">安装 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="d1020-104">Install the .NET Core SDK</span></span>

<span data-ttu-id="d1020-105">本文介绍如何安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="d1020-105">In this article, you'll learn how to install the .NET Core SDK.</span></span> <span data-ttu-id="d1020-106">.NET Core SDK 用于创建 .NET Core 应用和库。</span><span class="sxs-lookup"><span data-stu-id="d1020-106">The .NET Core SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="d1020-107">.NET Core 运行时始终随 SDK 一起安装。</span><span class="sxs-lookup"><span data-stu-id="d1020-107">The .NET Core runtime is always installed with the SDK.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="d1020-108">使用安装程序安装</span><span class="sxs-lookup"><span data-stu-id="d1020-108">Install with an installer</span></span>

<span data-ttu-id="d1020-109">Windows 具有独立的安装程序，可用于安装 .NET Core 3.1 SDK：</span><span class="sxs-lookup"><span data-stu-id="d1020-109">Windows has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="d1020-110">x64（64 位）CPU</span><span class="sxs-lookup"><span data-stu-id="d1020-110">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="d1020-111">x86（32 位）CPU</span><span class="sxs-lookup"><span data-stu-id="d1020-111">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="d1020-112">使用安装程序安装</span><span class="sxs-lookup"><span data-stu-id="d1020-112">Install with an installer</span></span>

<span data-ttu-id="d1020-113">macOS 具有独立的安装程序，可用于安装 .NET Core 3.1 SDK：</span><span class="sxs-lookup"><span data-stu-id="d1020-113">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="d1020-114">x64（64 位）CPU</span><span class="sxs-lookup"><span data-stu-id="d1020-114">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="d1020-115">下载并手动安装</span><span class="sxs-lookup"><span data-stu-id="d1020-115">Download and manually install</span></span>

<span data-ttu-id="d1020-116">除了使用适用于 .NET Core 的 macOS 安装程序，还可以下载并手动安装 SDK。</span><span class="sxs-lookup"><span data-stu-id="d1020-116">As an alternative to the macOS installers for .NET Core, you can download and manually install the SDK.</span></span>

<span data-ttu-id="d1020-117">若要提取 SDK 并使 .NET Core CLI 命令可用于终端，请先[下载](#all-net-core-downloads) .NET Core 二进制版本。</span><span class="sxs-lookup"><span data-stu-id="d1020-117">To extract the SDK and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="d1020-118">然后，打开终端并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="d1020-118">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="d1020-119">假定将运行时下载到 `~/Downloads/dotnet-sdk.pkg` 文件中。</span><span class="sxs-lookup"><span data-stu-id="d1020-119">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-sdk.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-sdk.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="d1020-120">使用包管理器安装</span><span class="sxs-lookup"><span data-stu-id="d1020-120">Install with a package manager</span></span>

<span data-ttu-id="d1020-121">可使用许多常见的 Linux 包管理器安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="d1020-121">You can install the .NET Core SDK with many of the common Linux package managers.</span></span> <span data-ttu-id="d1020-122">有关详细信息，请参阅 [Linux 包管理器 - 安装 .NET Core](linux-package-managers.md)。</span><span class="sxs-lookup"><span data-stu-id="d1020-122">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="d1020-123">仅在 x64 体系结构上支持使用包管理器安装。</span><span class="sxs-lookup"><span data-stu-id="d1020-123">Installing with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="d1020-124">如果要使用其他体系结构（如 ARM）安装 .NET Core SDK，请遵循下面的[下载并手动安装](#download-and-manually-install)说明。</span><span class="sxs-lookup"><span data-stu-id="d1020-124">If you're installing the .NET Core SDK with a different architecture, such as ARM, follow the [Download and manually install](#download-and-manually-install) instructions below.</span></span> <span data-ttu-id="d1020-125">有关支持的体系结构的详细信息，请参阅 [.NET Core 依赖项和要求](dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="d1020-125">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="d1020-126">下载并手动安装</span><span class="sxs-lookup"><span data-stu-id="d1020-126">Download and manually install</span></span>

<span data-ttu-id="d1020-127">若要提取 SDK 并使 .NET Core CLI 命令可用于终端，请先[下载](#all-net-core-downloads) .NET Core 二进制版本。</span><span class="sxs-lookup"><span data-stu-id="d1020-127">To extract the SDK and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="d1020-128">然后，打开终端并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="d1020-128">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf dotnet-sdk-3.1.100-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="d1020-129">前面的 `export` 命令只会使 .NET Core CLI 命令对运行它的终端会话可用。</span><span class="sxs-lookup"><span data-stu-id="d1020-129">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="d1020-130">你可以编辑 shell 配置文件，永久地添加这些命令。</span><span class="sxs-lookup"><span data-stu-id="d1020-130">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="d1020-131">Linux 提供了许多不同的 shell，每个都有不同的配置文件。</span><span class="sxs-lookup"><span data-stu-id="d1020-131">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="d1020-132">例如：</span><span class="sxs-lookup"><span data-stu-id="d1020-132">For example:</span></span>
>
> - <span data-ttu-id="d1020-133">**Bash Shell**：~/.bash_profile  、~/.bashrc </span><span class="sxs-lookup"><span data-stu-id="d1020-133">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="d1020-134">**Korn Shell**：~/.kshrc  或 .profile </span><span class="sxs-lookup"><span data-stu-id="d1020-134">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="d1020-135">**Z Shell**：~/.zshrc  或 .zprofile </span><span class="sxs-lookup"><span data-stu-id="d1020-135">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="d1020-136">为 shell 编辑相应的源文件，并将 `:$HOME/dotnet` 添加到现有 `PATH` 语句的末尾。</span><span class="sxs-lookup"><span data-stu-id="d1020-136">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="d1020-137">如果不包含 `PATH` 语句，则使用 `export PATH=$PATH:$HOME/dotnet` 添加新行。</span><span class="sxs-lookup"><span data-stu-id="d1020-137">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="d1020-138">另外，将 `export DOTNET_ROOT=$HOME/dotnet` 添加至文件的末尾。</span><span class="sxs-lookup"><span data-stu-id="d1020-138">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a><span data-ttu-id="d1020-139">使用 Visual Studio 安装</span><span class="sxs-lookup"><span data-stu-id="d1020-139">Install with Visual Studio</span></span>

<span data-ttu-id="d1020-140">如果你要使用 Visual Studio 开发 .NET Core 应用，请参阅下表，了解不同目标 .NET Core SDK 版本所需的 Visual Studio 最低版本。</span><span class="sxs-lookup"><span data-stu-id="d1020-140">If you're using Visual Studio to develop .NET Core apps, the following table describes the minimum required version of Visual Studio based on the target .NET Core SDK version.</span></span>

| <span data-ttu-id="d1020-141">.NET Core SDK 版本</span><span class="sxs-lookup"><span data-stu-id="d1020-141">.NET Core SDK version</span></span> | <span data-ttu-id="d1020-142">Visual Studio 版本</span><span class="sxs-lookup"><span data-stu-id="d1020-142">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="d1020-143">3.1</span><span class="sxs-lookup"><span data-stu-id="d1020-143">3.1</span></span>                   | <span data-ttu-id="d1020-144">Visual Studio 2019 版本 16.4 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d1020-144">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="d1020-145">3.0</span><span class="sxs-lookup"><span data-stu-id="d1020-145">3.0</span></span>                   | <span data-ttu-id="d1020-146">Visual Studio 2019 版本 16.3 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d1020-146">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="d1020-147">2.2</span><span class="sxs-lookup"><span data-stu-id="d1020-147">2.2</span></span>                   | <span data-ttu-id="d1020-148">Visual Studio 2017 版本 15.9 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d1020-148">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="d1020-149">2.1</span><span class="sxs-lookup"><span data-stu-id="d1020-149">2.1</span></span>                   | <span data-ttu-id="d1020-150">Visual Studio 2017 版本 15.7 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d1020-150">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="d1020-151">如果你已安装 Visual Studio，则可以使用以下步骤检查你的版本。</span><span class="sxs-lookup"><span data-stu-id="d1020-151">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="d1020-152">打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="d1020-152">Open Visual Studio.</span></span>
01. <span data-ttu-id="d1020-153">选择“帮助”   > “Microsoft Visual Studio”  。</span><span class="sxs-lookup"><span data-stu-id="d1020-153">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="d1020-154">从“关于”  对话框中读取版本号。</span><span class="sxs-lookup"><span data-stu-id="d1020-154">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="d1020-155">Visual Studio 可安装最新的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="d1020-155">Visual Studio can install the latest .NET Core SDK and runtime.</span></span>

- <span data-ttu-id="d1020-156">[下载 Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)。</span><span class="sxs-lookup"><span data-stu-id="d1020-156">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="d1020-157">选择工作负载</span><span class="sxs-lookup"><span data-stu-id="d1020-157">Select a workload</span></span>

<span data-ttu-id="d1020-158">安装或修改 Visual Studio 时，根据要生成的应用程序的类型，选择以下一个或多个工作负载：</span><span class="sxs-lookup"><span data-stu-id="d1020-158">When installing or modifying Visual Studio, select one or more of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="d1020-159">“其他工具集”部分中的“.NET Core 跨平台开发”工作负荷   。</span><span class="sxs-lookup"><span data-stu-id="d1020-159">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="d1020-160">“Web 和云”部分中的“ASP.NET 和 Web 开发”工作负荷   。</span><span class="sxs-lookup"><span data-stu-id="d1020-160">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="d1020-161">“Web 和云”部分中的“Azure 开发”工作负载   。</span><span class="sxs-lookup"><span data-stu-id="d1020-161">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="d1020-162">“桌面和移动”部分中的“NET 桌面开发”工作负载   。</span><span class="sxs-lookup"><span data-stu-id="d1020-162">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="d1020-163">[![具有 .NET Core 工作负载的 Windows Visual Studio 2019](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d1020-163">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="d1020-164">下载并手动安装</span><span class="sxs-lookup"><span data-stu-id="d1020-164">Download and manually install</span></span>

<span data-ttu-id="d1020-165">若要提取运行时并使 .NET Core CLI 命令可用于终端，请先[下载](#all-net-core-downloads) .NET Core 二进制版本。</span><span class="sxs-lookup"><span data-stu-id="d1020-165">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="d1020-166">然后，创建要安装到的目录，例如 `%USERPROFILE%\dotnet`。</span><span class="sxs-lookup"><span data-stu-id="d1020-166">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="d1020-167">最后，将下载的 zip 文件提取到该目录中。</span><span class="sxs-lookup"><span data-stu-id="d1020-167">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="d1020-168">默认情况下，.NET Core CLI 命令和应用不会使用通过这种方式安装的 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="d1020-168">By default, .NET Core CLI commands and apps will not use .NET Core installed in this way.</span></span> <span data-ttu-id="d1020-169">必须明确选择使用它。</span><span class="sxs-lookup"><span data-stu-id="d1020-169">You have to explicitly choose to use it.</span></span> <span data-ttu-id="d1020-170">为此，请更改用于启动应用程序的环境变量：</span><span class="sxs-lookup"><span data-stu-id="d1020-170">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="d1020-171">使用此方法可以将多个版本安装到不同的位置，然后通过使用指向安装位置的环境变量运行应用程序来明确选择应用程序应使用哪个安装位置。</span><span class="sxs-lookup"><span data-stu-id="d1020-171">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="d1020-172">即使已设置这些环境变量，在选择用于运行应用程序的最佳框架时，.NET Core 仍会考虑默认的全局安装位置。</span><span class="sxs-lookup"><span data-stu-id="d1020-172">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="d1020-173">默认位置通常为安装程序使用的 `C:\Program Files\dotnet`。</span><span class="sxs-lookup"><span data-stu-id="d1020-173">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="d1020-174">还可以通过设置此环境变量来指示运行时仅使用自定义安装位置：</span><span class="sxs-lookup"><span data-stu-id="d1020-174">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="d1020-175">使用 Visual Studio for Mac 安装</span><span class="sxs-lookup"><span data-stu-id="d1020-175">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="d1020-176">在选定“.NET Core”  工作负载时，使用 Visual Studio for Mac 安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="d1020-176">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="d1020-177">若要开始在 macOS 上进行 .NET Core 开发，请参阅[安装 Visual Studio 2019 for Mac](/visualstudio/mac/installation)。</span><span class="sxs-lookup"><span data-stu-id="d1020-177">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="d1020-178">对于最新的版本 .NET Core 3.1，则必须使用 Visual Studio for Mac 8.4 预览版。</span><span class="sxs-lookup"><span data-stu-id="d1020-178">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4 Preview.</span></span>

<span data-ttu-id="d1020-179">[![具有 .NET Core 工作负载功能的 macOS Visual Studio 2019 for Mac](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d1020-179">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

::: zone-end

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="d1020-180">随 Visual Studio Code 一起安装</span><span class="sxs-lookup"><span data-stu-id="d1020-180">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="d1020-181">Visual Studio Code 是一个功能强大的轻量级源代码编辑器，可在桌面上运行。</span><span class="sxs-lookup"><span data-stu-id="d1020-181">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="d1020-182">Visual Studio Code 适用于 Windows、macOS 和 Linux。</span><span class="sxs-lookup"><span data-stu-id="d1020-182">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="d1020-183">虽然 Visual Studio Code 不像 Visual Studio 一样附带自动的 .NET Core 安装程序，但添加 .NET Core 支持非常简单。</span><span class="sxs-lookup"><span data-stu-id="d1020-183">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="d1020-184">[下载并安装 Visual Studio Code](https://code.visualstudio.com/Download)。</span><span class="sxs-lookup"><span data-stu-id="d1020-184">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="d1020-185">[下载并安装 .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core)。</span><span class="sxs-lookup"><span data-stu-id="d1020-185">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="d1020-186">[从 Visual Studio Code 市场安装 C# 扩展](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)。</span><span class="sxs-lookup"><span data-stu-id="d1020-186">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span>

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="d1020-187">使用 PowerShell 自动化安装</span><span class="sxs-lookup"><span data-stu-id="d1020-187">Install with PowerShell automation</span></span>

<span data-ttu-id="d1020-188">[dotnet-install 脚本](../tools/dotnet-install-script.md)用于 SDK 的自动化和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="d1020-188">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="d1020-189">可从 [dotnet-install 脚本引用页](../tools/dotnet-install-script.md)下载该脚本。</span><span class="sxs-lookup"><span data-stu-id="d1020-189">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="d1020-190">此脚本默认安装最新的[长期支持 (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 版本，即 .NET Core 3.1。</span><span class="sxs-lookup"><span data-stu-id="d1020-190">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="d1020-191">若要安装最新版本的 .NET Core，请使用以下开关运行脚本。</span><span class="sxs-lookup"><span data-stu-id="d1020-191">To install the current release of .NET Core, run the script with the following switch.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="d1020-192">使用 Bash 自动化安装</span><span class="sxs-lookup"><span data-stu-id="d1020-192">Install with bash automation</span></span>

<span data-ttu-id="d1020-193">[dotnet-install 脚本](../tools/dotnet-install-script.md)用于 SDK 的自动化和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="d1020-193">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="d1020-194">可从 [dotnet-install 脚本引用页](../tools/dotnet-install-script.md)下载该脚本。</span><span class="sxs-lookup"><span data-stu-id="d1020-194">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="d1020-195">此脚本默认安装最新的[长期支持 (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 版本，即 .NET Core 3.1。</span><span class="sxs-lookup"><span data-stu-id="d1020-195">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="d1020-196">若要安装最新版本的 .NET Core，请使用以下开关运行脚本。</span><span class="sxs-lookup"><span data-stu-id="d1020-196">To install the current release of .NET Core, run the script with the following switch.</span></span>

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="d1020-197">所有 .NET Core 下载项</span><span class="sxs-lookup"><span data-stu-id="d1020-197">All .NET Core downloads</span></span>

<span data-ttu-id="d1020-198">可直接通过以下链接之一下载和安装 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="d1020-198">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="d1020-199">.NET Core 3.1 下载</span><span class="sxs-lookup"><span data-stu-id="d1020-199">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="d1020-200">.NET Core 3.0 下载</span><span class="sxs-lookup"><span data-stu-id="d1020-200">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="d1020-201">.NET Core 2.2 下载</span><span class="sxs-lookup"><span data-stu-id="d1020-201">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="d1020-202">.NET Core 2.1 下载</span><span class="sxs-lookup"><span data-stu-id="d1020-202">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="d1020-203">Docker</span><span class="sxs-lookup"><span data-stu-id="d1020-203">Docker</span></span>

<span data-ttu-id="d1020-204">容器提供了一种将应用程序与主机系统的其余部分隔离的轻量级方法。</span><span class="sxs-lookup"><span data-stu-id="d1020-204">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="d1020-205">同一计算机上的容器只共享内核，并使用为应用程序提供的资源。</span><span class="sxs-lookup"><span data-stu-id="d1020-205">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="d1020-206">.NET Core 可在 Docker 容器中运行。</span><span class="sxs-lookup"><span data-stu-id="d1020-206">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="d1020-207">官方 .NET Core Docker 映像发布到 Microsoft 容器注册表 (MCR)，用户可以在 [Microsoft.NET Core Docker 中心存储库](https://hub.docker.com/_/microsoft-dotnet-core/)中找到这些映像。</span><span class="sxs-lookup"><span data-stu-id="d1020-207">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="d1020-208">每个存储库包含 .NET（SDK 或运行时）和可以使用的操作系统的不同组合的映像。</span><span class="sxs-lookup"><span data-stu-id="d1020-208">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="d1020-209">Microsoft 提供适合特定场景的映像。</span><span class="sxs-lookup"><span data-stu-id="d1020-209">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="d1020-210">例如，[ASP.NET Core 存储库](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)提供针对在生产环境中运行 ASP.NET Core 应用生成的映像。</span><span class="sxs-lookup"><span data-stu-id="d1020-210">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="d1020-211">有关在 Docker 容器中使用 .NET Core 的详细信息，请参阅 [.NET 和 Docker 简介](../docker/introduction.md)和[示例](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)。</span><span class="sxs-lookup"><span data-stu-id="d1020-211">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d1020-212">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d1020-212">Next steps</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="d1020-213">[教程：Hello World 教程](../tutorials/with-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="d1020-213">[Tutorial: Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="d1020-214">[教程：使用 Visual Studio Code 创建一个新应用](../tutorials/with-visual-studio-code.md)。</span><span class="sxs-lookup"><span data-stu-id="d1020-214">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="d1020-215">[教程：使 .NET Core 应用容器化](../docker/build-container.md)。</span><span class="sxs-lookup"><span data-stu-id="d1020-215">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="d1020-216">[处理 macOS Catalina 公证](macos-notarization-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="d1020-216">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="d1020-217">[教程：开始使用 macOS](../tutorials/using-on-mac-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="d1020-217">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="d1020-218">[教程：使用 Visual Studio Code 创建一个新应用](../tutorials/with-visual-studio-code.md)。</span><span class="sxs-lookup"><span data-stu-id="d1020-218">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="d1020-219">[教程：使 .NET Core 应用容器化](../docker/build-container.md)。</span><span class="sxs-lookup"><span data-stu-id="d1020-219">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="d1020-220">[教程：使用 Visual Studio Code 创建一个新应用](../tutorials/with-visual-studio-code.md)。</span><span class="sxs-lookup"><span data-stu-id="d1020-220">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="d1020-221">[教程：使 .NET Core 应用容器化](../docker/build-container.md)。</span><span class="sxs-lookup"><span data-stu-id="d1020-221">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end
