---
title: 在 Windows、Linux 和 macOS 上安装 .NET Core 运行时 - .NET Core
description: 了解如何在 Windows、Linux 和 macOS 上安装 .NET Core。 发现运行 .NET Core 应用所需的依赖项。
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 8f4a895ad66dea3063a32f785e4c521196266978
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998887"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="a599d-104">安装 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="a599d-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="a599d-105">本文介绍如何下载和安装 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="a599d-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="a599d-106">.NET Core 运行时用于运行使用 .NET Core 创建的应用。</span><span class="sxs-lookup"><span data-stu-id="a599d-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="a599d-107">使用安装程序安装</span><span class="sxs-lookup"><span data-stu-id="a599d-107">Install with an installer</span></span>

<span data-ttu-id="a599d-108">Windows 具有独立的安装程序，可用于安装 .NET Core 3.1 运行时：</span><span class="sxs-lookup"><span data-stu-id="a599d-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="a599d-109">x64（64 位）CPU</span><span class="sxs-lookup"><span data-stu-id="a599d-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="a599d-110">x86（32 位）CPU</span><span class="sxs-lookup"><span data-stu-id="a599d-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="a599d-111">使用安装程序安装</span><span class="sxs-lookup"><span data-stu-id="a599d-111">Install with an installer</span></span>

<span data-ttu-id="a599d-112">macOS 具有独立的安装程序，可用于安装 .NET Core 3.1 运行时：</span><span class="sxs-lookup"><span data-stu-id="a599d-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="a599d-113">x64（64 位）CPU</span><span class="sxs-lookup"><span data-stu-id="a599d-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="a599d-114">使用包管理器安装</span><span class="sxs-lookup"><span data-stu-id="a599d-114">Install with a package manager</span></span>

<span data-ttu-id="a599d-115">可使用许多常见的 Linux 包管理器安装 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="a599d-115">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="a599d-116">有关详细信息，请参阅 [Linux 包管理器 - 安装 .NET Core](linux-package-manager-rhel7.md)。</span><span class="sxs-lookup"><span data-stu-id="a599d-116">For more information, see [Linux Package Manager - Install .NET Core](linux-package-manager-rhel7.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="a599d-117">使用 PowerShell 自动化安装</span><span class="sxs-lookup"><span data-stu-id="a599d-117">Install with PowerShell automation</span></span>

<span data-ttu-id="a599d-118">[dotnet-install 脚本](../tools/dotnet-install-script.md)用于运行时的自动化和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="a599d-118">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="a599d-119">可从 [dotnet-install 脚本引用页](../tools/dotnet-install-script.md)下载该脚本。</span><span class="sxs-lookup"><span data-stu-id="a599d-119">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="a599d-120">此脚本默认安装最新的[长期支持 (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 版本，即 .NET Core 3.1。</span><span class="sxs-lookup"><span data-stu-id="a599d-120">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="a599d-121">可通过指定 `Channel` 开关以选择特定版本。</span><span class="sxs-lookup"><span data-stu-id="a599d-121">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="a599d-122">包括 `Runtime` 开关以安装运行时。</span><span class="sxs-lookup"><span data-stu-id="a599d-122">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="a599d-123">否则，该脚本安装 [SDK](sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="a599d-123">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="a599d-124">以上命令安装 ASP.NET Core 运行时，用于实现最大的兼容性。</span><span class="sxs-lookup"><span data-stu-id="a599d-124">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="a599d-125">ASP.NET Core 运行时还包括标准 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="a599d-125">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="a599d-126">使用 Bash 自动化安装</span><span class="sxs-lookup"><span data-stu-id="a599d-126">Install with bash automation</span></span>

<span data-ttu-id="a599d-127">[dotnet-install 脚本](../tools/dotnet-install-script.md)用于运行时的自动化和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="a599d-127">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="a599d-128">可从 [dotnet-install 脚本引用页](../tools/dotnet-install-script.md)下载该脚本。</span><span class="sxs-lookup"><span data-stu-id="a599d-128">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="a599d-129">此脚本默认安装最新的[长期支持 (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 版本，即 .NET Core 3.1。</span><span class="sxs-lookup"><span data-stu-id="a599d-129">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="a599d-130">可通过指定 `current` 开关以选择特定版本。</span><span class="sxs-lookup"><span data-stu-id="a599d-130">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="a599d-131">包括 `runtime` 开关以安装运行时。</span><span class="sxs-lookup"><span data-stu-id="a599d-131">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="a599d-132">否则，该脚本安装 [SDK](sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="a599d-132">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --current 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="a599d-133">以上命令安装 ASP.NET Core 运行时，用于实现最大的兼容性。</span><span class="sxs-lookup"><span data-stu-id="a599d-133">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="a599d-134">ASP.NET Core 运行时还包括标准 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="a599d-134">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="a599d-135">所有 .NET Core 下载项</span><span class="sxs-lookup"><span data-stu-id="a599d-135">All .NET Core downloads</span></span>

<span data-ttu-id="a599d-136">可直接通过以下链接之一下载和安装 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="a599d-136">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="a599d-137">.NET Core 3.1 下载</span><span class="sxs-lookup"><span data-stu-id="a599d-137">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="a599d-138">.NET Core 3.0 下载</span><span class="sxs-lookup"><span data-stu-id="a599d-138">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="a599d-139">.NET Core 2.2 下载</span><span class="sxs-lookup"><span data-stu-id="a599d-139">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="a599d-140">.NET Core 2.1 下载</span><span class="sxs-lookup"><span data-stu-id="a599d-140">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="a599d-141">Docker</span><span class="sxs-lookup"><span data-stu-id="a599d-141">Docker</span></span>

<span data-ttu-id="a599d-142">容器提供了一种将应用程序与主机系统的其余部分隔离的轻量级方法。</span><span class="sxs-lookup"><span data-stu-id="a599d-142">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="a599d-143">同一计算机上的容器只共享内核，并使用为应用程序提供的资源。</span><span class="sxs-lookup"><span data-stu-id="a599d-143">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="a599d-144">.NET Core 可在 Docker 容器中运行。</span><span class="sxs-lookup"><span data-stu-id="a599d-144">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="a599d-145">官方 .NET Core Docker 映像发布到 Microsoft 容器注册表 (MCR)，用户可以在 [Microsoft.NET Core Docker 中心存储库](https://hub.docker.com/_/microsoft-dotnet-core/)中找到这些映像。</span><span class="sxs-lookup"><span data-stu-id="a599d-145">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="a599d-146">每个存储库包含 .NET（SDK 或运行时）和可以使用的操作系统的不同组合的映像。</span><span class="sxs-lookup"><span data-stu-id="a599d-146">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="a599d-147">Microsoft 提供适合特定场景的映像。</span><span class="sxs-lookup"><span data-stu-id="a599d-147">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="a599d-148">例如，[ASP.NET Core 存储库](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)提供针对在生产环境中运行 ASP.NET Core 应用生成的映像。</span><span class="sxs-lookup"><span data-stu-id="a599d-148">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="a599d-149">有关在 Docker 容器中使用 .NET Core 的详细信息，请参阅 [.NET 和 Docker 简介](../docker/introduction.md)和[示例](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)。</span><span class="sxs-lookup"><span data-stu-id="a599d-149">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a599d-150">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a599d-150">Next steps</span></span>

- <span data-ttu-id="a599d-151">[如何检查是否已安装 .NET Core](how-to-detect-installed-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="a599d-151">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
