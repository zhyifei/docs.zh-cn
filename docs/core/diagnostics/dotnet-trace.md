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
# <a name="trace-for-performance-analysis-utility-dotnet-trace"></a><span data-ttu-id="a2b81-103">跟踪性能分析实用工具 (`dotnet-trace`)</span><span class="sxs-lookup"><span data-stu-id="a2b81-103">Trace for performance analysis utility (`dotnet-trace`)</span></span>

<span data-ttu-id="a2b81-104">**本文适用于：** .NET Core 3.0 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="a2b81-104">**This article applies to:** .NET Core 3.0 SDK and later versions</span></span>

## <a name="installing-dotnet-trace"></a><span data-ttu-id="a2b81-105">安装 `dotnet-trace`</span><span class="sxs-lookup"><span data-stu-id="a2b81-105">Installing `dotnet-trace`</span></span>

<span data-ttu-id="a2b81-106">若要安装最新版 `dotnet-trace` [NuGet 包](https://www.nuget.org/packages/dotnet-trace)，请使用 [dotnet tool install](../tools/dotnet-tool-install.md) 命令：</span><span class="sxs-lookup"><span data-stu-id="a2b81-106">To install the latest release version of the `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a><span data-ttu-id="a2b81-107">摘要</span><span class="sxs-lookup"><span data-stu-id="a2b81-107">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="a2b81-108">说明</span><span class="sxs-lookup"><span data-stu-id="a2b81-108">Description</span></span>

<span data-ttu-id="a2b81-109">`dotnet-trace` 工具是一种跨平台 CLI 全局工具，可用于在不涉及任何本机探查器的情况下，收集正在运行的进程的 .NET Core 跟踪。</span><span class="sxs-lookup"><span data-stu-id="a2b81-109">The `dotnet-trace` tool is a cross-platform CLI global tool that enables the collection of .NET Core traces of a running process without any native profiler involved.</span></span> <span data-ttu-id="a2b81-110">它是围绕 .NET Core 运行时的跨平台 `EventPipe` 技术而构建的。</span><span class="sxs-lookup"><span data-stu-id="a2b81-110">It's built around the cross-platform `EventPipe` technology of the .NET Core runtime.</span></span> <span data-ttu-id="a2b81-111">`dotnet-trace` 在 Windows、Linux 或 macOS 上提供相同体验。</span><span class="sxs-lookup"><span data-stu-id="a2b81-111">`dotnet-trace` delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="a2b81-112">选项</span><span class="sxs-lookup"><span data-stu-id="a2b81-112">Options</span></span>

- **`--version`**

<span data-ttu-id="a2b81-113">显示 dotnet-counters 实用工具的版本。</span><span class="sxs-lookup"><span data-stu-id="a2b81-113">Display the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

<span data-ttu-id="a2b81-114">显示命令行帮助。</span><span class="sxs-lookup"><span data-stu-id="a2b81-114">Show command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="a2b81-115">命令</span><span class="sxs-lookup"><span data-stu-id="a2b81-115">Commands</span></span>

| <span data-ttu-id="a2b81-116">命令</span><span class="sxs-lookup"><span data-stu-id="a2b81-116">Command</span></span>                                                     |
| ----------------------------------------------------------- |
| [<span data-ttu-id="a2b81-117">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="a2b81-117">dotnet-trace collect</span></span>](#dotnet-trace-collect)               |
| [<span data-ttu-id="a2b81-118">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="a2b81-118">dotnet-trace convert</span></span>](#dotnet-trace-convert)               |
| [<span data-ttu-id="a2b81-119">dotnet-trace list-processes</span><span class="sxs-lookup"><span data-stu-id="a2b81-119">dotnet-trace list-processes</span></span>](#dotnet-trace-list-processes) |
| [<span data-ttu-id="a2b81-120">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="a2b81-120">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles)   |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="a2b81-121">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="a2b81-121">dotnet-trace collect</span></span>

<span data-ttu-id="a2b81-122">从正在运行的进程中收集诊断跟踪。</span><span class="sxs-lookup"><span data-stu-id="a2b81-122">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="a2b81-123">摘要</span><span class="sxs-lookup"><span data-stu-id="a2b81-123">Synopsis</span></span>

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a><span data-ttu-id="a2b81-124">选项</span><span class="sxs-lookup"><span data-stu-id="a2b81-124">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="a2b81-125">从中收集跟踪的进程。</span><span class="sxs-lookup"><span data-stu-id="a2b81-125">The process to collect the trace from.</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="a2b81-126">设置内存中循环缓冲区的大小（以 MB 表示）。</span><span class="sxs-lookup"><span data-stu-id="a2b81-126">Sets the size of the in-memory circular buffer in megabytes.</span></span> <span data-ttu-id="a2b81-127">默认值为 256 MB。</span><span class="sxs-lookup"><span data-stu-id="a2b81-127">Default 256 MB.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="a2b81-128">收集的跟踪数据的输出路径。</span><span class="sxs-lookup"><span data-stu-id="a2b81-128">The output path for the collected trace data.</span></span> <span data-ttu-id="a2b81-129">如果未指定，则默认为 `trace.nettrace`。</span><span class="sxs-lookup"><span data-stu-id="a2b81-129">If not specified it defaults to `trace.nettrace`.</span></span>

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="a2b81-130">要启用的 `EventPipe` 提供程序的以逗号分隔的列表。</span><span class="sxs-lookup"><span data-stu-id="a2b81-130">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="a2b81-131">这些提供程序会补充 `--profile <profile-name>` 隐含的任何提供程序。</span><span class="sxs-lookup"><span data-stu-id="a2b81-131">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="a2b81-132">如果特定提供程序存在任何不一致的情况，此处的配置将优先于配置文件中的隐式配置。</span><span class="sxs-lookup"><span data-stu-id="a2b81-132">If there's any inconsistency for a particular provider, the configuration here takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="a2b81-133">此提供程序列表的格式为：</span><span class="sxs-lookup"><span data-stu-id="a2b81-133">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="a2b81-134">`Provider` 的格式为：`KnownProviderName[:Flags[:Level][:KeyValueArgs]]`。</span><span class="sxs-lookup"><span data-stu-id="a2b81-134">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="a2b81-135">`KeyValueArgs` 的格式为：`[key1=value1][;key2=value2]`。</span><span class="sxs-lookup"><span data-stu-id="a2b81-135">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="a2b81-136">一组命名的预定义提供程序配置，允许简明地指定常见跟踪方案。</span><span class="sxs-lookup"><span data-stu-id="a2b81-136">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span>

- **`--format <NetTrace|Speedscope>`**

  <span data-ttu-id="a2b81-137">设置跟踪文件转换的输出格式。</span><span class="sxs-lookup"><span data-stu-id="a2b81-137">Sets the output format for the trace file conversion.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="a2b81-138">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="a2b81-138">dotnet-trace convert</span></span>

<span data-ttu-id="a2b81-139">将 `nettrace` 跟踪转换为备用格式，以便用于备用跟踪分析工具。</span><span class="sxs-lookup"><span data-stu-id="a2b81-139">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="a2b81-140">摘要</span><span class="sxs-lookup"><span data-stu-id="a2b81-140">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a><span data-ttu-id="a2b81-141">自变量</span><span class="sxs-lookup"><span data-stu-id="a2b81-141">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="a2b81-142">要转换的输入跟踪文件。</span><span class="sxs-lookup"><span data-stu-id="a2b81-142">Input trace file to be converted.</span></span> <span data-ttu-id="a2b81-143">默认为 trace.nettrace  。</span><span class="sxs-lookup"><span data-stu-id="a2b81-143">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="a2b81-144">选项</span><span class="sxs-lookup"><span data-stu-id="a2b81-144">Options</span></span>

- **`--format <NetTrace|Speedscope>`**

  <span data-ttu-id="a2b81-145">设置跟踪文件转换的输出格式。</span><span class="sxs-lookup"><span data-stu-id="a2b81-145">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="a2b81-146">输出文件名。</span><span class="sxs-lookup"><span data-stu-id="a2b81-146">Output filename.</span></span> <span data-ttu-id="a2b81-147">将添加目标格式的扩展。</span><span class="sxs-lookup"><span data-stu-id="a2b81-147">Extension of target format will be added.</span></span>

## <a name="dotnet-trace-list-processes"></a><span data-ttu-id="a2b81-148">dotnet-trace list-processes</span><span class="sxs-lookup"><span data-stu-id="a2b81-148">dotnet-trace list-processes</span></span>

<span data-ttu-id="a2b81-149">列出可以跟踪的 dotnet 进程。</span><span class="sxs-lookup"><span data-stu-id="a2b81-149">Lists dotnet processes that can be traced.</span></span>

### <a name="synopsis"></a><span data-ttu-id="a2b81-150">摘要</span><span class="sxs-lookup"><span data-stu-id="a2b81-150">Synopsis</span></span>

```console
dotnet-trace list-processes [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="a2b81-151">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="a2b81-151">dotnet-trace list-profiles</span></span>

<span data-ttu-id="a2b81-152">列出预生成的跟踪配置文件，并描述每个配置文件中包含的提供程序和筛选器。</span><span class="sxs-lookup"><span data-stu-id="a2b81-152">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="a2b81-153">摘要</span><span class="sxs-lookup"><span data-stu-id="a2b81-153">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="a2b81-154">使用 `dotnet-trace` 收集跟踪</span><span class="sxs-lookup"><span data-stu-id="a2b81-154">Collect a trace with `dotnet-trace`</span></span>

- <span data-ttu-id="a2b81-155">若要使用 `dotnet-trace` 收集跟踪，需要首先查找要从中收集跟踪的 .NET Core 应用程序的进程标识符 (PID)。</span><span class="sxs-lookup"><span data-stu-id="a2b81-155">To collect traces using `dotnet-trace`, you'll need to first, find out the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="a2b81-156">在 Windows 上提供了一些选择，例如，可以使用任务管理器或 `tasklist` 命令。</span><span class="sxs-lookup"><span data-stu-id="a2b81-156">On Windows, there are options such as using the task manager or the `tasklist` command.</span></span>
  - <span data-ttu-id="a2b81-157">在 Linux 上，一般选择使用 `ps` 命令。</span><span class="sxs-lookup"><span data-stu-id="a2b81-157">On Linux, the trivial option could be using `ps` command.</span></span>

<span data-ttu-id="a2b81-158">还可以使用 [dotnet-trace list-processes](#dotnet-trace-list-processes) 命令来找出正在运行的 .NET Core 进程及其 PID。</span><span class="sxs-lookup"><span data-stu-id="a2b81-158">You may also use the [dotnet-trace list-processes](#dotnet-trace-list-processes) command to find out what .NET Core processes are running, along with their PIDs.</span></span>

- <span data-ttu-id="a2b81-159">然后，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a2b81-159">Then, run the following command:</span></span>

```console
> dotnet-trace collect --process-id <PID>

Press <Enter> to exit...
Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
```

- <span data-ttu-id="a2b81-160">最后，通过按 `<Enter>` 键停止收集，`dotnet-trace` 会停止将事件记录到 `trace.nettrace` 文件中。</span><span class="sxs-lookup"><span data-stu-id="a2b81-160">Finally, stop collection by pressing the `<Enter>` key, and `dotnet-trace` will finish logging events to `trace.nettrace` file.</span></span>

## <a name="viewing-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="a2b81-161">查看从 `dotnet-trace` 捕获的跟踪</span><span class="sxs-lookup"><span data-stu-id="a2b81-161">Viewing the trace captured from `dotnet-trace`</span></span>

<span data-ttu-id="a2b81-162">在 Windows 上，可在 [PerfView](https://github.com/microsoft/perfview) 上查看 `.nettrace` 文件以进行分析，就像通过 ETW 或 LTTng 收集的跟踪一样。</span><span class="sxs-lookup"><span data-stu-id="a2b81-162">On Windows, `.nettrace` files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis, just like traces collected with ETW or LTTng.</span></span> <span data-ttu-id="a2b81-163">对于 Linux 上收集的跟踪，可以将跟踪移动到 Windows 计算机以在 PerfView 上进行查看。</span><span class="sxs-lookup"><span data-stu-id="a2b81-163">For traces collected on Linux, you can move the trace to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="a2b81-164">还可以通过将 `dotnet-trace` 的输出格式更改为 `speedscope` 来在 Linux 计算机上查看跟踪。</span><span class="sxs-lookup"><span data-stu-id="a2b81-164">You may also view the trace on a Linux machine by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="a2b81-165">可以使用 `-f|--format` 选项更改输出文件格式 - `-f speedscope` 会使 `dotnet-trace` 生成 `speedscope` 文件。</span><span class="sxs-lookup"><span data-stu-id="a2b81-165">You can change the output file format using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` to produce a `speedscope` file.</span></span> <span data-ttu-id="a2b81-166">目前，可以在 `nettrace`（默认选项）和 `speedscope` 之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="a2b81-166">You can currently choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="a2b81-167">可以在 <https://www.speedscope.app> 打开 `Speedscope` 文件。</span><span class="sxs-lookup"><span data-stu-id="a2b81-167">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="a2b81-168">.NET Core 运行时以 `nettrace` 格式生成跟踪，并在跟踪完成后将其转换为 speedscope（如果指定）。</span><span class="sxs-lookup"><span data-stu-id="a2b81-168">The .NET Core runtime generates traces in the `nettrace` format, and they're converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="a2b81-169">由于某些转换可能会导致数据丢失，因此，原始 `nettrace` 文件将保留在转换后的文件旁边。</span><span class="sxs-lookup"><span data-stu-id="a2b81-169">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="using-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="a2b81-170">使用 `dotnet-trace` 收集随时间变化的计数器值</span><span class="sxs-lookup"><span data-stu-id="a2b81-170">Using `dotnet-trace` to collect counter values over time</span></span>

<span data-ttu-id="a2b81-171">如果尝试在性能敏感的设置（如生产环境）中使用 `EventCounter` 进行基本运行状况监视，并且想要收集跟踪，而不是实时监视跟踪，则还可以使用 `dotnet-trace` 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a2b81-171">If you're trying to use `EventCounter` for basic health monitoring in  performance-sensitive settings like production environments and you want to collect traces instead of watching them in real time, you can do that with `dotnet-trace` as well.</span></span>

<span data-ttu-id="a2b81-172">例如，如果想要收集运行时性能计数器值，则可以使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="a2b81-172">For example, if you want to collect runtime performance counter values, you can use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="a2b81-173">此命令通知运行时计数器每秒报告一次，以便进行轻量型运行状况监视。</span><span class="sxs-lookup"><span data-stu-id="a2b81-173">This command tells the runtime counters to be reported once every second for lightweight health monitoring.</span></span> <span data-ttu-id="a2b81-174">通过使用较大的值（例如 60）替换 `EventCounterIntervalSec=1`，可以收集计数器数据中粒度较小的跟踪。</span><span class="sxs-lookup"><span data-stu-id="a2b81-174">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows you to collect a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="a2b81-175">如果要禁用运行时事件来更进一步降低开销（和跟踪大小），可以使用以下命令禁用运行时事件和托管堆栈探查器。</span><span class="sxs-lookup"><span data-stu-id="a2b81-175">If you want to disable runtime events to reduce the overhead (and trace size) even further, you can use the following command to disable runtime events and managed stack profiler.</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

## <a name="net-providers"></a><span data-ttu-id="a2b81-176">.NET 提供程序</span><span class="sxs-lookup"><span data-stu-id="a2b81-176">.NET Providers</span></span>

<span data-ttu-id="a2b81-177">.NET Core 运行时支持以下 .NET 提供程序：</span><span class="sxs-lookup"><span data-stu-id="a2b81-177">The .NET Core runtime supports the following .NET providers.</span></span> <span data-ttu-id="a2b81-178">.NET Core 使用相同的关键字来启用 `Event Tracing for Windows (ETW)` 和 `EventPipe` 跟踪。</span><span class="sxs-lookup"><span data-stu-id="a2b81-178">.NET Core uses the same keywords to enable both `Event Tracing for Windows (ETW)` and `EventPipe` traces.</span></span>

| <span data-ttu-id="a2b81-179">提供程序名称</span><span class="sxs-lookup"><span data-stu-id="a2b81-179">Provider name</span></span>                            | <span data-ttu-id="a2b81-180">信息</span><span class="sxs-lookup"><span data-stu-id="a2b81-180">Information</span></span> |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [<span data-ttu-id="a2b81-181">运行时提供程序</span><span class="sxs-lookup"><span data-stu-id="a2b81-181">The Runtime Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[<span data-ttu-id="a2b81-182">CLR 运行时关键字</span><span class="sxs-lookup"><span data-stu-id="a2b81-182">CLR Runtime Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [<span data-ttu-id="a2b81-183">断开提供程序</span><span class="sxs-lookup"><span data-stu-id="a2b81-183">The Rundown Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[<span data-ttu-id="a2b81-184">CLR 断开关键字</span><span class="sxs-lookup"><span data-stu-id="a2b81-184">CLR Rundown Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | <span data-ttu-id="a2b81-185">启用示例探查器。</span><span class="sxs-lookup"><span data-stu-id="a2b81-185">Enables the sample profiler.</span></span> |
