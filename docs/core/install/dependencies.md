---
title: .NET Core SDK 和运行时依赖项 - .NET Core
description: 详细介绍在 Windows、Linux 和 macOS 上安装 .NET Core SDK 和运行时的操作系统和 CPU 体系结构先决条件。
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: ca86b3c158bb38c1293cd4303dcf4c00ea9175b1
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157800"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="c3c9a-103">.NET Core 依赖项和要求</span><span class="sxs-lookup"><span data-stu-id="c3c9a-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="c3c9a-104">本文详细介绍了 .NET Core 支持的操作系统和 CPU 体系结构。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="c3c9a-105">支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="c3c9a-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="c3c9a-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="c3c9a-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="c3c9a-107">.NET Core 3.1 支持下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="c3c9a-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="c3c9a-108">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c3c9a-109">(OS)</span><span class="sxs-lookup"><span data-stu-id="c3c9a-109">OS</span></span>                            | <span data-ttu-id="c3c9a-110">Version</span><span class="sxs-lookup"><span data-stu-id="c3c9a-110">Version</span></span>                        | <span data-ttu-id="c3c9a-111">体系结构</span><span class="sxs-lookup"><span data-stu-id="c3c9a-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="c3c9a-112">Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="c3c9a-112">Windows Client</span></span>                | <span data-ttu-id="c3c9a-113">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="c3c9a-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="c3c9a-114">x64、x86</span><span class="sxs-lookup"><span data-stu-id="c3c9a-114">x64, x86</span></span>        |
| <span data-ttu-id="c3c9a-115">Windows 10 客户端</span><span class="sxs-lookup"><span data-stu-id="c3c9a-115">Windows 10 Client</span></span>             | <span data-ttu-id="c3c9a-116">版本 1607+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-116">Version 1607+</span></span>                  | <span data-ttu-id="c3c9a-117">x64、x86</span><span class="sxs-lookup"><span data-stu-id="c3c9a-117">x64, x86</span></span>        |
| <span data-ttu-id="c3c9a-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="c3c9a-118">Windows Server</span></span>                | <span data-ttu-id="c3c9a-119">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-119">2012 R2+</span></span>                       | <span data-ttu-id="c3c9a-120">x64、x86</span><span class="sxs-lookup"><span data-stu-id="c3c9a-120">x64, x86</span></span>        |
| <span data-ttu-id="c3c9a-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="c3c9a-121">Nano Server</span></span>                   | <span data-ttu-id="c3c9a-122">版本 1803+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-122">Version 1803+</span></span>                  | <span data-ttu-id="c3c9a-123">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="c3c9a-123">x64, ARM32</span></span>      |

<span data-ttu-id="c3c9a-124">有关 .NET Core 3.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="c3c9a-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c3c9a-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="c3c9a-126">.NET Core 3.0 支持下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="c3c9a-126">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="c3c9a-127">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-127">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c3c9a-128">(OS)</span><span class="sxs-lookup"><span data-stu-id="c3c9a-128">OS</span></span>                            | <span data-ttu-id="c3c9a-129">Version</span><span class="sxs-lookup"><span data-stu-id="c3c9a-129">Version</span></span>                        | <span data-ttu-id="c3c9a-130">体系结构</span><span class="sxs-lookup"><span data-stu-id="c3c9a-130">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="c3c9a-131">Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="c3c9a-131">Windows Client</span></span>                | <span data-ttu-id="c3c9a-132">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="c3c9a-132">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="c3c9a-133">x64、x86</span><span class="sxs-lookup"><span data-stu-id="c3c9a-133">x64, x86</span></span>        |
| <span data-ttu-id="c3c9a-134">Windows 10 客户端</span><span class="sxs-lookup"><span data-stu-id="c3c9a-134">Windows 10 Client</span></span>             | <span data-ttu-id="c3c9a-135">版本 1607+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-135">Version 1607+</span></span>                  | <span data-ttu-id="c3c9a-136">x64、x86</span><span class="sxs-lookup"><span data-stu-id="c3c9a-136">x64, x86</span></span>        |
| <span data-ttu-id="c3c9a-137">Windows Server</span><span class="sxs-lookup"><span data-stu-id="c3c9a-137">Windows Server</span></span>                | <span data-ttu-id="c3c9a-138">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-138">2012 R2+</span></span>                       | <span data-ttu-id="c3c9a-139">x64、x86</span><span class="sxs-lookup"><span data-stu-id="c3c9a-139">x64, x86</span></span>        |
| <span data-ttu-id="c3c9a-140">Nano Server</span><span class="sxs-lookup"><span data-stu-id="c3c9a-140">Nano Server</span></span>                   | <span data-ttu-id="c3c9a-141">版本 1803+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-141">Version 1803+</span></span>                  | <span data-ttu-id="c3c9a-142">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="c3c9a-142">x64, ARM32</span></span>      |

<span data-ttu-id="c3c9a-143">有关 .NET Core 3.0 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.0 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-143">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="c3c9a-144">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="c3c9a-144">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="c3c9a-145">.NET Core 2.2 支持下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="c3c9a-145">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="c3c9a-146">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-146">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c3c9a-147">(OS)</span><span class="sxs-lookup"><span data-stu-id="c3c9a-147">OS</span></span>                            | <span data-ttu-id="c3c9a-148">Version</span><span class="sxs-lookup"><span data-stu-id="c3c9a-148">Version</span></span>                        | <span data-ttu-id="c3c9a-149">体系结构</span><span class="sxs-lookup"><span data-stu-id="c3c9a-149">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="c3c9a-150">Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="c3c9a-150">Windows Client</span></span>                | <span data-ttu-id="c3c9a-151">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="c3c9a-151">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="c3c9a-152">x64、x86</span><span class="sxs-lookup"><span data-stu-id="c3c9a-152">x64, x86</span></span>        |
| <span data-ttu-id="c3c9a-153">Windows 10 客户端</span><span class="sxs-lookup"><span data-stu-id="c3c9a-153">Windows 10 Client</span></span>             | <span data-ttu-id="c3c9a-154">版本 1607+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-154">Version 1607+</span></span>                  | <span data-ttu-id="c3c9a-155">x64、x86</span><span class="sxs-lookup"><span data-stu-id="c3c9a-155">x64, x86</span></span>        |
| <span data-ttu-id="c3c9a-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="c3c9a-156">Windows Server</span></span>                | <span data-ttu-id="c3c9a-157">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-157">2008 R2 SP1+</span></span>                   | <span data-ttu-id="c3c9a-158">x64、x86</span><span class="sxs-lookup"><span data-stu-id="c3c9a-158">x64, x86</span></span>        |
| <span data-ttu-id="c3c9a-159">Nano Server</span><span class="sxs-lookup"><span data-stu-id="c3c9a-159">Nano Server</span></span>                   | <span data-ttu-id="c3c9a-160">版本 1803+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-160">Version 1803+</span></span>                   | <span data-ttu-id="c3c9a-161">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="c3c9a-161">x64, ARM32</span></span>      |

<span data-ttu-id="c3c9a-162">有关 .NET Core 2.2 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.2 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-162">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="c3c9a-163">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c3c9a-163">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="c3c9a-164">.NET Core 2.1 支持下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="c3c9a-164">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="c3c9a-165">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-165">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c3c9a-166">(OS)</span><span class="sxs-lookup"><span data-stu-id="c3c9a-166">OS</span></span>                            | <span data-ttu-id="c3c9a-167">Version</span><span class="sxs-lookup"><span data-stu-id="c3c9a-167">Version</span></span>                        | <span data-ttu-id="c3c9a-168">体系结构</span><span class="sxs-lookup"><span data-stu-id="c3c9a-168">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="c3c9a-169">Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="c3c9a-169">Windows Client</span></span>                | <span data-ttu-id="c3c9a-170">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="c3c9a-170">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="c3c9a-171">x64、x86</span><span class="sxs-lookup"><span data-stu-id="c3c9a-171">x64, x86</span></span>        |
| <span data-ttu-id="c3c9a-172">Windows 10 客户端</span><span class="sxs-lookup"><span data-stu-id="c3c9a-172">Windows 10 Client</span></span>             | <span data-ttu-id="c3c9a-173">版本 1607+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-173">Version 1607+</span></span>                  | <span data-ttu-id="c3c9a-174">x64、x86</span><span class="sxs-lookup"><span data-stu-id="c3c9a-174">x64, x86</span></span>        |
| <span data-ttu-id="c3c9a-175">Windows Server</span><span class="sxs-lookup"><span data-stu-id="c3c9a-175">Windows Server</span></span>                | <span data-ttu-id="c3c9a-176">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-176">2008 R2 SP1+</span></span>                   | <span data-ttu-id="c3c9a-177">x64、x86</span><span class="sxs-lookup"><span data-stu-id="c3c9a-177">x64, x86</span></span>        |
| <span data-ttu-id="c3c9a-178">Nano Server</span><span class="sxs-lookup"><span data-stu-id="c3c9a-178">Nano Server</span></span>                   | <span data-ttu-id="c3c9a-179">版本 1803+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-179">Version 1803+</span></span>                  | <span data-ttu-id="c3c9a-180">x64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-180">x64,</span></span>            |

<span data-ttu-id="c3c9a-181">有关 .NET Core 2.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-181">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="c3c9a-182">Windows 7/Vista/8.1/Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="c3c9a-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="c3c9a-183">如果要在以下 Windows 版本上安装 .NET SDK 或运行时，则需要其他依赖项：</span><span class="sxs-lookup"><span data-stu-id="c3c9a-183">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="c3c9a-184">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="c3c9a-184">Windows 7 SP1</span></span>
- <span data-ttu-id="c3c9a-185">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="c3c9a-185">Windows Vista SP 2</span></span>
- <span data-ttu-id="c3c9a-186">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="c3c9a-186">Windows 8.1</span></span>
- <span data-ttu-id="c3c9a-187">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="c3c9a-187">Windows Server 2008 R2</span></span>
- <span data-ttu-id="c3c9a-188">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c3c9a-188">Windows Server 2012 R2</span></span>

<span data-ttu-id="c3c9a-189">安装以下组件：</span><span class="sxs-lookup"><span data-stu-id="c3c9a-189">Install the following:</span></span>

- <span data-ttu-id="c3c9a-190">[Microsoft Visual C++ 2015 Redistributable 更新 3](https://www.microsoft.com/download/details.aspx?id=52685)。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="c3c9a-191">KB2533623</span><span class="sxs-lookup"><span data-stu-id="c3c9a-191">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="c3c9a-192">如果遇到一个以下错误，也需要满足上述要求：</span><span class="sxs-lookup"><span data-stu-id="c3c9a-192">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="c3c9a-193">此程序无法启动，因为计算机上缺少 api-ms-win-crt-runtime-l1-1-0.dll  。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-193">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="c3c9a-194">尝试重新安装该程序以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-194">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="c3c9a-195">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="c3c9a-195">\- or -</span></span>
>
> <span data-ttu-id="c3c9a-196">已找到库 hostfxr.dll  ，但未能将其从 C:\\\<path_to_app>\\hostfxr.dll 中加载  。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-196">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="c3c9a-197">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="c3c9a-197">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="c3c9a-198">.NET Core 3.1 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-198">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="c3c9a-199">对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-199">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="c3c9a-200">以下 Linux 发行版/版本支持 .NET Core 3.1：</span><span class="sxs-lookup"><span data-stu-id="c3c9a-200">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="c3c9a-201">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-201">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c3c9a-202">(OS)</span><span class="sxs-lookup"><span data-stu-id="c3c9a-202">OS</span></span>                             | <span data-ttu-id="c3c9a-203">Version</span><span class="sxs-lookup"><span data-stu-id="c3c9a-203">Version</span></span>               | <span data-ttu-id="c3c9a-204">体系结构</span><span class="sxs-lookup"><span data-stu-id="c3c9a-204">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="c3c9a-205">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c3c9a-205">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="c3c9a-206">6、7、8</span><span class="sxs-lookup"><span data-stu-id="c3c9a-206">6, 7, 8</span></span>               | <span data-ttu-id="c3c9a-207">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-207">x64</span></span> |
| <span data-ttu-id="c3c9a-208">CentOS</span><span class="sxs-lookup"><span data-stu-id="c3c9a-208">CentOS</span></span>                         | <span data-ttu-id="c3c9a-209">7+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-209">7+</span></span>                    | <span data-ttu-id="c3c9a-210">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-210">x64</span></span> |
| <span data-ttu-id="c3c9a-211">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="c3c9a-211">Oracle Linux</span></span>                   | <span data-ttu-id="c3c9a-212">7+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-212">7+</span></span>                    | <span data-ttu-id="c3c9a-213">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-213">x64</span></span> |
| <span data-ttu-id="c3c9a-214">Fedora</span><span class="sxs-lookup"><span data-stu-id="c3c9a-214">Fedora</span></span>                         | <span data-ttu-id="c3c9a-215">29+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-215">29+</span></span>                   | <span data-ttu-id="c3c9a-216">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-216">x64</span></span> |
| <span data-ttu-id="c3c9a-217">Debian</span><span class="sxs-lookup"><span data-stu-id="c3c9a-217">Debian</span></span>                         | <span data-ttu-id="c3c9a-218">9+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-218">9+</span></span>                    | <span data-ttu-id="c3c9a-219">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-219">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="c3c9a-220">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c3c9a-220">Ubuntu</span></span>                         | <span data-ttu-id="c3c9a-221">16.04+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-221">16.04+</span></span>                | <span data-ttu-id="c3c9a-222">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-222">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="c3c9a-223">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="c3c9a-223">Linux Mint</span></span>                     | <span data-ttu-id="c3c9a-224">18+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-224">18+</span></span>                   | <span data-ttu-id="c3c9a-225">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-225">x64</span></span> |
| <span data-ttu-id="c3c9a-226">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c3c9a-226">openSUSE</span></span>                       | <span data-ttu-id="c3c9a-227">15+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-227">15+</span></span>                   | <span data-ttu-id="c3c9a-228">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-228">x64</span></span> |
| <span data-ttu-id="c3c9a-229">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="c3c9a-229">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="c3c9a-230">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-230">12 SP2+</span></span>               | <span data-ttu-id="c3c9a-231">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-231">x64</span></span> |
| <span data-ttu-id="c3c9a-232">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c3c9a-232">Alpine Linux</span></span>                   | <span data-ttu-id="c3c9a-233">3.10+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-233">3.10+</span></span>                 | <span data-ttu-id="c3c9a-234">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-234">x64, ARM64</span></span> |

<span data-ttu-id="c3c9a-235">有关 .NET Core 3.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-235">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="c3c9a-236">有关如何在 ARM64（内核 4.14+）上安装 .NET Core 3.1 的详细信息，请参阅[在 Linux ARM64 上安装 .NET Core 3.0](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-236">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3c9a-237">ARM64 支持需要 Linux 内核 4.14 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-237">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="c3c9a-238">某些 linux 发行版满足此要求，而另一些则不满足。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-238">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="c3c9a-239">例如，支持 Ubuntu 18.04，但不支持 Ubuntu 16.04。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-239">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="c3c9a-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c3c9a-240">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="c3c9a-241">.NET Core 3.0 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-241">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="c3c9a-242">对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-242">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="c3c9a-243">以下 Linux 发行版本/版本支持 .NET Core 3.0：</span><span class="sxs-lookup"><span data-stu-id="c3c9a-243">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="c3c9a-244">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-244">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c3c9a-245">(OS)</span><span class="sxs-lookup"><span data-stu-id="c3c9a-245">OS</span></span>                             | <span data-ttu-id="c3c9a-246">Version</span><span class="sxs-lookup"><span data-stu-id="c3c9a-246">Version</span></span>               | <span data-ttu-id="c3c9a-247">体系结构</span><span class="sxs-lookup"><span data-stu-id="c3c9a-247">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="c3c9a-248">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c3c9a-248">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="c3c9a-249">6、7、8</span><span class="sxs-lookup"><span data-stu-id="c3c9a-249">6, 7, 8</span></span>               | <span data-ttu-id="c3c9a-250">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-250">x64</span></span> |
| <span data-ttu-id="c3c9a-251">CentOS</span><span class="sxs-lookup"><span data-stu-id="c3c9a-251">CentOS</span></span>                         | <span data-ttu-id="c3c9a-252">7+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-252">7+</span></span>                    | <span data-ttu-id="c3c9a-253">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-253">x64</span></span> |
| <span data-ttu-id="c3c9a-254">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="c3c9a-254">Oracle Linux</span></span>                   | <span data-ttu-id="c3c9a-255">7+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-255">7+</span></span>                    | <span data-ttu-id="c3c9a-256">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-256">x64</span></span> |
| <span data-ttu-id="c3c9a-257">Fedora</span><span class="sxs-lookup"><span data-stu-id="c3c9a-257">Fedora</span></span>                         | <span data-ttu-id="c3c9a-258">29+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-258">29+</span></span>                   | <span data-ttu-id="c3c9a-259">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-259">x64</span></span> |
| <span data-ttu-id="c3c9a-260">Debian</span><span class="sxs-lookup"><span data-stu-id="c3c9a-260">Debian</span></span>                         | <span data-ttu-id="c3c9a-261">9+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-261">9+</span></span>                    | <span data-ttu-id="c3c9a-262">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-262">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="c3c9a-263">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c3c9a-263">Ubuntu</span></span>                         | <span data-ttu-id="c3c9a-264">16.04+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-264">16.04+</span></span>                | <span data-ttu-id="c3c9a-265">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="c3c9a-266">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="c3c9a-266">Linux Mint</span></span>                     | <span data-ttu-id="c3c9a-267">18+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-267">18+</span></span>                   | <span data-ttu-id="c3c9a-268">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-268">x64</span></span> |
| <span data-ttu-id="c3c9a-269">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c3c9a-269">openSUSE</span></span>                       | <span data-ttu-id="c3c9a-270">15+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-270">15+</span></span>                   | <span data-ttu-id="c3c9a-271">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-271">x64</span></span> |
| <span data-ttu-id="c3c9a-272">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="c3c9a-272">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="c3c9a-273">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-273">12 SP2+</span></span>               | <span data-ttu-id="c3c9a-274">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-274">x64</span></span> |
| <span data-ttu-id="c3c9a-275">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c3c9a-275">Alpine Linux</span></span>                   | <span data-ttu-id="c3c9a-276">3.8+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-276">3.8+</span></span>                  | <span data-ttu-id="c3c9a-277">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-277">x64, ARM64</span></span> |

<span data-ttu-id="c3c9a-278">有关 .NET Core 3.0 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.0 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-278">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="c3c9a-279">有关如何在 ARM64 上安装 .NET Core 3.0 的详细信息，请参阅[在 Linux ARM64 上安装 .NET Core 3.0](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-279">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="c3c9a-280">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="c3c9a-280">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="c3c9a-281">.NET Core 2.2 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-281">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="c3c9a-282">对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-282">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="c3c9a-283">以下 Linux 发行版本/版本支持 .NET Core 2.2：</span><span class="sxs-lookup"><span data-stu-id="c3c9a-283">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="c3c9a-284">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-284">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c3c9a-285">(OS)</span><span class="sxs-lookup"><span data-stu-id="c3c9a-285">OS</span></span>                             |  <span data-ttu-id="c3c9a-286">Version</span><span class="sxs-lookup"><span data-stu-id="c3c9a-286">Version</span></span>                |  <span data-ttu-id="c3c9a-287">体系结构</span><span class="sxs-lookup"><span data-stu-id="c3c9a-287">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="c3c9a-288">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c3c9a-288">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="c3c9a-289">6、7</span><span class="sxs-lookup"><span data-stu-id="c3c9a-289">6, 7</span></span>                   | <span data-ttu-id="c3c9a-290">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-290">x64</span></span> |
| <span data-ttu-id="c3c9a-291">CentOS</span><span class="sxs-lookup"><span data-stu-id="c3c9a-291">CentOS</span></span>                         |  <span data-ttu-id="c3c9a-292">7</span><span class="sxs-lookup"><span data-stu-id="c3c9a-292">7</span></span>                      | <span data-ttu-id="c3c9a-293">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-293">x64</span></span> |
| <span data-ttu-id="c3c9a-294">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="c3c9a-294">Oracle Linux</span></span>                   |  <span data-ttu-id="c3c9a-295">7</span><span class="sxs-lookup"><span data-stu-id="c3c9a-295">7</span></span>                      | <span data-ttu-id="c3c9a-296">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-296">x64</span></span> |
| <span data-ttu-id="c3c9a-297">Fedora</span><span class="sxs-lookup"><span data-stu-id="c3c9a-297">Fedora</span></span>                         |  <span data-ttu-id="c3c9a-298">29、30</span><span class="sxs-lookup"><span data-stu-id="c3c9a-298">29, 30</span></span>                 | <span data-ttu-id="c3c9a-299">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-299">x64</span></span> |
| <span data-ttu-id="c3c9a-300">Debian</span><span class="sxs-lookup"><span data-stu-id="c3c9a-300">Debian</span></span>                         |  <span data-ttu-id="c3c9a-301">9</span><span class="sxs-lookup"><span data-stu-id="c3c9a-301">9</span></span>                      | <span data-ttu-id="c3c9a-302">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="c3c9a-302">x64, ARM32</span></span> |
| <span data-ttu-id="c3c9a-303">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c3c9a-303">Ubuntu</span></span>                         |  <span data-ttu-id="c3c9a-304">16.04、18.04、18.10</span><span class="sxs-lookup"><span data-stu-id="c3c9a-304">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="c3c9a-305">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="c3c9a-305">x64, ARM32</span></span> |
| <span data-ttu-id="c3c9a-306">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="c3c9a-306">Linux Mint</span></span>                     |  <span data-ttu-id="c3c9a-307">17、18</span><span class="sxs-lookup"><span data-stu-id="c3c9a-307">17, 18</span></span>                 | <span data-ttu-id="c3c9a-308">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-308">x64</span></span> |
| <span data-ttu-id="c3c9a-309">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c3c9a-309">openSUSE</span></span>                       |  <span data-ttu-id="c3c9a-310">15+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-310">15+</span></span>                    | <span data-ttu-id="c3c9a-311">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-311">x64</span></span> |
| <span data-ttu-id="c3c9a-312">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="c3c9a-312">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="c3c9a-313">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-313">12 SP2+</span></span>                | <span data-ttu-id="c3c9a-314">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-314">x64</span></span> |
| <span data-ttu-id="c3c9a-315">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c3c9a-315">Alpine Linux</span></span>                   |  <span data-ttu-id="c3c9a-316">3.8+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-316">3.8+</span></span>                   | <span data-ttu-id="c3c9a-317">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-317">x64</span></span> |

<span data-ttu-id="c3c9a-318">有关 .NET Core 2.2 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.2 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-318">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="c3c9a-319">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c3c9a-319">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="c3c9a-320">.NET Core 2.1 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-320">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="c3c9a-321">对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-321">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="c3c9a-322">以下 Linux 发行版本/版本支持 .NET Core 2.1：</span><span class="sxs-lookup"><span data-stu-id="c3c9a-322">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="c3c9a-323">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-323">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c3c9a-324">(OS)</span><span class="sxs-lookup"><span data-stu-id="c3c9a-324">OS</span></span>                             |  <span data-ttu-id="c3c9a-325">Version</span><span class="sxs-lookup"><span data-stu-id="c3c9a-325">Version</span></span>                |  <span data-ttu-id="c3c9a-326">体系结构</span><span class="sxs-lookup"><span data-stu-id="c3c9a-326">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="c3c9a-327">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c3c9a-327">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="c3c9a-328">6、7、8</span><span class="sxs-lookup"><span data-stu-id="c3c9a-328">6, 7, 8</span></span>                | <span data-ttu-id="c3c9a-329">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-329">x64</span></span> |
| <span data-ttu-id="c3c9a-330">CentOS</span><span class="sxs-lookup"><span data-stu-id="c3c9a-330">CentOS</span></span>                         |  <span data-ttu-id="c3c9a-331">7+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-331">7+</span></span>                     | <span data-ttu-id="c3c9a-332">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-332">x64</span></span> |
| <span data-ttu-id="c3c9a-333">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="c3c9a-333">Oracle Linux</span></span>                   |  <span data-ttu-id="c3c9a-334">7+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-334">7+</span></span>                     | <span data-ttu-id="c3c9a-335">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-335">x64</span></span> |
| <span data-ttu-id="c3c9a-336">Fedora</span><span class="sxs-lookup"><span data-stu-id="c3c9a-336">Fedora</span></span>                         |  <span data-ttu-id="c3c9a-337">29+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-337">29+</span></span>                    | <span data-ttu-id="c3c9a-338">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-338">x64</span></span> |
| <span data-ttu-id="c3c9a-339">Debian</span><span class="sxs-lookup"><span data-stu-id="c3c9a-339">Debian</span></span>                         |  <span data-ttu-id="c3c9a-340">9</span><span class="sxs-lookup"><span data-stu-id="c3c9a-340">9</span></span>                      | <span data-ttu-id="c3c9a-341">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="c3c9a-341">x64, ARM32</span></span> |
| <span data-ttu-id="c3c9a-342">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c3c9a-342">Ubuntu</span></span>                         |  <span data-ttu-id="c3c9a-343">16.04、18.04、19.04、19.10</span><span class="sxs-lookup"><span data-stu-id="c3c9a-343">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="c3c9a-344">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="c3c9a-344">x64, ARM32</span></span> |
| <span data-ttu-id="c3c9a-345">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="c3c9a-345">Linux Mint</span></span>                     |  <span data-ttu-id="c3c9a-346">17+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-346">17+</span></span>                    | <span data-ttu-id="c3c9a-347">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-347">x64</span></span> |
| <span data-ttu-id="c3c9a-348">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c3c9a-348">openSUSE</span></span>                       |  <span data-ttu-id="c3c9a-349">15+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-349">15+</span></span>                    | <span data-ttu-id="c3c9a-350">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-350">x64</span></span> |
| <span data-ttu-id="c3c9a-351">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="c3c9a-351">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="c3c9a-352">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-352">12 SP2+</span></span>                | <span data-ttu-id="c3c9a-353">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-353">x64</span></span> |
| <span data-ttu-id="c3c9a-354">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c3c9a-354">Alpine Linux</span></span>                   |  <span data-ttu-id="c3c9a-355">3.8+</span><span class="sxs-lookup"><span data-stu-id="c3c9a-355">3.8+</span></span>                   | <span data-ttu-id="c3c9a-356">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-356">x64</span></span> |

<span data-ttu-id="c3c9a-357">有关 .NET Core 2.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-357">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="c3c9a-358">Linux 发行版本依赖项</span><span class="sxs-lookup"><span data-stu-id="c3c9a-358">Linux distribution dependencies</span></span>

<span data-ttu-id="c3c9a-359">根据 Linux 发行版，你可能需要安装其他依赖项。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-359">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3c9a-360">确切的版本和名称可能因所选 Linux 发行版本略有不同。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-360">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="c3c9a-361">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c3c9a-361">Ubuntu</span></span>

<span data-ttu-id="c3c9a-362">Ubuntu 发行版需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="c3c9a-362">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="c3c9a-363">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="c3c9a-363">liblttng-ust0</span></span>
- <span data-ttu-id="c3c9a-364">libcurl3（针对 14.x 和 16.x）</span><span class="sxs-lookup"><span data-stu-id="c3c9a-364">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="c3c9a-365">libcurl4（针对 18.x）</span><span class="sxs-lookup"><span data-stu-id="c3c9a-365">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="c3c9a-366">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="c3c9a-366">libssl1.0.0</span></span>
- <span data-ttu-id="c3c9a-367">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="c3c9a-367">libkrb5-3</span></span>
- <span data-ttu-id="c3c9a-368">zlib1g</span><span class="sxs-lookup"><span data-stu-id="c3c9a-368">zlib1g</span></span>
- <span data-ttu-id="c3c9a-369">libicu52（针对 14.x）</span><span class="sxs-lookup"><span data-stu-id="c3c9a-369">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="c3c9a-370">libicu55（针对 16.x）</span><span class="sxs-lookup"><span data-stu-id="c3c9a-370">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="c3c9a-371">libicu57（针对 17.x）</span><span class="sxs-lookup"><span data-stu-id="c3c9a-371">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="c3c9a-372">libicu60（针对 18.x）</span><span class="sxs-lookup"><span data-stu-id="c3c9a-372">libicu60 (for 18.x)</span></span>

<span data-ttu-id="c3c9a-373">对于使用 System.Drawing.Common  程序集的 .NET Core 应用，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="c3c9a-373">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="c3c9a-374">libgdiplus（版本 6.0.1 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="c3c9a-374">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="c3c9a-375">大多数 Ubuntu 版本都包含 libgdiplus 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-375">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="c3c9a-376">可以通过将 Mono 存储库添加到系统来安装最新版 libgdiplus。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-376">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="c3c9a-377">有关详细信息，请参阅 <https://www.mono-project.com/download/stable/>。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-377">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="c3c9a-378">CentOS 和 Fedora</span><span class="sxs-lookup"><span data-stu-id="c3c9a-378">CentOS and Fedora</span></span>

<span data-ttu-id="c3c9a-379">CentOS 发行版本需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="c3c9a-379">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="c3c9a-380">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="c3c9a-380">lttng-ust</span></span>
- <span data-ttu-id="c3c9a-381">libcurl</span><span class="sxs-lookup"><span data-stu-id="c3c9a-381">libcurl</span></span>
- <span data-ttu-id="c3c9a-382">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="c3c9a-382">openssl-libs</span></span>
- <span data-ttu-id="c3c9a-383">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="c3c9a-383">krb5-libs</span></span>
- <span data-ttu-id="c3c9a-384">libicu</span><span class="sxs-lookup"><span data-stu-id="c3c9a-384">libicu</span></span>
- <span data-ttu-id="c3c9a-385">zlib</span><span class="sxs-lookup"><span data-stu-id="c3c9a-385">zlib</span></span>

<span data-ttu-id="c3c9a-386">Fedora 用户：如果 OpenSSL 的版本为 1.1 及更高版本，则需要安装 compat-openssl10  。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-386">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="c3c9a-387">对于 .NET Core 2.0，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="c3c9a-387">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="c3c9a-388">libunwind</span><span class="sxs-lookup"><span data-stu-id="c3c9a-388">libunwind</span></span>
- <span data-ttu-id="c3c9a-389">libuuid</span><span class="sxs-lookup"><span data-stu-id="c3c9a-389">libuuid</span></span>

<span data-ttu-id="c3c9a-390">有关依赖项的详细信息，请参阅[独立式 Linux 应用](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-390">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="c3c9a-391">对于使用 System.Drawing.Common  程序集的 .NET Core 应用，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="c3c9a-391">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="c3c9a-392">libgdiplus（版本 6.0.1 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="c3c9a-392">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="c3c9a-393">CentOS 和 Fedora 的大多数版本都包含 libgdiplus 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-393">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="c3c9a-394">可以通过将 Mono 存储库添加到系统来安装最新版 libgdiplus。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-394">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="c3c9a-395">有关详细信息，请参阅 <https://www.mono-project.com/download/stable/>。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-395">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="c3c9a-396">以下 macOS 版本支持 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="c3c9a-396">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="c3c9a-397">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-397">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c3c9a-398">.NET Core 版本</span><span class="sxs-lookup"><span data-stu-id="c3c9a-398">.NET Core Version</span></span> | <span data-ttu-id="c3c9a-399">macOS</span><span class="sxs-lookup"><span data-stu-id="c3c9a-399">macOS</span></span>                 | <span data-ttu-id="c3c9a-400">体系结构</span><span class="sxs-lookup"><span data-stu-id="c3c9a-400">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="c3c9a-401">3.1</span><span class="sxs-lookup"><span data-stu-id="c3c9a-401">3.1</span></span>               | <span data-ttu-id="c3c9a-402">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="c3c9a-402">High Sierra (10.13+)</span></span>  | <span data-ttu-id="c3c9a-403">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-403">x64</span></span> | [<span data-ttu-id="c3c9a-404">详细信息</span><span class="sxs-lookup"><span data-stu-id="c3c9a-404">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="c3c9a-405">3.0</span><span class="sxs-lookup"><span data-stu-id="c3c9a-405">3.0</span></span>               | <span data-ttu-id="c3c9a-406">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="c3c9a-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="c3c9a-407">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-407">x64</span></span> | [<span data-ttu-id="c3c9a-408">详细信息</span><span class="sxs-lookup"><span data-stu-id="c3c9a-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="c3c9a-409">2.2</span><span class="sxs-lookup"><span data-stu-id="c3c9a-409">2.2</span></span>               | <span data-ttu-id="c3c9a-410">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="c3c9a-410">Sierra (10.12+)</span></span>       | <span data-ttu-id="c3c9a-411">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-411">x64</span></span> | [<span data-ttu-id="c3c9a-412">详细信息</span><span class="sxs-lookup"><span data-stu-id="c3c9a-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="c3c9a-413">2.1</span><span class="sxs-lookup"><span data-stu-id="c3c9a-413">2.1</span></span>               | <span data-ttu-id="c3c9a-414">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="c3c9a-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="c3c9a-415">X64</span><span class="sxs-lookup"><span data-stu-id="c3c9a-415">x64</span></span> | [<span data-ttu-id="c3c9a-416">详细信息</span><span class="sxs-lookup"><span data-stu-id="c3c9a-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="c3c9a-417">自 macOS Catalina（版本10.15）开始，所有在 2019 年 6 月 1 日之后生成并使用开发者 ID 扩散的软件都必须经过公证。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-417">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="c3c9a-418">此要求应用于 .NET Core 运行时、.NET Core SDK 以及使用 .NET Core 创建的软件。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-418">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="c3c9a-419">自 2020 年 2 月 18 日起，.NET Core（运行时和 SDK）版本 3.1、3.0 和 2.1 的安装程序都已经过公证。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-419">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="c3c9a-420">以前发布的版本没有经过公证。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-420">Prior released versions aren't notarized.</span></span> <span data-ttu-id="c3c9a-421">如果运行未经过公证的应用，将看到类似于下图的错误：</span><span class="sxs-lookup"><span data-stu-id="c3c9a-421">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![macOS Catalina 公证警报](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="c3c9a-423">若要详细了解强制执行的公证要求对 .NET Core 和 .NET Core 应用的影响，请参阅[处理 macOS Catalina 公证](macos-notarization-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-423">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="c3c9a-424">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="c3c9a-424">libgdiplus</span></span>

<span data-ttu-id="c3c9a-425">使用 System.Drawing.Common  程序集的 .NET Core 应用程序要求安装 libgdiplus。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-425">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="c3c9a-426">获取 libgdiplus 的一个简单方法是使用适用于 macOS 的 [Homebrew (“brew”)](https://brew.sh/) 包。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-426">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="c3c9a-427">在安装 brew 后，通过在终端（命令）提示符处执行以下命令来安装 libgdiplus  ：</span><span class="sxs-lookup"><span data-stu-id="c3c9a-427">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="c3c9a-428">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c3c9a-428">Next steps</span></span>

- <span data-ttu-id="c3c9a-429">若要开发并运行应用，请安装 [.NET Core SDK](sdk.md)（包括运行时）。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-429">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="c3c9a-430">若要运行其他人创建的应用，请安装 [.NET Core 运行时](runtime.md)。</span><span class="sxs-lookup"><span data-stu-id="c3c9a-430">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
