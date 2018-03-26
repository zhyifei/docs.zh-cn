---
title: 使用 AsyncCallback 委托结束异步操作
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ending asynchronous operations
- asynchronous programming, ending operations
- AsyncCallback delegate
- stopping asynchronous operations
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
caps.latest.revision: ''
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d71e78ecd5bf365d0a1f3efb8c8e15d4a1de6dc7
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2018
---
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a><span data-ttu-id="65e7b-102">使用 AsyncCallback 委托结束异步操作</span><span class="sxs-lookup"><span data-stu-id="65e7b-102">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>
<span data-ttu-id="65e7b-103">如果应用可以在等待异步操作结果期间继续执行其他工作，不得阻止应用一直到操作完成。</span><span class="sxs-lookup"><span data-stu-id="65e7b-103">Applications that can do other work while waiting for the results of an asynchronous operation should not block waiting until the operation completes.</span></span> <span data-ttu-id="65e7b-104">请使用下列方法之一，在应用等待异步操作完成期间继续执行指令：</span><span class="sxs-lookup"><span data-stu-id="65e7b-104">Use one of the following options to continue executing instructions while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="65e7b-105">使用 <xref:System.AsyncCallback> 委托，在单独的线程中处理异步操作结果。</span><span class="sxs-lookup"><span data-stu-id="65e7b-105">Use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread.</span></span> <span data-ttu-id="65e7b-106">本主题介绍的就是这种方法。</span><span class="sxs-lookup"><span data-stu-id="65e7b-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="65e7b-107">使用异步操作的 BeginOperationName****** 方法返回的 <xref:System.IAsyncResult> 的 <xref:System.IAsyncResult.IsCompleted%2A> 属性，确定操作是否已完成。</span><span class="sxs-lookup"><span data-stu-id="65e7b-107">Use the <xref:System.IAsyncResult.IsCompleted%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin***OperationName* method to determine whether the operation has completed.</span></span> <span data-ttu-id="65e7b-108">有关展示这种方法的示例，请参阅[轮询异步操作状态](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="65e7b-108">For an example that demonstrates this approach, see [Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="65e7b-109">示例</span><span class="sxs-lookup"><span data-stu-id="65e7b-109">Example</span></span>  
 <span data-ttu-id="65e7b-110">下面的代码示例展示了如何使用 <xref:System.Net.Dns> 类中的异步方法，检索用户指定计算机的域名系统 (DNS) 信息。</span><span class="sxs-lookup"><span data-stu-id="65e7b-110">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="65e7b-111">此示例创建引用 `ProcessDnsInformation` 方法的 <xref:System.AsyncCallback> 委托。</span><span class="sxs-lookup"><span data-stu-id="65e7b-111">This example creates an <xref:System.AsyncCallback> delegate that references the `ProcessDnsInformation` method.</span></span> <span data-ttu-id="65e7b-112">每次异步请求获取 DNS 信息，都会调用一次此方法。</span><span class="sxs-lookup"><span data-stu-id="65e7b-112">This method is called once for each asynchronous request for DNS information.</span></span>  
  
 <span data-ttu-id="65e7b-113">请注意，将用户指定主机传递给 <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.Object> 参数。</span><span class="sxs-lookup"><span data-stu-id="65e7b-113">Note that the user-specified host is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.Object> parameter.</span></span> <span data-ttu-id="65e7b-114">有关展示了如何定义和使用更复杂状态对象的示例，请参阅[使用 AsyncCallback 委托和状态对象](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)。</span><span class="sxs-lookup"><span data-stu-id="65e7b-114">For an example that demonstrates defining and using a more complex state object, see [Using an AsyncCallback Delegate and State Object](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).</span></span>  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="65e7b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65e7b-115">See Also</span></span>  
 [<span data-ttu-id="65e7b-116">基于事件的异步模式 (EAP)</span><span class="sxs-lookup"><span data-stu-id="65e7b-116">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="65e7b-117">基于事件的异步模式概述</span><span class="sxs-lookup"><span data-stu-id="65e7b-117">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="65e7b-118">使用 IAsyncResult 调用异步方法</span><span class="sxs-lookup"><span data-stu-id="65e7b-118">Calling Asynchronous Methods Using IAsyncResult</span></span>](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)  
 [<span data-ttu-id="65e7b-119">使用 AsyncCallback 委托和状态对象</span><span class="sxs-lookup"><span data-stu-id="65e7b-119">Using an AsyncCallback Delegate and State Object</span></span>](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
