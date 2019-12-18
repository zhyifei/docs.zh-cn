---
title: 调试分析配置设置
description: 了解为 .NET Core 应用配置调试和分析的运行时设置。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: c57cfa7233f48def890ded3c9d589b7f268147df
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998857"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a><span data-ttu-id="a5103-103">用于调试和分析的运行时配置选项</span><span class="sxs-lookup"><span data-stu-id="a5103-103">Run-time configuration options for debugging and profiling</span></span>

## <a name="enable-diagnostics"></a><span data-ttu-id="a5103-104">启用诊断</span><span class="sxs-lookup"><span data-stu-id="a5103-104">Enable diagnostics</span></span>

- <span data-ttu-id="a5103-105">配置是启用还是禁用调试器、探查器和 EventPipe 诊断。</span><span class="sxs-lookup"><span data-stu-id="a5103-105">Configures whether the debugger, the profiler, and EventPipe diagnostics are enabled or disabled.</span></span>
- <span data-ttu-id="a5103-106">默认：启用 (`1`)。</span><span class="sxs-lookup"><span data-stu-id="a5103-106">Default: Enabled (`1`).</span></span>

| | <span data-ttu-id="a5103-107">设置名</span><span class="sxs-lookup"><span data-stu-id="a5103-107">Setting name</span></span> | <span data-ttu-id="a5103-108">值</span><span class="sxs-lookup"><span data-stu-id="a5103-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a5103-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a5103-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="a5103-110">不可用</span><span class="sxs-lookup"><span data-stu-id="a5103-110">N/A</span></span> | <span data-ttu-id="a5103-111">不可用</span><span class="sxs-lookup"><span data-stu-id="a5103-111">N/A</span></span> |
| <span data-ttu-id="a5103-112">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="a5103-112">**Environment variable**</span></span> | `COMPlus_EnableDiagnostics` | <span data-ttu-id="a5103-113">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="a5103-113">`1` - enabled</span></span><br/><span data-ttu-id="a5103-114">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="a5103-114">`0` - disabled</span></span> |

## <a name="enable-profiling"></a><span data-ttu-id="a5103-115">启用分析</span><span class="sxs-lookup"><span data-stu-id="a5103-115">Enable profiling</span></span>

- <span data-ttu-id="a5103-116">配置是否为当前正在运行的进程启用分析。</span><span class="sxs-lookup"><span data-stu-id="a5103-116">Configures whether profiling is enabled for the currently running process.</span></span>
- <span data-ttu-id="a5103-117">默认：禁用 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="a5103-117">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="a5103-118">设置名</span><span class="sxs-lookup"><span data-stu-id="a5103-118">Setting name</span></span> | <span data-ttu-id="a5103-119">值</span><span class="sxs-lookup"><span data-stu-id="a5103-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a5103-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a5103-120">**runtimeconfig.json**</span></span> | <span data-ttu-id="a5103-121">不可用</span><span class="sxs-lookup"><span data-stu-id="a5103-121">N/A</span></span> | <span data-ttu-id="a5103-122">不可用</span><span class="sxs-lookup"><span data-stu-id="a5103-122">N/A</span></span> |
| <span data-ttu-id="a5103-123">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="a5103-123">**Environment variable**</span></span> | `CORECLR_ENABLE_PROFILING` | <span data-ttu-id="a5103-124">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="a5103-124">`0` - disabled</span></span><br/><span data-ttu-id="a5103-125">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="a5103-125">`1` - enabled</span></span> |

## <a name="profiler-guid"></a><span data-ttu-id="a5103-126">探查器 GUID</span><span class="sxs-lookup"><span data-stu-id="a5103-126">Profiler GUID</span></span>

- <span data-ttu-id="a5103-127">指定要加载到当前正在运行的进程中的探查器 GUID。</span><span class="sxs-lookup"><span data-stu-id="a5103-127">Specifies the GUID of the profiler to load into the currently running process.</span></span>

| | <span data-ttu-id="a5103-128">设置名</span><span class="sxs-lookup"><span data-stu-id="a5103-128">Setting name</span></span> | <span data-ttu-id="a5103-129">值</span><span class="sxs-lookup"><span data-stu-id="a5103-129">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a5103-130">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a5103-130">**runtimeconfig.json**</span></span> | <span data-ttu-id="a5103-131">不可用</span><span class="sxs-lookup"><span data-stu-id="a5103-131">N/A</span></span> | <span data-ttu-id="a5103-132">不可用</span><span class="sxs-lookup"><span data-stu-id="a5103-132">N/A</span></span> |
| <span data-ttu-id="a5103-133">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="a5103-133">**Environment variable**</span></span> | `CORECLR_PROFILER` | <span data-ttu-id="a5103-134">string-guid </span><span class="sxs-lookup"><span data-stu-id="a5103-134">*string-guid*</span></span> |

## <a name="profiler-location"></a><span data-ttu-id="a5103-135">探查器位置</span><span class="sxs-lookup"><span data-stu-id="a5103-135">Profiler location</span></span>

- <span data-ttu-id="a5103-136">指定要加载到当前正在运行的进程（或 32 位/64 位进程）的探查器 DLL 路径。</span><span class="sxs-lookup"><span data-stu-id="a5103-136">Specifies the path to the profiler DLL to load into the currently running process (or 32-bit or 64-bit process).</span></span>
- <span data-ttu-id="a5103-137">如果设置了多个变量，则优先使用指定位数的变量。</span><span class="sxs-lookup"><span data-stu-id="a5103-137">If more than one variable is set, the bitness-specific variables take precedence.</span></span> <span data-ttu-id="a5103-138">它们指定要加载的探查器的位数。</span><span class="sxs-lookup"><span data-stu-id="a5103-138">They specify which bitness of profiler to load.</span></span>
- <span data-ttu-id="a5103-139">有关详细信息，请参阅 [Finding the profiler library](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md)（查找探查器库）。</span><span class="sxs-lookup"><span data-stu-id="a5103-139">For more information, see [Finding the profiler library](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span></span>

| | <span data-ttu-id="a5103-140">设置名</span><span class="sxs-lookup"><span data-stu-id="a5103-140">Setting name</span></span> | <span data-ttu-id="a5103-141">值</span><span class="sxs-lookup"><span data-stu-id="a5103-141">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a5103-142">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="a5103-142">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH` | <span data-ttu-id="a5103-143">string-path </span><span class="sxs-lookup"><span data-stu-id="a5103-143">*string-path*</span></span> |
| <span data-ttu-id="a5103-144">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="a5103-144">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_32` | <span data-ttu-id="a5103-145">string-path </span><span class="sxs-lookup"><span data-stu-id="a5103-145">*string-path*</span></span> |
| <span data-ttu-id="a5103-146">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="a5103-146">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_64` | <span data-ttu-id="a5103-147">string-path </span><span class="sxs-lookup"><span data-stu-id="a5103-147">*string-path*</span></span> |

## <a name="write-perf-map"></a><span data-ttu-id="a5103-148">写入 Perf 映射</span><span class="sxs-lookup"><span data-stu-id="a5103-148">Write perf map</span></span>

- <span data-ttu-id="a5103-149">允许或禁止在 Linux 系统上写入 /tmp/perf-$pid.map  。</span><span class="sxs-lookup"><span data-stu-id="a5103-149">Enables or disables writing */tmp/perf-$pid.map* on Linux systems.</span></span>
- <span data-ttu-id="a5103-150">默认：禁用 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="a5103-150">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="a5103-151">设置名</span><span class="sxs-lookup"><span data-stu-id="a5103-151">Setting name</span></span> | <span data-ttu-id="a5103-152">值</span><span class="sxs-lookup"><span data-stu-id="a5103-152">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a5103-153">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a5103-153">**runtimeconfig.json**</span></span> | <span data-ttu-id="a5103-154">不可用</span><span class="sxs-lookup"><span data-stu-id="a5103-154">N/A</span></span> | <span data-ttu-id="a5103-155">不可用</span><span class="sxs-lookup"><span data-stu-id="a5103-155">N/A</span></span> |
| <span data-ttu-id="a5103-156">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="a5103-156">**Environment variable**</span></span> | `COMPlus_PerfMapEnabled` | <span data-ttu-id="a5103-157">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="a5103-157">`0` - disabled</span></span><br/><span data-ttu-id="a5103-158">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="a5103-158">`1` - enabled</span></span> |

## <a name="perf-log-markers"></a><span data-ttu-id="a5103-159">性能日志标记</span><span class="sxs-lookup"><span data-stu-id="a5103-159">Perf log markers</span></span>

- <span data-ttu-id="a5103-160">将 `COMPlus_PerfMapEnabled` 设置为 `1` 时，允许或禁止以性能日志中的标记接受和忽略指定信号。</span><span class="sxs-lookup"><span data-stu-id="a5103-160">When `COMPlus_PerfMapEnabled` is set to `1`, enables or disables the specified signal to be accepted and ignored as a marker in the perf logs.</span></span>
- <span data-ttu-id="a5103-161">默认：禁用 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="a5103-161">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="a5103-162">设置名</span><span class="sxs-lookup"><span data-stu-id="a5103-162">Setting name</span></span> | <span data-ttu-id="a5103-163">值</span><span class="sxs-lookup"><span data-stu-id="a5103-163">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a5103-164">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a5103-164">**runtimeconfig.json**</span></span> | <span data-ttu-id="a5103-165">不可用</span><span class="sxs-lookup"><span data-stu-id="a5103-165">N/A</span></span> | <span data-ttu-id="a5103-166">不可用</span><span class="sxs-lookup"><span data-stu-id="a5103-166">N/A</span></span> |
| <span data-ttu-id="a5103-167">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="a5103-167">**Environment variable**</span></span> | `COMPlus_PerfMapIgnoreSignal` | <span data-ttu-id="a5103-168">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="a5103-168">`0` - disabled</span></span><br/><span data-ttu-id="a5103-169">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="a5103-169">`1` - enabled</span></span> |
