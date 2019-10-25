---
title: Linux 上 .NET Core 的先决条件
description: 支持的 Linux 版本和 .NET Core 依赖项，用于在 Linux 计算机上开发、部署和运行 .NET Core 应用程序。
author: leecow
ms.author: leecow
ms.date: 10/11/2019
ms.openlocfilehash: 0e798e86fcf88a1b7a67f50c2301e10ad725fad8
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72521485"
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="c4b6b-103">Linux 上 .NET Core 的先决条件</span><span class="sxs-lookup"><span data-stu-id="c4b6b-103">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="c4b6b-104">本文介绍了在 Linux 上开发 .NET Core 应用程序所需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-104">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="c4b6b-105">支持的 Linux 发行版本/版本和依赖项适用于在 Linux 上开发 .NET Core 应用程序的两种方法：</span><span class="sxs-lookup"><span data-stu-id="c4b6b-105">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

- [<span data-ttu-id="c4b6b-106">结合使用命令行和常用编辑器</span><span class="sxs-lookup"><span data-stu-id="c4b6b-106">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
- [<span data-ttu-id="c4b6b-107">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c4b6b-107">Visual Studio Code</span></span>](https://code.visualstudio.com/)

> [!NOTE]
> <span data-ttu-id="c4b6b-108">生产服务器/环境不需要 .NET Core SDK 包。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-108">The .NET Core SDK package is not required for production servers/environments.</span></span> <span data-ttu-id="c4b6b-109">部署到生产环境的应用只需要 .NET Core 运行时包。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-109">Only the .NET Core runtime package is needed for apps deployed to production environments.</span></span> <span data-ttu-id="c4b6b-110">.NET Core 运行时与应用一同部署为独立部署的一部分，但是，对于依赖框架的部署应用，它必须单独部署。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-110">The .NET Core runtime is deployed with apps as part of a self-contained deployment, however, it must be deployed for Framework-dependent deployed apps separately.</span></span> <span data-ttu-id="c4b6b-111">有关依赖框架和独立部署类型的更多信息，请参阅 [.NET Core 应用程序部署](./deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-111">For more information about framework-dependent and self-contained deployment types, see [.NET Core application deployment](./deploying/index.md).</span></span> <span data-ttu-id="c4b6b-112">另请参阅[独立式 Linux 应用程序](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)，了解特定准则。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-112">Also see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) for specific guidelines.</span></span>

## <a name="supported-linux-versions"></a><span data-ttu-id="c4b6b-113">支持的 Linux 版本</span><span class="sxs-lookup"><span data-stu-id="c4b6b-113">Supported Linux versions</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="c4b6b-114">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c4b6b-114">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="c4b6b-115">.NET Core 3.0 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-115">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="c4b6b-116">支持的 Linux 分发都对应有一个 Linux 内部版本（根据芯片体系结构）。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-116">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span> 

<span data-ttu-id="c4b6b-117">有关下载链接和详细信息，请参阅 [.NET Core 3.0 下载](https://dotnet.microsoft.com/download/dotnet-core/3.0)。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-117">For download links and more information, see [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="c4b6b-118">以下 Linux 发行版本/版本支持 .NET Core 3.0：</span><span class="sxs-lookup"><span data-stu-id="c4b6b-118">.NET Core 3.0 is supported on the following Linux distributions/versions):</span></span>

> [!NOTE]
> <span data-ttu-id="c4b6b-119">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-119">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c4b6b-120">(OS)</span><span class="sxs-lookup"><span data-stu-id="c4b6b-120">OS</span></span>                             | <span data-ttu-id="c4b6b-121">Version</span><span class="sxs-lookup"><span data-stu-id="c4b6b-121">Version</span></span>               | <span data-ttu-id="c4b6b-122">体系结构</span><span class="sxs-lookup"><span data-stu-id="c4b6b-122">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="c4b6b-123">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c4b6b-123">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="c4b6b-124">6+、7</span><span class="sxs-lookup"><span data-stu-id="c4b6b-124">6+, 7</span></span>                 | <span data-ttu-id="c4b6b-125">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-125">x64</span></span> |
| <span data-ttu-id="c4b6b-126">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="c4b6b-126">Oracle Linux</span></span>                   | <span data-ttu-id="c4b6b-127">7</span><span class="sxs-lookup"><span data-stu-id="c4b6b-127">7</span></span>                     | <span data-ttu-id="c4b6b-128">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-128">x64</span></span> |
| <span data-ttu-id="c4b6b-129">CentOS</span><span class="sxs-lookup"><span data-stu-id="c4b6b-129">CentOS</span></span>                         | <span data-ttu-id="c4b6b-130">7</span><span class="sxs-lookup"><span data-stu-id="c4b6b-130">7</span></span>                     | <span data-ttu-id="c4b6b-131">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-131">x64</span></span> |
| <span data-ttu-id="c4b6b-132">Fedora</span><span class="sxs-lookup"><span data-stu-id="c4b6b-132">Fedora</span></span>                         | <span data-ttu-id="c4b6b-133">29+</span><span class="sxs-lookup"><span data-stu-id="c4b6b-133">29+</span></span>                   | <span data-ttu-id="c4b6b-134">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-134">x64</span></span> |
| <span data-ttu-id="c4b6b-135">Debian</span><span class="sxs-lookup"><span data-stu-id="c4b6b-135">Debian</span></span>                         | <span data-ttu-id="c4b6b-136">9+</span><span class="sxs-lookup"><span data-stu-id="c4b6b-136">9+</span></span>                    | <span data-ttu-id="c4b6b-137">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-137">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="c4b6b-138">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c4b6b-138">Ubuntu</span></span>                         | <span data-ttu-id="c4b6b-139">16.04+</span><span class="sxs-lookup"><span data-stu-id="c4b6b-139">16.04+</span></span>                | <span data-ttu-id="c4b6b-140">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-140">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="c4b6b-141">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="c4b6b-141">Linux Mint</span></span>                     | <span data-ttu-id="c4b6b-142">18+</span><span class="sxs-lookup"><span data-stu-id="c4b6b-142">18+</span></span>                   | <span data-ttu-id="c4b6b-143">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-143">x64</span></span> |
| <span data-ttu-id="c4b6b-144">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c4b6b-144">openSUSE</span></span>                       | <span data-ttu-id="c4b6b-145">15+</span><span class="sxs-lookup"><span data-stu-id="c4b6b-145">15+</span></span>                   | <span data-ttu-id="c4b6b-146">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-146">x64</span></span> |
| <span data-ttu-id="c4b6b-147">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="c4b6b-147">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="c4b6b-148">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="c4b6b-148">12 SP2+</span></span>               | <span data-ttu-id="c4b6b-149">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-149">x64</span></span> |
| <span data-ttu-id="c4b6b-150">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c4b6b-150">Alpine Linux</span></span>                   | <span data-ttu-id="c4b6b-151">3.8+</span><span class="sxs-lookup"><span data-stu-id="c4b6b-151">3.8+</span></span>                  | <span data-ttu-id="c4b6b-152">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-152">x64, ARM64</span></span> |

<span data-ttu-id="c4b6b-153">有关 .NET Core 3.0 支持的操作系统、发行版本和版本、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 3.0 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-153">See [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) for the complete list of .NET Core 3.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="c4b6b-154">有关如何在 ARM64 上安装 .NET Core 3.0 的详细信息，请参阅[在 Linux ARM64 上安装 .NET Core 3.0](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-154">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="c4b6b-155">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="c4b6b-155">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="c4b6b-156">.NET Core 2.2 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-156">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="c4b6b-157">支持的 Linux 分发都对应有一个 Linux 内部版本（根据芯片体系结构）。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-157">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="c4b6b-158">有关下载链接和详细信息，请参阅 [.NET Core 2.2 下载](https://dotnet.microsoft.com/download/dotnet-core/2.2)。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-158">For download links and more information, see [.NET Core 2.2 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.2).</span></span>

<span data-ttu-id="c4b6b-159">以下 Linux 发行版本/版本支持 .NET Core 2.2：</span><span class="sxs-lookup"><span data-stu-id="c4b6b-159">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="c4b6b-160">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-160">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c4b6b-161">(OS)</span><span class="sxs-lookup"><span data-stu-id="c4b6b-161">OS</span></span>                             |  <span data-ttu-id="c4b6b-162">Version</span><span class="sxs-lookup"><span data-stu-id="c4b6b-162">Version</span></span>                |  <span data-ttu-id="c4b6b-163">体系结构</span><span class="sxs-lookup"><span data-stu-id="c4b6b-163">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="c4b6b-164">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c4b6b-164">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="c4b6b-165">6、7</span><span class="sxs-lookup"><span data-stu-id="c4b6b-165">6, 7</span></span>                   | <span data-ttu-id="c4b6b-166">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-166">x64</span></span> |
| <span data-ttu-id="c4b6b-167">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="c4b6b-167">Oracle Linux</span></span>                   |  <span data-ttu-id="c4b6b-168">7</span><span class="sxs-lookup"><span data-stu-id="c4b6b-168">7</span></span>                      | <span data-ttu-id="c4b6b-169">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-169">x64</span></span> |
| <span data-ttu-id="c4b6b-170">CentOS</span><span class="sxs-lookup"><span data-stu-id="c4b6b-170">CentOS</span></span>                         |  <span data-ttu-id="c4b6b-171">7</span><span class="sxs-lookup"><span data-stu-id="c4b6b-171">7</span></span>                      | <span data-ttu-id="c4b6b-172">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-172">x64</span></span> |
| <span data-ttu-id="c4b6b-173">Fedora</span><span class="sxs-lookup"><span data-stu-id="c4b6b-173">Fedora</span></span>                         |  <span data-ttu-id="c4b6b-174">29、30</span><span class="sxs-lookup"><span data-stu-id="c4b6b-174">29, 30</span></span>                 | <span data-ttu-id="c4b6b-175">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-175">x64</span></span> |
| <span data-ttu-id="c4b6b-176">Debian</span><span class="sxs-lookup"><span data-stu-id="c4b6b-176">Debian</span></span>                         |  <span data-ttu-id="c4b6b-177">9</span><span class="sxs-lookup"><span data-stu-id="c4b6b-177">9</span></span>                      | <span data-ttu-id="c4b6b-178">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="c4b6b-178">x64, ARM32</span></span> |
| <span data-ttu-id="c4b6b-179">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c4b6b-179">Ubuntu</span></span>                         |  <span data-ttu-id="c4b6b-180">16.04、18.04、18.10</span><span class="sxs-lookup"><span data-stu-id="c4b6b-180">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="c4b6b-181">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="c4b6b-181">x64, ARM32</span></span> |
| <span data-ttu-id="c4b6b-182">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="c4b6b-182">Linux Mint</span></span>                     |  <span data-ttu-id="c4b6b-183">17、18</span><span class="sxs-lookup"><span data-stu-id="c4b6b-183">17, 18</span></span>                 | <span data-ttu-id="c4b6b-184">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-184">x64</span></span> |
| <span data-ttu-id="c4b6b-185">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c4b6b-185">openSUSE</span></span>                       |  <span data-ttu-id="c4b6b-186">15+</span><span class="sxs-lookup"><span data-stu-id="c4b6b-186">15+</span></span>                    | <span data-ttu-id="c4b6b-187">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-187">x64</span></span> |
| <span data-ttu-id="c4b6b-188">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="c4b6b-188">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="c4b6b-189">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="c4b6b-189">12 SP2+</span></span>                | <span data-ttu-id="c4b6b-190">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-190">x64</span></span> |
| <span data-ttu-id="c4b6b-191">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c4b6b-191">Alpine Linux</span></span>                   |  <span data-ttu-id="c4b6b-192">3.7+</span><span class="sxs-lookup"><span data-stu-id="c4b6b-192">3.7+</span></span>                   | <span data-ttu-id="c4b6b-193">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-193">x64</span></span> |

<span data-ttu-id="c4b6b-194">要在完整列表中了解 .NET Core 2.2 支持的操作系统、发行版本和版本、生命周期策略链接和不支持的 OS 版本，请参阅 [.NET Core 2.2 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-194">See [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) for the complete list of .NET Core 2.2 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c4b6b-195">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c4b6b-195">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="c4b6b-196">.NET Core 2.1 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-196">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="c4b6b-197">支持的 Linux 分发都对应有一个 Linux 内部版本（根据芯片体系结构）。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-197">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="c4b6b-198">有关下载链接和详细信息，请参阅 [.NET Core 2.1 下载](https://dotnet.microsoft.com/download/dotnet-core/2.1)。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-198">For download links and more information, see [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

<span data-ttu-id="c4b6b-199">以下 Linux 发行版本/版本支持 .NET Core 2.1：</span><span class="sxs-lookup"><span data-stu-id="c4b6b-199">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

| <span data-ttu-id="c4b6b-200">(OS)</span><span class="sxs-lookup"><span data-stu-id="c4b6b-200">OS</span></span>                             |  <span data-ttu-id="c4b6b-201">Version</span><span class="sxs-lookup"><span data-stu-id="c4b6b-201">Version</span></span>                |  <span data-ttu-id="c4b6b-202">体系结构</span><span class="sxs-lookup"><span data-stu-id="c4b6b-202">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="c4b6b-203">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c4b6b-203">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="c4b6b-204">6、7、8</span><span class="sxs-lookup"><span data-stu-id="c4b6b-204">6, 7, 8</span></span>                | <span data-ttu-id="c4b6b-205">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-205">x64</span></span> |
| <span data-ttu-id="c4b6b-206">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="c4b6b-206">Oracle Linux</span></span>                   |  <span data-ttu-id="c4b6b-207">7</span><span class="sxs-lookup"><span data-stu-id="c4b6b-207">7</span></span>                      | <span data-ttu-id="c4b6b-208">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-208">x64</span></span> |
| <span data-ttu-id="c4b6b-209">CentOS</span><span class="sxs-lookup"><span data-stu-id="c4b6b-209">CentOS</span></span>                         |  <span data-ttu-id="c4b6b-210">7</span><span class="sxs-lookup"><span data-stu-id="c4b6b-210">7</span></span>                      | <span data-ttu-id="c4b6b-211">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-211">x64</span></span> |
| <span data-ttu-id="c4b6b-212">Fedora</span><span class="sxs-lookup"><span data-stu-id="c4b6b-212">Fedora</span></span>                         |  <span data-ttu-id="c4b6b-213">29、30</span><span class="sxs-lookup"><span data-stu-id="c4b6b-213">29, 30</span></span>                 | <span data-ttu-id="c4b6b-214">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-214">x64</span></span> |
| <span data-ttu-id="c4b6b-215">Debian</span><span class="sxs-lookup"><span data-stu-id="c4b6b-215">Debian</span></span>                         |  <span data-ttu-id="c4b6b-216">9</span><span class="sxs-lookup"><span data-stu-id="c4b6b-216">9</span></span>                      | <span data-ttu-id="c4b6b-217">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="c4b6b-217">x64, ARM32</span></span> |
| <span data-ttu-id="c4b6b-218">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c4b6b-218">Ubuntu</span></span>                         |  <span data-ttu-id="c4b6b-219">16.04、18.04、19.04</span><span class="sxs-lookup"><span data-stu-id="c4b6b-219">16.04, 18.04, 19.04</span></span>    | <span data-ttu-id="c4b6b-220">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="c4b6b-220">x64, ARM32</span></span> |
| <span data-ttu-id="c4b6b-221">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="c4b6b-221">Linux Mint</span></span>                     |  <span data-ttu-id="c4b6b-222">17、18</span><span class="sxs-lookup"><span data-stu-id="c4b6b-222">17, 18</span></span>                 | <span data-ttu-id="c4b6b-223">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-223">x64</span></span> |
| <span data-ttu-id="c4b6b-224">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c4b6b-224">openSUSE</span></span>                       |  <span data-ttu-id="c4b6b-225">42.3+</span><span class="sxs-lookup"><span data-stu-id="c4b6b-225">42.3+</span></span>                  | <span data-ttu-id="c4b6b-226">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-226">x64</span></span> |
| <span data-ttu-id="c4b6b-227">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="c4b6b-227">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="c4b6b-228">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="c4b6b-228">12 SP2+</span></span>                | <span data-ttu-id="c4b6b-229">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-229">x64</span></span> |
| <span data-ttu-id="c4b6b-230">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c4b6b-230">Alpine Linux</span></span>                   |  <span data-ttu-id="c4b6b-231">3.7+</span><span class="sxs-lookup"><span data-stu-id="c4b6b-231">3.7+</span></span>                   | <span data-ttu-id="c4b6b-232">X64</span><span class="sxs-lookup"><span data-stu-id="c4b6b-232">x64</span></span> |

<span data-ttu-id="c4b6b-233">有关 .NET Core 2.1 支持的操作系统、发行版本和版本、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 2.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-233">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) for the complete list of .NET Core 2.1 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="c4b6b-234">Linux 发行版本依赖项</span><span class="sxs-lookup"><span data-stu-id="c4b6b-234">Linux distribution dependencies</span></span>

<span data-ttu-id="c4b6b-235">以下各项用作示例。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-235">The following are intended to be examples.</span></span> <span data-ttu-id="c4b6b-236">确切的版本和名称可能因所选 Linux 发行版本略有不同。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-236">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="c4b6b-237">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c4b6b-237">Ubuntu</span></span>

<span data-ttu-id="c4b6b-238">Ubuntu 发行版本需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="c4b6b-238">Ubuntu distributions require the following libraries installed:</span></span>

- <span data-ttu-id="c4b6b-239">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="c4b6b-239">liblttng-ust0</span></span>
- <span data-ttu-id="c4b6b-240">libcurl3（针对 14.x 和 16.x）</span><span class="sxs-lookup"><span data-stu-id="c4b6b-240">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="c4b6b-241">libcurl4（针对 18.x）</span><span class="sxs-lookup"><span data-stu-id="c4b6b-241">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="c4b6b-242">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="c4b6b-242">libssl1.0.0</span></span>
- <span data-ttu-id="c4b6b-243">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="c4b6b-243">libkrb5-3</span></span>
- <span data-ttu-id="c4b6b-244">zlib1g</span><span class="sxs-lookup"><span data-stu-id="c4b6b-244">zlib1g</span></span>
- <span data-ttu-id="c4b6b-245">libicu52（针对 14.x）</span><span class="sxs-lookup"><span data-stu-id="c4b6b-245">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="c4b6b-246">libicu55（针对 16.x）</span><span class="sxs-lookup"><span data-stu-id="c4b6b-246">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="c4b6b-247">libicu57（针对 17.x）</span><span class="sxs-lookup"><span data-stu-id="c4b6b-247">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="c4b6b-248">libicu60（针对 18.x）</span><span class="sxs-lookup"><span data-stu-id="c4b6b-248">libicu60 (for 18.x)</span></span>

<span data-ttu-id="c4b6b-249">对于 .NET Core 2.1 之前的版本，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="c4b6b-249">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

- <span data-ttu-id="c4b6b-250">libunwind8</span><span class="sxs-lookup"><span data-stu-id="c4b6b-250">libunwind8</span></span>
- <span data-ttu-id="c4b6b-251">libuuid1</span><span class="sxs-lookup"><span data-stu-id="c4b6b-251">libuuid1</span></span>

<span data-ttu-id="c4b6b-252">对于使用 System.Drawing.Common  程序集的 .NET Core 应用程序，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="c4b6b-252">For .NET Core applications that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

* <span data-ttu-id="c4b6b-253">libgdiplus（版本 6.0.1 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="c4b6b-253">libgdiplus (version 6.0.1 or later)</span></span>

> [!NOTE]
> <span data-ttu-id="c4b6b-254">大多数 Ubuntu 版本都包含 libgdiplus 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-254">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="c4b6b-255">可以通过将 Mono 存储库添加到系统来安装最新版 libgdiplus。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-255">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="c4b6b-256">有关详细信息，请参阅 <https://www.mono-project.com/download/stable/>。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-256">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="c4b6b-257">CentOS 和 Fedora</span><span class="sxs-lookup"><span data-stu-id="c4b6b-257">CentOS and Fedora</span></span>

<span data-ttu-id="c4b6b-258">CentOS 发行版本需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="c4b6b-258">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="c4b6b-259">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="c4b6b-259">lttng-ust</span></span>
- <span data-ttu-id="c4b6b-260">libcurl</span><span class="sxs-lookup"><span data-stu-id="c4b6b-260">libcurl</span></span>
- <span data-ttu-id="c4b6b-261">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="c4b6b-261">openssl-libs</span></span>
- <span data-ttu-id="c4b6b-262">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="c4b6b-262">krb5-libs</span></span>
- <span data-ttu-id="c4b6b-263">libicu</span><span class="sxs-lookup"><span data-stu-id="c4b6b-263">libicu</span></span>
- <span data-ttu-id="c4b6b-264">zlib</span><span class="sxs-lookup"><span data-stu-id="c4b6b-264">zlib</span></span>

<span data-ttu-id="c4b6b-265">Fedora 用户：如果 openssl 的版本为 1.1 及以上版本，则需要安装 compat-openssl10。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-265">Fedora users: If your openssl's version >= 1.1, you'll need to install compat-openssl10.</span></span>

<span data-ttu-id="c4b6b-266">对于 .NET Core 2.1 之前的版本，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="c4b6b-266">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

- <span data-ttu-id="c4b6b-267">libunwind</span><span class="sxs-lookup"><span data-stu-id="c4b6b-267">libunwind</span></span>
- <span data-ttu-id="c4b6b-268">libuuid</span><span class="sxs-lookup"><span data-stu-id="c4b6b-268">libuuid</span></span>

<span data-ttu-id="c4b6b-269">有关依赖项的详细信息，请参阅[独立式 Linux 应用程序](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-269">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="c4b6b-270">对于使用 System.Drawing.Common  程序集的 .NET Core 应用程序，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="c4b6b-270">For .NET Core applications that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

* <span data-ttu-id="c4b6b-271">libgdiplus（版本 6.0.1 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="c4b6b-271">libgdiplus (version 6.0.1 or later)</span></span>

> [!NOTE]
> <span data-ttu-id="c4b6b-272">CentOS 和 Fedora 的大多数版本都包含 libgdiplus 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-272">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="c4b6b-273">可以通过将 Mono 存储库添加到系统来安装最新版 libgdiplus。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-273">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="c4b6b-274">有关详细信息，请参阅 <https://www.mono-project.com/download/stable/>。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-274">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="c4b6b-275">使用本机安装程序安装 .NET Core 依赖项</span><span class="sxs-lookup"><span data-stu-id="c4b6b-275">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="c4b6b-276">.NET Core 本机安装程序适用于支持的 Linux 发行版本/版本。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-276">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="c4b6b-277">本机安装程序需要拥有对服务器的管理员 (sudo) 访问权限。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-277">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="c4b6b-278">使用本机安装程序的优势在于，可以安装所有 .NET Core 本机依赖项。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-278">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="c4b6b-279">本机安装程序还会在整个系统内安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-279">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="c4b6b-280">在 Linux 上，安装程序包有两种使用方式：</span><span class="sxs-lookup"><span data-stu-id="c4b6b-280">On Linux, there are two installer package choices:</span></span>

- <span data-ttu-id="c4b6b-281">使用基于源的包管理器，如适用于 Ubuntu 的 apt-get，或适用于 CentOS/RHEL 的 yum。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-281">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
- <span data-ttu-id="c4b6b-282">使用包本身（DEB 或 RPM）。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-282">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="c4b6b-283">使用 .NET Core 安装程序脚本编写安装脚本</span><span class="sxs-lookup"><span data-stu-id="c4b6b-283">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="c4b6b-284">[dotnet-install 脚本](./tools/dotnet-install-script.md)用于执行 CLI 工具链和共享运行时的非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-284">The [dotnet-install scripts](./tools/dotnet-install-script.md) are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="c4b6b-285">可通过 <https://dot.net/v1/dotnet-install.sh> 下载脚本。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-285">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="c4b6b-286">此脚本会默认安装最新的“LTS”版本，当前为 .NET Core 1.1。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-286">The script defaults to installing the latest "LTS" version, which is currently .NET Core 1.1.</span></span> <span data-ttu-id="c4b6b-287">要安装 .NET Core 2.1，请使用以下开关运行脚本：</span><span class="sxs-lookup"><span data-stu-id="c4b6b-287">To install .NET Core 2.1, run the script with the following switch:</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="c4b6b-288">安装程序 bash 脚本用于自动化方案和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-288">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="c4b6b-289">此脚本也读取 PowerShell 开关，因此可以与 Linux/OS X 系统上的脚本结合使用。</span><span class="sxs-lookup"><span data-stu-id="c4b6b-289">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="c4b6b-290">疑难解答</span><span class="sxs-lookup"><span data-stu-id="c4b6b-290">Troubleshoot</span></span>

<span data-ttu-id="c4b6b-291">若对在支持的 Linux 分发/版本上安装 .NET Core 有疑问，请参阅下方你所安装的分发/版本的相应主题：</span><span class="sxs-lookup"><span data-stu-id="c4b6b-291">If you have problems with a .NET Core installation on a supported Linux distribution/version, consult the following topics for your installed distributions/versions:</span></span>

- [<span data-ttu-id="c4b6b-292">.NET Core 3.0 已知问题</span><span class="sxs-lookup"><span data-stu-id="c4b6b-292">.NET Core 3.0 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/3.0)
- [<span data-ttu-id="c4b6b-293">.NET Core 2.2 已知问题</span><span class="sxs-lookup"><span data-stu-id="c4b6b-293">.NET Core 2.2 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.2)
- [<span data-ttu-id="c4b6b-294">.NET Core 2.1 已知问题</span><span class="sxs-lookup"><span data-stu-id="c4b6b-294">.NET Core 2.1 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.1)
- [<span data-ttu-id="c4b6b-295">.NET Core 1.1 已知问题</span><span class="sxs-lookup"><span data-stu-id="c4b6b-295">.NET Core 1.1 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.1)
- [<span data-ttu-id="c4b6b-296">.NET Core 1.0 已知问题</span><span class="sxs-lookup"><span data-stu-id="c4b6b-296">.NET Core 1.0 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0)
