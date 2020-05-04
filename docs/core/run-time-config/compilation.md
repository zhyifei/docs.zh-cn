---
title: 编译配置设置
description: 了解用于为 .NET Core 应用配置 JIT 编译器工作原理的运行时设置。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 4db20ee6d36fe3d3d66f473644b70c02d4e02cb3
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506839"
---
# <a name="run-time-configuration-options-for-compilation"></a><span data-ttu-id="7ac2e-103">用于编译的运行时配置选项</span><span class="sxs-lookup"><span data-stu-id="7ac2e-103">Run-time configuration options for compilation</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="7ac2e-104">分层编译</span><span class="sxs-lookup"><span data-stu-id="7ac2e-104">Tiered compilation</span></span>

- <span data-ttu-id="7ac2e-105">配置实时 (JIT) 编译器是否使用[分层编译](../whats-new/dotnet-core-3-0.md#tiered-compilation)。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-105">Configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="7ac2e-106">分层编译将方法转换到两个层级：</span><span class="sxs-lookup"><span data-stu-id="7ac2e-106">Tiered compilation transitions methods through two tiers:</span></span>
  - <span data-ttu-id="7ac2e-107">第一层可以更快速地生成代码（[快速 JIT](#quick-jit)）或加载预编译的代码 ([ReadyToRun](#readytorun))。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-107">The first tier generates code more quickly ([quick JIT](#quick-jit)) or loads pre-compiled code ([ReadyToRun](#readytorun)).</span></span>
  - <span data-ttu-id="7ac2e-108">第二层在后台生成优化的代码（“优化 JIT”）。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-108">The second tier generates optimized code in the background ("optimizing JIT").</span></span>
- <span data-ttu-id="7ac2e-109">在 NET Core 3.0 及更高版本中，默认情况下已启用分层编译。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-109">In .NET Core 3.0 and later, tiered compilation is enabled by default.</span></span>
- <span data-ttu-id="7ac2e-110">在 NET Core 2.1 和 2.2 中，默认情况下已禁用分层编译。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-110">In .NET Core 2.1 and 2.2, tiered compilation is disabled by default.</span></span>
- <span data-ttu-id="7ac2e-111">有关详细信息，请参阅[分层编译指南](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md)。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-111">For more information, see the [Tiered compilation guide](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md).</span></span>

| | <span data-ttu-id="7ac2e-112">设置名</span><span class="sxs-lookup"><span data-stu-id="7ac2e-112">Setting name</span></span> | <span data-ttu-id="7ac2e-113">值</span><span class="sxs-lookup"><span data-stu-id="7ac2e-113">Values</span></span> |
| - | - | - |
| <span data-ttu-id="7ac2e-114">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="7ac2e-114">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation` | <span data-ttu-id="7ac2e-115">`true` - 启用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-115">`true` - enabled</span></span><br/><span data-ttu-id="7ac2e-116">`false` - 禁用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-116">`false` - disabled</span></span> |
| <span data-ttu-id="7ac2e-117">MSBuild 属性 </span><span class="sxs-lookup"><span data-stu-id="7ac2e-117">**MSBuild property**</span></span> | `TieredCompilation` | <span data-ttu-id="7ac2e-118">`true` - 启用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-118">`true` - enabled</span></span><br/><span data-ttu-id="7ac2e-119">`false` - 禁用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-119">`false` - disabled</span></span> |
| <span data-ttu-id="7ac2e-120">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="7ac2e-120">**Environment variable**</span></span> | `COMPlus_TieredCompilation` | <span data-ttu-id="7ac2e-121">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-121">`1` - enabled</span></span><br/><span data-ttu-id="7ac2e-122">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-122">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="7ac2e-123">示例</span><span class="sxs-lookup"><span data-stu-id="7ac2e-123">Examples</span></span>

<span data-ttu-id="7ac2e-124">runtimeconfig.json 文件： </span><span class="sxs-lookup"><span data-stu-id="7ac2e-124">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation": false
      }
   }
}
```

<span data-ttu-id="7ac2e-125">项目文件：</span><span class="sxs-lookup"><span data-stu-id="7ac2e-125">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit"></a><span data-ttu-id="7ac2e-126">快速 JIT</span><span class="sxs-lookup"><span data-stu-id="7ac2e-126">Quick JIT</span></span>

- <span data-ttu-id="7ac2e-127">配置 JIT 编译器是否使用快速 JIT。 </span><span class="sxs-lookup"><span data-stu-id="7ac2e-127">Configures whether the JIT compiler uses *quick JIT*.</span></span> <span data-ttu-id="7ac2e-128">对于不包含循环且不可使用预编译代码的方法，快速 JIT 可以更快完成编译，但不会进行优化。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-128">For methods that don't contain loops and for which pre-compiled code is not available, quick JIT compiles them more quickly but without optimizations.</span></span>
- <span data-ttu-id="7ac2e-129">启用快速 JIT 会缩短启动时间，但可能会生成性能下降的代码。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-129">Enabling quick JIT decreases startup time but can produce code with degraded performance characteristics.</span></span> <span data-ttu-id="7ac2e-130">例如，代码可能会使用更多堆栈空间、分配更多内存并以更慢的速度运行。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-130">For example, the code may use more stack space, allocate more memory, and run slower.</span></span>
- <span data-ttu-id="7ac2e-131">如果禁用了快速 JIT 但启用了[分层编译](#tiered-compilation)，则只有预编译的代码参与分层编译。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-131">If quick JIT is disabled but [tiered compilation](#tiered-compilation) is enabled, only pre-compiled code participates in tiered compilation.</span></span> <span data-ttu-id="7ac2e-132">如果未使用 [ReadyToRun](#readytorun) 预编译方法，则 JIT 行为与禁用[分层编译](#tiered-compilation)时相同。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-132">If a method is not pre-compiled with [ReadyToRun](#readytorun), the JIT behavior is the same as if [tiered compilation](#tiered-compilation) were disabled.</span></span>
- <span data-ttu-id="7ac2e-133">在 NET Core 3.0 及更高版本中，默认启用快速 JIT。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-133">In .NET Core 3.0 and later, quick JIT is enabled by default.</span></span>
- <span data-ttu-id="7ac2e-134">在 NET Core 2.1 和 2.2 中，默认禁用快速 JIT。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-134">In .NET Core 2.1 and 2.2, quick JIT is disabled by default.</span></span>

| | <span data-ttu-id="7ac2e-135">设置名</span><span class="sxs-lookup"><span data-stu-id="7ac2e-135">Setting name</span></span> | <span data-ttu-id="7ac2e-136">值</span><span class="sxs-lookup"><span data-stu-id="7ac2e-136">Values</span></span> |
| - | - | - |
| <span data-ttu-id="7ac2e-137">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="7ac2e-137">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJit` | <span data-ttu-id="7ac2e-138">`true` - 启用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-138">`true` - enabled</span></span><br/><span data-ttu-id="7ac2e-139">`false` - 禁用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-139">`false` - disabled</span></span> |
| <span data-ttu-id="7ac2e-140">MSBuild 属性 </span><span class="sxs-lookup"><span data-stu-id="7ac2e-140">**MSBuild property**</span></span> | `TieredCompilationQuickJit` | <span data-ttu-id="7ac2e-141">`true` - 启用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-141">`true` - enabled</span></span><br/><span data-ttu-id="7ac2e-142">`false` - 禁用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-142">`false` - disabled</span></span> |
| <span data-ttu-id="7ac2e-143">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="7ac2e-143">**Environment variable**</span></span> | `COMPlus_TC_QuickJit` | <span data-ttu-id="7ac2e-144">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-144">`1` - enabled</span></span><br/><span data-ttu-id="7ac2e-145">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-145">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="7ac2e-146">示例</span><span class="sxs-lookup"><span data-stu-id="7ac2e-146">Examples</span></span>

<span data-ttu-id="7ac2e-147">runtimeconfig.json 文件： </span><span class="sxs-lookup"><span data-stu-id="7ac2e-147">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJit": false
      }
   }
}
```

<span data-ttu-id="7ac2e-148">项目文件：</span><span class="sxs-lookup"><span data-stu-id="7ac2e-148">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit-for-loops"></a><span data-ttu-id="7ac2e-149">适用于循环的快速 JIT</span><span class="sxs-lookup"><span data-stu-id="7ac2e-149">Quick JIT for loops</span></span>

- <span data-ttu-id="7ac2e-150">配置 JIT 编译器是否对包含循环的方法使用快速 JIT。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-150">Configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span>
- <span data-ttu-id="7ac2e-151">启用适用于循环的快速 JIT 可以提高启动性能。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-151">Enabling quick JIT for loops may improve startup performance.</span></span> <span data-ttu-id="7ac2e-152">不过，在优化程度较低的代码中，长时间运行的循环可能会停滞较长时间。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-152">However, long-running loops can get stuck in less-optimized code for long periods.</span></span>
- <span data-ttu-id="7ac2e-153">如果禁用[快速 JIT](#quick-jit)，则此设置不起作用。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-153">If [quick JIT](#quick-jit) is disabled, this setting has no effect.</span></span>
- <span data-ttu-id="7ac2e-154">默认：禁用 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-154">Default: Disabled (`false`).</span></span>

| | <span data-ttu-id="7ac2e-155">设置名</span><span class="sxs-lookup"><span data-stu-id="7ac2e-155">Setting name</span></span> | <span data-ttu-id="7ac2e-156">值</span><span class="sxs-lookup"><span data-stu-id="7ac2e-156">Values</span></span> |
| - | - | - |
| <span data-ttu-id="7ac2e-157">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="7ac2e-157">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJitForLoops` | <span data-ttu-id="7ac2e-158">`false` - 禁用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-158">`false` - disabled</span></span><br/><span data-ttu-id="7ac2e-159">`true` - 启用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-159">`true` - enabled</span></span> |
| <span data-ttu-id="7ac2e-160">MSBuild 属性 </span><span class="sxs-lookup"><span data-stu-id="7ac2e-160">**MSBuild property**</span></span> | `TieredCompilationQuickJitForLoops` | <span data-ttu-id="7ac2e-161">`false` - 禁用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-161">`false` - disabled</span></span><br/><span data-ttu-id="7ac2e-162">`true` - 启用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-162">`true` - enabled</span></span> |
| <span data-ttu-id="7ac2e-163">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="7ac2e-163">**Environment variable**</span></span> | `COMPlus_TC_QuickJitForLoops` | <span data-ttu-id="7ac2e-164">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-164">`0` - disabled</span></span><br/><span data-ttu-id="7ac2e-165">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-165">`1` - enabled</span></span> |

### <a name="examples"></a><span data-ttu-id="7ac2e-166">示例</span><span class="sxs-lookup"><span data-stu-id="7ac2e-166">Examples</span></span>

<span data-ttu-id="7ac2e-167">runtimeconfig.json 文件： </span><span class="sxs-lookup"><span data-stu-id="7ac2e-167">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJitForLoops": false
      }
   }
}
```

<span data-ttu-id="7ac2e-168">项目文件：</span><span class="sxs-lookup"><span data-stu-id="7ac2e-168">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
  </PropertyGroup>

</Project>
```

## <a name="readytorun"></a><span data-ttu-id="7ac2e-169">ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="7ac2e-169">ReadyToRun</span></span>

- <span data-ttu-id="7ac2e-170">配置 .NET Core 运行时是否要为具有可用 ReadyToRun 数据的映像使用预编译代码。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-170">Configures whether the .NET Core runtime uses pre-compiled code for images with available ReadyToRun data.</span></span> <span data-ttu-id="7ac2e-171">如果禁用此选项，会强制运行时对框架代码进行 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-171">Disabling this option forces the runtime to JIT-compile framework code.</span></span>
- <span data-ttu-id="7ac2e-172">有关详细信息，请参阅 [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images)。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-172">For more information, see [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).</span></span>
- <span data-ttu-id="7ac2e-173">默认：启用 (`1`)。</span><span class="sxs-lookup"><span data-stu-id="7ac2e-173">Default: Enabled (`1`).</span></span>

| | <span data-ttu-id="7ac2e-174">设置名</span><span class="sxs-lookup"><span data-stu-id="7ac2e-174">Setting name</span></span> | <span data-ttu-id="7ac2e-175">值</span><span class="sxs-lookup"><span data-stu-id="7ac2e-175">Values</span></span> |
| - | - | - |
| <span data-ttu-id="7ac2e-176">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="7ac2e-176">**Environment variable**</span></span> | `COMPlus_ReadyToRun` | <span data-ttu-id="7ac2e-177">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-177">`1` - enabled</span></span><br/><span data-ttu-id="7ac2e-178">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="7ac2e-178">`0` - disabled</span></span> |
