---
title: 诊断工具概述 - .NET Core
description: 概述用于 .NET Core 应用程序的工具和技术。
author: sdmaclea
ms.author: stmaclea
ms.date: 12/17/2019
ms.topic: overview
ms.openlocfilehash: 20374c53769bf19901b042e0909175718665b523
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75341482"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="d8958-103">.NET Core 中提供哪些诊断工具？</span><span class="sxs-lookup"><span data-stu-id="d8958-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="d8958-104">软件并非始终按预计方式运行，但 .NET Core 具有可帮助用户快速有效地诊断这些问题的工具和 API。</span><span class="sxs-lookup"><span data-stu-id="d8958-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="d8958-105">本文可帮助用户查找各种所需的工具。</span><span class="sxs-lookup"><span data-stu-id="d8958-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="d8958-106">托管调试器</span><span class="sxs-lookup"><span data-stu-id="d8958-106">Managed debuggers</span></span>

<span data-ttu-id="d8958-107">借助[托管调试器](managed-debuggers.md)，用户可以与程序进行交互。</span><span class="sxs-lookup"><span data-stu-id="d8958-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="d8958-108">暂停、增量执行、检查和恢复操作可让用户深入了解代码的行为。</span><span class="sxs-lookup"><span data-stu-id="d8958-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="d8958-109">调试器是诊断易于重现的功能问题的首选。</span><span class="sxs-lookup"><span data-stu-id="d8958-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="d8958-110">日志记录和跟踪</span><span class="sxs-lookup"><span data-stu-id="d8958-110">Logging and tracing</span></span>

<span data-ttu-id="d8958-111">[日志记录和跟踪](logging-tracing.md)是相关技术。</span><span class="sxs-lookup"><span data-stu-id="d8958-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="d8958-112">它们指的是用于创建日志文件的检测代码。</span><span class="sxs-lookup"><span data-stu-id="d8958-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="d8958-113">这些文件记录了程序操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d8958-113">The files record the details of what a program does.</span></span> <span data-ttu-id="d8958-114">这些细节可用于诊断最复杂的问题。</span><span class="sxs-lookup"><span data-stu-id="d8958-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="d8958-115">当与时间戳结合使用时，这些技术在性能调查中也非常有用。</span><span class="sxs-lookup"><span data-stu-id="d8958-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="d8958-116">单元测试</span><span class="sxs-lookup"><span data-stu-id="d8958-116">Unit testing</span></span>

<span data-ttu-id="d8958-117">[单元测试](../testing/index.md)是持续集成和部署高质量软件的关键组件。</span><span class="sxs-lookup"><span data-stu-id="d8958-117">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="d8958-118">单元测试的目的在于，在用户操作导致系统出现问题时提前向其发出警告。</span><span class="sxs-lookup"><span data-stu-id="d8958-118">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="net-core-dotnet-diagnostic-global-tools"></a><span data-ttu-id="d8958-119">.NET Core dotnet 诊断全局工具</span><span class="sxs-lookup"><span data-stu-id="d8958-119">.NET Core dotnet diagnostic Global Tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="d8958-120">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="d8958-120">dotnet-counters</span></span>

<span data-ttu-id="d8958-121">[dotnet-counters](dotnet-counters.md) 是一个性能监视工具，用于初级运行状况监视和性能调查。</span><span class="sxs-lookup"><span data-stu-id="d8958-121">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="d8958-122">它通过 <xref:System.Diagnostics.Tracing.EventCounter> API 观察已发布的性能计数器值。</span><span class="sxs-lookup"><span data-stu-id="d8958-122">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="d8958-123">例如，可以快速监视 CPU 使用情况或 .NET Core 应用程序中的异常率等指标。</span><span class="sxs-lookup"><span data-stu-id="d8958-123">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="d8958-124">dotnet-dump</span><span class="sxs-lookup"><span data-stu-id="d8958-124">dotnet-dump</span></span>

<span data-ttu-id="d8958-125">通过 [dotnet-dump](dotnet-dump.md) 工具，可在不使用本机调试器的情况下收集和分析 Windows 和 Linux 核心转储。</span><span class="sxs-lookup"><span data-stu-id="d8958-125">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="d8958-126">dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="d8958-126">dotnet-trace</span></span>

<span data-ttu-id="d8958-127">分析数据通过 .NET Core 中的 `EventPipe` 公开。</span><span class="sxs-lookup"><span data-stu-id="d8958-127">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="d8958-128">通过 [dotnet-trace](dotnet-trace.md) 工具，可以使用来自应用的有意思的分析数据，这些数据可帮助你分析应用运行缓慢的根本原因。</span><span class="sxs-lookup"><span data-stu-id="d8958-128">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>

## <a name="net-core-diagnostics-tutorials"></a><span data-ttu-id="d8958-129">.NET Core 诊断教程</span><span class="sxs-lookup"><span data-stu-id="d8958-129">.NET Core diagnostics tutorials</span></span>

### <a name="debug-a-memory-leak"></a><span data-ttu-id="d8958-130">调试内存泄露</span><span class="sxs-lookup"><span data-stu-id="d8958-130">Debug a memory leak</span></span>

<span data-ttu-id="d8958-131">[教程：调试内存泄漏](debug-memory-leak.md)演示了如何查找内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="d8958-131">[Tutorial: Debug a memory leak](debug-memory-leak.md) walks through finding a memory leak.</span></span> <span data-ttu-id="d8958-132">[dotnet-counters](dotnet-counters.md) 工具用于确认泄露，[dotnet-dump](dotnet-dump.md) 工具用于诊断泄露。</span><span class="sxs-lookup"><span data-stu-id="d8958-132">The [dotnet-counters](dotnet-counters.md) tool is used to confirm the leak and the [dotnet-dump](dotnet-dump.md) tool is used to diagnose the leak.</span></span>
