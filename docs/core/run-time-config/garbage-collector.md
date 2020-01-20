---
title: 垃圾回收器配置设置
description: 了解用于配置垃圾回收器如何为 .NET Core 应用管理内存的运行时设置。
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: 24e5c47de781e7eed5f76d2c551cac2dce1e8f05
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900099"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="84be3-103">用于垃圾回收的运行时配置选项</span><span class="sxs-lookup"><span data-stu-id="84be3-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="84be3-104">此页包含有关可在运行时更改的垃圾回收器 (GC) 设置的信息。</span><span class="sxs-lookup"><span data-stu-id="84be3-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="84be3-105">如果你要尝试让正在运行的应用达到最佳性能，请考虑使用这些设置。</span><span class="sxs-lookup"><span data-stu-id="84be3-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="84be3-106">然而，在特定情况下，默认值为大多数应用程序提供最佳性能。</span><span class="sxs-lookup"><span data-stu-id="84be3-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="84be3-107">设置在此页上被排入组中。</span><span class="sxs-lookup"><span data-stu-id="84be3-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="84be3-108">每个组内的设置通常彼此结合使用以实现特定的结果。</span><span class="sxs-lookup"><span data-stu-id="84be3-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="84be3-109">这些设置也可以在应用运行时由应用动态地进行更改，因此，你设置的任何运行时设置都可能会被覆盖。</span><span class="sxs-lookup"><span data-stu-id="84be3-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="84be3-110">某些设置（如[延迟级别](../../standard/garbage-collection/latency.md)）通常仅在设计时通过 API 进行设置。</span><span class="sxs-lookup"><span data-stu-id="84be3-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="84be3-111">此页面省略了此类设置。</span><span class="sxs-lookup"><span data-stu-id="84be3-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="84be3-112">对于数值，请对 runtimeconfig.json  文件中的设置使用十进制表示法，而对环境变量设置使用十六进制表示法。</span><span class="sxs-lookup"><span data-stu-id="84be3-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="84be3-113">对于十六进制值，可以使用或不使用“0x”前缀来指定它们。</span><span class="sxs-lookup"><span data-stu-id="84be3-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="84be3-114">垃圾回收的风格</span><span class="sxs-lookup"><span data-stu-id="84be3-114">Flavors of garbage collection</span></span>

<span data-ttu-id="84be3-115">垃圾回收的两种主要风格是工作站 GC 和服务器 GC。</span><span class="sxs-lookup"><span data-stu-id="84be3-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="84be3-116">有关两者之间的差异的详细信息，请参阅[垃圾回收的基础知识](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection)。</span><span class="sxs-lookup"><span data-stu-id="84be3-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="84be3-117">垃圾回收的次要风格是后台垃圾回收和非并发垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="84be3-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="84be3-118">使用以下设置，选择垃圾回收的风格：</span><span class="sxs-lookup"><span data-stu-id="84be3-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="84be3-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="84be3-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="84be3-120">配置应用程序是使用工作站垃圾回收还是服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="84be3-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="84be3-121">默认：工作站垃圾回收 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="84be3-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="84be3-122">设置名</span><span class="sxs-lookup"><span data-stu-id="84be3-122">Setting name</span></span> | <span data-ttu-id="84be3-123">值</span><span class="sxs-lookup"><span data-stu-id="84be3-123">Values</span></span> | <span data-ttu-id="84be3-124">引入的版本</span><span class="sxs-lookup"><span data-stu-id="84be3-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="84be3-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="84be3-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="84be3-126">`false` - 工作站</span><span class="sxs-lookup"><span data-stu-id="84be3-126">`false` - workstation</span></span><br/><span data-ttu-id="84be3-127">`true` - 服务器</span><span class="sxs-lookup"><span data-stu-id="84be3-127">`true` - server</span></span> | <span data-ttu-id="84be3-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="84be3-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="84be3-129">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="84be3-129">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="84be3-130">`0` - 工作站</span><span class="sxs-lookup"><span data-stu-id="84be3-130">`0` - workstation</span></span><br/><span data-ttu-id="84be3-131">`1` - 服务器</span><span class="sxs-lookup"><span data-stu-id="84be3-131">`1` - server</span></span> | <span data-ttu-id="84be3-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="84be3-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="84be3-133">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="84be3-133">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="84be3-134">GCServer</span><span class="sxs-lookup"><span data-stu-id="84be3-134">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="84be3-135">`false` - 工作站</span><span class="sxs-lookup"><span data-stu-id="84be3-135">`false` - workstation</span></span><br/><span data-ttu-id="84be3-136">`true` - 服务器</span><span class="sxs-lookup"><span data-stu-id="84be3-136">`true` - server</span></span> |  |

<span data-ttu-id="84be3-137">示例：</span><span class="sxs-lookup"><span data-stu-id="84be3-137">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="84be3-138">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="84be3-138">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="84be3-139">配置是否启用后台（并发）垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="84be3-139">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="84be3-140">默认：启用 (`true`)。</span><span class="sxs-lookup"><span data-stu-id="84be3-140">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="84be3-141">有关详细信息，请参阅[后台垃圾回收](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection)和[后台服务器垃圾回收](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection)。</span><span class="sxs-lookup"><span data-stu-id="84be3-141">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="84be3-142">设置名</span><span class="sxs-lookup"><span data-stu-id="84be3-142">Setting name</span></span> | <span data-ttu-id="84be3-143">值</span><span class="sxs-lookup"><span data-stu-id="84be3-143">Values</span></span> | <span data-ttu-id="84be3-144">引入的版本</span><span class="sxs-lookup"><span data-stu-id="84be3-144">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="84be3-145">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="84be3-145">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="84be3-146">`true` - 后台 GC</span><span class="sxs-lookup"><span data-stu-id="84be3-146">`true` - background GC</span></span><br/><span data-ttu-id="84be3-147">`false` - 非并发 GC</span><span class="sxs-lookup"><span data-stu-id="84be3-147">`false` - non-concurrent GC</span></span> | <span data-ttu-id="84be3-148">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="84be3-148">.NET Core 1.0</span></span> |
| <span data-ttu-id="84be3-149">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="84be3-149">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="84be3-150">`true` - 后台 GC</span><span class="sxs-lookup"><span data-stu-id="84be3-150">`true` - background GC</span></span><br/><span data-ttu-id="84be3-151">`false` - 非并发 GC</span><span class="sxs-lookup"><span data-stu-id="84be3-151">`false` - non-concurrent GC</span></span> | <span data-ttu-id="84be3-152">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="84be3-152">.NET Core 1.0</span></span> |
| <span data-ttu-id="84be3-153">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="84be3-153">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="84be3-154">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="84be3-154">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="84be3-155">`true` - 后台 GC</span><span class="sxs-lookup"><span data-stu-id="84be3-155">`true` - background GC</span></span><br/><span data-ttu-id="84be3-156">`false` - 非并发 GC</span><span class="sxs-lookup"><span data-stu-id="84be3-156">`false` - non-concurrent GC</span></span> |  |

<span data-ttu-id="84be3-157">示例：</span><span class="sxs-lookup"><span data-stu-id="84be3-157">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

## <a name="manage-resource-usage"></a><span data-ttu-id="84be3-158">管理资源使用情况</span><span class="sxs-lookup"><span data-stu-id="84be3-158">Manage resource usage</span></span>

<span data-ttu-id="84be3-159">使用此部分中所述的设置，管理垃圾回收器的内存和处理器使用情况。</span><span class="sxs-lookup"><span data-stu-id="84be3-159">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="84be3-160">有关其中某些设置的详细信息，请参阅 [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/)（服务器和工作站 GC 之间的中间地带）博客条目。</span><span class="sxs-lookup"><span data-stu-id="84be3-160">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="84be3-161">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="84be3-161">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="84be3-162">限制通过垃圾回收器创建的堆数。</span><span class="sxs-lookup"><span data-stu-id="84be3-162">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="84be3-163">仅适用于服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="84be3-163">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="84be3-164">如果启用了默认的 GC 处理器关联，堆计数设置会将 `n` 个 GC 堆/线程关联到前 `n` 个处理器。</span><span class="sxs-lookup"><span data-stu-id="84be3-164">If GC processor affinity is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="84be3-165">（使用关联掩码或关联范围设置来精确指定要关联的处理器。）</span><span class="sxs-lookup"><span data-stu-id="84be3-165">(Use the affinitize mask or affinitize ranges settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="84be3-166">如果禁用了 GC 处理器关联，则此设置会限制 GC 堆的数量。</span><span class="sxs-lookup"><span data-stu-id="84be3-166">If GC processor affinity is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="84be3-167">有关详细信息，请参阅 [GCHeapCount 备注](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks)。</span><span class="sxs-lookup"><span data-stu-id="84be3-167">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="84be3-168">设置名</span><span class="sxs-lookup"><span data-stu-id="84be3-168">Setting name</span></span> | <span data-ttu-id="84be3-169">值</span><span class="sxs-lookup"><span data-stu-id="84be3-169">Values</span></span> | <span data-ttu-id="84be3-170">引入的版本</span><span class="sxs-lookup"><span data-stu-id="84be3-170">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="84be3-171">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="84be3-171">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="84be3-172">十进制值 </span><span class="sxs-lookup"><span data-stu-id="84be3-172">*decimal value*</span></span> | <span data-ttu-id="84be3-173">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="84be3-173">.NET Core 3.0</span></span> |
| <span data-ttu-id="84be3-174">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="84be3-174">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="84be3-175">十六进制值 </span><span class="sxs-lookup"><span data-stu-id="84be3-175">*hexadecimal value*</span></span> | <span data-ttu-id="84be3-176">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="84be3-176">.NET Core 3.0</span></span> |
| <span data-ttu-id="84be3-177">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="84be3-177">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="84be3-178">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="84be3-178">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="84be3-179">十进制值 </span><span class="sxs-lookup"><span data-stu-id="84be3-179">*decimal value*</span></span> | <span data-ttu-id="84be3-180">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="84be3-180">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="84be3-181">示例：</span><span class="sxs-lookup"><span data-stu-id="84be3-181">Example:</span></span>

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
> <span data-ttu-id="84be3-182">如果要在 runtimeconfig.template.json  中设置该选项，请指定一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="84be3-182">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="84be3-183">如果要将选项设置为一个环境变量，请指定一个十六进制值。</span><span class="sxs-lookup"><span data-stu-id="84be3-183">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="84be3-184">例如，若要将堆数限制为 16，则该值对于 JSON 文件为 16，对于环境变量则为 0x10 或 10。</span><span class="sxs-lookup"><span data-stu-id="84be3-184">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="84be3-185">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="84be3-185">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="84be3-186">指定垃圾回收器线程应使用的确切处理器数。</span><span class="sxs-lookup"><span data-stu-id="84be3-186">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="84be3-187">如果通过将 `System.GC.NoAffinitize` 设置为 `true` 禁用了处理器关联，则忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="84be3-187">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="84be3-188">仅适用于服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="84be3-188">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="84be3-189">该值是一个位掩码，用于定义可用于该进程的处理器。</span><span class="sxs-lookup"><span data-stu-id="84be3-189">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="84be3-190">例如，十进制值 1023 或十六进制值 0x3FF 或 3FF（如果使用环境变量）在二进制记数法中为 0011 1111 1111。</span><span class="sxs-lookup"><span data-stu-id="84be3-190">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="84be3-191">这指定将使用前 10 个处理器。</span><span class="sxs-lookup"><span data-stu-id="84be3-191">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="84be3-192">若要指定接下来使用的 10 个处理器（即处理器 10-19），请指定一个十进制值 1047552（或十六进制值 0xFFC00 或 FFC00），它等效于二进制值 1111 1111 1100 0000 0000。</span><span class="sxs-lookup"><span data-stu-id="84be3-192">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="84be3-193">设置名</span><span class="sxs-lookup"><span data-stu-id="84be3-193">Setting name</span></span> | <span data-ttu-id="84be3-194">值</span><span class="sxs-lookup"><span data-stu-id="84be3-194">Values</span></span> | <span data-ttu-id="84be3-195">引入的版本</span><span class="sxs-lookup"><span data-stu-id="84be3-195">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="84be3-196">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="84be3-196">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="84be3-197">十进制值 </span><span class="sxs-lookup"><span data-stu-id="84be3-197">*decimal value*</span></span> | <span data-ttu-id="84be3-198">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="84be3-198">.NET Core 3.0</span></span> |
| <span data-ttu-id="84be3-199">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="84be3-199">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="84be3-200">十六进制值 </span><span class="sxs-lookup"><span data-stu-id="84be3-200">*hexadecimal value*</span></span> | <span data-ttu-id="84be3-201">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="84be3-201">.NET Core 3.0</span></span> |
| <span data-ttu-id="84be3-202">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="84be3-202">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="84be3-203">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="84be3-203">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="84be3-204">十进制值 </span><span class="sxs-lookup"><span data-stu-id="84be3-204">*decimal value*</span></span> | <span data-ttu-id="84be3-205">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="84be3-205">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="84be3-206">示例：</span><span class="sxs-lookup"><span data-stu-id="84be3-206">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="84be3-207">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="84be3-207">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="84be3-208">指定用于垃圾回收器线程的处理器列表。</span><span class="sxs-lookup"><span data-stu-id="84be3-208">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="84be3-209">此设置与 `System.GC.HeapAffinitizeMask` 类似，只是它允许你指定超过 64 个的处理器。</span><span class="sxs-lookup"><span data-stu-id="84be3-209">This setting is similar to `System.GC.HeapAffinitizeMask`, except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="84be3-210">对于 Windows 操作系统，请为处理器编号或范围加上相应的 [CPU 组](/windows/win32/procthread/processor-groups)作为前缀，例如“0:1-10,0:12,1:50-52,1:70”。</span><span class="sxs-lookup"><span data-stu-id="84be3-210">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="84be3-211">如果通过将 `System.GC.NoAffinitize` 设置为 `true` 禁用了处理器关联，则忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="84be3-211">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="84be3-212">仅适用于服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="84be3-212">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="84be3-213">有关详细信息，请参阅 Maoni Stephens 的博客文章 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)（在 CPU 大于 64 个的计算机上，为 GC 提供更好的 CPU 配置）。</span><span class="sxs-lookup"><span data-stu-id="84be3-213">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="84be3-214">设置名</span><span class="sxs-lookup"><span data-stu-id="84be3-214">Setting name</span></span> | <span data-ttu-id="84be3-215">值</span><span class="sxs-lookup"><span data-stu-id="84be3-215">Values</span></span> | <span data-ttu-id="84be3-216">引入的版本</span><span class="sxs-lookup"><span data-stu-id="84be3-216">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="84be3-217">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="84be3-217">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="84be3-218">以逗号分隔的处理器编号列表或处理器编号范围。</span><span class="sxs-lookup"><span data-stu-id="84be3-218">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="84be3-219">Unix 示例：“1-10,12,50-52,70”</span><span class="sxs-lookup"><span data-stu-id="84be3-219">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="84be3-220">Windows 示例：“0:1-10,0:12,1:50-52,1:70”</span><span class="sxs-lookup"><span data-stu-id="84be3-220">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="84be3-221">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="84be3-221">.NET Core 3.0</span></span> |
| <span data-ttu-id="84be3-222">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="84be3-222">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="84be3-223">以逗号分隔的处理器编号列表或处理器编号范围。</span><span class="sxs-lookup"><span data-stu-id="84be3-223">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="84be3-224">Unix 示例：“1-10,12,50-52,70”</span><span class="sxs-lookup"><span data-stu-id="84be3-224">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="84be3-225">Windows 示例：“0:1-10,0:12,1:50-52,1:70”</span><span class="sxs-lookup"><span data-stu-id="84be3-225">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="84be3-226">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="84be3-226">.NET Core 3.0</span></span> |

<span data-ttu-id="84be3-227">示例：</span><span class="sxs-lookup"><span data-stu-id="84be3-227">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="84be3-228">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="84be3-228">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="84be3-229">配置垃圾回收器是否使用 [CPU 组](/windows/win32/procthread/processor-groups)。</span><span class="sxs-lookup"><span data-stu-id="84be3-229">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="84be3-230">当 64 位 Windows 计算机具有多个 CPU 组（即，有超过 64 个处理器）时，通过启用此元素，可跨所有 CPU 组扩展垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="84be3-230">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="84be3-231">垃圾回收器使用所有核心来创建和平衡堆。</span><span class="sxs-lookup"><span data-stu-id="84be3-231">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="84be3-232">仅适用于 64 位 Windows 操作系统上的服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="84be3-232">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="84be3-233">默认：禁用 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="84be3-233">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="84be3-234">有关详细信息，请参阅 Maoni Stephens 的博客文章 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)（在 CPU 大于 64 个的计算机上，为 GC 提供更好的 CPU 配置）。</span><span class="sxs-lookup"><span data-stu-id="84be3-234">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="84be3-235">设置名</span><span class="sxs-lookup"><span data-stu-id="84be3-235">Setting name</span></span> | <span data-ttu-id="84be3-236">值</span><span class="sxs-lookup"><span data-stu-id="84be3-236">Values</span></span> | <span data-ttu-id="84be3-237">引入的版本</span><span class="sxs-lookup"><span data-stu-id="84be3-237">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="84be3-238">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="84be3-238">**runtimeconfig.json**</span></span> | <span data-ttu-id="84be3-239">不可用</span><span class="sxs-lookup"><span data-stu-id="84be3-239">N/A</span></span> | <span data-ttu-id="84be3-240">不可用</span><span class="sxs-lookup"><span data-stu-id="84be3-240">N/A</span></span> | <span data-ttu-id="84be3-241">不可用</span><span class="sxs-lookup"><span data-stu-id="84be3-241">N/A</span></span> |
| <span data-ttu-id="84be3-242">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="84be3-242">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="84be3-243">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="84be3-243">`0` - disabled</span></span><br/><span data-ttu-id="84be3-244">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="84be3-244">`1` - enabled</span></span> | <span data-ttu-id="84be3-245">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="84be3-245">.NET Core 1.0</span></span> |
| <span data-ttu-id="84be3-246">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="84be3-246">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="84be3-247">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="84be3-247">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="84be3-248">`false` - 禁用</span><span class="sxs-lookup"><span data-stu-id="84be3-248">`false` - disabled</span></span><br/><span data-ttu-id="84be3-249">`true` - 启用</span><span class="sxs-lookup"><span data-stu-id="84be3-249">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="84be3-250">若要配置公共语言运行时 (CLR)，使其也在所有 CPU 组之间分配线程池中的线程，请启用 [Thread_UseAllCpuGroups 元素](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)选项。</span><span class="sxs-lookup"><span data-stu-id="84be3-250">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="84be3-251">对于 .NET Core 应用，可以通过将 `COMPlus_Thread_UseAllCpuGroups` 环境变量的值设置为 `1` 以启用此选项。</span><span class="sxs-lookup"><span data-stu-id="84be3-251">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="84be3-252">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="84be3-252">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="84be3-253">指定是否将垃圾回收线程与处理器关联  。</span><span class="sxs-lookup"><span data-stu-id="84be3-253">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="84be3-254">若要关联一个 GC 线程，则意味着它只能在其特定的 CPU 上运行。</span><span class="sxs-lookup"><span data-stu-id="84be3-254">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="84be3-255">为每个 GC 线程创建一个堆。</span><span class="sxs-lookup"><span data-stu-id="84be3-255">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="84be3-256">仅适用于服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="84be3-256">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="84be3-257">默认：将垃圾回收线程与处理器关联 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="84be3-257">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="84be3-258">设置名</span><span class="sxs-lookup"><span data-stu-id="84be3-258">Setting name</span></span> | <span data-ttu-id="84be3-259">值</span><span class="sxs-lookup"><span data-stu-id="84be3-259">Values</span></span> | <span data-ttu-id="84be3-260">引入的版本</span><span class="sxs-lookup"><span data-stu-id="84be3-260">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="84be3-261">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="84be3-261">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="84be3-262">`false` - 关联</span><span class="sxs-lookup"><span data-stu-id="84be3-262">`false` - affinitize</span></span><br/><span data-ttu-id="84be3-263">`true` - 不关联</span><span class="sxs-lookup"><span data-stu-id="84be3-263">`true` - don't affinitize</span></span> | <span data-ttu-id="84be3-264">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="84be3-264">.NET Core 3.0</span></span> |
| <span data-ttu-id="84be3-265">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="84be3-265">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="84be3-266">`0` - 关联</span><span class="sxs-lookup"><span data-stu-id="84be3-266">`0` - affinitize</span></span><br/><span data-ttu-id="84be3-267">`1` - 不关联</span><span class="sxs-lookup"><span data-stu-id="84be3-267">`1` - don't affinitize</span></span> | <span data-ttu-id="84be3-268">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="84be3-268">.NET Core 3.0</span></span> |
| <span data-ttu-id="84be3-269">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="84be3-269">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="84be3-270">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="84be3-270">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="84be3-271">`false` - 关联</span><span class="sxs-lookup"><span data-stu-id="84be3-271">`false` - affinitize</span></span><br/><span data-ttu-id="84be3-272">`true` - 不关联</span><span class="sxs-lookup"><span data-stu-id="84be3-272">`true` - don't affinitize</span></span> | <span data-ttu-id="84be3-273">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="84be3-273">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="84be3-274">示例：</span><span class="sxs-lookup"><span data-stu-id="84be3-274">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="84be3-275">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="84be3-275">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="84be3-276">指定 GC 堆和 GC 簿记的最大提交大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="84be3-276">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>

| | <span data-ttu-id="84be3-277">设置名</span><span class="sxs-lookup"><span data-stu-id="84be3-277">Setting name</span></span> | <span data-ttu-id="84be3-278">值</span><span class="sxs-lookup"><span data-stu-id="84be3-278">Values</span></span> | <span data-ttu-id="84be3-279">引入的版本</span><span class="sxs-lookup"><span data-stu-id="84be3-279">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="84be3-280">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="84be3-280">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="84be3-281">十进制值 </span><span class="sxs-lookup"><span data-stu-id="84be3-281">*decimal value*</span></span> | <span data-ttu-id="84be3-282">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="84be3-282">.NET Core 3.0</span></span> |
| <span data-ttu-id="84be3-283">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="84be3-283">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="84be3-284">十六进制值 </span><span class="sxs-lookup"><span data-stu-id="84be3-284">*hexadecimal value*</span></span> | <span data-ttu-id="84be3-285">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="84be3-285">.NET Core 3.0</span></span> |

<span data-ttu-id="84be3-286">示例：</span><span class="sxs-lookup"><span data-stu-id="84be3-286">Example:</span></span>

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
> <span data-ttu-id="84be3-287">如果要在 runtimeconfig.template.json  中设置该选项，请指定一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="84be3-287">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="84be3-288">如果要将选项设置为一个环境变量，请指定一个十六进制值。</span><span class="sxs-lookup"><span data-stu-id="84be3-288">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="84be3-289">例如，若要将堆硬限制指定为 200 个兆字节 (MiB)，则该值对于 JSON 文件为 209715200，对于环境变量则为 0xC800000 或 C800000。</span><span class="sxs-lookup"><span data-stu-id="84be3-289">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="84be3-290">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="84be3-290">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="84be3-291">指定 GC 堆使用量占总内存的百分比。</span><span class="sxs-lookup"><span data-stu-id="84be3-291">Specifies the GC heap usage as a percentage of the total memory.</span></span>

| | <span data-ttu-id="84be3-292">设置名</span><span class="sxs-lookup"><span data-stu-id="84be3-292">Setting name</span></span> | <span data-ttu-id="84be3-293">值</span><span class="sxs-lookup"><span data-stu-id="84be3-293">Values</span></span> | <span data-ttu-id="84be3-294">引入的版本</span><span class="sxs-lookup"><span data-stu-id="84be3-294">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="84be3-295">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="84be3-295">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="84be3-296">十进制值 </span><span class="sxs-lookup"><span data-stu-id="84be3-296">*decimal value*</span></span> | <span data-ttu-id="84be3-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="84be3-297">.NET Core 3.0</span></span> |
| <span data-ttu-id="84be3-298">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="84be3-298">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="84be3-299">十六进制值 </span><span class="sxs-lookup"><span data-stu-id="84be3-299">*hexadecimal value*</span></span> | <span data-ttu-id="84be3-300">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="84be3-300">.NET Core 3.0</span></span> |

<span data-ttu-id="84be3-301">示例：</span><span class="sxs-lookup"><span data-stu-id="84be3-301">Example:</span></span>

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
> <span data-ttu-id="84be3-302">如果要在 runtimeconfig.template.json  中设置该选项，请指定一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="84be3-302">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="84be3-303">如果要将选项设置为一个环境变量，请指定一个十六进制值。</span><span class="sxs-lookup"><span data-stu-id="84be3-303">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="84be3-304">例如，若要将堆使用率限制为 30%，则该值对于 JSON 文件为 30，对于环境变量则为 0x1E 或 1E。</span><span class="sxs-lookup"><span data-stu-id="84be3-304">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="84be3-305">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="84be3-305">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="84be3-306">配置是将应删除的段置于备用列表上供将来使用，还是将其释放回操作系统 (OS)。</span><span class="sxs-lookup"><span data-stu-id="84be3-306">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="84be3-307">默认：将段释放回操作系统 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="84be3-307">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="84be3-308">设置名</span><span class="sxs-lookup"><span data-stu-id="84be3-308">Setting name</span></span> | <span data-ttu-id="84be3-309">值</span><span class="sxs-lookup"><span data-stu-id="84be3-309">Values</span></span> | <span data-ttu-id="84be3-310">引入的版本</span><span class="sxs-lookup"><span data-stu-id="84be3-310">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="84be3-311">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="84be3-311">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="84be3-312">`false` - 释放到 OS</span><span class="sxs-lookup"><span data-stu-id="84be3-312">`false` - release to OS</span></span><br/><span data-ttu-id="84be3-313">`true` - 置于备用列表上</span><span class="sxs-lookup"><span data-stu-id="84be3-313">`true` - put on standby</span></span>| <span data-ttu-id="84be3-314">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="84be3-314">.NET Core 1.0</span></span> |
| <span data-ttu-id="84be3-315">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="84be3-315">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="84be3-316">`0` - 释放到 OS</span><span class="sxs-lookup"><span data-stu-id="84be3-316">`0` - release to OS</span></span><br/><span data-ttu-id="84be3-317">`1` - 置于备用列表上</span><span class="sxs-lookup"><span data-stu-id="84be3-317">`1` - put on standby</span></span> | <span data-ttu-id="84be3-318">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="84be3-318">.NET Core 1.0</span></span> |

<span data-ttu-id="84be3-319">示例：</span><span class="sxs-lookup"><span data-stu-id="84be3-319">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

## <a name="large-pages"></a><span data-ttu-id="84be3-320">大型页面</span><span class="sxs-lookup"><span data-stu-id="84be3-320">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="84be3-321">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="84be3-321">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="84be3-322">指定设置堆硬限制时是否应使用大型页面。</span><span class="sxs-lookup"><span data-stu-id="84be3-322">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="84be3-323">默认：禁用 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="84be3-323">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="84be3-324">这是一项实验性设置。</span><span class="sxs-lookup"><span data-stu-id="84be3-324">This is an experimental setting.</span></span>

| | <span data-ttu-id="84be3-325">设置名</span><span class="sxs-lookup"><span data-stu-id="84be3-325">Setting name</span></span> | <span data-ttu-id="84be3-326">值</span><span class="sxs-lookup"><span data-stu-id="84be3-326">Values</span></span> | <span data-ttu-id="84be3-327">引入的版本</span><span class="sxs-lookup"><span data-stu-id="84be3-327">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="84be3-328">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="84be3-328">**runtimeconfig.json**</span></span> | <span data-ttu-id="84be3-329">不可用</span><span class="sxs-lookup"><span data-stu-id="84be3-329">N/A</span></span> | <span data-ttu-id="84be3-330">不可用</span><span class="sxs-lookup"><span data-stu-id="84be3-330">N/A</span></span> | <span data-ttu-id="84be3-331">不可用</span><span class="sxs-lookup"><span data-stu-id="84be3-331">N/A</span></span> |
| <span data-ttu-id="84be3-332">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="84be3-332">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="84be3-333">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="84be3-333">`0` - disabled</span></span><br/><span data-ttu-id="84be3-334">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="84be3-334">`1` - enabled</span></span> | <span data-ttu-id="84be3-335">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="84be3-335">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="84be3-336">大型对象</span><span class="sxs-lookup"><span data-stu-id="84be3-336">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="84be3-337">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="84be3-337">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="84be3-338">在 64 位平台上，为总大小大于 2 千兆字节 (GB) 的数组配置垃圾回收器支持。</span><span class="sxs-lookup"><span data-stu-id="84be3-338">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="84be3-339">默认：启用 (`1`)。</span><span class="sxs-lookup"><span data-stu-id="84be3-339">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="84be3-340">在未来的 .NET 版本中，此选项可能会过时。</span><span class="sxs-lookup"><span data-stu-id="84be3-340">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="84be3-341">设置名</span><span class="sxs-lookup"><span data-stu-id="84be3-341">Setting name</span></span> | <span data-ttu-id="84be3-342">值</span><span class="sxs-lookup"><span data-stu-id="84be3-342">Values</span></span> | <span data-ttu-id="84be3-343">引入的版本</span><span class="sxs-lookup"><span data-stu-id="84be3-343">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="84be3-344">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="84be3-344">**runtimeconfig.json**</span></span> | <span data-ttu-id="84be3-345">不可用</span><span class="sxs-lookup"><span data-stu-id="84be3-345">N/A</span></span> | <span data-ttu-id="84be3-346">不可用</span><span class="sxs-lookup"><span data-stu-id="84be3-346">N/A</span></span> | <span data-ttu-id="84be3-347">不可用</span><span class="sxs-lookup"><span data-stu-id="84be3-347">N/A</span></span> |
| <span data-ttu-id="84be3-348">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="84be3-348">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="84be3-349">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="84be3-349">`1` - enabled</span></span><br/> <span data-ttu-id="84be3-350">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="84be3-350">`0` - disabled</span></span> | <span data-ttu-id="84be3-351">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="84be3-351">.NET Core 1.0</span></span> |
| <span data-ttu-id="84be3-352">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="84be3-352">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="84be3-353">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="84be3-353">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="84be3-354">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="84be3-354">`1` - enabled</span></span><br/> <span data-ttu-id="84be3-355">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="84be3-355">`0` - disabled</span></span> | <span data-ttu-id="84be3-356">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="84be3-356">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="84be3-357">大型对象堆阈值</span><span class="sxs-lookup"><span data-stu-id="84be3-357">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="84be3-358">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="84be3-358">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="84be3-359">指定导致对象进入大型对象堆 (LOH) 的阈值大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="84be3-359">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="84be3-360">默认阈值为 85,000 字节。</span><span class="sxs-lookup"><span data-stu-id="84be3-360">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="84be3-361">指定的值必须大于默认阈值。</span><span class="sxs-lookup"><span data-stu-id="84be3-361">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="84be3-362">设置名</span><span class="sxs-lookup"><span data-stu-id="84be3-362">Setting name</span></span> | <span data-ttu-id="84be3-363">值</span><span class="sxs-lookup"><span data-stu-id="84be3-363">Values</span></span> | <span data-ttu-id="84be3-364">引入的版本</span><span class="sxs-lookup"><span data-stu-id="84be3-364">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="84be3-365">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="84be3-365">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="84be3-366">十进制值 </span><span class="sxs-lookup"><span data-stu-id="84be3-366">*decimal value*</span></span> | <span data-ttu-id="84be3-367">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="84be3-367">.NET Core 1.0</span></span> |
| <span data-ttu-id="84be3-368">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="84be3-368">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="84be3-369">十六进制值 </span><span class="sxs-lookup"><span data-stu-id="84be3-369">*hexadecimal value*</span></span> | <span data-ttu-id="84be3-370">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="84be3-370">.NET Core 1.0</span></span> |
| <span data-ttu-id="84be3-371">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="84be3-371">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="84be3-372">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="84be3-372">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="84be3-373">十进制值 </span><span class="sxs-lookup"><span data-stu-id="84be3-373">*decimal value*</span></span> | <span data-ttu-id="84be3-374">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="84be3-374">.NET Framework 4.8</span></span> |

<span data-ttu-id="84be3-375">示例：</span><span class="sxs-lookup"><span data-stu-id="84be3-375">Example:</span></span>

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
> <span data-ttu-id="84be3-376">如果要在 runtimeconfig.template.json  中设置该选项，请指定一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="84be3-376">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="84be3-377">如果要将选项设置为一个环境变量，请指定一个十六进制值。</span><span class="sxs-lookup"><span data-stu-id="84be3-377">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="84be3-378">例如，若要将阙值大小设置为 120,000 个字节，则该值对于 JSON 文件为 120,000，对于环境变量则为 0x1D4C0 或 1D4C0。</span><span class="sxs-lookup"><span data-stu-id="84be3-378">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="84be3-379">独立 GC</span><span class="sxs-lookup"><span data-stu-id="84be3-379">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="84be3-380">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="84be3-380">COMPlus_GCName</span></span>

- <span data-ttu-id="84be3-381">指定库的路径，该库包含运行时打算加载的垃圾回收器。</span><span class="sxs-lookup"><span data-stu-id="84be3-381">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="84be3-382">有关详细信息，请参阅 [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md)（独立 GC 加载程序设计）。</span><span class="sxs-lookup"><span data-stu-id="84be3-382">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="84be3-383">设置名</span><span class="sxs-lookup"><span data-stu-id="84be3-383">Setting name</span></span> | <span data-ttu-id="84be3-384">值</span><span class="sxs-lookup"><span data-stu-id="84be3-384">Values</span></span> | <span data-ttu-id="84be3-385">引入的版本</span><span class="sxs-lookup"><span data-stu-id="84be3-385">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="84be3-386">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="84be3-386">**runtimeconfig.json**</span></span> | <span data-ttu-id="84be3-387">不可用</span><span class="sxs-lookup"><span data-stu-id="84be3-387">N/A</span></span> | <span data-ttu-id="84be3-388">不可用</span><span class="sxs-lookup"><span data-stu-id="84be3-388">N/A</span></span> | <span data-ttu-id="84be3-389">不可用</span><span class="sxs-lookup"><span data-stu-id="84be3-389">N/A</span></span> |
| <span data-ttu-id="84be3-390">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="84be3-390">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="84be3-391">string_path </span><span class="sxs-lookup"><span data-stu-id="84be3-391">*string_path*</span></span> | <span data-ttu-id="84be3-392">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="84be3-392">.NET Core 2.0</span></span> |
