---
title: "如何：通过轮询侦听取消请求"
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
helpviewer_keywords: cancellation, how to poll for requests
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f0e05e3f66d591a28d7e84d358934959764dab6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-by-polling"></a><span data-ttu-id="1d087-102">如何：通过轮询侦听取消请求</span><span class="sxs-lookup"><span data-stu-id="1d087-102">How to: Listen for Cancellation Requests by Polling</span></span>
<span data-ttu-id="1d087-103">下面的示例演示一个用户代码可以按固定的间隔，以查看从调用线程是否已请求取消轮询取消标记的方法。</span><span class="sxs-lookup"><span data-stu-id="1d087-103">The following example shows one way that user code can poll a cancellation token at regular intervals to see whether cancellation has been requested from the calling thread.</span></span> <span data-ttu-id="1d087-104">此示例使用<xref:System.Threading.Tasks.Task?displayProperty=nameWithType>类型，但相同的模式适用于异步操作直接通过创建<xref:System.Threading.ThreadPool?displayProperty=nameWithType>类型或<xref:System.Threading.Thread?displayProperty=nameWithType>类型。</span><span class="sxs-lookup"><span data-stu-id="1d087-104">This example uses the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> type, but the same pattern applies to asynchronous operations created directly by the <xref:System.Threading.ThreadPool?displayProperty=nameWithType> type or the <xref:System.Threading.Thread?displayProperty=nameWithType> type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d087-105">示例</span><span class="sxs-lookup"><span data-stu-id="1d087-105">Example</span></span>  
 <span data-ttu-id="1d087-106">轮询需要某种类型的循环或递归代码，可以定期读取的布尔值<xref:System.Threading.CancellationToken.IsCancellationRequested%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="1d087-106">Polling requires some kind of loop or recursive code that can periodically read the value of the Boolean <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property.</span></span> <span data-ttu-id="1d087-107">如果你使用<xref:System.Threading.Tasks.Task?displayProperty=nameWithType>类型，并等待任务完成调用线程上，你可以使用<xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>方法来检查该属性，并引发异常。</span><span class="sxs-lookup"><span data-stu-id="1d087-107">If you are using the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> type and you are waiting for the task to complete on the calling thread, you can use the <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> method to check the property and throw the exception.</span></span> <span data-ttu-id="1d087-108">通过使用此方法，你确保正确的异常引发到请求的响应中。</span><span class="sxs-lookup"><span data-stu-id="1d087-108">By using this method, you ensure that the correct exception is thrown in response to a request.</span></span> <span data-ttu-id="1d087-109">如果你使用<xref:System.Threading.Tasks.Task>，然后调用此方法优于手动引发<xref:System.OperationCanceledException>。</span><span class="sxs-lookup"><span data-stu-id="1d087-109">If you are using a <xref:System.Threading.Tasks.Task>, then calling this method is better than manually throwing an <xref:System.OperationCanceledException>.</span></span> <span data-ttu-id="1d087-110">如果不需要引发异常，则仅可以检查该属性，并从该方法返回，如果属性是`true`。</span><span class="sxs-lookup"><span data-stu-id="1d087-110">If you do not have to throw the exception, then you can just check the property and return from the method if the property is `true`.</span></span>  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 <span data-ttu-id="1d087-111">调用<xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>非常快，不会引入的很大的开销，在循环中。</span><span class="sxs-lookup"><span data-stu-id="1d087-111">Calling <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> is extremely fast and does not introduce significant overhead in loops.</span></span>  
  
 <span data-ttu-id="1d087-112">如果你调用<xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>，只需显式检查<xref:System.Threading.CancellationToken.IsCancellationRequested%2A>属性，如果你有其他工作要做以响应取消除了引发异常。</span><span class="sxs-lookup"><span data-stu-id="1d087-112">If you are calling <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, you only have to explicitly check the <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property if you have other work to do in response to the cancellation besides throwing the exception.</span></span> <span data-ttu-id="1d087-113">在此示例中，你可以看到，代码实际访问该属性两次： 一次中的显式访问权限和再次在<xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="1d087-113">In this example, you can see that the code actually accesses the property twice: once in the explicit access and again in the <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> method.</span></span> <span data-ttu-id="1d087-114">但是，由于读取 act<xref:System.Threading.CancellationToken.IsCancellationRequested%2A>属性包括只有一个可变读取每次访问的指令，两次访问并不重要从性能角度。</span><span class="sxs-lookup"><span data-stu-id="1d087-114">But because the act of reading the <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property involves only one volatile read instruction per access, the double access is not significant from a performance perspective.</span></span> <span data-ttu-id="1d087-115">它是调用方法，而不是手动引发仍优于<xref:System.OperationCanceledException>。</span><span class="sxs-lookup"><span data-stu-id="1d087-115">It is still preferable to call the method rather than manually throw the <xref:System.OperationCanceledException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d087-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d087-116">See Also</span></span>  
 [<span data-ttu-id="1d087-117">托管线程中的取消</span><span class="sxs-lookup"><span data-stu-id="1d087-117">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
