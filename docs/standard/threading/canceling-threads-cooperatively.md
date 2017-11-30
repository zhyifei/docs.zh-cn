---
title: "以协作方式取消线程"
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
helpviewer_keywords: threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 482f48b347af1a4f76231abcb15abc2f4dba168b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="canceling-threads-cooperatively"></a><span data-ttu-id="50a49-102">以协作方式取消线程</span><span class="sxs-lookup"><span data-stu-id="50a49-102">Canceling Threads Cooperatively</span></span>
<span data-ttu-id="50a49-103">在 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]之前，.NET Framework 不提供内置方法在线程启动以后以协作方式取消线程。</span><span class="sxs-lookup"><span data-stu-id="50a49-103">Prior to the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the .NET Framework provided no built-in way to cancel a thread cooperatively after it was started.</span></span> <span data-ttu-id="50a49-104">但是，在[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]，你可以使用取消标记来取消线程，就像可以使用它们来取消<xref:System.Threading.Tasks.Task?displayProperty=nameWithType>对象或 PLINQ 查询。</span><span class="sxs-lookup"><span data-stu-id="50a49-104">However, in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use cancellation tokens to cancel threads, just as you can use them to cancel <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or PLINQ queries.</span></span> <span data-ttu-id="50a49-105">尽管<xref:System.Threading.Thread?displayProperty=nameWithType>类不提供对取消标记的内置支持，你可以通过将令牌传递给一个线程的过程<xref:System.Threading.Thread>构造函数采用<xref:System.Threading.ParameterizedThreadStart>委托。</span><span class="sxs-lookup"><span data-stu-id="50a49-105">Although the <xref:System.Threading.Thread?displayProperty=nameWithType> class does not offer built-in support for cancellation tokens, you can pass a token to a thread procedure by using the <xref:System.Threading.Thread> constructor that takes a <xref:System.Threading.ParameterizedThreadStart> delegate.</span></span> <span data-ttu-id="50a49-106">下面的示例演示如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="50a49-106">The following example demonstrates how to do this.</span></span>  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="50a49-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50a49-107">See Also</span></span>  
 [<span data-ttu-id="50a49-108">使用线程和线程处理</span><span class="sxs-lookup"><span data-stu-id="50a49-108">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
