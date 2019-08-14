---
title: 诊断工具概述 - .NET Core
description: 概述用于 .NET Core 应用程序的工具和技术。
author: sdmaclea
ms.author: stmaclea
ms.date: 08/05/2019
ms.topic: overview
ms.openlocfilehash: f107d15fa5584bb5a4834b5f11f1096bec7eb749
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974145"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="616f2-103">.NET Core 中提供哪些诊断工具？</span><span class="sxs-lookup"><span data-stu-id="616f2-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="616f2-104">软件并非始终按预计方式运行，但 .NET Core 具有可帮助用户快速有效地诊断这些问题的工具和 API。</span><span class="sxs-lookup"><span data-stu-id="616f2-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="616f2-105">本文可帮助用户查找各种所需的工具。</span><span class="sxs-lookup"><span data-stu-id="616f2-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggersmanaged-debuggersmd"></a>[<span data-ttu-id="616f2-106">托管调试器</span><span class="sxs-lookup"><span data-stu-id="616f2-106">Managed debuggers</span></span>](managed-debuggers.md)
<span data-ttu-id="616f2-107">借助托管调试器，用户可以与程序进行交互。</span><span class="sxs-lookup"><span data-stu-id="616f2-107">Managed debuggers allow you to interact with your program.</span></span> <span data-ttu-id="616f2-108">暂停、增量执行、检查和恢复操作可让用户深入了解代码的行为。</span><span class="sxs-lookup"><span data-stu-id="616f2-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="616f2-109">调试器是诊断易于重现的功能问题的首选。</span><span class="sxs-lookup"><span data-stu-id="616f2-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracinglogging-tracingmd"></a>[<span data-ttu-id="616f2-110">日志记录和跟踪</span><span class="sxs-lookup"><span data-stu-id="616f2-110">Logging and tracing</span></span>](logging-tracing.md)
<span data-ttu-id="616f2-111">日志记录和跟踪是相关技术。</span><span class="sxs-lookup"><span data-stu-id="616f2-111">Logging and tracing are related techniques.</span></span> <span data-ttu-id="616f2-112">它们指的是用于创建日志文件的检测代码。</span><span class="sxs-lookup"><span data-stu-id="616f2-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="616f2-113">这些文件记录了程序操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="616f2-113">The files record the details of what a program does.</span></span> <span data-ttu-id="616f2-114">这些细节可用于诊断最复杂的问题。</span><span class="sxs-lookup"><span data-stu-id="616f2-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="616f2-115">当与时间戳结合使用时，这些技术在性能调查中也非常有用。</span><span class="sxs-lookup"><span data-stu-id="616f2-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testingtestingindexmd"></a>[<span data-ttu-id="616f2-116">单元测试</span><span class="sxs-lookup"><span data-stu-id="616f2-116">Unit testing</span></span>](../testing/index.md)
<span data-ttu-id="616f2-117">单元测试是持续集成和部署高质量软件的关键组件。</span><span class="sxs-lookup"><span data-stu-id="616f2-117">Unit testing is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="616f2-118">单元测试的目的在于，在用户操作导致系统出现问题时提前向其发出警告。</span><span class="sxs-lookup"><span data-stu-id="616f2-118">Unit tests are designed to give you an early warning when you break something.</span></span>
