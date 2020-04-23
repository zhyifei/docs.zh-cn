---
title: 垃圾回收器配置设置
description: 了解用于配置垃圾回收器如何为 .NET Core 应用管理内存的运行时设置。
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: dfb641eeda03d1acaa4771bd6253fcb33c4082a6
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607805"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="bd227-103">用于垃圾回收的运行时配置选项</span><span class="sxs-lookup"><span data-stu-id="bd227-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="bd227-104">此页包含有关可在运行时更改的垃圾回收器 (GC) 设置的信息。</span><span class="sxs-lookup"><span data-stu-id="bd227-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="bd227-105">如果你要尝试让正在运行的应用达到最佳性能，请考虑使用这些设置。</span><span class="sxs-lookup"><span data-stu-id="bd227-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="bd227-106">然而，在特定情况下，默认值为大多数应用程序提供最佳性能。</span><span class="sxs-lookup"><span data-stu-id="bd227-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="bd227-107">设置在此页上被排入组中。</span><span class="sxs-lookup"><span data-stu-id="bd227-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="bd227-108">每个组内的设置通常彼此结合使用以实现特定的结果。</span><span class="sxs-lookup"><span data-stu-id="bd227-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="bd227-109">这些设置也可以在应用运行时由应用动态地进行更改，因此，你设置的任何运行时设置都可能会被覆盖。</span><span class="sxs-lookup"><span data-stu-id="bd227-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="bd227-110">某些设置（如[延迟级别](../../standard/garbage-collection/latency.md)）通常仅在设计时通过 API 进行设置。</span><span class="sxs-lookup"><span data-stu-id="bd227-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="bd227-111">此页面省略了此类设置。</span><span class="sxs-lookup"><span data-stu-id="bd227-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="bd227-112">对于数值，请对 runtimeconfig.json  文件中的设置使用十进制表示法，而对环境变量设置使用十六进制表示法。</span><span class="sxs-lookup"><span data-stu-id="bd227-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="bd227-113">对于十六进制值，可以使用或不使用“0x”前缀来指定它们。</span><span class="sxs-lookup"><span data-stu-id="bd227-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="bd227-114">垃圾回收的风格</span><span class="sxs-lookup"><span data-stu-id="bd227-114">Flavors of garbage collection</span></span>

<span data-ttu-id="bd227-115">垃圾回收的两种主要风格是工作站 GC 和服务器 GC。</span><span class="sxs-lookup"><span data-stu-id="bd227-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="bd227-116">有关两者之间的差异的详细信息，请参阅[垃圾回收的基础知识](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection)。</span><span class="sxs-lookup"><span data-stu-id="bd227-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="bd227-117">垃圾回收的次要风格是后台垃圾回收和非并发垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="bd227-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="bd227-118">使用以下设置，选择垃圾回收的风格：</span><span class="sxs-lookup"><span data-stu-id="bd227-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="bd227-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="bd227-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="bd227-120">配置应用程序是使用工作站垃圾回收还是服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="bd227-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="bd227-121">默认：工作站垃圾回收 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="bd227-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="bd227-122">设置名</span><span class="sxs-lookup"><span data-stu-id="bd227-122">Setting name</span></span> | <span data-ttu-id="bd227-123">值</span><span class="sxs-lookup"><span data-stu-id="bd227-123">Values</span></span> | <span data-ttu-id="bd227-124">引入的版本</span><span class="sxs-lookup"><span data-stu-id="bd227-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bd227-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bd227-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="bd227-126">`false` - 工作站</span><span class="sxs-lookup"><span data-stu-id="bd227-126">`false` - workstation</span></span><br/><span data-ttu-id="bd227-127">`true` - 服务器</span><span class="sxs-lookup"><span data-stu-id="bd227-127">`true` - server</span></span> | <span data-ttu-id="bd227-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bd227-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="bd227-129">MSBuild 属性 </span><span class="sxs-lookup"><span data-stu-id="bd227-129">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="bd227-130">`false` - 工作站</span><span class="sxs-lookup"><span data-stu-id="bd227-130">`false` - workstation</span></span><br/><span data-ttu-id="bd227-131">`true` - 服务器</span><span class="sxs-lookup"><span data-stu-id="bd227-131">`true` - server</span></span> | <span data-ttu-id="bd227-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bd227-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="bd227-133">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="bd227-133">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="bd227-134">`0` - 工作站</span><span class="sxs-lookup"><span data-stu-id="bd227-134">`0` - workstation</span></span><br/><span data-ttu-id="bd227-135">`1` - 服务器</span><span class="sxs-lookup"><span data-stu-id="bd227-135">`1` - server</span></span> | <span data-ttu-id="bd227-136">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bd227-136">.NET Core 1.0</span></span> |
| <span data-ttu-id="bd227-137">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="bd227-137">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bd227-138">GCServer</span><span class="sxs-lookup"><span data-stu-id="bd227-138">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="bd227-139">`false` - 工作站</span><span class="sxs-lookup"><span data-stu-id="bd227-139">`false` - workstation</span></span><br/><span data-ttu-id="bd227-140">`true` - 服务器</span><span class="sxs-lookup"><span data-stu-id="bd227-140">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="bd227-141">示例</span><span class="sxs-lookup"><span data-stu-id="bd227-141">Examples</span></span>

<span data-ttu-id="bd227-142">runtimeconfig.json 文件： </span><span class="sxs-lookup"><span data-stu-id="bd227-142">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="bd227-143">项目文件：</span><span class="sxs-lookup"><span data-stu-id="bd227-143">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="bd227-144">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="bd227-144">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="bd227-145">配置是否启用后台（并发）垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="bd227-145">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="bd227-146">默认：启用 (`true`)。</span><span class="sxs-lookup"><span data-stu-id="bd227-146">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="bd227-147">有关详细信息，请参阅[后台垃圾回收](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection)和[后台服务器垃圾回收](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection)。</span><span class="sxs-lookup"><span data-stu-id="bd227-147">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="bd227-148">设置名</span><span class="sxs-lookup"><span data-stu-id="bd227-148">Setting name</span></span> | <span data-ttu-id="bd227-149">值</span><span class="sxs-lookup"><span data-stu-id="bd227-149">Values</span></span> | <span data-ttu-id="bd227-150">引入的版本</span><span class="sxs-lookup"><span data-stu-id="bd227-150">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bd227-151">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bd227-151">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="bd227-152">`true` - 后台 GC</span><span class="sxs-lookup"><span data-stu-id="bd227-152">`true` - background GC</span></span><br/><span data-ttu-id="bd227-153">`false` - 非并发 GC</span><span class="sxs-lookup"><span data-stu-id="bd227-153">`false` - non-concurrent GC</span></span> | <span data-ttu-id="bd227-154">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bd227-154">.NET Core 1.0</span></span> |
| <span data-ttu-id="bd227-155">MSBuild 属性 </span><span class="sxs-lookup"><span data-stu-id="bd227-155">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="bd227-156">`true` - 后台 GC</span><span class="sxs-lookup"><span data-stu-id="bd227-156">`true` - background GC</span></span><br/><span data-ttu-id="bd227-157">`false` - 非并发 GC</span><span class="sxs-lookup"><span data-stu-id="bd227-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="bd227-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bd227-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="bd227-159">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="bd227-159">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="bd227-160">`true` - 后台 GC</span><span class="sxs-lookup"><span data-stu-id="bd227-160">`true` - background GC</span></span><br/><span data-ttu-id="bd227-161">`false` - 非并发 GC</span><span class="sxs-lookup"><span data-stu-id="bd227-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="bd227-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bd227-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="bd227-163">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="bd227-163">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bd227-164">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="bd227-164">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="bd227-165">`true` - 后台 GC</span><span class="sxs-lookup"><span data-stu-id="bd227-165">`true` - background GC</span></span><br/><span data-ttu-id="bd227-166">`false` - 非并发 GC</span><span class="sxs-lookup"><span data-stu-id="bd227-166">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="bd227-167">示例</span><span class="sxs-lookup"><span data-stu-id="bd227-167">Examples</span></span>

<span data-ttu-id="bd227-168">runtimeconfig.json 文件： </span><span class="sxs-lookup"><span data-stu-id="bd227-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="bd227-169">项目文件：</span><span class="sxs-lookup"><span data-stu-id="bd227-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="bd227-170">管理资源使用情况</span><span class="sxs-lookup"><span data-stu-id="bd227-170">Manage resource usage</span></span>

<span data-ttu-id="bd227-171">使用此部分中所述的设置，管理垃圾回收器的内存和处理器使用情况。</span><span class="sxs-lookup"><span data-stu-id="bd227-171">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="bd227-172">有关其中某些设置的详细信息，请参阅 [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/)（服务器和工作站 GC 之间的中间地带）博客条目。</span><span class="sxs-lookup"><span data-stu-id="bd227-172">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="bd227-173">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="bd227-173">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="bd227-174">限制通过垃圾回收器创建的堆数。</span><span class="sxs-lookup"><span data-stu-id="bd227-174">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="bd227-175">仅适用于服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="bd227-175">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="bd227-176">如果启用了默认的 [GC 处理器关联](#systemgcnoaffinitizecomplus_gcnoaffinitize)，堆计数设置会将 `n` 个 GC 堆/线程关联到前 `n` 个处理器。</span><span class="sxs-lookup"><span data-stu-id="bd227-176">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="bd227-177">（使用[关联掩码](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask)或[关联范围](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges)设置可精确指定要关联的处理器。）</span><span class="sxs-lookup"><span data-stu-id="bd227-177">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="bd227-178">如果禁用了 [GC 处理器关联](#systemgcnoaffinitizecomplus_gcnoaffinitize)，则此设置会限制 GC 堆的数量。</span><span class="sxs-lookup"><span data-stu-id="bd227-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="bd227-179">有关详细信息，请参阅 [GCHeapCount 备注](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks)。</span><span class="sxs-lookup"><span data-stu-id="bd227-179">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="bd227-180">设置名</span><span class="sxs-lookup"><span data-stu-id="bd227-180">Setting name</span></span> | <span data-ttu-id="bd227-181">值</span><span class="sxs-lookup"><span data-stu-id="bd227-181">Values</span></span> | <span data-ttu-id="bd227-182">引入的版本</span><span class="sxs-lookup"><span data-stu-id="bd227-182">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bd227-183">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bd227-183">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="bd227-184">十进制值 </span><span class="sxs-lookup"><span data-stu-id="bd227-184">*decimal value*</span></span> | <span data-ttu-id="bd227-185">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bd227-185">.NET Core 3.0</span></span> |
| <span data-ttu-id="bd227-186">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="bd227-186">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="bd227-187">十六进制值 </span><span class="sxs-lookup"><span data-stu-id="bd227-187">*hexadecimal value*</span></span> | <span data-ttu-id="bd227-188">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bd227-188">.NET Core 3.0</span></span> |
| <span data-ttu-id="bd227-189">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="bd227-189">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bd227-190">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="bd227-190">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="bd227-191">十进制值 </span><span class="sxs-lookup"><span data-stu-id="bd227-191">*decimal value*</span></span> | <span data-ttu-id="bd227-192">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="bd227-192">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="bd227-193">示例：</span><span class="sxs-lookup"><span data-stu-id="bd227-193">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapCount": 16
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="bd227-194">如果要在 runtimeconfig.template.json  中设置该选项，请指定一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="bd227-194">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="bd227-195">如果要将选项设置为一个环境变量，请指定一个十六进制值。</span><span class="sxs-lookup"><span data-stu-id="bd227-195">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="bd227-196">例如，若要将堆数限制为 16，则该值对于 JSON 文件为 16，对于环境变量则为 0x10 或 10。</span><span class="sxs-lookup"><span data-stu-id="bd227-196">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="bd227-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="bd227-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="bd227-198">指定垃圾回收器线程应使用的确切处理器数。</span><span class="sxs-lookup"><span data-stu-id="bd227-198">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="bd227-199">如果禁用了 [GC 处理器关联](#systemgcnoaffinitizecomplus_gcnoaffinitize)，则忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="bd227-199">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="bd227-200">仅适用于服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="bd227-200">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="bd227-201">该值是一个位掩码，用于定义可用于该进程的处理器。</span><span class="sxs-lookup"><span data-stu-id="bd227-201">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="bd227-202">例如，十进制值 1023 或十六进制值 0x3FF 或 3FF（如果使用环境变量）在二进制记数法中为 0011 1111 1111。</span><span class="sxs-lookup"><span data-stu-id="bd227-202">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="bd227-203">这指定将使用前 10 个处理器。</span><span class="sxs-lookup"><span data-stu-id="bd227-203">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="bd227-204">若要指定接下来使用的 10 个处理器（即处理器 10-19），请指定一个十进制值 1047552（或十六进制值 0xFFC00 或 FFC00），它等效于二进制值 1111 1111 1100 0000 0000。</span><span class="sxs-lookup"><span data-stu-id="bd227-204">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="bd227-205">设置名</span><span class="sxs-lookup"><span data-stu-id="bd227-205">Setting name</span></span> | <span data-ttu-id="bd227-206">值</span><span class="sxs-lookup"><span data-stu-id="bd227-206">Values</span></span> | <span data-ttu-id="bd227-207">引入的版本</span><span class="sxs-lookup"><span data-stu-id="bd227-207">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bd227-208">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bd227-208">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="bd227-209">十进制值 </span><span class="sxs-lookup"><span data-stu-id="bd227-209">*decimal value*</span></span> | <span data-ttu-id="bd227-210">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bd227-210">.NET Core 3.0</span></span> |
| <span data-ttu-id="bd227-211">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="bd227-211">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="bd227-212">十六进制值 </span><span class="sxs-lookup"><span data-stu-id="bd227-212">*hexadecimal value*</span></span> | <span data-ttu-id="bd227-213">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bd227-213">.NET Core 3.0</span></span> |
| <span data-ttu-id="bd227-214">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="bd227-214">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bd227-215">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="bd227-215">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="bd227-216">十进制值 </span><span class="sxs-lookup"><span data-stu-id="bd227-216">*decimal value*</span></span> | <span data-ttu-id="bd227-217">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="bd227-217">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="bd227-218">示例：</span><span class="sxs-lookup"><span data-stu-id="bd227-218">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="bd227-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="bd227-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="bd227-220">指定用于垃圾回收器线程的处理器列表。</span><span class="sxs-lookup"><span data-stu-id="bd227-220">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="bd227-221">此设置与 [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) 类似，只是它允许你指定超过 64 个的处理器。</span><span class="sxs-lookup"><span data-stu-id="bd227-221">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="bd227-222">对于 Windows 操作系统，请为处理器编号或范围加上相应的 [CPU 组](/windows/win32/procthread/processor-groups)作为前缀，例如“0:1-10,0:12,1:50-52,1:70”。</span><span class="sxs-lookup"><span data-stu-id="bd227-222">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="bd227-223">如果禁用了 [GC 处理器关联](#systemgcnoaffinitizecomplus_gcnoaffinitize)，则忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="bd227-223">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="bd227-224">仅适用于服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="bd227-224">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="bd227-225">有关详细信息，请参阅 Maoni Stephens 的博客文章 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)（在 CPU 大于 64 个的计算机上，为 GC 提供更好的 CPU 配置）。</span><span class="sxs-lookup"><span data-stu-id="bd227-225">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="bd227-226">设置名</span><span class="sxs-lookup"><span data-stu-id="bd227-226">Setting name</span></span> | <span data-ttu-id="bd227-227">值</span><span class="sxs-lookup"><span data-stu-id="bd227-227">Values</span></span> | <span data-ttu-id="bd227-228">引入的版本</span><span class="sxs-lookup"><span data-stu-id="bd227-228">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bd227-229">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bd227-229">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="bd227-230">以逗号分隔的处理器编号列表或处理器编号范围。</span><span class="sxs-lookup"><span data-stu-id="bd227-230">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="bd227-231">Unix 示例：“1-10,12,50-52,70”</span><span class="sxs-lookup"><span data-stu-id="bd227-231">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="bd227-232">Windows 示例：“0:1-10,0:12,1:50-52,1:70”</span><span class="sxs-lookup"><span data-stu-id="bd227-232">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="bd227-233">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bd227-233">.NET Core 3.0</span></span> |
| <span data-ttu-id="bd227-234">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="bd227-234">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="bd227-235">以逗号分隔的处理器编号列表或处理器编号范围。</span><span class="sxs-lookup"><span data-stu-id="bd227-235">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="bd227-236">Unix 示例：“1-10,12,50-52,70”</span><span class="sxs-lookup"><span data-stu-id="bd227-236">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="bd227-237">Windows 示例：“0:1-10,0:12,1:50-52,1:70”</span><span class="sxs-lookup"><span data-stu-id="bd227-237">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="bd227-238">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bd227-238">.NET Core 3.0</span></span> |

<span data-ttu-id="bd227-239">示例：</span><span class="sxs-lookup"><span data-stu-id="bd227-239">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="bd227-240">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="bd227-240">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="bd227-241">配置垃圾回收器是否使用 [CPU 组](/windows/win32/procthread/processor-groups)。</span><span class="sxs-lookup"><span data-stu-id="bd227-241">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="bd227-242">当 64 位 Windows 计算机具有多个 CPU 组（即，有超过 64 个处理器）时，通过启用此元素，可跨所有 CPU 组扩展垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="bd227-242">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="bd227-243">垃圾回收器使用所有核心来创建和平衡堆。</span><span class="sxs-lookup"><span data-stu-id="bd227-243">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="bd227-244">仅适用于 64 位 Windows 操作系统上的服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="bd227-244">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="bd227-245">默认：禁用 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="bd227-245">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="bd227-246">有关详细信息，请参阅 Maoni Stephens 的博客文章 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)（在 CPU 大于 64 个的计算机上，为 GC 提供更好的 CPU 配置）。</span><span class="sxs-lookup"><span data-stu-id="bd227-246">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="bd227-247">设置名</span><span class="sxs-lookup"><span data-stu-id="bd227-247">Setting name</span></span> | <span data-ttu-id="bd227-248">值</span><span class="sxs-lookup"><span data-stu-id="bd227-248">Values</span></span> | <span data-ttu-id="bd227-249">引入的版本</span><span class="sxs-lookup"><span data-stu-id="bd227-249">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bd227-250">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bd227-250">**runtimeconfig.json**</span></span> | <span data-ttu-id="bd227-251">不可用</span><span class="sxs-lookup"><span data-stu-id="bd227-251">N/A</span></span> | <span data-ttu-id="bd227-252">不可用</span><span class="sxs-lookup"><span data-stu-id="bd227-252">N/A</span></span> | <span data-ttu-id="bd227-253">不可用</span><span class="sxs-lookup"><span data-stu-id="bd227-253">N/A</span></span> |
| <span data-ttu-id="bd227-254">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="bd227-254">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="bd227-255">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="bd227-255">`0` - disabled</span></span><br/><span data-ttu-id="bd227-256">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="bd227-256">`1` - enabled</span></span> | <span data-ttu-id="bd227-257">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bd227-257">.NET Core 1.0</span></span> |
| <span data-ttu-id="bd227-258">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="bd227-258">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bd227-259">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="bd227-259">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="bd227-260">`false` - 禁用</span><span class="sxs-lookup"><span data-stu-id="bd227-260">`false` - disabled</span></span><br/><span data-ttu-id="bd227-261">`true` - 启用</span><span class="sxs-lookup"><span data-stu-id="bd227-261">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="bd227-262">若要配置公共语言运行时 (CLR)，使其也在所有 CPU 组之间分配线程池中的线程，请启用 [Thread_UseAllCpuGroups 元素](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)选项。</span><span class="sxs-lookup"><span data-stu-id="bd227-262">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="bd227-263">对于 .NET Core 应用，可以通过将 `COMPlus_Thread_UseAllCpuGroups` 环境变量的值设置为 `1` 以启用此选项。</span><span class="sxs-lookup"><span data-stu-id="bd227-263">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="bd227-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="bd227-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="bd227-265">指定是否将垃圾回收线程与处理器关联  。</span><span class="sxs-lookup"><span data-stu-id="bd227-265">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="bd227-266">若要关联一个 GC 线程，则意味着它只能在其特定的 CPU 上运行。</span><span class="sxs-lookup"><span data-stu-id="bd227-266">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="bd227-267">为每个 GC 线程创建一个堆。</span><span class="sxs-lookup"><span data-stu-id="bd227-267">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="bd227-268">仅适用于服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="bd227-268">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="bd227-269">默认：将垃圾回收线程与处理器关联 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="bd227-269">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="bd227-270">设置名</span><span class="sxs-lookup"><span data-stu-id="bd227-270">Setting name</span></span> | <span data-ttu-id="bd227-271">值</span><span class="sxs-lookup"><span data-stu-id="bd227-271">Values</span></span> | <span data-ttu-id="bd227-272">引入的版本</span><span class="sxs-lookup"><span data-stu-id="bd227-272">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bd227-273">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bd227-273">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="bd227-274">`false` - 关联</span><span class="sxs-lookup"><span data-stu-id="bd227-274">`false` - affinitize</span></span><br/><span data-ttu-id="bd227-275">`true` - 不关联</span><span class="sxs-lookup"><span data-stu-id="bd227-275">`true` - don't affinitize</span></span> | <span data-ttu-id="bd227-276">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bd227-276">.NET Core 3.0</span></span> |
| <span data-ttu-id="bd227-277">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="bd227-277">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="bd227-278">`0` - 关联</span><span class="sxs-lookup"><span data-stu-id="bd227-278">`0` - affinitize</span></span><br/><span data-ttu-id="bd227-279">`1` - 不关联</span><span class="sxs-lookup"><span data-stu-id="bd227-279">`1` - don't affinitize</span></span> | <span data-ttu-id="bd227-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bd227-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="bd227-281">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="bd227-281">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bd227-282">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="bd227-282">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="bd227-283">`false` - 关联</span><span class="sxs-lookup"><span data-stu-id="bd227-283">`false` - affinitize</span></span><br/><span data-ttu-id="bd227-284">`true` - 不关联</span><span class="sxs-lookup"><span data-stu-id="bd227-284">`true` - don't affinitize</span></span> | <span data-ttu-id="bd227-285">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="bd227-285">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="bd227-286">示例：</span><span class="sxs-lookup"><span data-stu-id="bd227-286">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="bd227-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="bd227-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="bd227-288">指定 GC 堆和 GC 簿记的最大提交大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="bd227-288">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="bd227-289">此设置仅适用于 64 位计算机。</span><span class="sxs-lookup"><span data-stu-id="bd227-289">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="bd227-290">默认值（仅在某些情况下适用）是 20 MB 或容器内存限制的 75%（以较小者为准）。</span><span class="sxs-lookup"><span data-stu-id="bd227-290">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="bd227-291">此默认值在以下情况下适用：</span><span class="sxs-lookup"><span data-stu-id="bd227-291">The default value applies if:</span></span>

  - <span data-ttu-id="bd227-292">进程正在具有指定内存限制的容器中运行。</span><span class="sxs-lookup"><span data-stu-id="bd227-292">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="bd227-293">[HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) 未设置。</span><span class="sxs-lookup"><span data-stu-id="bd227-293">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="bd227-294">设置名</span><span class="sxs-lookup"><span data-stu-id="bd227-294">Setting name</span></span> | <span data-ttu-id="bd227-295">值</span><span class="sxs-lookup"><span data-stu-id="bd227-295">Values</span></span> | <span data-ttu-id="bd227-296">引入的版本</span><span class="sxs-lookup"><span data-stu-id="bd227-296">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bd227-297">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bd227-297">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="bd227-298">十进制值 </span><span class="sxs-lookup"><span data-stu-id="bd227-298">*decimal value*</span></span> | <span data-ttu-id="bd227-299">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bd227-299">.NET Core 3.0</span></span> |
| <span data-ttu-id="bd227-300">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="bd227-300">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="bd227-301">十六进制值 </span><span class="sxs-lookup"><span data-stu-id="bd227-301">*hexadecimal value*</span></span> | <span data-ttu-id="bd227-302">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bd227-302">.NET Core 3.0</span></span> |

<span data-ttu-id="bd227-303">示例：</span><span class="sxs-lookup"><span data-stu-id="bd227-303">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimit": 209715200
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="bd227-304">如果要在 runtimeconfig.template.json  中设置该选项，请指定一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="bd227-304">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="bd227-305">如果要将选项设置为一个环境变量，请指定一个十六进制值。</span><span class="sxs-lookup"><span data-stu-id="bd227-305">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="bd227-306">例如，若要将堆硬限制指定为 200 个兆字节 (MiB)，则该值对于 JSON 文件为 209715200，对于环境变量则为 0xC800000 或 C800000。</span><span class="sxs-lookup"><span data-stu-id="bd227-306">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="bd227-307">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="bd227-307">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="bd227-308">指定允许的 GC 堆使用量占总物理内存的百分比。</span><span class="sxs-lookup"><span data-stu-id="bd227-308">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="bd227-309">如果还设置了 [System.GC.heaphdlimit](#systemgcheaphardlimitcomplus_gcheaphardlimit)，则忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="bd227-309">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="bd227-310">此设置仅适用于 64 位计算机。</span><span class="sxs-lookup"><span data-stu-id="bd227-310">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="bd227-311">如果进程正在具有指定内存限制的容器中运行，则百分比的计算结果将为该内存限制的百分比。</span><span class="sxs-lookup"><span data-stu-id="bd227-311">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="bd227-312">默认值（仅在某些情况下适用）是 20 MB 或容器内存限制的 75%（以较小者为准）。</span><span class="sxs-lookup"><span data-stu-id="bd227-312">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="bd227-313">此默认值在以下情况下适用：</span><span class="sxs-lookup"><span data-stu-id="bd227-313">The default value applies if:</span></span>

  - <span data-ttu-id="bd227-314">进程正在具有指定内存限制的容器中运行。</span><span class="sxs-lookup"><span data-stu-id="bd227-314">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="bd227-315">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) 未设置。</span><span class="sxs-lookup"><span data-stu-id="bd227-315">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="bd227-316">设置名</span><span class="sxs-lookup"><span data-stu-id="bd227-316">Setting name</span></span> | <span data-ttu-id="bd227-317">值</span><span class="sxs-lookup"><span data-stu-id="bd227-317">Values</span></span> | <span data-ttu-id="bd227-318">引入的版本</span><span class="sxs-lookup"><span data-stu-id="bd227-318">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bd227-319">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bd227-319">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="bd227-320">十进制值 </span><span class="sxs-lookup"><span data-stu-id="bd227-320">*decimal value*</span></span> | <span data-ttu-id="bd227-321">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bd227-321">.NET Core 3.0</span></span> |
| <span data-ttu-id="bd227-322">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="bd227-322">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="bd227-323">十六进制值 </span><span class="sxs-lookup"><span data-stu-id="bd227-323">*hexadecimal value*</span></span> | <span data-ttu-id="bd227-324">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bd227-324">.NET Core 3.0</span></span> |

<span data-ttu-id="bd227-325">示例：</span><span class="sxs-lookup"><span data-stu-id="bd227-325">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimitPercent": 30
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="bd227-326">如果要在 runtimeconfig.template.json  中设置该选项，请指定一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="bd227-326">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="bd227-327">如果要将选项设置为一个环境变量，请指定一个十六进制值。</span><span class="sxs-lookup"><span data-stu-id="bd227-327">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="bd227-328">例如，若要将堆使用率限制为 30%，则该值对于 JSON 文件为 30，对于环境变量则为 0x1E 或 1E。</span><span class="sxs-lookup"><span data-stu-id="bd227-328">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="bd227-329">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="bd227-329">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="bd227-330">配置是将应删除的段置于备用列表上供将来使用，还是将其释放回操作系统 (OS)。</span><span class="sxs-lookup"><span data-stu-id="bd227-330">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="bd227-331">默认：将段释放回操作系统 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="bd227-331">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="bd227-332">设置名</span><span class="sxs-lookup"><span data-stu-id="bd227-332">Setting name</span></span> | <span data-ttu-id="bd227-333">值</span><span class="sxs-lookup"><span data-stu-id="bd227-333">Values</span></span> | <span data-ttu-id="bd227-334">引入的版本</span><span class="sxs-lookup"><span data-stu-id="bd227-334">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bd227-335">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bd227-335">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="bd227-336">`false` - 释放到 OS</span><span class="sxs-lookup"><span data-stu-id="bd227-336">`false` - release to OS</span></span><br/><span data-ttu-id="bd227-337">`true` - 置于备用列表上</span><span class="sxs-lookup"><span data-stu-id="bd227-337">`true` - put on standby</span></span> | <span data-ttu-id="bd227-338">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bd227-338">.NET Core 1.0</span></span> |
| <span data-ttu-id="bd227-339">MSBuild 属性 </span><span class="sxs-lookup"><span data-stu-id="bd227-339">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="bd227-340">`false` - 释放到 OS</span><span class="sxs-lookup"><span data-stu-id="bd227-340">`false` - release to OS</span></span><br/><span data-ttu-id="bd227-341">`true` - 置于备用列表上</span><span class="sxs-lookup"><span data-stu-id="bd227-341">`true` - put on standby</span></span> | <span data-ttu-id="bd227-342">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bd227-342">.NET Core 1.0</span></span> |
| <span data-ttu-id="bd227-343">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="bd227-343">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="bd227-344">`0` - 释放到 OS</span><span class="sxs-lookup"><span data-stu-id="bd227-344">`0` - release to OS</span></span><br/><span data-ttu-id="bd227-345">`1` - 置于备用列表上</span><span class="sxs-lookup"><span data-stu-id="bd227-345">`1` - put on standby</span></span> | <span data-ttu-id="bd227-346">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bd227-346">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="bd227-347">示例</span><span class="sxs-lookup"><span data-stu-id="bd227-347">Examples</span></span>

<span data-ttu-id="bd227-348">runtimeconfig.json 文件： </span><span class="sxs-lookup"><span data-stu-id="bd227-348">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="bd227-349">项目文件：</span><span class="sxs-lookup"><span data-stu-id="bd227-349">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="bd227-350">大型页面</span><span class="sxs-lookup"><span data-stu-id="bd227-350">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="bd227-351">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="bd227-351">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="bd227-352">指定设置堆硬限制时是否应使用大型页面。</span><span class="sxs-lookup"><span data-stu-id="bd227-352">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="bd227-353">默认：禁用 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="bd227-353">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="bd227-354">这是一项实验性设置。</span><span class="sxs-lookup"><span data-stu-id="bd227-354">This is an experimental setting.</span></span>

| | <span data-ttu-id="bd227-355">设置名</span><span class="sxs-lookup"><span data-stu-id="bd227-355">Setting name</span></span> | <span data-ttu-id="bd227-356">值</span><span class="sxs-lookup"><span data-stu-id="bd227-356">Values</span></span> | <span data-ttu-id="bd227-357">引入的版本</span><span class="sxs-lookup"><span data-stu-id="bd227-357">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bd227-358">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bd227-358">**runtimeconfig.json**</span></span> | <span data-ttu-id="bd227-359">不可用</span><span class="sxs-lookup"><span data-stu-id="bd227-359">N/A</span></span> | <span data-ttu-id="bd227-360">不可用</span><span class="sxs-lookup"><span data-stu-id="bd227-360">N/A</span></span> | <span data-ttu-id="bd227-361">不可用</span><span class="sxs-lookup"><span data-stu-id="bd227-361">N/A</span></span> |
| <span data-ttu-id="bd227-362">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="bd227-362">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="bd227-363">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="bd227-363">`0` - disabled</span></span><br/><span data-ttu-id="bd227-364">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="bd227-364">`1` - enabled</span></span> | <span data-ttu-id="bd227-365">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bd227-365">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="bd227-366">大型对象</span><span class="sxs-lookup"><span data-stu-id="bd227-366">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="bd227-367">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="bd227-367">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="bd227-368">在 64 位平台上，为总大小大于 2 千兆字节 (GB) 的数组配置垃圾回收器支持。</span><span class="sxs-lookup"><span data-stu-id="bd227-368">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="bd227-369">默认：启用 (`1`)。</span><span class="sxs-lookup"><span data-stu-id="bd227-369">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="bd227-370">在未来的 .NET 版本中，此选项可能会过时。</span><span class="sxs-lookup"><span data-stu-id="bd227-370">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="bd227-371">设置名</span><span class="sxs-lookup"><span data-stu-id="bd227-371">Setting name</span></span> | <span data-ttu-id="bd227-372">值</span><span class="sxs-lookup"><span data-stu-id="bd227-372">Values</span></span> | <span data-ttu-id="bd227-373">引入的版本</span><span class="sxs-lookup"><span data-stu-id="bd227-373">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bd227-374">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bd227-374">**runtimeconfig.json**</span></span> | <span data-ttu-id="bd227-375">不可用</span><span class="sxs-lookup"><span data-stu-id="bd227-375">N/A</span></span> | <span data-ttu-id="bd227-376">不可用</span><span class="sxs-lookup"><span data-stu-id="bd227-376">N/A</span></span> | <span data-ttu-id="bd227-377">不可用</span><span class="sxs-lookup"><span data-stu-id="bd227-377">N/A</span></span> |
| <span data-ttu-id="bd227-378">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="bd227-378">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="bd227-379">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="bd227-379">`1` - enabled</span></span><br/> <span data-ttu-id="bd227-380">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="bd227-380">`0` - disabled</span></span> | <span data-ttu-id="bd227-381">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bd227-381">.NET Core 1.0</span></span> |
| <span data-ttu-id="bd227-382">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="bd227-382">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bd227-383">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="bd227-383">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="bd227-384">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="bd227-384">`1` - enabled</span></span><br/> <span data-ttu-id="bd227-385">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="bd227-385">`0` - disabled</span></span> | <span data-ttu-id="bd227-386">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="bd227-386">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="bd227-387">大型对象堆阈值</span><span class="sxs-lookup"><span data-stu-id="bd227-387">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="bd227-388">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="bd227-388">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="bd227-389">指定导致对象进入大型对象堆 (LOH) 的阈值大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="bd227-389">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="bd227-390">默认阈值为 85,000 字节。</span><span class="sxs-lookup"><span data-stu-id="bd227-390">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="bd227-391">指定的值必须大于默认阈值。</span><span class="sxs-lookup"><span data-stu-id="bd227-391">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="bd227-392">设置名</span><span class="sxs-lookup"><span data-stu-id="bd227-392">Setting name</span></span> | <span data-ttu-id="bd227-393">值</span><span class="sxs-lookup"><span data-stu-id="bd227-393">Values</span></span> | <span data-ttu-id="bd227-394">引入的版本</span><span class="sxs-lookup"><span data-stu-id="bd227-394">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bd227-395">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bd227-395">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="bd227-396">十进制值 </span><span class="sxs-lookup"><span data-stu-id="bd227-396">*decimal value*</span></span> | <span data-ttu-id="bd227-397">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bd227-397">.NET Core 1.0</span></span> |
| <span data-ttu-id="bd227-398">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="bd227-398">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="bd227-399">十六进制值 </span><span class="sxs-lookup"><span data-stu-id="bd227-399">*hexadecimal value*</span></span> | <span data-ttu-id="bd227-400">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bd227-400">.NET Core 1.0</span></span> |
| <span data-ttu-id="bd227-401">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="bd227-401">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bd227-402">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="bd227-402">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="bd227-403">十进制值 </span><span class="sxs-lookup"><span data-stu-id="bd227-403">*decimal value*</span></span> | <span data-ttu-id="bd227-404">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="bd227-404">.NET Framework 4.8</span></span> |

<span data-ttu-id="bd227-405">示例：</span><span class="sxs-lookup"><span data-stu-id="bd227-405">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.LOHThreshold": 120000
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="bd227-406">如果要在 runtimeconfig.template.json  中设置该选项，请指定一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="bd227-406">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="bd227-407">如果要将选项设置为一个环境变量，请指定一个十六进制值。</span><span class="sxs-lookup"><span data-stu-id="bd227-407">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="bd227-408">例如，若要将阙值大小设置为 120,000 个字节，则该值对于 JSON 文件为 120,000，对于环境变量则为 0x1D4C0 或 1D4C0。</span><span class="sxs-lookup"><span data-stu-id="bd227-408">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="bd227-409">独立 GC</span><span class="sxs-lookup"><span data-stu-id="bd227-409">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="bd227-410">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="bd227-410">COMPlus_GCName</span></span>

- <span data-ttu-id="bd227-411">指定库的路径，该库包含运行时打算加载的垃圾回收器。</span><span class="sxs-lookup"><span data-stu-id="bd227-411">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="bd227-412">有关详细信息，请参阅 [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md)（独立 GC 加载程序设计）。</span><span class="sxs-lookup"><span data-stu-id="bd227-412">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="bd227-413">设置名</span><span class="sxs-lookup"><span data-stu-id="bd227-413">Setting name</span></span> | <span data-ttu-id="bd227-414">值</span><span class="sxs-lookup"><span data-stu-id="bd227-414">Values</span></span> | <span data-ttu-id="bd227-415">引入的版本</span><span class="sxs-lookup"><span data-stu-id="bd227-415">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bd227-416">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bd227-416">**runtimeconfig.json**</span></span> | <span data-ttu-id="bd227-417">不可用</span><span class="sxs-lookup"><span data-stu-id="bd227-417">N/A</span></span> | <span data-ttu-id="bd227-418">不可用</span><span class="sxs-lookup"><span data-stu-id="bd227-418">N/A</span></span> | <span data-ttu-id="bd227-419">不可用</span><span class="sxs-lookup"><span data-stu-id="bd227-419">N/A</span></span> |
| <span data-ttu-id="bd227-420">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="bd227-420">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="bd227-421">string_path </span><span class="sxs-lookup"><span data-stu-id="bd227-421">*string_path*</span></span> | <span data-ttu-id="bd227-422">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="bd227-422">.NET Core 2.0</span></span> |
