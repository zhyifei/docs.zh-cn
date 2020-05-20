---
title: 以协作方式取消线程
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
ms.openlocfilehash: 1d1433ecf39974bf9e68fe07b9d0818ac16fb544
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138126"
---
# <a name="canceling-threads-cooperatively"></a><span data-ttu-id="7c12e-102">以协作方式取消线程</span><span class="sxs-lookup"><span data-stu-id="7c12e-102">Canceling threads cooperatively</span></span>

<span data-ttu-id="7c12e-103">在 .NET Framework 4 之前，.NET Framework 不提供内置方法在线程启动以后以协作方式取消线程。</span><span class="sxs-lookup"><span data-stu-id="7c12e-103">Prior to the .NET Framework 4, the .NET Framework provided no built-in way to cancel a thread cooperatively after it was started.</span></span> <span data-ttu-id="7c12e-104">不过，从 .NET Framework 4 开始，可以使用 <xref:System.Threading.CancellationToken?displayProperty=nameWithType> 来取消线程，就像使用它们取消 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 对象或 PLINQ 查询一样。</span><span class="sxs-lookup"><span data-stu-id="7c12e-104">However, starting with the .NET Framework 4, you can use a <xref:System.Threading.CancellationToken?displayProperty=nameWithType> to cancel threads, just as you can use them to cancel <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or PLINQ queries.</span></span> <span data-ttu-id="7c12e-105">虽然 <xref:System.Threading.Thread?displayProperty=nameWithType> 类不提供对取消标记的内置支持，但可以使用采用 <xref:System.Threading.ParameterizedThreadStart> 委托的 <xref:System.Threading.Thread> 构造函数将一个标记传递给一个线程过程。</span><span class="sxs-lookup"><span data-stu-id="7c12e-105">Although the <xref:System.Threading.Thread?displayProperty=nameWithType> class does not offer built-in support for cancellation tokens, you can pass a token to a thread procedure by using the <xref:System.Threading.Thread> constructor that takes a <xref:System.Threading.ParameterizedThreadStart> delegate.</span></span> <span data-ttu-id="7c12e-106">下面的示例演示如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7c12e-106">The following example demonstrates how to do this.</span></span>  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="7c12e-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c12e-107">See also</span></span>

- [<span data-ttu-id="7c12e-108">使用线程和线程处理</span><span class="sxs-lookup"><span data-stu-id="7c12e-108">Using Threads and Threading</span></span>](using-threads-and-threading.md)
