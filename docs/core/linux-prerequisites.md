---
title: Linux 上 .NET Core 的先决条件
description: 支持的 Linux 版本和 .NET Core 依赖项，用于在 Linux 计算机上开发、部署和运行 .NET Core 应用程序。
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS,
author: jralexander
ms.author: johalex
ms.date: 04/19/2018
ms.topic: conceptual
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.workload:
- dotnetcore
ms.openlocfilehash: 7ce13af00a43e1ce84f7c8af70155d0c4a5bed4c
ms.sourcegitcommit: 68b60d38043e50104ccc90c76f8599b1ffe18346
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="1c333-104">Linux 上 .NET Core 的先决条件</span><span class="sxs-lookup"><span data-stu-id="1c333-104">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="1c333-105">本文介绍了在 Linux 上开发 .NET Core 应用程序所需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="1c333-105">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="1c333-106">支持的 Linux 发行版本/版本和依赖项适用于在 Linux 上开发 .NET Core 应用程序的两种方法：</span><span class="sxs-lookup"><span data-stu-id="1c333-106">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="1c333-107">结合使用命令行和常用编辑器</span><span class="sxs-lookup"><span data-stu-id="1c333-107">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="1c333-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="1c333-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

> [!NOTE]
> <span data-ttu-id="1c333-109">生产服务器/环境不需要 .NET Core SDK 包。</span><span class="sxs-lookup"><span data-stu-id="1c333-109">The .NET Core SDK package is not required for production servers/environments.</span></span> <span data-ttu-id="1c333-110">部署到生产环境的应用只需要 .NET Core 运行时包。</span><span class="sxs-lookup"><span data-stu-id="1c333-110">Only the .NET Core runtime package is needed for apps deployed to production environments.</span></span> <span data-ttu-id="1c333-111">.NET Core 运行时与应用一同部署为独立部署的一部分，但是，对于依赖框架的部署应用，它必须单独部署。</span><span class="sxs-lookup"><span data-stu-id="1c333-111">The .NET Core runtime is deployed with apps as part of a self-contained deployment, however, it must be deployed for Framework-dependent deployed apps separately.</span></span> <span data-ttu-id="1c333-112">有关依赖框架和独立部署类型的更多信息，请参阅 [.NET Core 应用程序部署](./deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="1c333-112">For more information about framework-dependent and self-contained deployment types, see [.NET Core application deployment](./deploying/index.md).</span></span> <span data-ttu-id="1c333-113">另请参阅[独立式 Linux 应用程序](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)，了解特定准则。</span><span class="sxs-lookup"><span data-stu-id="1c333-113">Also see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) for specific guidelines.</span></span>

## <a name="supported-linux-versions"></a><span data-ttu-id="1c333-114">支持的 Linux 版本</span><span class="sxs-lookup"><span data-stu-id="1c333-114">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="1c333-115">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="1c333-115">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="1c333-116">.NET Core 2.x 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="1c333-116">.NET Core 2.x treats Linux as a single operating system.</span></span> <span data-ttu-id="1c333-117">支持的 Linux 分发都对应有一个 Linux 内部版本（根据芯片体系结构）。</span><span class="sxs-lookup"><span data-stu-id="1c333-117">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="1c333-118">以下 Linux 64 位（`x86_64` 或 `amd64`）发行版本/版本支持 NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="1c333-118">NET Core 2.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="1c333-119">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="1c333-119">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="1c333-120">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="1c333-120">CentOS 7</span></span>
* <span data-ttu-id="1c333-121">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="1c333-121">Oracle Linux 7</span></span>
* <span data-ttu-id="1c333-122">Fedora 27、26</span><span class="sxs-lookup"><span data-stu-id="1c333-122">Fedora 27, 26</span></span>
* <span data-ttu-id="1c333-123">Debian 9、8.7 或更高版本</span><span class="sxs-lookup"><span data-stu-id="1c333-123">Debian 9, 8.7 or later versions</span></span>
* <span data-ttu-id="1c333-124">Ubuntu 17.10、16.04、14.04</span><span class="sxs-lookup"><span data-stu-id="1c333-124">Ubuntu 17.10, 16.04, 14.04</span></span>
* <span data-ttu-id="1c333-125">Linux Mint 18、17</span><span class="sxs-lookup"><span data-stu-id="1c333-125">Linux Mint 18, 17</span></span>
* <span data-ttu-id="1c333-126">openSUSE 42.3 或更高版本</span><span class="sxs-lookup"><span data-stu-id="1c333-126">openSUSE 42.3 or later versions</span></span>
* <span data-ttu-id="1c333-127">SUSE Enterprise Linux (SLES) 12 Service Pack 2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="1c333-127">SUSE Enterprise Linux (SLES) 12 Service Pack 2 or later</span></span>

<span data-ttu-id="1c333-128">有关 .NET Core 2.x 支持的操作系统、分发和版本、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 2.x - 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="1c333-128">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1c333-129">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1c333-129">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="1c333-130">以下 Linux 64 位（`x86_64` 或 `amd64`）发行版本/版本支持 .NET Core 1.x：</span><span class="sxs-lookup"><span data-stu-id="1c333-130">.NET Core 1.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="1c333-131">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="1c333-131">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="1c333-132">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="1c333-132">CentOS 7</span></span>
* <span data-ttu-id="1c333-133">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="1c333-133">Oracle Linux 7</span></span>
* <span data-ttu-id="1c333-134">Fedora 26</span><span class="sxs-lookup"><span data-stu-id="1c333-134">Fedora 26</span></span>
* <span data-ttu-id="1c333-135">Debian 8.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="1c333-135">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="1c333-136">Ubuntu 16.04、14.04</span><span class="sxs-lookup"><span data-stu-id="1c333-136">Ubuntu 16.04, 14.04</span></span>
* <span data-ttu-id="1c333-137">Linux Mint 18、17</span><span class="sxs-lookup"><span data-stu-id="1c333-137">Linux Mint 18, 17</span></span>
* <span data-ttu-id="1c333-138">openSUSE 42.3 或更高版本 (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="1c333-138">openSUSE 42.3 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="1c333-139">有关支持 .NET Core 1.x 的操作系统、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 1.x - 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="1c333-139">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="1c333-140">Linux 发行版本依赖项</span><span class="sxs-lookup"><span data-stu-id="1c333-140">Linux distribution dependencies</span></span>

<span data-ttu-id="1c333-141">以下各项用作示例。</span><span class="sxs-lookup"><span data-stu-id="1c333-141">The following are intended to be examples.</span></span> <span data-ttu-id="1c333-142">确切的版本和名称可能因所选 Linux 发行版本略有不同。</span><span class="sxs-lookup"><span data-stu-id="1c333-142">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="1c333-143">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1c333-143">Ubuntu</span></span>

<span data-ttu-id="1c333-144">Ubuntu 发行版本需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="1c333-144">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="1c333-145">libunwind8</span><span class="sxs-lookup"><span data-stu-id="1c333-145">libunwind8</span></span>
* <span data-ttu-id="1c333-146">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="1c333-146">liblttng-ust0</span></span>
* <span data-ttu-id="1c333-147">libcurl3</span><span class="sxs-lookup"><span data-stu-id="1c333-147">libcurl3</span></span>
* <span data-ttu-id="1c333-148">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="1c333-148">libssl1.0.0</span></span>
* <span data-ttu-id="1c333-149">libuuid1</span><span class="sxs-lookup"><span data-stu-id="1c333-149">libuuid1</span></span>
* <span data-ttu-id="1c333-150">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="1c333-150">libkrb5-3</span></span>
* <span data-ttu-id="1c333-151">zlib1g</span><span class="sxs-lookup"><span data-stu-id="1c333-151">zlib1g</span></span>
* <span data-ttu-id="1c333-152">libicu52（针对 14.x）</span><span class="sxs-lookup"><span data-stu-id="1c333-152">libicu52 (for 14.x)</span></span>
* <span data-ttu-id="1c333-153">libicu55（针对 16.x）</span><span class="sxs-lookup"><span data-stu-id="1c333-153">libicu55 (for 16.x)</span></span>
* <span data-ttu-id="1c333-154">libicu57（针对 17.x）</span><span class="sxs-lookup"><span data-stu-id="1c333-154">libicu57 (for 17.x)</span></span>

### <a name="centos"></a><span data-ttu-id="1c333-155">CentOS</span><span class="sxs-lookup"><span data-stu-id="1c333-155">CentOS</span></span>

<span data-ttu-id="1c333-156">CentOS 发行版本需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="1c333-156">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="1c333-157">libunwind</span><span class="sxs-lookup"><span data-stu-id="1c333-157">libunwind</span></span>
* <span data-ttu-id="1c333-158">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="1c333-158">lttng-ust</span></span>
* <span data-ttu-id="1c333-159">libcurl</span><span class="sxs-lookup"><span data-stu-id="1c333-159">libcurl</span></span>
* <span data-ttu-id="1c333-160">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="1c333-160">openssl-libs</span></span>
* <span data-ttu-id="1c333-161">libuuid</span><span class="sxs-lookup"><span data-stu-id="1c333-161">libuuid</span></span>
* <span data-ttu-id="1c333-162">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="1c333-162">krb5-libs</span></span>
* <span data-ttu-id="1c333-163">libicu</span><span class="sxs-lookup"><span data-stu-id="1c333-163">libicu</span></span>
* <span data-ttu-id="1c333-164">zlib</span><span class="sxs-lookup"><span data-stu-id="1c333-164">zlib</span></span>

<span data-ttu-id="1c333-165">有关依赖项的详细信息，请参阅[独立式 Linux 应用程序](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="1c333-165">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="1c333-166">使用本机安装程序安装 .NET Core 依赖项</span><span class="sxs-lookup"><span data-stu-id="1c333-166">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="1c333-167">.NET Core 本机安装程序适用于支持的 Linux 发行版本/版本。</span><span class="sxs-lookup"><span data-stu-id="1c333-167">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="1c333-168">本机安装程序需要拥有对服务器的管理员 (sudo) 访问权限。</span><span class="sxs-lookup"><span data-stu-id="1c333-168">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="1c333-169">使用本机安装程序的优势在于，可以安装所有 .NET Core 本机依赖项。</span><span class="sxs-lookup"><span data-stu-id="1c333-169">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="1c333-170">本机安装程序还会在整个系统内安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="1c333-170">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="1c333-171">在 Linux 上，安装程序包有两种使用方式：</span><span class="sxs-lookup"><span data-stu-id="1c333-171">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="1c333-172">使用基于源的包管理器，如适用于 Ubuntu 的 apt-get，或适用于 CentOS/RHEL 的 yum。</span><span class="sxs-lookup"><span data-stu-id="1c333-172">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="1c333-173">使用包本身（DEB 或 RPM）。</span><span class="sxs-lookup"><span data-stu-id="1c333-173">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="1c333-174">使用 .NET Core 安装程序脚本编写安装脚本</span><span class="sxs-lookup"><span data-stu-id="1c333-174">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="1c333-175">[dotnet-install 脚本](./tools/dotnet-install-script.md)用于执行 CLI 工具链和共享运行时的非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="1c333-175">The [dotnet-install scripts](./tools/dotnet-install-script.md) are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="1c333-176">可通过 [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh) 下载脚本。</span><span class="sxs-lookup"><span data-stu-id="1c333-176">You can download the script from [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh).</span></span>

<span data-ttu-id="1c333-177">安装程序 bash 脚本用于自动化方案和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="1c333-177">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="1c333-178">此脚本也读取 PowerShell 开关，因此可以与 Linux/OS X 系统上的脚本结合使用。</span><span class="sxs-lookup"><span data-stu-id="1c333-178">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

## <a name="install-net-core-for-supported-red-hat-enterprise-linux-rhel-versions"></a><span data-ttu-id="1c333-179">为支持的 Red Hat Enterprise Linux (RHEL) 版本安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="1c333-179">Install .NET Core for supported Red Hat Enterprise Linux (RHEL) versions</span></span>

<span data-ttu-id="1c333-180">在支持的 RHEL 版本上安装 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="1c333-180">To install .NET Core on supported RHEL versions:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="1c333-181">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="1c333-181">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="1c333-182">为确保获得最新的安装信息，请遵循适用于支持的 RHEL 版本的 [.NET Core 2.x SDK 和 Runtime 安装程序说明](https://www.microsoft.com/net/download/linux-package-manager/rhel/sdk-current)。</span><span class="sxs-lookup"><span data-stu-id="1c333-182">To ensure you have the latest installation information, follow the [.NET Core 2.x SDK and Runtime Installer instructions](https://www.microsoft.com/net/download/linux-package-manager/rhel/sdk-current) for supported RHEL versions.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1c333-183">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1c333-183">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="1c333-184">**.NET Core 1.1**</span><span class="sxs-lookup"><span data-stu-id="1c333-184">**.NET Core 1.1**</span></span>

1. <span data-ttu-id="1c333-185">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="1c333-185">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2.  <span data-ttu-id="1c333-186">有关 Red Hat Enterprise Linux 上最新的 .NET Core 1.1 安装信息，请参阅 [.NET Core 1.1 入门指南](https://access.redhat.com/documentation/en-us/net_core/1.1/html/getting_started_guide/)</span><span class="sxs-lookup"><span data-stu-id="1c333-186">For the latest .NET Core 1.1 on Red Hat Enterprise Linux installation information, see [the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/1.1/html/getting_started_guide/)</span></span>
     
<span data-ttu-id="1c333-187">**.NET Core 1.0**</span><span class="sxs-lookup"><span data-stu-id="1c333-187">**.NET Core 1.0**</span></span>

1. <span data-ttu-id="1c333-188">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="1c333-188">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2.  <span data-ttu-id="1c333-189">有关 Red Hat Enterprise Linux 上最新的 .NET Core 1.0 安装信息，请参阅 [.NET Core 1.0 入门指南](https://access.redhat.com/documentation/en-us/net_core/1.0/html/getting_started_guide/)</span><span class="sxs-lookup"><span data-stu-id="1c333-189">For the latest .NET Core 1.0 on Red Hat Enterprise Linux installation information, see [the .NET Core 1.0 Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/1.0/html/getting_started_guide/)</span></span>

<span data-ttu-id="1c333-190">若要获取 Red Hat .NET 通道访问注册方面的帮助，请参阅 Red Hat 提供的 [.NET Core 1.1 入门指南的第 1 章](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/)。</span><span class="sxs-lookup"><span data-stu-id="1c333-190">For Red Hat .NET channel access registration help, see [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) at Red Hat.</span></span>

---

## <a name="install-net-core-for-supported-ubuntu-and-linux-mint-distributionsversions-64-bit"></a><span data-ttu-id="1c333-191">为支持的 Ubuntu 和 Linux Mint 分发/版本（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="1c333-191">Install .NET Core for supported Ubuntu and Linux Mint distributions/versions (64 bit)</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="1c333-192">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="1c333-192">.NET Core 2.x</span></span>](#tab/netcore2x)

1. <span data-ttu-id="1c333-193">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="1c333-193">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="1c333-194">在支持的 Ubuntu 和 Linux Mint 分发/版本（64 位）上安装 .NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="1c333-194">Install .NET Core 2.x on supported Ubuntu and Linux Mint distributions/versions (64 bit):</span></span>

<span data-ttu-id="1c333-195">**.NET Core 2.0**</span><span class="sxs-lookup"><span data-stu-id="1c333-195">**.NET Core 2.0**</span></span>

|<span data-ttu-id="1c333-196">Runtime / SDK</span><span class="sxs-lookup"><span data-stu-id="1c333-196">Runtimes / SDKs</span></span>          |<span data-ttu-id="1c333-197">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="1c333-197">Ubuntu 17.10</span></span>  |<span data-ttu-id="1c333-198">Ubuntu 16.04 / Linux Mint 18</span><span class="sxs-lookup"><span data-stu-id="1c333-198">Ubuntu 16.04 / Linux Mint 18</span></span>|<span data-ttu-id="1c333-199">Ubuntu 14.04 / Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="1c333-199">Ubuntu 14.04 / Linux Mint 17</span></span>|
|-------------------------|--------------|----------------------------|----------------------------|
|<span data-ttu-id="1c333-200">.NET Core Runtime 2.0.6</span><span class="sxs-lookup"><span data-stu-id="1c333-200">.NET Core Runtime 2.0.6</span></span>  |[<span data-ttu-id="1c333-201">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-201">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.6)|[<span data-ttu-id="1c333-202">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-202">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.6)          |[<span data-ttu-id="1c333-203">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-203">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.6)            |
|<span data-ttu-id="1c333-204">.NET Core Runtime 2.0.5</span><span class="sxs-lookup"><span data-stu-id="1c333-204">.NET Core Runtime 2.0.5</span></span>  |[<span data-ttu-id="1c333-205">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-205">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.5)|[<span data-ttu-id="1c333-206">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-206">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.5)          |[<span data-ttu-id="1c333-207">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-207">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.5)            |
|<span data-ttu-id="1c333-208">.NET Core SDK 2.1.103</span><span class="sxs-lookup"><span data-stu-id="1c333-208">.NET Core SDK 2.1.103</span></span>    |[<span data-ttu-id="1c333-209">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-209">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.103)|[<span data-ttu-id="1c333-210">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-210">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.103)            |[<span data-ttu-id="1c333-211">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-211">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.103)            |
|<span data-ttu-id="1c333-212">.NET Core SDK 2.0.3</span><span class="sxs-lookup"><span data-stu-id="1c333-212">.NET Core SDK 2.0.3</span></span>      |[<span data-ttu-id="1c333-213">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-213">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.0.3)|[<span data-ttu-id="1c333-214">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-214">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.0.3)          |[<span data-ttu-id="1c333-215">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-215">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.0.3)            |

<span data-ttu-id="1c333-216">**.NET Core 2.1**</span><span class="sxs-lookup"><span data-stu-id="1c333-216">**.NET Core 2.1**</span></span>

>[!IMPORTANT]
> <span data-ttu-id="1c333-217">若要将 .NET Core 2.1 与 Visual Studio 一起使用，需要[安装 Visual Studio 2017 15.7 Preview 1 或更高版本](https://www.visualstudio.com/vs/preview)。</span><span class="sxs-lookup"><span data-stu-id="1c333-217">To use .NET Core 2.1 with Visual Studio, you need to [install Visual Studio 2017 15.7 Preview 1 or newer](https://www.visualstudio.com/vs/preview).</span></span>

|<span data-ttu-id="1c333-218">Runtime / SDK</span><span class="sxs-lookup"><span data-stu-id="1c333-218">Runtimes / SDKs</span></span>                  |<span data-ttu-id="1c333-219">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="1c333-219">Ubuntu 17.10</span></span>    |<span data-ttu-id="1c333-220">Ubuntu 16.04 / Linux Mint 18</span><span class="sxs-lookup"><span data-stu-id="1c333-220">Ubuntu 16.04 / Linux Mint 18</span></span>|<span data-ttu-id="1c333-221">Ubuntu 14.04 / Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="1c333-221">Ubuntu 14.04 / Linux Mint 17</span></span>|
|---------------------------------|----------------|----------------------------|----------------------------|
|<span data-ttu-id="1c333-222">.NET Core Runtime 2.1.0-preview2</span><span class="sxs-lookup"><span data-stu-id="1c333-222">.NET Core Runtime 2.1.0-preview2</span></span> |[<span data-ttu-id="1c333-223">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-223">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.0-preview2)|[<span data-ttu-id="1c333-224">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-224">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.0-preview2)            |[<span data-ttu-id="1c333-225">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-225">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.0-preview2)            |
|<span data-ttu-id="1c333-226">.NET Core Runtime 2.1.0-preview1</span><span class="sxs-lookup"><span data-stu-id="1c333-226">.NET Core Runtime 2.1.0-preview1</span></span> |[<span data-ttu-id="1c333-227">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-227">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.0-preview1)|[<span data-ttu-id="1c333-228">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-228">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.0-preview1)            |[<span data-ttu-id="1c333-229">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-229">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.0-preview1)            |
|<span data-ttu-id="1c333-230">.NET Core SDK 2.1.300-preview2</span><span class="sxs-lookup"><span data-stu-id="1c333-230">.NET Core SDK 2.1.300-preview2</span></span>   |[<span data-ttu-id="1c333-231">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-231">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.300-preview2)|[<span data-ttu-id="1c333-232">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-232">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.300-preview2)            |[<span data-ttu-id="1c333-233">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-233">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.300-preview2)
|<span data-ttu-id="1c333-234">.NET Core SDK 2.1.300-preview1</span><span class="sxs-lookup"><span data-stu-id="1c333-234">.NET Core SDK 2.1.300-preview1</span></span>   |[<span data-ttu-id="1c333-235">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-235">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.300-preview1)|[<span data-ttu-id="1c333-236">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-236">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.300-preview1)            |[<span data-ttu-id="1c333-237">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-237">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.300-preview1)            |


# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1c333-238">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1c333-238">.NET Core 1.x</span></span>](#tab/netcore1x)

1. <span data-ttu-id="1c333-239">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="1c333-239">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="1c333-240">在支持的 Ubuntu 和 Linux Mint 分发/版本（64 位）上安装 .NET Core 1.x：</span><span class="sxs-lookup"><span data-stu-id="1c333-240">Install .NET Core 1.x on supported Ubuntu and Linux Mint distributions/versions (64 bit):</span></span>

| <span data-ttu-id="1c333-241">Runtime / SDK</span><span class="sxs-lookup"><span data-stu-id="1c333-241">Runtimes / SDKs</span></span>         |<span data-ttu-id="1c333-242">Ubuntu 16.04 / Linux Mint 18</span><span class="sxs-lookup"><span data-stu-id="1c333-242">Ubuntu 16.04 / Linux Mint 18</span></span>|<span data-ttu-id="1c333-243">Ubuntu 14.04 / Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="1c333-243">Ubuntu 14.04 / Linux Mint 17</span></span>|
|-------------------------|----------------------------|----------------------------|
|<span data-ttu-id="1c333-244">.NET Core Runtime 1.1.7</span><span class="sxs-lookup"><span data-stu-id="1c333-244">.NET Core Runtime 1.1.7</span></span>  |[<span data-ttu-id="1c333-245">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-245">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="1c333-246">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-246">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="1c333-247">.NET Core Runtime 1.1.6</span><span class="sxs-lookup"><span data-stu-id="1c333-247">.NET Core Runtime 1.1.6</span></span>  |[<span data-ttu-id="1c333-248">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-248">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="1c333-249">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-249">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="1c333-250">.NET Core Runtime 1.0.10</span><span class="sxs-lookup"><span data-stu-id="1c333-250">.NET Core Runtime 1.0.10</span></span> |[<span data-ttu-id="1c333-251">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-251">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="1c333-252">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-252">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="1c333-253">.NET Core Runtime 1.0.9</span><span class="sxs-lookup"><span data-stu-id="1c333-253">.NET Core Runtime 1.0.9</span></span>  |[<span data-ttu-id="1c333-254">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-254">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="1c333-255">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-255">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="1c333-256">.NET Core SDK 1.1.8</span><span class="sxs-lookup"><span data-stu-id="1c333-256">.NET Core SDK 1.1.8</span></span>      |[<span data-ttu-id="1c333-257">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-257">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="1c333-258">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-258">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="1c333-259">.NET Core SDK 1.1.7</span><span class="sxs-lookup"><span data-stu-id="1c333-259">.NET Core SDK 1.1.7</span></span>      |[<span data-ttu-id="1c333-260">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-260">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="1c333-261">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-261">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="1c333-262">.NET Core SDK 1.0.4</span><span class="sxs-lookup"><span data-stu-id="1c333-262">.NET Core SDK 1.0.4</span></span>      |[<span data-ttu-id="1c333-263">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-263">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="1c333-264">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-264">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="1c333-265">.NET Core SDK 1.0.1</span><span class="sxs-lookup"><span data-stu-id="1c333-265">.NET Core SDK 1.0.1</span></span>      |[<span data-ttu-id="1c333-266">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-266">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="1c333-267">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-267">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-ubuntu-14.04-x64-binaries)            |

---

## <a name="install-net-core-for-supported-debian-versions-64-bit"></a><span data-ttu-id="1c333-268">为支持的 Debian 版本（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="1c333-268">Install .NET Core for supported Debian versions (64 bit)</span></span>

<span data-ttu-id="1c333-269">在支持的 Debian 版本（64 位）上安装 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="1c333-269">To install .NET Core on supported Debian versions (64 bit):</span></span>

> [!NOTE]
> <span data-ttu-id="1c333-270">必须有用户控制目录，才能通过 tar.gz 在 Linux 系统上进行安装。</span><span class="sxs-lookup"><span data-stu-id="1c333-270">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="1c333-271">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="1c333-271">.NET Core 2.x</span></span>](#tab/netcore2x)

1. <span data-ttu-id="1c333-272">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="1c333-272">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="1c333-273">在支持的 Debian 版本（64 位）上安装 .NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="1c333-273">Install .NET Core 2.x on supported Debian versions (64 bit):</span></span>

<span data-ttu-id="1c333-274">**.NET Core 2.0**</span><span class="sxs-lookup"><span data-stu-id="1c333-274">**.NET Core 2.0**</span></span>

|<span data-ttu-id="1c333-275">Runtime / SDK</span><span class="sxs-lookup"><span data-stu-id="1c333-275">Runtimes / SDKs</span></span>          |<span data-ttu-id="1c333-276">Debian 9</span><span class="sxs-lookup"><span data-stu-id="1c333-276">Debian 9</span></span>       |<span data-ttu-id="1c333-277">Debian 8</span><span class="sxs-lookup"><span data-stu-id="1c333-277">Debian 8</span></span>       |
|-------------------------|---------------|---------------|
|<span data-ttu-id="1c333-278">.NET Core Runtime 2.0.6</span><span class="sxs-lookup"><span data-stu-id="1c333-278">.NET Core Runtime 2.0.6</span></span>  |[<span data-ttu-id="1c333-279">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-279">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.6)   |[<span data-ttu-id="1c333-280">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-280">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.6)   |
|<span data-ttu-id="1c333-281">.NET Core Runtime 2.0.5</span><span class="sxs-lookup"><span data-stu-id="1c333-281">.NET Core Runtime 2.0.5</span></span>  |[<span data-ttu-id="1c333-282">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-282">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.5)   |[<span data-ttu-id="1c333-283">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-283">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.5)   |
|<span data-ttu-id="1c333-284">.NET Core SDK 2.1.103</span><span class="sxs-lookup"><span data-stu-id="1c333-284">.NET Core SDK 2.1.103</span></span>    |[<span data-ttu-id="1c333-285">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-285">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.103)   |[<span data-ttu-id="1c333-286">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-286">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.103)   |
|<span data-ttu-id="1c333-287">.NET Core SDK 2.0.3</span><span class="sxs-lookup"><span data-stu-id="1c333-287">.NET Core SDK 2.0.3</span></span>      |[<span data-ttu-id="1c333-288">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-288">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.0.3)   |[<span data-ttu-id="1c333-289">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-289">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.0.3)   |

<span data-ttu-id="1c333-290">**.NET Core 2.1**</span><span class="sxs-lookup"><span data-stu-id="1c333-290">**.NET Core 2.1**</span></span>

>[!IMPORTANT]
> <span data-ttu-id="1c333-291">若要将 .NET Core 2.1 与 Visual Studio 一起使用，需要[安装 Visual Studio 2017 15.7 Preview 1 或更高版本](https://www.visualstudio.com/vs/preview)。</span><span class="sxs-lookup"><span data-stu-id="1c333-291">To use .NET Core 2.1 with Visual Studio, you need to [install Visual Studio 2017 15.7 Preview 1 or newer](https://www.visualstudio.com/vs/preview).</span></span>

|<span data-ttu-id="1c333-292">Runtime / SDK</span><span class="sxs-lookup"><span data-stu-id="1c333-292">Runtimes / SDKs</span></span>                  |<span data-ttu-id="1c333-293">Debian 9</span><span class="sxs-lookup"><span data-stu-id="1c333-293">Debian 9</span></span>       |<span data-ttu-id="1c333-294">Debian 8</span><span class="sxs-lookup"><span data-stu-id="1c333-294">Debian 8</span></span>       |
|---------------------------------|---------------|---------------|
|<span data-ttu-id="1c333-295">.NET Core Runtime 2.1.0-preview2</span><span class="sxs-lookup"><span data-stu-id="1c333-295">.NET Core Runtime 2.1.0-preview2</span></span> |[<span data-ttu-id="1c333-296">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-296">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.0-preview2)   |[<span data-ttu-id="1c333-297">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-297">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.0-preview2)   |
|<span data-ttu-id="1c333-298">.NET Core Runtime 2.1.0-preview1</span><span class="sxs-lookup"><span data-stu-id="1c333-298">.NET Core Runtime 2.1.0-preview1</span></span> |[<span data-ttu-id="1c333-299">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-299">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.0-preview1)   |[<span data-ttu-id="1c333-300">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-300">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.0-preview1)   |
|<span data-ttu-id="1c333-301">.NET Core SDK 2.1.300-preview2</span><span class="sxs-lookup"><span data-stu-id="1c333-301">.NET Core SDK 2.1.300-preview2</span></span>   |[<span data-ttu-id="1c333-302">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-302">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.300-preview2)   |[<span data-ttu-id="1c333-303">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-303">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.300-preview2)   |
|<span data-ttu-id="1c333-304">.NET Core SDK 2.1.300-preview1</span><span class="sxs-lookup"><span data-stu-id="1c333-304">.NET Core SDK 2.1.300-preview1</span></span>   |[<span data-ttu-id="1c333-305">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-305">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.300-preview1)   |[<span data-ttu-id="1c333-306">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-306">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.300-preview1)   |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1c333-307">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1c333-307">.NET Core 1.x</span></span>](#tab/netcore1x)

1. <span data-ttu-id="1c333-308">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="1c333-308">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="1c333-309">在 Debian 9 或 Debian 8 上安装 .NET Core 1.x：</span><span class="sxs-lookup"><span data-stu-id="1c333-309">Install .NET Core 1.x on Debian 9 or Debian 8:</span></span>

* <span data-ttu-id="1c333-310">.NET Core Runtime 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-310">.NET Core Runtime 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="1c333-311">.NET Core Runtime 1.1.6 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-311">.NET Core Runtime 1.1.6 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="1c333-312">.NET Core Runtime 1.0.10 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-312">.NET Core Runtime 1.0.10 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="1c333-313">.NET Core Runtime 1.0.9 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-313">.NET Core Runtime 1.0.9 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="1c333-314">.NET Core SDK 1.1.8 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-314">.NET Core SDK 1.1.8 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="1c333-315">.NET Core SDK 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-315">.NET Core SDK 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="1c333-316">.NET Core SDK 1.0.4 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-316">.NET Core SDK 1.0.4 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="1c333-317">.NET Core SDK 1.0.1 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-317">.NET Core SDK 1.0.1 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)</span></span>

---

## <a name="install-net-core-for-supported-fedora-versions-64-bit"></a><span data-ttu-id="1c333-318">为支持的 Fedora 版本（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="1c333-318">Install .NET Core for supported Fedora versions (64 bit)</span></span>

<span data-ttu-id="1c333-319">在支持的 Fedora 版本上安装 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="1c333-319">To install .NET Core on supported Fedora versions:</span></span>

> [!NOTE]
> <span data-ttu-id="1c333-320">必须有用户控制目录，才能通过 tar.gz 在 Linux 系统上进行安装。</span><span class="sxs-lookup"><span data-stu-id="1c333-320">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="1c333-321">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="1c333-321">.NET Core 2.x</span></span>](#tab/netcore2x)

1. <span data-ttu-id="1c333-322">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="1c333-322">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="1c333-323">在支持的 Fedora 版本（64 位）上安装 .NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="1c333-323">Install .NET Core 2.x on supported Fedora versions (64 bit):</span></span>

<span data-ttu-id="1c333-324">**.NET Core 2.0**</span><span class="sxs-lookup"><span data-stu-id="1c333-324">**.NET Core 2.0**</span></span>

|<span data-ttu-id="1c333-325">Runtime / SDK</span><span class="sxs-lookup"><span data-stu-id="1c333-325">Runtimes / SDKs</span></span>          |<span data-ttu-id="1c333-326">Fedora 26 或更高版本</span><span class="sxs-lookup"><span data-stu-id="1c333-326">Fedora 26 or later</span></span> |<span data-ttu-id="1c333-327">Fedora 25 或以前版本</span><span class="sxs-lookup"><span data-stu-id="1c333-327">Fedora 25 or previous</span></span> |
|-------------------------|-------------------|----------------------|
|<span data-ttu-id="1c333-328">.NET Core Runtime 2.0.6</span><span class="sxs-lookup"><span data-stu-id="1c333-328">.NET Core Runtime 2.0.6</span></span>  |[<span data-ttu-id="1c333-329">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-329">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.6)       |[<span data-ttu-id="1c333-330">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-330">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.6)           |
|<span data-ttu-id="1c333-331">.NET Core Runtime 2.0.5</span><span class="sxs-lookup"><span data-stu-id="1c333-331">.NET Core Runtime 2.0.5</span></span>  |[<span data-ttu-id="1c333-332">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-332">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.5)       |[<span data-ttu-id="1c333-333">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-333">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.5)           |
|<span data-ttu-id="1c333-334">.NET Core SDK 2.1.103</span><span class="sxs-lookup"><span data-stu-id="1c333-334">.NET Core SDK 2.1.103</span></span>    |[<span data-ttu-id="1c333-335">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-335">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.103)       |[<span data-ttu-id="1c333-336">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-336">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.103)           |
|<span data-ttu-id="1c333-337">.NET Core SDK 2.0.3</span><span class="sxs-lookup"><span data-stu-id="1c333-337">.NET Core SDK 2.0.3</span></span>      |[<span data-ttu-id="1c333-338">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-338">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.0.3)       |[<span data-ttu-id="1c333-339">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-339">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.0.3)           |

<span data-ttu-id="1c333-340">**.NET Core 2.1**</span><span class="sxs-lookup"><span data-stu-id="1c333-340">**.NET Core 2.1**</span></span>

>[!IMPORTANT]
> <span data-ttu-id="1c333-341">若要将 .NET Core 2.1 与 Visual Studio 一起使用，需要[安装 Visual Studio 2017 15.7 Preview 1 或更高版本](https://www.visualstudio.com/vs/preview)。</span><span class="sxs-lookup"><span data-stu-id="1c333-341">To use .NET Core 2.1 with Visual Studio, you need to [install Visual Studio 2017 15.7 Preview 1 or newer](https://www.visualstudio.com/vs/preview).</span></span>

|<span data-ttu-id="1c333-342">Runtime / SDK</span><span class="sxs-lookup"><span data-stu-id="1c333-342">Runtimes / SDKs</span></span>                  |<span data-ttu-id="1c333-343">Fedora 26 或更高版本</span><span class="sxs-lookup"><span data-stu-id="1c333-343">Fedora 26 or later</span></span> |<span data-ttu-id="1c333-344">Fedora 25 或以前版本</span><span class="sxs-lookup"><span data-stu-id="1c333-344">Fedora 25 or previous</span></span> |
|---------------------------------|-------------------|----------------------|
|<span data-ttu-id="1c333-345">.NET Core Runtime 2.1.0-preview2</span><span class="sxs-lookup"><span data-stu-id="1c333-345">.NET Core Runtime 2.1.0-preview2</span></span> |[<span data-ttu-id="1c333-346">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-346">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.1.0-preview2)       |[<span data-ttu-id="1c333-347">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-347">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.1.0-preview2)           |
|<span data-ttu-id="1c333-348">.NET Core Runtime 2.1.0-preview1</span><span class="sxs-lookup"><span data-stu-id="1c333-348">.NET Core Runtime 2.1.0-preview1</span></span> |[<span data-ttu-id="1c333-349">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-349">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.1.0-preview1)       |[<span data-ttu-id="1c333-350">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-350">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.1.0-preview1)           |
|<span data-ttu-id="1c333-351">.NET Core SDK 2.1.300-preview2</span><span class="sxs-lookup"><span data-stu-id="1c333-351">.NET Core SDK 2.1.300-preview2</span></span>   |[<span data-ttu-id="1c333-352">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-352">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.300-preview2)       |[<span data-ttu-id="1c333-353">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-353">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.300-preview2)           |
|<span data-ttu-id="1c333-354">.NET Core SDK 2.1.300-preview1</span><span class="sxs-lookup"><span data-stu-id="1c333-354">.NET Core SDK 2.1.300-preview1</span></span>   |[<span data-ttu-id="1c333-355">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-355">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.300-preview1)       |[<span data-ttu-id="1c333-356">安装链接</span><span class="sxs-lookup"><span data-stu-id="1c333-356">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.300-preview1)           |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1c333-357">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1c333-357">.NET Core 1.x</span></span>](#tab/netcore1x)

1. <span data-ttu-id="1c333-358">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="1c333-358">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="1c333-359">在支持的 Fedora 版本（64 位）上安装 .NET Core 1.x：</span><span class="sxs-lookup"><span data-stu-id="1c333-359">Install .NET Core 1.x supported Fedora versions (64 bit):</span></span>

<span data-ttu-id="1c333-360">**Fedora 24**</span><span class="sxs-lookup"><span data-stu-id="1c333-360">**Fedora 24**</span></span>

* <span data-ttu-id="1c333-361">.NET Core Runtime 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-fedora-24-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-361">.NET Core Runtime 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-fedora-24-x64-binaries)</span></span>
* <span data-ttu-id="1c333-362">.NET Core Runtime 1.1.6 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-fedora-24-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-362">.NET Core Runtime 1.1.6 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-fedora-24-x64-binaries)</span></span>
* <span data-ttu-id="1c333-363">.NET Core SDK 1.1.8 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-fedora-24-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-363">.NET Core SDK 1.1.8 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-fedora-24-x64-binaries)</span></span>
* <span data-ttu-id="1c333-364">.NET Core SDK 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-fedora-24-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-364">.NET Core SDK 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-fedora-24-x64-binaries)</span></span>
* <span data-ttu-id="1c333-365">.NET Core SDK 1.0.1 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-365">.NET Core SDK 1.0.1 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)</span></span>

<span data-ttu-id="1c333-366">**Fedora 23**</span><span class="sxs-lookup"><span data-stu-id="1c333-366">**Fedora 23**</span></span>

* <span data-ttu-id="1c333-367">.NET Core Runtime 1.0.9 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-fedora-23-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-367">.NET Core Runtime 1.0.9 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-fedora-23-x64-binaries)</span></span>
* <span data-ttu-id="1c333-368">.NET Core SDK 1.0.4 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-fedora-23-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-368">.NET Core SDK 1.0.4 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-fedora-23-x64-binaries)</span></span>
* <span data-ttu-id="1c333-369">.NET Core SDK 1.0.1 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-fedora-23-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-369">.NET Core SDK 1.0.1 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-fedora-23-x64-binaries)</span></span>

---

## <a name="install-net-core-for-supported-centos-and-oracle-linux-distributionsversions-64-bit"></a><span data-ttu-id="1c333-370">为支持的 CentOS 和 Oracle Linux 分发/版本（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="1c333-370">Install .NET Core for supported CentOS and Oracle Linux distributions/versions (64 bit)</span></span>

<span data-ttu-id="1c333-371">为支持的 CentOS 和 Oracle Linux 分发/版本（64 位）安装 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="1c333-371">To install .NET Core for supported CentOS and Oracle Linux distributions/versions (64 bit):</span></span>

> [!NOTE]
> <span data-ttu-id="1c333-372">必须有用户控制目录，才能通过 tar.gz 在 Linux 系统上进行安装。</span><span class="sxs-lookup"><span data-stu-id="1c333-372">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="1c333-373">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="1c333-373">.NET Core 2.x</span></span>](#tab/netcore2x)

1. <span data-ttu-id="1c333-374">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="1c333-374">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="1c333-375">在支持的 CentOS 和 Oracle Linux 分发/版本（64 位）上安装 .NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="1c333-375">Install .NET Core 2.x on supported CentOS and Oracle Linux distributions/versions (64 bit):</span></span>

<span data-ttu-id="1c333-376">**.NET Core 2.0**</span><span class="sxs-lookup"><span data-stu-id="1c333-376">**.NET Core 2.0**</span></span>

* <span data-ttu-id="1c333-377">.NET Core Runtime 2.0.6 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.6)</span><span class="sxs-lookup"><span data-stu-id="1c333-377">.NET Core Runtime 2.0.6 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.6)</span></span>
* <span data-ttu-id="1c333-378">.NET Core Runtime 2.0.5 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.5)</span><span class="sxs-lookup"><span data-stu-id="1c333-378">.NET Core Runtime 2.0.5 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.5)</span></span>
* <span data-ttu-id="1c333-379">.NET Core SDK 2.1.103 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.103)</span><span class="sxs-lookup"><span data-stu-id="1c333-379">.NET Core SDK 2.1.103 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.103)</span></span>
* <span data-ttu-id="1c333-380">.NET Core SDK 2.0.3 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.0.3)</span><span class="sxs-lookup"><span data-stu-id="1c333-380">.NET Core SDK 2.0.3 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.0.3)</span></span>
 
<span data-ttu-id="1c333-381">**.NET Core 2.1**</span><span class="sxs-lookup"><span data-stu-id="1c333-381">**.NET Core 2.1**</span></span>

>[!IMPORTANT]
> <span data-ttu-id="1c333-382">若要将 .NET Core 2.1 与 Visual Studio 一起使用，需要[安装 Visual Studio 2017 15.7 Preview 1 或更高版本](https://www.visualstudio.com/vs/preview/)。</span><span class="sxs-lookup"><span data-stu-id="1c333-382">To use .NET Core 2.1 with Visual Studio, you need to [install Visual Studio 2017 15.7 Preview 1 or newer](https://www.visualstudio.com/vs/preview/).</span></span>

* <span data-ttu-id="1c333-383">.NET Core Runtime 2.1.0-preview2 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview2)</span><span class="sxs-lookup"><span data-stu-id="1c333-383">.NET Core Runtime 2.1.0-preview2 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview2)</span></span>
* <span data-ttu-id="1c333-384">.NET Core Runtime 2.1.0-preview1 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview1)</span><span class="sxs-lookup"><span data-stu-id="1c333-384">.NET Core Runtime 2.1.0-preview1 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview1)</span></span>
* <span data-ttu-id="1c333-385">.NET Core SDK 2.1.300-preview2 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview2)</span><span class="sxs-lookup"><span data-stu-id="1c333-385">.NET Core SDK 2.1.300-preview2 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview2)</span></span>
* <span data-ttu-id="1c333-386">.NET Core SDK 2.1.300-preview1 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview1)</span><span class="sxs-lookup"><span data-stu-id="1c333-386">.NET Core SDK 2.1.300-preview1 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview1)</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1c333-387">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1c333-387">.NET Core 1.x</span></span>](#tab/netcore1x)

1. <span data-ttu-id="1c333-388">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="1c333-388">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="1c333-389">在支持的 CentOS 和 Oracle Linux 发行版本/版本（64 位）上安装 .NET Core 1.x：</span><span class="sxs-lookup"><span data-stu-id="1c333-389">Install .NET Core 1.x on supported CentOS and Oracle Linux distributions/versions (64 bit):</span></span>

* <span data-ttu-id="1c333-390">.NET Core Runtime 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-390">.NET Core Runtime 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="1c333-391">.NET Core Runtime 1.1.6 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-391">.NET Core Runtime 1.1.6 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="1c333-392">.NET Core Runtime 1.0.10 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-392">.NET Core Runtime 1.0.10 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="1c333-393">.NET Core Runtime 1.0.9 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-393">.NET Core Runtime 1.0.9 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="1c333-394">.NET Core SDK 1.1.8 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-394">.NET Core SDK 1.1.8 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="1c333-395">.NET Core SDK 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-395">.NET Core SDK 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="1c333-396">.NET Core SDK 1.0.4 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-396">.NET Core SDK 1.0.4 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="1c333-397">.NET Core SDK 1.0.1 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-397">.NET Core SDK 1.0.1 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-centos-x64-binaries)</span></span>

---

## <a name="install-net-core-for-supported-suse-linux-enterprise-server-and-opensuse-distributionsversions-64-bit"></a><span data-ttu-id="1c333-398">为支持的 SUSE Linux Enterprise Server 和 OpenSUSE 发行版本/版本（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="1c333-398">Install .NET Core for supported SUSE Linux Enterprise Server and OpenSUSE distributions/versions (64 bit)</span></span>

<span data-ttu-id="1c333-399">为支持的 SUSE Linux Enterprise Server 和 OpenSUSE 发行版本/版本（64 位）安装 .NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="1c333-399">To install .NET Core 2.x for supported SUSE Linux Enterprise Server and OpenSUSE distributions/versions (64 bit):</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="1c333-400">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="1c333-400">.NET Core 2.x</span></span>](#tab/netcore2x)

1. <span data-ttu-id="1c333-401">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="1c333-401">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="1c333-402">在支持的 SUSE Linux Enterprise Server 和 OpenSUSE 发行版本/版本（64 位）上安装 .NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="1c333-402">Install .NET Core 2.x on supported SUSE Linux Enterprise Server and OpenSUSE distributions/versions (64 bit):</span></span>

<span data-ttu-id="1c333-403">**.NET Core 2.0**</span><span class="sxs-lookup"><span data-stu-id="1c333-403">**.NET Core 2.0**</span></span>

* <span data-ttu-id="1c333-404">.NET Core Runtime 2.0.6 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.6)</span><span class="sxs-lookup"><span data-stu-id="1c333-404">.NET Core Runtime 2.0.6 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.6)</span></span>
* <span data-ttu-id="1c333-405">.NET Core Runtime 2.0.5 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.5)</span><span class="sxs-lookup"><span data-stu-id="1c333-405">.NET Core Runtime 2.0.5 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.5)</span></span>
* <span data-ttu-id="1c333-406">.NET Core SDK 2.1.103 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.103)</span><span class="sxs-lookup"><span data-stu-id="1c333-406">.NET Core SDK 2.1.103 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.103)</span></span>
* <span data-ttu-id="1c333-407">.NET Core SDK 2.0.3 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.0.3)</span><span class="sxs-lookup"><span data-stu-id="1c333-407">.NET Core SDK 2.0.3 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.0.3)</span></span>
 
<span data-ttu-id="1c333-408">**.NET Core 2.1**</span><span class="sxs-lookup"><span data-stu-id="1c333-408">**.NET Core 2.1**</span></span>

>[!IMPORTANT]
> <span data-ttu-id="1c333-409">若要将 .NET Core 2.1 与 Visual Studio 一起使用，需要[安装 Visual Studio 2017 15.7 Preview 1 或更高版本](https://www.visualstudio.com/vs/preview)。</span><span class="sxs-lookup"><span data-stu-id="1c333-409">To use .NET Core 2.1 with Visual Studio, you need to [install Visual Studio 2017 15.7 Preview 1 or newer](https://www.visualstudio.com/vs/preview).</span></span>

* <span data-ttu-id="1c333-410">.NET Core Runtime 2.1.0-preview2 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview2)</span><span class="sxs-lookup"><span data-stu-id="1c333-410">.NET Core Runtime 2.1.0-preview2 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview2)</span></span>
* <span data-ttu-id="1c333-411">.NET Core Runtime 2.1.0-preview1 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview1)</span><span class="sxs-lookup"><span data-stu-id="1c333-411">.NET Core Runtime 2.1.0-preview1  [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview1)</span></span>
* <span data-ttu-id="1c333-412">.NET Core SDK 2.1.300-preview2 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview2)</span><span class="sxs-lookup"><span data-stu-id="1c333-412">.NET Core SDK 2.1.300-preview2 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview2)</span></span>
* <span data-ttu-id="1c333-413">.NET Core SDK 2.1.300-preview1 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview1)</span><span class="sxs-lookup"><span data-stu-id="1c333-413">.NET Core SDK 2.1.300-preview1 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview1)</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1c333-414">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1c333-414">.NET Core 1.x</span></span>](#tab/netcore1x)

1. <span data-ttu-id="1c333-415">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="1c333-415">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="1c333-416">在支持的 SUSE Linux Enterprise Server 和 OpenSUSE 发行版本/版本（64 位）上安装 .NET Core 1.x：</span><span class="sxs-lookup"><span data-stu-id="1c333-416">Install .NET Core 1.x on supported SUSE Linux Enterprise Server and OpenSUSE distributions/versions (64 bit):</span></span>

<span data-ttu-id="1c333-417">**SUSE Linux Enterprise Server 13.2**</span><span class="sxs-lookup"><span data-stu-id="1c333-417">**SUSE Linux Enterprise Server 13.2**</span></span>

* <span data-ttu-id="1c333-418">.NET Core Runtime 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-opensuse-13.2-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-418">.NET Core Runtime 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-opensuse-13.2-x64-binaries)</span></span>
* <span data-ttu-id="1c333-419">.NET Core Runtime 1.1.6 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-opensuse-13.2-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-419">.NET Core Runtime 1.1.6 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-opensuse-13.2-x64-binaries)</span></span>
* <span data-ttu-id="1c333-420">.NET Core SDK 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-opensuse-13.2-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-420">.NET Core SDK 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-opensuse-13.2-x64-binaries)</span></span>

<span data-ttu-id="1c333-421">**openSUSE 24**</span><span class="sxs-lookup"><span data-stu-id="1c333-421">**openSUSE 24**</span></span>

* <span data-ttu-id="1c333-422">.NET Core SDK 1.0.4 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-opensuse-24-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-422">.NET Core SDK 1.0.4 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-opensuse-24-x64-binaries)</span></span>
* <span data-ttu-id="1c333-423">.NET Core SDK 1.0.1 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-opensuse-24-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="1c333-423">.NET Core SDK 1.0.1 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-opensuse-24-x64-binaries)</span></span>

---

> [!IMPORTANT]
> <span data-ttu-id="1c333-424">若对在支持的 Linux 分发/版本上安装 .NET Core 有疑问，请参阅下方你所安装的分发/版本的相应主题：</span><span class="sxs-lookup"><span data-stu-id="1c333-424">If you have problems with a .NET Core installation on a supported Linux distribution/version, consult the following topics for your installed distributions/versions:</span></span>
> * [<span data-ttu-id="1c333-425">.NET Core 2.1 已知问题</span><span class="sxs-lookup"><span data-stu-id="1c333-425">.NET Core 2.1 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.1)
> * [<span data-ttu-id="1c333-426">.NET Core 2.0 已知问题</span><span class="sxs-lookup"><span data-stu-id="1c333-426">.NET Core 2.0 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.0)
> * [<span data-ttu-id="1c333-427">.NET Core 1.1 已知问题</span><span class="sxs-lookup"><span data-stu-id="1c333-427">.NET Core 1.1 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.1)
> * [<span data-ttu-id="1c333-428">.NET Core 1.0 已知问题</span><span class="sxs-lookup"><span data-stu-id="1c333-428">.NET Core 1.0 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0)