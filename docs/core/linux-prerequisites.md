---
title: "Linux 上 .NET Core 的先决条件"
description: "支持的 Linux 版本和 .NET Core 依赖项，用于在 Linux 计算机上开发、部署和运行 .NET Core 应用程序。"
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS,
author: jralexander
ms.author: johalex
ms.date: 09/01/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 7bbb8405f39a52d2798fd1dbc78f3116cb3bedbb
ms.openlocfilehash: 9864ffa31caa007cb649a9e6e8913863d9cb2c35
ms.contentlocale: zh-cn
ms.lasthandoff: 09/05/2017

---

# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="aab3d-104">Linux 上 .NET Core 的先决条件</span><span class="sxs-lookup"><span data-stu-id="aab3d-104">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="aab3d-105">本文介绍了在 Linux 上开发 .NET Core 应用程序所需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="aab3d-105">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="aab3d-106">支持的 Linux 发行版本/版本和依赖项适用于在 Linux 上开发 .NET Core 应用程序的两种方法：</span><span class="sxs-lookup"><span data-stu-id="aab3d-106">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="aab3d-107">结合使用命令行和常用编辑器</span><span class="sxs-lookup"><span data-stu-id="aab3d-107">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="aab3d-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="aab3d-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a><span data-ttu-id="aab3d-109">支持的 Linux 版本</span><span class="sxs-lookup"><span data-stu-id="aab3d-109">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="aab3d-110">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="aab3d-110">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="aab3d-111">.NET Core 2.0 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="aab3d-111">.NET Core 2.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="aab3d-112">支持的 Linux 发行版本都对应有一个 Linux 版本（每芯片体系结构）。</span><span class="sxs-lookup"><span data-stu-id="aab3d-112">There is a single Linux build (per chip architecture) for supported Linux distros.</span></span>

<span data-ttu-id="aab3d-113">以下 Linux x64 发行版本/版本支持 NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="aab3d-113">NET Core 2.x is supported on the following Linux x64 distributions/versions:</span></span>

 * <span data-ttu-id="aab3d-114">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="aab3d-114">Red Hat Enterprise Linux 7</span></span>
 * <span data-ttu-id="aab3d-115">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="aab3d-115">CentOS 7</span></span>
 * <span data-ttu-id="aab3d-116">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="aab3d-116">Oracle Linux 7</span></span>
 * <span data-ttu-id="aab3d-117">Fedora 25、Fedora 26</span><span class="sxs-lookup"><span data-stu-id="aab3d-117">Fedora 25, Fedora 26</span></span>
 * <span data-ttu-id="aab3d-118">Debian 8.7 或更高版本</span><span class="sxs-lookup"><span data-stu-id="aab3d-118">Debian 8.7 or later versions</span></span> 
 * <span data-ttu-id="aab3d-119">Ubuntu 17.04、Ubuntu 16.04、Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="aab3d-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span></span>
 * <span data-ttu-id="aab3d-120">Linux Mint 18、Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="aab3d-120">Linux Mint 18, Linux Mint 17</span></span>
 * <span data-ttu-id="aab3d-121">openSUSE 42.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="aab3d-121">openSUSE 42.2 or later versions</span></span>
 * <span data-ttu-id="aab3d-122">SUSE Enterprise Linux (SLES) 12 SP2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="aab3d-122">SUSE Enterprise Linux (SLES) 12 SP2 or later versions</span></span>

<span data-ttu-id="aab3d-123">有关支持 .NET Core 2.x 的操作系统、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 2.x - 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="aab3d-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="aab3d-124">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="aab3d-124">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="aab3d-125">以下 Linux x64 发行版本/版本支持 .NET Core 1.x：</span><span class="sxs-lookup"><span data-stu-id="aab3d-125">.NET Core 1.x is supported on the following Linux x64 distributions/versions:</span></span>

* <span data-ttu-id="aab3d-126">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="aab3d-126">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="aab3d-127">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="aab3d-127">CentOS 7</span></span>
* <span data-ttu-id="aab3d-128">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="aab3d-128">Oracle Linux 7</span></span>
* <span data-ttu-id="aab3d-129">Fedora 24</span><span class="sxs-lookup"><span data-stu-id="aab3d-129">Fedora 24</span></span>
* <span data-ttu-id="aab3d-130">Debian 8.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="aab3d-130">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="aab3d-131">Ubuntu 14.04、Ubuntu 16.04、Ubuntu 16.10\*</span><span class="sxs-lookup"><span data-stu-id="aab3d-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span></span>
 * <span data-ttu-id="aab3d-132">最新修补版 .NET Core 1.1 支持 Ubuntu 16.10</span><span class="sxs-lookup"><span data-stu-id="aab3d-132">Ubuntu 16.10 is supported by the latest patch release of .NET Core 1.1</span></span>
* <span data-ttu-id="aab3d-133">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="aab3d-133">Linux Mint 17</span></span>
* <span data-ttu-id="aab3d-134">openSUSE 42.1 或更高版本 (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="aab3d-134">openSUSE 42.1 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="aab3d-135">有关支持 .NET Core 1.x 的操作系统、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 1.x - 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="aab3d-135">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="aab3d-136">Linux 发行版本依赖项</span><span class="sxs-lookup"><span data-stu-id="aab3d-136">Linux distribution dependencies</span></span>

### <a name="ubuntu"></a><span data-ttu-id="aab3d-137">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="aab3d-137">Ubuntu</span></span>

<span data-ttu-id="aab3d-138">Ubuntu 发行版本需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="aab3d-138">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="aab3d-139">libunwind8</span><span class="sxs-lookup"><span data-stu-id="aab3d-139">libunwind8</span></span>
* <span data-ttu-id="aab3d-140">libunwind8-dev</span><span class="sxs-lookup"><span data-stu-id="aab3d-140">libunwind8-dev</span></span>
* <span data-ttu-id="aab3d-141">gettext</span><span class="sxs-lookup"><span data-stu-id="aab3d-141">gettext</span></span>
* <span data-ttu-id="aab3d-142">libicu-dev</span><span class="sxs-lookup"><span data-stu-id="aab3d-142">libicu-dev</span></span>
* <span data-ttu-id="aab3d-143">liblttng-ust-dev</span><span class="sxs-lookup"><span data-stu-id="aab3d-143">liblttng-ust-dev</span></span>
* <span data-ttu-id="aab3d-144">libcurl4-openssl-dev</span><span class="sxs-lookup"><span data-stu-id="aab3d-144">libcurl4-openssl-dev</span></span>
* <span data-ttu-id="aab3d-145">libssl-dev</span><span class="sxs-lookup"><span data-stu-id="aab3d-145">libssl-dev</span></span>
* <span data-ttu-id="aab3d-146">uuid-dev</span><span class="sxs-lookup"><span data-stu-id="aab3d-146">uuid-dev</span></span>
* <span data-ttu-id="aab3d-147">unzip</span><span class="sxs-lookup"><span data-stu-id="aab3d-147">unzip</span></span>

### <a name="centos"></a><span data-ttu-id="aab3d-148">CentOS</span><span class="sxs-lookup"><span data-stu-id="aab3d-148">CentOS</span></span>

<span data-ttu-id="aab3d-149">CentOS 发行版本需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="aab3d-149">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="aab3d-150">deltarpm</span><span class="sxs-lookup"><span data-stu-id="aab3d-150">deltarpm</span></span>
* <span data-ttu-id="aab3d-151">epel-release</span><span class="sxs-lookup"><span data-stu-id="aab3d-151">epel-release</span></span>
* <span data-ttu-id="aab3d-152">unzip</span><span class="sxs-lookup"><span data-stu-id="aab3d-152">unzip</span></span>
* <span data-ttu-id="aab3d-153">libunwind</span><span class="sxs-lookup"><span data-stu-id="aab3d-153">libunwind</span></span>
* <span data-ttu-id="aab3d-154">gettext</span><span class="sxs-lookup"><span data-stu-id="aab3d-154">gettext</span></span>
* <span data-ttu-id="aab3d-155">libcurl-devel</span><span class="sxs-lookup"><span data-stu-id="aab3d-155">libcurl-devel</span></span>
* <span data-ttu-id="aab3d-156">openssl-devel</span><span class="sxs-lookup"><span data-stu-id="aab3d-156">openssl-devel</span></span>
* <span data-ttu-id="aab3d-157">zlib</span><span class="sxs-lookup"><span data-stu-id="aab3d-157">zlib</span></span>
* <span data-ttu-id="aab3d-158">libicu-devel</span><span class="sxs-lookup"><span data-stu-id="aab3d-158">libicu-devel</span></span>

<span data-ttu-id="aab3d-159">有关依赖项的详细信息，请参阅[独立式 Linux 应用程序](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="aab3d-159">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="aab3d-160">使用本机安装程序安装 .NET Core 依赖项</span><span class="sxs-lookup"><span data-stu-id="aab3d-160">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="aab3d-161">.NET Core 本机安装程序适用于支持的 Linux 发行版本/版本。</span><span class="sxs-lookup"><span data-stu-id="aab3d-161">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="aab3d-162">本机安装程序需要拥有对服务器的管理员 (sudo) 访问权限。</span><span class="sxs-lookup"><span data-stu-id="aab3d-162">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="aab3d-163">使用本机安装程序的优势在于，可以安装所有 .NET Core 本机依赖项。</span><span class="sxs-lookup"><span data-stu-id="aab3d-163">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="aab3d-164">本机安装程序还会在整个系统内安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="aab3d-164">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="aab3d-165">在 Linux 上，安装程序包有两种使用方式：</span><span class="sxs-lookup"><span data-stu-id="aab3d-165">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="aab3d-166">使用基于源的包管理器，如适用于 Ubuntu 的 apt-get，或适用于 CentOS/RHEL 的 yum。</span><span class="sxs-lookup"><span data-stu-id="aab3d-166">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="aab3d-167">使用包本身（DEB 或 RPM）。</span><span class="sxs-lookup"><span data-stu-id="aab3d-167">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="aab3d-168">使用 .NET Core 安装程序脚本编写安装脚本</span><span class="sxs-lookup"><span data-stu-id="aab3d-168">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="aab3d-169">`dotnet-install` 脚本用于执行 CLI 工具链和共享运行时的非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="aab3d-169">The `dotnet-install` scripts are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="aab3d-170">可以从 [CLI GitHub 存储库](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain)下载脚本。</span><span class="sxs-lookup"><span data-stu-id="aab3d-170">You can download the scripts from the [CLI GitHub repo](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain).</span></span>

<span data-ttu-id="aab3d-171">安装程序 bash 脚本用于自动化方案和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="aab3d-171">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="aab3d-172">此脚本也读取 PowerShell 开关，因此可以与 Linux/OS X 系统上的脚本结合使用。</span><span class="sxs-lookup"><span data-stu-id="aab3d-172">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aab3d-173">运行脚本前，请安装所需的[依赖项](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)。</span><span class="sxs-lookup"><span data-stu-id="aab3d-173">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="aab3d-174">为 Red Hat Enterprise Linux (RHEL) 7 安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="aab3d-174">Install .NET Core for Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="aab3d-175">在 RHEL 7 上安装 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="aab3d-175">To install .NET Core on RHEL 7:</span></span>

1. <span data-ttu-id="aab3d-176">启用 Red Hat .NET 通道（在 RHEL 7 订阅下）。</span><span class="sxs-lookup"><span data-stu-id="aab3d-176">Enable the Red Hat .NET channel, available under your RHEL 7 subscription.</span></span>
    * <span data-ttu-id="aab3d-177">对于 Red Hat Enterprise 7 服务器，请使用：</span><span class="sxs-lookup"><span data-stu-id="aab3d-177">For Red Hat Enterprise 7 Server, use:</span></span>
    
         ```bash
         subscription-manager repos --enable=rhel-7-server-dotnet-rpms
         ```
    
    * <span data-ttu-id="aab3d-178">对于 Red Hat Enterprise 7 工作站，请使用：</span><span class="sxs-lookup"><span data-stu-id="aab3d-178">For Red Hat Enterprise 7 Workstation, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
         ```
    
    * <span data-ttu-id="aab3d-179">对于 Red Hat Enterprise 7 HPC 计算节点，请使用：</span><span class="sxs-lookup"><span data-stu-id="aab3d-179">For Red Hat Enterprise 7 HPC Compute Node, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. <span data-ttu-id="aab3d-180">安装 scl 工具。</span><span class="sxs-lookup"><span data-stu-id="aab3d-180">Install the scl tool.</span></span>

    ```bash
    yum install scl-utils
    ```
    
3. <span data-ttu-id="aab3d-181">安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="aab3d-181">Install .NET Core</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="aab3d-182">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="aab3d-182">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="aab3d-183">安装 .NET Core 2.0 SDK 和运行时：</span><span class="sxs-lookup"><span data-stu-id="aab3d-183">Install .NET Core 2.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnet20
   ```

<span data-ttu-id="aab3d-184">为环境启用 .NET Core 2.0 SDK/运行时：</span><span class="sxs-lookup"><span data-stu-id="aab3d-184">Enable .NET Core 2.0 SDK/Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnet20 bash
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="aab3d-185">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="aab3d-185">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="aab3d-186">**.NET Core 1.1**</span><span class="sxs-lookup"><span data-stu-id="aab3d-186">**.NET Core 1.1**</span></span>

<span data-ttu-id="aab3d-187">安装 .NET Core 1.1 SDK 和运行时：</span><span class="sxs-lookup"><span data-stu-id="aab3d-187">Install .NET Core 1.1 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore11
   ```

<span data-ttu-id="aab3d-188">为环境启用 .NET Core 1.1 SDK 和运行时：</span><span class="sxs-lookup"><span data-stu-id="aab3d-188">Enable .NET Core 1.1 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore11 bash
   ```

<span data-ttu-id="aab3d-189">**.NET Core 1.0**</span><span class="sxs-lookup"><span data-stu-id="aab3d-189">**.NET Core 1.0**</span></span>

<span data-ttu-id="aab3d-190">安装 .NET Core 1.0 SDK 和运行时：</span><span class="sxs-lookup"><span data-stu-id="aab3d-190">Install .NET Core 1.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore10
   ```

<span data-ttu-id="aab3d-191">为环境启用 .NET Core 1.0 SDK 和运行时：</span><span class="sxs-lookup"><span data-stu-id="aab3d-191">Enable .NET Core 1.0 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore10 bash
   ```

---
4. <span data-ttu-id="aab3d-192">运行 `dotnet --version` 命令，以证明安装成功。</span><span class="sxs-lookup"><span data-stu-id="aab3d-192">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

     ```bash
     dotnet --version
     ```

<span data-ttu-id="aab3d-193">若要获取 Red Hat .NET 通道访问注册方面的帮助，请参阅 Red Hat 提供的 [.NET Core 1.1 入门指南的第 1 章](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/)。</span><span class="sxs-lookup"><span data-stu-id="aab3d-193">For Red Hat .NET channel access registration help, see [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) at Red Hat.</span></span>

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a><span data-ttu-id="aab3d-194">为 Ubuntu 14.04、Ubuntu 16.04、Ubuntu 16.10、Linux Mint 17 和 Linux Mint 18（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="aab3d-194">Install .NET Core for Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bit)</span></span>

1. <span data-ttu-id="aab3d-195">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="aab3d-195">Remove any **previous preview** versions of .NET Core from your system.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="aab3d-196">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="aab3d-196">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="aab3d-197">注册受信任的 Microsoft 产品密钥。</span><span class="sxs-lookup"><span data-stu-id="aab3d-197">Register the Microsoft Product key as trusted.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. <span data-ttu-id="aab3d-198">设置所需的版本宿主包源。</span><span class="sxs-lookup"><span data-stu-id="aab3d-198">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="aab3d-199">**Ubuntu 17.04**</span><span class="sxs-lookup"><span data-stu-id="aab3d-199">**Ubuntu 17.04**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="aab3d-200">**Ubuntu 16.04 / Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="aab3d-200">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="aab3d-201">**Ubuntu 14.04 / Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="aab3d-201">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. <span data-ttu-id="aab3d-202">安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="aab3d-202">Install .NET Core.</span></span>

   ```bash
   sudo apt-get install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="aab3d-203">运行 `dotnet --version` 命令，以证明安装成功。</span><span class="sxs-lookup"><span data-stu-id="aab3d-203">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="aab3d-204">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="aab3d-204">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="aab3d-205">设置所需的版本宿主包源。</span><span class="sxs-lookup"><span data-stu-id="aab3d-205">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="aab3d-206">**Ubuntu 16.10**</span><span class="sxs-lookup"><span data-stu-id="aab3d-206">**Ubuntu 16.10**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  <span data-ttu-id="aab3d-207">**Ubuntu 16.04 / Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="aab3d-207">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   <span data-ttu-id="aab3d-208">**Ubuntu 14.04 / Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="aab3d-208">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. <span data-ttu-id="aab3d-209">在 Ubuntu 或 Linux Mint 上安装 .NET Core 1.x：</span><span class="sxs-lookup"><span data-stu-id="aab3d-209">Install .NET Core 1.x on Ubuntu or Linux Mint:</span></span>

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. <span data-ttu-id="aab3d-210">运行 `dotnet --version` 命令，以证明安装成功。</span><span class="sxs-lookup"><span data-stu-id="aab3d-210">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a><span data-ttu-id="aab3d-211">为 Debian 8 或 Debian 9（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="aab3d-211">Install .NET Core for Debian 8 or Debian 9 (64 bit)</span></span>

<span data-ttu-id="aab3d-212">在 Debian 8 或 Debian 9（64 位）上安装 .NET Core 的具体步骤：</span><span class="sxs-lookup"><span data-stu-id="aab3d-212">To install .NET Core on Debian 8 or Debian 9 (64 bit):</span></span>

1. <span data-ttu-id="aab3d-213">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="aab3d-213">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="aab3d-214">必须有用户控制目录，才能通过 tar.gz 在 Linux 系统上进行安装。</span><span class="sxs-lookup"><span data-stu-id="aab3d-214">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="aab3d-215">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="aab3d-215">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="aab3d-216">安装系统组件。</span><span class="sxs-lookup"><span data-stu-id="aab3d-216">Install system components.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. <span data-ttu-id="aab3d-217">注册受信任的 Microsoft 产品密钥。</span><span class="sxs-lookup"><span data-stu-id="aab3d-217">Register the trusted Microsoft Product key.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. <span data-ttu-id="aab3d-218">注册 Microsoft 产品源。</span><span class="sxs-lookup"><span data-stu-id="aab3d-218">Register the Microsoft Product feed.</span></span>

   <span data-ttu-id="aab3d-219">**Debian 9 (Stretch)**</span><span class="sxs-lookup"><span data-stu-id="aab3d-219">**Debian 9 (Stretch)**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   <span data-ttu-id="aab3d-220">**Debian 8 (Jessie)**</span><span class="sxs-lookup"><span data-stu-id="aab3d-220">**Debian 8 (Jessie)**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. <span data-ttu-id="aab3d-221">提取 .NET Core SDK 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="aab3d-221">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. <span data-ttu-id="aab3d-222">将 dotnet 添加到 PATH。</span><span class="sxs-lookup"><span data-stu-id="aab3d-222">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="aab3d-223">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="aab3d-223">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="aab3d-224">获取系统必备。</span><span class="sxs-lookup"><span data-stu-id="aab3d-224">Get the prerequisites.</span></span>

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. <span data-ttu-id="aab3d-225">下载 .NET Core SDK 二进制文件 (tarball)。</span><span class="sxs-lookup"><span data-stu-id="aab3d-225">Download the .NET Core SDK binaries (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. <span data-ttu-id="aab3d-226">提取 .NET Core SDK 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="aab3d-226">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="aab3d-227">将 dotnet 添加到 PATH。</span><span class="sxs-lookup"><span data-stu-id="aab3d-227">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="aab3d-228">运行 `dotnet --version` 命令，以证明安装成功。</span><span class="sxs-lookup"><span data-stu-id="aab3d-228">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a><span data-ttu-id="aab3d-229">为 Fedora 24、Fedora 25 或 Fedora 26（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="aab3d-229">Install .NET Core for Fedora 24, Fedora 25, or Fedora 26 (64 bit)</span></span>

<span data-ttu-id="aab3d-230">为 Fedora 26、Fedora 25 (.NET Core 2.x) 或 Fedora 24 (.NET Core 1.x) 安装 .NET Core 的具体步骤：</span><span class="sxs-lookup"><span data-stu-id="aab3d-230">To Install .NET Core for Fedora 26, Fedora 25 (.NET Core 2.x) or Fedora 24 (.NET Core 1.x):</span></span>

1. <span data-ttu-id="aab3d-231">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="aab3d-231">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="aab3d-232">必须有用户控制目录，才能通过 tar.gz 在 Linux 系统上进行安装。</span><span class="sxs-lookup"><span data-stu-id="aab3d-232">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="aab3d-233">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="aab3d-233">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="aab3d-234">**Fedora 26 或 Fedora 25**</span><span class="sxs-lookup"><span data-stu-id="aab3d-234">**Fedora 26 or Fedora 25**</span></span>

2. <span data-ttu-id="aab3d-235">注册 Microsoft 签名密钥。</span><span class="sxs-lookup"><span data-stu-id="aab3d-235">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="aab3d-236">添加 dotnet 产品源。</span><span class="sxs-lookup"><span data-stu-id="aab3d-236">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="aab3d-237">安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="aab3d-237">Install the .NET Core SDK.</span></span>

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="aab3d-238">将 dotnet 添加到 PATH。</span><span class="sxs-lookup"><span data-stu-id="aab3d-238">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="aab3d-239">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="aab3d-239">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="aab3d-240">**Fedora 24**</span><span class="sxs-lookup"><span data-stu-id="aab3d-240">**Fedora 24**</span></span>

2. <span data-ttu-id="aab3d-241">获取系统必备。</span><span class="sxs-lookup"><span data-stu-id="aab3d-241">Get the prerequisites.</span></span>

   ```bash
   sudo dnf install libunwind libicu
   ```

3. <span data-ttu-id="aab3d-242">下载 .NET Core SDK 二进制文件 (tarball)。</span><span class="sxs-lookup"><span data-stu-id="aab3d-242">Download the .NET Core SDK binary  (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. <span data-ttu-id="aab3d-243">提取 .NET Core SDK 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="aab3d-243">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="aab3d-244">将 dotnet 添加到 PATH。</span><span class="sxs-lookup"><span data-stu-id="aab3d-244">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="aab3d-245">运行 `dotnet --version` 命令，以证明安装成功。</span><span class="sxs-lookup"><span data-stu-id="aab3d-245">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a><span data-ttu-id="aab3d-246">为 CentOS 7.1（64 位）和 Oracle Linux 7.1（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="aab3d-246">Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit)</span></span>

<span data-ttu-id="aab3d-247">若要为 CentOS 7.1（64 位）和 Oracle Linux 7.1（64 位）安装 .NET Core，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="aab3d-247">To Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit):</span></span>

1. <span data-ttu-id="aab3d-248">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="aab3d-248">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="aab3d-249">必须有用户控制目录，才能通过 tar.gz 在 Linux 系统上进行安装。</span><span class="sxs-lookup"><span data-stu-id="aab3d-249">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="aab3d-250">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="aab3d-250">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="aab3d-251">注册 Microsoft 签名密钥。</span><span class="sxs-lookup"><span data-stu-id="aab3d-251">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="aab3d-252">添加 Microsoft 产品源。</span><span class="sxs-lookup"><span data-stu-id="aab3d-252">Add the Microsoft Product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="aab3d-253">安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="aab3d-253">Install the .NET Core SDK.</span></span>

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="aab3d-254">将 dotnet 添加到 PATH</span><span class="sxs-lookup"><span data-stu-id="aab3d-254">Add dotnet to your PATH</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="aab3d-255">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="aab3d-255">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="aab3d-256">获取系统必备。</span><span class="sxs-lookup"><span data-stu-id="aab3d-256">Get the prerequisites.</span></span>

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. <span data-ttu-id="aab3d-257">下载 .NET Core SDK 二进制文件 (tarball)。</span><span class="sxs-lookup"><span data-stu-id="aab3d-257">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. <span data-ttu-id="aab3d-258">提取 .NET Core SDK 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="aab3d-258">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="aab3d-259">将 dotnet 添加到 PATH。</span><span class="sxs-lookup"><span data-stu-id="aab3d-259">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="aab3d-260">运行 `dotnet --version` 命令，以证明安装成功。</span><span class="sxs-lookup"><span data-stu-id="aab3d-260">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a><span data-ttu-id="aab3d-261">为 SUSE Linux Enterprise Server（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="aab3d-261">Install .NET Core for SUSE Linux Enterprise Server (64 bit)</span></span>

<span data-ttu-id="aab3d-262">为 SUSE Linux Enterprise Server (SLES) 12 SP2（64 位）安装 .NET Core 2.x 的具体步骤：</span><span class="sxs-lookup"><span data-stu-id="aab3d-262">To Install .NET Core 2.x for SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bit):</span></span>

1. <span data-ttu-id="aab3d-263">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="aab3d-263">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="aab3d-264">添加 dotnet 产品源。</span><span class="sxs-lookup"><span data-stu-id="aab3d-264">Add the dotnet product feed.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. <span data-ttu-id="aab3d-265">安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="aab3d-265">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="aab3d-266">将 dotnet 添加到 PATH。</span><span class="sxs-lookup"><span data-stu-id="aab3d-266">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. <span data-ttu-id="aab3d-267">运行 `dotnet --version` 命令，以证明安装成功。</span><span class="sxs-lookup"><span data-stu-id="aab3d-267">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a><span data-ttu-id="aab3d-268">为 openSUSE（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="aab3d-268">Install .NET Core for openSUSE (64 bit)</span></span>

<span data-ttu-id="aab3d-269">为 openSUSE 安装 .NET Core 2.x/为 openSUSE（64 位）安装 .NET Core 1.x 的具体步骤：</span><span class="sxs-lookup"><span data-stu-id="aab3d-269">To Install .NET Core 2.x for openSUSE or .NET Core 1.x for openSUSE (64 bit):</span></span>

1. <span data-ttu-id="aab3d-270">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="aab3d-270">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="aab3d-271">必须有用户控制目录，才能通过 tar.gz 在 Linux 系统上进行安装。</span><span class="sxs-lookup"><span data-stu-id="aab3d-271">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="aab3d-272">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="aab3d-272">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="aab3d-273">注册 Microsoft 签名密钥。</span><span class="sxs-lookup"><span data-stu-id="aab3d-273">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="aab3d-274">添加 dotnet 产品源。</span><span class="sxs-lookup"><span data-stu-id="aab3d-274">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. <span data-ttu-id="aab3d-275">安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="aab3d-275">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="aab3d-276">将 dotnet 添加到 PATH。</span><span class="sxs-lookup"><span data-stu-id="aab3d-276">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="aab3d-277">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="aab3d-277">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="aab3d-278">获取系统必备。</span><span class="sxs-lookup"><span data-stu-id="aab3d-278">Get the prerequisites.</span></span>

   ```bash
   sudo zypper install libunwind libicu
   ```

3. <span data-ttu-id="aab3d-279">下载 .NET Core SDK 二进制文件 (tarball)。</span><span class="sxs-lookup"><span data-stu-id="aab3d-279">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. <span data-ttu-id="aab3d-280">提取 .NET Core SDK 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="aab3d-280">Extract the .NET Core SDK binaries.</span></span>
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="aab3d-281">将 dotnet 添加到 PATH。</span><span class="sxs-lookup"><span data-stu-id="aab3d-281">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="aab3d-282">运行 `dotnet --version` 命令，以证明安装成功。</span><span class="sxs-lookup"><span data-stu-id="aab3d-282">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> <span data-ttu-id="aab3d-283">若对在支持的 Linux 发行版本/版本上安装 .NET Core 2.x 有疑问，请参阅每个已安装的发行版本/版本对应的 [2.0 已知问题](https://github.com/dotnet/core/tree/master/release-notes/2.0)主题。</span><span class="sxs-lookup"><span data-stu-id="aab3d-283">If you have problems with the .NET Core 2.x installation on a supported Linux distribution/version, consult the [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for your installed distributions/versions.</span></span> 
>
> <span data-ttu-id="aab3d-284">若对在支持的 Linux 发行版本/版本上安装 .NET Core 1.x 有疑问，请参阅每个已安装的发行版本/版本对应的 [1.0.0 已知问题](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md)和 [1.0.1 已知问题](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md)主题。</span><span class="sxs-lookup"><span data-stu-id="aab3d-284">If you have problems with the .NET Core 1.x installation on a supported Linux distribution/version, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics for your installed distributions/versions.</span></span>

