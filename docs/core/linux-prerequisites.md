---
title: Linux 上 .NET Core 的先决条件
description: 支持的 Linux 版本和 .NET Core 依赖项，用于在 Linux 计算机上开发、部署和运行 .NET Core 应用程序。
author: thraka
ms.author: adegeo
ms.date: 12/14/2018
ms.openlocfilehash: 0bd3287535ba2c398f6577890d1d39f42a806364
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612220"
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="30204-103">Linux 上 .NET Core 的先决条件</span><span class="sxs-lookup"><span data-stu-id="30204-103">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="30204-104">本文介绍了在 Linux 上开发 .NET Core 应用程序所需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="30204-104">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="30204-105">支持的 Linux 发行版本/版本和依赖项适用于在 Linux 上开发 .NET Core 应用程序的两种方法：</span><span class="sxs-lookup"><span data-stu-id="30204-105">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="30204-106">结合使用命令行和常用编辑器</span><span class="sxs-lookup"><span data-stu-id="30204-106">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="30204-107">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="30204-107">Visual Studio Code</span></span>](https://code.visualstudio.com/)

> [!NOTE]
> <span data-ttu-id="30204-108">生产服务器/环境不需要 .NET Core SDK 包。</span><span class="sxs-lookup"><span data-stu-id="30204-108">The .NET Core SDK package is not required for production servers/environments.</span></span> <span data-ttu-id="30204-109">部署到生产环境的应用只需要 .NET Core 运行时包。</span><span class="sxs-lookup"><span data-stu-id="30204-109">Only the .NET Core runtime package is needed for apps deployed to production environments.</span></span> <span data-ttu-id="30204-110">.NET Core 运行时与应用一同部署为独立部署的一部分，但是，对于依赖框架的部署应用，它必须单独部署。</span><span class="sxs-lookup"><span data-stu-id="30204-110">The .NET Core runtime is deployed with apps as part of a self-contained deployment, however, it must be deployed for Framework-dependent deployed apps separately.</span></span> <span data-ttu-id="30204-111">有关依赖框架和独立部署类型的更多信息，请参阅 [.NET Core 应用程序部署](./deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="30204-111">For more information about framework-dependent and self-contained deployment types, see [.NET Core application deployment](./deploying/index.md).</span></span> <span data-ttu-id="30204-112">另请参阅[独立式 Linux 应用程序](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)，了解特定准则。</span><span class="sxs-lookup"><span data-stu-id="30204-112">Also see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) for specific guidelines.</span></span>

## <a name="supported-linux-versions"></a><span data-ttu-id="30204-113">支持的 Linux 版本</span><span class="sxs-lookup"><span data-stu-id="30204-113">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="30204-114">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="30204-114">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="30204-115">.NET Core 2.x 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="30204-115">.NET Core 2.x treats Linux as a single operating system.</span></span> <span data-ttu-id="30204-116">支持的 Linux 分发都对应有一个 Linux 内部版本（根据芯片体系结构）。</span><span class="sxs-lookup"><span data-stu-id="30204-116">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span> 

<span data-ttu-id="30204-117">有关下载链接和详细信息，请参阅 [.NET Core 2.2 下载](https://www.microsoft.com/net/download/dotnet-core/2.2)或 [.NET Core 2.1 下载](https://www.microsoft.com/net/download/dotnet-core/2.1)。</span><span class="sxs-lookup"><span data-stu-id="30204-117">For download links and more information, see [.NET Core 2.2 downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) or [.NET Core 2.1 downloads](https://www.microsoft.com/net/download/dotnet-core/2.1).</span></span>

<span data-ttu-id="30204-118">以下 Linux 发行版本/版本支持 .NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="30204-118">.NET Core 2.x is supported on the following Linux distributions/versions:</span></span>

* <span data-ttu-id="30204-119">Red Hat Enterprise Linux 7，6 - 64 位（`x86_64` 或 `amd64`）</span><span class="sxs-lookup"><span data-stu-id="30204-119">Red Hat Enterprise Linux 7, 6 - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="30204-120">CentOS 7  - 64 位（`x86_64` 或 `amd64`）</span><span class="sxs-lookup"><span data-stu-id="30204-120">CentOS 7  - 64-bit (`x86_64` or `amd64`)</span></span> 
* <span data-ttu-id="30204-121">Oracle Linux 7 - 64 位（`x86_64` 或 `amd64`）</span><span class="sxs-lookup"><span data-stu-id="30204-121">Oracle Linux 7 - 64-bit (`x86_64` or `amd64`)</span></span> 
* <span data-ttu-id="30204-122">Fedora 28、27 - 64 位（`x86_64` 或 `amd64`）</span><span class="sxs-lookup"><span data-stu-id="30204-122">Fedora 28, 27 - 64-bit (`x86_64` or `amd64`)</span></span> 
* <span data-ttu-id="30204-123">Debian 9（64 位，`arm32`）、8.7 或更高版本 - 64 位（`x86_64` 或 `amd64`）</span><span class="sxs-lookup"><span data-stu-id="30204-123">Debian 9 (64-bit, `arm32`), 8.7 or later versions - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="30204-124">Ubuntu 18.04（64 位，`arm32`）、16.04、14.04 - 64 位（`x86_64` 或 `amd64`）</span><span class="sxs-lookup"><span data-stu-id="30204-124">Ubuntu 18.04 (64-bit, `arm32`), 16.04, 14.04 - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="30204-125">Linux Mint 18、17 - 64 位（`x86_64` 或 `amd64`）</span><span class="sxs-lookup"><span data-stu-id="30204-125">Linux Mint 18, 17 - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="30204-126">openSUSE 42.3 或更高版本 - 64 位（`x86_64` 或 `amd64`）</span><span class="sxs-lookup"><span data-stu-id="30204-126">openSUSE 42.3 or later versions - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="30204-127">SUSE Enterprise Linux (SLES) 12 Service Pack 2 或更高版本 - 64 位（`x86_64` 或 `amd64`）</span><span class="sxs-lookup"><span data-stu-id="30204-127">SUSE Enterprise Linux (SLES) 12 Service Pack 2 or later - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="30204-128">Alpine Linux 3.7 或更高版本 - 64 位（`x86_64` 或 `amd64`）</span><span class="sxs-lookup"><span data-stu-id="30204-128">Alpine Linux 3.7 or later versions - 64-bit (`x86_64` or `amd64`)</span></span>

<span data-ttu-id="30204-129">有关 .NET Core 2.1 和 .NET Core 2.2 支持的操作系统、发行版本和版本、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 2.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)和 [.NET Core 2.2 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="30204-129">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) and [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) for the complete list of .NET Core 2.1 and .NET Core 2.2 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="30204-130">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="30204-130">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="30204-131">有关下载链接和详细信息，请参阅 [.NET Core 1.1 下载](https://www.microsoft.com/net/download/dotnet-core/1.1)或 [.NET Core 1.0 下载](https://www.microsoft.com/net/download/dotnet-core/1.0)。</span><span class="sxs-lookup"><span data-stu-id="30204-131">For download links and more information, see [.NET Core 1.1 downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) or [.NET Core 1.0 downloads](https://www.microsoft.com/net/download/dotnet-core/1.0).</span></span>

<span data-ttu-id="30204-132">以下 Linux 64 位（`x86_64` 或 `amd64`）发行版本/版本支持 .NET Core 1.x：</span><span class="sxs-lookup"><span data-stu-id="30204-132">.NET Core 1.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="30204-133">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="30204-133">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="30204-134">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="30204-134">CentOS 7</span></span>
* <span data-ttu-id="30204-135">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="30204-135">Oracle Linux 7</span></span>
* <span data-ttu-id="30204-136">Fedora 28 (.NET Core 1.1)、27</span><span class="sxs-lookup"><span data-stu-id="30204-136">Fedora 28 (.NET Core 1.1), 27</span></span>
* <span data-ttu-id="30204-137">Debian 8.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="30204-137">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="30204-138">Ubuntu 18.04 (.NET Core 1.1)、16.04、14.04</span><span class="sxs-lookup"><span data-stu-id="30204-138">Ubuntu 18.04 (.NET Core 1.1), 16.04, 14.04</span></span>
* <span data-ttu-id="30204-139">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="30204-139">Linux Mint 17</span></span>
* <span data-ttu-id="30204-140">openSUSE 42.3 或更高版本 (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="30204-140">openSUSE 42.3 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="30204-141">有关支持 .NET Core 1.x 的操作系统、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 1.x - 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="30204-141">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-30-preview-1tabnetcore30"></a>[<span data-ttu-id="30204-142">.NET Core 3.0 预览版 1</span><span class="sxs-lookup"><span data-stu-id="30204-142">.NET Core 3.0 Preview 1</span></span>](#tab/netcore30)

<span data-ttu-id="30204-143">.NET Core 3.0 预览版 1 将 Linux 视为单一操作系统。</span><span class="sxs-lookup"><span data-stu-id="30204-143">.NET Core 3.0 Preview 1 treats Linux as a single operating system.</span></span> <span data-ttu-id="30204-144">支持的 Linux 分发都对应有一个 Linux 内部版本（根据芯片体系结构）。</span><span class="sxs-lookup"><span data-stu-id="30204-144">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span> 

<span data-ttu-id="30204-145">有关下载链接和详细信息，请参阅 [.NET Core 3.0 下载](https://dotnet.microsoft.com/download/dotnet-core/3.0)。</span><span class="sxs-lookup"><span data-stu-id="30204-145">For download links and more information, see [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="30204-146">以下 Linux 发行版本/版本支持 .NET Core 3.0 预览版 1。</span><span class="sxs-lookup"><span data-stu-id="30204-146">.NET Core 3.0 Preview 1 is supported on the following Linux distributions/versions.</span></span> 

<span data-ttu-id="30204-147">(OS)</span><span class="sxs-lookup"><span data-stu-id="30204-147">OS</span></span>                            | <span data-ttu-id="30204-148">Version</span><span class="sxs-lookup"><span data-stu-id="30204-148">Version</span></span>               | <span data-ttu-id="30204-149">体系结构</span><span class="sxs-lookup"><span data-stu-id="30204-149">Architectures</span></span>  
------------------------------|-----------------------|----------------
<span data-ttu-id="30204-150">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="30204-150">Red Hat Enterprise Linux</span></span>      | <span data-ttu-id="30204-151">6</span><span class="sxs-lookup"><span data-stu-id="30204-151">6</span></span>                     | <span data-ttu-id="30204-152">X64</span><span class="sxs-lookup"><span data-stu-id="30204-152">x64</span></span>
<span data-ttu-id="30204-153">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="30204-153">Red Hat Enterprise Linux</span></span><br><span data-ttu-id="30204-154">CentOS</span><span class="sxs-lookup"><span data-stu-id="30204-154">CentOS</span></span><br><span data-ttu-id="30204-155">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="30204-155">Oracle Linux</span></span>  | <span data-ttu-id="30204-156">7</span><span class="sxs-lookup"><span data-stu-id="30204-156">7</span></span>                     | <span data-ttu-id="30204-157">X64</span><span class="sxs-lookup"><span data-stu-id="30204-157">x64</span></span>
<span data-ttu-id="30204-158">Fedora</span><span class="sxs-lookup"><span data-stu-id="30204-158">Fedora</span></span>                        | <span data-ttu-id="30204-159">28</span><span class="sxs-lookup"><span data-stu-id="30204-159">28</span></span>                    | <span data-ttu-id="30204-160">X64</span><span class="sxs-lookup"><span data-stu-id="30204-160">x64</span></span>
<span data-ttu-id="30204-161">Debian</span><span class="sxs-lookup"><span data-stu-id="30204-161">Debian</span></span>                        | <span data-ttu-id="30204-162">9</span><span class="sxs-lookup"><span data-stu-id="30204-162">9</span></span>                     | <span data-ttu-id="30204-163">x64、ARM32\*ARM64\*</span><span class="sxs-lookup"><span data-stu-id="30204-163">x64, ARM32\*, ARM64\*</span></span>
<span data-ttu-id="30204-164">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="30204-164">Ubuntu</span></span>                        | <span data-ttu-id="30204-165">16.04+、18.04+</span><span class="sxs-lookup"><span data-stu-id="30204-165">16.04+, 18.04+</span></span>        | <span data-ttu-id="30204-166">x64、ARM32\*ARM64\*</span><span class="sxs-lookup"><span data-stu-id="30204-166">x64, ARM32\*, ARM64\*</span></span>
<span data-ttu-id="30204-167">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="30204-167">Linux Mint</span></span>                    | <span data-ttu-id="30204-168">18</span><span class="sxs-lookup"><span data-stu-id="30204-168">18</span></span>                    | <span data-ttu-id="30204-169">X64</span><span class="sxs-lookup"><span data-stu-id="30204-169">x64</span></span>
<span data-ttu-id="30204-170">openSUSE</span><span class="sxs-lookup"><span data-stu-id="30204-170">openSUSE</span></span>                      | <span data-ttu-id="30204-171">42.3+</span><span class="sxs-lookup"><span data-stu-id="30204-171">42.3+</span></span>                 | <span data-ttu-id="30204-172">X64</span><span class="sxs-lookup"><span data-stu-id="30204-172">x64</span></span>
<span data-ttu-id="30204-173">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="30204-173">SUSE Enterprise Linux (SLES)</span></span>  | <span data-ttu-id="30204-174">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="30204-174">12 SP2+</span></span>               | <span data-ttu-id="30204-175">X64</span><span class="sxs-lookup"><span data-stu-id="30204-175">x64</span></span>
<span data-ttu-id="30204-176">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="30204-176">Alpine Linux</span></span>                  | <span data-ttu-id="30204-177">3.8+</span><span class="sxs-lookup"><span data-stu-id="30204-177">3.8+</span></span>                  | <span data-ttu-id="30204-178">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="30204-178">x64, ARM64</span></span>

<span data-ttu-id="30204-179">\* ARM32 和 ARM64 支持 Debian 9 和 Ubuntu 16.04 及以上版本。</span><span class="sxs-lookup"><span data-stu-id="30204-179">\* ARM32 and ARM64 support starts with Debian 9 and Ubuntu 16.04.</span></span> <span data-ttu-id="30204-180">ARM 芯片不支持这些发行版本的早期版本。</span><span class="sxs-lookup"><span data-stu-id="30204-180">Earlier versions of those distros are not supported on ARM chips.</span></span>

<span data-ttu-id="30204-181">有关 .NET Core 3.0 支持的操作系统、发行版本和版本、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 3.0 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="30204-181">See [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) for the complete list of .NET Core 3.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="30204-182">有关如何在 ARM64 上安装 .NET Core 3.0 的详细信息，请参阅[在 Linux ARM64 上安装 .NET Core 3.0](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)。</span><span class="sxs-lookup"><span data-stu-id="30204-182">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="30204-183">Linux 发行版本依赖项</span><span class="sxs-lookup"><span data-stu-id="30204-183">Linux distribution dependencies</span></span>

<span data-ttu-id="30204-184">以下各项用作示例。</span><span class="sxs-lookup"><span data-stu-id="30204-184">The following are intended to be examples.</span></span> <span data-ttu-id="30204-185">确切的版本和名称可能因所选 Linux 发行版本略有不同。</span><span class="sxs-lookup"><span data-stu-id="30204-185">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="30204-186">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="30204-186">Ubuntu</span></span>

<span data-ttu-id="30204-187">Ubuntu 发行版本需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="30204-187">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="30204-188">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="30204-188">liblttng-ust0</span></span>
* <span data-ttu-id="30204-189">libcurl3（针对 14.x 和 16.x）</span><span class="sxs-lookup"><span data-stu-id="30204-189">libcurl3 (for 14.x and 16.x)</span></span>
* <span data-ttu-id="30204-190">libcurl4（针对 18.x）</span><span class="sxs-lookup"><span data-stu-id="30204-190">libcurl4 (for 18.x)</span></span>
* <span data-ttu-id="30204-191">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="30204-191">libssl1.0.0</span></span>
* <span data-ttu-id="30204-192">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="30204-192">libkrb5-3</span></span>
* <span data-ttu-id="30204-193">zlib1g</span><span class="sxs-lookup"><span data-stu-id="30204-193">zlib1g</span></span>
* <span data-ttu-id="30204-194">libicu52（针对 14.x）</span><span class="sxs-lookup"><span data-stu-id="30204-194">libicu52 (for 14.x)</span></span>
* <span data-ttu-id="30204-195">libicu55（针对 16.x）</span><span class="sxs-lookup"><span data-stu-id="30204-195">libicu55 (for 16.x)</span></span>
* <span data-ttu-id="30204-196">libicu57（针对 17.x）</span><span class="sxs-lookup"><span data-stu-id="30204-196">libicu57 (for 17.x)</span></span>
* <span data-ttu-id="30204-197">libicu60（针对 18.x）</span><span class="sxs-lookup"><span data-stu-id="30204-197">libicu60 (for 18.x)</span></span>

<span data-ttu-id="30204-198">对于 .NET Core 2.1 之前的版本，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="30204-198">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

* <span data-ttu-id="30204-199">libunwind8</span><span class="sxs-lookup"><span data-stu-id="30204-199">libunwind8</span></span>
* <span data-ttu-id="30204-200">libuuid1</span><span class="sxs-lookup"><span data-stu-id="30204-200">libuuid1</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="30204-201">CentOS 和 Fedora</span><span class="sxs-lookup"><span data-stu-id="30204-201">CentOS and Fedora</span></span>

<span data-ttu-id="30204-202">CentOS 发行版本需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="30204-202">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="30204-203">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="30204-203">lttng-ust</span></span>
* <span data-ttu-id="30204-204">libcurl</span><span class="sxs-lookup"><span data-stu-id="30204-204">libcurl</span></span>
* <span data-ttu-id="30204-205">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="30204-205">openssl-libs</span></span>
* <span data-ttu-id="30204-206">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="30204-206">krb5-libs</span></span>
* <span data-ttu-id="30204-207">libicu</span><span class="sxs-lookup"><span data-stu-id="30204-207">libicu</span></span>
* <span data-ttu-id="30204-208">zlib</span><span class="sxs-lookup"><span data-stu-id="30204-208">zlib</span></span>

<span data-ttu-id="30204-209">Fedora 用户：如果 openssl 的版本为 1.1 及以上版本，则需要安装 compat-openssl10。</span><span class="sxs-lookup"><span data-stu-id="30204-209">Fedora users: If your openssl's version >= 1.1, you'll need to install compat-openssl10.</span></span>

<span data-ttu-id="30204-210">对于 .NET Core 2.1 之前的版本，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="30204-210">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

* <span data-ttu-id="30204-211">libunwind</span><span class="sxs-lookup"><span data-stu-id="30204-211">libunwind</span></span>
* <span data-ttu-id="30204-212">libuuid</span><span class="sxs-lookup"><span data-stu-id="30204-212">libuuid</span></span>

<span data-ttu-id="30204-213">有关依赖项的详细信息，请参阅[独立式 Linux 应用程序](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="30204-213">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="30204-214">使用本机安装程序安装 .NET Core 依赖项</span><span class="sxs-lookup"><span data-stu-id="30204-214">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="30204-215">.NET Core 本机安装程序适用于支持的 Linux 发行版本/版本。</span><span class="sxs-lookup"><span data-stu-id="30204-215">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="30204-216">本机安装程序需要拥有对服务器的管理员 (sudo) 访问权限。</span><span class="sxs-lookup"><span data-stu-id="30204-216">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="30204-217">使用本机安装程序的优势在于，可以安装所有 .NET Core 本机依赖项。</span><span class="sxs-lookup"><span data-stu-id="30204-217">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="30204-218">本机安装程序还会在整个系统内安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="30204-218">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="30204-219">在 Linux 上，安装程序包有两种使用方式：</span><span class="sxs-lookup"><span data-stu-id="30204-219">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="30204-220">使用基于源的包管理器，如适用于 Ubuntu 的 apt-get，或适用于 CentOS/RHEL 的 yum。</span><span class="sxs-lookup"><span data-stu-id="30204-220">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="30204-221">使用包本身（DEB 或 RPM）。</span><span class="sxs-lookup"><span data-stu-id="30204-221">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="30204-222">使用 .NET Core 安装程序脚本编写安装脚本</span><span class="sxs-lookup"><span data-stu-id="30204-222">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="30204-223">[dotnet-install 脚本](./tools/dotnet-install-script.md)用于执行 CLI 工具链和共享运行时的非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="30204-223">The [dotnet-install scripts](./tools/dotnet-install-script.md) are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="30204-224">可通过 <https://dot.net/v1/dotnet-install.sh> 下载脚本。</span><span class="sxs-lookup"><span data-stu-id="30204-224">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="30204-225">此脚本会默认安装最新的“LTS”版本，当前为 .NET Core 1.1。</span><span class="sxs-lookup"><span data-stu-id="30204-225">The script defaults to installing the latest "LTS" version, which is currently .NET Core 1.1.</span></span> <span data-ttu-id="30204-226">要安装 .NET Core 2.1，请使用以下开关运行脚本：</span><span class="sxs-lookup"><span data-stu-id="30204-226">To install .NET Core 2.1, run the script with the following switch:</span></span>

```console
./dotnet-install.sh -c Current
```

<span data-ttu-id="30204-227">安装程序 bash 脚本用于自动化方案和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="30204-227">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="30204-228">此脚本也读取 PowerShell 开关，因此可以与 Linux/OS X 系统上的脚本结合使用。</span><span class="sxs-lookup"><span data-stu-id="30204-228">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="30204-229">疑难解答</span><span class="sxs-lookup"><span data-stu-id="30204-229">Troubleshoot</span></span>

<span data-ttu-id="30204-230">若对在支持的 Linux 分发/版本上安装 .NET Core 有疑问，请参阅下方你所安装的分发/版本的相应主题：</span><span class="sxs-lookup"><span data-stu-id="30204-230">If you have problems with a .NET Core installation on a supported Linux distribution/version, consult the following topics for your installed distributions/versions:</span></span>

* [<span data-ttu-id="30204-231">.NET Core 3.0 已知问题</span><span class="sxs-lookup"><span data-stu-id="30204-231">.NET Core 3.0 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/3.0)
* [<span data-ttu-id="30204-232">.NET Core 2.2 已知问题</span><span class="sxs-lookup"><span data-stu-id="30204-232">.NET Core 2.2 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.2)
* [<span data-ttu-id="30204-233">.NET Core 2.1 已知问题</span><span class="sxs-lookup"><span data-stu-id="30204-233">.NET Core 2.1 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.1)
* [<span data-ttu-id="30204-234">.NET Core 1.1 已知问题</span><span class="sxs-lookup"><span data-stu-id="30204-234">.NET Core 1.1 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.1)
* [<span data-ttu-id="30204-235">.NET Core 1.0 已知问题</span><span class="sxs-lookup"><span data-stu-id="30204-235">.NET Core 1.0 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0)
