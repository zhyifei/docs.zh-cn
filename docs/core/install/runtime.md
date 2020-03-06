---
title: 在 Windows、Linux 和 macOS 上安装 .NET Core 运行时 - .NET Core
description: 了解如何在 Windows、Linux 和 macOS 上安装 .NET Core。 发现运行 .NET Core 应用所需的依赖项。
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: a41bbdf5419585f06773583dbe82ab0d84ebaa4c
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157631"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="88c06-104">安装 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="88c06-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="88c06-105">本文介绍如何下载和安装 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="88c06-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="88c06-106">.NET Core 运行时用于运行使用 .NET Core 创建的应用。</span><span class="sxs-lookup"><span data-stu-id="88c06-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="88c06-107">使用安装程序安装</span><span class="sxs-lookup"><span data-stu-id="88c06-107">Install with an installer</span></span>

<span data-ttu-id="88c06-108">Windows 具有独立的安装程序，可用于安装 .NET Core 3.1 运行时：</span><span class="sxs-lookup"><span data-stu-id="88c06-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="88c06-109">x64（64 位）CPU</span><span class="sxs-lookup"><span data-stu-id="88c06-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="88c06-110">x86（32 位）CPU</span><span class="sxs-lookup"><span data-stu-id="88c06-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="88c06-111">使用安装程序安装</span><span class="sxs-lookup"><span data-stu-id="88c06-111">Install with an installer</span></span>

<span data-ttu-id="88c06-112">macOS 具有独立的安装程序，可用于安装 .NET Core 3.1 运行时：</span><span class="sxs-lookup"><span data-stu-id="88c06-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="88c06-113">x64（64 位）CPU</span><span class="sxs-lookup"><span data-stu-id="88c06-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="88c06-114">下载并手动安装</span><span class="sxs-lookup"><span data-stu-id="88c06-114">Download and manually install</span></span>

<span data-ttu-id="88c06-115">除了使用适用于 .NET Core 的 macOS 安装程序，还可以下载并手动安装运行时。</span><span class="sxs-lookup"><span data-stu-id="88c06-115">As an alternative to the macOS installers for .NET Core, you can download and manually install the runtime.</span></span>

<span data-ttu-id="88c06-116">若要安装运行时并使 .NET Core CLI 命令可用于终端，请先[下载](#all-net-core-downloads) .NET Core 二进制版本。</span><span class="sxs-lookup"><span data-stu-id="88c06-116">To install the runtime and enable the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="88c06-117">然后，打开终端并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="88c06-117">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="88c06-118">假定将运行时下载到 `~/Downloads/dotnet-runtime.pkg` 文件中。</span><span class="sxs-lookup"><span data-stu-id="88c06-118">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-runtime.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-runtime.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="88c06-119">使用包管理器安装</span><span class="sxs-lookup"><span data-stu-id="88c06-119">Install with a package manager</span></span>

<span data-ttu-id="88c06-120">可使用许多常见的 Linux 包管理器安装 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="88c06-120">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="88c06-121">有关详细信息，请参阅 [Linux 包管理器 - 安装 .NET Core](linux-package-managers.md)。</span><span class="sxs-lookup"><span data-stu-id="88c06-121">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="88c06-122">仅在 x64 体系结构上支持使用包管理器安装。</span><span class="sxs-lookup"><span data-stu-id="88c06-122">Installing it with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="88c06-123">如果要使用其他体系结构（如 ARM）安装 .NET Core 运行时，请遵循[下载并手动安装](#download-and-manually-install)部分中的说明。</span><span class="sxs-lookup"><span data-stu-id="88c06-123">If you're installing the .NET Core Runtime with a different architecture, such as ARM, follow the instructions on the [Download and manually install](#download-and-manually-install) section.</span></span> <span data-ttu-id="88c06-124">有关支持的体系结构的详细信息，请参阅 [.NET Core 依赖项和要求](dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="88c06-124">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="88c06-125">下载并手动安装</span><span class="sxs-lookup"><span data-stu-id="88c06-125">Download and manually install</span></span>

<span data-ttu-id="88c06-126">若要提取运行时并使 .NET Core CLI 命令可用于终端，请先[下载](#all-net-core-downloads) .NET Core 二进制版本。</span><span class="sxs-lookup"><span data-stu-id="88c06-126">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="88c06-127">然后，打开终端并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="88c06-127">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="88c06-128">前面的 `export` 命令只会使 .NET Core CLI 命令对运行它的终端会话可用。</span><span class="sxs-lookup"><span data-stu-id="88c06-128">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="88c06-129">你可以编辑 shell 配置文件，永久地添加这些命令。</span><span class="sxs-lookup"><span data-stu-id="88c06-129">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="88c06-130">Linux 提供了许多不同的 shell，每个都有不同的配置文件。</span><span class="sxs-lookup"><span data-stu-id="88c06-130">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="88c06-131">例如：</span><span class="sxs-lookup"><span data-stu-id="88c06-131">For example:</span></span>
>
> - <span data-ttu-id="88c06-132">**Bash Shell**：~/.bash_profile  、~/.bashrc </span><span class="sxs-lookup"><span data-stu-id="88c06-132">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="88c06-133">**Korn Shell**：~/.kshrc  或 .profile </span><span class="sxs-lookup"><span data-stu-id="88c06-133">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="88c06-134">**Z Shell**：~/.zshrc  或 .zprofile </span><span class="sxs-lookup"><span data-stu-id="88c06-134">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="88c06-135">为 shell 编辑相应的源文件，并将 `:$HOME/dotnet` 添加到现有 `PATH` 语句的末尾。</span><span class="sxs-lookup"><span data-stu-id="88c06-135">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="88c06-136">如果不包含 `PATH` 语句，则使用 `export PATH=$PATH:$HOME/dotnet` 添加新行。</span><span class="sxs-lookup"><span data-stu-id="88c06-136">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="88c06-137">另外，将 `export DOTNET_ROOT=$HOME/dotnet` 添加至文件的末尾。</span><span class="sxs-lookup"><span data-stu-id="88c06-137">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="88c06-138">使用此方法可以将不同的版本安装到不同的位置，并明确选择应用程序要使用的对应版本。</span><span class="sxs-lookup"><span data-stu-id="88c06-138">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="88c06-139">使用 PowerShell 自动化安装</span><span class="sxs-lookup"><span data-stu-id="88c06-139">Install with PowerShell automation</span></span>

<span data-ttu-id="88c06-140">[dotnet-install 脚本](../tools/dotnet-install-script.md)用于运行时的自动化和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="88c06-140">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="88c06-141">可从 [dotnet-install 脚本引用页](../tools/dotnet-install-script.md)下载该脚本。</span><span class="sxs-lookup"><span data-stu-id="88c06-141">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="88c06-142">此脚本默认安装最新的[长期支持 (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 版本，即 .NET Core 3.1。</span><span class="sxs-lookup"><span data-stu-id="88c06-142">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="88c06-143">可通过指定 `Channel` 开关以选择特定版本。</span><span class="sxs-lookup"><span data-stu-id="88c06-143">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="88c06-144">包括 `Runtime` 开关以安装运行时。</span><span class="sxs-lookup"><span data-stu-id="88c06-144">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="88c06-145">否则，该脚本安装 [SDK](sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="88c06-145">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="88c06-146">以上命令安装 ASP.NET Core 运行时，用于实现最大的兼容性。</span><span class="sxs-lookup"><span data-stu-id="88c06-146">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="88c06-147">ASP.NET Core 运行时还包括标准 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="88c06-147">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="88c06-148">下载并手动安装</span><span class="sxs-lookup"><span data-stu-id="88c06-148">Download and manually install</span></span>

<span data-ttu-id="88c06-149">若要提取运行时并使 .NET Core CLI 命令可用于终端，请先[下载](#all-net-core-downloads) .NET Core 二进制版本。</span><span class="sxs-lookup"><span data-stu-id="88c06-149">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="88c06-150">然后，创建要安装到的目录，例如 `%USERPROFILE%\dotnet`。</span><span class="sxs-lookup"><span data-stu-id="88c06-150">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="88c06-151">最后，将下载的 zip 文件提取到该目录中。</span><span class="sxs-lookup"><span data-stu-id="88c06-151">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="88c06-152">默认情况下，.NET Core CLI 命令和应用不会使用通过这种方式安装的 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="88c06-152">By default, .NET Core CLI commands and apps will not use .NET Core installed in this way.</span></span> <span data-ttu-id="88c06-153">必须明确选择使用它。</span><span class="sxs-lookup"><span data-stu-id="88c06-153">You have to explicitly choose to use it.</span></span> <span data-ttu-id="88c06-154">为此，请更改用于启动应用程序的环境变量：</span><span class="sxs-lookup"><span data-stu-id="88c06-154">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="88c06-155">使用此方法可以将多个版本安装到不同的位置，然后通过使用指向安装位置的环境变量运行应用程序来明确选择应用程序应使用哪个安装位置。</span><span class="sxs-lookup"><span data-stu-id="88c06-155">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="88c06-156">即使已设置这些环境变量，在选择用于运行应用程序的最佳框架时，.NET Core 仍会考虑默认的全局安装位置。</span><span class="sxs-lookup"><span data-stu-id="88c06-156">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="88c06-157">默认位置通常为安装程序使用的 `C:\Program Files\dotnet`。</span><span class="sxs-lookup"><span data-stu-id="88c06-157">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="88c06-158">还可以通过设置此环境变量来指示运行时仅使用自定义安装位置：</span><span class="sxs-lookup"><span data-stu-id="88c06-158">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="88c06-159">使用 Bash 自动化安装</span><span class="sxs-lookup"><span data-stu-id="88c06-159">Install with bash automation</span></span>

<span data-ttu-id="88c06-160">[dotnet-install 脚本](../tools/dotnet-install-script.md)用于运行时的自动化和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="88c06-160">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="88c06-161">可从 [dotnet-install 脚本引用页](../tools/dotnet-install-script.md)下载该脚本。</span><span class="sxs-lookup"><span data-stu-id="88c06-161">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="88c06-162">此脚本默认安装最新的[长期支持 (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 版本，即 .NET Core 3.1。</span><span class="sxs-lookup"><span data-stu-id="88c06-162">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="88c06-163">可通过指定 `current` 开关以选择特定版本。</span><span class="sxs-lookup"><span data-stu-id="88c06-163">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="88c06-164">包括 `runtime` 开关以安装运行时。</span><span class="sxs-lookup"><span data-stu-id="88c06-164">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="88c06-165">否则，该脚本安装 [SDK](sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="88c06-165">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="88c06-166">以上命令安装 ASP.NET Core 运行时，用于实现最大的兼容性。</span><span class="sxs-lookup"><span data-stu-id="88c06-166">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="88c06-167">ASP.NET Core 运行时还包括标准 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="88c06-167">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="88c06-168">所有 .NET Core 下载项</span><span class="sxs-lookup"><span data-stu-id="88c06-168">All .NET Core downloads</span></span>

<span data-ttu-id="88c06-169">可直接通过以下链接之一下载和安装 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="88c06-169">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="88c06-170">.NET Core 3.1 下载</span><span class="sxs-lookup"><span data-stu-id="88c06-170">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="88c06-171">.NET Core 3.0 下载</span><span class="sxs-lookup"><span data-stu-id="88c06-171">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="88c06-172">.NET Core 2.2 下载</span><span class="sxs-lookup"><span data-stu-id="88c06-172">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="88c06-173">.NET Core 2.1 下载</span><span class="sxs-lookup"><span data-stu-id="88c06-173">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="88c06-174">Docker</span><span class="sxs-lookup"><span data-stu-id="88c06-174">Docker</span></span>

<span data-ttu-id="88c06-175">容器提供了一种将应用程序与主机系统的其余部分隔离的轻量级方法。</span><span class="sxs-lookup"><span data-stu-id="88c06-175">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="88c06-176">同一计算机上的容器只共享内核，并使用为应用程序提供的资源。</span><span class="sxs-lookup"><span data-stu-id="88c06-176">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="88c06-177">.NET Core 可在 Docker 容器中运行。</span><span class="sxs-lookup"><span data-stu-id="88c06-177">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="88c06-178">官方 .NET Core Docker 映像发布到 Microsoft 容器注册表 (MCR)，用户可以在 [Microsoft.NET Core Docker 中心存储库](https://hub.docker.com/_/microsoft-dotnet-core/)中找到这些映像。</span><span class="sxs-lookup"><span data-stu-id="88c06-178">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="88c06-179">每个存储库包含 .NET（SDK 或运行时）和可以使用的操作系统的不同组合的映像。</span><span class="sxs-lookup"><span data-stu-id="88c06-179">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="88c06-180">Microsoft 提供适合特定场景的映像。</span><span class="sxs-lookup"><span data-stu-id="88c06-180">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="88c06-181">例如，[ASP.NET Core 存储库](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)提供针对在生产环境中运行 ASP.NET Core 应用生成的映像。</span><span class="sxs-lookup"><span data-stu-id="88c06-181">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="88c06-182">有关在 Docker 容器中使用 .NET Core 的详细信息，请参阅 [.NET 和 Docker 简介](../docker/introduction.md)和[示例](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)。</span><span class="sxs-lookup"><span data-stu-id="88c06-182">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="88c06-183">后续步骤</span><span class="sxs-lookup"><span data-stu-id="88c06-183">Next steps</span></span>

- <span data-ttu-id="88c06-184">[如何检查是否已安装 .NET Core](how-to-detect-installed-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="88c06-184">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
