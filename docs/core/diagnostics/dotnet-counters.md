---
title: dotnet-counters - .NET Core
description: 了解如何安装和使用 dotnet-counter 命令行工具。
ms.date: 02/26/2020
ms.openlocfilehash: 88f701a60d0ee03dd0236ae54c57679943e14939
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157877"
---
# <a name="dotnet-counters"></a><span data-ttu-id="573ae-103">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="573ae-103">dotnet-counters</span></span>

<span data-ttu-id="573ae-104"> 本文适用于： ✔️ .NET Core 3.0 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="573ae-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-counters"></a><span data-ttu-id="573ae-105">安装 dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="573ae-105">Install dotnet-counters</span></span>

<span data-ttu-id="573ae-106">若要安装最新版 `dotnet-counters` [NuGet 包](https://www.nuget.org/packages/dotnet-counters)，请使用 [dotnet tool install](../tools/dotnet-tool-install.md) 命令：</span><span class="sxs-lookup"><span data-stu-id="573ae-106">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a><span data-ttu-id="573ae-107">摘要</span><span class="sxs-lookup"><span data-stu-id="573ae-107">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="573ae-108">描述</span><span class="sxs-lookup"><span data-stu-id="573ae-108">Description</span></span>

<span data-ttu-id="573ae-109">`dotnet-counters` 是一个性能监视工具，用于临时运行状况监视和初级性能调查。</span><span class="sxs-lookup"><span data-stu-id="573ae-109">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="573ae-110">它可以观察通过 <xref:System.Diagnostics.Tracing.EventCounter> API 发布的性能计数器值。</span><span class="sxs-lookup"><span data-stu-id="573ae-110">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="573ae-111">例如，可以快速监视 CPU 使用情况或 .NET Core 应用程序中引发的异常率，以了解在使用 `PerfView` 或 `dotnet-trace` 深入调查更严重的性能问题之前是否有任何可疑操作。</span><span class="sxs-lookup"><span data-stu-id="573ae-111">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="573ae-112">选项</span><span class="sxs-lookup"><span data-stu-id="573ae-112">Options</span></span>

- **`--version`**

  <span data-ttu-id="573ae-113">显示 dotnet-counters 实用工具的版本。</span><span class="sxs-lookup"><span data-stu-id="573ae-113">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="573ae-114">显示命令行帮助。</span><span class="sxs-lookup"><span data-stu-id="573ae-114">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="573ae-115">命令</span><span class="sxs-lookup"><span data-stu-id="573ae-115">Commands</span></span>

| <span data-ttu-id="573ae-116">命令</span><span class="sxs-lookup"><span data-stu-id="573ae-116">Command</span></span>                                             |
| --------------------------------------------------- |
| [<span data-ttu-id="573ae-117">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="573ae-117">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="573ae-118">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="573ae-118">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="573ae-119">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="573ae-119">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="573ae-120">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="573ae-120">dotnet-counters ps</span></span>](#dotnet-counters-ps) |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="573ae-121">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="573ae-121">dotnet-counters collect</span></span>

<span data-ttu-id="573ae-122">定期收集所选计数器的值，并将它们导出为指定的文件格式以进行后续处理。</span><span class="sxs-lookup"><span data-stu-id="573ae-122">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="573ae-123">摘要</span><span class="sxs-lookup"><span data-stu-id="573ae-123">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list] [--format] [-o|--output]
```

### <a name="options"></a><span data-ttu-id="573ae-124">选项</span><span class="sxs-lookup"><span data-stu-id="573ae-124">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="573ae-125">要监视的进程的 ID。</span><span class="sxs-lookup"><span data-stu-id="573ae-125">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="573ae-126">更新显示的计数器之间延迟的秒数</span><span class="sxs-lookup"><span data-stu-id="573ae-126">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="573ae-127">计数器的空格分隔列表。</span><span class="sxs-lookup"><span data-stu-id="573ae-127">A space separated list of counters.</span></span> <span data-ttu-id="573ae-128">计数器可以指定为 `provider_name[:counter_name]`。</span><span class="sxs-lookup"><span data-stu-id="573ae-128">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="573ae-129">如果在没有符合条件的 `counter_name` 的情况下使用 `provider_name`，则会显示所有计数器。</span><span class="sxs-lookup"><span data-stu-id="573ae-129">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="573ae-130">若要发现提供程序和计数器名称，请使用 [dotnet-counters list](#dotnet-counters-list) 命令。</span><span class="sxs-lookup"><span data-stu-id="573ae-130">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="573ae-131">要导出的格式。</span><span class="sxs-lookup"><span data-stu-id="573ae-131">TThe format to be exported.</span></span> <span data-ttu-id="573ae-132">当前可用的格式：csv 和 json。</span><span class="sxs-lookup"><span data-stu-id="573ae-132">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="573ae-133">输出文件的名称。</span><span class="sxs-lookup"><span data-stu-id="573ae-133">The name of the output file.</span></span>

### <a name="examples"></a><span data-ttu-id="573ae-134">示例</span><span class="sxs-lookup"><span data-stu-id="573ae-134">Examples</span></span>

- <span data-ttu-id="573ae-135">以 3 秒的刷新间隔时间收集所有计数器的值，并生成 csv 输出文件：</span><span class="sxs-lookup"><span data-stu-id="573ae-135">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="573ae-136">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="573ae-136">dotnet-counters list</span></span>

<span data-ttu-id="573ae-137">显示按提供程序分组的计数器名称和说明的列表。</span><span class="sxs-lookup"><span data-stu-id="573ae-137">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="573ae-138">摘要</span><span class="sxs-lookup"><span data-stu-id="573ae-138">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="573ae-139">示例</span><span class="sxs-lookup"><span data-stu-id="573ae-139">Example</span></span>

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

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="573ae-140">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="573ae-140">dotnet-counters monitor</span></span>

<span data-ttu-id="573ae-141">显示所选计数器的定期刷新值。</span><span class="sxs-lookup"><span data-stu-id="573ae-141">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="573ae-142">摘要</span><span class="sxs-lookup"><span data-stu-id="573ae-142">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a><span data-ttu-id="573ae-143">选项</span><span class="sxs-lookup"><span data-stu-id="573ae-143">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="573ae-144">要监视的进程的 ID。</span><span class="sxs-lookup"><span data-stu-id="573ae-144">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="573ae-145">更新显示的计数器之间延迟的秒数</span><span class="sxs-lookup"><span data-stu-id="573ae-145">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="573ae-146">计数器的空格分隔列表。</span><span class="sxs-lookup"><span data-stu-id="573ae-146">A space separated list of counters.</span></span> <span data-ttu-id="573ae-147">计数器可以指定为 `provider_name[:counter_name]`。</span><span class="sxs-lookup"><span data-stu-id="573ae-147">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="573ae-148">如果在没有符合条件的 `counter_name` 的情况下使用 `provider_name`，则会显示所有计数器。</span><span class="sxs-lookup"><span data-stu-id="573ae-148">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="573ae-149">若要发现提供程序和计数器名称，请使用 [dotnet-counters list](#dotnet-counters-list) 命令。</span><span class="sxs-lookup"><span data-stu-id="573ae-149">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

### <a name="examples"></a><span data-ttu-id="573ae-150">示例</span><span class="sxs-lookup"><span data-stu-id="573ae-150">Examples</span></span>

- <span data-ttu-id="573ae-151">以 3 秒的刷新间隔监视 `System.Runtime` 中的所有计数器：</span><span class="sxs-lookup"><span data-stu-id="573ae-151">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

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

- <span data-ttu-id="573ae-152">仅监视 `System.Runtime` 中的 CPU 使用情况和 GC 堆大小：</span><span class="sxs-lookup"><span data-stu-id="573ae-152">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="573ae-153">监视用户定义的 `EventSource` 中的 `EventCounter` 值。</span><span class="sxs-lookup"><span data-stu-id="573ae-153">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="573ae-154">有关详细信息，请参阅[教程：如何使用 EventCounters 度量操作非常频繁事件的性能](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="573ae-154">For more information, see [Tutorial: How to measure performance for very frequent events using EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
  
## <a name="dotnet-counters-ps"></a><span data-ttu-id="573ae-155">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="573ae-155">dotnet-counters ps</span></span> 

<span data-ttu-id="573ae-156">显示可监视的 dotnet 进程的列表。</span><span class="sxs-lookup"><span data-stu-id="573ae-156">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="573ae-157">摘要</span><span class="sxs-lookup"><span data-stu-id="573ae-157">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="573ae-158">示例</span><span class="sxs-lookup"><span data-stu-id="573ae-158">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/suwhang/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```
