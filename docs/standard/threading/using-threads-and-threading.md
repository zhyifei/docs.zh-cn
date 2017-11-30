---
title: "使用线程和线程处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 9b5ec2cd-121b-4d49-b075-222cf26f2344
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80eb4c3bb98acdd1f83dbf5bcf57b2f7b295742b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="using-threads-and-threading"></a><span data-ttu-id="da6e1-102">使用线程和线程处理</span><span class="sxs-lookup"><span data-stu-id="da6e1-102">Using Threads and Threading</span></span>
<span data-ttu-id="da6e1-103">本部分中的主题讨论的创建和管理托管的线程、 如何将数据传递给托管线程和返回结果，以及如何销毁线程和处理<xref:System.Threading.ThreadAbortException>。</span><span class="sxs-lookup"><span data-stu-id="da6e1-103">The topics in this section discuss the creation and management of managed threads, how to pass data to managed threads and get results back, and how to destroy threads and handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="da6e1-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="da6e1-104">In This Section</span></span>  
 [<span data-ttu-id="da6e1-105">启动时创建线程并传递数据</span><span class="sxs-lookup"><span data-stu-id="da6e1-105">Creating Threads and Passing Data at Start Time</span></span>](../../../docs/standard/threading/creating-threads-and-passing-data-at-start-time.md)  
 <span data-ttu-id="da6e1-106">讨论并演示了如何创建托管线程，包括如何将数据传递到新线程和如何取回数据。</span><span class="sxs-lookup"><span data-stu-id="da6e1-106">Discusses and demonstrates the creation of managed threads, including how to pass data to new threads and how to get data back.</span></span>  
  
 [<span data-ttu-id="da6e1-107">暂停和恢复线程</span><span class="sxs-lookup"><span data-stu-id="da6e1-107">Pausing and Resuming Threads</span></span>](../../../docs/standard/threading/pausing-and-resuming-threads.md)  
 <span data-ttu-id="da6e1-108">讨论暂停和继续执行托管的线程的后果。</span><span class="sxs-lookup"><span data-stu-id="da6e1-108">Discusses the ramifications of pausing and resuming managed threads.</span></span>  
  
 [<span data-ttu-id="da6e1-109">销毁线程</span><span class="sxs-lookup"><span data-stu-id="da6e1-109">Destroying Threads</span></span>](../../../docs/standard/threading/destroying-threads.md)  
 <span data-ttu-id="da6e1-110">讨论销毁托管的线程，以及如何处理的后果<xref:System.Threading.ThreadAbortException>。</span><span class="sxs-lookup"><span data-stu-id="da6e1-110">Discusses the ramifications of destroying managed threads, and how to handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
 [<span data-ttu-id="da6e1-111">计划线程</span><span class="sxs-lookup"><span data-stu-id="da6e1-111">Scheduling Threads</span></span>](../../../docs/standard/threading/scheduling-threads.md)  
 <span data-ttu-id="da6e1-112">讨论线程优先级以及它们如何影响线程计划。</span><span class="sxs-lookup"><span data-stu-id="da6e1-112">Discusses thread priorities and how they affect thread scheduling.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="da6e1-113">参考</span><span class="sxs-lookup"><span data-stu-id="da6e1-113">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="da6e1-114">提供的参考文档<xref:System.Threading.Thread>类，该类表示托管的线程，无论它来自非托管代码还是在托管应用程序中创建。</span><span class="sxs-lookup"><span data-stu-id="da6e1-114">Provides reference documentation for the <xref:System.Threading.Thread> class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.Threading.ThreadStart>  
 <span data-ttu-id="da6e1-115">提供的参考文档<xref:System.Threading.ThreadStart>委托，表示无参数的线程过程。</span><span class="sxs-lookup"><span data-stu-id="da6e1-115">Provides reference documentation for the <xref:System.Threading.ThreadStart> delegate that represents parameterless thread procedures.</span></span>  
  
 <xref:System.Threading.ParameterizedThreadStart>  
 <span data-ttu-id="da6e1-116">可以轻松地将数据传递给一个线程的过程，不使用强类型。</span><span class="sxs-lookup"><span data-stu-id="da6e1-116">Provides an easy way to pass data to a thread procedure, although without strong typing.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="da6e1-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="da6e1-117">Related Sections</span></span>  
 [<span data-ttu-id="da6e1-118">线程与线程处理</span><span class="sxs-lookup"><span data-stu-id="da6e1-118">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 <span data-ttu-id="da6e1-119">提供对托管线程处理的介绍。</span><span class="sxs-lookup"><span data-stu-id="da6e1-119">Provides an introduction to managed threading.</span></span>
