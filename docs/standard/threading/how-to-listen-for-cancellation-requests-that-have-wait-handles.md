---
title: "如何：侦听具有等待句柄的取消请求"
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
helpviewer_keywords: cancellation, waiting with wait handles
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1eaa84d924fde63e94c36fab50a809c7c03f075
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-that-have-wait-handles"></a><span data-ttu-id="808fb-102">如何：侦听具有等待句柄的取消请求</span><span class="sxs-lookup"><span data-stu-id="808fb-102">How to: Listen for Cancellation Requests That Have Wait Handles</span></span>
<span data-ttu-id="808fb-103">如果它等待事件接收信号时，被阻止方法，它不能检查取消标记的值并及时响应。</span><span class="sxs-lookup"><span data-stu-id="808fb-103">If a method is blocked while it is waiting for an event to be signaled, it cannot check the value of the cancellation token and respond in a timely manner.</span></span> <span data-ttu-id="808fb-104">第一个示例演示如何解决此问题，如你正在使用事件时<xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>不以本机方式支持统一的取消框架。</span><span class="sxs-lookup"><span data-stu-id="808fb-104">The first example shows how to solve this problem when you are working with events such as <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> that do not natively support the unified cancellation framework.</span></span> <span data-ttu-id="808fb-105">第二个示例演示一种更简单的方法，使用<xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>，支持统一取消。</span><span class="sxs-lookup"><span data-stu-id="808fb-105">The second example shows a more streamlined approach that uses <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, which does support unified cancellation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="808fb-106">某些情况下，当启用“仅我的代码”后，Visual Studio 会在引发异常的行中断运行并显示一条错误消息，该消息显示“用户代码未处理异常”。</span><span class="sxs-lookup"><span data-stu-id="808fb-106">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="808fb-107">此错误是良性的。</span><span class="sxs-lookup"><span data-stu-id="808fb-107">This error is benign.</span></span> <span data-ttu-id="808fb-108">可以按 F5 继续运行，并请参阅下面示例中所示的异常处理行为。</span><span class="sxs-lookup"><span data-stu-id="808fb-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="808fb-109">若要阻止 Visual Studio 的第一个错误时中断，只需取消选中下的"仅我的代码"复选框**工具、 选项、 调试、 常规**。</span><span class="sxs-lookup"><span data-stu-id="808fb-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="808fb-110">示例</span><span class="sxs-lookup"><span data-stu-id="808fb-110">Example</span></span>  
 <span data-ttu-id="808fb-111">下面的示例使用<xref:System.Threading.ManualResetEvent>来演示如何取消阻止不支持统一的取消的等待句柄。</span><span class="sxs-lookup"><span data-stu-id="808fb-111">The following example uses a <xref:System.Threading.ManualResetEvent> to demonstrate how to unblock wait handles that do not support unified cancellation.</span></span>  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="808fb-112">示例</span><span class="sxs-lookup"><span data-stu-id="808fb-112">Example</span></span>  
 <span data-ttu-id="808fb-113">下面的示例使用<xref:System.Threading.ManualResetEventSlim>来演示如何取消阻止协调基元支持统一取消。</span><span class="sxs-lookup"><span data-stu-id="808fb-113">The following example uses a <xref:System.Threading.ManualResetEventSlim> to demonstrate how to unblock coordination primitives that do support unified cancellation.</span></span> <span data-ttu-id="808fb-114">相同的方法可与其他轻型坐标基元，例如<xref:System.Threading.Semaphore>`Slim`和<xref:System.Threading.CountdownEvent>。</span><span class="sxs-lookup"><span data-stu-id="808fb-114">The same approach can be used with other lightweight coordination primitives, such as <xref:System.Threading.Semaphore>`Slim` and <xref:System.Threading.CountdownEvent>.</span></span>  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="808fb-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="808fb-115">See Also</span></span>  
 [<span data-ttu-id="808fb-116">托管线程中的取消</span><span class="sxs-lookup"><span data-stu-id="808fb-116">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
