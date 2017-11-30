---
title: "使用 AsyncCallback 委托和状态对象"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, delegates
- AsyncCallback delegate, samples
- asynchronous programming, state objects
- IAsyncResult interface, samples
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e8793a78289e9b58407038f41cc9d403ff9f9940
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a><span data-ttu-id="7588b-102">使用 AsyncCallback 委托和状态对象</span><span class="sxs-lookup"><span data-stu-id="7588b-102">Using an AsyncCallback Delegate and State Object</span></span>
<span data-ttu-id="7588b-103">当你使用<xref:System.AsyncCallback>委托的一个单独的线程中的异步操作对结果进行处理，则可以使用的状态对象，两个回调之间传递信息以及如何检索最终结果。</span><span class="sxs-lookup"><span data-stu-id="7588b-103">When you use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread, you can use a state object to pass information between the callbacks and to retrieve a final result.</span></span> <span data-ttu-id="7588b-104">本主题通过扩展中的示例演示这种做法[使用 AsyncCallback 委托结束异步操作](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="7588b-104">This topic demonstrates that practice by expanding the example in [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7588b-105">示例</span><span class="sxs-lookup"><span data-stu-id="7588b-105">Example</span></span>  
 <span data-ttu-id="7588b-106">下面的代码示例演示如何使用中的异步方法<xref:System.Net.Dns>类检索指定用户的计算机的域名系统 (DNS) 信息。</span><span class="sxs-lookup"><span data-stu-id="7588b-106">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="7588b-107">此示例定义并使用`HostRequest`类来存储状态信息。</span><span class="sxs-lookup"><span data-stu-id="7588b-107">This example defines and uses the `HostRequest` class to store state information.</span></span> <span data-ttu-id="7588b-108">A`HostRequest`获取用户输入的每个计算机名创建对象。</span><span class="sxs-lookup"><span data-stu-id="7588b-108">A `HostRequest` object gets created for each computer name entered by the user.</span></span> <span data-ttu-id="7588b-109">此对象传递给<xref:System.Net.Dns.BeginGetHostByName%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="7588b-109">This object is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A> method.</span></span> <span data-ttu-id="7588b-110">`ProcessDnsInformation`每次请求完成后调用方法。</span><span class="sxs-lookup"><span data-stu-id="7588b-110">The `ProcessDnsInformation` method is called each time a request completes.</span></span> <span data-ttu-id="7588b-111">`HostRequest`对象使用检索<xref:System.IAsyncResult.AsyncState%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7588b-111">The `HostRequest` object is retrieved using the <xref:System.IAsyncResult.AsyncState%2A> property.</span></span> <span data-ttu-id="7588b-112">`ProcessDnsInformation`方法使用`HostRequest`要存储对象<xref:System.Net.IPHostEntry>该请求返回的或<xref:System.Net.Sockets.SocketException>引发的请求。</span><span class="sxs-lookup"><span data-stu-id="7588b-112">The `ProcessDnsInformation` method uses the `HostRequest` object to store the <xref:System.Net.IPHostEntry> returned by the request or a <xref:System.Net.Sockets.SocketException> thrown by the request.</span></span> <span data-ttu-id="7588b-113">应用程序完成后的所有请求，循环访问`HostRequest`对象，并显示的 DNS 信息或<xref:System.Net.Sockets.SocketException>错误消息。</span><span class="sxs-lookup"><span data-stu-id="7588b-113">When all requests are complete, the application iterates over the `HostRequest` objects and displays the DNS information or <xref:System.Net.Sockets.SocketException> error message.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="7588b-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7588b-114">See Also</span></span>  
 [<span data-ttu-id="7588b-115">基于事件的异步模式 (EAP)</span><span class="sxs-lookup"><span data-stu-id="7588b-115">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="7588b-116">基于事件的异步模式概述</span><span class="sxs-lookup"><span data-stu-id="7588b-116">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="7588b-117">使用 AsyncCallback 委托停止异步操作</span><span class="sxs-lookup"><span data-stu-id="7588b-117">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
