---
title: Linux 上 .NET Core 的先决条件
description: 支持的 Linux 版本和 .NET Core 依赖项，用于在 Linux 计算机上开发、部署和运行 .NET Core 应用程序。
author: leecow
ms.author: leecow
ms.date: 09/25/2019
ms.openlocfilehash: 4c5d79459c9d69111ca6452d9305f0deb37212b8
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591702"
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="7fee0-103">Linux 上 .NET Core 的先决条件</span><span class="sxs-lookup"><span data-stu-id="7fee0-103">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="7fee0-104">本文介绍了在 Linux 上开发 .NET Core 应用程序所需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="7fee0-104">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="7fee0-105">支持的 Linux 发行版本/版本和依赖项适用于在 Linux 上开发 .NET Core 应用程序的两种方法：</span><span class="sxs-lookup"><span data-stu-id="7fee0-105">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="7fee0-106">结合使用命令行和常用编辑器</span><span class="sxs-lookup"><span data-stu-id="7fee0-106">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="7fee0-107">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="7fee0-107">Visual Studio Code</span></span>](https://code.visualstudio.com/)

> [!NOTE]
> <span data-ttu-id="7fee0-108">生产服务器/环境不需要 .NET Core SDK 包。</span><span class="sxs-lookup"><span data-stu-id="7fee0-108">The .NET Core SDK package is not required for production servers/environments.</span></span> <span data-ttu-id="7fee0-109">部署到生产环境的应用只需要 .NET Core 运行时包。</span><span class="sxs-lookup"><span data-stu-id="7fee0-109">Only the .NET Core runtime package is needed for apps deployed to production environments.</span></span> <span data-ttu-id="7fee0-110">.NET Core 运行时与应用一同部署为独立部署的一部分，但是，对于依赖框架的部署应用，它必须单独部署。</span><span class="sxs-lookup"><span data-stu-id="7fee0-110">The .NET Core runtime is deployed with apps as part of a self-contained deployment, however, it must be deployed for Framework-dependent deployed apps separately.</span></span> <span data-ttu-id="7fee0-111">有关依赖框架和独立部署类型的更多信息，请参阅 [.NET Core 应用程序部署](./deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="7fee0-111">For more information about framework-dependent and self-contained deployment types, see [.NET Core application deployment](./deploying/index.md).</span></span> <span data-ttu-id="7fee0-112">另请参阅[独立式 Linux 应用程序](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)，了解特定准则。</span><span class="sxs-lookup"><span data-stu-id="7fee0-112">Also see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) for specific guidelines.</span></span>

## <a name="supported-linux-versions"></a><span data-ttu-id="7fee0-113">支持的 Linux 版本</span><span class="sxs-lookup"><span data-stu-id="7fee0-113">Supported Linux versions</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="7fee0-114">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="7fee0-114">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="7fee0-115">.NET Core 3.0 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="7fee0-115">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="7fee0-116">支持的 Linux 分发都对应有一个 Linux 内部版本（根据芯片体系结构）。</span><span class="sxs-lookup"><span data-stu-id="7fee0-116">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span> 

<span data-ttu-id="7fee0-117">有关下载链接和详细信息，请参阅 [.NET Core 3.0 下载](https://dotnet.microsoft.com/download/dotnet-core/3.0)。</span><span class="sxs-lookup"><span data-stu-id="7fee0-117">For download links and more information, see [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="7fee0-118">以下 Linux 发行版本/版本支持 .NET Core 3.0：</span><span class="sxs-lookup"><span data-stu-id="7fee0-118">.NET Core 3.0 is supported on the following Linux distributions/versions):</span></span>

> [!NOTE]
> <span data-ttu-id="7fee0-119">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="7fee0-119">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7fee0-120">(OS)</span><span class="sxs-lookup"><span data-stu-id="7fee0-120">OS</span></span>                             | <span data-ttu-id="7fee0-121">Version</span><span class="sxs-lookup"><span data-stu-id="7fee0-121">Version</span></span>               | <span data-ttu-id="7fee0-122">体系结构</span><span class="sxs-lookup"><span data-stu-id="7fee0-122">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="7fee0-123">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="7fee0-123">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="7fee0-124">6+、7</span><span class="sxs-lookup"><span data-stu-id="7fee0-124">6+, 7</span></span>                 | <span data-ttu-id="7fee0-125">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-125">x64</span></span> |
| <span data-ttu-id="7fee0-126">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="7fee0-126">Oracle Linux</span></span>                   | <span data-ttu-id="7fee0-127">7</span><span class="sxs-lookup"><span data-stu-id="7fee0-127">7</span></span>                     | <span data-ttu-id="7fee0-128">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-128">x64</span></span> |
| <span data-ttu-id="7fee0-129">CentOS</span><span class="sxs-lookup"><span data-stu-id="7fee0-129">CentOS</span></span>                         | <span data-ttu-id="7fee0-130">7</span><span class="sxs-lookup"><span data-stu-id="7fee0-130">7</span></span>                     | <span data-ttu-id="7fee0-131">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-131">x64</span></span> |
| <span data-ttu-id="7fee0-132">Fedora</span><span class="sxs-lookup"><span data-stu-id="7fee0-132">Fedora</span></span>                         | <span data-ttu-id="7fee0-133">29+</span><span class="sxs-lookup"><span data-stu-id="7fee0-133">29+</span></span>                   | <span data-ttu-id="7fee0-134">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-134">x64</span></span> |
| <span data-ttu-id="7fee0-135">Debian</span><span class="sxs-lookup"><span data-stu-id="7fee0-135">Debian</span></span>                         | <span data-ttu-id="7fee0-136">9+</span><span class="sxs-lookup"><span data-stu-id="7fee0-136">9+</span></span>                    | <span data-ttu-id="7fee0-137">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="7fee0-137">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="7fee0-138">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="7fee0-138">Ubuntu</span></span>                         | <span data-ttu-id="7fee0-139">16.04+</span><span class="sxs-lookup"><span data-stu-id="7fee0-139">16.04+</span></span>                | <span data-ttu-id="7fee0-140">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="7fee0-140">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="7fee0-141">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="7fee0-141">Linux Mint</span></span>                     | <span data-ttu-id="7fee0-142">18+</span><span class="sxs-lookup"><span data-stu-id="7fee0-142">18+</span></span>                   | <span data-ttu-id="7fee0-143">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-143">x64</span></span> |
| <span data-ttu-id="7fee0-144">openSUSE</span><span class="sxs-lookup"><span data-stu-id="7fee0-144">openSUSE</span></span>                       | <span data-ttu-id="7fee0-145">15+</span><span class="sxs-lookup"><span data-stu-id="7fee0-145">15+</span></span>                   | <span data-ttu-id="7fee0-146">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-146">x64</span></span> |
| <span data-ttu-id="7fee0-147">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="7fee0-147">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="7fee0-148">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="7fee0-148">12 SP2+</span></span>               | <span data-ttu-id="7fee0-149">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-149">x64</span></span> |
| <span data-ttu-id="7fee0-150">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="7fee0-150">Alpine Linux</span></span>                   | <span data-ttu-id="7fee0-151">3.8+</span><span class="sxs-lookup"><span data-stu-id="7fee0-151">3.8+</span></span>                  | <span data-ttu-id="7fee0-152">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="7fee0-152">x64, ARM64</span></span> |

<span data-ttu-id="7fee0-153">有关 .NET Core 3.0 支持的操作系统、发行版本和版本、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 3.0 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="7fee0-153">See [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) for the complete list of .NET Core 3.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="7fee0-154">有关如何在 ARM64 上安装 .NET Core 3.0 的详细信息，请参阅[在 Linux ARM64 上安装 .NET Core 3.0](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)。</span><span class="sxs-lookup"><span data-stu-id="7fee0-154">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="7fee0-155">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="7fee0-155">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="7fee0-156">.NET Core 2.2 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="7fee0-156">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="7fee0-157">支持的 Linux 分发都对应有一个 Linux 内部版本（根据芯片体系结构）。</span><span class="sxs-lookup"><span data-stu-id="7fee0-157">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="7fee0-158">有关下载链接和详细信息，请参阅 [.NET Core 2.2 下载](https://dotnet.microsoft.com/download/dotnet-core/2.2)。</span><span class="sxs-lookup"><span data-stu-id="7fee0-158">For download links and more information, see [.NET Core 2.2 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.2).</span></span>

<span data-ttu-id="7fee0-159">以下 Linux 发行版本/版本支持 .NET Core 2.2：</span><span class="sxs-lookup"><span data-stu-id="7fee0-159">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="7fee0-160">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="7fee0-160">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7fee0-161">(OS)</span><span class="sxs-lookup"><span data-stu-id="7fee0-161">OS</span></span>                             |  <span data-ttu-id="7fee0-162">Version</span><span class="sxs-lookup"><span data-stu-id="7fee0-162">Version</span></span>                |  <span data-ttu-id="7fee0-163">体系结构</span><span class="sxs-lookup"><span data-stu-id="7fee0-163">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="7fee0-164">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="7fee0-164">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="7fee0-165">6、7</span><span class="sxs-lookup"><span data-stu-id="7fee0-165">6, 7</span></span>                   | <span data-ttu-id="7fee0-166">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-166">x64</span></span> |
| <span data-ttu-id="7fee0-167">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="7fee0-167">Oracle Linux</span></span>                   |  <span data-ttu-id="7fee0-168">7</span><span class="sxs-lookup"><span data-stu-id="7fee0-168">7</span></span>                      | <span data-ttu-id="7fee0-169">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-169">x64</span></span> |
| <span data-ttu-id="7fee0-170">CentOS</span><span class="sxs-lookup"><span data-stu-id="7fee0-170">CentOS</span></span>                         |  <span data-ttu-id="7fee0-171">7</span><span class="sxs-lookup"><span data-stu-id="7fee0-171">7</span></span>                      | <span data-ttu-id="7fee0-172">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-172">x64</span></span> |
| <span data-ttu-id="7fee0-173">Fedora</span><span class="sxs-lookup"><span data-stu-id="7fee0-173">Fedora</span></span>                         |  <span data-ttu-id="7fee0-174">29、30</span><span class="sxs-lookup"><span data-stu-id="7fee0-174">29, 30</span></span>                 | <span data-ttu-id="7fee0-175">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-175">x64</span></span> |
| <span data-ttu-id="7fee0-176">Debian</span><span class="sxs-lookup"><span data-stu-id="7fee0-176">Debian</span></span>                         |  <span data-ttu-id="7fee0-177">9</span><span class="sxs-lookup"><span data-stu-id="7fee0-177">9</span></span>                      | <span data-ttu-id="7fee0-178">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="7fee0-178">x64, ARM32</span></span> |
| <span data-ttu-id="7fee0-179">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="7fee0-179">Ubuntu</span></span>                         |  <span data-ttu-id="7fee0-180">16.04、18.04、18.10</span><span class="sxs-lookup"><span data-stu-id="7fee0-180">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="7fee0-181">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="7fee0-181">x64, ARM32</span></span> |
| <span data-ttu-id="7fee0-182">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="7fee0-182">Linux Mint</span></span>                     |  <span data-ttu-id="7fee0-183">17、18</span><span class="sxs-lookup"><span data-stu-id="7fee0-183">17, 18</span></span>                 | <span data-ttu-id="7fee0-184">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-184">x64</span></span> |
| <span data-ttu-id="7fee0-185">openSUSE</span><span class="sxs-lookup"><span data-stu-id="7fee0-185">openSUSE</span></span>                       |  <span data-ttu-id="7fee0-186">15+</span><span class="sxs-lookup"><span data-stu-id="7fee0-186">15+</span></span>                    | <span data-ttu-id="7fee0-187">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-187">x64</span></span> |
| <span data-ttu-id="7fee0-188">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="7fee0-188">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="7fee0-189">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="7fee0-189">12 SP2+</span></span>                | <span data-ttu-id="7fee0-190">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-190">x64</span></span> |
| <span data-ttu-id="7fee0-191">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="7fee0-191">Alpine Linux</span></span>                   |  <span data-ttu-id="7fee0-192">3.7+</span><span class="sxs-lookup"><span data-stu-id="7fee0-192">3.7+</span></span>                   | <span data-ttu-id="7fee0-193">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-193">x64</span></span> |

<span data-ttu-id="7fee0-194">要在完整列表中了解 .NET Core 2.2 支持的操作系统、发行版本和版本、生命周期策略链接和不支持的 OS 版本，请参阅 [.NET Core 2.2 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="7fee0-194">See [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) for the complete list of .NET Core 2.2 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="7fee0-195">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7fee0-195">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="7fee0-196">.NET Core 2.1 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="7fee0-196">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="7fee0-197">支持的 Linux 分发都对应有一个 Linux 内部版本（根据芯片体系结构）。</span><span class="sxs-lookup"><span data-stu-id="7fee0-197">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="7fee0-198">有关下载链接和详细信息，请参阅 [.NET Core 2.1 下载](https://dotnet.microsoft.com/download/dotnet-core/2.1)。</span><span class="sxs-lookup"><span data-stu-id="7fee0-198">For download links and more information, see [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

<span data-ttu-id="7fee0-199">以下 Linux 发行版本/版本支持 .NET Core 2.1：</span><span class="sxs-lookup"><span data-stu-id="7fee0-199">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

| <span data-ttu-id="7fee0-200">(OS)</span><span class="sxs-lookup"><span data-stu-id="7fee0-200">OS</span></span>                             |  <span data-ttu-id="7fee0-201">Version</span><span class="sxs-lookup"><span data-stu-id="7fee0-201">Version</span></span>                |  <span data-ttu-id="7fee0-202">体系结构</span><span class="sxs-lookup"><span data-stu-id="7fee0-202">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="7fee0-203">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="7fee0-203">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="7fee0-204">6、7、8</span><span class="sxs-lookup"><span data-stu-id="7fee0-204">6, 7, 8</span></span>                | <span data-ttu-id="7fee0-205">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-205">x64</span></span> |
| <span data-ttu-id="7fee0-206">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="7fee0-206">Oracle Linux</span></span>                   |  <span data-ttu-id="7fee0-207">7</span><span class="sxs-lookup"><span data-stu-id="7fee0-207">7</span></span>                      | <span data-ttu-id="7fee0-208">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-208">x64</span></span> |
| <span data-ttu-id="7fee0-209">CentOS</span><span class="sxs-lookup"><span data-stu-id="7fee0-209">CentOS</span></span>                         |  <span data-ttu-id="7fee0-210">7</span><span class="sxs-lookup"><span data-stu-id="7fee0-210">7</span></span>                      | <span data-ttu-id="7fee0-211">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-211">x64</span></span> |
| <span data-ttu-id="7fee0-212">Fedora</span><span class="sxs-lookup"><span data-stu-id="7fee0-212">Fedora</span></span>                         |  <span data-ttu-id="7fee0-213">29、30</span><span class="sxs-lookup"><span data-stu-id="7fee0-213">29, 30</span></span>                 | <span data-ttu-id="7fee0-214">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-214">x64</span></span> |
| <span data-ttu-id="7fee0-215">Debian</span><span class="sxs-lookup"><span data-stu-id="7fee0-215">Debian</span></span>                         |  <span data-ttu-id="7fee0-216">9</span><span class="sxs-lookup"><span data-stu-id="7fee0-216">9</span></span>                      | <span data-ttu-id="7fee0-217">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="7fee0-217">x64, ARM32</span></span> |
| <span data-ttu-id="7fee0-218">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="7fee0-218">Ubuntu</span></span>                         |  <span data-ttu-id="7fee0-219">16.04、18.04、19.04</span><span class="sxs-lookup"><span data-stu-id="7fee0-219">16.04, 18.04, 19.04</span></span>    | <span data-ttu-id="7fee0-220">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="7fee0-220">x64, ARM32</span></span> |
| <span data-ttu-id="7fee0-221">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="7fee0-221">Linux Mint</span></span>                     |  <span data-ttu-id="7fee0-222">17、18</span><span class="sxs-lookup"><span data-stu-id="7fee0-222">17, 18</span></span>                 | <span data-ttu-id="7fee0-223">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-223">x64</span></span> |
| <span data-ttu-id="7fee0-224">openSUSE</span><span class="sxs-lookup"><span data-stu-id="7fee0-224">openSUSE</span></span>                       |  <span data-ttu-id="7fee0-225">42.3+</span><span class="sxs-lookup"><span data-stu-id="7fee0-225">42.3+</span></span>                  | <span data-ttu-id="7fee0-226">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-226">x64</span></span> |
| <span data-ttu-id="7fee0-227">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="7fee0-227">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="7fee0-228">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="7fee0-228">12 SP2+</span></span>                | <span data-ttu-id="7fee0-229">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-229">x64</span></span> |
| <span data-ttu-id="7fee0-230">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="7fee0-230">Alpine Linux</span></span>                   |  <span data-ttu-id="7fee0-231">3.7+</span><span class="sxs-lookup"><span data-stu-id="7fee0-231">3.7+</span></span>                   | <span data-ttu-id="7fee0-232">X64</span><span class="sxs-lookup"><span data-stu-id="7fee0-232">x64</span></span> |

<span data-ttu-id="7fee0-233">有关 .NET Core 2.1 支持的操作系统、发行版本和版本、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 2.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="7fee0-233">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) for the complete list of .NET Core 2.1 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="7fee0-234">Linux 发行版本依赖项</span><span class="sxs-lookup"><span data-stu-id="7fee0-234">Linux distribution dependencies</span></span>

<span data-ttu-id="7fee0-235">以下各项用作示例。</span><span class="sxs-lookup"><span data-stu-id="7fee0-235">The following are intended to be examples.</span></span> <span data-ttu-id="7fee0-236">确切的版本和名称可能因所选 Linux 发行版本略有不同。</span><span class="sxs-lookup"><span data-stu-id="7fee0-236">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="7fee0-237">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="7fee0-237">Ubuntu</span></span>

<span data-ttu-id="7fee0-238">Ubuntu 发行版本需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="7fee0-238">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="7fee0-239">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="7fee0-239">liblttng-ust0</span></span>
* <span data-ttu-id="7fee0-240">libcurl3（针对 14.x 和 16.x）</span><span class="sxs-lookup"><span data-stu-id="7fee0-240">libcurl3 (for 14.x and 16.x)</span></span>
* <span data-ttu-id="7fee0-241">libcurl4（针对 18.x）</span><span class="sxs-lookup"><span data-stu-id="7fee0-241">libcurl4 (for 18.x)</span></span>
* <span data-ttu-id="7fee0-242">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="7fee0-242">libssl1.0.0</span></span>
* <span data-ttu-id="7fee0-243">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="7fee0-243">libkrb5-3</span></span>
* <span data-ttu-id="7fee0-244">zlib1g</span><span class="sxs-lookup"><span data-stu-id="7fee0-244">zlib1g</span></span>
* <span data-ttu-id="7fee0-245">libicu52（针对 14.x）</span><span class="sxs-lookup"><span data-stu-id="7fee0-245">libicu52 (for 14.x)</span></span>
* <span data-ttu-id="7fee0-246">libicu55（针对 16.x）</span><span class="sxs-lookup"><span data-stu-id="7fee0-246">libicu55 (for 16.x)</span></span>
* <span data-ttu-id="7fee0-247">libicu57（针对 17.x）</span><span class="sxs-lookup"><span data-stu-id="7fee0-247">libicu57 (for 17.x)</span></span>
* <span data-ttu-id="7fee0-248">libicu60（针对 18.x）</span><span class="sxs-lookup"><span data-stu-id="7fee0-248">libicu60 (for 18.x)</span></span>

<span data-ttu-id="7fee0-249">对于 .NET Core 2.1 之前的版本，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="7fee0-249">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

* <span data-ttu-id="7fee0-250">libunwind8</span><span class="sxs-lookup"><span data-stu-id="7fee0-250">libunwind8</span></span>
* <span data-ttu-id="7fee0-251">libuuid1</span><span class="sxs-lookup"><span data-stu-id="7fee0-251">libuuid1</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="7fee0-252">CentOS 和 Fedora</span><span class="sxs-lookup"><span data-stu-id="7fee0-252">CentOS and Fedora</span></span>

<span data-ttu-id="7fee0-253">CentOS 发行版本需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="7fee0-253">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="7fee0-254">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="7fee0-254">lttng-ust</span></span>
* <span data-ttu-id="7fee0-255">libcurl</span><span class="sxs-lookup"><span data-stu-id="7fee0-255">libcurl</span></span>
* <span data-ttu-id="7fee0-256">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="7fee0-256">openssl-libs</span></span>
* <span data-ttu-id="7fee0-257">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="7fee0-257">krb5-libs</span></span>
* <span data-ttu-id="7fee0-258">libicu</span><span class="sxs-lookup"><span data-stu-id="7fee0-258">libicu</span></span>
* <span data-ttu-id="7fee0-259">zlib</span><span class="sxs-lookup"><span data-stu-id="7fee0-259">zlib</span></span>

<span data-ttu-id="7fee0-260">Fedora 用户：如果 openssl 的版本为 1.1 及以上版本，则需要安装 compat-openssl10。</span><span class="sxs-lookup"><span data-stu-id="7fee0-260">Fedora users: If your openssl's version >= 1.1, you'll need to install compat-openssl10.</span></span>

<span data-ttu-id="7fee0-261">对于 .NET Core 2.1 之前的版本，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="7fee0-261">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

* <span data-ttu-id="7fee0-262">libunwind</span><span class="sxs-lookup"><span data-stu-id="7fee0-262">libunwind</span></span>
* <span data-ttu-id="7fee0-263">libuuid</span><span class="sxs-lookup"><span data-stu-id="7fee0-263">libuuid</span></span>

<span data-ttu-id="7fee0-264">有关依赖项的详细信息，请参阅[独立式 Linux 应用程序](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="7fee0-264">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="7fee0-265">使用本机安装程序安装 .NET Core 依赖项</span><span class="sxs-lookup"><span data-stu-id="7fee0-265">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="7fee0-266">.NET Core 本机安装程序适用于支持的 Linux 发行版本/版本。</span><span class="sxs-lookup"><span data-stu-id="7fee0-266">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="7fee0-267">本机安装程序需要拥有对服务器的管理员 (sudo) 访问权限。</span><span class="sxs-lookup"><span data-stu-id="7fee0-267">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="7fee0-268">使用本机安装程序的优势在于，可以安装所有 .NET Core 本机依赖项。</span><span class="sxs-lookup"><span data-stu-id="7fee0-268">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="7fee0-269">本机安装程序还会在整个系统内安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="7fee0-269">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="7fee0-270">在 Linux 上，安装程序包有两种使用方式：</span><span class="sxs-lookup"><span data-stu-id="7fee0-270">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="7fee0-271">使用基于源的包管理器，如适用于 Ubuntu 的 apt-get，或适用于 CentOS/RHEL 的 yum。</span><span class="sxs-lookup"><span data-stu-id="7fee0-271">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="7fee0-272">使用包本身（DEB 或 RPM）。</span><span class="sxs-lookup"><span data-stu-id="7fee0-272">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="7fee0-273">使用 .NET Core 安装程序脚本编写安装脚本</span><span class="sxs-lookup"><span data-stu-id="7fee0-273">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="7fee0-274">[dotnet-install 脚本](./tools/dotnet-install-script.md)用于执行 CLI 工具链和共享运行时的非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="7fee0-274">The [dotnet-install scripts](./tools/dotnet-install-script.md) are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="7fee0-275">可通过 <https://dot.net/v1/dotnet-install.sh> 下载脚本。</span><span class="sxs-lookup"><span data-stu-id="7fee0-275">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="7fee0-276">此脚本会默认安装最新的“LTS”版本，当前为 .NET Core 1.1。</span><span class="sxs-lookup"><span data-stu-id="7fee0-276">The script defaults to installing the latest "LTS" version, which is currently .NET Core 1.1.</span></span> <span data-ttu-id="7fee0-277">要安装 .NET Core 2.1，请使用以下开关运行脚本：</span><span class="sxs-lookup"><span data-stu-id="7fee0-277">To install .NET Core 2.1, run the script with the following switch:</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="7fee0-278">安装程序 bash 脚本用于自动化方案和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="7fee0-278">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="7fee0-279">此脚本也读取 PowerShell 开关，因此可以与 Linux/OS X 系统上的脚本结合使用。</span><span class="sxs-lookup"><span data-stu-id="7fee0-279">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="7fee0-280">疑难解答</span><span class="sxs-lookup"><span data-stu-id="7fee0-280">Troubleshoot</span></span>

<span data-ttu-id="7fee0-281">若对在支持的 Linux 分发/版本上安装 .NET Core 有疑问，请参阅下方你所安装的分发/版本的相应主题：</span><span class="sxs-lookup"><span data-stu-id="7fee0-281">If you have problems with a .NET Core installation on a supported Linux distribution/version, consult the following topics for your installed distributions/versions:</span></span>

* [<span data-ttu-id="7fee0-282">.NET Core 3.0 已知问题</span><span class="sxs-lookup"><span data-stu-id="7fee0-282">.NET Core 3.0 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/3.0)
* [<span data-ttu-id="7fee0-283">.NET Core 2.2 已知问题</span><span class="sxs-lookup"><span data-stu-id="7fee0-283">.NET Core 2.2 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.2)
* [<span data-ttu-id="7fee0-284">.NET Core 2.1 已知问题</span><span class="sxs-lookup"><span data-stu-id="7fee0-284">.NET Core 2.1 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.1)
* [<span data-ttu-id="7fee0-285">.NET Core 1.1 已知问题</span><span class="sxs-lookup"><span data-stu-id="7fee0-285">.NET Core 1.1 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.1)
* [<span data-ttu-id="7fee0-286">.NET Core 1.0 已知问题</span><span class="sxs-lookup"><span data-stu-id="7fee0-286">.NET Core 1.0 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0)
