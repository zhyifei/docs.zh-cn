---
title: dotnet-counters - .NET Core
description: 了解如何安装和使用 dotnet-counter 命令行工具。
ms.date: 10/14/2019
ms.openlocfilehash: 10af451a8b1b4d8b27da1490b99b19a4359c860f
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740801"
---
# <a name="dotnet-counters"></a><span data-ttu-id="11488-103">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="11488-103">dotnet-counters</span></span>

<span data-ttu-id="11488-104">**本文适用于：✓** .NET Core 3.0 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="11488-104">**This article applies to: ✓** .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-counters"></a><span data-ttu-id="11488-105">安装 dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="11488-105">Install dotnet-counters</span></span>

<span data-ttu-id="11488-106">若要安装最新版 `dotnet-counters` [NuGet 包](https://www.nuget.org/packages/dotnet-counters)，请使用 [dotnet tool install](../tools/dotnet-tool-install.md) 命令：</span><span class="sxs-lookup"><span data-stu-id="11488-106">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a><span data-ttu-id="11488-107">摘要</span><span class="sxs-lookup"><span data-stu-id="11488-107">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="11488-108">描述</span><span class="sxs-lookup"><span data-stu-id="11488-108">Description</span></span>

<span data-ttu-id="11488-109">`dotnet-counters` 是一个性能监视工具，用于临时运行状况监视和初级性能调查。</span><span class="sxs-lookup"><span data-stu-id="11488-109">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="11488-110">它可以观察通过 <xref:System.Diagnostics.Tracing.EventCounter> API 发布的性能计数器值。</span><span class="sxs-lookup"><span data-stu-id="11488-110">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="11488-111">例如，可以快速监视 CPU 使用情况或 .NET Core 应用程序中引发的异常率，以了解在使用 `PerfView` 或 `dotnet-trace` 深入调查更严重的性能问题之前是否有任何可疑操作。</span><span class="sxs-lookup"><span data-stu-id="11488-111">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="11488-112">选项</span><span class="sxs-lookup"><span data-stu-id="11488-112">Options</span></span>

- **`--version`**

  <span data-ttu-id="11488-113">显示 dotnet-counters 实用工具的版本。</span><span class="sxs-lookup"><span data-stu-id="11488-113">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="11488-114">显示命令行帮助。</span><span class="sxs-lookup"><span data-stu-id="11488-114">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="11488-115">命令</span><span class="sxs-lookup"><span data-stu-id="11488-115">Commands</span></span>

| <span data-ttu-id="11488-116">命令</span><span class="sxs-lookup"><span data-stu-id="11488-116">Command</span></span>                                             |
| --------------------------------------------------- |
| [<span data-ttu-id="11488-117">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="11488-117">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="11488-118">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="11488-118">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |

## <a name="dotnet-counters-list"></a><span data-ttu-id="11488-119">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="11488-119">dotnet-counters list</span></span>

<span data-ttu-id="11488-120">显示按提供程序分组的计数器名称和说明的列表。</span><span class="sxs-lookup"><span data-stu-id="11488-120">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="11488-121">摘要</span><span class="sxs-lookup"><span data-stu-id="11488-121">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="11488-122">示例</span><span class="sxs-lookup"><span data-stu-id="11488-122">Example</span></span>

```console
> dotnet-counters list

    Showing well-known counters only. Specific processes may support additional counters.
    System.Runtime
        cpu-usage                    Amount of time the process has utilized the CPU (ms)
        working-set                  Amount of working set used by the process (MB)
        gc-heap-size                 Total heap size reported by the GC (MB)
        gen-0-gc-count               Number of Gen 0 GCs / sec
        gen-1-gc-count               Number of Gen 1 GCs / sec
        gen-2-gc-count               Number of Gen 2 GCs / sec
        exception-count              Number of Exceptions / sec
```

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="11488-123">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="11488-123">dotnet-counters monitor</span></span>

<span data-ttu-id="11488-124">显示所选计数器的定期刷新值。</span><span class="sxs-lookup"><span data-stu-id="11488-124">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="11488-125">摘要</span><span class="sxs-lookup"><span data-stu-id="11488-125">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a><span data-ttu-id="11488-126">选项</span><span class="sxs-lookup"><span data-stu-id="11488-126">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="11488-127">要监视的进程的 ID。</span><span class="sxs-lookup"><span data-stu-id="11488-127">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="11488-128">更新显示的计数器之间延迟的秒数</span><span class="sxs-lookup"><span data-stu-id="11488-128">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="11488-129">计数器的空格分隔列表。</span><span class="sxs-lookup"><span data-stu-id="11488-129">A space separated list of counters.</span></span> <span data-ttu-id="11488-130">计数器可以指定为 `provider_name[:counter_name]`。</span><span class="sxs-lookup"><span data-stu-id="11488-130">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="11488-131">如果在没有符合条件的 `counter_name` 的情况下使用 `provider_name`，则会显示所有计数器。</span><span class="sxs-lookup"><span data-stu-id="11488-131">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="11488-132">若要发现提供程序和计数器名称，请使用 [dotnet-counters list](#dotnet-counters-list) 命令。</span><span class="sxs-lookup"><span data-stu-id="11488-132">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

### <a name="examples"></a><span data-ttu-id="11488-133">示例</span><span class="sxs-lookup"><span data-stu-id="11488-133">Examples</span></span>

- <span data-ttu-id="11488-134">以 3 秒的刷新间隔监视 `System.Runtime` 中的所有计数器：</span><span class="sxs-lookup"><span data-stu-id="11488-134">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 System.Runtime

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      Working Set (MB)                            1982
      GC Heap Size (MB)                            811
      Gen 0 GC / second                             20
      Gen 1 GC / second                              4
      Gen 2 GC / second                              1
      Number of Exceptions / sec                     4
  ```

- <span data-ttu-id="11488-135">仅监视 `System.Runtime` 中的 CPU 使用情况和 GC 堆大小：</span><span class="sxs-lookup"><span data-stu-id="11488-135">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="11488-136">监视用户定义的 `EventSource` 中的 `EventCounter` 值。</span><span class="sxs-lookup"><span data-stu-id="11488-136">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="11488-137">有关详细信息，请参阅[教程：如何使用 EventCounters 度量操作非常频繁事件的性能](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="11488-137">For more information, see [Tutorial: How to measure performance for very frequent events using EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
