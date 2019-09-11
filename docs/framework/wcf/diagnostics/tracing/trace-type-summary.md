---
title: 跟踪类型摘要
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 8f54f71ef63338708a29fac5557c7c7e8f257f58
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856014"
---
# <a name="trace-type-summary"></a><span data-ttu-id="374b9-102">跟踪类型摘要</span><span class="sxs-lookup"><span data-stu-id="374b9-102">Trace Type Summary</span></span>
<span data-ttu-id="374b9-103">[源级别](https://go.microsoft.com/fwlink/?LinkID=94943)定义了不同的跟踪级别：严重、错误、警告、信息和详细信息，并提供`ActivityTracing`标志的说明，该标志用于切换跟踪边界和活动传输事件的输出。</span><span class="sxs-lookup"><span data-stu-id="374b9-103">[Source Levels](https://go.microsoft.com/fwlink/?LinkID=94943) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="374b9-104">对于可以从<xref:System.Diagnostics>发出的跟踪类型，还可以查看[TraceEventType](https://go.microsoft.com/fwlink/?LinkId=95169) 。</span><span class="sxs-lookup"><span data-stu-id="374b9-104">You can also review [TraceEventType](https://go.microsoft.com/fwlink/?LinkId=95169) for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="374b9-105">下表列出了最重要的跟踪类型。</span><span class="sxs-lookup"><span data-stu-id="374b9-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="374b9-106">跟踪类型</span><span class="sxs-lookup"><span data-stu-id="374b9-106">Trace Type</span></span>|<span data-ttu-id="374b9-107">描述</span><span class="sxs-lookup"><span data-stu-id="374b9-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="374b9-108">关键</span><span class="sxs-lookup"><span data-stu-id="374b9-108">Critical</span></span>|<span data-ttu-id="374b9-109">致命错误或应用程序崩溃。</span><span class="sxs-lookup"><span data-stu-id="374b9-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="374b9-110">Error</span><span class="sxs-lookup"><span data-stu-id="374b9-110">Error</span></span>|<span data-ttu-id="374b9-111">可恢复的错误。</span><span class="sxs-lookup"><span data-stu-id="374b9-111">Recoverable error.</span></span>|  
|<span data-ttu-id="374b9-112">警告</span><span class="sxs-lookup"><span data-stu-id="374b9-112">Warning</span></span>|<span data-ttu-id="374b9-113">信息性消息。</span><span class="sxs-lookup"><span data-stu-id="374b9-113">Informational message.</span></span>|  
|<span data-ttu-id="374b9-114">Information</span><span class="sxs-lookup"><span data-stu-id="374b9-114">Information</span></span>|<span data-ttu-id="374b9-115">非严重问题。</span><span class="sxs-lookup"><span data-stu-id="374b9-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="374b9-116">详细</span><span class="sxs-lookup"><span data-stu-id="374b9-116">Verbose</span></span>|<span data-ttu-id="374b9-117">调试跟踪。</span><span class="sxs-lookup"><span data-stu-id="374b9-117">Debugging trace.</span></span>|  
|<span data-ttu-id="374b9-118">Start</span><span class="sxs-lookup"><span data-stu-id="374b9-118">Start</span></span>|<span data-ttu-id="374b9-119">开始处理逻辑单元。</span><span class="sxs-lookup"><span data-stu-id="374b9-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="374b9-120">挂起</span><span class="sxs-lookup"><span data-stu-id="374b9-120">Suspend</span></span>|<span data-ttu-id="374b9-121">挂起逻辑单元处理。</span><span class="sxs-lookup"><span data-stu-id="374b9-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="374b9-122">Resume</span><span class="sxs-lookup"><span data-stu-id="374b9-122">Resume</span></span>|<span data-ttu-id="374b9-123">继续逻辑单元处理。</span><span class="sxs-lookup"><span data-stu-id="374b9-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="374b9-124">停止</span><span class="sxs-lookup"><span data-stu-id="374b9-124">Stop</span></span>|<span data-ttu-id="374b9-125">停止处理逻辑单元。</span><span class="sxs-lookup"><span data-stu-id="374b9-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="374b9-126">传输</span><span class="sxs-lookup"><span data-stu-id="374b9-126">Transfer</span></span>|<span data-ttu-id="374b9-127">更改相关标识。</span><span class="sxs-lookup"><span data-stu-id="374b9-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="374b9-128">活动定义为上述跟踪类型的组合。</span><span class="sxs-lookup"><span data-stu-id="374b9-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="374b9-129">下面的正则表达式用于定义本地（跟踪源）范围内的理想活动，</span><span class="sxs-lookup"><span data-stu-id="374b9-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="374b9-130">这意味着活动必须满足以下条件。</span><span class="sxs-lookup"><span data-stu-id="374b9-130">This means that an activity must satisfy the following conditions.</span></span>  
  
- <span data-ttu-id="374b9-131">它必须分别由开始跟踪和停止跟踪来启动和停止</span><span class="sxs-lookup"><span data-stu-id="374b9-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
- <span data-ttu-id="374b9-132">它必须刚好在挂起跟踪或恢复跟踪之前具有传输跟踪</span><span class="sxs-lookup"><span data-stu-id="374b9-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
- <span data-ttu-id="374b9-133">如果有挂起和恢复跟踪，则在挂起跟踪和恢复跟踪之间不能有任何跟踪</span><span class="sxs-lookup"><span data-stu-id="374b9-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
- <span data-ttu-id="374b9-134">只要符合上述条件，就可以有任意多个严重/错误/警告/信息/详细/传输跟踪</span><span class="sxs-lookup"><span data-stu-id="374b9-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="374b9-135">下面的正则表达式用于定义全局范围内的理想活动，</span><span class="sxs-lookup"><span data-stu-id="374b9-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
`R+`  
  
 <span data-ttu-id="374b9-136">R 是本地范围内活动的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="374b9-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="374b9-137">这将转换为，</span><span class="sxs-lookup"><span data-stu-id="374b9-137">This translates to,</span></span>  
  
`[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+`
