---
title: .NET Core SDK 和运行时依赖项 - .NET Core
description: 详细介绍在 Windows、Linux 和 macOS 上安装 .NET Core SDK 和运行时的操作系统和 CPU 体系结构先决条件。
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 023b8fdf029dd6b17fe2186296d87dd7507c60b5
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546557"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="a0e11-103">.NET Core 依赖项和要求</span><span class="sxs-lookup"><span data-stu-id="a0e11-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="a0e11-104">本文详细介绍了 .NET Core 支持的操作系统和 CPU 体系结构。</span><span class="sxs-lookup"><span data-stu-id="a0e11-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="a0e11-105">支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="a0e11-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="a0e11-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a0e11-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="a0e11-107">.NET Core 3.1 支持下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="a0e11-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="a0e11-108">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="a0e11-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a0e11-109">(OS)</span><span class="sxs-lookup"><span data-stu-id="a0e11-109">OS</span></span>                            | <span data-ttu-id="a0e11-110">Version</span><span class="sxs-lookup"><span data-stu-id="a0e11-110">Version</span></span>                        | <span data-ttu-id="a0e11-111">体系结构</span><span class="sxs-lookup"><span data-stu-id="a0e11-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="a0e11-112">Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="a0e11-112">Windows Client</span></span>                | <span data-ttu-id="a0e11-113">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="a0e11-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="a0e11-114">x64、x86</span><span class="sxs-lookup"><span data-stu-id="a0e11-114">x64, x86</span></span>        |
| <span data-ttu-id="a0e11-115">Windows 10 客户端</span><span class="sxs-lookup"><span data-stu-id="a0e11-115">Windows 10 Client</span></span>             | <span data-ttu-id="a0e11-116">版本 1607+</span><span class="sxs-lookup"><span data-stu-id="a0e11-116">Version 1607+</span></span>                  | <span data-ttu-id="a0e11-117">x64、x86</span><span class="sxs-lookup"><span data-stu-id="a0e11-117">x64, x86</span></span>        |
| <span data-ttu-id="a0e11-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="a0e11-118">Windows Server</span></span>                | <span data-ttu-id="a0e11-119">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="a0e11-119">2012 R2+</span></span>                       | <span data-ttu-id="a0e11-120">x64、x86</span><span class="sxs-lookup"><span data-stu-id="a0e11-120">x64, x86</span></span>        |
| <span data-ttu-id="a0e11-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="a0e11-121">Nano Server</span></span>                   | <span data-ttu-id="a0e11-122">版本 1803+</span><span class="sxs-lookup"><span data-stu-id="a0e11-122">Version 1803+</span></span>                  | <span data-ttu-id="a0e11-123">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="a0e11-123">x64, ARM32</span></span>      |

<span data-ttu-id="a0e11-124">有关 .NET Core 3.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="a0e11-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="a0e11-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a0e11-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="a0e11-126">目前不支持 .NET Core 3.0。  有关详细信息，请参阅 [.NET Core 支持策略](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)。</span><span class="sxs-lookup"><span data-stu-id="a0e11-126">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="a0e11-127">.NET Core 3.0 支持下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="a0e11-127">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="a0e11-128">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="a0e11-128">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a0e11-129">(OS)</span><span class="sxs-lookup"><span data-stu-id="a0e11-129">OS</span></span>                            | <span data-ttu-id="a0e11-130">Version</span><span class="sxs-lookup"><span data-stu-id="a0e11-130">Version</span></span>                        | <span data-ttu-id="a0e11-131">体系结构</span><span class="sxs-lookup"><span data-stu-id="a0e11-131">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="a0e11-132">Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="a0e11-132">Windows Client</span></span>                | <span data-ttu-id="a0e11-133">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="a0e11-133">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="a0e11-134">x64、x86</span><span class="sxs-lookup"><span data-stu-id="a0e11-134">x64, x86</span></span>        |
| <span data-ttu-id="a0e11-135">Windows 10 客户端</span><span class="sxs-lookup"><span data-stu-id="a0e11-135">Windows 10 Client</span></span>             | <span data-ttu-id="a0e11-136">版本 1607+</span><span class="sxs-lookup"><span data-stu-id="a0e11-136">Version 1607+</span></span>                  | <span data-ttu-id="a0e11-137">x64、x86</span><span class="sxs-lookup"><span data-stu-id="a0e11-137">x64, x86</span></span>        |
| <span data-ttu-id="a0e11-138">Windows Server</span><span class="sxs-lookup"><span data-stu-id="a0e11-138">Windows Server</span></span>                | <span data-ttu-id="a0e11-139">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="a0e11-139">2012 R2+</span></span>                       | <span data-ttu-id="a0e11-140">x64、x86</span><span class="sxs-lookup"><span data-stu-id="a0e11-140">x64, x86</span></span>        |
| <span data-ttu-id="a0e11-141">Nano Server</span><span class="sxs-lookup"><span data-stu-id="a0e11-141">Nano Server</span></span>                   | <span data-ttu-id="a0e11-142">版本 1803+</span><span class="sxs-lookup"><span data-stu-id="a0e11-142">Version 1803+</span></span>                  | <span data-ttu-id="a0e11-143">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="a0e11-143">x64, ARM32</span></span>      |

<span data-ttu-id="a0e11-144">有关 .NET Core 3.0 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.0 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="a0e11-144">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="a0e11-145">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="a0e11-145">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="a0e11-146">目前不支持 .NET Core 2.2。  有关详细信息，请参阅 [.NET Core 支持策略](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)。</span><span class="sxs-lookup"><span data-stu-id="a0e11-146">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="a0e11-147">.NET Core 2.2 支持下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="a0e11-147">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="a0e11-148">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="a0e11-148">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a0e11-149">(OS)</span><span class="sxs-lookup"><span data-stu-id="a0e11-149">OS</span></span>                            | <span data-ttu-id="a0e11-150">Version</span><span class="sxs-lookup"><span data-stu-id="a0e11-150">Version</span></span>                        | <span data-ttu-id="a0e11-151">体系结构</span><span class="sxs-lookup"><span data-stu-id="a0e11-151">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="a0e11-152">Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="a0e11-152">Windows Client</span></span>                | <span data-ttu-id="a0e11-153">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="a0e11-153">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="a0e11-154">x64、x86</span><span class="sxs-lookup"><span data-stu-id="a0e11-154">x64, x86</span></span>        |
| <span data-ttu-id="a0e11-155">Windows 10 客户端</span><span class="sxs-lookup"><span data-stu-id="a0e11-155">Windows 10 Client</span></span>             | <span data-ttu-id="a0e11-156">版本 1607+</span><span class="sxs-lookup"><span data-stu-id="a0e11-156">Version 1607+</span></span>                  | <span data-ttu-id="a0e11-157">x64、x86</span><span class="sxs-lookup"><span data-stu-id="a0e11-157">x64, x86</span></span>        |
| <span data-ttu-id="a0e11-158">Windows Server</span><span class="sxs-lookup"><span data-stu-id="a0e11-158">Windows Server</span></span>                | <span data-ttu-id="a0e11-159">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="a0e11-159">2008 R2 SP1+</span></span>                   | <span data-ttu-id="a0e11-160">x64、x86</span><span class="sxs-lookup"><span data-stu-id="a0e11-160">x64, x86</span></span>        |
| <span data-ttu-id="a0e11-161">Nano Server</span><span class="sxs-lookup"><span data-stu-id="a0e11-161">Nano Server</span></span>                   | <span data-ttu-id="a0e11-162">版本 1803+</span><span class="sxs-lookup"><span data-stu-id="a0e11-162">Version 1803+</span></span>                   | <span data-ttu-id="a0e11-163">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="a0e11-163">x64, ARM32</span></span>      |

<span data-ttu-id="a0e11-164">有关 .NET Core 2.2 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.2 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="a0e11-164">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="a0e11-165">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a0e11-165">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="a0e11-166">.NET Core 2.1 支持下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="a0e11-166">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="a0e11-167">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="a0e11-167">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a0e11-168">(OS)</span><span class="sxs-lookup"><span data-stu-id="a0e11-168">OS</span></span>                            | <span data-ttu-id="a0e11-169">Version</span><span class="sxs-lookup"><span data-stu-id="a0e11-169">Version</span></span>                        | <span data-ttu-id="a0e11-170">体系结构</span><span class="sxs-lookup"><span data-stu-id="a0e11-170">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="a0e11-171">Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="a0e11-171">Windows Client</span></span>                | <span data-ttu-id="a0e11-172">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="a0e11-172">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="a0e11-173">x64、x86</span><span class="sxs-lookup"><span data-stu-id="a0e11-173">x64, x86</span></span>        |
| <span data-ttu-id="a0e11-174">Windows 10 客户端</span><span class="sxs-lookup"><span data-stu-id="a0e11-174">Windows 10 Client</span></span>             | <span data-ttu-id="a0e11-175">版本 1607+</span><span class="sxs-lookup"><span data-stu-id="a0e11-175">Version 1607+</span></span>                  | <span data-ttu-id="a0e11-176">x64、x86</span><span class="sxs-lookup"><span data-stu-id="a0e11-176">x64, x86</span></span>        |
| <span data-ttu-id="a0e11-177">Windows Server</span><span class="sxs-lookup"><span data-stu-id="a0e11-177">Windows Server</span></span>                | <span data-ttu-id="a0e11-178">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="a0e11-178">2008 R2 SP1+</span></span>                   | <span data-ttu-id="a0e11-179">x64、x86</span><span class="sxs-lookup"><span data-stu-id="a0e11-179">x64, x86</span></span>        |
| <span data-ttu-id="a0e11-180">Nano Server</span><span class="sxs-lookup"><span data-stu-id="a0e11-180">Nano Server</span></span>                   | <span data-ttu-id="a0e11-181">版本 1803+</span><span class="sxs-lookup"><span data-stu-id="a0e11-181">Version 1803+</span></span>                  | <span data-ttu-id="a0e11-182">x64</span><span class="sxs-lookup"><span data-stu-id="a0e11-182">x64,</span></span>            |

<span data-ttu-id="a0e11-183">有关 .NET Core 2.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="a0e11-183">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="a0e11-184">Windows 7/Vista/8.1/Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a0e11-184">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="a0e11-185">如果要在以下 Windows 版本上安装 .NET SDK 或运行时，则需要其他依赖项：</span><span class="sxs-lookup"><span data-stu-id="a0e11-185">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="a0e11-186">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="a0e11-186">Windows 7 SP1</span></span>
- <span data-ttu-id="a0e11-187">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="a0e11-187">Windows Vista SP 2</span></span>
- <span data-ttu-id="a0e11-188">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="a0e11-188">Windows 8.1</span></span>
- <span data-ttu-id="a0e11-189">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a0e11-189">Windows Server 2008 R2</span></span>
- <span data-ttu-id="a0e11-190">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a0e11-190">Windows Server 2012 R2</span></span>

<span data-ttu-id="a0e11-191">安装以下组件：</span><span class="sxs-lookup"><span data-stu-id="a0e11-191">Install the following:</span></span>

- <span data-ttu-id="a0e11-192">[Microsoft Visual C++ 2015 Redistributable 更新 3](https://www.microsoft.com/download/details.aspx?id=52685)。</span><span class="sxs-lookup"><span data-stu-id="a0e11-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="a0e11-193">KB2533623</span><span class="sxs-lookup"><span data-stu-id="a0e11-193">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="a0e11-194">如果遇到一个以下错误，也需要满足上述要求：</span><span class="sxs-lookup"><span data-stu-id="a0e11-194">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="a0e11-195">此程序无法启动，因为计算机上缺少 api-ms-win-crt-runtime-l1-1-0.dll  。</span><span class="sxs-lookup"><span data-stu-id="a0e11-195">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="a0e11-196">尝试重新安装该程序以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="a0e11-196">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="a0e11-197">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="a0e11-197">\- or -</span></span>
>
> <span data-ttu-id="a0e11-198">已找到库 hostfxr.dll  ，但未能将其从 C:\\\<path_to_app>\\hostfxr.dll 中加载  。</span><span class="sxs-lookup"><span data-stu-id="a0e11-198">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="a0e11-199">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a0e11-199">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="a0e11-200">.NET Core 3.1 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="a0e11-200">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="a0e11-201">对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。</span><span class="sxs-lookup"><span data-stu-id="a0e11-201">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="a0e11-202">以下 Linux 发行版/版本支持 .NET Core 3.1：</span><span class="sxs-lookup"><span data-stu-id="a0e11-202">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="a0e11-203">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="a0e11-203">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a0e11-204">(OS)</span><span class="sxs-lookup"><span data-stu-id="a0e11-204">OS</span></span>                             | <span data-ttu-id="a0e11-205">Version</span><span class="sxs-lookup"><span data-stu-id="a0e11-205">Version</span></span>               | <span data-ttu-id="a0e11-206">体系结构</span><span class="sxs-lookup"><span data-stu-id="a0e11-206">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="a0e11-207">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="a0e11-207">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="a0e11-208">6、7、8</span><span class="sxs-lookup"><span data-stu-id="a0e11-208">6, 7, 8</span></span>               | <span data-ttu-id="a0e11-209">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-209">x64</span></span> |
| <span data-ttu-id="a0e11-210">CentOS</span><span class="sxs-lookup"><span data-stu-id="a0e11-210">CentOS</span></span>                         | <span data-ttu-id="a0e11-211">7+</span><span class="sxs-lookup"><span data-stu-id="a0e11-211">7+</span></span>                    | <span data-ttu-id="a0e11-212">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-212">x64</span></span> |
| <span data-ttu-id="a0e11-213">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="a0e11-213">Oracle Linux</span></span>                   | <span data-ttu-id="a0e11-214">7+</span><span class="sxs-lookup"><span data-stu-id="a0e11-214">7+</span></span>                    | <span data-ttu-id="a0e11-215">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-215">x64</span></span> |
| <span data-ttu-id="a0e11-216">Fedora</span><span class="sxs-lookup"><span data-stu-id="a0e11-216">Fedora</span></span>                         | <span data-ttu-id="a0e11-217">30+</span><span class="sxs-lookup"><span data-stu-id="a0e11-217">30+</span></span>                   | <span data-ttu-id="a0e11-218">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-218">x64</span></span> |
| <span data-ttu-id="a0e11-219">Debian</span><span class="sxs-lookup"><span data-stu-id="a0e11-219">Debian</span></span>                         | <span data-ttu-id="a0e11-220">9+</span><span class="sxs-lookup"><span data-stu-id="a0e11-220">9+</span></span>                    | <span data-ttu-id="a0e11-221">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="a0e11-221">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="a0e11-222">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a0e11-222">Ubuntu</span></span>                         | <span data-ttu-id="a0e11-223">16.04+</span><span class="sxs-lookup"><span data-stu-id="a0e11-223">16.04+</span></span>                | <span data-ttu-id="a0e11-224">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="a0e11-224">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="a0e11-225">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="a0e11-225">Linux Mint</span></span>                     | <span data-ttu-id="a0e11-226">18+</span><span class="sxs-lookup"><span data-stu-id="a0e11-226">18+</span></span>                   | <span data-ttu-id="a0e11-227">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-227">x64</span></span> |
| <span data-ttu-id="a0e11-228">openSUSE</span><span class="sxs-lookup"><span data-stu-id="a0e11-228">openSUSE</span></span>                       | <span data-ttu-id="a0e11-229">15+</span><span class="sxs-lookup"><span data-stu-id="a0e11-229">15+</span></span>                   | <span data-ttu-id="a0e11-230">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-230">x64</span></span> |
| <span data-ttu-id="a0e11-231">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="a0e11-231">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="a0e11-232">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="a0e11-232">12 SP2+</span></span>               | <span data-ttu-id="a0e11-233">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-233">x64</span></span> |
| <span data-ttu-id="a0e11-234">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="a0e11-234">Alpine Linux</span></span>                   | <span data-ttu-id="a0e11-235">3.10+</span><span class="sxs-lookup"><span data-stu-id="a0e11-235">3.10+</span></span>                 | <span data-ttu-id="a0e11-236">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="a0e11-236">x64, ARM64</span></span> |

<span data-ttu-id="a0e11-237">有关 .NET Core 3.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="a0e11-237">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="a0e11-238">有关如何在 ARM64（内核 4.14+）上安装 .NET Core 3.1 的详细信息，请参阅[在 Linux ARM64 上安装 .NET Core 3.0](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)。</span><span class="sxs-lookup"><span data-stu-id="a0e11-238">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0e11-239">ARM64 支持需要 Linux 内核 4.14 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a0e11-239">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="a0e11-240">某些 linux 发行版满足此要求，而另一些则不满足。</span><span class="sxs-lookup"><span data-stu-id="a0e11-240">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="a0e11-241">例如，支持 Ubuntu 18.04，但不支持 Ubuntu 16.04。</span><span class="sxs-lookup"><span data-stu-id="a0e11-241">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="a0e11-242">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a0e11-242">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="a0e11-243">目前不支持 .NET Core 3.0。  有关详细信息，请参阅 [.NET Core 支持策略](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)。</span><span class="sxs-lookup"><span data-stu-id="a0e11-243">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="a0e11-244">.NET Core 3.0 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="a0e11-244">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="a0e11-245">对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。</span><span class="sxs-lookup"><span data-stu-id="a0e11-245">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="a0e11-246">以下 Linux 发行版本/版本支持 .NET Core 3.0：</span><span class="sxs-lookup"><span data-stu-id="a0e11-246">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="a0e11-247">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="a0e11-247">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a0e11-248">(OS)</span><span class="sxs-lookup"><span data-stu-id="a0e11-248">OS</span></span>                             | <span data-ttu-id="a0e11-249">Version</span><span class="sxs-lookup"><span data-stu-id="a0e11-249">Version</span></span>               | <span data-ttu-id="a0e11-250">体系结构</span><span class="sxs-lookup"><span data-stu-id="a0e11-250">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="a0e11-251">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="a0e11-251">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="a0e11-252">6、7、8</span><span class="sxs-lookup"><span data-stu-id="a0e11-252">6, 7, 8</span></span>               | <span data-ttu-id="a0e11-253">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-253">x64</span></span> |
| <span data-ttu-id="a0e11-254">CentOS</span><span class="sxs-lookup"><span data-stu-id="a0e11-254">CentOS</span></span>                         | <span data-ttu-id="a0e11-255">7+</span><span class="sxs-lookup"><span data-stu-id="a0e11-255">7+</span></span>                    | <span data-ttu-id="a0e11-256">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-256">x64</span></span> |
| <span data-ttu-id="a0e11-257">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="a0e11-257">Oracle Linux</span></span>                   | <span data-ttu-id="a0e11-258">7+</span><span class="sxs-lookup"><span data-stu-id="a0e11-258">7+</span></span>                    | <span data-ttu-id="a0e11-259">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-259">x64</span></span> |
| <span data-ttu-id="a0e11-260">Fedora</span><span class="sxs-lookup"><span data-stu-id="a0e11-260">Fedora</span></span>                         | <span data-ttu-id="a0e11-261">29+</span><span class="sxs-lookup"><span data-stu-id="a0e11-261">29+</span></span>                   | <span data-ttu-id="a0e11-262">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-262">x64</span></span> |
| <span data-ttu-id="a0e11-263">Debian</span><span class="sxs-lookup"><span data-stu-id="a0e11-263">Debian</span></span>                         | <span data-ttu-id="a0e11-264">9+</span><span class="sxs-lookup"><span data-stu-id="a0e11-264">9+</span></span>                    | <span data-ttu-id="a0e11-265">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="a0e11-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="a0e11-266">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a0e11-266">Ubuntu</span></span>                         | <span data-ttu-id="a0e11-267">16.04+</span><span class="sxs-lookup"><span data-stu-id="a0e11-267">16.04+</span></span>                | <span data-ttu-id="a0e11-268">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="a0e11-268">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="a0e11-269">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="a0e11-269">Linux Mint</span></span>                     | <span data-ttu-id="a0e11-270">18+</span><span class="sxs-lookup"><span data-stu-id="a0e11-270">18+</span></span>                   | <span data-ttu-id="a0e11-271">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-271">x64</span></span> |
| <span data-ttu-id="a0e11-272">openSUSE</span><span class="sxs-lookup"><span data-stu-id="a0e11-272">openSUSE</span></span>                       | <span data-ttu-id="a0e11-273">15+</span><span class="sxs-lookup"><span data-stu-id="a0e11-273">15+</span></span>                   | <span data-ttu-id="a0e11-274">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-274">x64</span></span> |
| <span data-ttu-id="a0e11-275">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="a0e11-275">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="a0e11-276">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="a0e11-276">12 SP2+</span></span>               | <span data-ttu-id="a0e11-277">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-277">x64</span></span> |
| <span data-ttu-id="a0e11-278">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="a0e11-278">Alpine Linux</span></span>                   | <span data-ttu-id="a0e11-279">3.8+</span><span class="sxs-lookup"><span data-stu-id="a0e11-279">3.8+</span></span>                  | <span data-ttu-id="a0e11-280">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="a0e11-280">x64, ARM64</span></span> |

<span data-ttu-id="a0e11-281">有关 .NET Core 3.0 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.0 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="a0e11-281">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="a0e11-282">有关如何在 ARM64 上安装 .NET Core 3.0 的详细信息，请参阅[在 Linux ARM64 上安装 .NET Core 3.0](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)。</span><span class="sxs-lookup"><span data-stu-id="a0e11-282">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="a0e11-283">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="a0e11-283">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="a0e11-284">目前不支持 .NET Core 2.2。  有关详细信息，请参阅 [.NET Core 支持策略](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)。</span><span class="sxs-lookup"><span data-stu-id="a0e11-284">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="a0e11-285">.NET Core 2.2 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="a0e11-285">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="a0e11-286">对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。</span><span class="sxs-lookup"><span data-stu-id="a0e11-286">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="a0e11-287">以下 Linux 发行版本/版本支持 .NET Core 2.2：</span><span class="sxs-lookup"><span data-stu-id="a0e11-287">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="a0e11-288">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="a0e11-288">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a0e11-289">(OS)</span><span class="sxs-lookup"><span data-stu-id="a0e11-289">OS</span></span>                             |  <span data-ttu-id="a0e11-290">Version</span><span class="sxs-lookup"><span data-stu-id="a0e11-290">Version</span></span>                |  <span data-ttu-id="a0e11-291">体系结构</span><span class="sxs-lookup"><span data-stu-id="a0e11-291">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="a0e11-292">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="a0e11-292">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="a0e11-293">6、7</span><span class="sxs-lookup"><span data-stu-id="a0e11-293">6, 7</span></span>                   | <span data-ttu-id="a0e11-294">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-294">x64</span></span> |
| <span data-ttu-id="a0e11-295">CentOS</span><span class="sxs-lookup"><span data-stu-id="a0e11-295">CentOS</span></span>                         |  <span data-ttu-id="a0e11-296">7</span><span class="sxs-lookup"><span data-stu-id="a0e11-296">7</span></span>                      | <span data-ttu-id="a0e11-297">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-297">x64</span></span> |
| <span data-ttu-id="a0e11-298">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="a0e11-298">Oracle Linux</span></span>                   |  <span data-ttu-id="a0e11-299">7</span><span class="sxs-lookup"><span data-stu-id="a0e11-299">7</span></span>                      | <span data-ttu-id="a0e11-300">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-300">x64</span></span> |
| <span data-ttu-id="a0e11-301">Fedora</span><span class="sxs-lookup"><span data-stu-id="a0e11-301">Fedora</span></span>                         |  <span data-ttu-id="a0e11-302">29、30</span><span class="sxs-lookup"><span data-stu-id="a0e11-302">29, 30</span></span>                 | <span data-ttu-id="a0e11-303">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-303">x64</span></span> |
| <span data-ttu-id="a0e11-304">Debian</span><span class="sxs-lookup"><span data-stu-id="a0e11-304">Debian</span></span>                         |  <span data-ttu-id="a0e11-305">9</span><span class="sxs-lookup"><span data-stu-id="a0e11-305">9</span></span>                      | <span data-ttu-id="a0e11-306">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="a0e11-306">x64, ARM32</span></span> |
| <span data-ttu-id="a0e11-307">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a0e11-307">Ubuntu</span></span>                         |  <span data-ttu-id="a0e11-308">16.04、18.04、18.10</span><span class="sxs-lookup"><span data-stu-id="a0e11-308">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="a0e11-309">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="a0e11-309">x64, ARM32</span></span> |
| <span data-ttu-id="a0e11-310">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="a0e11-310">Linux Mint</span></span>                     |  <span data-ttu-id="a0e11-311">17、18</span><span class="sxs-lookup"><span data-stu-id="a0e11-311">17, 18</span></span>                 | <span data-ttu-id="a0e11-312">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-312">x64</span></span> |
| <span data-ttu-id="a0e11-313">openSUSE</span><span class="sxs-lookup"><span data-stu-id="a0e11-313">openSUSE</span></span>                       |  <span data-ttu-id="a0e11-314">15+</span><span class="sxs-lookup"><span data-stu-id="a0e11-314">15+</span></span>                    | <span data-ttu-id="a0e11-315">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-315">x64</span></span> |
| <span data-ttu-id="a0e11-316">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="a0e11-316">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="a0e11-317">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="a0e11-317">12 SP2+</span></span>                | <span data-ttu-id="a0e11-318">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-318">x64</span></span> |
| <span data-ttu-id="a0e11-319">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="a0e11-319">Alpine Linux</span></span>                   |  <span data-ttu-id="a0e11-320">3.8+</span><span class="sxs-lookup"><span data-stu-id="a0e11-320">3.8+</span></span>                   | <span data-ttu-id="a0e11-321">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-321">x64</span></span> |

<span data-ttu-id="a0e11-322">有关 .NET Core 2.2 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.2 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="a0e11-322">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="a0e11-323">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a0e11-323">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="a0e11-324">.NET Core 2.1 将 Linux 视为一个操作系统。</span><span class="sxs-lookup"><span data-stu-id="a0e11-324">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="a0e11-325">对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。</span><span class="sxs-lookup"><span data-stu-id="a0e11-325">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="a0e11-326">以下 Linux 发行版本/版本支持 .NET Core 2.1：</span><span class="sxs-lookup"><span data-stu-id="a0e11-326">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="a0e11-327">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="a0e11-327">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a0e11-328">(OS)</span><span class="sxs-lookup"><span data-stu-id="a0e11-328">OS</span></span>                             |  <span data-ttu-id="a0e11-329">Version</span><span class="sxs-lookup"><span data-stu-id="a0e11-329">Version</span></span>                |  <span data-ttu-id="a0e11-330">体系结构</span><span class="sxs-lookup"><span data-stu-id="a0e11-330">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="a0e11-331">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="a0e11-331">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="a0e11-332">6、7、8</span><span class="sxs-lookup"><span data-stu-id="a0e11-332">6, 7, 8</span></span>                | <span data-ttu-id="a0e11-333">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-333">x64</span></span> |
| <span data-ttu-id="a0e11-334">CentOS</span><span class="sxs-lookup"><span data-stu-id="a0e11-334">CentOS</span></span>                         |  <span data-ttu-id="a0e11-335">7+</span><span class="sxs-lookup"><span data-stu-id="a0e11-335">7+</span></span>                     | <span data-ttu-id="a0e11-336">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-336">x64</span></span> |
| <span data-ttu-id="a0e11-337">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="a0e11-337">Oracle Linux</span></span>                   |  <span data-ttu-id="a0e11-338">7+</span><span class="sxs-lookup"><span data-stu-id="a0e11-338">7+</span></span>                     | <span data-ttu-id="a0e11-339">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-339">x64</span></span> |
| <span data-ttu-id="a0e11-340">Fedora</span><span class="sxs-lookup"><span data-stu-id="a0e11-340">Fedora</span></span>                         |  <span data-ttu-id="a0e11-341">30+</span><span class="sxs-lookup"><span data-stu-id="a0e11-341">30+</span></span>                    | <span data-ttu-id="a0e11-342">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-342">x64</span></span> |
| <span data-ttu-id="a0e11-343">Debian</span><span class="sxs-lookup"><span data-stu-id="a0e11-343">Debian</span></span>                         |  <span data-ttu-id="a0e11-344">9</span><span class="sxs-lookup"><span data-stu-id="a0e11-344">9</span></span>                      | <span data-ttu-id="a0e11-345">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="a0e11-345">x64, ARM32</span></span> |
| <span data-ttu-id="a0e11-346">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a0e11-346">Ubuntu</span></span>                         |  <span data-ttu-id="a0e11-347">16.04、18.04、19.04、19.10</span><span class="sxs-lookup"><span data-stu-id="a0e11-347">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="a0e11-348">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="a0e11-348">x64, ARM32</span></span> |
| <span data-ttu-id="a0e11-349">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="a0e11-349">Linux Mint</span></span>                     |  <span data-ttu-id="a0e11-350">17+</span><span class="sxs-lookup"><span data-stu-id="a0e11-350">17+</span></span>                    | <span data-ttu-id="a0e11-351">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-351">x64</span></span> |
| <span data-ttu-id="a0e11-352">openSUSE</span><span class="sxs-lookup"><span data-stu-id="a0e11-352">openSUSE</span></span>                       |  <span data-ttu-id="a0e11-353">15+</span><span class="sxs-lookup"><span data-stu-id="a0e11-353">15+</span></span>                    | <span data-ttu-id="a0e11-354">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-354">x64</span></span> |
| <span data-ttu-id="a0e11-355">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="a0e11-355">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="a0e11-356">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="a0e11-356">12 SP2+</span></span>                | <span data-ttu-id="a0e11-357">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-357">x64</span></span> |
| <span data-ttu-id="a0e11-358">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="a0e11-358">Alpine Linux</span></span>                   |  <span data-ttu-id="a0e11-359">3.8+</span><span class="sxs-lookup"><span data-stu-id="a0e11-359">3.8+</span></span>                   | <span data-ttu-id="a0e11-360">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-360">x64</span></span> |

<span data-ttu-id="a0e11-361">有关 .NET Core 2.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="a0e11-361">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="a0e11-362">Linux 发行版本依赖项</span><span class="sxs-lookup"><span data-stu-id="a0e11-362">Linux distribution dependencies</span></span>

<span data-ttu-id="a0e11-363">根据 Linux 发行版，你可能需要安装其他依赖项。</span><span class="sxs-lookup"><span data-stu-id="a0e11-363">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0e11-364">确切的版本和名称可能因所选 Linux 发行版本略有不同。</span><span class="sxs-lookup"><span data-stu-id="a0e11-364">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="a0e11-365">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a0e11-365">Ubuntu</span></span>

<span data-ttu-id="a0e11-366">Ubuntu 发行版需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="a0e11-366">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="a0e11-367">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="a0e11-367">liblttng-ust0</span></span>
- <span data-ttu-id="a0e11-368">libcurl3（针对 14.x 和 16.x）</span><span class="sxs-lookup"><span data-stu-id="a0e11-368">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="a0e11-369">libcurl4（针对 18.x）</span><span class="sxs-lookup"><span data-stu-id="a0e11-369">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="a0e11-370">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="a0e11-370">libssl1.0.0</span></span>
- <span data-ttu-id="a0e11-371">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="a0e11-371">libkrb5-3</span></span>
- <span data-ttu-id="a0e11-372">zlib1g</span><span class="sxs-lookup"><span data-stu-id="a0e11-372">zlib1g</span></span>
- <span data-ttu-id="a0e11-373">libicu52（针对 14.x）</span><span class="sxs-lookup"><span data-stu-id="a0e11-373">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="a0e11-374">libicu55（针对 16.x）</span><span class="sxs-lookup"><span data-stu-id="a0e11-374">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="a0e11-375">libicu57（针对 17.x）</span><span class="sxs-lookup"><span data-stu-id="a0e11-375">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="a0e11-376">libicu60（针对 18.x）</span><span class="sxs-lookup"><span data-stu-id="a0e11-376">libicu60 (for 18.x)</span></span>

<span data-ttu-id="a0e11-377">对于使用 System.Drawing.Common  程序集的 .NET Core 应用，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="a0e11-377">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="a0e11-378">libgdiplus（版本 6.0.1 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="a0e11-378">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="a0e11-379">大多数 Ubuntu 版本都包含 libgdiplus 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="a0e11-379">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="a0e11-380">可以通过将 Mono 存储库添加到系统来安装最新版 libgdiplus。</span><span class="sxs-lookup"><span data-stu-id="a0e11-380">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="a0e11-381">有关详细信息，请参阅 <https://www.mono-project.com/download/stable/>。</span><span class="sxs-lookup"><span data-stu-id="a0e11-381">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="a0e11-382">CentOS 和 Fedora</span><span class="sxs-lookup"><span data-stu-id="a0e11-382">CentOS and Fedora</span></span>

<span data-ttu-id="a0e11-383">CentOS 发行版本需要安装以下库：</span><span class="sxs-lookup"><span data-stu-id="a0e11-383">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="a0e11-384">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="a0e11-384">lttng-ust</span></span>
- <span data-ttu-id="a0e11-385">libcurl</span><span class="sxs-lookup"><span data-stu-id="a0e11-385">libcurl</span></span>
- <span data-ttu-id="a0e11-386">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="a0e11-386">openssl-libs</span></span>
- <span data-ttu-id="a0e11-387">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="a0e11-387">krb5-libs</span></span>
- <span data-ttu-id="a0e11-388">libicu</span><span class="sxs-lookup"><span data-stu-id="a0e11-388">libicu</span></span>
- <span data-ttu-id="a0e11-389">zlib</span><span class="sxs-lookup"><span data-stu-id="a0e11-389">zlib</span></span>

<span data-ttu-id="a0e11-390">Fedora 用户：如果 OpenSSL 的版本为 1.1 及更高版本，则需要安装 compat-openssl10  。</span><span class="sxs-lookup"><span data-stu-id="a0e11-390">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="a0e11-391">对于 .NET Core 2.0，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="a0e11-391">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="a0e11-392">libunwind</span><span class="sxs-lookup"><span data-stu-id="a0e11-392">libunwind</span></span>
- <span data-ttu-id="a0e11-393">libuuid</span><span class="sxs-lookup"><span data-stu-id="a0e11-393">libuuid</span></span>

<span data-ttu-id="a0e11-394">有关依赖项的详细信息，请参阅[独立式 Linux 应用](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="a0e11-394">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="a0e11-395">对于使用 System.Drawing.Common  程序集的 .NET Core 应用，还需要以下依赖项：</span><span class="sxs-lookup"><span data-stu-id="a0e11-395">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="a0e11-396">libgdiplus（版本 6.0.1 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="a0e11-396">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="a0e11-397">CentOS 和 Fedora 的大多数版本都包含 libgdiplus 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="a0e11-397">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="a0e11-398">可以通过将 Mono 存储库添加到系统来安装最新版 libgdiplus。</span><span class="sxs-lookup"><span data-stu-id="a0e11-398">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="a0e11-399">有关详细信息，请参阅 <https://www.mono-project.com/download/stable/>。</span><span class="sxs-lookup"><span data-stu-id="a0e11-399">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="a0e11-400">以下 macOS 版本支持 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="a0e11-400">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="a0e11-401">`+` 表示最低版本。</span><span class="sxs-lookup"><span data-stu-id="a0e11-401">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a0e11-402">.NET Core 版本</span><span class="sxs-lookup"><span data-stu-id="a0e11-402">.NET Core Version</span></span> | <span data-ttu-id="a0e11-403">macOS</span><span class="sxs-lookup"><span data-stu-id="a0e11-403">macOS</span></span>                 | <span data-ttu-id="a0e11-404">体系结构</span><span class="sxs-lookup"><span data-stu-id="a0e11-404">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="a0e11-405">3.1</span><span class="sxs-lookup"><span data-stu-id="a0e11-405">3.1</span></span>               | <span data-ttu-id="a0e11-406">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="a0e11-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="a0e11-407">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-407">x64</span></span> | [<span data-ttu-id="a0e11-408">详细信息</span><span class="sxs-lookup"><span data-stu-id="a0e11-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="a0e11-409">3.0</span><span class="sxs-lookup"><span data-stu-id="a0e11-409">3.0</span></span>               | <span data-ttu-id="a0e11-410">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="a0e11-410">High Sierra (10.13+)</span></span>  | <span data-ttu-id="a0e11-411">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-411">x64</span></span> | [<span data-ttu-id="a0e11-412">详细信息</span><span class="sxs-lookup"><span data-stu-id="a0e11-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="a0e11-413">2.2</span><span class="sxs-lookup"><span data-stu-id="a0e11-413">2.2</span></span>               | <span data-ttu-id="a0e11-414">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="a0e11-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="a0e11-415">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-415">x64</span></span> | [<span data-ttu-id="a0e11-416">详细信息</span><span class="sxs-lookup"><span data-stu-id="a0e11-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="a0e11-417">2.1</span><span class="sxs-lookup"><span data-stu-id="a0e11-417">2.1</span></span>               | <span data-ttu-id="a0e11-418">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="a0e11-418">Sierra (10.12+)</span></span>       | <span data-ttu-id="a0e11-419">X64</span><span class="sxs-lookup"><span data-stu-id="a0e11-419">x64</span></span> | [<span data-ttu-id="a0e11-420">详细信息</span><span class="sxs-lookup"><span data-stu-id="a0e11-420">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="a0e11-421">自 macOS Catalina（版本10.15）开始，所有在 2019 年 6 月 1 日之后生成并使用开发者 ID 扩散的软件都必须经过公证。</span><span class="sxs-lookup"><span data-stu-id="a0e11-421">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="a0e11-422">此要求应用于 .NET Core 运行时、.NET Core SDK 以及使用 .NET Core 创建的软件。</span><span class="sxs-lookup"><span data-stu-id="a0e11-422">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="a0e11-423">自 2020 年 2 月 18 日起，.NET Core（运行时和 SDK）版本 3.1、3.0 和 2.1 的安装程序都已经过公证。</span><span class="sxs-lookup"><span data-stu-id="a0e11-423">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="a0e11-424">以前发布的版本没有经过公证。</span><span class="sxs-lookup"><span data-stu-id="a0e11-424">Prior released versions aren't notarized.</span></span> <span data-ttu-id="a0e11-425">如果运行未经过公证的应用，将看到类似于下图的错误：</span><span class="sxs-lookup"><span data-stu-id="a0e11-425">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![macOS Catalina 公证警报](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="a0e11-427">若要详细了解强制执行的公证要求对 .NET Core 和 .NET Core 应用的影响，请参阅[处理 macOS Catalina 公证](macos-notarization-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="a0e11-427">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="a0e11-428">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="a0e11-428">libgdiplus</span></span>

<span data-ttu-id="a0e11-429">使用 System.Drawing.Common  程序集的 .NET Core 应用程序要求安装 libgdiplus。</span><span class="sxs-lookup"><span data-stu-id="a0e11-429">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="a0e11-430">获取 libgdiplus 的一个简单方法是使用适用于 macOS 的 [Homebrew (“brew”)](https://brew.sh/) 包。</span><span class="sxs-lookup"><span data-stu-id="a0e11-430">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="a0e11-431">在安装 brew 后，通过在终端（命令）提示符处执行以下命令来安装 libgdiplus  ：</span><span class="sxs-lookup"><span data-stu-id="a0e11-431">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="a0e11-432">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a0e11-432">Next steps</span></span>

- <span data-ttu-id="a0e11-433">若要开发并运行应用，请安装 [.NET Core SDK](sdk.md)（包括运行时）。</span><span class="sxs-lookup"><span data-stu-id="a0e11-433">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="a0e11-434">若要运行其他人创建的应用，请安装 [.NET Core 运行时](runtime.md)。</span><span class="sxs-lookup"><span data-stu-id="a0e11-434">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
