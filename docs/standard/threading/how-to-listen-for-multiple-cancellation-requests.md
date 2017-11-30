---
title: "如何：侦听多个取消请求"
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
- cancellation tokens, joining
- LinkedTokenSource, how to
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 36cf338a15ad3f7d234f902c50a2dbb1b2e95847
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-multiple-cancellation-requests"></a><span data-ttu-id="139aa-102">如何：侦听多个取消请求</span><span class="sxs-lookup"><span data-stu-id="139aa-102">How to: Listen for Multiple Cancellation Requests</span></span>
<span data-ttu-id="139aa-103">此示例演示如何同时侦听除外到两个取消标记，以便你可以取消的操作，如果任一令牌请求，则。</span><span class="sxs-lookup"><span data-stu-id="139aa-103">This example shows how to listen to two cancellation tokens simultaneously so that you can cancel an operation if either token requests it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="139aa-104">某些情况下，当启用“仅我的代码”后，Visual Studio 会在引发异常的行中断运行并显示一条错误消息，该消息显示“用户代码未处理异常”。</span><span class="sxs-lookup"><span data-stu-id="139aa-104">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="139aa-105">此错误是良性的。</span><span class="sxs-lookup"><span data-stu-id="139aa-105">This error is benign.</span></span> <span data-ttu-id="139aa-106">可以按 F5 继续运行，并请参阅下面示例中所示的异常处理行为。</span><span class="sxs-lookup"><span data-stu-id="139aa-106">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="139aa-107">若要阻止 Visual Studio 的第一个错误时中断，只需取消选中下的"仅我的代码"复选框**工具、 选项、 调试、 常规**。</span><span class="sxs-lookup"><span data-stu-id="139aa-107">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="139aa-108">示例</span><span class="sxs-lookup"><span data-stu-id="139aa-108">Example</span></span>  
 <span data-ttu-id="139aa-109">在下面的示例中，<xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A>方法用于将两个标记联接成一个令牌。</span><span class="sxs-lookup"><span data-stu-id="139aa-109">In the following example, the <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> method is used to join two tokens into one token.</span></span> <span data-ttu-id="139aa-110">这使得可以将标记传递给只采用一个取消标记作为参数的方法。</span><span class="sxs-lookup"><span data-stu-id="139aa-110">This enables the token to be passed to methods that take just one cancellation token as an argument.</span></span> <span data-ttu-id="139aa-111">该示例演示一种方法必须在其中观察在传递从外部类，并在类中生成的令牌的这两个标记的常见方案。</span><span class="sxs-lookup"><span data-stu-id="139aa-111">The example demonstrates a common scenario in which a method must observe both a token passed in from outside the class, and a token generated inside the class.</span></span>  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 <span data-ttu-id="139aa-112">当链接的令牌引发<xref:System.OperationCanceledException>，传递给此异常的标记是链接的令牌，不是任何一个前置令牌。</span><span class="sxs-lookup"><span data-stu-id="139aa-112">When the linked token throws an <xref:System.OperationCanceledException>, the token that is passed to the exception is the linked token, not either of the predecessor tokens.</span></span> <span data-ttu-id="139aa-113">若要确定哪些标记已取消，请直接检查前置标记的状态。</span><span class="sxs-lookup"><span data-stu-id="139aa-113">To determine which of the tokens was canceled, check the status of the predecessor tokens directly.</span></span>  
  
 <span data-ttu-id="139aa-114">在此示例中，<xref:System.AggregateException>应永远不会引发，但因为此处捕获在实际方案中除以外的任何其他异常<xref:System.OperationCanceledException>从任务委托引发的包装在<xref:System.OperationCanceledException>。</span><span class="sxs-lookup"><span data-stu-id="139aa-114">In this example, <xref:System.AggregateException> should never be thrown, but it is caught here because in real-world scenarios any other exceptions besides <xref:System.OperationCanceledException> that are thrown from the task delegate are wrapped in a <xref:System.OperationCanceledException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="139aa-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="139aa-115">See Also</span></span>  
 [<span data-ttu-id="139aa-116">托管线程中的取消</span><span class="sxs-lookup"><span data-stu-id="139aa-116">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
