---
title: Linux 上 .NET Core 的先决条件
description: 支持的 Linux 版本和 .NET Core 依赖项，用于在 Linux 计算机上开发、部署和运行 .NET Core 应用程序。
author: jralexander
ms.author: johalex
ms.date: 04/19/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 9d986ed56bbc6f803988fde4b5500cd5d5364050
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="062d6-103">Linux 上 .NET Core 的先决条件</span><span class="sxs-lookup"><span data-stu-id="062d6-103">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="062d6-104">本文介绍了在 Linux 上开发 .NET Core 应用程序所需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="062d6-104">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="062d6-105">支持的 Linux 发行版本/版本和依赖项适用于在 Linux 上开发 .NET Core 应用程序的两种方法：</span><span class="sxs-lookup"><span data-stu-id="062d6-105">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="062d6-106">结合使用命令行和常用编辑器</span><span class="sxs-lookup"><span data-stu-id="062d6-106">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="062d6-107">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="062d6-107">Visual Studio Code</span></span>](https://code.visualstudio.com/)

> [!NOTE]
> <span data-ttu-id="062d6-108">生产服务器/环境不需要 .NET Core SDK 包。</span><span class="sxs-lookup"><span data-stu-id="062d6-108">The .NET Core SDK package is not required for production servers/environments.</span></span> <span data-ttu-id="062d6-109">部署到生产环境的应用只需要 .NET Core 运行时包。</span><span class="sxs-lookup"><span data-stu-id="062d6-109">Only the .NET Core runtime package is needed for apps deployed to production environments.</span></span> <span data-ttu-id="062d6-110">.NET Core 运行时与应用一同部署为独立部署的一部分，但是，对于依赖框架的部署应用，它必须单独部署。</span><span class="sxs-lookup"><span data-stu-id="062d6-110">The .NET Core runtime is deployed with apps as part of a self-contained deployment, however, it must be deployed for Framework-dependent deployed apps separately.</span></span> <span data-ttu-id="062d6-111">有关依赖框架和独立部署类型的更多信息，请参阅 [.NET Core 应用程序部署](./deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="062d6-111">For more information about framework-dependent and self-contained deployment types, see [.NET Core application deployment](./deploying/index.md).</span></span> <span data-ttu-id="062d6-112">另请参阅[独立式 Linux 应用程序](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)，了解特定准则。</span><span class="sxs-lookup"><span data-stu-id="062d6-112">Also see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) for specific guidelines.</span></span>

## <a name="supported-linux-versions"></a><span data-ttu-id="062d6-113">支持的 Linux 版本</span><span class="sxs-lookup"><span data-stu-id="062d6-113">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="062d6-114">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="062d6-114">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="062d6-115">.NET Core 2.x 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="062d6-115">.NET Core 2.x treats Linux as a single operating system.</span></span> <span data-ttu-id="062d6-116">支持的 Linux 分发都对应有一个 Linux 内部版本（根据芯片体系结构）。</span><span class="sxs-lookup"><span data-stu-id="062d6-116">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="062d6-117">以下 Linux 64 位（`x86_64` 或 `amd64`）发行版本/版本支持 NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="062d6-117">NET Core 2.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="062d6-118">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="062d6-118">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="062d6-119">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="062d6-119">CentOS 7</span></span>
* <span data-ttu-id="062d6-120">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="062d6-120">Oracle Linux 7</span></span>
* <span data-ttu-id="062d6-121">Fedora 27、26</span><span class="sxs-lookup"><span data-stu-id="062d6-121">Fedora 27, 26</span></span>
* <span data-ttu-id="062d6-122">Debian 9、8.7 或更高版本</span><span class="sxs-lookup"><span data-stu-id="062d6-122">Debian 9, 8.7 or later versions</span></span>
* <span data-ttu-id="062d6-123">Ubuntu 17.10、16.04、14.04</span><span class="sxs-lookup"><span data-stu-id="062d6-123">Ubuntu 17.10, 16.04, 14.04</span></span>
* <span data-ttu-id="062d6-124">Linux Mint 18、17</span><span class="sxs-lookup"><span data-stu-id="062d6-124">Linux Mint 18, 17</span></span>
* <span data-ttu-id="062d6-125">openSUSE 42.3 或更高版本</span><span class="sxs-lookup"><span data-stu-id="062d6-125">openSUSE 42.3 or later versions</span></span>
* <span data-ttu-id="062d6-126">SUSE Enterprise Linux (SLES) 12 Service Pack 2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="062d6-126">SUSE Enterprise Linux (SLES) 12 Service Pack 2 or later</span></span>

<span data-ttu-id="062d6-127">有关 .NET Core 2.x 支持的操作系统、分发和版本、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 2.x - 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="062d6-127">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="062d6-128">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="062d6-128">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="062d6-129">以下 Linux 64 位（`x86_64` 或 `amd64`）发行版本/版本支持 .NET Core 1.x：</span><span class="sxs-lookup"><span data-stu-id="062d6-129">.NET Core 1.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="062d6-130">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="062d6-130">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="062d6-131">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="062d6-131">CentOS 7</span></span>
* <span data-ttu-id="062d6-132">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="062d6-132">Oracle Linux 7</span></span>
* <span data-ttu-id="062d6-133">Fedora 26</span><span class="sxs-lookup"><span data-stu-id="062d6-133">Fedora 26</span></span>
* <span data-ttu-id="062d6-134">Debian 8.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="062d6-134">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="062d6-135">Ubuntu 16.04、14.04</span><span class="sxs-lookup"><span data-stu-id="062d6-135">Ubuntu 16.04, 14.04</span></span>
* <span data-ttu-id="062d6-136">Linux Mint 18、17</span><span class="sxs-lookup"><span data-stu-id="062d6-136">Linux Mint 18, 17</span></span>
* <span data-ttu-id="062d6-137">openSUSE 42.3 或更高版本 (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="062d6-137">openSUSE 42.3 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="062d6-138">有关支持 .NET Core 1.x 的操作系统、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 1.x - 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="062d6-138">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="062d6-139">Linux 发行版本依赖项</span><span class="sxs-lookup"><span data-stu-id="062d6-139">Linux distribution dependencies</span></span>

<span data-ttu-id="062d6-140">以下各项用作示例。</span><span class="sxs-lookup"><span data-stu-id="062d6-140">The following are intended to be examples.</span></span> <span data-ttu-id="062d6-141">确切的版本和名称可能因所选 Linux 发行版本略有不同。</span><span class="sxs-lookup"><span data-stu-id="062d6-141">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="062d6-142">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="062d6-142">Ubuntu</span></span>

<span data-ttu-id="062d6-143">Ubuntu 发行版本需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="062d6-143">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="062d6-144">libunwind8</span><span class="sxs-lookup"><span data-stu-id="062d6-144">libunwind8</span></span>
* <span data-ttu-id="062d6-145">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="062d6-145">liblttng-ust0</span></span>
* <span data-ttu-id="062d6-146">libcurl3</span><span class="sxs-lookup"><span data-stu-id="062d6-146">libcurl3</span></span>
* <span data-ttu-id="062d6-147">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="062d6-147">libssl1.0.0</span></span>
* <span data-ttu-id="062d6-148">libuuid1</span><span class="sxs-lookup"><span data-stu-id="062d6-148">libuuid1</span></span>
* <span data-ttu-id="062d6-149">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="062d6-149">libkrb5-3</span></span>
* <span data-ttu-id="062d6-150">zlib1g</span><span class="sxs-lookup"><span data-stu-id="062d6-150">zlib1g</span></span>
* <span data-ttu-id="062d6-151">libicu52（针对 14.x）</span><span class="sxs-lookup"><span data-stu-id="062d6-151">libicu52 (for 14.x)</span></span>
* <span data-ttu-id="062d6-152">libicu55（针对 16.x）</span><span class="sxs-lookup"><span data-stu-id="062d6-152">libicu55 (for 16.x)</span></span>
* <span data-ttu-id="062d6-153">libicu57（针对 17.x）</span><span class="sxs-lookup"><span data-stu-id="062d6-153">libicu57 (for 17.x)</span></span>

### <a name="centos"></a><span data-ttu-id="062d6-154">CentOS</span><span class="sxs-lookup"><span data-stu-id="062d6-154">CentOS</span></span>

<span data-ttu-id="062d6-155">CentOS 发行版本需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="062d6-155">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="062d6-156">libunwind</span><span class="sxs-lookup"><span data-stu-id="062d6-156">libunwind</span></span>
* <span data-ttu-id="062d6-157">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="062d6-157">lttng-ust</span></span>
* <span data-ttu-id="062d6-158">libcurl</span><span class="sxs-lookup"><span data-stu-id="062d6-158">libcurl</span></span>
* <span data-ttu-id="062d6-159">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="062d6-159">openssl-libs</span></span>
* <span data-ttu-id="062d6-160">libuuid</span><span class="sxs-lookup"><span data-stu-id="062d6-160">libuuid</span></span>
* <span data-ttu-id="062d6-161">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="062d6-161">krb5-libs</span></span>
* <span data-ttu-id="062d6-162">libicu</span><span class="sxs-lookup"><span data-stu-id="062d6-162">libicu</span></span>
* <span data-ttu-id="062d6-163">zlib</span><span class="sxs-lookup"><span data-stu-id="062d6-163">zlib</span></span>

<span data-ttu-id="062d6-164">有关依赖项的详细信息，请参阅[独立式 Linux 应用程序](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="062d6-164">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="062d6-165">使用本机安装程序安装 .NET Core 依赖项</span><span class="sxs-lookup"><span data-stu-id="062d6-165">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="062d6-166">.NET Core 本机安装程序适用于支持的 Linux 发行版本/版本。</span><span class="sxs-lookup"><span data-stu-id="062d6-166">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="062d6-167">本机安装程序需要拥有对服务器的管理员 (sudo) 访问权限。</span><span class="sxs-lookup"><span data-stu-id="062d6-167">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="062d6-168">使用本机安装程序的优势在于，可以安装所有 .NET Core 本机依赖项。</span><span class="sxs-lookup"><span data-stu-id="062d6-168">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="062d6-169">本机安装程序还会在整个系统内安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="062d6-169">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="062d6-170">在 Linux 上，安装程序包有两种使用方式：</span><span class="sxs-lookup"><span data-stu-id="062d6-170">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="062d6-171">使用基于源的包管理器，如适用于 Ubuntu 的 apt-get，或适用于 CentOS/RHEL 的 yum。</span><span class="sxs-lookup"><span data-stu-id="062d6-171">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="062d6-172">使用包本身（DEB 或 RPM）。</span><span class="sxs-lookup"><span data-stu-id="062d6-172">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="062d6-173">使用 .NET Core 安装程序脚本编写安装脚本</span><span class="sxs-lookup"><span data-stu-id="062d6-173">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="062d6-174">[dotnet-install 脚本](./tools/dotnet-install-script.md)用于执行 CLI 工具链和共享运行时的非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="062d6-174">The [dotnet-install scripts](./tools/dotnet-install-script.md) are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="062d6-175">可通过 [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh) 下载脚本。</span><span class="sxs-lookup"><span data-stu-id="062d6-175">You can download the script from [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh).</span></span>

<span data-ttu-id="062d6-176">安装程序 bash 脚本用于自动化方案和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="062d6-176">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="062d6-177">此脚本也读取 PowerShell 开关，因此可以与 Linux/OS X 系统上的脚本结合使用。</span><span class="sxs-lookup"><span data-stu-id="062d6-177">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

## <a name="install-net-core-for-supported-red-hat-enterprise-linux-rhel-versions"></a><span data-ttu-id="062d6-178">为支持的 Red Hat Enterprise Linux (RHEL) 版本安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="062d6-178">Install .NET Core for supported Red Hat Enterprise Linux (RHEL) versions</span></span>

<span data-ttu-id="062d6-179">在支持的 RHEL 版本上安装 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="062d6-179">To install .NET Core on supported RHEL versions:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="062d6-180">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="062d6-180">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="062d6-181">为确保获得最新的安装信息，请遵循适用于支持的 RHEL 版本的 [.NET Core 2.x SDK 和 Runtime 安装程序说明](https://www.microsoft.com/net/download/linux-package-manager/rhel/sdk-current)。</span><span class="sxs-lookup"><span data-stu-id="062d6-181">To ensure you have the latest installation information, follow the [.NET Core 2.x SDK and Runtime Installer instructions](https://www.microsoft.com/net/download/linux-package-manager/rhel/sdk-current) for supported RHEL versions.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="062d6-182">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="062d6-182">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="062d6-183">**.NET Core 1.1**</span><span class="sxs-lookup"><span data-stu-id="062d6-183">**.NET Core 1.1**</span></span>

1. <span data-ttu-id="062d6-184">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="062d6-184">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2.  <span data-ttu-id="062d6-185">有关 Red Hat Enterprise Linux 上最新的 .NET Core 1.1 安装信息，请参阅 [.NET Core 1.1 入门指南](https://access.redhat.com/documentation/en-us/net_core/1.1/html/getting_started_guide/)</span><span class="sxs-lookup"><span data-stu-id="062d6-185">For the latest .NET Core 1.1 on Red Hat Enterprise Linux installation information, see [the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/1.1/html/getting_started_guide/)</span></span>
     
<span data-ttu-id="062d6-186">**.NET Core 1.0**</span><span class="sxs-lookup"><span data-stu-id="062d6-186">**.NET Core 1.0**</span></span>

1. <span data-ttu-id="062d6-187">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="062d6-187">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2.  <span data-ttu-id="062d6-188">有关 Red Hat Enterprise Linux 上最新的 .NET Core 1.0 安装信息，请参阅 [.NET Core 1.0 入门指南](https://access.redhat.com/documentation/en-us/net_core/1.0/html/getting_started_guide/)</span><span class="sxs-lookup"><span data-stu-id="062d6-188">For the latest .NET Core 1.0 on Red Hat Enterprise Linux installation information, see [the .NET Core 1.0 Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/1.0/html/getting_started_guide/)</span></span>

<span data-ttu-id="062d6-189">若要获取 Red Hat .NET 通道访问注册方面的帮助，请参阅 Red Hat 提供的 [.NET Core 1.1 入门指南的第 1 章](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/)。</span><span class="sxs-lookup"><span data-stu-id="062d6-189">For Red Hat .NET channel access registration help, see [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) at Red Hat.</span></span>

---

## <a name="install-net-core-for-supported-ubuntu-and-linux-mint-distributionsversions-64-bit"></a><span data-ttu-id="062d6-190">为支持的 Ubuntu 和 Linux Mint 分发/版本（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="062d6-190">Install .NET Core for supported Ubuntu and Linux Mint distributions/versions (64 bit)</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="062d6-191">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="062d6-191">.NET Core 2.x</span></span>](#tab/netcore2x)

1. <span data-ttu-id="062d6-192">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="062d6-192">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="062d6-193">在支持的 Ubuntu 和 Linux Mint 分发/版本（64 位）上安装 .NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="062d6-193">Install .NET Core 2.x on supported Ubuntu and Linux Mint distributions/versions (64 bit):</span></span>

<span data-ttu-id="062d6-194">**.NET Core 2.0**</span><span class="sxs-lookup"><span data-stu-id="062d6-194">**.NET Core 2.0**</span></span>

|<span data-ttu-id="062d6-195">Runtime / SDK</span><span class="sxs-lookup"><span data-stu-id="062d6-195">Runtimes / SDKs</span></span>          |<span data-ttu-id="062d6-196">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="062d6-196">Ubuntu 17.10</span></span>  |<span data-ttu-id="062d6-197">Ubuntu 16.04 / Linux Mint 18</span><span class="sxs-lookup"><span data-stu-id="062d6-197">Ubuntu 16.04 / Linux Mint 18</span></span>|<span data-ttu-id="062d6-198">Ubuntu 14.04 / Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="062d6-198">Ubuntu 14.04 / Linux Mint 17</span></span>|
|-------------------------|--------------|----------------------------|----------------------------|
|<span data-ttu-id="062d6-199">.NET Core Runtime 2.0.6</span><span class="sxs-lookup"><span data-stu-id="062d6-199">.NET Core Runtime 2.0.6</span></span>  |[<span data-ttu-id="062d6-200">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-200">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.6)|[<span data-ttu-id="062d6-201">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-201">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.6)          |[<span data-ttu-id="062d6-202">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-202">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.6)            |
|<span data-ttu-id="062d6-203">.NET Core Runtime 2.0.5</span><span class="sxs-lookup"><span data-stu-id="062d6-203">.NET Core Runtime 2.0.5</span></span>  |[<span data-ttu-id="062d6-204">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-204">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.5)|[<span data-ttu-id="062d6-205">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-205">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.5)          |[<span data-ttu-id="062d6-206">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-206">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.5)            |
|<span data-ttu-id="062d6-207">.NET Core SDK 2.1.103</span><span class="sxs-lookup"><span data-stu-id="062d6-207">.NET Core SDK 2.1.103</span></span>    |[<span data-ttu-id="062d6-208">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-208">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.103)|[<span data-ttu-id="062d6-209">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-209">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.103)            |[<span data-ttu-id="062d6-210">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-210">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.103)            |
|<span data-ttu-id="062d6-211">.NET Core SDK 2.0.3</span><span class="sxs-lookup"><span data-stu-id="062d6-211">.NET Core SDK 2.0.3</span></span>      |[<span data-ttu-id="062d6-212">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-212">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.0.3)|[<span data-ttu-id="062d6-213">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-213">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.0.3)          |[<span data-ttu-id="062d6-214">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-214">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.0.3)            |

<span data-ttu-id="062d6-215">**.NET Core 2.1**</span><span class="sxs-lookup"><span data-stu-id="062d6-215">**.NET Core 2.1**</span></span>

>[!IMPORTANT]
> <span data-ttu-id="062d6-216">若要将 .NET Core 2.1 与 Visual Studio 一起使用，需要[安装 Visual Studio 2017 15.7 Preview 1 或更高版本](https://www.visualstudio.com/vs/preview)。</span><span class="sxs-lookup"><span data-stu-id="062d6-216">To use .NET Core 2.1 with Visual Studio, you need to [install Visual Studio 2017 15.7 Preview 1 or newer](https://www.visualstudio.com/vs/preview).</span></span>

|<span data-ttu-id="062d6-217">Runtime / SDK</span><span class="sxs-lookup"><span data-stu-id="062d6-217">Runtimes / SDKs</span></span>                  |<span data-ttu-id="062d6-218">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="062d6-218">Ubuntu 17.10</span></span>    |<span data-ttu-id="062d6-219">Ubuntu 16.04 / Linux Mint 18</span><span class="sxs-lookup"><span data-stu-id="062d6-219">Ubuntu 16.04 / Linux Mint 18</span></span>|<span data-ttu-id="062d6-220">Ubuntu 14.04 / Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="062d6-220">Ubuntu 14.04 / Linux Mint 17</span></span>|
|---------------------------------|----------------|----------------------------|----------------------------|
|<span data-ttu-id="062d6-221">.NET Core Runtime 2.1.0-preview2</span><span class="sxs-lookup"><span data-stu-id="062d6-221">.NET Core Runtime 2.1.0-preview2</span></span> |[<span data-ttu-id="062d6-222">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-222">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.0-preview2)|[<span data-ttu-id="062d6-223">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-223">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.0-preview2)            |[<span data-ttu-id="062d6-224">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-224">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.0-preview2)            |
|<span data-ttu-id="062d6-225">.NET Core Runtime 2.1.0-preview1</span><span class="sxs-lookup"><span data-stu-id="062d6-225">.NET Core Runtime 2.1.0-preview1</span></span> |[<span data-ttu-id="062d6-226">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-226">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.0-preview1)|[<span data-ttu-id="062d6-227">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-227">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.0-preview1)            |[<span data-ttu-id="062d6-228">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-228">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.0-preview1)            |
|<span data-ttu-id="062d6-229">.NET Core SDK 2.1.300-preview2</span><span class="sxs-lookup"><span data-stu-id="062d6-229">.NET Core SDK 2.1.300-preview2</span></span>   |[<span data-ttu-id="062d6-230">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-230">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.300-preview2)|[<span data-ttu-id="062d6-231">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-231">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.300-preview2)            |[<span data-ttu-id="062d6-232">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-232">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.300-preview2)
|<span data-ttu-id="062d6-233">.NET Core SDK 2.1.300-preview1</span><span class="sxs-lookup"><span data-stu-id="062d6-233">.NET Core SDK 2.1.300-preview1</span></span>   |[<span data-ttu-id="062d6-234">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-234">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.300-preview1)|[<span data-ttu-id="062d6-235">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-235">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.300-preview1)            |[<span data-ttu-id="062d6-236">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-236">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.300-preview1)            |


# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="062d6-237">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="062d6-237">.NET Core 1.x</span></span>](#tab/netcore1x)

1. <span data-ttu-id="062d6-238">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="062d6-238">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="062d6-239">在支持的 Ubuntu 和 Linux Mint 分发/版本（64 位）上安装 .NET Core 1.x：</span><span class="sxs-lookup"><span data-stu-id="062d6-239">Install .NET Core 1.x on supported Ubuntu and Linux Mint distributions/versions (64 bit):</span></span>

| <span data-ttu-id="062d6-240">Runtime / SDK</span><span class="sxs-lookup"><span data-stu-id="062d6-240">Runtimes / SDKs</span></span>         |<span data-ttu-id="062d6-241">Ubuntu 16.04 / Linux Mint 18</span><span class="sxs-lookup"><span data-stu-id="062d6-241">Ubuntu 16.04 / Linux Mint 18</span></span>|<span data-ttu-id="062d6-242">Ubuntu 14.04 / Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="062d6-242">Ubuntu 14.04 / Linux Mint 17</span></span>|
|-------------------------|----------------------------|----------------------------|
|<span data-ttu-id="062d6-243">.NET Core Runtime 1.1.7</span><span class="sxs-lookup"><span data-stu-id="062d6-243">.NET Core Runtime 1.1.7</span></span>  |[<span data-ttu-id="062d6-244">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-244">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="062d6-245">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-245">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="062d6-246">.NET Core Runtime 1.1.6</span><span class="sxs-lookup"><span data-stu-id="062d6-246">.NET Core Runtime 1.1.6</span></span>  |[<span data-ttu-id="062d6-247">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-247">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="062d6-248">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-248">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="062d6-249">.NET Core Runtime 1.0.10</span><span class="sxs-lookup"><span data-stu-id="062d6-249">.NET Core Runtime 1.0.10</span></span> |[<span data-ttu-id="062d6-250">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-250">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="062d6-251">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-251">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="062d6-252">.NET Core Runtime 1.0.9</span><span class="sxs-lookup"><span data-stu-id="062d6-252">.NET Core Runtime 1.0.9</span></span>  |[<span data-ttu-id="062d6-253">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-253">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="062d6-254">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-254">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="062d6-255">.NET Core SDK 1.1.8</span><span class="sxs-lookup"><span data-stu-id="062d6-255">.NET Core SDK 1.1.8</span></span>      |[<span data-ttu-id="062d6-256">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-256">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="062d6-257">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-257">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="062d6-258">.NET Core SDK 1.1.7</span><span class="sxs-lookup"><span data-stu-id="062d6-258">.NET Core SDK 1.1.7</span></span>      |[<span data-ttu-id="062d6-259">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-259">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="062d6-260">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-260">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="062d6-261">.NET Core SDK 1.0.4</span><span class="sxs-lookup"><span data-stu-id="062d6-261">.NET Core SDK 1.0.4</span></span>      |[<span data-ttu-id="062d6-262">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-262">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="062d6-263">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-263">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="062d6-264">.NET Core SDK 1.0.1</span><span class="sxs-lookup"><span data-stu-id="062d6-264">.NET Core SDK 1.0.1</span></span>      |[<span data-ttu-id="062d6-265">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-265">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="062d6-266">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-266">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-ubuntu-14.04-x64-binaries)            |

---

## <a name="install-net-core-for-supported-debian-versions-64-bit"></a><span data-ttu-id="062d6-267">为支持的 Debian 版本（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="062d6-267">Install .NET Core for supported Debian versions (64 bit)</span></span>

<span data-ttu-id="062d6-268">在支持的 Debian 版本（64 位）上安装 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="062d6-268">To install .NET Core on supported Debian versions (64 bit):</span></span>

> [!NOTE]
> <span data-ttu-id="062d6-269">必须有用户控制目录，才能通过 tar.gz 在 Linux 系统上进行安装。</span><span class="sxs-lookup"><span data-stu-id="062d6-269">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="062d6-270">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="062d6-270">.NET Core 2.x</span></span>](#tab/netcore2x)

1. <span data-ttu-id="062d6-271">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="062d6-271">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="062d6-272">在支持的 Debian 版本（64 位）上安装 .NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="062d6-272">Install .NET Core 2.x on supported Debian versions (64 bit):</span></span>

<span data-ttu-id="062d6-273">**.NET Core 2.0**</span><span class="sxs-lookup"><span data-stu-id="062d6-273">**.NET Core 2.0**</span></span>

|<span data-ttu-id="062d6-274">Runtime / SDK</span><span class="sxs-lookup"><span data-stu-id="062d6-274">Runtimes / SDKs</span></span>          |<span data-ttu-id="062d6-275">Debian 9</span><span class="sxs-lookup"><span data-stu-id="062d6-275">Debian 9</span></span>       |<span data-ttu-id="062d6-276">Debian 8</span><span class="sxs-lookup"><span data-stu-id="062d6-276">Debian 8</span></span>       |
|-------------------------|---------------|---------------|
|<span data-ttu-id="062d6-277">.NET Core Runtime 2.0.6</span><span class="sxs-lookup"><span data-stu-id="062d6-277">.NET Core Runtime 2.0.6</span></span>  |[<span data-ttu-id="062d6-278">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-278">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.6)   |[<span data-ttu-id="062d6-279">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-279">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.6)   |
|<span data-ttu-id="062d6-280">.NET Core Runtime 2.0.5</span><span class="sxs-lookup"><span data-stu-id="062d6-280">.NET Core Runtime 2.0.5</span></span>  |[<span data-ttu-id="062d6-281">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-281">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.5)   |[<span data-ttu-id="062d6-282">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-282">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.5)   |
|<span data-ttu-id="062d6-283">.NET Core SDK 2.1.103</span><span class="sxs-lookup"><span data-stu-id="062d6-283">.NET Core SDK 2.1.103</span></span>    |[<span data-ttu-id="062d6-284">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-284">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.103)   |[<span data-ttu-id="062d6-285">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-285">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.103)   |
|<span data-ttu-id="062d6-286">.NET Core SDK 2.0.3</span><span class="sxs-lookup"><span data-stu-id="062d6-286">.NET Core SDK 2.0.3</span></span>      |[<span data-ttu-id="062d6-287">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-287">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.0.3)   |[<span data-ttu-id="062d6-288">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-288">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.0.3)   |

<span data-ttu-id="062d6-289">**.NET Core 2.1**</span><span class="sxs-lookup"><span data-stu-id="062d6-289">**.NET Core 2.1**</span></span>

>[!IMPORTANT]
> <span data-ttu-id="062d6-290">若要将 .NET Core 2.1 与 Visual Studio 一起使用，需要[安装 Visual Studio 2017 15.7 Preview 1 或更高版本](https://www.visualstudio.com/vs/preview)。</span><span class="sxs-lookup"><span data-stu-id="062d6-290">To use .NET Core 2.1 with Visual Studio, you need to [install Visual Studio 2017 15.7 Preview 1 or newer](https://www.visualstudio.com/vs/preview).</span></span>

|<span data-ttu-id="062d6-291">Runtime / SDK</span><span class="sxs-lookup"><span data-stu-id="062d6-291">Runtimes / SDKs</span></span>                  |<span data-ttu-id="062d6-292">Debian 9</span><span class="sxs-lookup"><span data-stu-id="062d6-292">Debian 9</span></span>       |<span data-ttu-id="062d6-293">Debian 8</span><span class="sxs-lookup"><span data-stu-id="062d6-293">Debian 8</span></span>       |
|---------------------------------|---------------|---------------|
|<span data-ttu-id="062d6-294">.NET Core Runtime 2.1.0-preview2</span><span class="sxs-lookup"><span data-stu-id="062d6-294">.NET Core Runtime 2.1.0-preview2</span></span> |[<span data-ttu-id="062d6-295">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-295">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.0-preview2)   |[<span data-ttu-id="062d6-296">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-296">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.0-preview2)   |
|<span data-ttu-id="062d6-297">.NET Core Runtime 2.1.0-preview1</span><span class="sxs-lookup"><span data-stu-id="062d6-297">.NET Core Runtime 2.1.0-preview1</span></span> |[<span data-ttu-id="062d6-298">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-298">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.0-preview1)   |[<span data-ttu-id="062d6-299">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-299">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.0-preview1)   |
|<span data-ttu-id="062d6-300">.NET Core SDK 2.1.300-preview2</span><span class="sxs-lookup"><span data-stu-id="062d6-300">.NET Core SDK 2.1.300-preview2</span></span>   |[<span data-ttu-id="062d6-301">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-301">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.300-preview2)   |[<span data-ttu-id="062d6-302">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-302">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.300-preview2)   |
|<span data-ttu-id="062d6-303">.NET Core SDK 2.1.300-preview1</span><span class="sxs-lookup"><span data-stu-id="062d6-303">.NET Core SDK 2.1.300-preview1</span></span>   |[<span data-ttu-id="062d6-304">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-304">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.300-preview1)   |[<span data-ttu-id="062d6-305">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-305">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.300-preview1)   |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="062d6-306">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="062d6-306">.NET Core 1.x</span></span>](#tab/netcore1x)

1. <span data-ttu-id="062d6-307">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="062d6-307">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="062d6-308">在 Debian 9 或 Debian 8 上安装 .NET Core 1.x：</span><span class="sxs-lookup"><span data-stu-id="062d6-308">Install .NET Core 1.x on Debian 9 or Debian 8:</span></span>

* <span data-ttu-id="062d6-309">.NET Core Runtime 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-309">.NET Core Runtime 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="062d6-310">.NET Core Runtime 1.1.6 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-310">.NET Core Runtime 1.1.6 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="062d6-311">.NET Core Runtime 1.0.10 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-311">.NET Core Runtime 1.0.10 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="062d6-312">.NET Core Runtime 1.0.9 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-312">.NET Core Runtime 1.0.9 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="062d6-313">.NET Core SDK 1.1.8 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-313">.NET Core SDK 1.1.8 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="062d6-314">.NET Core SDK 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-314">.NET Core SDK 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="062d6-315">.NET Core SDK 1.0.4 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-315">.NET Core SDK 1.0.4 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="062d6-316">.NET Core SDK 1.0.1 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-316">.NET Core SDK 1.0.1 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)</span></span>

---

## <a name="install-net-core-for-supported-fedora-versions-64-bit"></a><span data-ttu-id="062d6-317">为支持的 Fedora 版本（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="062d6-317">Install .NET Core for supported Fedora versions (64 bit)</span></span>

<span data-ttu-id="062d6-318">在支持的 Fedora 版本上安装 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="062d6-318">To install .NET Core on supported Fedora versions:</span></span>

> [!NOTE]
> <span data-ttu-id="062d6-319">必须有用户控制目录，才能通过 tar.gz 在 Linux 系统上进行安装。</span><span class="sxs-lookup"><span data-stu-id="062d6-319">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="062d6-320">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="062d6-320">.NET Core 2.x</span></span>](#tab/netcore2x)

1. <span data-ttu-id="062d6-321">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="062d6-321">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="062d6-322">在支持的 Fedora 版本（64 位）上安装 .NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="062d6-322">Install .NET Core 2.x on supported Fedora versions (64 bit):</span></span>

<span data-ttu-id="062d6-323">**.NET Core 2.0**</span><span class="sxs-lookup"><span data-stu-id="062d6-323">**.NET Core 2.0**</span></span>

|<span data-ttu-id="062d6-324">Runtime / SDK</span><span class="sxs-lookup"><span data-stu-id="062d6-324">Runtimes / SDKs</span></span>          |<span data-ttu-id="062d6-325">Fedora 26 或更高版本</span><span class="sxs-lookup"><span data-stu-id="062d6-325">Fedora 26 or later</span></span> |<span data-ttu-id="062d6-326">Fedora 25 或以前版本</span><span class="sxs-lookup"><span data-stu-id="062d6-326">Fedora 25 or previous</span></span> |
|-------------------------|-------------------|----------------------|
|<span data-ttu-id="062d6-327">.NET Core Runtime 2.0.6</span><span class="sxs-lookup"><span data-stu-id="062d6-327">.NET Core Runtime 2.0.6</span></span>  |[<span data-ttu-id="062d6-328">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-328">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.6)       |[<span data-ttu-id="062d6-329">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-329">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.6)           |
|<span data-ttu-id="062d6-330">.NET Core Runtime 2.0.5</span><span class="sxs-lookup"><span data-stu-id="062d6-330">.NET Core Runtime 2.0.5</span></span>  |[<span data-ttu-id="062d6-331">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-331">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.5)       |[<span data-ttu-id="062d6-332">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-332">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.5)           |
|<span data-ttu-id="062d6-333">.NET Core SDK 2.1.103</span><span class="sxs-lookup"><span data-stu-id="062d6-333">.NET Core SDK 2.1.103</span></span>    |[<span data-ttu-id="062d6-334">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-334">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.103)       |[<span data-ttu-id="062d6-335">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-335">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.103)           |
|<span data-ttu-id="062d6-336">.NET Core SDK 2.0.3</span><span class="sxs-lookup"><span data-stu-id="062d6-336">.NET Core SDK 2.0.3</span></span>      |[<span data-ttu-id="062d6-337">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-337">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.0.3)       |[<span data-ttu-id="062d6-338">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-338">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.0.3)           |

<span data-ttu-id="062d6-339">**.NET Core 2.1**</span><span class="sxs-lookup"><span data-stu-id="062d6-339">**.NET Core 2.1**</span></span>

>[!IMPORTANT]
> <span data-ttu-id="062d6-340">若要将 .NET Core 2.1 与 Visual Studio 一起使用，需要[安装 Visual Studio 2017 15.7 Preview 1 或更高版本](https://www.visualstudio.com/vs/preview)。</span><span class="sxs-lookup"><span data-stu-id="062d6-340">To use .NET Core 2.1 with Visual Studio, you need to [install Visual Studio 2017 15.7 Preview 1 or newer](https://www.visualstudio.com/vs/preview).</span></span>

|<span data-ttu-id="062d6-341">Runtime / SDK</span><span class="sxs-lookup"><span data-stu-id="062d6-341">Runtimes / SDKs</span></span>                  |<span data-ttu-id="062d6-342">Fedora 26 或更高版本</span><span class="sxs-lookup"><span data-stu-id="062d6-342">Fedora 26 or later</span></span> |<span data-ttu-id="062d6-343">Fedora 25 或以前版本</span><span class="sxs-lookup"><span data-stu-id="062d6-343">Fedora 25 or previous</span></span> |
|---------------------------------|-------------------|----------------------|
|<span data-ttu-id="062d6-344">.NET Core Runtime 2.1.0-preview2</span><span class="sxs-lookup"><span data-stu-id="062d6-344">.NET Core Runtime 2.1.0-preview2</span></span> |[<span data-ttu-id="062d6-345">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-345">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.1.0-preview2)       |[<span data-ttu-id="062d6-346">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-346">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.1.0-preview2)           |
|<span data-ttu-id="062d6-347">.NET Core Runtime 2.1.0-preview1</span><span class="sxs-lookup"><span data-stu-id="062d6-347">.NET Core Runtime 2.1.0-preview1</span></span> |[<span data-ttu-id="062d6-348">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-348">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.1.0-preview1)       |[<span data-ttu-id="062d6-349">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-349">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.1.0-preview1)           |
|<span data-ttu-id="062d6-350">.NET Core SDK 2.1.300-preview2</span><span class="sxs-lookup"><span data-stu-id="062d6-350">.NET Core SDK 2.1.300-preview2</span></span>   |[<span data-ttu-id="062d6-351">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-351">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.300-preview2)       |[<span data-ttu-id="062d6-352">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-352">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.300-preview2)           |
|<span data-ttu-id="062d6-353">.NET Core SDK 2.1.300-preview1</span><span class="sxs-lookup"><span data-stu-id="062d6-353">.NET Core SDK 2.1.300-preview1</span></span>   |[<span data-ttu-id="062d6-354">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-354">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.300-preview1)       |[<span data-ttu-id="062d6-355">安装链接</span><span class="sxs-lookup"><span data-stu-id="062d6-355">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.300-preview1)           |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="062d6-356">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="062d6-356">.NET Core 1.x</span></span>](#tab/netcore1x)

1. <span data-ttu-id="062d6-357">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="062d6-357">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="062d6-358">在支持的 Fedora 版本（64 位）上安装 .NET Core 1.x：</span><span class="sxs-lookup"><span data-stu-id="062d6-358">Install .NET Core 1.x supported Fedora versions (64 bit):</span></span>

<span data-ttu-id="062d6-359">**Fedora 24**</span><span class="sxs-lookup"><span data-stu-id="062d6-359">**Fedora 24**</span></span>

* <span data-ttu-id="062d6-360">.NET Core Runtime 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-fedora-24-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-360">.NET Core Runtime 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-fedora-24-x64-binaries)</span></span>
* <span data-ttu-id="062d6-361">.NET Core Runtime 1.1.6 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-fedora-24-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-361">.NET Core Runtime 1.1.6 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-fedora-24-x64-binaries)</span></span>
* <span data-ttu-id="062d6-362">.NET Core SDK 1.1.8 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-fedora-24-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-362">.NET Core SDK 1.1.8 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-fedora-24-x64-binaries)</span></span>
* <span data-ttu-id="062d6-363">.NET Core SDK 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-fedora-24-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-363">.NET Core SDK 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-fedora-24-x64-binaries)</span></span>
* <span data-ttu-id="062d6-364">.NET Core SDK 1.0.1 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-364">.NET Core SDK 1.0.1 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)</span></span>

<span data-ttu-id="062d6-365">**Fedora 23**</span><span class="sxs-lookup"><span data-stu-id="062d6-365">**Fedora 23**</span></span>

* <span data-ttu-id="062d6-366">.NET Core Runtime 1.0.9 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-fedora-23-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-366">.NET Core Runtime 1.0.9 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-fedora-23-x64-binaries)</span></span>
* <span data-ttu-id="062d6-367">.NET Core SDK 1.0.4 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-fedora-23-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-367">.NET Core SDK 1.0.4 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-fedora-23-x64-binaries)</span></span>
* <span data-ttu-id="062d6-368">.NET Core SDK 1.0.1 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-fedora-23-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-368">.NET Core SDK 1.0.1 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-fedora-23-x64-binaries)</span></span>

---

## <a name="install-net-core-for-supported-centos-and-oracle-linux-distributionsversions-64-bit"></a><span data-ttu-id="062d6-369">为支持的 CentOS 和 Oracle Linux 分发/版本（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="062d6-369">Install .NET Core for supported CentOS and Oracle Linux distributions/versions (64 bit)</span></span>

<span data-ttu-id="062d6-370">为支持的 CentOS 和 Oracle Linux 分发/版本（64 位）安装 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="062d6-370">To install .NET Core for supported CentOS and Oracle Linux distributions/versions (64 bit):</span></span>

> [!NOTE]
> <span data-ttu-id="062d6-371">必须有用户控制目录，才能通过 tar.gz 在 Linux 系统上进行安装。</span><span class="sxs-lookup"><span data-stu-id="062d6-371">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="062d6-372">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="062d6-372">.NET Core 2.x</span></span>](#tab/netcore2x)

1. <span data-ttu-id="062d6-373">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="062d6-373">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="062d6-374">在支持的 CentOS 和 Oracle Linux 分发/版本（64 位）上安装 .NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="062d6-374">Install .NET Core 2.x on supported CentOS and Oracle Linux distributions/versions (64 bit):</span></span>

<span data-ttu-id="062d6-375">**.NET Core 2.0**</span><span class="sxs-lookup"><span data-stu-id="062d6-375">**.NET Core 2.0**</span></span>

* <span data-ttu-id="062d6-376">.NET Core Runtime 2.0.6 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.6)</span><span class="sxs-lookup"><span data-stu-id="062d6-376">.NET Core Runtime 2.0.6 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.6)</span></span>
* <span data-ttu-id="062d6-377">.NET Core Runtime 2.0.5 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.5)</span><span class="sxs-lookup"><span data-stu-id="062d6-377">.NET Core Runtime 2.0.5 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.5)</span></span>
* <span data-ttu-id="062d6-378">.NET Core SDK 2.1.103 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.103)</span><span class="sxs-lookup"><span data-stu-id="062d6-378">.NET Core SDK 2.1.103 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.103)</span></span>
* <span data-ttu-id="062d6-379">.NET Core SDK 2.0.3 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.0.3)</span><span class="sxs-lookup"><span data-stu-id="062d6-379">.NET Core SDK 2.0.3 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.0.3)</span></span>
 
<span data-ttu-id="062d6-380">**.NET Core 2.1**</span><span class="sxs-lookup"><span data-stu-id="062d6-380">**.NET Core 2.1**</span></span>

>[!IMPORTANT]
> <span data-ttu-id="062d6-381">若要将 .NET Core 2.1 与 Visual Studio 一起使用，需要[安装 Visual Studio 2017 15.7 Preview 1 或更高版本](https://www.visualstudio.com/vs/preview/)。</span><span class="sxs-lookup"><span data-stu-id="062d6-381">To use .NET Core 2.1 with Visual Studio, you need to [install Visual Studio 2017 15.7 Preview 1 or newer](https://www.visualstudio.com/vs/preview/).</span></span>

* <span data-ttu-id="062d6-382">.NET Core Runtime 2.1.0-preview2 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview2)</span><span class="sxs-lookup"><span data-stu-id="062d6-382">.NET Core Runtime 2.1.0-preview2 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview2)</span></span>
* <span data-ttu-id="062d6-383">.NET Core Runtime 2.1.0-preview1 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview1)</span><span class="sxs-lookup"><span data-stu-id="062d6-383">.NET Core Runtime 2.1.0-preview1 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview1)</span></span>
* <span data-ttu-id="062d6-384">.NET Core SDK 2.1.300-preview2 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview2)</span><span class="sxs-lookup"><span data-stu-id="062d6-384">.NET Core SDK 2.1.300-preview2 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview2)</span></span>
* <span data-ttu-id="062d6-385">.NET Core SDK 2.1.300-preview1 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview1)</span><span class="sxs-lookup"><span data-stu-id="062d6-385">.NET Core SDK 2.1.300-preview1 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview1)</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="062d6-386">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="062d6-386">.NET Core 1.x</span></span>](#tab/netcore1x)

1. <span data-ttu-id="062d6-387">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="062d6-387">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="062d6-388">在支持的 CentOS 和 Oracle Linux 发行版本/版本（64 位）上安装 .NET Core 1.x：</span><span class="sxs-lookup"><span data-stu-id="062d6-388">Install .NET Core 1.x on supported CentOS and Oracle Linux distributions/versions (64 bit):</span></span>

* <span data-ttu-id="062d6-389">.NET Core Runtime 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-389">.NET Core Runtime 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="062d6-390">.NET Core Runtime 1.1.6 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-390">.NET Core Runtime 1.1.6 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="062d6-391">.NET Core Runtime 1.0.10 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-391">.NET Core Runtime 1.0.10 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="062d6-392">.NET Core Runtime 1.0.9 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-392">.NET Core Runtime 1.0.9 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="062d6-393">.NET Core SDK 1.1.8 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-393">.NET Core SDK 1.1.8 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="062d6-394">.NET Core SDK 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-394">.NET Core SDK 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="062d6-395">.NET Core SDK 1.0.4 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-395">.NET Core SDK 1.0.4 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="062d6-396">.NET Core SDK 1.0.1 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-396">.NET Core SDK 1.0.1 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-centos-x64-binaries)</span></span>

---

## <a name="install-net-core-for-supported-suse-linux-enterprise-server-and-opensuse-distributionsversions-64-bit"></a><span data-ttu-id="062d6-397">为支持的 SUSE Linux Enterprise Server 和 OpenSUSE 发行版本/版本（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="062d6-397">Install .NET Core for supported SUSE Linux Enterprise Server and OpenSUSE distributions/versions (64 bit)</span></span>

<span data-ttu-id="062d6-398">为支持的 SUSE Linux Enterprise Server 和 OpenSUSE 发行版本/版本（64 位）安装 .NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="062d6-398">To install .NET Core 2.x for supported SUSE Linux Enterprise Server and OpenSUSE distributions/versions (64 bit):</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="062d6-399">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="062d6-399">.NET Core 2.x</span></span>](#tab/netcore2x)

1. <span data-ttu-id="062d6-400">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="062d6-400">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="062d6-401">在支持的 SUSE Linux Enterprise Server 和 OpenSUSE 发行版本/版本（64 位）上安装 .NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="062d6-401">Install .NET Core 2.x on supported SUSE Linux Enterprise Server and OpenSUSE distributions/versions (64 bit):</span></span>

<span data-ttu-id="062d6-402">**.NET Core 2.0**</span><span class="sxs-lookup"><span data-stu-id="062d6-402">**.NET Core 2.0**</span></span>

* <span data-ttu-id="062d6-403">.NET Core Runtime 2.0.6 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.6)</span><span class="sxs-lookup"><span data-stu-id="062d6-403">.NET Core Runtime 2.0.6 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.6)</span></span>
* <span data-ttu-id="062d6-404">.NET Core Runtime 2.0.5 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.5)</span><span class="sxs-lookup"><span data-stu-id="062d6-404">.NET Core Runtime 2.0.5 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.5)</span></span>
* <span data-ttu-id="062d6-405">.NET Core SDK 2.1.103 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.103)</span><span class="sxs-lookup"><span data-stu-id="062d6-405">.NET Core SDK 2.1.103 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.103)</span></span>
* <span data-ttu-id="062d6-406">.NET Core SDK 2.0.3 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.0.3)</span><span class="sxs-lookup"><span data-stu-id="062d6-406">.NET Core SDK 2.0.3 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.0.3)</span></span>
 
<span data-ttu-id="062d6-407">**.NET Core 2.1**</span><span class="sxs-lookup"><span data-stu-id="062d6-407">**.NET Core 2.1**</span></span>

>[!IMPORTANT]
> <span data-ttu-id="062d6-408">若要将 .NET Core 2.1 与 Visual Studio 一起使用，需要[安装 Visual Studio 2017 15.7 Preview 1 或更高版本](https://www.visualstudio.com/vs/preview)。</span><span class="sxs-lookup"><span data-stu-id="062d6-408">To use .NET Core 2.1 with Visual Studio, you need to [install Visual Studio 2017 15.7 Preview 1 or newer](https://www.visualstudio.com/vs/preview).</span></span>

* <span data-ttu-id="062d6-409">.NET Core Runtime 2.1.0-preview2 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview2)</span><span class="sxs-lookup"><span data-stu-id="062d6-409">.NET Core Runtime 2.1.0-preview2 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview2)</span></span>
* <span data-ttu-id="062d6-410">.NET Core Runtime 2.1.0-preview1 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview1)</span><span class="sxs-lookup"><span data-stu-id="062d6-410">.NET Core Runtime 2.1.0-preview1  [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview1)</span></span>
* <span data-ttu-id="062d6-411">.NET Core SDK 2.1.300-preview2 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview2)</span><span class="sxs-lookup"><span data-stu-id="062d6-411">.NET Core SDK 2.1.300-preview2 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview2)</span></span>
* <span data-ttu-id="062d6-412">.NET Core SDK 2.1.300-preview1 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview1)</span><span class="sxs-lookup"><span data-stu-id="062d6-412">.NET Core SDK 2.1.300-preview1 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview1)</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="062d6-413">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="062d6-413">.NET Core 1.x</span></span>](#tab/netcore1x)

1. <span data-ttu-id="062d6-414">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="062d6-414">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="062d6-415">在支持的 SUSE Linux Enterprise Server 和 OpenSUSE 发行版本/版本（64 位）上安装 .NET Core 1.x：</span><span class="sxs-lookup"><span data-stu-id="062d6-415">Install .NET Core 1.x on supported SUSE Linux Enterprise Server and OpenSUSE distributions/versions (64 bit):</span></span>

<span data-ttu-id="062d6-416">**SUSE Linux Enterprise Server 13.2**</span><span class="sxs-lookup"><span data-stu-id="062d6-416">**SUSE Linux Enterprise Server 13.2**</span></span>

* <span data-ttu-id="062d6-417">.NET Core Runtime 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-opensuse-13.2-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-417">.NET Core Runtime 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-opensuse-13.2-x64-binaries)</span></span>
* <span data-ttu-id="062d6-418">.NET Core Runtime 1.1.6 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-opensuse-13.2-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-418">.NET Core Runtime 1.1.6 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-opensuse-13.2-x64-binaries)</span></span>
* <span data-ttu-id="062d6-419">.NET Core SDK 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-opensuse-13.2-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-419">.NET Core SDK 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-opensuse-13.2-x64-binaries)</span></span>

<span data-ttu-id="062d6-420">**openSUSE 24**</span><span class="sxs-lookup"><span data-stu-id="062d6-420">**openSUSE 24**</span></span>

* <span data-ttu-id="062d6-421">.NET Core SDK 1.0.4 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-opensuse-24-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-421">.NET Core SDK 1.0.4 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-opensuse-24-x64-binaries)</span></span>
* <span data-ttu-id="062d6-422">.NET Core SDK 1.0.1 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-opensuse-24-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="062d6-422">.NET Core SDK 1.0.1 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-opensuse-24-x64-binaries)</span></span>

---

> [!IMPORTANT]
> <span data-ttu-id="062d6-423">若对在支持的 Linux 分发/版本上安装 .NET Core 有疑问，请参阅下方你所安装的分发/版本的相应主题：</span><span class="sxs-lookup"><span data-stu-id="062d6-423">If you have problems with a .NET Core installation on a supported Linux distribution/version, consult the following topics for your installed distributions/versions:</span></span>
> * [<span data-ttu-id="062d6-424">.NET Core 2.1 已知问题</span><span class="sxs-lookup"><span data-stu-id="062d6-424">.NET Core 2.1 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.1)
> * [<span data-ttu-id="062d6-425">.NET Core 2.0 已知问题</span><span class="sxs-lookup"><span data-stu-id="062d6-425">.NET Core 2.0 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.0)
> * [<span data-ttu-id="062d6-426">.NET Core 1.1 已知问题</span><span class="sxs-lookup"><span data-stu-id="062d6-426">.NET Core 1.1 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.1)
> * [<span data-ttu-id="062d6-427">.NET Core 1.0 已知问题</span><span class="sxs-lookup"><span data-stu-id="062d6-427">.NET Core 1.0 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0)