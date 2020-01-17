---
title: 在 Windows、Linux 和 macOS 上安装 .NET Core 运行时 - .NET Core
description: 了解如何在 Windows、Linux 和 macOS 上安装 .NET Core。 发现运行 .NET Core 应用所需的依赖项。
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: d36909e06bd9a3de0940c4c1b2b9eacbf9cafe7f
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740594"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="c1d19-104">安装 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="c1d19-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="c1d19-105">本文介绍如何下载和安装 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="c1d19-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="c1d19-106">.NET Core 运行时用于运行使用 .NET Core 创建的应用。</span><span class="sxs-lookup"><span data-stu-id="c1d19-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="c1d19-107">使用安装程序安装</span><span class="sxs-lookup"><span data-stu-id="c1d19-107">Install with an installer</span></span>

<span data-ttu-id="c1d19-108">Windows 具有独立的安装程序，可用于安装 .NET Core 3.1 运行时：</span><span class="sxs-lookup"><span data-stu-id="c1d19-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="c1d19-109">x64（64 位）CPU</span><span class="sxs-lookup"><span data-stu-id="c1d19-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="c1d19-110">x86（32 位）CPU</span><span class="sxs-lookup"><span data-stu-id="c1d19-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="c1d19-111">使用安装程序安装</span><span class="sxs-lookup"><span data-stu-id="c1d19-111">Install with an installer</span></span>

<span data-ttu-id="c1d19-112">macOS 具有独立的安装程序，可用于安装 .NET Core 3.1 运行时：</span><span class="sxs-lookup"><span data-stu-id="c1d19-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="c1d19-113">x64（64 位）CPU</span><span class="sxs-lookup"><span data-stu-id="c1d19-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="c1d19-114">使用包管理器安装</span><span class="sxs-lookup"><span data-stu-id="c1d19-114">Install with a package manager</span></span>

<span data-ttu-id="c1d19-115">可使用许多常见的 Linux 包管理器安装 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="c1d19-115">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="c1d19-116">有关详细信息，请参阅 [Linux 包管理器 - 安装 .NET Core](linux-package-managers.md)。</span><span class="sxs-lookup"><span data-stu-id="c1d19-116">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="c1d19-117">仅在 x64 体系结构上支持使用包管理器安装。</span><span class="sxs-lookup"><span data-stu-id="c1d19-117">Installing it with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="c1d19-118">如果要使用其他体系结构（如 ARM）安装 .NET Core 运行时，请遵循[下载并手动安装](#download-and-manually-install)部分中的说明。</span><span class="sxs-lookup"><span data-stu-id="c1d19-118">If you're installing the .NET Core Runtime with a different architecture, such as ARM, follow the instructions on the [Download and manually install](#download-and-manually-install) section.</span></span> <span data-ttu-id="c1d19-119">有关支持的体系结构的详细信息，请参阅 [.NET Core 依赖项和要求](dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="c1d19-119">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="c1d19-120">下载并手动安装</span><span class="sxs-lookup"><span data-stu-id="c1d19-120">Download and manually install</span></span>

<span data-ttu-id="c1d19-121">若要提取运行时并使 .NET Core CLI 命令可用于终端，请先[下载](#all-net-core-downloads) .NET Core 二进制版本。</span><span class="sxs-lookup"><span data-stu-id="c1d19-121">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="c1d19-122">然后，打开终端并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="c1d19-122">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="c1d19-123">前面的 `export` 命令只会使 .NET Core CLI 命令对运行它的终端会话可用。</span><span class="sxs-lookup"><span data-stu-id="c1d19-123">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="c1d19-124">你可以编辑 shell 配置文件，永久地添加这些命令。</span><span class="sxs-lookup"><span data-stu-id="c1d19-124">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="c1d19-125">Linux 提供了许多不同的 shell，每个都有不同的配置文件。</span><span class="sxs-lookup"><span data-stu-id="c1d19-125">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="c1d19-126">例如：</span><span class="sxs-lookup"><span data-stu-id="c1d19-126">For example:</span></span>
>
> - <span data-ttu-id="c1d19-127">**Bash Shell**：~/.bash_profile、~/.bashrc</span><span class="sxs-lookup"><span data-stu-id="c1d19-127">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="c1d19-128">**Korn Shell**：~/.kshrc 或 .profile</span><span class="sxs-lookup"><span data-stu-id="c1d19-128">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="c1d19-129">**Z Shell**：~/.zshrc 或 .zprofile</span><span class="sxs-lookup"><span data-stu-id="c1d19-129">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
> 
> <span data-ttu-id="c1d19-130">为 shell 编辑相应的源文件，并将 `:$HOME/dotnet` 添加到现有 `PATH` 语句的末尾。</span><span class="sxs-lookup"><span data-stu-id="c1d19-130">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="c1d19-131">如果不包含 `PATH` 语句，则使用 `export PATH=$PATH:$HOME/dotnet` 添加新行。</span><span class="sxs-lookup"><span data-stu-id="c1d19-131">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="c1d19-132">另外，将 `export DOTNET_ROOT=$HOME/dotnet` 添加至文件的末尾。</span><span class="sxs-lookup"><span data-stu-id="c1d19-132">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="c1d19-133">使用 PowerShell 自动化安装</span><span class="sxs-lookup"><span data-stu-id="c1d19-133">Install with PowerShell automation</span></span>

<span data-ttu-id="c1d19-134">[dotnet-install 脚本](../tools/dotnet-install-script.md)用于运行时的自动化和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="c1d19-134">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="c1d19-135">可从 [dotnet-install 脚本引用页](../tools/dotnet-install-script.md)下载该脚本。</span><span class="sxs-lookup"><span data-stu-id="c1d19-135">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="c1d19-136">此脚本默认安装最新的[长期支持 (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 版本，即 .NET Core 3.1。</span><span class="sxs-lookup"><span data-stu-id="c1d19-136">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="c1d19-137">可通过指定 `Channel` 开关以选择特定版本。</span><span class="sxs-lookup"><span data-stu-id="c1d19-137">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="c1d19-138">包括 `Runtime` 开关以安装运行时。</span><span class="sxs-lookup"><span data-stu-id="c1d19-138">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="c1d19-139">否则，该脚本安装 [SDK](sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="c1d19-139">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="c1d19-140">以上命令安装 ASP.NET Core 运行时，用于实现最大的兼容性。</span><span class="sxs-lookup"><span data-stu-id="c1d19-140">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="c1d19-141">ASP.NET Core 运行时还包括标准 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="c1d19-141">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="c1d19-142">使用 Bash 自动化安装</span><span class="sxs-lookup"><span data-stu-id="c1d19-142">Install with bash automation</span></span>

<span data-ttu-id="c1d19-143">[dotnet-install 脚本](../tools/dotnet-install-script.md)用于运行时的自动化和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="c1d19-143">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="c1d19-144">可从 [dotnet-install 脚本引用页](../tools/dotnet-install-script.md)下载该脚本。</span><span class="sxs-lookup"><span data-stu-id="c1d19-144">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="c1d19-145">此脚本默认安装最新的[长期支持 (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 版本，即 .NET Core 3.1。</span><span class="sxs-lookup"><span data-stu-id="c1d19-145">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="c1d19-146">可通过指定 `current` 开关以选择特定版本。</span><span class="sxs-lookup"><span data-stu-id="c1d19-146">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="c1d19-147">包括 `runtime` 开关以安装运行时。</span><span class="sxs-lookup"><span data-stu-id="c1d19-147">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="c1d19-148">否则，该脚本安装 [SDK](sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="c1d19-148">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="c1d19-149">以上命令安装 ASP.NET Core 运行时，用于实现最大的兼容性。</span><span class="sxs-lookup"><span data-stu-id="c1d19-149">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="c1d19-150">ASP.NET Core 运行时还包括标准 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="c1d19-150">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="c1d19-151">所有 .NET Core 下载项</span><span class="sxs-lookup"><span data-stu-id="c1d19-151">All .NET Core downloads</span></span>

<span data-ttu-id="c1d19-152">可直接通过以下链接之一下载和安装 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="c1d19-152">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="c1d19-153">.NET Core 3.1 下载</span><span class="sxs-lookup"><span data-stu-id="c1d19-153">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="c1d19-154">.NET Core 3.0 下载</span><span class="sxs-lookup"><span data-stu-id="c1d19-154">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="c1d19-155">.NET Core 2.2 下载</span><span class="sxs-lookup"><span data-stu-id="c1d19-155">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="c1d19-156">.NET Core 2.1 下载</span><span class="sxs-lookup"><span data-stu-id="c1d19-156">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="c1d19-157">Docker</span><span class="sxs-lookup"><span data-stu-id="c1d19-157">Docker</span></span>

<span data-ttu-id="c1d19-158">容器提供了一种将应用程序与主机系统的其余部分隔离的轻量级方法。</span><span class="sxs-lookup"><span data-stu-id="c1d19-158">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="c1d19-159">同一计算机上的容器只共享内核，并使用为应用程序提供的资源。</span><span class="sxs-lookup"><span data-stu-id="c1d19-159">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="c1d19-160">.NET Core 可在 Docker 容器中运行。</span><span class="sxs-lookup"><span data-stu-id="c1d19-160">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="c1d19-161">官方 .NET Core Docker 映像发布到 Microsoft 容器注册表 (MCR)，用户可以在 [Microsoft.NET Core Docker 中心存储库](https://hub.docker.com/_/microsoft-dotnet-core/)中找到这些映像。</span><span class="sxs-lookup"><span data-stu-id="c1d19-161">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="c1d19-162">每个存储库包含 .NET（SDK 或运行时）和可以使用的操作系统的不同组合的映像。</span><span class="sxs-lookup"><span data-stu-id="c1d19-162">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="c1d19-163">Microsoft 提供适合特定场景的映像。</span><span class="sxs-lookup"><span data-stu-id="c1d19-163">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="c1d19-164">例如，[ASP.NET Core 存储库](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)提供针对在生产环境中运行 ASP.NET Core 应用生成的映像。</span><span class="sxs-lookup"><span data-stu-id="c1d19-164">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="c1d19-165">有关在 Docker 容器中使用 .NET Core 的详细信息，请参阅 [.NET 和 Docker 简介](../docker/introduction.md)和[示例](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)。</span><span class="sxs-lookup"><span data-stu-id="c1d19-165">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c1d19-166">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c1d19-166">Next steps</span></span>

- <span data-ttu-id="c1d19-167">[如何检查是否已安装 .NET Core](how-to-detect-installed-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="c1d19-167">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
