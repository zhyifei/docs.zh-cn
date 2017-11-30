---
title: "轮询异步操作的状态"
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
- asynchronous programming, status polling
- polling asynchronous operation status
- status information [.NET Framework], asynchronous operations
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1f7f74a8b38c06f6a042d55c0def76ddfc5da77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="polling-for-the-status-of-an-asynchronous-operation"></a><span data-ttu-id="bbcbc-102">轮询异步操作的状态</span><span class="sxs-lookup"><span data-stu-id="bbcbc-102">Polling for the Status of an Asynchronous Operation</span></span>
<span data-ttu-id="bbcbc-103">应用程序可以完成其他工作的同时等待异步操作的结果不应阻止等待操作完成。</span><span class="sxs-lookup"><span data-stu-id="bbcbc-103">Applications that can do other work while waiting for the results of an asynchronous operation should not block waiting until the operation completes.</span></span> <span data-ttu-id="bbcbc-104">使用以下选项之一可继续在等待异步操作以完成时执行的说明：</span><span class="sxs-lookup"><span data-stu-id="bbcbc-104">Use one of the following options to continue executing instructions while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="bbcbc-105">使用<xref:System.IAsyncResult.IsCompleted%2A>属性<xref:System.IAsyncResult>异步操作返回**开始** *OperationName*方法来确定是否已完成该操作。</span><span class="sxs-lookup"><span data-stu-id="bbcbc-105">Use the <xref:System.IAsyncResult.IsCompleted%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin** *OperationName* method to determine whether the operation has completed.</span></span> <span data-ttu-id="bbcbc-106">此方法被称为轮询，并在本主题中所示。</span><span class="sxs-lookup"><span data-stu-id="bbcbc-106">This approach is known as polling and is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="bbcbc-107">使用<xref:System.AsyncCallback>委托的一个单独的线程中的异步操作对结果进行处理。</span><span class="sxs-lookup"><span data-stu-id="bbcbc-107">Use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread.</span></span> <span data-ttu-id="bbcbc-108">有关演示此方法的示例，请参阅[使用 AsyncCallback 委托结束异步操作](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="bbcbc-108">For an example that demonstrates this approach, see [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbcbc-109">示例</span><span class="sxs-lookup"><span data-stu-id="bbcbc-109">Example</span></span>  
 <span data-ttu-id="bbcbc-110">下面的代码示例演示如何使用中的异步方法<xref:System.Net.Dns>类检索指定用户的计算机的域名系统信息。</span><span class="sxs-lookup"><span data-stu-id="bbcbc-110">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="bbcbc-111">此示例将启动异步操作，然后输出句点 ("。") 在控制台完成该操作之前。</span><span class="sxs-lookup"><span data-stu-id="bbcbc-111">This example starts the asynchronous operation and then prints periods (".") at the console until the operation is complete.</span></span> <span data-ttu-id="bbcbc-112">请注意， **null** (**执行任何操作**在 Visual Basic 中) 为传递<xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.AsyncCallback>和<xref:System.Object>参数因为这些自变量并不需要使用此方法时。</span><span class="sxs-lookup"><span data-stu-id="bbcbc-112">Note that **null** (**Nothing** in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.AsyncCallback> and <xref:System.Object> parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="bbcbc-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bbcbc-113">See Also</span></span>  
 [<span data-ttu-id="bbcbc-114">基于事件的异步模式 (EAP)</span><span class="sxs-lookup"><span data-stu-id="bbcbc-114">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="bbcbc-115">基于事件的异步模式概述</span><span class="sxs-lookup"><span data-stu-id="bbcbc-115">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
