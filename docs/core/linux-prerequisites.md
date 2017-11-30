---
title: "Linux 上 .NET Core 的先决条件"
description: "支持的 Linux 版本和 .NET Core 依赖项，用于在 Linux 计算机上开发、部署和运行 .NET Core 应用程序。"
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS,
author: jralexander
ms.author: johalex
ms.date: 09/07/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.openlocfilehash: 04fdf26e150e6d489c0641588563f69f24835615
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="b645e-104">Linux 上 .NET Core 的先决条件</span><span class="sxs-lookup"><span data-stu-id="b645e-104">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="b645e-105">本文介绍了在 Linux 上开发 .NET Core 应用程序所需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="b645e-105">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="b645e-106">支持的 Linux 发行版本/版本和依赖项适用于在 Linux 上开发 .NET Core 应用程序的两种方法：</span><span class="sxs-lookup"><span data-stu-id="b645e-106">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="b645e-107">结合使用命令行和常用编辑器</span><span class="sxs-lookup"><span data-stu-id="b645e-107">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="b645e-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b645e-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a><span data-ttu-id="b645e-109">支持的 Linux 版本</span><span class="sxs-lookup"><span data-stu-id="b645e-109">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b645e-110">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b645e-110">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="b645e-111">.NET Core 2.0 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="b645e-111">.NET Core 2.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="b645e-112">支持的 Linux 发行版本都对应有一个 Linux 版本（每芯片体系结构）。</span><span class="sxs-lookup"><span data-stu-id="b645e-112">There is a single Linux build (per chip architecture) for supported Linux distros.</span></span>

<span data-ttu-id="b645e-113">以下 Linux 64 位（`x86_64` 或 `amd64`）发行版本/版本支持 NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="b645e-113">NET Core 2.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

 * <span data-ttu-id="b645e-114">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="b645e-114">Red Hat Enterprise Linux 7</span></span>
 * <span data-ttu-id="b645e-115">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="b645e-115">CentOS 7</span></span>
 * <span data-ttu-id="b645e-116">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="b645e-116">Oracle Linux 7</span></span>
 * <span data-ttu-id="b645e-117">Fedora 25、Fedora 26</span><span class="sxs-lookup"><span data-stu-id="b645e-117">Fedora 25, Fedora 26</span></span>
 * <span data-ttu-id="b645e-118">Debian 8.7 或更高版本</span><span class="sxs-lookup"><span data-stu-id="b645e-118">Debian 8.7 or later versions</span></span> 
 * <span data-ttu-id="b645e-119">Ubuntu 17.04、Ubuntu 16.04、Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="b645e-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span></span>
 * <span data-ttu-id="b645e-120">Linux Mint 18、Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="b645e-120">Linux Mint 18, Linux Mint 17</span></span>
 * <span data-ttu-id="b645e-121">openSUSE 42.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="b645e-121">openSUSE 42.2 or later versions</span></span>
 * <span data-ttu-id="b645e-122">SUSE Enterprise Linux (SLES) 12 SP2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="b645e-122">SUSE Enterprise Linux (SLES) 12 SP2 or later versions</span></span>

<span data-ttu-id="b645e-123">有关支持 .NET Core 2.x 的操作系统、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 2.x - 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="b645e-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b645e-124">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b645e-124">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="b645e-125">以下 Linux 64 位（`x86_64` 或 `amd64`）发行版本/版本支持 .NET Core 1.x：</span><span class="sxs-lookup"><span data-stu-id="b645e-125">.NET Core 1.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="b645e-126">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="b645e-126">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="b645e-127">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="b645e-127">CentOS 7</span></span>
* <span data-ttu-id="b645e-128">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="b645e-128">Oracle Linux 7</span></span>
* <span data-ttu-id="b645e-129">Fedora 24</span><span class="sxs-lookup"><span data-stu-id="b645e-129">Fedora 24</span></span>
* <span data-ttu-id="b645e-130">Debian 8.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="b645e-130">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="b645e-131">Ubuntu 14.04、Ubuntu 16.04、Ubuntu 16.10\*</span><span class="sxs-lookup"><span data-stu-id="b645e-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span></span>
 * <span data-ttu-id="b645e-132">最新修补版 .NET Core 1.1 支持 Ubuntu 16.10</span><span class="sxs-lookup"><span data-stu-id="b645e-132">Ubuntu 16.10 is supported by the latest patch release of .NET Core 1.1</span></span>
* <span data-ttu-id="b645e-133">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="b645e-133">Linux Mint 17</span></span>
* <span data-ttu-id="b645e-134">openSUSE 42.1 或更高版本 (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="b645e-134">openSUSE 42.1 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="b645e-135">有关支持 .NET Core 1.x 的操作系统、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 1.x - 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="b645e-135">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="b645e-136">Linux 发行版本依赖项</span><span class="sxs-lookup"><span data-stu-id="b645e-136">Linux distribution dependencies</span></span>

<span data-ttu-id="b645e-137">以下打算用作示例。</span><span class="sxs-lookup"><span data-stu-id="b645e-137">The following are intended to be examples.</span></span> <span data-ttu-id="b645e-138">确切的版本和名称可能选择的 Linux 分发上略有不同。</span><span class="sxs-lookup"><span data-stu-id="b645e-138">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="b645e-139">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="b645e-139">Ubuntu</span></span>

<span data-ttu-id="b645e-140">Ubuntu 发行版本需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="b645e-140">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="b645e-141">libunwind8</span><span class="sxs-lookup"><span data-stu-id="b645e-141">libunwind8</span></span>
* <span data-ttu-id="b645e-142">liblttng ust0</span><span class="sxs-lookup"><span data-stu-id="b645e-142">liblttng-ust0</span></span>
* <span data-ttu-id="b645e-143">libcurl3</span><span class="sxs-lookup"><span data-stu-id="b645e-143">libcurl3</span></span>
* <span data-ttu-id="b645e-144">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="b645e-144">libssl1.0.0</span></span>
* <span data-ttu-id="b645e-145">libuuid1</span><span class="sxs-lookup"><span data-stu-id="b645e-145">libuuid1</span></span>
* <span data-ttu-id="b645e-146">libkrb5</span><span class="sxs-lookup"><span data-stu-id="b645e-146">libkrb5</span></span>
* <span data-ttu-id="b645e-147">zlib1g</span><span class="sxs-lookup"><span data-stu-id="b645e-147">zlib1g</span></span>
* <span data-ttu-id="b645e-148">（对于 14.X) libicu52</span><span class="sxs-lookup"><span data-stu-id="b645e-148">libicu52 (for 14.X)</span></span>
* <span data-ttu-id="b645e-149">（对于 16.X) libicu55</span><span class="sxs-lookup"><span data-stu-id="b645e-149">libicu55 (for 16.X)</span></span>
* <span data-ttu-id="b645e-150">（对于 17.X) libicu57</span><span class="sxs-lookup"><span data-stu-id="b645e-150">libicu57 (for 17.X)</span></span>

### <a name="centos"></a><span data-ttu-id="b645e-151">CentOS</span><span class="sxs-lookup"><span data-stu-id="b645e-151">CentOS</span></span>

<span data-ttu-id="b645e-152">CentOS 发行版本需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="b645e-152">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="b645e-153">libunwind</span><span class="sxs-lookup"><span data-stu-id="b645e-153">libunwind</span></span>
* <span data-ttu-id="b645e-154">lttng 必须</span><span class="sxs-lookup"><span data-stu-id="b645e-154">lttng-ust</span></span>
* <span data-ttu-id="b645e-155">libcurl</span><span class="sxs-lookup"><span data-stu-id="b645e-155">libcurl</span></span>
* <span data-ttu-id="b645e-156">openssl 库</span><span class="sxs-lookup"><span data-stu-id="b645e-156">openssl-libs</span></span>
* <span data-ttu-id="b645e-157">libuuid</span><span class="sxs-lookup"><span data-stu-id="b645e-157">libuuid</span></span>
* <span data-ttu-id="b645e-158">krb5 libs</span><span class="sxs-lookup"><span data-stu-id="b645e-158">krb5-libs</span></span>
* <span data-ttu-id="b645e-159">libicu</span><span class="sxs-lookup"><span data-stu-id="b645e-159">libicu</span></span>
* <span data-ttu-id="b645e-160">zlib</span><span class="sxs-lookup"><span data-stu-id="b645e-160">zlib</span></span>

<span data-ttu-id="b645e-161">有关依赖项的详细信息，请参阅[独立式 Linux 应用程序](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="b645e-161">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="b645e-162">使用本机安装程序安装 .NET Core 依赖项</span><span class="sxs-lookup"><span data-stu-id="b645e-162">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="b645e-163">.NET Core 本机安装程序适用于支持的 Linux 发行版本/版本。</span><span class="sxs-lookup"><span data-stu-id="b645e-163">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="b645e-164">本机安装程序需要拥有对服务器的管理员 (sudo) 访问权限。</span><span class="sxs-lookup"><span data-stu-id="b645e-164">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="b645e-165">使用本机安装程序的优势在于，可以安装所有 .NET Core 本机依赖项。</span><span class="sxs-lookup"><span data-stu-id="b645e-165">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="b645e-166">本机安装程序还会在整个系统内安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="b645e-166">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="b645e-167">在 Linux 上，安装程序包有两种使用方式：</span><span class="sxs-lookup"><span data-stu-id="b645e-167">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="b645e-168">使用基于源的包管理器，如适用于 Ubuntu 的 apt-get，或适用于 CentOS/RHEL 的 yum。</span><span class="sxs-lookup"><span data-stu-id="b645e-168">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="b645e-169">使用包本身（DEB 或 RPM）。</span><span class="sxs-lookup"><span data-stu-id="b645e-169">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="b645e-170">使用 .NET Core 安装程序脚本编写安装脚本</span><span class="sxs-lookup"><span data-stu-id="b645e-170">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="b645e-171">`dotnet-install` 脚本用于执行 CLI 工具链和共享运行时的非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="b645e-171">The `dotnet-install` scripts are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="b645e-172">你可以下载中的脚本： https://dot.net/v1/dotnet-install.sh</span><span class="sxs-lookup"><span data-stu-id="b645e-172">You can download the script from: https://dot.net/v1/dotnet-install.sh</span></span>

<span data-ttu-id="b645e-173">安装程序 bash 脚本用于自动化方案和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="b645e-173">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="b645e-174">此脚本也读取 PowerShell 开关，因此可以与 Linux/OS X 系统上的脚本结合使用。</span><span class="sxs-lookup"><span data-stu-id="b645e-174">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b645e-175">运行脚本前，请安装所需的[依赖项](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)。</span><span class="sxs-lookup"><span data-stu-id="b645e-175">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="b645e-176">为 Red Hat Enterprise Linux (RHEL) 7 安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="b645e-176">Install .NET Core for Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="b645e-177">在 RHEL 7 上安装 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="b645e-177">To install .NET Core on RHEL 7:</span></span>

1. <span data-ttu-id="b645e-178">启用 Red Hat .NET 通道（在 RHEL 7 订阅下）。</span><span class="sxs-lookup"><span data-stu-id="b645e-178">Enable the Red Hat .NET channel, available under your RHEL 7 subscription.</span></span>
    * <span data-ttu-id="b645e-179">对于 Red Hat Enterprise 7 服务器，请使用：</span><span class="sxs-lookup"><span data-stu-id="b645e-179">For Red Hat Enterprise 7 Server, use:</span></span>
    
         ```bash
         subscription-manager repos --enable=rhel-7-server-dotnet-rpms
         ```
    
    * <span data-ttu-id="b645e-180">对于 Red Hat Enterprise 7 工作站，请使用：</span><span class="sxs-lookup"><span data-stu-id="b645e-180">For Red Hat Enterprise 7 Workstation, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
         ```
    
    * <span data-ttu-id="b645e-181">对于 Red Hat Enterprise 7 HPC 计算节点，请使用：</span><span class="sxs-lookup"><span data-stu-id="b645e-181">For Red Hat Enterprise 7 HPC Compute Node, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. <span data-ttu-id="b645e-182">安装 scl 工具。</span><span class="sxs-lookup"><span data-stu-id="b645e-182">Install the scl tool.</span></span>

    ```bash
    yum install scl-utils
    ```
    
3. <span data-ttu-id="b645e-183">安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="b645e-183">Install .NET Core</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b645e-184">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b645e-184">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="b645e-185">安装 .NET Core 2.0 SDK 和运行时：</span><span class="sxs-lookup"><span data-stu-id="b645e-185">Install .NET Core 2.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnet20
   ```

<span data-ttu-id="b645e-186">为环境启用 .NET Core 2.0 SDK/运行时：</span><span class="sxs-lookup"><span data-stu-id="b645e-186">Enable .NET Core 2.0 SDK/Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnet20 bash
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b645e-187">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b645e-187">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="b645e-188">**.NET Core 1.1**</span><span class="sxs-lookup"><span data-stu-id="b645e-188">**.NET Core 1.1**</span></span>

<span data-ttu-id="b645e-189">安装 .NET Core 1.1 SDK 和运行时：</span><span class="sxs-lookup"><span data-stu-id="b645e-189">Install .NET Core 1.1 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore11
   ```

<span data-ttu-id="b645e-190">为环境启用 .NET Core 1.1 SDK 和运行时：</span><span class="sxs-lookup"><span data-stu-id="b645e-190">Enable .NET Core 1.1 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore11 bash
   ```

<span data-ttu-id="b645e-191">**.NET Core 1.0**</span><span class="sxs-lookup"><span data-stu-id="b645e-191">**.NET Core 1.0**</span></span>

<span data-ttu-id="b645e-192">安装 .NET Core 1.0 SDK 和运行时：</span><span class="sxs-lookup"><span data-stu-id="b645e-192">Install .NET Core 1.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore10
   ```

<span data-ttu-id="b645e-193">为环境启用 .NET Core 1.0 SDK 和运行时：</span><span class="sxs-lookup"><span data-stu-id="b645e-193">Enable .NET Core 1.0 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore10 bash
   ```

---
4. <span data-ttu-id="b645e-194">运行 `dotnet --version` 命令，以证明安装成功。</span><span class="sxs-lookup"><span data-stu-id="b645e-194">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

     ```bash
     dotnet --version
     ```

<span data-ttu-id="b645e-195">若要获取 Red Hat .NET 通道访问注册方面的帮助，请参阅 Red Hat 提供的 [.NET Core 1.1 入门指南的第 1 章](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/)。</span><span class="sxs-lookup"><span data-stu-id="b645e-195">For Red Hat .NET channel access registration help, see [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) at Red Hat.</span></span>

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a><span data-ttu-id="b645e-196">为 Ubuntu 14.04、Ubuntu 16.04、Ubuntu 16.10、Linux Mint 17 和 Linux Mint 18（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="b645e-196">Install .NET Core for Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bit)</span></span>

1. <span data-ttu-id="b645e-197">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="b645e-197">Remove any **previous preview** versions of .NET Core from your system.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b645e-198">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b645e-198">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="b645e-199">注册受信任的 Microsoft 产品密钥。</span><span class="sxs-lookup"><span data-stu-id="b645e-199">Register the Microsoft Product key as trusted.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. <span data-ttu-id="b645e-200">设置所需的版本宿主包源。</span><span class="sxs-lookup"><span data-stu-id="b645e-200">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="b645e-201">**Ubuntu 17.04**</span><span class="sxs-lookup"><span data-stu-id="b645e-201">**Ubuntu 17.04**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="b645e-202">**Ubuntu 16.04 / Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="b645e-202">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="b645e-203">**Ubuntu 14.04 / Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="b645e-203">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. <span data-ttu-id="b645e-204">安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="b645e-204">Install .NET Core.</span></span>

   ```bash
   sudo apt-get install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="b645e-205">运行 `dotnet --version` 命令，以证明安装成功。</span><span class="sxs-lookup"><span data-stu-id="b645e-205">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b645e-206">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b645e-206">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="b645e-207">设置所需的版本宿主包源。</span><span class="sxs-lookup"><span data-stu-id="b645e-207">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="b645e-208">**Ubuntu 16.10**</span><span class="sxs-lookup"><span data-stu-id="b645e-208">**Ubuntu 16.10**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  <span data-ttu-id="b645e-209">**Ubuntu 16.04 / Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="b645e-209">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   <span data-ttu-id="b645e-210">**Ubuntu 14.04 / Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="b645e-210">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. <span data-ttu-id="b645e-211">在 Ubuntu 或 Linux Mint 上安装 .NET Core 1.x：</span><span class="sxs-lookup"><span data-stu-id="b645e-211">Install .NET Core 1.x on Ubuntu or Linux Mint:</span></span>

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. <span data-ttu-id="b645e-212">运行 `dotnet --version` 命令，以证明安装成功。</span><span class="sxs-lookup"><span data-stu-id="b645e-212">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a><span data-ttu-id="b645e-213">为 Debian 8 或 Debian 9（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="b645e-213">Install .NET Core for Debian 8 or Debian 9 (64 bit)</span></span>

<span data-ttu-id="b645e-214">在 Debian 8 或 Debian 9（64 位）上安装 .NET Core 的具体步骤：</span><span class="sxs-lookup"><span data-stu-id="b645e-214">To install .NET Core on Debian 8 or Debian 9 (64 bit):</span></span>

1. <span data-ttu-id="b645e-215">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="b645e-215">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="b645e-216">必须有用户控制目录，才能通过 tar.gz 在 Linux 系统上进行安装。</span><span class="sxs-lookup"><span data-stu-id="b645e-216">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b645e-217">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b645e-217">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="b645e-218">安装系统组件。</span><span class="sxs-lookup"><span data-stu-id="b645e-218">Install system components.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. <span data-ttu-id="b645e-219">注册受信任的 Microsoft 产品密钥。</span><span class="sxs-lookup"><span data-stu-id="b645e-219">Register the trusted Microsoft Product key.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. <span data-ttu-id="b645e-220">注册 Microsoft 产品源。</span><span class="sxs-lookup"><span data-stu-id="b645e-220">Register the Microsoft Product feed.</span></span>

   <span data-ttu-id="b645e-221">**Debian 9 (Stretch)**</span><span class="sxs-lookup"><span data-stu-id="b645e-221">**Debian 9 (Stretch)**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   <span data-ttu-id="b645e-222">**Debian 8 (Jessie)**</span><span class="sxs-lookup"><span data-stu-id="b645e-222">**Debian 8 (Jessie)**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. <span data-ttu-id="b645e-223">安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="b645e-223">Install .NET Core SDK.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. <span data-ttu-id="b645e-224">将 dotnet 添加到 PATH。</span><span class="sxs-lookup"><span data-stu-id="b645e-224">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```
   
7. <span data-ttu-id="b645e-225">运行 `dotnet --version` 命令，以证明安装成功。</span><span class="sxs-lookup"><span data-stu-id="b645e-225">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```   
  

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b645e-226">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b645e-226">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="b645e-227">获取系统必备。</span><span class="sxs-lookup"><span data-stu-id="b645e-227">Get the prerequisites.</span></span>

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. <span data-ttu-id="b645e-228">下载 .NET Core SDK 二进制文件 (tarball)。</span><span class="sxs-lookup"><span data-stu-id="b645e-228">Download the .NET Core SDK binaries (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. <span data-ttu-id="b645e-229">提取 .NET Core SDK 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="b645e-229">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="b645e-230">将 dotnet 添加到 PATH。</span><span class="sxs-lookup"><span data-stu-id="b645e-230">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

6. <span data-ttu-id="b645e-231">运行 `dotnet --version` 命令，以证明安装成功。</span><span class="sxs-lookup"><span data-stu-id="b645e-231">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a><span data-ttu-id="b645e-232">为 Fedora 24、Fedora 25 或 Fedora 26（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="b645e-232">Install .NET Core for Fedora 24, Fedora 25, or Fedora 26 (64 bit)</span></span>

<span data-ttu-id="b645e-233">若要在 Fedora 26 或 Fedora 25 上安装 .NET Core 2.x，或在 Fedora 24 上安装 .NET Core 1.x，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b645e-233">To install .NET Core 2.x on Fedora 26 or Fedora 25, or .NET Core 1.x on Fedora 24:</span></span>

1. <span data-ttu-id="b645e-234">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="b645e-234">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="b645e-235">必须有用户控制目录，才能通过 tar.gz 在 Linux 系统上进行安装。</span><span class="sxs-lookup"><span data-stu-id="b645e-235">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b645e-236">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b645e-236">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="b645e-237">**Fedora 26 或 Fedora 25**</span><span class="sxs-lookup"><span data-stu-id="b645e-237">**Fedora 26 or Fedora 25**</span></span>

2. <span data-ttu-id="b645e-238">注册 Microsoft 签名密钥。</span><span class="sxs-lookup"><span data-stu-id="b645e-238">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="b645e-239">添加 dotnet 产品源。</span><span class="sxs-lookup"><span data-stu-id="b645e-239">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="b645e-240">安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="b645e-240">Install the .NET Core SDK.</span></span>

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="b645e-241">将 dotnet 添加到 PATH。</span><span class="sxs-lookup"><span data-stu-id="b645e-241">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b645e-242">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b645e-242">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="b645e-243">**Fedora 24**</span><span class="sxs-lookup"><span data-stu-id="b645e-243">**Fedora 24**</span></span>

2. <span data-ttu-id="b645e-244">获取系统必备。</span><span class="sxs-lookup"><span data-stu-id="b645e-244">Get the prerequisites.</span></span>

   ```bash
   sudo dnf install libunwind libicu
   ```

3. <span data-ttu-id="b645e-245">下载 .NET Core SDK 二进制文件 (tarball)。</span><span class="sxs-lookup"><span data-stu-id="b645e-245">Download the .NET Core SDK binary  (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. <span data-ttu-id="b645e-246">提取 .NET Core SDK 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="b645e-246">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="b645e-247">将 dotnet 添加到 PATH。</span><span class="sxs-lookup"><span data-stu-id="b645e-247">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="b645e-248">运行 `dotnet --version` 命令，以证明安装成功。</span><span class="sxs-lookup"><span data-stu-id="b645e-248">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a><span data-ttu-id="b645e-249">为 CentOS 7.1（64 位）和 Oracle Linux 7.1（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="b645e-249">Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit)</span></span>

<span data-ttu-id="b645e-250">若要为 CentOS 7.1（64 位）和 Oracle Linux 7.1（64 位）安装 .NET Core，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b645e-250">To install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit):</span></span>

1. <span data-ttu-id="b645e-251">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="b645e-251">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="b645e-252">必须有用户控制目录，才能通过 tar.gz 在 Linux 系统上进行安装。</span><span class="sxs-lookup"><span data-stu-id="b645e-252">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b645e-253">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b645e-253">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="b645e-254">注册 Microsoft 签名密钥。</span><span class="sxs-lookup"><span data-stu-id="b645e-254">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="b645e-255">添加 Microsoft 产品源。</span><span class="sxs-lookup"><span data-stu-id="b645e-255">Add the Microsoft Product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="b645e-256">安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="b645e-256">Install the .NET Core SDK.</span></span>

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="b645e-257">将 dotnet 添加到 PATH</span><span class="sxs-lookup"><span data-stu-id="b645e-257">Add dotnet to your PATH</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b645e-258">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b645e-258">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="b645e-259">获取系统必备。</span><span class="sxs-lookup"><span data-stu-id="b645e-259">Get the prerequisites.</span></span>

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. <span data-ttu-id="b645e-260">下载 .NET Core SDK 二进制文件 (tarball)。</span><span class="sxs-lookup"><span data-stu-id="b645e-260">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. <span data-ttu-id="b645e-261">提取 .NET Core SDK 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="b645e-261">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="b645e-262">将 dotnet 添加到 PATH。</span><span class="sxs-lookup"><span data-stu-id="b645e-262">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="b645e-263">运行 `dotnet --version` 命令，以证明安装成功。</span><span class="sxs-lookup"><span data-stu-id="b645e-263">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a><span data-ttu-id="b645e-264">为 SUSE Linux Enterprise Server（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="b645e-264">Install .NET Core for SUSE Linux Enterprise Server (64 bit)</span></span>

<span data-ttu-id="b645e-265">若要为 SUSE Linux Enterprise Server (SLES) 12 SP2（64 位）安装 .NET Core 2.x，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b645e-265">To install .NET Core 2.x for SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bit):</span></span>

1. <span data-ttu-id="b645e-266">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="b645e-266">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="b645e-267">添加 dotnet 产品源。</span><span class="sxs-lookup"><span data-stu-id="b645e-267">Add the dotnet product feed.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. <span data-ttu-id="b645e-268">安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="b645e-268">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="b645e-269">将 dotnet 添加到 PATH。</span><span class="sxs-lookup"><span data-stu-id="b645e-269">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. <span data-ttu-id="b645e-270">运行 `dotnet --version` 命令，以证明安装成功。</span><span class="sxs-lookup"><span data-stu-id="b645e-270">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a><span data-ttu-id="b645e-271">为 openSUSE（64 位）安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="b645e-271">Install .NET Core for openSUSE (64 bit)</span></span>

<span data-ttu-id="b645e-272">若要为 openSUSE 安装 .NET Core 2.x 或者为 openSUSE（64 位）安装 .NET Core 1.x，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b645e-272">To install .NET Core 2.x for openSUSE or .NET Core 1.x for openSUSE (64 bit):</span></span>

1. <span data-ttu-id="b645e-273">从系统中删除 .NET Core 的所有旧预览版本。</span><span class="sxs-lookup"><span data-stu-id="b645e-273">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="b645e-274">必须有用户控制目录，才能通过 tar.gz 在 Linux 系统上进行安装。</span><span class="sxs-lookup"><span data-stu-id="b645e-274">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b645e-275">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b645e-275">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="b645e-276">注册 Microsoft 签名密钥。</span><span class="sxs-lookup"><span data-stu-id="b645e-276">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="b645e-277">添加 dotnet 产品源。</span><span class="sxs-lookup"><span data-stu-id="b645e-277">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. <span data-ttu-id="b645e-278">安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="b645e-278">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="b645e-279">将 dotnet 添加到 PATH。</span><span class="sxs-lookup"><span data-stu-id="b645e-279">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b645e-280">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b645e-280">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="b645e-281">获取系统必备。</span><span class="sxs-lookup"><span data-stu-id="b645e-281">Get the prerequisites.</span></span>

   ```bash
   sudo zypper install libunwind libicu
   ```

3. <span data-ttu-id="b645e-282">下载 .NET Core SDK 二进制文件 (tarball)。</span><span class="sxs-lookup"><span data-stu-id="b645e-282">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. <span data-ttu-id="b645e-283">提取 .NET Core SDK 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="b645e-283">Extract the .NET Core SDK binaries.</span></span>
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="b645e-284">将 dotnet 添加到 PATH。</span><span class="sxs-lookup"><span data-stu-id="b645e-284">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="b645e-285">运行 `dotnet --version` 命令，以证明安装成功。</span><span class="sxs-lookup"><span data-stu-id="b645e-285">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> <span data-ttu-id="b645e-286">若对在支持的 Linux 发行版本/版本上安装 .NET Core 2.x 有疑问，请参阅每个已安装的发行版本/版本对应的 [2.0 已知问题](https://github.com/dotnet/core/tree/master/release-notes/2.0)主题。</span><span class="sxs-lookup"><span data-stu-id="b645e-286">If you have problems with the .NET Core 2.x installation on a supported Linux distribution/version, consult the [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for your installed distributions/versions.</span></span> 
>
> <span data-ttu-id="b645e-287">若对在支持的 Linux 发行版本/版本上安装 .NET Core 1.x 有疑问，请参阅每个已安装的发行版本/版本对应的 [1.0.0 已知问题](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md)和 [1.0.1 已知问题](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md)主题。</span><span class="sxs-lookup"><span data-stu-id="b645e-287">If you have problems with the .NET Core 1.x installation on a supported Linux distribution/version, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics for your installed distributions/versions.</span></span>
