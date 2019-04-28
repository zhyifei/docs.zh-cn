---
title: 公共语言运行时中的 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d059a5d4df402b309f628bf3e9393114c4cdeec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723181"
---
# <a name="etw-events-in-the-common-language-runtime"></a><span data-ttu-id="c0637-102">公共语言运行时中的 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="c0637-102">ETW Events in the Common Language Runtime</span></span>
<span data-ttu-id="c0637-103">公共语言运行时 (CLR) 通过大量的调试和分析事件，提供有用的 Windows 事件跟踪 (ETW) 诊断信息。</span><span class="sxs-lookup"><span data-stu-id="c0637-103">The common language runtime (CLR) provides useful event tracing for Windows (ETW) diagnostic information through a large variety of debugging and profiling events.</span></span> <span data-ttu-id="c0637-104">CLR ETW 事件利用 Windows ETW 跟踪系统来扩充公共语言运行时所提供的现有分析和调试支持。</span><span class="sxs-lookup"><span data-stu-id="c0637-104">CLR ETW events leverage the Windows ETW tracing system to augment the existing profiling and debugging support provided by the common language runtime.</span></span>  
  
 <span data-ttu-id="c0637-105">有关 ETW 的详细信息，请参阅 MSDN 上的[使用 ETW 改善调试和性能优化](https://go.microsoft.com/fwlink/?LinkID=161142)一文。</span><span class="sxs-lookup"><span data-stu-id="c0637-105">More information about ETW is available in the article [Improve Debugging and Performance Tuning with ETW](https://go.microsoft.com/fwlink/?LinkID=161142) on MSDN.</span></span> <span data-ttu-id="c0637-106">有关 Xperf 的详细信息，请参阅 NTDebugging 博客中的 [Windows Performance Toolkit - Xperf](https://go.microsoft.com/fwlink/?LinkID=161144)（Windows 性能工具包 - Xperf）。</span><span class="sxs-lookup"><span data-stu-id="c0637-106">Information about Xperf can be found in the entry [Windows Performance Toolkit - Xperf](https://go.microsoft.com/fwlink/?LinkID=161144) in the NTDebugging blog.</span></span>  
  
 <span data-ttu-id="c0637-107">在事件主题中介绍的所有事件要求 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="c0637-107">The [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] or later is required for all the events described in the event topics.</span></span> <span data-ttu-id="c0637-108">Windows Vista 操作系统是支持的最低客户端，而 Windows Server 2008 是支持的最低服务器。</span><span class="sxs-lookup"><span data-stu-id="c0637-108">The Windows Vista operating system is the minimum supported client, and Windows Server 2008 is the minimum supported server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0637-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="c0637-109">In This Section</span></span>  
 [<span data-ttu-id="c0637-110">控制 .NET Framework 日志记录</span><span class="sxs-lookup"><span data-stu-id="c0637-110">Controlling .NET Framework Logging</span></span>](../../../docs/framework/performance/controlling-logging.md)  
 <span data-ttu-id="c0637-111">介绍用于捕获和查看 ETW 事件的工具和命令。</span><span class="sxs-lookup"><span data-stu-id="c0637-111">Describes the tools and commands for capturing and viewing ETW events.</span></span>  
  
 [<span data-ttu-id="c0637-112">CLR ETW 提供程序</span><span class="sxs-lookup"><span data-stu-id="c0637-112">CLR ETW Providers</span></span>](../../../docs/framework/performance/clr-etw-providers.md)  
 <span data-ttu-id="c0637-113">提供有关运行时和断开提供程序，以及如何使用它们收集 ETW 数据的信息。</span><span class="sxs-lookup"><span data-stu-id="c0637-113">Provides information about the runtime and rundown providers, and how you can use them for ETW data collection.</span></span>  
  
 [<span data-ttu-id="c0637-114">CLR ETW 关键字和级别</span><span class="sxs-lookup"><span data-stu-id="c0637-114">CLR ETW Keywords and Levels</span></span>](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)  
 <span data-ttu-id="c0637-115">介绍运行时和断开提供程序的关键字，可通过这些关键字按类别筛选事件。</span><span class="sxs-lookup"><span data-stu-id="c0637-115">Describes the keywords for the Runtime and Rundown providers that enable the filtering of events by category.</span></span>  
  
 [<span data-ttu-id="c0637-116">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="c0637-116">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)  
 <span data-ttu-id="c0637-117">提供有关 CLR ETW 事件及其关键字、级别和事件数据的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c0637-117">Provides detailed information about CLR ETW events, their keywords, levels, and event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0637-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0637-118">See also</span></span>

- [<span data-ttu-id="c0637-119">.NET Framework 中的 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="c0637-119">ETW Events in the .NET Framework</span></span>](../../../docs/framework/performance/etw-events.md)
