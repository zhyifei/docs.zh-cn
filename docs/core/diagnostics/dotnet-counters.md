---
title: dotnet-counters - .NET Core
description: 了解如何安装和使用 dotnet-counter 命令行工具。
ms.date: 10/14/2019
ms.openlocfilehash: 399d5908e8ac52bcd4a20c1a819fc6c99f4de2f4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737704"
---
# <a name="dotnet-counters"></a>dotnet-counters

 本文适用于： ✔️ .NET Core 3.0 SDK 及更高版本

## <a name="install-dotnet-counters"></a>安装 dotnet-counters

若要安装最新版 `dotnet-counters` [NuGet 包](https://www.nuget.org/packages/dotnet-counters)，请使用 [dotnet tool install](../tools/dotnet-tool-install.md) 命令：

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a>摘要

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a>描述

`dotnet-counters` 是一个性能监视工具，用于临时运行状况监视和初级性能调查。 它可以观察通过 <xref:System.Diagnostics.Tracing.EventCounter> API 发布的性能计数器值。 例如，可以快速监视 CPU 使用情况或 .NET Core 应用程序中引发的异常率，以了解在使用 `PerfView` 或 `dotnet-trace` 深入调查更严重的性能问题之前是否有任何可疑操作。

## <a name="options"></a>选项

- **`--version`**

  显示 dotnet-counters 实用工具的版本。

- **`-h|--help`**

  显示命令行帮助。

## <a name="commands"></a>命令

| 命令                                             |
| --------------------------------------------------- |
| [dotnet-counters list](#dotnet-counters-list)       |
| [dotnet-counters monitor](#dotnet-counters-monitor) |

## <a name="dotnet-counters-list"></a>dotnet-counters list

显示按提供程序分组的计数器名称和说明的列表。

### <a name="synopsis"></a>摘要

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a>示例

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

## <a name="dotnet-counters-monitor"></a>dotnet-counters monitor

显示所选计数器的定期刷新值。

### <a name="synopsis"></a>摘要

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a>选项

- **`-p|--process-id <PID>`**

  要监视的进程的 ID。

- **`--refresh-interval <SECONDS>`**

  更新显示的计数器之间延迟的秒数

- **`counter_list <COUNTERS>`**

  计数器的空格分隔列表。 计数器可以指定为 `provider_name[:counter_name]`。 如果在没有符合条件的 `counter_name` 的情况下使用 `provider_name`，则会显示所有计数器。 若要发现提供程序和计数器名称，请使用 [dotnet-counters list](#dotnet-counters-list) 命令。

### <a name="examples"></a>示例

- 以 3 秒的刷新间隔监视 `System.Runtime` 中的所有计数器：

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

- 仅监视 `System.Runtime` 中的 CPU 使用情况和 GC 堆大小：

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- 监视用户定义的 `EventSource` 中的 `EventCounter` 值。 有关详细信息，请参阅[教程：如何使用 EventCounters 度量操作非常频繁事件的性能](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md)。

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
