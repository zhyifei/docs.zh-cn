---
title: 使用线程和线程处理
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 9b5ec2cd-121b-4d49-b075-222cf26f2344
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 725a47cae6e3e91cf9e7385427bceece81f3c918
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584175"
---
# <a name="using-threads-and-threading"></a><span data-ttu-id="e0c92-102">使用线程和线程处理</span><span class="sxs-lookup"><span data-stu-id="e0c92-102">Using Threads and Threading</span></span>
<span data-ttu-id="e0c92-103">本节中的主题介绍了如何创建和管理托管线程、如何向托管线程传递数据并返回结果，以及如何销毁线程和处理 <xref:System.Threading.ThreadAbortException>。</span><span class="sxs-lookup"><span data-stu-id="e0c92-103">The topics in this section discuss the creation and management of managed threads, how to pass data to managed threads and get results back, and how to destroy threads and handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e0c92-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="e0c92-104">In This Section</span></span>  
 [<span data-ttu-id="e0c92-105">启动时创建线程并传递数据</span><span class="sxs-lookup"><span data-stu-id="e0c92-105">Creating Threads and Passing Data at Start Time</span></span>](../../../docs/standard/threading/creating-threads-and-passing-data-at-start-time.md)  
 <span data-ttu-id="e0c92-106">介绍并展示了如何创建托管线程，包括如何向新线程传递数据和返回数据。</span><span class="sxs-lookup"><span data-stu-id="e0c92-106">Discusses and demonstrates the creation of managed threads, including how to pass data to new threads and how to get data back.</span></span>  
  
 [<span data-ttu-id="e0c92-107">暂停和恢复线程</span><span class="sxs-lookup"><span data-stu-id="e0c92-107">Pausing and Resuming Threads</span></span>](../../../docs/standard/threading/pausing-and-resuming-threads.md)  
 <span data-ttu-id="e0c92-108">介绍了暂停和恢复托管线程的后果。</span><span class="sxs-lookup"><span data-stu-id="e0c92-108">Discusses the ramifications of pausing and resuming managed threads.</span></span>  
  
 [<span data-ttu-id="e0c92-109">销毁线程</span><span class="sxs-lookup"><span data-stu-id="e0c92-109">Destroying Threads</span></span>](../../../docs/standard/threading/destroying-threads.md)  
 <span data-ttu-id="e0c92-110">介绍了销毁托管线程的后果，以及如何处理 <xref:System.Threading.ThreadAbortException>。</span><span class="sxs-lookup"><span data-stu-id="e0c92-110">Discusses the ramifications of destroying managed threads, and how to handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
 [<span data-ttu-id="e0c92-111">计划线程</span><span class="sxs-lookup"><span data-stu-id="e0c92-111">Scheduling Threads</span></span>](../../../docs/standard/threading/scheduling-threads.md)  
 <span data-ttu-id="e0c92-112">介绍了线程优先级及其如何影响线程计划。</span><span class="sxs-lookup"><span data-stu-id="e0c92-112">Discusses thread priorities and how they affect thread scheduling.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e0c92-113">参考</span><span class="sxs-lookup"><span data-stu-id="e0c92-113">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="e0c92-114">收录了 <xref:System.Threading.Thread> 类的参考文档，无论此类是来自非托管代码，还是在托管应用中创建，它都表示托管线程。</span><span class="sxs-lookup"><span data-stu-id="e0c92-114">Provides reference documentation for the <xref:System.Threading.Thread> class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.Threading.ThreadStart>  
 <span data-ttu-id="e0c92-115">收录了表示无参数线程过程的 <xref:System.Threading.ThreadStart> 委托的参考文档。</span><span class="sxs-lookup"><span data-stu-id="e0c92-115">Provides reference documentation for the <xref:System.Threading.ThreadStart> delegate that represents parameterless thread procedures.</span></span>  
  
 <xref:System.Threading.ParameterizedThreadStart>  
 <span data-ttu-id="e0c92-116">提供了将数据轻松传递给线程过程的方法，尽管没有强类型化。</span><span class="sxs-lookup"><span data-stu-id="e0c92-116">Provides an easy way to pass data to a thread procedure, although without strong typing.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e0c92-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="e0c92-117">Related Sections</span></span>  
 [<span data-ttu-id="e0c92-118">线程与线程处理</span><span class="sxs-lookup"><span data-stu-id="e0c92-118">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 <span data-ttu-id="e0c92-119">介绍了托管线程。</span><span class="sxs-lookup"><span data-stu-id="e0c92-119">Provides an introduction to managed threading.</span></span>
