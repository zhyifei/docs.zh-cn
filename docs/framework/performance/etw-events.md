---
title: ETW Events in the .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework ETW events
- ETW events in the .NET Framework
ms.assetid: d186276f-6afb-4dfd-bf3c-4251edc2c299
caps.latest.revision: 9
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 53bd8bce147e8939a975f483223db08296707e3d
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="etw-events-in-the-net-framework"></a><span data-ttu-id="44b87-102">ETW Events in the .NET Framework</span><span class="sxs-lookup"><span data-stu-id="44b87-102">ETW Events in the .NET Framework</span></span>
<span data-ttu-id="44b87-103">Windows 事件跟踪 (ETW) 是 Windows 操作系统提供的高性能、低开销的可缩放跟踪系统。</span><span class="sxs-lookup"><span data-stu-id="44b87-103">Event tracing for Windows (ETW) is a high-performance, low-overhead, scalable tracing system provided by Windows operating systems.</span></span> <span data-ttu-id="44b87-104">它可补充 .NET Framework 所提供的分析和调试支持，可用于排除各种问题。</span><span class="sxs-lookup"><span data-stu-id="44b87-104">It supplements the profiling and debugging support provided by the .NET Framework and can be used to troubleshoot a variety of scenarios.</span></span> <span data-ttu-id="44b87-105">有关 ETW 的常规信息，请参阅 MSDN 库中的[使用 ETW 改善调试和性能优化](http://go.microsoft.com/fwlink/?LinkID=161142)。</span><span class="sxs-lookup"><span data-stu-id="44b87-105">For general information about ETW, see [Improve Debugging and Performance Tuning with ETW](http://go.microsoft.com/fwlink/?LinkID=161142) in the MSDN Library.</span></span>  
  
 <span data-ttu-id="44b87-106">在 .NET Framework 中，ETW 事件跟踪适用于公共语言运行时 (CLR)、[任务并行库](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)和 [并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)。</span><span class="sxs-lookup"><span data-stu-id="44b87-106">In the .NET Framework, ETW event tracing is available for the common language runtime (CLR), the [Task Parallel Library](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md), and [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="44b87-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="44b87-107">In This Section</span></span>  
 [<span data-ttu-id="44b87-108">任务并行库和 PLINQ 中的 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="44b87-108">ETW Events in Task Parallel Library and PLINQ</span></span>](../../../docs/framework/performance/etw-events-in-task-parallel-library-and-plinq.md)  
 <span data-ttu-id="44b87-109">介绍如何分析并行应用程序代码。</span><span class="sxs-lookup"><span data-stu-id="44b87-109">Describes how to profile parallel application code.</span></span>  
  
 [<span data-ttu-id="44b87-110">公共语言运行时中的 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="44b87-110">ETW Events in the Common Language Runtime</span></span>](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)  
 <span data-ttu-id="44b87-111">介绍 CLR ETW 事件如何补充公共语言运行时所提供的分析和调试支持。</span><span class="sxs-lookup"><span data-stu-id="44b87-111">Describes how CLR ETW events supplement the profiling and debugging support provided by the common language runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44b87-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44b87-112">See Also</span></span>  
 <span data-ttu-id="44b87-113">[CLR ETW 事件](../../../docs/framework/performance/clr-etw-events.md) </span><span class="sxs-lookup"><span data-stu-id="44b87-113">[CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) </span></span>  
 <span data-ttu-id="44b87-114">[任务并行库 (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md) </span><span class="sxs-lookup"><span data-stu-id="44b87-114">[Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md) </span></span>  
 [<span data-ttu-id="44b87-115">并行 LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="44b87-115">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)

