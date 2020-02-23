---
title: .NET Core SDK 和运行时依赖项 - .NET Core
description: 详细介绍在 Windows、Linux 和 macOS 上安装 .NET Core SDK 和运行时的操作系统和 CPU 体系结构先决条件。
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 4164ea5a04d80ab20109168a225b793b02ee616a
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448888"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="fe849-103">.NET Core 依赖项和要求</span><span class="sxs-lookup"><span data-stu-id="fe849-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="fe849-104">本文详细介绍了 .NET Core 支持的操作系统和 CPU 体系结构。</span><span class="sxs-lookup"><span data-stu-id="fe849-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="fe849-105">支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="fe849-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="fe849-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="fe849-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="fe849-107">.NET Core 3.1 支持下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="fe849-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="fe849-108">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="fe849-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="fe849-109">(OS)</span><span class="sxs-lookup"><span data-stu-id="fe849-109">OS</span></span>                            | <span data-ttu-id="fe849-110">Version</span><span class="sxs-lookup"><span data-stu-id="fe849-110">Version</span></span>                        | <span data-ttu-id="fe849-111">体系结构</span><span class="sxs-lookup"><span data-stu-id="fe849-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="fe849-112">Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="fe849-112">Windows Client</span></span>                | <span data-ttu-id="fe849-113">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="fe849-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="fe849-114">x64、x86</span><span class="sxs-lookup"><span data-stu-id="fe849-114">x64, x86</span></span>        |
| <span data-ttu-id="fe849-115">Windows 10 客户端</span><span class="sxs-lookup"><span data-stu-id="fe849-115">Windows 10 Client</span></span>             | <span data-ttu-id="fe849-116">版本 1607+</span><span class="sxs-lookup"><span data-stu-id="fe849-116">Version 1607+</span></span>                  | <span data-ttu-id="fe849-117">x64、x86</span><span class="sxs-lookup"><span data-stu-id="fe849-117">x64, x86</span></span>        |
| <span data-ttu-id="fe849-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="fe849-118">Windows Server</span></span>                | <span data-ttu-id="fe849-119">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="fe849-119">2012 R2+</span></span>                       | <span data-ttu-id="fe849-120">x64、x86</span><span class="sxs-lookup"><span data-stu-id="fe849-120">x64, x86</span></span>        |
| <span data-ttu-id="fe849-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="fe849-121">Nano Server</span></span>                   | <span data-ttu-id="fe849-122">版本 1803+</span><span class="sxs-lookup"><span data-stu-id="fe849-122">Version 1803+</span></span>                  | <span data-ttu-id="fe849-123">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="fe849-123">x64, ARM32</span></span>      |

<span data-ttu-id="fe849-124">有关 .NET Core 3.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="fe849-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="fe849-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="fe849-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="fe849-126">.NET Core 3.0 支持下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="fe849-126">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="fe849-127">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="fe849-127">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="fe849-128">(OS)</span><span class="sxs-lookup"><span data-stu-id="fe849-128">OS</span></span>                            | <span data-ttu-id="fe849-129">Version</span><span class="sxs-lookup"><span data-stu-id="fe849-129">Version</span></span>                        | <span data-ttu-id="fe849-130">体系结构</span><span class="sxs-lookup"><span data-stu-id="fe849-130">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="fe849-131">Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="fe849-131">Windows Client</span></span>                | <span data-ttu-id="fe849-132">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="fe849-132">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="fe849-133">x64、x86</span><span class="sxs-lookup"><span data-stu-id="fe849-133">x64, x86</span></span>        |
| <span data-ttu-id="fe849-134">Windows 10 客户端</span><span class="sxs-lookup"><span data-stu-id="fe849-134">Windows 10 Client</span></span>             | <span data-ttu-id="fe849-135">版本 1607+</span><span class="sxs-lookup"><span data-stu-id="fe849-135">Version 1607+</span></span>                  | <span data-ttu-id="fe849-136">x64、x86</span><span class="sxs-lookup"><span data-stu-id="fe849-136">x64, x86</span></span>        |
| <span data-ttu-id="fe849-137">Windows Server</span><span class="sxs-lookup"><span data-stu-id="fe849-137">Windows Server</span></span>                | <span data-ttu-id="fe849-138">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="fe849-138">2012 R2+</span></span>                       | <span data-ttu-id="fe849-139">x64、x86</span><span class="sxs-lookup"><span data-stu-id="fe849-139">x64, x86</span></span>        |
| <span data-ttu-id="fe849-140">Nano Server</span><span class="sxs-lookup"><span data-stu-id="fe849-140">Nano Server</span></span>                   | <span data-ttu-id="fe849-141">版本 1803+</span><span class="sxs-lookup"><span data-stu-id="fe849-141">Version 1803+</span></span>                  | <span data-ttu-id="fe849-142">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="fe849-142">x64, ARM32</span></span>      |

<span data-ttu-id="fe849-143">有关 .NET Core 3.0 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.0 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="fe849-143">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="fe849-144">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="fe849-144">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="fe849-145">.NET Core 2.2 支持下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="fe849-145">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="fe849-146">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="fe849-146">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="fe849-147">(OS)</span><span class="sxs-lookup"><span data-stu-id="fe849-147">OS</span></span>                            | <span data-ttu-id="fe849-148">Version</span><span class="sxs-lookup"><span data-stu-id="fe849-148">Version</span></span>                        | <span data-ttu-id="fe849-149">体系结构</span><span class="sxs-lookup"><span data-stu-id="fe849-149">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="fe849-150">Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="fe849-150">Windows Client</span></span>                | <span data-ttu-id="fe849-151">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="fe849-151">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="fe849-152">x64、x86</span><span class="sxs-lookup"><span data-stu-id="fe849-152">x64, x86</span></span>        |
| <span data-ttu-id="fe849-153">Windows 10 客户端</span><span class="sxs-lookup"><span data-stu-id="fe849-153">Windows 10 Client</span></span>             | <span data-ttu-id="fe849-154">版本 1607+</span><span class="sxs-lookup"><span data-stu-id="fe849-154">Version 1607+</span></span>                  | <span data-ttu-id="fe849-155">x64、x86</span><span class="sxs-lookup"><span data-stu-id="fe849-155">x64, x86</span></span>        |
| <span data-ttu-id="fe849-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="fe849-156">Windows Server</span></span>                | <span data-ttu-id="fe849-157">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="fe849-157">2008 R2 SP1+</span></span>                   | <span data-ttu-id="fe849-158">x64、x86</span><span class="sxs-lookup"><span data-stu-id="fe849-158">x64, x86</span></span>        |
| <span data-ttu-id="fe849-159">Nano Server</span><span class="sxs-lookup"><span data-stu-id="fe849-159">Nano Server</span></span>                   | <span data-ttu-id="fe849-160">版本 1803+</span><span class="sxs-lookup"><span data-stu-id="fe849-160">Version 1803+</span></span>                   | <span data-ttu-id="fe849-161">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="fe849-161">x64, ARM32</span></span>      |

<span data-ttu-id="fe849-162">有关 .NET Core 2.2 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.2 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="fe849-162">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="fe849-163">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="fe849-163">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="fe849-164">.NET Core 2.1 支持下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="fe849-164">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="fe849-165">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="fe849-165">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="fe849-166">(OS)</span><span class="sxs-lookup"><span data-stu-id="fe849-166">OS</span></span>                            | <span data-ttu-id="fe849-167">Version</span><span class="sxs-lookup"><span data-stu-id="fe849-167">Version</span></span>                        | <span data-ttu-id="fe849-168">体系结构</span><span class="sxs-lookup"><span data-stu-id="fe849-168">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="fe849-169">Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="fe849-169">Windows Client</span></span>                | <span data-ttu-id="fe849-170">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="fe849-170">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="fe849-171">x64、x86</span><span class="sxs-lookup"><span data-stu-id="fe849-171">x64, x86</span></span>        |
| <span data-ttu-id="fe849-172">Windows 10 客户端</span><span class="sxs-lookup"><span data-stu-id="fe849-172">Windows 10 Client</span></span>             | <span data-ttu-id="fe849-173">版本 1607+</span><span class="sxs-lookup"><span data-stu-id="fe849-173">Version 1607+</span></span>                  | <span data-ttu-id="fe849-174">x64、x86</span><span class="sxs-lookup"><span data-stu-id="fe849-174">x64, x86</span></span>        |
| <span data-ttu-id="fe849-175">Windows Server</span><span class="sxs-lookup"><span data-stu-id="fe849-175">Windows Server</span></span>                | <span data-ttu-id="fe849-176">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="fe849-176">2008 R2 SP1+</span></span>                   | <span data-ttu-id="fe849-177">x64、x86</span><span class="sxs-lookup"><span data-stu-id="fe849-177">x64, x86</span></span>        |
| <span data-ttu-id="fe849-178">Nano Server</span><span class="sxs-lookup"><span data-stu-id="fe849-178">Nano Server</span></span>                   | <span data-ttu-id="fe849-179">版本 1803+</span><span class="sxs-lookup"><span data-stu-id="fe849-179">Version 1803+</span></span>                  | <span data-ttu-id="fe849-180">x64</span><span class="sxs-lookup"><span data-stu-id="fe849-180">x64,</span></span>            |

<span data-ttu-id="fe849-181">有关 .NET Core 2.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="fe849-181">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="fe849-182">Windows 7/Vista/8.1/Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="fe849-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="fe849-183">如果要在以下 Windows 版本上安装 .NET SDK 或运行时，则需要其他依赖项：</span><span class="sxs-lookup"><span data-stu-id="fe849-183">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="fe849-184">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="fe849-184">Windows 7 SP1</span></span>
- <span data-ttu-id="fe849-185">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="fe849-185">Windows Vista SP 2</span></span>
- <span data-ttu-id="fe849-186">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="fe849-186">Windows 8.1</span></span>
- <span data-ttu-id="fe849-187">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="fe849-187">Windows Server 2008 R2</span></span>
- <span data-ttu-id="fe849-188">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="fe849-188">Windows Server 2012 R2</span></span>

<span data-ttu-id="fe849-189">安装以下组件：</span><span class="sxs-lookup"><span data-stu-id="fe849-189">Install the following:</span></span>

- <span data-ttu-id="fe849-190">[Microsoft Visual C++ 2015 Redistributable 更新 3](https://www.microsoft.com/download/details.aspx?id=52685)。</span><span class="sxs-lookup"><span data-stu-id="fe849-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="fe849-191">KB2533623</span><span class="sxs-lookup"><span data-stu-id="fe849-191">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="fe849-192">如果遇到一个以下错误，也需要满足上述要求：</span><span class="sxs-lookup"><span data-stu-id="fe849-192">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="fe849-193">此程序无法启动，因为计算机上缺少 api-ms-win-crt-runtime-l1-1-0.dll  。</span><span class="sxs-lookup"><span data-stu-id="fe849-193">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="fe849-194">尝试重新安装该程序以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="fe849-194">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="fe849-195">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="fe849-195">\- or -</span></span>
>
> <span data-ttu-id="fe849-196">已找到库 hostfxr.dll  ，但未能将其从 C:\\\<path_to_app>\\hostfxr.dll 中加载  。</span><span class="sxs-lookup"><span data-stu-id="fe849-196">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="fe849-197">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="fe849-197">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="fe849-198">.NET Core 3.1 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="fe849-198">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="fe849-199">对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。</span><span class="sxs-lookup"><span data-stu-id="fe849-199">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="fe849-200">以下 Linux 发行版/版本支持 .NET Core 3.1：</span><span class="sxs-lookup"><span data-stu-id="fe849-200">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="fe849-201">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="fe849-201">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="fe849-202">(OS)</span><span class="sxs-lookup"><span data-stu-id="fe849-202">OS</span></span>                             | <span data-ttu-id="fe849-203">Version</span><span class="sxs-lookup"><span data-stu-id="fe849-203">Version</span></span>               | <span data-ttu-id="fe849-204">体系结构</span><span class="sxs-lookup"><span data-stu-id="fe849-204">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="fe849-205">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="fe849-205">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="fe849-206">6、7、8</span><span class="sxs-lookup"><span data-stu-id="fe849-206">6, 7, 8</span></span>               | <span data-ttu-id="fe849-207">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-207">x64</span></span> |
| <span data-ttu-id="fe849-208">CentOS</span><span class="sxs-lookup"><span data-stu-id="fe849-208">CentOS</span></span>                         | <span data-ttu-id="fe849-209">7+</span><span class="sxs-lookup"><span data-stu-id="fe849-209">7+</span></span>                    | <span data-ttu-id="fe849-210">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-210">x64</span></span> |
| <span data-ttu-id="fe849-211">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="fe849-211">Oracle Linux</span></span>                   | <span data-ttu-id="fe849-212">7+</span><span class="sxs-lookup"><span data-stu-id="fe849-212">7+</span></span>                    | <span data-ttu-id="fe849-213">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-213">x64</span></span> |
| <span data-ttu-id="fe849-214">Fedora</span><span class="sxs-lookup"><span data-stu-id="fe849-214">Fedora</span></span>                         | <span data-ttu-id="fe849-215">29+</span><span class="sxs-lookup"><span data-stu-id="fe849-215">29+</span></span>                   | <span data-ttu-id="fe849-216">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-216">x64</span></span> |
| <span data-ttu-id="fe849-217">Debian</span><span class="sxs-lookup"><span data-stu-id="fe849-217">Debian</span></span>                         | <span data-ttu-id="fe849-218">9+</span><span class="sxs-lookup"><span data-stu-id="fe849-218">9+</span></span>                    | <span data-ttu-id="fe849-219">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="fe849-219">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="fe849-220">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="fe849-220">Ubuntu</span></span>                         | <span data-ttu-id="fe849-221">16.04+</span><span class="sxs-lookup"><span data-stu-id="fe849-221">16.04+</span></span>                | <span data-ttu-id="fe849-222">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="fe849-222">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="fe849-223">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="fe849-223">Linux Mint</span></span>                     | <span data-ttu-id="fe849-224">18+</span><span class="sxs-lookup"><span data-stu-id="fe849-224">18+</span></span>                   | <span data-ttu-id="fe849-225">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-225">x64</span></span> |
| <span data-ttu-id="fe849-226">openSUSE</span><span class="sxs-lookup"><span data-stu-id="fe849-226">openSUSE</span></span>                       | <span data-ttu-id="fe849-227">15+</span><span class="sxs-lookup"><span data-stu-id="fe849-227">15+</span></span>                   | <span data-ttu-id="fe849-228">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-228">x64</span></span> |
| <span data-ttu-id="fe849-229">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="fe849-229">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="fe849-230">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="fe849-230">12 SP2+</span></span>               | <span data-ttu-id="fe849-231">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-231">x64</span></span> |
| <span data-ttu-id="fe849-232">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="fe849-232">Alpine Linux</span></span>                   | <span data-ttu-id="fe849-233">3.10+</span><span class="sxs-lookup"><span data-stu-id="fe849-233">3.10+</span></span>                 | <span data-ttu-id="fe849-234">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="fe849-234">x64, ARM64</span></span> |

<span data-ttu-id="fe849-235">有关 .NET Core 3.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="fe849-235">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="fe849-236">有关如何在 ARM64（内核 4.14+）上安装 .NET Core 3.1 的详细信息，请参阅[在 Linux ARM64 上安装 .NET Core 3.0](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)。</span><span class="sxs-lookup"><span data-stu-id="fe849-236">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe849-237">ARM64 支持需要 Linux 内核 4.14 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="fe849-237">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="fe849-238">某些 linux 发行版满足此要求，而另一些则不满足。</span><span class="sxs-lookup"><span data-stu-id="fe849-238">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="fe849-239">例如，支持 Ubuntu 18.04，但不支持 Ubuntu 16.04。</span><span class="sxs-lookup"><span data-stu-id="fe849-239">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="fe849-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="fe849-240">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="fe849-241">.NET Core 3.0 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="fe849-241">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="fe849-242">对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。</span><span class="sxs-lookup"><span data-stu-id="fe849-242">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="fe849-243">以下 Linux 发行版本/版本支持 .NET Core 3.0：</span><span class="sxs-lookup"><span data-stu-id="fe849-243">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="fe849-244">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="fe849-244">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="fe849-245">(OS)</span><span class="sxs-lookup"><span data-stu-id="fe849-245">OS</span></span>                             | <span data-ttu-id="fe849-246">Version</span><span class="sxs-lookup"><span data-stu-id="fe849-246">Version</span></span>               | <span data-ttu-id="fe849-247">体系结构</span><span class="sxs-lookup"><span data-stu-id="fe849-247">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="fe849-248">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="fe849-248">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="fe849-249">6、7、8</span><span class="sxs-lookup"><span data-stu-id="fe849-249">6, 7, 8</span></span>               | <span data-ttu-id="fe849-250">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-250">x64</span></span> |
| <span data-ttu-id="fe849-251">CentOS</span><span class="sxs-lookup"><span data-stu-id="fe849-251">CentOS</span></span>                         | <span data-ttu-id="fe849-252">7+</span><span class="sxs-lookup"><span data-stu-id="fe849-252">7+</span></span>                    | <span data-ttu-id="fe849-253">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-253">x64</span></span> |
| <span data-ttu-id="fe849-254">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="fe849-254">Oracle Linux</span></span>                   | <span data-ttu-id="fe849-255">7+</span><span class="sxs-lookup"><span data-stu-id="fe849-255">7+</span></span>                    | <span data-ttu-id="fe849-256">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-256">x64</span></span> |
| <span data-ttu-id="fe849-257">Fedora</span><span class="sxs-lookup"><span data-stu-id="fe849-257">Fedora</span></span>                         | <span data-ttu-id="fe849-258">29+</span><span class="sxs-lookup"><span data-stu-id="fe849-258">29+</span></span>                   | <span data-ttu-id="fe849-259">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-259">x64</span></span> |
| <span data-ttu-id="fe849-260">Debian</span><span class="sxs-lookup"><span data-stu-id="fe849-260">Debian</span></span>                         | <span data-ttu-id="fe849-261">9+</span><span class="sxs-lookup"><span data-stu-id="fe849-261">9+</span></span>                    | <span data-ttu-id="fe849-262">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="fe849-262">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="fe849-263">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="fe849-263">Ubuntu</span></span>                         | <span data-ttu-id="fe849-264">16.04+</span><span class="sxs-lookup"><span data-stu-id="fe849-264">16.04+</span></span>                | <span data-ttu-id="fe849-265">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="fe849-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="fe849-266">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="fe849-266">Linux Mint</span></span>                     | <span data-ttu-id="fe849-267">18+</span><span class="sxs-lookup"><span data-stu-id="fe849-267">18+</span></span>                   | <span data-ttu-id="fe849-268">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-268">x64</span></span> |
| <span data-ttu-id="fe849-269">openSUSE</span><span class="sxs-lookup"><span data-stu-id="fe849-269">openSUSE</span></span>                       | <span data-ttu-id="fe849-270">15+</span><span class="sxs-lookup"><span data-stu-id="fe849-270">15+</span></span>                   | <span data-ttu-id="fe849-271">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-271">x64</span></span> |
| <span data-ttu-id="fe849-272">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="fe849-272">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="fe849-273">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="fe849-273">12 SP2+</span></span>               | <span data-ttu-id="fe849-274">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-274">x64</span></span> |
| <span data-ttu-id="fe849-275">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="fe849-275">Alpine Linux</span></span>                   | <span data-ttu-id="fe849-276">3.8+</span><span class="sxs-lookup"><span data-stu-id="fe849-276">3.8+</span></span>                  | <span data-ttu-id="fe849-277">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="fe849-277">x64, ARM64</span></span> |

<span data-ttu-id="fe849-278">有关 .NET Core 3.0 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.0 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="fe849-278">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="fe849-279">有关如何在 ARM64 上安装 .NET Core 3.0 的详细信息，请参阅[在 Linux ARM64 上安装 .NET Core 3.0](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)。</span><span class="sxs-lookup"><span data-stu-id="fe849-279">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="fe849-280">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="fe849-280">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="fe849-281">.NET Core 2.2 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="fe849-281">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="fe849-282">对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。</span><span class="sxs-lookup"><span data-stu-id="fe849-282">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="fe849-283">以下 Linux 发行版本/版本支持 .NET Core 2.2：</span><span class="sxs-lookup"><span data-stu-id="fe849-283">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="fe849-284">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="fe849-284">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="fe849-285">(OS)</span><span class="sxs-lookup"><span data-stu-id="fe849-285">OS</span></span>                             |  <span data-ttu-id="fe849-286">Version</span><span class="sxs-lookup"><span data-stu-id="fe849-286">Version</span></span>                |  <span data-ttu-id="fe849-287">体系结构</span><span class="sxs-lookup"><span data-stu-id="fe849-287">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="fe849-288">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="fe849-288">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="fe849-289">6、7</span><span class="sxs-lookup"><span data-stu-id="fe849-289">6, 7</span></span>                   | <span data-ttu-id="fe849-290">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-290">x64</span></span> |
| <span data-ttu-id="fe849-291">CentOS</span><span class="sxs-lookup"><span data-stu-id="fe849-291">CentOS</span></span>                         |  <span data-ttu-id="fe849-292">7</span><span class="sxs-lookup"><span data-stu-id="fe849-292">7</span></span>                      | <span data-ttu-id="fe849-293">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-293">x64</span></span> |
| <span data-ttu-id="fe849-294">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="fe849-294">Oracle Linux</span></span>                   |  <span data-ttu-id="fe849-295">7</span><span class="sxs-lookup"><span data-stu-id="fe849-295">7</span></span>                      | <span data-ttu-id="fe849-296">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-296">x64</span></span> |
| <span data-ttu-id="fe849-297">Fedora</span><span class="sxs-lookup"><span data-stu-id="fe849-297">Fedora</span></span>                         |  <span data-ttu-id="fe849-298">29、30</span><span class="sxs-lookup"><span data-stu-id="fe849-298">29, 30</span></span>                 | <span data-ttu-id="fe849-299">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-299">x64</span></span> |
| <span data-ttu-id="fe849-300">Debian</span><span class="sxs-lookup"><span data-stu-id="fe849-300">Debian</span></span>                         |  <span data-ttu-id="fe849-301">9</span><span class="sxs-lookup"><span data-stu-id="fe849-301">9</span></span>                      | <span data-ttu-id="fe849-302">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="fe849-302">x64, ARM32</span></span> |
| <span data-ttu-id="fe849-303">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="fe849-303">Ubuntu</span></span>                         |  <span data-ttu-id="fe849-304">16.04、18.04、18.10</span><span class="sxs-lookup"><span data-stu-id="fe849-304">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="fe849-305">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="fe849-305">x64, ARM32</span></span> |
| <span data-ttu-id="fe849-306">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="fe849-306">Linux Mint</span></span>                     |  <span data-ttu-id="fe849-307">17、18</span><span class="sxs-lookup"><span data-stu-id="fe849-307">17, 18</span></span>                 | <span data-ttu-id="fe849-308">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-308">x64</span></span> |
| <span data-ttu-id="fe849-309">openSUSE</span><span class="sxs-lookup"><span data-stu-id="fe849-309">openSUSE</span></span>                       |  <span data-ttu-id="fe849-310">15+</span><span class="sxs-lookup"><span data-stu-id="fe849-310">15+</span></span>                    | <span data-ttu-id="fe849-311">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-311">x64</span></span> |
| <span data-ttu-id="fe849-312">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="fe849-312">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="fe849-313">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="fe849-313">12 SP2+</span></span>                | <span data-ttu-id="fe849-314">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-314">x64</span></span> |
| <span data-ttu-id="fe849-315">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="fe849-315">Alpine Linux</span></span>                   |  <span data-ttu-id="fe849-316">3.8+</span><span class="sxs-lookup"><span data-stu-id="fe849-316">3.8+</span></span>                   | <span data-ttu-id="fe849-317">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-317">x64</span></span> |

<span data-ttu-id="fe849-318">有关 .NET Core 2.2 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.2 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="fe849-318">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="fe849-319">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="fe849-319">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="fe849-320">.NET Core 2.1 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="fe849-320">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="fe849-321">对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。</span><span class="sxs-lookup"><span data-stu-id="fe849-321">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="fe849-322">以下 Linux 发行版本/版本支持 .NET Core 2.1：</span><span class="sxs-lookup"><span data-stu-id="fe849-322">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="fe849-323">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="fe849-323">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="fe849-324">(OS)</span><span class="sxs-lookup"><span data-stu-id="fe849-324">OS</span></span>                             |  <span data-ttu-id="fe849-325">Version</span><span class="sxs-lookup"><span data-stu-id="fe849-325">Version</span></span>                |  <span data-ttu-id="fe849-326">体系结构</span><span class="sxs-lookup"><span data-stu-id="fe849-326">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="fe849-327">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="fe849-327">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="fe849-328">6、7、8</span><span class="sxs-lookup"><span data-stu-id="fe849-328">6, 7, 8</span></span>                | <span data-ttu-id="fe849-329">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-329">x64</span></span> |
| <span data-ttu-id="fe849-330">CentOS</span><span class="sxs-lookup"><span data-stu-id="fe849-330">CentOS</span></span>                         |  <span data-ttu-id="fe849-331">7+</span><span class="sxs-lookup"><span data-stu-id="fe849-331">7+</span></span>                     | <span data-ttu-id="fe849-332">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-332">x64</span></span> |
| <span data-ttu-id="fe849-333">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="fe849-333">Oracle Linux</span></span>                   |  <span data-ttu-id="fe849-334">7+</span><span class="sxs-lookup"><span data-stu-id="fe849-334">7+</span></span>                     | <span data-ttu-id="fe849-335">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-335">x64</span></span> |
| <span data-ttu-id="fe849-336">Fedora</span><span class="sxs-lookup"><span data-stu-id="fe849-336">Fedora</span></span>                         |  <span data-ttu-id="fe849-337">29+</span><span class="sxs-lookup"><span data-stu-id="fe849-337">29+</span></span>                    | <span data-ttu-id="fe849-338">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-338">x64</span></span> |
| <span data-ttu-id="fe849-339">Debian</span><span class="sxs-lookup"><span data-stu-id="fe849-339">Debian</span></span>                         |  <span data-ttu-id="fe849-340">9</span><span class="sxs-lookup"><span data-stu-id="fe849-340">9</span></span>                      | <span data-ttu-id="fe849-341">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="fe849-341">x64, ARM32</span></span> |
| <span data-ttu-id="fe849-342">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="fe849-342">Ubuntu</span></span>                         |  <span data-ttu-id="fe849-343">16.04、18.04、19.04、19.10</span><span class="sxs-lookup"><span data-stu-id="fe849-343">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="fe849-344">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="fe849-344">x64, ARM32</span></span> |
| <span data-ttu-id="fe849-345">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="fe849-345">Linux Mint</span></span>                     |  <span data-ttu-id="fe849-346">17+</span><span class="sxs-lookup"><span data-stu-id="fe849-346">17+</span></span>                    | <span data-ttu-id="fe849-347">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-347">x64</span></span> |
| <span data-ttu-id="fe849-348">openSUSE</span><span class="sxs-lookup"><span data-stu-id="fe849-348">openSUSE</span></span>                       |  <span data-ttu-id="fe849-349">15+</span><span class="sxs-lookup"><span data-stu-id="fe849-349">15+</span></span>                    | <span data-ttu-id="fe849-350">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-350">x64</span></span> |
| <span data-ttu-id="fe849-351">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="fe849-351">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="fe849-352">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="fe849-352">12 SP2+</span></span>                | <span data-ttu-id="fe849-353">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-353">x64</span></span> |
| <span data-ttu-id="fe849-354">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="fe849-354">Alpine Linux</span></span>                   |  <span data-ttu-id="fe849-355">3.8+</span><span class="sxs-lookup"><span data-stu-id="fe849-355">3.8+</span></span>                   | <span data-ttu-id="fe849-356">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-356">x64</span></span> |

<span data-ttu-id="fe849-357">有关 .NET Core 2.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="fe849-357">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="fe849-358">Linux 发行版本依赖项</span><span class="sxs-lookup"><span data-stu-id="fe849-358">Linux distribution dependencies</span></span>

<span data-ttu-id="fe849-359">根据 Linux 发行版，你可能需要安装其他依赖项。</span><span class="sxs-lookup"><span data-stu-id="fe849-359">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe849-360">确切的版本和名称可能因所选 Linux 发行版本略有不同。</span><span class="sxs-lookup"><span data-stu-id="fe849-360">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="fe849-361">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="fe849-361">Ubuntu</span></span>

<span data-ttu-id="fe849-362">Ubuntu 发行版需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="fe849-362">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="fe849-363">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="fe849-363">liblttng-ust0</span></span>
- <span data-ttu-id="fe849-364">libcurl3（针对 14.x 和 16.x）</span><span class="sxs-lookup"><span data-stu-id="fe849-364">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="fe849-365">libcurl4（针对 18.x）</span><span class="sxs-lookup"><span data-stu-id="fe849-365">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="fe849-366">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="fe849-366">libssl1.0.0</span></span>
- <span data-ttu-id="fe849-367">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="fe849-367">libkrb5-3</span></span>
- <span data-ttu-id="fe849-368">zlib1g</span><span class="sxs-lookup"><span data-stu-id="fe849-368">zlib1g</span></span>
- <span data-ttu-id="fe849-369">libicu52（针对 14.x）</span><span class="sxs-lookup"><span data-stu-id="fe849-369">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="fe849-370">libicu55（针对 16.x）</span><span class="sxs-lookup"><span data-stu-id="fe849-370">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="fe849-371">libicu57（针对 17.x）</span><span class="sxs-lookup"><span data-stu-id="fe849-371">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="fe849-372">libicu60（针对 18.x）</span><span class="sxs-lookup"><span data-stu-id="fe849-372">libicu60 (for 18.x)</span></span>

<span data-ttu-id="fe849-373">对于使用 System.Drawing.Common  程序集的 .NET Core 应用，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="fe849-373">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="fe849-374">libgdiplus（版本 6.0.1 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="fe849-374">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="fe849-375">大多数 Ubuntu 版本都包含 libgdiplus 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="fe849-375">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="fe849-376">可以通过将 Mono 存储库添加到系统来安装最新版 libgdiplus。</span><span class="sxs-lookup"><span data-stu-id="fe849-376">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="fe849-377">有关详细信息，请参阅 <https://www.mono-project.com/download/stable/>。</span><span class="sxs-lookup"><span data-stu-id="fe849-377">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="fe849-378">CentOS 和 Fedora</span><span class="sxs-lookup"><span data-stu-id="fe849-378">CentOS and Fedora</span></span>

<span data-ttu-id="fe849-379">CentOS 发行版本需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="fe849-379">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="fe849-380">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="fe849-380">lttng-ust</span></span>
- <span data-ttu-id="fe849-381">libcurl</span><span class="sxs-lookup"><span data-stu-id="fe849-381">libcurl</span></span>
- <span data-ttu-id="fe849-382">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="fe849-382">openssl-libs</span></span>
- <span data-ttu-id="fe849-383">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="fe849-383">krb5-libs</span></span>
- <span data-ttu-id="fe849-384">libicu</span><span class="sxs-lookup"><span data-stu-id="fe849-384">libicu</span></span>
- <span data-ttu-id="fe849-385">zlib</span><span class="sxs-lookup"><span data-stu-id="fe849-385">zlib</span></span>

<span data-ttu-id="fe849-386">Fedora 用户：如果 OpenSSL 的版本为 1.1 及更高版本，则需要安装 compat-openssl10  。</span><span class="sxs-lookup"><span data-stu-id="fe849-386">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="fe849-387">对于 .NET Core 2.0，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="fe849-387">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="fe849-388">libunwind</span><span class="sxs-lookup"><span data-stu-id="fe849-388">libunwind</span></span>
- <span data-ttu-id="fe849-389">libuuid</span><span class="sxs-lookup"><span data-stu-id="fe849-389">libuuid</span></span>

<span data-ttu-id="fe849-390">有关依赖项的详细信息，请参阅[独立式 Linux 应用](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="fe849-390">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="fe849-391">对于使用 System.Drawing.Common  程序集的 .NET Core 应用，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="fe849-391">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="fe849-392">libgdiplus（版本 6.0.1 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="fe849-392">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="fe849-393">CentOS 和 Fedora 的大多数版本都包含 libgdiplus 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="fe849-393">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="fe849-394">可以通过将 Mono 存储库添加到系统来安装最新版 libgdiplus。</span><span class="sxs-lookup"><span data-stu-id="fe849-394">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="fe849-395">有关详细信息，请参阅 <https://www.mono-project.com/download/stable/>。</span><span class="sxs-lookup"><span data-stu-id="fe849-395">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="fe849-396">以下 macOS 版本支持 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="fe849-396">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="fe849-397">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="fe849-397">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="fe849-398">.NET Core 版本</span><span class="sxs-lookup"><span data-stu-id="fe849-398">.NET Core Version</span></span> | <span data-ttu-id="fe849-399">macOS</span><span class="sxs-lookup"><span data-stu-id="fe849-399">macOS</span></span>                 | <span data-ttu-id="fe849-400">体系结构</span><span class="sxs-lookup"><span data-stu-id="fe849-400">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="fe849-401">3.1</span><span class="sxs-lookup"><span data-stu-id="fe849-401">3.1</span></span>               | <span data-ttu-id="fe849-402">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="fe849-402">High Sierra (10.13+)</span></span>  | <span data-ttu-id="fe849-403">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-403">x64</span></span> | [<span data-ttu-id="fe849-404">详细信息</span><span class="sxs-lookup"><span data-stu-id="fe849-404">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="fe849-405">3.0</span><span class="sxs-lookup"><span data-stu-id="fe849-405">3.0</span></span>               | <span data-ttu-id="fe849-406">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="fe849-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="fe849-407">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-407">x64</span></span> | [<span data-ttu-id="fe849-408">详细信息</span><span class="sxs-lookup"><span data-stu-id="fe849-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="fe849-409">2.2</span><span class="sxs-lookup"><span data-stu-id="fe849-409">2.2</span></span>               | <span data-ttu-id="fe849-410">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="fe849-410">Sierra (10.12+)</span></span>       | <span data-ttu-id="fe849-411">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-411">x64</span></span> | [<span data-ttu-id="fe849-412">详细信息</span><span class="sxs-lookup"><span data-stu-id="fe849-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="fe849-413">2.1</span><span class="sxs-lookup"><span data-stu-id="fe849-413">2.1</span></span>               | <span data-ttu-id="fe849-414">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="fe849-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="fe849-415">X64</span><span class="sxs-lookup"><span data-stu-id="fe849-415">x64</span></span> | [<span data-ttu-id="fe849-416">详细信息</span><span class="sxs-lookup"><span data-stu-id="fe849-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

## <a name="libgdiplus"></a><span data-ttu-id="fe849-417">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="fe849-417">libgdiplus</span></span>

<span data-ttu-id="fe849-418">使用 System.Drawing.Common  程序集的 .NET Core 应用程序要求安装 libgdiplus。</span><span class="sxs-lookup"><span data-stu-id="fe849-418">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="fe849-419">获取 libgdiplus 的一个简单方法是使用适用于 macOS 的 [Homebrew (“brew”)](https://brew.sh/) 包。</span><span class="sxs-lookup"><span data-stu-id="fe849-419">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="fe849-420">在安装 brew 后，通过在终端（命令）提示符处执行以下命令来安装 libgdiplus  ：</span><span class="sxs-lookup"><span data-stu-id="fe849-420">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="fe849-421">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fe849-421">Next steps</span></span>

- <span data-ttu-id="fe849-422">若要开发并运行应用，请安装 [.NET Core SDK](sdk.md)（包括运行时）。</span><span class="sxs-lookup"><span data-stu-id="fe849-422">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="fe849-423">若要运行其他人创建的应用，请安装 [.NET Core 运行时](runtime.md)。</span><span class="sxs-lookup"><span data-stu-id="fe849-423">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
