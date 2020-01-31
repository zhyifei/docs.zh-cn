---
title: 线程配置设置
description: 了解为 .NET Core 应用配置线程的运行时设置。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: ed7688d4d8f7178440fe59afc6e2f5e0a11b2a5c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733431"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="ef0bf-103">用于线程的运行时配置选项</span><span class="sxs-lookup"><span data-stu-id="ef0bf-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="ef0bf-104">CPU 组</span><span class="sxs-lookup"><span data-stu-id="ef0bf-104">CPU groups</span></span>

- <span data-ttu-id="ef0bf-105">配置是否在各 CPU 组之间自动分布线程。</span><span class="sxs-lookup"><span data-stu-id="ef0bf-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="ef0bf-106">默认：禁用 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="ef0bf-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="ef0bf-107">设置名</span><span class="sxs-lookup"><span data-stu-id="ef0bf-107">Setting name</span></span> | <span data-ttu-id="ef0bf-108">值</span><span class="sxs-lookup"><span data-stu-id="ef0bf-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="ef0bf-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ef0bf-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="ef0bf-110">不可用</span><span class="sxs-lookup"><span data-stu-id="ef0bf-110">N/A</span></span> | <span data-ttu-id="ef0bf-111">不可用</span><span class="sxs-lookup"><span data-stu-id="ef0bf-111">N/A</span></span> |
| <span data-ttu-id="ef0bf-112">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ef0bf-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="ef0bf-113">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="ef0bf-113">`0` - disabled</span></span><br/><span data-ttu-id="ef0bf-114">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="ef0bf-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="ef0bf-115">最小线程数</span><span class="sxs-lookup"><span data-stu-id="ef0bf-115">Minimum threads</span></span>

- <span data-ttu-id="ef0bf-116">指定工作线程池的最小线程数。</span><span class="sxs-lookup"><span data-stu-id="ef0bf-116">Specifies the minimum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="ef0bf-117">对应于 <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="ef0bf-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="ef0bf-118">设置名</span><span class="sxs-lookup"><span data-stu-id="ef0bf-118">Setting name</span></span> | <span data-ttu-id="ef0bf-119">值</span><span class="sxs-lookup"><span data-stu-id="ef0bf-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="ef0bf-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ef0bf-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="ef0bf-121">一个表示最小线程数的整数</span><span class="sxs-lookup"><span data-stu-id="ef0bf-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="ef0bf-122">MSBuild 属性 </span><span class="sxs-lookup"><span data-stu-id="ef0bf-122">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="ef0bf-123">一个表示最小线程数的整数</span><span class="sxs-lookup"><span data-stu-id="ef0bf-123">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="ef0bf-124">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ef0bf-124">**Environment variable**</span></span> | <span data-ttu-id="ef0bf-125">不可用</span><span class="sxs-lookup"><span data-stu-id="ef0bf-125">N/A</span></span> | <span data-ttu-id="ef0bf-126">不可用</span><span class="sxs-lookup"><span data-stu-id="ef0bf-126">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="ef0bf-127">示例</span><span class="sxs-lookup"><span data-stu-id="ef0bf-127">Examples</span></span>

<span data-ttu-id="ef0bf-128">runtimeconfig.json 文件： </span><span class="sxs-lookup"><span data-stu-id="ef0bf-128">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="ef0bf-129">项目文件：</span><span class="sxs-lookup"><span data-stu-id="ef0bf-129">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="ef0bf-130">最大线程数</span><span class="sxs-lookup"><span data-stu-id="ef0bf-130">Maximum threads</span></span>

- <span data-ttu-id="ef0bf-131">指定工作线程池的最大线程数。</span><span class="sxs-lookup"><span data-stu-id="ef0bf-131">Specifies the maximum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="ef0bf-132">对应于 <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="ef0bf-132">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="ef0bf-133">设置名</span><span class="sxs-lookup"><span data-stu-id="ef0bf-133">Setting name</span></span> | <span data-ttu-id="ef0bf-134">值</span><span class="sxs-lookup"><span data-stu-id="ef0bf-134">Values</span></span> |
| - | - | - |
| <span data-ttu-id="ef0bf-135">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ef0bf-135">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="ef0bf-136">一个表示最大线程数的整数</span><span class="sxs-lookup"><span data-stu-id="ef0bf-136">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="ef0bf-137">MSBuild 属性 </span><span class="sxs-lookup"><span data-stu-id="ef0bf-137">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="ef0bf-138">一个表示最大线程数的整数</span><span class="sxs-lookup"><span data-stu-id="ef0bf-138">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="ef0bf-139">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ef0bf-139">**Environment variable**</span></span> | <span data-ttu-id="ef0bf-140">不可用</span><span class="sxs-lookup"><span data-stu-id="ef0bf-140">N/A</span></span> | <span data-ttu-id="ef0bf-141">不可用</span><span class="sxs-lookup"><span data-stu-id="ef0bf-141">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="ef0bf-142">示例</span><span class="sxs-lookup"><span data-stu-id="ef0bf-142">Examples</span></span>

<span data-ttu-id="ef0bf-143">runtimeconfig.json 文件： </span><span class="sxs-lookup"><span data-stu-id="ef0bf-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="ef0bf-144">项目文件：</span><span class="sxs-lookup"><span data-stu-id="ef0bf-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
