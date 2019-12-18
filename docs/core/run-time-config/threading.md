---
title: 线程配置设置
description: 了解为 .NET Core 应用配置线程的运行时设置。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 6a920dbc301830e3f4c95bf637ff3de6d4f464ff
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998827"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="530d3-103">用于线程的运行时配置选项</span><span class="sxs-lookup"><span data-stu-id="530d3-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="530d3-104">CPU 组</span><span class="sxs-lookup"><span data-stu-id="530d3-104">CPU groups</span></span>

- <span data-ttu-id="530d3-105">配置是否在各 CPU 组之间自动分布线程。</span><span class="sxs-lookup"><span data-stu-id="530d3-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="530d3-106">默认：禁用 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="530d3-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="530d3-107">设置名</span><span class="sxs-lookup"><span data-stu-id="530d3-107">Setting name</span></span> | <span data-ttu-id="530d3-108">值</span><span class="sxs-lookup"><span data-stu-id="530d3-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="530d3-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="530d3-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="530d3-110">不可用</span><span class="sxs-lookup"><span data-stu-id="530d3-110">N/A</span></span> | <span data-ttu-id="530d3-111">不可用</span><span class="sxs-lookup"><span data-stu-id="530d3-111">N/A</span></span> |
| <span data-ttu-id="530d3-112">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="530d3-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="530d3-113">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="530d3-113">`0` - disabled</span></span><br/><span data-ttu-id="530d3-114">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="530d3-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="530d3-115">最小线程数</span><span class="sxs-lookup"><span data-stu-id="530d3-115">Minimum threads</span></span>

- <span data-ttu-id="530d3-116">指定工作线程池的最小线程数。</span><span class="sxs-lookup"><span data-stu-id="530d3-116">Specifies the minimum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="530d3-117">对应于 <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="530d3-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="530d3-118">设置名</span><span class="sxs-lookup"><span data-stu-id="530d3-118">Setting name</span></span> | <span data-ttu-id="530d3-119">值</span><span class="sxs-lookup"><span data-stu-id="530d3-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="530d3-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="530d3-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="530d3-121">一个表示最小线程数的整数</span><span class="sxs-lookup"><span data-stu-id="530d3-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="530d3-122">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="530d3-122">**Environment variable**</span></span> | <span data-ttu-id="530d3-123">不可用</span><span class="sxs-lookup"><span data-stu-id="530d3-123">N/A</span></span> | <span data-ttu-id="530d3-124">不可用</span><span class="sxs-lookup"><span data-stu-id="530d3-124">N/A</span></span> |

## <a name="maximum-threads"></a><span data-ttu-id="530d3-125">最大线程数</span><span class="sxs-lookup"><span data-stu-id="530d3-125">Maximum threads</span></span>

- <span data-ttu-id="530d3-126">指定工作线程池的最大线程数。</span><span class="sxs-lookup"><span data-stu-id="530d3-126">Specifies the maximum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="530d3-127">对应于 <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="530d3-127">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="530d3-128">设置名</span><span class="sxs-lookup"><span data-stu-id="530d3-128">Setting name</span></span> | <span data-ttu-id="530d3-129">值</span><span class="sxs-lookup"><span data-stu-id="530d3-129">Values</span></span> |
| - | - | - |
| <span data-ttu-id="530d3-130">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="530d3-130">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="530d3-131">一个表示最大线程数的整数</span><span class="sxs-lookup"><span data-stu-id="530d3-131">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="530d3-132">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="530d3-132">**Environment variable**</span></span> | <span data-ttu-id="530d3-133">不可用</span><span class="sxs-lookup"><span data-stu-id="530d3-133">N/A</span></span> | <span data-ttu-id="530d3-134">不可用</span><span class="sxs-lookup"><span data-stu-id="530d3-134">N/A</span></span> |
