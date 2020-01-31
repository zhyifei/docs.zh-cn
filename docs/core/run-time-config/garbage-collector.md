---
title: 垃圾回收器配置设置
description: 了解用于配置垃圾回收器如何为 .NET Core 应用管理内存的运行时设置。
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: 044083d69601f5092724a46d358b2ee5673d428d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733521"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="d5806-103">用于垃圾回收的运行时配置选项</span><span class="sxs-lookup"><span data-stu-id="d5806-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="d5806-104">此页包含有关可在运行时更改的垃圾回收器 (GC) 设置的信息。</span><span class="sxs-lookup"><span data-stu-id="d5806-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="d5806-105">如果你要尝试让正在运行的应用达到最佳性能，请考虑使用这些设置。</span><span class="sxs-lookup"><span data-stu-id="d5806-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="d5806-106">然而，在特定情况下，默认值为大多数应用程序提供最佳性能。</span><span class="sxs-lookup"><span data-stu-id="d5806-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="d5806-107">设置在此页上被排入组中。</span><span class="sxs-lookup"><span data-stu-id="d5806-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="d5806-108">每个组内的设置通常彼此结合使用以实现特定的结果。</span><span class="sxs-lookup"><span data-stu-id="d5806-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="d5806-109">这些设置也可以在应用运行时由应用动态地进行更改，因此，你设置的任何运行时设置都可能会被覆盖。</span><span class="sxs-lookup"><span data-stu-id="d5806-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="d5806-110">某些设置（如[延迟级别](../../standard/garbage-collection/latency.md)）通常仅在设计时通过 API 进行设置。</span><span class="sxs-lookup"><span data-stu-id="d5806-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="d5806-111">此页面省略了此类设置。</span><span class="sxs-lookup"><span data-stu-id="d5806-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="d5806-112">对于数值，请对 runtimeconfig.json  文件中的设置使用十进制表示法，而对环境变量设置使用十六进制表示法。</span><span class="sxs-lookup"><span data-stu-id="d5806-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="d5806-113">对于十六进制值，可以使用或不使用“0x”前缀来指定它们。</span><span class="sxs-lookup"><span data-stu-id="d5806-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="d5806-114">垃圾回收的风格</span><span class="sxs-lookup"><span data-stu-id="d5806-114">Flavors of garbage collection</span></span>

<span data-ttu-id="d5806-115">垃圾回收的两种主要风格是工作站 GC 和服务器 GC。</span><span class="sxs-lookup"><span data-stu-id="d5806-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="d5806-116">有关两者之间的差异的详细信息，请参阅[垃圾回收的基础知识](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection)。</span><span class="sxs-lookup"><span data-stu-id="d5806-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="d5806-117">垃圾回收的次要风格是后台垃圾回收和非并发垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="d5806-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="d5806-118">使用以下设置，选择垃圾回收的风格：</span><span class="sxs-lookup"><span data-stu-id="d5806-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="d5806-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="d5806-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="d5806-120">配置应用程序是使用工作站垃圾回收还是服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="d5806-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="d5806-121">默认：工作站垃圾回收 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="d5806-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="d5806-122">设置名</span><span class="sxs-lookup"><span data-stu-id="d5806-122">Setting name</span></span> | <span data-ttu-id="d5806-123">值</span><span class="sxs-lookup"><span data-stu-id="d5806-123">Values</span></span> | <span data-ttu-id="d5806-124">引入的版本</span><span class="sxs-lookup"><span data-stu-id="d5806-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d5806-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d5806-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="d5806-126">`false` - 工作站</span><span class="sxs-lookup"><span data-stu-id="d5806-126">`false` - workstation</span></span><br/><span data-ttu-id="d5806-127">`true` - 服务器</span><span class="sxs-lookup"><span data-stu-id="d5806-127">`true` - server</span></span> | <span data-ttu-id="d5806-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d5806-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="d5806-129">MSBuild 属性 </span><span class="sxs-lookup"><span data-stu-id="d5806-129">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="d5806-130">`false` - 工作站</span><span class="sxs-lookup"><span data-stu-id="d5806-130">`false` - workstation</span></span><br/><span data-ttu-id="d5806-131">`true` - 服务器</span><span class="sxs-lookup"><span data-stu-id="d5806-131">`true` - server</span></span> | <span data-ttu-id="d5806-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d5806-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="d5806-133">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="d5806-133">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="d5806-134">`0` - 工作站</span><span class="sxs-lookup"><span data-stu-id="d5806-134">`0` - workstation</span></span><br/><span data-ttu-id="d5806-135">`1` - 服务器</span><span class="sxs-lookup"><span data-stu-id="d5806-135">`1` - server</span></span> | <span data-ttu-id="d5806-136">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d5806-136">.NET Core 1.0</span></span> |
| <span data-ttu-id="d5806-137">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="d5806-137">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d5806-138">GCServer</span><span class="sxs-lookup"><span data-stu-id="d5806-138">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="d5806-139">`false` - 工作站</span><span class="sxs-lookup"><span data-stu-id="d5806-139">`false` - workstation</span></span><br/><span data-ttu-id="d5806-140">`true` - 服务器</span><span class="sxs-lookup"><span data-stu-id="d5806-140">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="d5806-141">示例</span><span class="sxs-lookup"><span data-stu-id="d5806-141">Examples</span></span>

<span data-ttu-id="d5806-142">runtimeconfig.json 文件： </span><span class="sxs-lookup"><span data-stu-id="d5806-142">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="d5806-143">项目文件：</span><span class="sxs-lookup"><span data-stu-id="d5806-143">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="d5806-144">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="d5806-144">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="d5806-145">配置是否启用后台（并发）垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="d5806-145">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="d5806-146">默认：启用 (`true`)。</span><span class="sxs-lookup"><span data-stu-id="d5806-146">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="d5806-147">有关详细信息，请参阅[后台垃圾回收](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection)和[后台服务器垃圾回收](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection)。</span><span class="sxs-lookup"><span data-stu-id="d5806-147">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="d5806-148">设置名</span><span class="sxs-lookup"><span data-stu-id="d5806-148">Setting name</span></span> | <span data-ttu-id="d5806-149">值</span><span class="sxs-lookup"><span data-stu-id="d5806-149">Values</span></span> | <span data-ttu-id="d5806-150">引入的版本</span><span class="sxs-lookup"><span data-stu-id="d5806-150">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d5806-151">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d5806-151">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="d5806-152">`true` - 后台 GC</span><span class="sxs-lookup"><span data-stu-id="d5806-152">`true` - background GC</span></span><br/><span data-ttu-id="d5806-153">`false` - 非并发 GC</span><span class="sxs-lookup"><span data-stu-id="d5806-153">`false` - non-concurrent GC</span></span> | <span data-ttu-id="d5806-154">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d5806-154">.NET Core 1.0</span></span> |
| <span data-ttu-id="d5806-155">MSBuild 属性 </span><span class="sxs-lookup"><span data-stu-id="d5806-155">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="d5806-156">`true` - 后台 GC</span><span class="sxs-lookup"><span data-stu-id="d5806-156">`true` - background GC</span></span><br/><span data-ttu-id="d5806-157">`false` - 非并发 GC</span><span class="sxs-lookup"><span data-stu-id="d5806-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="d5806-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d5806-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="d5806-159">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="d5806-159">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="d5806-160">`true` - 后台 GC</span><span class="sxs-lookup"><span data-stu-id="d5806-160">`true` - background GC</span></span><br/><span data-ttu-id="d5806-161">`false` - 非并发 GC</span><span class="sxs-lookup"><span data-stu-id="d5806-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="d5806-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d5806-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="d5806-163">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="d5806-163">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d5806-164">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="d5806-164">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="d5806-165">`true` - 后台 GC</span><span class="sxs-lookup"><span data-stu-id="d5806-165">`true` - background GC</span></span><br/><span data-ttu-id="d5806-166">`false` - 非并发 GC</span><span class="sxs-lookup"><span data-stu-id="d5806-166">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="d5806-167">示例</span><span class="sxs-lookup"><span data-stu-id="d5806-167">Examples</span></span>

<span data-ttu-id="d5806-168">runtimeconfig.json 文件： </span><span class="sxs-lookup"><span data-stu-id="d5806-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="d5806-169">项目文件：</span><span class="sxs-lookup"><span data-stu-id="d5806-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="d5806-170">管理资源使用情况</span><span class="sxs-lookup"><span data-stu-id="d5806-170">Manage resource usage</span></span>

<span data-ttu-id="d5806-171">使用此部分中所述的设置，管理垃圾回收器的内存和处理器使用情况。</span><span class="sxs-lookup"><span data-stu-id="d5806-171">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="d5806-172">有关其中某些设置的详细信息，请参阅 [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/)（服务器和工作站 GC 之间的中间地带）博客条目。</span><span class="sxs-lookup"><span data-stu-id="d5806-172">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="d5806-173">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="d5806-173">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="d5806-174">限制通过垃圾回收器创建的堆数。</span><span class="sxs-lookup"><span data-stu-id="d5806-174">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="d5806-175">仅适用于服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="d5806-175">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="d5806-176">如果启用了默认的 GC 处理器关联，堆计数设置会将 `n` 个 GC 堆/线程关联到前 `n` 个处理器。</span><span class="sxs-lookup"><span data-stu-id="d5806-176">If GC processor affinity is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="d5806-177">（使用关联掩码或关联范围设置来精确指定要关联的处理器。）</span><span class="sxs-lookup"><span data-stu-id="d5806-177">(Use the affinitize mask or affinitize ranges settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="d5806-178">如果禁用了 GC 处理器关联，则此设置会限制 GC 堆的数量。</span><span class="sxs-lookup"><span data-stu-id="d5806-178">If GC processor affinity is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="d5806-179">有关详细信息，请参阅 [GCHeapCount 备注](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks)。</span><span class="sxs-lookup"><span data-stu-id="d5806-179">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="d5806-180">设置名</span><span class="sxs-lookup"><span data-stu-id="d5806-180">Setting name</span></span> | <span data-ttu-id="d5806-181">值</span><span class="sxs-lookup"><span data-stu-id="d5806-181">Values</span></span> | <span data-ttu-id="d5806-182">引入的版本</span><span class="sxs-lookup"><span data-stu-id="d5806-182">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d5806-183">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d5806-183">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="d5806-184">十进制值 </span><span class="sxs-lookup"><span data-stu-id="d5806-184">*decimal value*</span></span> | <span data-ttu-id="d5806-185">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d5806-185">.NET Core 3.0</span></span> |
| <span data-ttu-id="d5806-186">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="d5806-186">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="d5806-187">十六进制值 </span><span class="sxs-lookup"><span data-stu-id="d5806-187">*hexadecimal value*</span></span> | <span data-ttu-id="d5806-188">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d5806-188">.NET Core 3.0</span></span> |
| <span data-ttu-id="d5806-189">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="d5806-189">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d5806-190">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="d5806-190">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="d5806-191">十进制值 </span><span class="sxs-lookup"><span data-stu-id="d5806-191">*decimal value*</span></span> | <span data-ttu-id="d5806-192">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="d5806-192">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="d5806-193">示例：</span><span class="sxs-lookup"><span data-stu-id="d5806-193">Example:</span></span>

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
> <span data-ttu-id="d5806-194">如果要在 runtimeconfig.template.json  中设置该选项，请指定一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="d5806-194">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="d5806-195">如果要将选项设置为一个环境变量，请指定一个十六进制值。</span><span class="sxs-lookup"><span data-stu-id="d5806-195">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="d5806-196">例如，若要将堆数限制为 16，则该值对于 JSON 文件为 16，对于环境变量则为 0x10 或 10。</span><span class="sxs-lookup"><span data-stu-id="d5806-196">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="d5806-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="d5806-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="d5806-198">指定垃圾回收器线程应使用的确切处理器数。</span><span class="sxs-lookup"><span data-stu-id="d5806-198">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="d5806-199">如果通过将 `System.GC.NoAffinitize` 设置为 `true` 禁用了处理器关联，则忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="d5806-199">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="d5806-200">仅适用于服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="d5806-200">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="d5806-201">该值是一个位掩码，用于定义可用于该进程的处理器。</span><span class="sxs-lookup"><span data-stu-id="d5806-201">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="d5806-202">例如，十进制值 1023 或十六进制值 0x3FF 或 3FF（如果使用环境变量）在二进制记数法中为 0011 1111 1111。</span><span class="sxs-lookup"><span data-stu-id="d5806-202">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="d5806-203">这指定将使用前 10 个处理器。</span><span class="sxs-lookup"><span data-stu-id="d5806-203">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="d5806-204">若要指定接下来使用的 10 个处理器（即处理器 10-19），请指定一个十进制值 1047552（或十六进制值 0xFFC00 或 FFC00），它等效于二进制值 1111 1111 1100 0000 0000。</span><span class="sxs-lookup"><span data-stu-id="d5806-204">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="d5806-205">设置名</span><span class="sxs-lookup"><span data-stu-id="d5806-205">Setting name</span></span> | <span data-ttu-id="d5806-206">值</span><span class="sxs-lookup"><span data-stu-id="d5806-206">Values</span></span> | <span data-ttu-id="d5806-207">引入的版本</span><span class="sxs-lookup"><span data-stu-id="d5806-207">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d5806-208">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d5806-208">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="d5806-209">十进制值 </span><span class="sxs-lookup"><span data-stu-id="d5806-209">*decimal value*</span></span> | <span data-ttu-id="d5806-210">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d5806-210">.NET Core 3.0</span></span> |
| <span data-ttu-id="d5806-211">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="d5806-211">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="d5806-212">十六进制值 </span><span class="sxs-lookup"><span data-stu-id="d5806-212">*hexadecimal value*</span></span> | <span data-ttu-id="d5806-213">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d5806-213">.NET Core 3.0</span></span> |
| <span data-ttu-id="d5806-214">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="d5806-214">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d5806-215">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="d5806-215">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="d5806-216">十进制值 </span><span class="sxs-lookup"><span data-stu-id="d5806-216">*decimal value*</span></span> | <span data-ttu-id="d5806-217">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="d5806-217">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="d5806-218">示例：</span><span class="sxs-lookup"><span data-stu-id="d5806-218">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="d5806-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="d5806-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="d5806-220">指定用于垃圾回收器线程的处理器列表。</span><span class="sxs-lookup"><span data-stu-id="d5806-220">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="d5806-221">此设置与 `System.GC.HeapAffinitizeMask` 类似，只是它允许你指定超过 64 个的处理器。</span><span class="sxs-lookup"><span data-stu-id="d5806-221">This setting is similar to `System.GC.HeapAffinitizeMask`, except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="d5806-222">对于 Windows 操作系统，请为处理器编号或范围加上相应的 [CPU 组](/windows/win32/procthread/processor-groups)作为前缀，例如“0:1-10,0:12,1:50-52,1:70”。</span><span class="sxs-lookup"><span data-stu-id="d5806-222">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="d5806-223">如果通过将 `System.GC.NoAffinitize` 设置为 `true` 禁用了处理器关联，则忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="d5806-223">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="d5806-224">仅适用于服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="d5806-224">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="d5806-225">有关详细信息，请参阅 Maoni Stephens 的博客文章 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)（在 CPU 大于 64 个的计算机上，为 GC 提供更好的 CPU 配置）。</span><span class="sxs-lookup"><span data-stu-id="d5806-225">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="d5806-226">设置名</span><span class="sxs-lookup"><span data-stu-id="d5806-226">Setting name</span></span> | <span data-ttu-id="d5806-227">值</span><span class="sxs-lookup"><span data-stu-id="d5806-227">Values</span></span> | <span data-ttu-id="d5806-228">引入的版本</span><span class="sxs-lookup"><span data-stu-id="d5806-228">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d5806-229">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d5806-229">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="d5806-230">以逗号分隔的处理器编号列表或处理器编号范围。</span><span class="sxs-lookup"><span data-stu-id="d5806-230">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="d5806-231">Unix 示例：“1-10,12,50-52,70”</span><span class="sxs-lookup"><span data-stu-id="d5806-231">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="d5806-232">Windows 示例：“0:1-10,0:12,1:50-52,1:70”</span><span class="sxs-lookup"><span data-stu-id="d5806-232">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="d5806-233">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d5806-233">.NET Core 3.0</span></span> |
| <span data-ttu-id="d5806-234">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="d5806-234">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="d5806-235">以逗号分隔的处理器编号列表或处理器编号范围。</span><span class="sxs-lookup"><span data-stu-id="d5806-235">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="d5806-236">Unix 示例：“1-10,12,50-52,70”</span><span class="sxs-lookup"><span data-stu-id="d5806-236">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="d5806-237">Windows 示例：“0:1-10,0:12,1:50-52,1:70”</span><span class="sxs-lookup"><span data-stu-id="d5806-237">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="d5806-238">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d5806-238">.NET Core 3.0</span></span> |

<span data-ttu-id="d5806-239">示例：</span><span class="sxs-lookup"><span data-stu-id="d5806-239">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="d5806-240">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="d5806-240">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="d5806-241">配置垃圾回收器是否使用 [CPU 组](/windows/win32/procthread/processor-groups)。</span><span class="sxs-lookup"><span data-stu-id="d5806-241">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="d5806-242">当 64 位 Windows 计算机具有多个 CPU 组（即，有超过 64 个处理器）时，通过启用此元素，可跨所有 CPU 组扩展垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="d5806-242">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="d5806-243">垃圾回收器使用所有核心来创建和平衡堆。</span><span class="sxs-lookup"><span data-stu-id="d5806-243">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="d5806-244">仅适用于 64 位 Windows 操作系统上的服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="d5806-244">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="d5806-245">默认：禁用 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="d5806-245">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="d5806-246">有关详细信息，请参阅 Maoni Stephens 的博客文章 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)（在 CPU 大于 64 个的计算机上，为 GC 提供更好的 CPU 配置）。</span><span class="sxs-lookup"><span data-stu-id="d5806-246">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="d5806-247">设置名</span><span class="sxs-lookup"><span data-stu-id="d5806-247">Setting name</span></span> | <span data-ttu-id="d5806-248">值</span><span class="sxs-lookup"><span data-stu-id="d5806-248">Values</span></span> | <span data-ttu-id="d5806-249">引入的版本</span><span class="sxs-lookup"><span data-stu-id="d5806-249">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d5806-250">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d5806-250">**runtimeconfig.json**</span></span> | <span data-ttu-id="d5806-251">不可用</span><span class="sxs-lookup"><span data-stu-id="d5806-251">N/A</span></span> | <span data-ttu-id="d5806-252">不可用</span><span class="sxs-lookup"><span data-stu-id="d5806-252">N/A</span></span> | <span data-ttu-id="d5806-253">不可用</span><span class="sxs-lookup"><span data-stu-id="d5806-253">N/A</span></span> |
| <span data-ttu-id="d5806-254">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="d5806-254">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="d5806-255">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="d5806-255">`0` - disabled</span></span><br/><span data-ttu-id="d5806-256">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="d5806-256">`1` - enabled</span></span> | <span data-ttu-id="d5806-257">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d5806-257">.NET Core 1.0</span></span> |
| <span data-ttu-id="d5806-258">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="d5806-258">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d5806-259">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="d5806-259">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="d5806-260">`false` - 禁用</span><span class="sxs-lookup"><span data-stu-id="d5806-260">`false` - disabled</span></span><br/><span data-ttu-id="d5806-261">`true` - 启用</span><span class="sxs-lookup"><span data-stu-id="d5806-261">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="d5806-262">若要配置公共语言运行时 (CLR)，使其也在所有 CPU 组之间分配线程池中的线程，请启用 [Thread_UseAllCpuGroups 元素](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)选项。</span><span class="sxs-lookup"><span data-stu-id="d5806-262">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="d5806-263">对于 .NET Core 应用，可以通过将 `COMPlus_Thread_UseAllCpuGroups` 环境变量的值设置为 `1` 以启用此选项。</span><span class="sxs-lookup"><span data-stu-id="d5806-263">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="d5806-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="d5806-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="d5806-265">指定是否将垃圾回收线程与处理器关联  。</span><span class="sxs-lookup"><span data-stu-id="d5806-265">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="d5806-266">若要关联一个 GC 线程，则意味着它只能在其特定的 CPU 上运行。</span><span class="sxs-lookup"><span data-stu-id="d5806-266">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="d5806-267">为每个 GC 线程创建一个堆。</span><span class="sxs-lookup"><span data-stu-id="d5806-267">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="d5806-268">仅适用于服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="d5806-268">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="d5806-269">默认：将垃圾回收线程与处理器关联 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="d5806-269">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="d5806-270">设置名</span><span class="sxs-lookup"><span data-stu-id="d5806-270">Setting name</span></span> | <span data-ttu-id="d5806-271">值</span><span class="sxs-lookup"><span data-stu-id="d5806-271">Values</span></span> | <span data-ttu-id="d5806-272">引入的版本</span><span class="sxs-lookup"><span data-stu-id="d5806-272">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d5806-273">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d5806-273">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="d5806-274">`false` - 关联</span><span class="sxs-lookup"><span data-stu-id="d5806-274">`false` - affinitize</span></span><br/><span data-ttu-id="d5806-275">`true` - 不关联</span><span class="sxs-lookup"><span data-stu-id="d5806-275">`true` - don't affinitize</span></span> | <span data-ttu-id="d5806-276">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d5806-276">.NET Core 3.0</span></span> |
| <span data-ttu-id="d5806-277">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="d5806-277">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="d5806-278">`0` - 关联</span><span class="sxs-lookup"><span data-stu-id="d5806-278">`0` - affinitize</span></span><br/><span data-ttu-id="d5806-279">`1` - 不关联</span><span class="sxs-lookup"><span data-stu-id="d5806-279">`1` - don't affinitize</span></span> | <span data-ttu-id="d5806-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d5806-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="d5806-281">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="d5806-281">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d5806-282">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="d5806-282">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="d5806-283">`false` - 关联</span><span class="sxs-lookup"><span data-stu-id="d5806-283">`false` - affinitize</span></span><br/><span data-ttu-id="d5806-284">`true` - 不关联</span><span class="sxs-lookup"><span data-stu-id="d5806-284">`true` - don't affinitize</span></span> | <span data-ttu-id="d5806-285">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="d5806-285">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="d5806-286">示例：</span><span class="sxs-lookup"><span data-stu-id="d5806-286">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="d5806-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="d5806-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="d5806-288">指定 GC 堆和 GC 簿记的最大提交大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="d5806-288">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>

| | <span data-ttu-id="d5806-289">设置名</span><span class="sxs-lookup"><span data-stu-id="d5806-289">Setting name</span></span> | <span data-ttu-id="d5806-290">值</span><span class="sxs-lookup"><span data-stu-id="d5806-290">Values</span></span> | <span data-ttu-id="d5806-291">引入的版本</span><span class="sxs-lookup"><span data-stu-id="d5806-291">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d5806-292">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d5806-292">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="d5806-293">十进制值 </span><span class="sxs-lookup"><span data-stu-id="d5806-293">*decimal value*</span></span> | <span data-ttu-id="d5806-294">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d5806-294">.NET Core 3.0</span></span> |
| <span data-ttu-id="d5806-295">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="d5806-295">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="d5806-296">十六进制值 </span><span class="sxs-lookup"><span data-stu-id="d5806-296">*hexadecimal value*</span></span> | <span data-ttu-id="d5806-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d5806-297">.NET Core 3.0</span></span> |

<span data-ttu-id="d5806-298">示例：</span><span class="sxs-lookup"><span data-stu-id="d5806-298">Example:</span></span>

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
> <span data-ttu-id="d5806-299">如果要在 runtimeconfig.template.json  中设置该选项，请指定一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="d5806-299">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="d5806-300">如果要将选项设置为一个环境变量，请指定一个十六进制值。</span><span class="sxs-lookup"><span data-stu-id="d5806-300">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="d5806-301">例如，若要将堆硬限制指定为 200 个兆字节 (MiB)，则该值对于 JSON 文件为 209715200，对于环境变量则为 0xC800000 或 C800000。</span><span class="sxs-lookup"><span data-stu-id="d5806-301">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="d5806-302">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="d5806-302">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="d5806-303">指定 GC 堆使用量占总内存的百分比。</span><span class="sxs-lookup"><span data-stu-id="d5806-303">Specifies the GC heap usage as a percentage of the total memory.</span></span>

| | <span data-ttu-id="d5806-304">设置名</span><span class="sxs-lookup"><span data-stu-id="d5806-304">Setting name</span></span> | <span data-ttu-id="d5806-305">值</span><span class="sxs-lookup"><span data-stu-id="d5806-305">Values</span></span> | <span data-ttu-id="d5806-306">引入的版本</span><span class="sxs-lookup"><span data-stu-id="d5806-306">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d5806-307">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d5806-307">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="d5806-308">十进制值 </span><span class="sxs-lookup"><span data-stu-id="d5806-308">*decimal value*</span></span> | <span data-ttu-id="d5806-309">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d5806-309">.NET Core 3.0</span></span> |
| <span data-ttu-id="d5806-310">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="d5806-310">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="d5806-311">十六进制值 </span><span class="sxs-lookup"><span data-stu-id="d5806-311">*hexadecimal value*</span></span> | <span data-ttu-id="d5806-312">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d5806-312">.NET Core 3.0</span></span> |

<span data-ttu-id="d5806-313">示例：</span><span class="sxs-lookup"><span data-stu-id="d5806-313">Example:</span></span>

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
> <span data-ttu-id="d5806-314">如果要在 runtimeconfig.template.json  中设置该选项，请指定一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="d5806-314">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="d5806-315">如果要将选项设置为一个环境变量，请指定一个十六进制值。</span><span class="sxs-lookup"><span data-stu-id="d5806-315">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="d5806-316">例如，若要将堆使用率限制为 30%，则该值对于 JSON 文件为 30，对于环境变量则为 0x1E 或 1E。</span><span class="sxs-lookup"><span data-stu-id="d5806-316">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="d5806-317">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="d5806-317">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="d5806-318">配置是将应删除的段置于备用列表上供将来使用，还是将其释放回操作系统 (OS)。</span><span class="sxs-lookup"><span data-stu-id="d5806-318">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="d5806-319">默认：将段释放回操作系统 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="d5806-319">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="d5806-320">设置名</span><span class="sxs-lookup"><span data-stu-id="d5806-320">Setting name</span></span> | <span data-ttu-id="d5806-321">值</span><span class="sxs-lookup"><span data-stu-id="d5806-321">Values</span></span> | <span data-ttu-id="d5806-322">引入的版本</span><span class="sxs-lookup"><span data-stu-id="d5806-322">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d5806-323">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d5806-323">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="d5806-324">`false` - 释放到 OS</span><span class="sxs-lookup"><span data-stu-id="d5806-324">`false` - release to OS</span></span><br/><span data-ttu-id="d5806-325">`true` - 置于备用列表上</span><span class="sxs-lookup"><span data-stu-id="d5806-325">`true` - put on standby</span></span> | <span data-ttu-id="d5806-326">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d5806-326">.NET Core 1.0</span></span> |
| <span data-ttu-id="d5806-327">MSBuild 属性 </span><span class="sxs-lookup"><span data-stu-id="d5806-327">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="d5806-328">`false` - 释放到 OS</span><span class="sxs-lookup"><span data-stu-id="d5806-328">`false` - release to OS</span></span><br/><span data-ttu-id="d5806-329">`true` - 置于备用列表上</span><span class="sxs-lookup"><span data-stu-id="d5806-329">`true` - put on standby</span></span> | <span data-ttu-id="d5806-330">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d5806-330">.NET Core 1.0</span></span> |
| <span data-ttu-id="d5806-331">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="d5806-331">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="d5806-332">`0` - 释放到 OS</span><span class="sxs-lookup"><span data-stu-id="d5806-332">`0` - release to OS</span></span><br/><span data-ttu-id="d5806-333">`1` - 置于备用列表上</span><span class="sxs-lookup"><span data-stu-id="d5806-333">`1` - put on standby</span></span> | <span data-ttu-id="d5806-334">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d5806-334">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="d5806-335">示例</span><span class="sxs-lookup"><span data-stu-id="d5806-335">Examples</span></span>

<span data-ttu-id="d5806-336">runtimeconfig.json 文件： </span><span class="sxs-lookup"><span data-stu-id="d5806-336">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="d5806-337">项目文件：</span><span class="sxs-lookup"><span data-stu-id="d5806-337">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="d5806-338">大型页面</span><span class="sxs-lookup"><span data-stu-id="d5806-338">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="d5806-339">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="d5806-339">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="d5806-340">指定设置堆硬限制时是否应使用大型页面。</span><span class="sxs-lookup"><span data-stu-id="d5806-340">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="d5806-341">默认：禁用 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="d5806-341">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="d5806-342">这是一项实验性设置。</span><span class="sxs-lookup"><span data-stu-id="d5806-342">This is an experimental setting.</span></span>

| | <span data-ttu-id="d5806-343">设置名</span><span class="sxs-lookup"><span data-stu-id="d5806-343">Setting name</span></span> | <span data-ttu-id="d5806-344">值</span><span class="sxs-lookup"><span data-stu-id="d5806-344">Values</span></span> | <span data-ttu-id="d5806-345">引入的版本</span><span class="sxs-lookup"><span data-stu-id="d5806-345">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d5806-346">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d5806-346">**runtimeconfig.json**</span></span> | <span data-ttu-id="d5806-347">不可用</span><span class="sxs-lookup"><span data-stu-id="d5806-347">N/A</span></span> | <span data-ttu-id="d5806-348">不可用</span><span class="sxs-lookup"><span data-stu-id="d5806-348">N/A</span></span> | <span data-ttu-id="d5806-349">不可用</span><span class="sxs-lookup"><span data-stu-id="d5806-349">N/A</span></span> |
| <span data-ttu-id="d5806-350">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="d5806-350">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="d5806-351">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="d5806-351">`0` - disabled</span></span><br/><span data-ttu-id="d5806-352">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="d5806-352">`1` - enabled</span></span> | <span data-ttu-id="d5806-353">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d5806-353">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="d5806-354">大型对象</span><span class="sxs-lookup"><span data-stu-id="d5806-354">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="d5806-355">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="d5806-355">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="d5806-356">在 64 位平台上，为总大小大于 2 千兆字节 (GB) 的数组配置垃圾回收器支持。</span><span class="sxs-lookup"><span data-stu-id="d5806-356">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="d5806-357">默认：启用 (`1`)。</span><span class="sxs-lookup"><span data-stu-id="d5806-357">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="d5806-358">在未来的 .NET 版本中，此选项可能会过时。</span><span class="sxs-lookup"><span data-stu-id="d5806-358">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="d5806-359">设置名</span><span class="sxs-lookup"><span data-stu-id="d5806-359">Setting name</span></span> | <span data-ttu-id="d5806-360">值</span><span class="sxs-lookup"><span data-stu-id="d5806-360">Values</span></span> | <span data-ttu-id="d5806-361">引入的版本</span><span class="sxs-lookup"><span data-stu-id="d5806-361">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d5806-362">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d5806-362">**runtimeconfig.json**</span></span> | <span data-ttu-id="d5806-363">不可用</span><span class="sxs-lookup"><span data-stu-id="d5806-363">N/A</span></span> | <span data-ttu-id="d5806-364">不可用</span><span class="sxs-lookup"><span data-stu-id="d5806-364">N/A</span></span> | <span data-ttu-id="d5806-365">不可用</span><span class="sxs-lookup"><span data-stu-id="d5806-365">N/A</span></span> |
| <span data-ttu-id="d5806-366">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="d5806-366">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="d5806-367">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="d5806-367">`1` - enabled</span></span><br/> <span data-ttu-id="d5806-368">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="d5806-368">`0` - disabled</span></span> | <span data-ttu-id="d5806-369">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d5806-369">.NET Core 1.0</span></span> |
| <span data-ttu-id="d5806-370">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="d5806-370">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d5806-371">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="d5806-371">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="d5806-372">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="d5806-372">`1` - enabled</span></span><br/> <span data-ttu-id="d5806-373">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="d5806-373">`0` - disabled</span></span> | <span data-ttu-id="d5806-374">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="d5806-374">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="d5806-375">大型对象堆阈值</span><span class="sxs-lookup"><span data-stu-id="d5806-375">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="d5806-376">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="d5806-376">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="d5806-377">指定导致对象进入大型对象堆 (LOH) 的阈值大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="d5806-377">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="d5806-378">默认阈值为 85,000 字节。</span><span class="sxs-lookup"><span data-stu-id="d5806-378">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="d5806-379">指定的值必须大于默认阈值。</span><span class="sxs-lookup"><span data-stu-id="d5806-379">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="d5806-380">设置名</span><span class="sxs-lookup"><span data-stu-id="d5806-380">Setting name</span></span> | <span data-ttu-id="d5806-381">值</span><span class="sxs-lookup"><span data-stu-id="d5806-381">Values</span></span> | <span data-ttu-id="d5806-382">引入的版本</span><span class="sxs-lookup"><span data-stu-id="d5806-382">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d5806-383">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d5806-383">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="d5806-384">十进制值 </span><span class="sxs-lookup"><span data-stu-id="d5806-384">*decimal value*</span></span> | <span data-ttu-id="d5806-385">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d5806-385">.NET Core 1.0</span></span> |
| <span data-ttu-id="d5806-386">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="d5806-386">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="d5806-387">十六进制值 </span><span class="sxs-lookup"><span data-stu-id="d5806-387">*hexadecimal value*</span></span> | <span data-ttu-id="d5806-388">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d5806-388">.NET Core 1.0</span></span> |
| <span data-ttu-id="d5806-389">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="d5806-389">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d5806-390">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="d5806-390">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="d5806-391">十进制值 </span><span class="sxs-lookup"><span data-stu-id="d5806-391">*decimal value*</span></span> | <span data-ttu-id="d5806-392">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="d5806-392">.NET Framework 4.8</span></span> |

<span data-ttu-id="d5806-393">示例：</span><span class="sxs-lookup"><span data-stu-id="d5806-393">Example:</span></span>

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
> <span data-ttu-id="d5806-394">如果要在 runtimeconfig.template.json  中设置该选项，请指定一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="d5806-394">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="d5806-395">如果要将选项设置为一个环境变量，请指定一个十六进制值。</span><span class="sxs-lookup"><span data-stu-id="d5806-395">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="d5806-396">例如，若要将阙值大小设置为 120,000 个字节，则该值对于 JSON 文件为 120,000，对于环境变量则为 0x1D4C0 或 1D4C0。</span><span class="sxs-lookup"><span data-stu-id="d5806-396">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="d5806-397">独立 GC</span><span class="sxs-lookup"><span data-stu-id="d5806-397">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="d5806-398">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="d5806-398">COMPlus_GCName</span></span>

- <span data-ttu-id="d5806-399">指定库的路径，该库包含运行时打算加载的垃圾回收器。</span><span class="sxs-lookup"><span data-stu-id="d5806-399">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="d5806-400">有关详细信息，请参阅 [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md)（独立 GC 加载程序设计）。</span><span class="sxs-lookup"><span data-stu-id="d5806-400">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="d5806-401">设置名</span><span class="sxs-lookup"><span data-stu-id="d5806-401">Setting name</span></span> | <span data-ttu-id="d5806-402">值</span><span class="sxs-lookup"><span data-stu-id="d5806-402">Values</span></span> | <span data-ttu-id="d5806-403">引入的版本</span><span class="sxs-lookup"><span data-stu-id="d5806-403">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d5806-404">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d5806-404">**runtimeconfig.json**</span></span> | <span data-ttu-id="d5806-405">不可用</span><span class="sxs-lookup"><span data-stu-id="d5806-405">N/A</span></span> | <span data-ttu-id="d5806-406">不可用</span><span class="sxs-lookup"><span data-stu-id="d5806-406">N/A</span></span> | <span data-ttu-id="d5806-407">不可用</span><span class="sxs-lookup"><span data-stu-id="d5806-407">N/A</span></span> |
| <span data-ttu-id="d5806-408">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="d5806-408">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="d5806-409">string_path </span><span class="sxs-lookup"><span data-stu-id="d5806-409">*string_path*</span></span> | <span data-ttu-id="d5806-410">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="d5806-410">.NET Core 2.0</span></span> |
