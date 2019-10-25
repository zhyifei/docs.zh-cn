---
title: dotnet-trace - .NET Core
description: 安装和使用 dotnet-trace 命令行工具。
author: sdmaclea
ms.author: stmaclea
ms.date: 10/14/2019
ms.openlocfilehash: 6513cf63070bc1984006da75313e9912d76a6c95
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321530"
---
# <a name="trace-for-performance-analysis-utility-dotnet-trace"></a>跟踪性能分析实用工具 (`dotnet-trace`)

**本文适用于：** .NET Core 3.0 SDK 及更高版本

## <a name="installing-dotnet-trace"></a>安装 `dotnet-trace`

若要安装最新版 `dotnet-trace` [NuGet 包](https://www.nuget.org/packages/dotnet-trace)，请使用 [dotnet tool install](../tools/dotnet-tool-install.md) 命令：

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a>摘要

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a>说明

`dotnet-trace` 工具是一种跨平台 CLI 全局工具，可用于在不涉及任何本机探查器的情况下，收集正在运行的进程的 .NET Core 跟踪。 它是围绕 .NET Core 运行时的跨平台 `EventPipe` 技术而构建的。 `dotnet-trace` 在 Windows、Linux 或 macOS 上提供相同体验。

## <a name="options"></a>选项

- **`--version`**

显示 dotnet-counters 实用工具的版本。

- **`-h|--help`**

显示命令行帮助。

## <a name="commands"></a>命令

| 命令                                                     |
| ----------------------------------------------------------- |
| [dotnet-trace collect](#dotnet-trace-collect)               |
| [dotnet-trace convert](#dotnet-trace-convert)               |
| [dotnet-trace list-processes](#dotnet-trace-list-processes) |
| [dotnet-trace list-profiles](#dotnet-trace-list-profiles)   |

## <a name="dotnet-trace-collect"></a>dotnet-trace collect

从正在运行的进程中收集诊断跟踪。

### <a name="synopsis"></a>摘要

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a>选项

- **`-p|--process-id <PID>`**

  从中收集跟踪的进程。

- **`--buffersize <size>`**

  设置内存中循环缓冲区的大小（以 MB 表示）。 默认值为 256 MB。

- **`-o|--output <trace-file-path>`**

  收集的跟踪数据的输出路径。 如果未指定，则默认为 `trace.nettrace`。

- **`--providers <list-of-comma-separated-providers>`**

  要启用的 `EventPipe` 提供程序的以逗号分隔的列表。 这些提供程序会补充 `--profile <profile-name>` 隐含的任何提供程序。 如果特定提供程序存在任何不一致的情况，此处的配置将优先于配置文件中的隐式配置。

  此提供程序列表的格式为：

  - `Provider[,Provider]`
  - `Provider` 的格式为：`KnownProviderName[:Flags[:Level][:KeyValueArgs]]`。
  - `KeyValueArgs` 的格式为：`[key1=value1][;key2=value2]`。

- **`--profile <profile-name>`**

  一组命名的预定义提供程序配置，允许简明地指定常见跟踪方案。

- **`--format <NetTrace|Speedscope>`**

  设置跟踪文件转换的输出格式。

## <a name="dotnet-trace-convert"></a>dotnet-trace convert

将 `nettrace` 跟踪转换为备用格式，以便用于备用跟踪分析工具。

### <a name="synopsis"></a>摘要

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a>自变量

- **`<input-filename>`**

  要转换的输入跟踪文件。 默认为 trace.nettrace  。

### <a name="options"></a>选项

- **`--format <NetTrace|Speedscope>`**

  设置跟踪文件转换的输出格式。

- **`-o|--output <output-filename>`**

  输出文件名。 将添加目标格式的扩展。

## <a name="dotnet-trace-list-processes"></a>dotnet-trace list-processes

列出可以跟踪的 dotnet 进程。

### <a name="synopsis"></a>摘要

```console
dotnet-trace list-processes [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a>dotnet-trace list-profiles

列出预生成的跟踪配置文件，并描述每个配置文件中包含的提供程序和筛选器。

### <a name="synopsis"></a>摘要

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a>使用 `dotnet-trace` 收集跟踪

- 若要使用 `dotnet-trace` 收集跟踪，需要首先查找要从中收集跟踪的 .NET Core 应用程序的进程标识符 (PID)。

  - 在 Windows 上提供了一些选择，例如，可以使用任务管理器或 `tasklist` 命令。
  - 在 Linux 上，一般选择使用 `ps` 命令。

还可以使用 [dotnet-trace list-processes](#dotnet-trace-list-processes) 命令来找出正在运行的 .NET Core 进程及其 PID。

- 然后，运行以下命令：

```console
> dotnet-trace collect --process-id <PID>

Press <Enter> to exit...
Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
```

- 最后，通过按 `<Enter>` 键停止收集，`dotnet-trace` 会停止将事件记录到 `trace.nettrace` 文件中。

## <a name="viewing-the-trace-captured-from-dotnet-trace"></a>查看从 `dotnet-trace` 捕获的跟踪

在 Windows 上，可在 [PerfView](https://github.com/microsoft/perfview) 上查看 `.nettrace` 文件以进行分析，就像通过 ETW 或 LTTng 收集的跟踪一样。 对于 Linux 上收集的跟踪，可以将跟踪移动到 Windows 计算机以在 PerfView 上进行查看。

还可以通过将 `dotnet-trace` 的输出格式更改为 `speedscope` 来在 Linux 计算机上查看跟踪。 可以使用 `-f|--format` 选项更改输出文件格式 - `-f speedscope` 会使 `dotnet-trace` 生成 `speedscope` 文件。 目前，可以在 `nettrace`（默认选项）和 `speedscope` 之间进行选择。 可以在 <https://www.speedscope.app> 打开 `Speedscope` 文件。

> [!NOTE]
> .NET Core 运行时以 `nettrace` 格式生成跟踪，并在跟踪完成后将其转换为 speedscope（如果指定）。 由于某些转换可能会导致数据丢失，因此，原始 `nettrace` 文件将保留在转换后的文件旁边。

## <a name="using-dotnet-trace-to-collect-counter-values-over-time"></a>使用 `dotnet-trace` 收集随时间变化的计数器值

如果尝试在性能敏感的设置（如生产环境）中使用 `EventCounter` 进行基本运行状况监视，并且想要收集跟踪，而不是实时监视跟踪，则还可以使用 `dotnet-trace` 执行此操作。

例如，如果想要收集运行时性能计数器值，则可以使用以下命令：

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

此命令通知运行时计数器每秒报告一次，以便进行轻量型运行状况监视。 通过使用较大的值（例如 60）替换 `EventCounterIntervalSec=1`，可以收集计数器数据中粒度较小的跟踪。

如果要禁用运行时事件来更进一步降低开销（和跟踪大小），可以使用以下命令禁用运行时事件和托管堆栈探查器。

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

## <a name="net-providers"></a>.NET 提供程序

.NET Core 运行时支持以下 .NET 提供程序： .NET Core 使用相同的关键字来启用 `Event Tracing for Windows (ETW)` 和 `EventPipe` 跟踪。

| 提供程序名称                            | 信息 |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [运行时提供程序](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[CLR 运行时关键字](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [断开提供程序](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[CLR 断开关键字](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | 启用示例探查器。 |
