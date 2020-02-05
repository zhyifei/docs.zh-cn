---
title: 线程配置设置
description: 了解为 .NET Core 应用配置线程的运行时设置。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 68b8e93ca6ec3f708a7a627307655ada1955500a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789856"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="f383a-103">用于线程的运行时配置选项</span><span class="sxs-lookup"><span data-stu-id="f383a-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="f383a-104">CPU 组</span><span class="sxs-lookup"><span data-stu-id="f383a-104">CPU groups</span></span>

- <span data-ttu-id="f383a-105">配置是否在各 CPU 组之间自动分布线程。</span><span class="sxs-lookup"><span data-stu-id="f383a-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="f383a-106">默认：禁用 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="f383a-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="f383a-107">设置名</span><span class="sxs-lookup"><span data-stu-id="f383a-107">Setting name</span></span> | <span data-ttu-id="f383a-108">值</span><span class="sxs-lookup"><span data-stu-id="f383a-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f383a-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f383a-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="f383a-110">不可用</span><span class="sxs-lookup"><span data-stu-id="f383a-110">N/A</span></span> | <span data-ttu-id="f383a-111">不可用</span><span class="sxs-lookup"><span data-stu-id="f383a-111">N/A</span></span> |
| <span data-ttu-id="f383a-112">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="f383a-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="f383a-113">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="f383a-113">`0` - disabled</span></span><br/><span data-ttu-id="f383a-114">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="f383a-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="f383a-115">最小线程数</span><span class="sxs-lookup"><span data-stu-id="f383a-115">Minimum threads</span></span>

- <span data-ttu-id="f383a-116">指定工作线程池的最小线程数。</span><span class="sxs-lookup"><span data-stu-id="f383a-116">Specifies the minimum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="f383a-117">对应于 <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="f383a-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="f383a-118">设置名</span><span class="sxs-lookup"><span data-stu-id="f383a-118">Setting name</span></span> | <span data-ttu-id="f383a-119">值</span><span class="sxs-lookup"><span data-stu-id="f383a-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f383a-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f383a-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="f383a-121">一个表示最小线程数的整数</span><span class="sxs-lookup"><span data-stu-id="f383a-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="f383a-122">MSBuild 属性 </span><span class="sxs-lookup"><span data-stu-id="f383a-122">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="f383a-123">一个表示最小线程数的整数</span><span class="sxs-lookup"><span data-stu-id="f383a-123">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="f383a-124">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="f383a-124">**Environment variable**</span></span> | <span data-ttu-id="f383a-125">不可用</span><span class="sxs-lookup"><span data-stu-id="f383a-125">N/A</span></span> | <span data-ttu-id="f383a-126">不可用</span><span class="sxs-lookup"><span data-stu-id="f383a-126">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="f383a-127">示例</span><span class="sxs-lookup"><span data-stu-id="f383a-127">Examples</span></span>

<span data-ttu-id="f383a-128">runtimeconfig.json 文件： </span><span class="sxs-lookup"><span data-stu-id="f383a-128">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="f383a-129">项目文件：</span><span class="sxs-lookup"><span data-stu-id="f383a-129">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="f383a-130">最大线程数</span><span class="sxs-lookup"><span data-stu-id="f383a-130">Maximum threads</span></span>

- <span data-ttu-id="f383a-131">指定工作线程池的最大线程数。</span><span class="sxs-lookup"><span data-stu-id="f383a-131">Specifies the maximum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="f383a-132">对应于 <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="f383a-132">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="f383a-133">设置名</span><span class="sxs-lookup"><span data-stu-id="f383a-133">Setting name</span></span> | <span data-ttu-id="f383a-134">值</span><span class="sxs-lookup"><span data-stu-id="f383a-134">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f383a-135">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f383a-135">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="f383a-136">一个表示最大线程数的整数</span><span class="sxs-lookup"><span data-stu-id="f383a-136">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="f383a-137">MSBuild 属性 </span><span class="sxs-lookup"><span data-stu-id="f383a-137">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="f383a-138">一个表示最大线程数的整数</span><span class="sxs-lookup"><span data-stu-id="f383a-138">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="f383a-139">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="f383a-139">**Environment variable**</span></span> | <span data-ttu-id="f383a-140">不可用</span><span class="sxs-lookup"><span data-stu-id="f383a-140">N/A</span></span> | <span data-ttu-id="f383a-141">不可用</span><span class="sxs-lookup"><span data-stu-id="f383a-141">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="f383a-142">示例</span><span class="sxs-lookup"><span data-stu-id="f383a-142">Examples</span></span>

<span data-ttu-id="f383a-143">runtimeconfig.json 文件： </span><span class="sxs-lookup"><span data-stu-id="f383a-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="f383a-144">项目文件：</span><span class="sxs-lookup"><span data-stu-id="f383a-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
