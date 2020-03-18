---
title: .NET Core SDK 和运行时依赖项 - .NET Core
description: 详细介绍在 Windows、Linux 和 macOS 上安装 .NET Core SDK 和运行时的操作系统和 CPU 体系结构先决条件。
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: ca86b3c158bb38c1293cd4303dcf4c00ea9175b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "78157800"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="1c785-103">.NET Core 依赖项和要求</span><span class="sxs-lookup"><span data-stu-id="1c785-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="1c785-104">本文详细介绍了 .NET Core 支持的操作系统和 CPU 体系结构。</span><span class="sxs-lookup"><span data-stu-id="1c785-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="1c785-105">支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="1c785-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="1c785-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="1c785-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="1c785-107">.NET Core 3.1 支持下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="1c785-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="1c785-108">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="1c785-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1c785-109">(OS)</span><span class="sxs-lookup"><span data-stu-id="1c785-109">OS</span></span>                            | <span data-ttu-id="1c785-110">Version</span><span class="sxs-lookup"><span data-stu-id="1c785-110">Version</span></span>                        | <span data-ttu-id="1c785-111">体系结构</span><span class="sxs-lookup"><span data-stu-id="1c785-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="1c785-112">Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="1c785-112">Windows Client</span></span>                | <span data-ttu-id="1c785-113">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="1c785-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="1c785-114">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1c785-114">x64, x86</span></span>        |
| <span data-ttu-id="1c785-115">Windows 10 客户端</span><span class="sxs-lookup"><span data-stu-id="1c785-115">Windows 10 Client</span></span>             | <span data-ttu-id="1c785-116">版本 1607+</span><span class="sxs-lookup"><span data-stu-id="1c785-116">Version 1607+</span></span>                  | <span data-ttu-id="1c785-117">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1c785-117">x64, x86</span></span>        |
| <span data-ttu-id="1c785-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="1c785-118">Windows Server</span></span>                | <span data-ttu-id="1c785-119">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="1c785-119">2012 R2+</span></span>                       | <span data-ttu-id="1c785-120">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1c785-120">x64, x86</span></span>        |
| <span data-ttu-id="1c785-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="1c785-121">Nano Server</span></span>                   | <span data-ttu-id="1c785-122">版本 1803+</span><span class="sxs-lookup"><span data-stu-id="1c785-122">Version 1803+</span></span>                  | <span data-ttu-id="1c785-123">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="1c785-123">x64, ARM32</span></span>      |

<span data-ttu-id="1c785-124">有关 .NET Core 3.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="1c785-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="1c785-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1c785-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="1c785-126">.NET Core 3.0 支持下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="1c785-126">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="1c785-127">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="1c785-127">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1c785-128">(OS)</span><span class="sxs-lookup"><span data-stu-id="1c785-128">OS</span></span>                            | <span data-ttu-id="1c785-129">Version</span><span class="sxs-lookup"><span data-stu-id="1c785-129">Version</span></span>                        | <span data-ttu-id="1c785-130">体系结构</span><span class="sxs-lookup"><span data-stu-id="1c785-130">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="1c785-131">Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="1c785-131">Windows Client</span></span>                | <span data-ttu-id="1c785-132">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="1c785-132">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="1c785-133">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1c785-133">x64, x86</span></span>        |
| <span data-ttu-id="1c785-134">Windows 10 客户端</span><span class="sxs-lookup"><span data-stu-id="1c785-134">Windows 10 Client</span></span>             | <span data-ttu-id="1c785-135">版本 1607+</span><span class="sxs-lookup"><span data-stu-id="1c785-135">Version 1607+</span></span>                  | <span data-ttu-id="1c785-136">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1c785-136">x64, x86</span></span>        |
| <span data-ttu-id="1c785-137">Windows Server</span><span class="sxs-lookup"><span data-stu-id="1c785-137">Windows Server</span></span>                | <span data-ttu-id="1c785-138">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="1c785-138">2012 R2+</span></span>                       | <span data-ttu-id="1c785-139">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1c785-139">x64, x86</span></span>        |
| <span data-ttu-id="1c785-140">Nano Server</span><span class="sxs-lookup"><span data-stu-id="1c785-140">Nano Server</span></span>                   | <span data-ttu-id="1c785-141">版本 1803+</span><span class="sxs-lookup"><span data-stu-id="1c785-141">Version 1803+</span></span>                  | <span data-ttu-id="1c785-142">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="1c785-142">x64, ARM32</span></span>      |

<span data-ttu-id="1c785-143">有关 .NET Core 3.0 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.0 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="1c785-143">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="1c785-144">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="1c785-144">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="1c785-145">.NET Core 2.2 支持下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="1c785-145">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="1c785-146">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="1c785-146">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1c785-147">(OS)</span><span class="sxs-lookup"><span data-stu-id="1c785-147">OS</span></span>                            | <span data-ttu-id="1c785-148">Version</span><span class="sxs-lookup"><span data-stu-id="1c785-148">Version</span></span>                        | <span data-ttu-id="1c785-149">体系结构</span><span class="sxs-lookup"><span data-stu-id="1c785-149">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="1c785-150">Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="1c785-150">Windows Client</span></span>                | <span data-ttu-id="1c785-151">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="1c785-151">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="1c785-152">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1c785-152">x64, x86</span></span>        |
| <span data-ttu-id="1c785-153">Windows 10 客户端</span><span class="sxs-lookup"><span data-stu-id="1c785-153">Windows 10 Client</span></span>             | <span data-ttu-id="1c785-154">版本 1607+</span><span class="sxs-lookup"><span data-stu-id="1c785-154">Version 1607+</span></span>                  | <span data-ttu-id="1c785-155">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1c785-155">x64, x86</span></span>        |
| <span data-ttu-id="1c785-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="1c785-156">Windows Server</span></span>                | <span data-ttu-id="1c785-157">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="1c785-157">2008 R2 SP1+</span></span>                   | <span data-ttu-id="1c785-158">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1c785-158">x64, x86</span></span>        |
| <span data-ttu-id="1c785-159">Nano Server</span><span class="sxs-lookup"><span data-stu-id="1c785-159">Nano Server</span></span>                   | <span data-ttu-id="1c785-160">版本 1803+</span><span class="sxs-lookup"><span data-stu-id="1c785-160">Version 1803+</span></span>                   | <span data-ttu-id="1c785-161">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="1c785-161">x64, ARM32</span></span>      |

<span data-ttu-id="1c785-162">有关 .NET Core 2.2 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.2 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="1c785-162">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="1c785-163">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1c785-163">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="1c785-164">.NET Core 2.1 支持下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="1c785-164">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="1c785-165">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="1c785-165">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1c785-166">(OS)</span><span class="sxs-lookup"><span data-stu-id="1c785-166">OS</span></span>                            | <span data-ttu-id="1c785-167">Version</span><span class="sxs-lookup"><span data-stu-id="1c785-167">Version</span></span>                        | <span data-ttu-id="1c785-168">体系结构</span><span class="sxs-lookup"><span data-stu-id="1c785-168">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="1c785-169">Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="1c785-169">Windows Client</span></span>                | <span data-ttu-id="1c785-170">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="1c785-170">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="1c785-171">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1c785-171">x64, x86</span></span>        |
| <span data-ttu-id="1c785-172">Windows 10 客户端</span><span class="sxs-lookup"><span data-stu-id="1c785-172">Windows 10 Client</span></span>             | <span data-ttu-id="1c785-173">版本 1607+</span><span class="sxs-lookup"><span data-stu-id="1c785-173">Version 1607+</span></span>                  | <span data-ttu-id="1c785-174">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1c785-174">x64, x86</span></span>        |
| <span data-ttu-id="1c785-175">Windows Server</span><span class="sxs-lookup"><span data-stu-id="1c785-175">Windows Server</span></span>                | <span data-ttu-id="1c785-176">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="1c785-176">2008 R2 SP1+</span></span>                   | <span data-ttu-id="1c785-177">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1c785-177">x64, x86</span></span>        |
| <span data-ttu-id="1c785-178">Nano Server</span><span class="sxs-lookup"><span data-stu-id="1c785-178">Nano Server</span></span>                   | <span data-ttu-id="1c785-179">版本 1803+</span><span class="sxs-lookup"><span data-stu-id="1c785-179">Version 1803+</span></span>                  | <span data-ttu-id="1c785-180">x64</span><span class="sxs-lookup"><span data-stu-id="1c785-180">x64,</span></span>            |

<span data-ttu-id="1c785-181">有关 .NET Core 2.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="1c785-181">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="1c785-182">Windows 7/Vista/8.1/Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="1c785-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="1c785-183">如果要在以下 Windows 版本上安装 .NET SDK 或运行时，则需要其他依赖项：</span><span class="sxs-lookup"><span data-stu-id="1c785-183">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="1c785-184">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="1c785-184">Windows 7 SP1</span></span>
- <span data-ttu-id="1c785-185">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="1c785-185">Windows Vista SP 2</span></span>
- <span data-ttu-id="1c785-186">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="1c785-186">Windows 8.1</span></span>
- <span data-ttu-id="1c785-187">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="1c785-187">Windows Server 2008 R2</span></span>
- <span data-ttu-id="1c785-188">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1c785-188">Windows Server 2012 R2</span></span>

<span data-ttu-id="1c785-189">安装以下组件：</span><span class="sxs-lookup"><span data-stu-id="1c785-189">Install the following:</span></span>

- <span data-ttu-id="1c785-190">[Microsoft Visual C++ 2015 Redistributable 更新 3](https://www.microsoft.com/download/details.aspx?id=52685)。</span><span class="sxs-lookup"><span data-stu-id="1c785-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="1c785-191">KB2533623</span><span class="sxs-lookup"><span data-stu-id="1c785-191">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="1c785-192">如果遇到一个以下错误，也需要满足上述要求：</span><span class="sxs-lookup"><span data-stu-id="1c785-192">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="1c785-193">此程序无法启动，因为计算机上缺少 api-ms-win-crt-runtime-l1-1-0.dll  。</span><span class="sxs-lookup"><span data-stu-id="1c785-193">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="1c785-194">尝试重新安装该程序以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="1c785-194">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="1c785-195">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="1c785-195">\- or -</span></span>
>
> <span data-ttu-id="1c785-196">已找到库 hostfxr.dll  ，但未能将其从 C:\\\<path_to_app>\\hostfxr.dll 中加载  。</span><span class="sxs-lookup"><span data-stu-id="1c785-196">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="1c785-197">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="1c785-197">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="1c785-198">.NET Core 3.1 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="1c785-198">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="1c785-199">对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。</span><span class="sxs-lookup"><span data-stu-id="1c785-199">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="1c785-200">以下 Linux 发行版/版本支持 .NET Core 3.1：</span><span class="sxs-lookup"><span data-stu-id="1c785-200">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="1c785-201">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="1c785-201">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1c785-202">(OS)</span><span class="sxs-lookup"><span data-stu-id="1c785-202">OS</span></span>                             | <span data-ttu-id="1c785-203">Version</span><span class="sxs-lookup"><span data-stu-id="1c785-203">Version</span></span>               | <span data-ttu-id="1c785-204">体系结构</span><span class="sxs-lookup"><span data-stu-id="1c785-204">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="1c785-205">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="1c785-205">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="1c785-206">6、7、8</span><span class="sxs-lookup"><span data-stu-id="1c785-206">6, 7, 8</span></span>               | <span data-ttu-id="1c785-207">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-207">x64</span></span> |
| <span data-ttu-id="1c785-208">CentOS</span><span class="sxs-lookup"><span data-stu-id="1c785-208">CentOS</span></span>                         | <span data-ttu-id="1c785-209">7+</span><span class="sxs-lookup"><span data-stu-id="1c785-209">7+</span></span>                    | <span data-ttu-id="1c785-210">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-210">x64</span></span> |
| <span data-ttu-id="1c785-211">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="1c785-211">Oracle Linux</span></span>                   | <span data-ttu-id="1c785-212">7+</span><span class="sxs-lookup"><span data-stu-id="1c785-212">7+</span></span>                    | <span data-ttu-id="1c785-213">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-213">x64</span></span> |
| <span data-ttu-id="1c785-214">Fedora</span><span class="sxs-lookup"><span data-stu-id="1c785-214">Fedora</span></span>                         | <span data-ttu-id="1c785-215">29+</span><span class="sxs-lookup"><span data-stu-id="1c785-215">29+</span></span>                   | <span data-ttu-id="1c785-216">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-216">x64</span></span> |
| <span data-ttu-id="1c785-217">Debian</span><span class="sxs-lookup"><span data-stu-id="1c785-217">Debian</span></span>                         | <span data-ttu-id="1c785-218">9+</span><span class="sxs-lookup"><span data-stu-id="1c785-218">9+</span></span>                    | <span data-ttu-id="1c785-219">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="1c785-219">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="1c785-220">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1c785-220">Ubuntu</span></span>                         | <span data-ttu-id="1c785-221">16.04+</span><span class="sxs-lookup"><span data-stu-id="1c785-221">16.04+</span></span>                | <span data-ttu-id="1c785-222">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="1c785-222">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="1c785-223">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="1c785-223">Linux Mint</span></span>                     | <span data-ttu-id="1c785-224">18+</span><span class="sxs-lookup"><span data-stu-id="1c785-224">18+</span></span>                   | <span data-ttu-id="1c785-225">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-225">x64</span></span> |
| <span data-ttu-id="1c785-226">openSUSE</span><span class="sxs-lookup"><span data-stu-id="1c785-226">openSUSE</span></span>                       | <span data-ttu-id="1c785-227">15+</span><span class="sxs-lookup"><span data-stu-id="1c785-227">15+</span></span>                   | <span data-ttu-id="1c785-228">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-228">x64</span></span> |
| <span data-ttu-id="1c785-229">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="1c785-229">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="1c785-230">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="1c785-230">12 SP2+</span></span>               | <span data-ttu-id="1c785-231">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-231">x64</span></span> |
| <span data-ttu-id="1c785-232">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="1c785-232">Alpine Linux</span></span>                   | <span data-ttu-id="1c785-233">3.10+</span><span class="sxs-lookup"><span data-stu-id="1c785-233">3.10+</span></span>                 | <span data-ttu-id="1c785-234">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="1c785-234">x64, ARM64</span></span> |

<span data-ttu-id="1c785-235">有关 .NET Core 3.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="1c785-235">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="1c785-236">有关如何在 ARM64（内核 4.14+）上安装 .NET Core 3.1 的详细信息，请参阅[在 Linux ARM64 上安装 .NET Core 3.0](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)。</span><span class="sxs-lookup"><span data-stu-id="1c785-236">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c785-237">ARM64 支持需要 Linux 内核 4.14 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="1c785-237">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="1c785-238">某些 linux 发行版满足此要求，而另一些则不满足。</span><span class="sxs-lookup"><span data-stu-id="1c785-238">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="1c785-239">例如，支持 Ubuntu 18.04，但不支持 Ubuntu 16.04。</span><span class="sxs-lookup"><span data-stu-id="1c785-239">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="1c785-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1c785-240">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="1c785-241">.NET Core 3.0 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="1c785-241">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="1c785-242">对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。</span><span class="sxs-lookup"><span data-stu-id="1c785-242">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="1c785-243">以下 Linux 发行版本/版本支持 .NET Core 3.0：</span><span class="sxs-lookup"><span data-stu-id="1c785-243">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="1c785-244">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="1c785-244">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1c785-245">(OS)</span><span class="sxs-lookup"><span data-stu-id="1c785-245">OS</span></span>                             | <span data-ttu-id="1c785-246">Version</span><span class="sxs-lookup"><span data-stu-id="1c785-246">Version</span></span>               | <span data-ttu-id="1c785-247">体系结构</span><span class="sxs-lookup"><span data-stu-id="1c785-247">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="1c785-248">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="1c785-248">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="1c785-249">6、7、8</span><span class="sxs-lookup"><span data-stu-id="1c785-249">6, 7, 8</span></span>               | <span data-ttu-id="1c785-250">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-250">x64</span></span> |
| <span data-ttu-id="1c785-251">CentOS</span><span class="sxs-lookup"><span data-stu-id="1c785-251">CentOS</span></span>                         | <span data-ttu-id="1c785-252">7+</span><span class="sxs-lookup"><span data-stu-id="1c785-252">7+</span></span>                    | <span data-ttu-id="1c785-253">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-253">x64</span></span> |
| <span data-ttu-id="1c785-254">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="1c785-254">Oracle Linux</span></span>                   | <span data-ttu-id="1c785-255">7+</span><span class="sxs-lookup"><span data-stu-id="1c785-255">7+</span></span>                    | <span data-ttu-id="1c785-256">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-256">x64</span></span> |
| <span data-ttu-id="1c785-257">Fedora</span><span class="sxs-lookup"><span data-stu-id="1c785-257">Fedora</span></span>                         | <span data-ttu-id="1c785-258">29+</span><span class="sxs-lookup"><span data-stu-id="1c785-258">29+</span></span>                   | <span data-ttu-id="1c785-259">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-259">x64</span></span> |
| <span data-ttu-id="1c785-260">Debian</span><span class="sxs-lookup"><span data-stu-id="1c785-260">Debian</span></span>                         | <span data-ttu-id="1c785-261">9+</span><span class="sxs-lookup"><span data-stu-id="1c785-261">9+</span></span>                    | <span data-ttu-id="1c785-262">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="1c785-262">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="1c785-263">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1c785-263">Ubuntu</span></span>                         | <span data-ttu-id="1c785-264">16.04+</span><span class="sxs-lookup"><span data-stu-id="1c785-264">16.04+</span></span>                | <span data-ttu-id="1c785-265">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="1c785-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="1c785-266">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="1c785-266">Linux Mint</span></span>                     | <span data-ttu-id="1c785-267">18+</span><span class="sxs-lookup"><span data-stu-id="1c785-267">18+</span></span>                   | <span data-ttu-id="1c785-268">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-268">x64</span></span> |
| <span data-ttu-id="1c785-269">openSUSE</span><span class="sxs-lookup"><span data-stu-id="1c785-269">openSUSE</span></span>                       | <span data-ttu-id="1c785-270">15+</span><span class="sxs-lookup"><span data-stu-id="1c785-270">15+</span></span>                   | <span data-ttu-id="1c785-271">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-271">x64</span></span> |
| <span data-ttu-id="1c785-272">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="1c785-272">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="1c785-273">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="1c785-273">12 SP2+</span></span>               | <span data-ttu-id="1c785-274">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-274">x64</span></span> |
| <span data-ttu-id="1c785-275">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="1c785-275">Alpine Linux</span></span>                   | <span data-ttu-id="1c785-276">3.8+</span><span class="sxs-lookup"><span data-stu-id="1c785-276">3.8+</span></span>                  | <span data-ttu-id="1c785-277">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="1c785-277">x64, ARM64</span></span> |

<span data-ttu-id="1c785-278">有关 .NET Core 3.0 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.0 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="1c785-278">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="1c785-279">有关如何在 ARM64 上安装 .NET Core 3.0 的详细信息，请参阅[在 Linux ARM64 上安装 .NET Core 3.0](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)。</span><span class="sxs-lookup"><span data-stu-id="1c785-279">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="1c785-280">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="1c785-280">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="1c785-281">.NET Core 2.2 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="1c785-281">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="1c785-282">对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。</span><span class="sxs-lookup"><span data-stu-id="1c785-282">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="1c785-283">以下 Linux 发行版本/版本支持 .NET Core 2.2：</span><span class="sxs-lookup"><span data-stu-id="1c785-283">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="1c785-284">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="1c785-284">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1c785-285">(OS)</span><span class="sxs-lookup"><span data-stu-id="1c785-285">OS</span></span>                             |  <span data-ttu-id="1c785-286">Version</span><span class="sxs-lookup"><span data-stu-id="1c785-286">Version</span></span>                |  <span data-ttu-id="1c785-287">体系结构</span><span class="sxs-lookup"><span data-stu-id="1c785-287">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="1c785-288">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="1c785-288">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="1c785-289">6、7</span><span class="sxs-lookup"><span data-stu-id="1c785-289">6, 7</span></span>                   | <span data-ttu-id="1c785-290">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-290">x64</span></span> |
| <span data-ttu-id="1c785-291">CentOS</span><span class="sxs-lookup"><span data-stu-id="1c785-291">CentOS</span></span>                         |  <span data-ttu-id="1c785-292">7</span><span class="sxs-lookup"><span data-stu-id="1c785-292">7</span></span>                      | <span data-ttu-id="1c785-293">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-293">x64</span></span> |
| <span data-ttu-id="1c785-294">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="1c785-294">Oracle Linux</span></span>                   |  <span data-ttu-id="1c785-295">7</span><span class="sxs-lookup"><span data-stu-id="1c785-295">7</span></span>                      | <span data-ttu-id="1c785-296">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-296">x64</span></span> |
| <span data-ttu-id="1c785-297">Fedora</span><span class="sxs-lookup"><span data-stu-id="1c785-297">Fedora</span></span>                         |  <span data-ttu-id="1c785-298">29、30</span><span class="sxs-lookup"><span data-stu-id="1c785-298">29, 30</span></span>                 | <span data-ttu-id="1c785-299">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-299">x64</span></span> |
| <span data-ttu-id="1c785-300">Debian</span><span class="sxs-lookup"><span data-stu-id="1c785-300">Debian</span></span>                         |  <span data-ttu-id="1c785-301">9</span><span class="sxs-lookup"><span data-stu-id="1c785-301">9</span></span>                      | <span data-ttu-id="1c785-302">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="1c785-302">x64, ARM32</span></span> |
| <span data-ttu-id="1c785-303">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1c785-303">Ubuntu</span></span>                         |  <span data-ttu-id="1c785-304">16.04、18.04、18.10</span><span class="sxs-lookup"><span data-stu-id="1c785-304">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="1c785-305">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="1c785-305">x64, ARM32</span></span> |
| <span data-ttu-id="1c785-306">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="1c785-306">Linux Mint</span></span>                     |  <span data-ttu-id="1c785-307">17、18</span><span class="sxs-lookup"><span data-stu-id="1c785-307">17, 18</span></span>                 | <span data-ttu-id="1c785-308">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-308">x64</span></span> |
| <span data-ttu-id="1c785-309">openSUSE</span><span class="sxs-lookup"><span data-stu-id="1c785-309">openSUSE</span></span>                       |  <span data-ttu-id="1c785-310">15+</span><span class="sxs-lookup"><span data-stu-id="1c785-310">15+</span></span>                    | <span data-ttu-id="1c785-311">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-311">x64</span></span> |
| <span data-ttu-id="1c785-312">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="1c785-312">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="1c785-313">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="1c785-313">12 SP2+</span></span>                | <span data-ttu-id="1c785-314">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-314">x64</span></span> |
| <span data-ttu-id="1c785-315">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="1c785-315">Alpine Linux</span></span>                   |  <span data-ttu-id="1c785-316">3.8+</span><span class="sxs-lookup"><span data-stu-id="1c785-316">3.8+</span></span>                   | <span data-ttu-id="1c785-317">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-317">x64</span></span> |

<span data-ttu-id="1c785-318">有关 .NET Core 2.2 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.2 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="1c785-318">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="1c785-319">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1c785-319">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="1c785-320">.NET Core 2.1 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="1c785-320">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="1c785-321">对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。</span><span class="sxs-lookup"><span data-stu-id="1c785-321">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="1c785-322">以下 Linux 发行版本/版本支持 .NET Core 2.1：</span><span class="sxs-lookup"><span data-stu-id="1c785-322">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="1c785-323">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="1c785-323">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1c785-324">(OS)</span><span class="sxs-lookup"><span data-stu-id="1c785-324">OS</span></span>                             |  <span data-ttu-id="1c785-325">Version</span><span class="sxs-lookup"><span data-stu-id="1c785-325">Version</span></span>                |  <span data-ttu-id="1c785-326">体系结构</span><span class="sxs-lookup"><span data-stu-id="1c785-326">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="1c785-327">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="1c785-327">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="1c785-328">6、7、8</span><span class="sxs-lookup"><span data-stu-id="1c785-328">6, 7, 8</span></span>                | <span data-ttu-id="1c785-329">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-329">x64</span></span> |
| <span data-ttu-id="1c785-330">CentOS</span><span class="sxs-lookup"><span data-stu-id="1c785-330">CentOS</span></span>                         |  <span data-ttu-id="1c785-331">7+</span><span class="sxs-lookup"><span data-stu-id="1c785-331">7+</span></span>                     | <span data-ttu-id="1c785-332">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-332">x64</span></span> |
| <span data-ttu-id="1c785-333">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="1c785-333">Oracle Linux</span></span>                   |  <span data-ttu-id="1c785-334">7+</span><span class="sxs-lookup"><span data-stu-id="1c785-334">7+</span></span>                     | <span data-ttu-id="1c785-335">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-335">x64</span></span> |
| <span data-ttu-id="1c785-336">Fedora</span><span class="sxs-lookup"><span data-stu-id="1c785-336">Fedora</span></span>                         |  <span data-ttu-id="1c785-337">29+</span><span class="sxs-lookup"><span data-stu-id="1c785-337">29+</span></span>                    | <span data-ttu-id="1c785-338">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-338">x64</span></span> |
| <span data-ttu-id="1c785-339">Debian</span><span class="sxs-lookup"><span data-stu-id="1c785-339">Debian</span></span>                         |  <span data-ttu-id="1c785-340">9</span><span class="sxs-lookup"><span data-stu-id="1c785-340">9</span></span>                      | <span data-ttu-id="1c785-341">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="1c785-341">x64, ARM32</span></span> |
| <span data-ttu-id="1c785-342">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1c785-342">Ubuntu</span></span>                         |  <span data-ttu-id="1c785-343">16.04、18.04、19.04、19.10</span><span class="sxs-lookup"><span data-stu-id="1c785-343">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="1c785-344">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="1c785-344">x64, ARM32</span></span> |
| <span data-ttu-id="1c785-345">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="1c785-345">Linux Mint</span></span>                     |  <span data-ttu-id="1c785-346">17+</span><span class="sxs-lookup"><span data-stu-id="1c785-346">17+</span></span>                    | <span data-ttu-id="1c785-347">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-347">x64</span></span> |
| <span data-ttu-id="1c785-348">openSUSE</span><span class="sxs-lookup"><span data-stu-id="1c785-348">openSUSE</span></span>                       |  <span data-ttu-id="1c785-349">15+</span><span class="sxs-lookup"><span data-stu-id="1c785-349">15+</span></span>                    | <span data-ttu-id="1c785-350">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-350">x64</span></span> |
| <span data-ttu-id="1c785-351">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="1c785-351">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="1c785-352">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="1c785-352">12 SP2+</span></span>                | <span data-ttu-id="1c785-353">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-353">x64</span></span> |
| <span data-ttu-id="1c785-354">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="1c785-354">Alpine Linux</span></span>                   |  <span data-ttu-id="1c785-355">3.8+</span><span class="sxs-lookup"><span data-stu-id="1c785-355">3.8+</span></span>                   | <span data-ttu-id="1c785-356">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-356">x64</span></span> |

<span data-ttu-id="1c785-357">有关 .NET Core 2.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="1c785-357">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="1c785-358">Linux 发行版本依赖项</span><span class="sxs-lookup"><span data-stu-id="1c785-358">Linux distribution dependencies</span></span>

<span data-ttu-id="1c785-359">根据 Linux 发行版，你可能需要安装其他依赖项。</span><span class="sxs-lookup"><span data-stu-id="1c785-359">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c785-360">确切的版本和名称可能因所选 Linux 发行版本略有不同。</span><span class="sxs-lookup"><span data-stu-id="1c785-360">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="1c785-361">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1c785-361">Ubuntu</span></span>

<span data-ttu-id="1c785-362">Ubuntu 发行版需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="1c785-362">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="1c785-363">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="1c785-363">liblttng-ust0</span></span>
- <span data-ttu-id="1c785-364">libcurl3（针对 14.x 和 16.x）</span><span class="sxs-lookup"><span data-stu-id="1c785-364">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="1c785-365">libcurl4（针对 18.x）</span><span class="sxs-lookup"><span data-stu-id="1c785-365">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="1c785-366">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="1c785-366">libssl1.0.0</span></span>
- <span data-ttu-id="1c785-367">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="1c785-367">libkrb5-3</span></span>
- <span data-ttu-id="1c785-368">zlib1g</span><span class="sxs-lookup"><span data-stu-id="1c785-368">zlib1g</span></span>
- <span data-ttu-id="1c785-369">libicu52（针对 14.x）</span><span class="sxs-lookup"><span data-stu-id="1c785-369">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="1c785-370">libicu55（针对 16.x）</span><span class="sxs-lookup"><span data-stu-id="1c785-370">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="1c785-371">libicu57（针对 17.x）</span><span class="sxs-lookup"><span data-stu-id="1c785-371">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="1c785-372">libicu60（针对 18.x）</span><span class="sxs-lookup"><span data-stu-id="1c785-372">libicu60 (for 18.x)</span></span>

<span data-ttu-id="1c785-373">对于使用 System.Drawing.Common  程序集的 .NET Core 应用，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="1c785-373">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="1c785-374">libgdiplus（版本 6.0.1 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="1c785-374">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="1c785-375">大多数 Ubuntu 版本都包含 libgdiplus 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="1c785-375">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="1c785-376">可以通过将 Mono 存储库添加到系统来安装最新版 libgdiplus。</span><span class="sxs-lookup"><span data-stu-id="1c785-376">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="1c785-377">有关详细信息，请参阅 <https://www.mono-project.com/download/stable/>。</span><span class="sxs-lookup"><span data-stu-id="1c785-377">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="1c785-378">CentOS 和 Fedora</span><span class="sxs-lookup"><span data-stu-id="1c785-378">CentOS and Fedora</span></span>

<span data-ttu-id="1c785-379">CentOS 发行版本需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="1c785-379">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="1c785-380">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="1c785-380">lttng-ust</span></span>
- <span data-ttu-id="1c785-381">libcurl</span><span class="sxs-lookup"><span data-stu-id="1c785-381">libcurl</span></span>
- <span data-ttu-id="1c785-382">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="1c785-382">openssl-libs</span></span>
- <span data-ttu-id="1c785-383">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="1c785-383">krb5-libs</span></span>
- <span data-ttu-id="1c785-384">libicu</span><span class="sxs-lookup"><span data-stu-id="1c785-384">libicu</span></span>
- <span data-ttu-id="1c785-385">zlib</span><span class="sxs-lookup"><span data-stu-id="1c785-385">zlib</span></span>

<span data-ttu-id="1c785-386">Fedora 用户：如果 OpenSSL 的版本为 1.1 及更高版本，则需要安装 compat-openssl10  。</span><span class="sxs-lookup"><span data-stu-id="1c785-386">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="1c785-387">对于 .NET Core 2.0，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="1c785-387">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="1c785-388">libunwind</span><span class="sxs-lookup"><span data-stu-id="1c785-388">libunwind</span></span>
- <span data-ttu-id="1c785-389">libuuid</span><span class="sxs-lookup"><span data-stu-id="1c785-389">libuuid</span></span>

<span data-ttu-id="1c785-390">有关依赖项的详细信息，请参阅[独立式 Linux 应用](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="1c785-390">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="1c785-391">对于使用 System.Drawing.Common  程序集的 .NET Core 应用，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="1c785-391">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="1c785-392">libgdiplus（版本 6.0.1 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="1c785-392">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="1c785-393">CentOS 和 Fedora 的大多数版本都包含 libgdiplus 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="1c785-393">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="1c785-394">可以通过将 Mono 存储库添加到系统来安装最新版 libgdiplus。</span><span class="sxs-lookup"><span data-stu-id="1c785-394">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="1c785-395">有关详细信息，请参阅 <https://www.mono-project.com/download/stable/>。</span><span class="sxs-lookup"><span data-stu-id="1c785-395">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="1c785-396">以下 macOS 版本支持 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="1c785-396">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="1c785-397">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="1c785-397">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1c785-398">.NET Core 版本</span><span class="sxs-lookup"><span data-stu-id="1c785-398">.NET Core Version</span></span> | <span data-ttu-id="1c785-399">macOS</span><span class="sxs-lookup"><span data-stu-id="1c785-399">macOS</span></span>                 | <span data-ttu-id="1c785-400">体系结构</span><span class="sxs-lookup"><span data-stu-id="1c785-400">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="1c785-401">3.1</span><span class="sxs-lookup"><span data-stu-id="1c785-401">3.1</span></span>               | <span data-ttu-id="1c785-402">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="1c785-402">High Sierra (10.13+)</span></span>  | <span data-ttu-id="1c785-403">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-403">x64</span></span> | [<span data-ttu-id="1c785-404">详细信息</span><span class="sxs-lookup"><span data-stu-id="1c785-404">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="1c785-405">3.0</span><span class="sxs-lookup"><span data-stu-id="1c785-405">3.0</span></span>               | <span data-ttu-id="1c785-406">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="1c785-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="1c785-407">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-407">x64</span></span> | [<span data-ttu-id="1c785-408">详细信息</span><span class="sxs-lookup"><span data-stu-id="1c785-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="1c785-409">2.2</span><span class="sxs-lookup"><span data-stu-id="1c785-409">2.2</span></span>               | <span data-ttu-id="1c785-410">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="1c785-410">Sierra (10.12+)</span></span>       | <span data-ttu-id="1c785-411">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-411">x64</span></span> | [<span data-ttu-id="1c785-412">详细信息</span><span class="sxs-lookup"><span data-stu-id="1c785-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="1c785-413">2.1</span><span class="sxs-lookup"><span data-stu-id="1c785-413">2.1</span></span>               | <span data-ttu-id="1c785-414">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="1c785-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="1c785-415">X64</span><span class="sxs-lookup"><span data-stu-id="1c785-415">x64</span></span> | [<span data-ttu-id="1c785-416">详细信息</span><span class="sxs-lookup"><span data-stu-id="1c785-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="1c785-417">自 macOS Catalina（版本10.15）开始，所有在 2019 年 6 月 1 日之后生成并使用开发者 ID 扩散的软件都必须经过公证。</span><span class="sxs-lookup"><span data-stu-id="1c785-417">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="1c785-418">此要求应用于 .NET Core 运行时、.NET Core SDK 以及使用 .NET Core 创建的软件。</span><span class="sxs-lookup"><span data-stu-id="1c785-418">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="1c785-419">自 2020 年 2 月 18 日起，.NET Core（运行时和 SDK）版本 3.1、3.0 和 2.1 的安装程序都已经过公证。</span><span class="sxs-lookup"><span data-stu-id="1c785-419">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="1c785-420">以前发布的版本没有经过公证。</span><span class="sxs-lookup"><span data-stu-id="1c785-420">Prior released versions aren't notarized.</span></span> <span data-ttu-id="1c785-421">如果运行未经过公证的应用，将看到类似于下图的错误：</span><span class="sxs-lookup"><span data-stu-id="1c785-421">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![macOS Catalina 公证警报](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="1c785-423">若要详细了解强制执行的公证要求对 .NET Core 和 .NET Core 应用的影响，请参阅[处理 macOS Catalina 公证](macos-notarization-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1c785-423">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="1c785-424">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="1c785-424">libgdiplus</span></span>

<span data-ttu-id="1c785-425">使用 System.Drawing.Common  程序集的 .NET Core 应用程序要求安装 libgdiplus。</span><span class="sxs-lookup"><span data-stu-id="1c785-425">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="1c785-426">获取 libgdiplus 的一个简单方法是使用适用于 macOS 的 [Homebrew (“brew”)](https://brew.sh/) 包。</span><span class="sxs-lookup"><span data-stu-id="1c785-426">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="1c785-427">在安装 brew 后，通过在终端（命令）提示符处执行以下命令来安装 libgdiplus  ：</span><span class="sxs-lookup"><span data-stu-id="1c785-427">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="1c785-428">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1c785-428">Next steps</span></span>

- <span data-ttu-id="1c785-429">若要开发并运行应用，请安装 [.NET Core SDK](sdk.md)（包括运行时）。</span><span class="sxs-lookup"><span data-stu-id="1c785-429">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="1c785-430">若要运行其他人创建的应用，请安装 [.NET Core 运行时](runtime.md)。</span><span class="sxs-lookup"><span data-stu-id="1c785-430">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
