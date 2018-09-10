---
title: 使用委托进行异步编程
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- BeginInvoke method
- asynchronous programming, delegates
- asynchronous delegates
- calling synchronous methods in asynchronous manner
- EndInvoke method
- calling asynchronous methods
- delegates [.NET Framework], asynchronous
- synchronous calling in asynchronous manner
ms.assetid: 38a345ca-6963-4436-9608-5c9defef9c64
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bad5372af1d771dc93a20e61090ef84126f3e1eb
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44267110"
---
# <a name="asynchronous-programming-using-delegates"></a><span data-ttu-id="46139-102">使用委托进行异步编程</span><span class="sxs-lookup"><span data-stu-id="46139-102">Asynchronous Programming Using Delegates</span></span>
<span data-ttu-id="46139-103">使用委托可通过异步方式调用同步方法。</span><span class="sxs-lookup"><span data-stu-id="46139-103">Delegates enable you to call a synchronous method in an asynchronous manner.</span></span> <span data-ttu-id="46139-104">如果同步调用委托，`Invoke` 方法将在当前线程上直接调用目标方法。</span><span class="sxs-lookup"><span data-stu-id="46139-104">When you call a delegate synchronously, the `Invoke` method calls the target method directly on the current thread.</span></span> <span data-ttu-id="46139-105">如果调用 `BeginInvoke` 方法，公共语言运行时 (CLR) 将对请求进行排队并立即返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="46139-105">If the `BeginInvoke` method is called, the common language runtime (CLR) queues the request and returns immediately to the caller.</span></span> <span data-ttu-id="46139-106">目标方法将在线程池中的某个线程上异步调用。</span><span class="sxs-lookup"><span data-stu-id="46139-106">The target method is called asynchronously on a thread from the thread pool.</span></span> <span data-ttu-id="46139-107">提交请求的原始线程可以不受限制地继续与目标方法并行执行。</span><span class="sxs-lookup"><span data-stu-id="46139-107">The original thread, which submitted the request, is free to continue executing in parallel with the target method.</span></span> <span data-ttu-id="46139-108">如果已在对 `BeginInvoke` 方法的调用中指定回叫方法，则目标方法结束时，将调用回叫方法。</span><span class="sxs-lookup"><span data-stu-id="46139-108">If a callback method has been specified in the call to the `BeginInvoke` method, the callback method is called when the target method ends.</span></span> <span data-ttu-id="46139-109">在回叫方法中，`EndInvoke` 方法将获取返回值和所有输入/输出或仅输出参数。</span><span class="sxs-lookup"><span data-stu-id="46139-109">In the callback method, the `EndInvoke` method obtains the return value and any input/output or output-only parameters.</span></span> <span data-ttu-id="46139-110">如果调用 `BeginInvoke` 时未指定回叫方法，则可能从调用 `BeginInvoke` 的线程上调用 `EndInvoke`。</span><span class="sxs-lookup"><span data-stu-id="46139-110">If no callback method is specified when calling `BeginInvoke`, `EndInvoke` can be called from the thread that called `BeginInvoke`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="46139-111">编译器应使用由用户指定的委托签名，发出具有 `Invoke`、`BeginInvoke` 和 `EndInvoke` 方法的委托类。</span><span class="sxs-lookup"><span data-stu-id="46139-111">Compilers should emit delegate classes with `Invoke`, `BeginInvoke`, and `EndInvoke` methods using the delegate signature specified by the user.</span></span> <span data-ttu-id="46139-112">`BeginInvoke` 和 `EndInvoke` 方法应标记为本机方法。</span><span class="sxs-lookup"><span data-stu-id="46139-112">The `BeginInvoke` and `EndInvoke` methods should be decorated as native.</span></span> <span data-ttu-id="46139-113">由于这些方法被标记为本机方法，CLR 将在类加载时自动提供实现。</span><span class="sxs-lookup"><span data-stu-id="46139-113">Because these methods are marked as native, the CLR automatically provides the implementation at class load time.</span></span> <span data-ttu-id="46139-114">加载程序可确保其不会被替代。</span><span class="sxs-lookup"><span data-stu-id="46139-114">The loader ensures that they are not overridden.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="46139-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="46139-115">In This Section</span></span>  
 [<span data-ttu-id="46139-116">使用异步方式调用同步方法</span><span class="sxs-lookup"><span data-stu-id="46139-116">Calling Synchronous Methods Asynchronously</span></span>](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 <span data-ttu-id="46139-117">讨论如何使用委托对普通方法进行异步调用，并提供简单的代码示例演示等待异步调用返回的四种方法。</span><span class="sxs-lookup"><span data-stu-id="46139-117">Discusses the use of delegates to make asynchronous calls to ordinary methods, and provides simple code examples that show the four ways to wait for an asynchronous call to return.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="46139-118">相关章节</span><span class="sxs-lookup"><span data-stu-id="46139-118">Related Sections</span></span>  
 [<span data-ttu-id="46139-119">基于事件的异步模式 (EAP)</span><span class="sxs-lookup"><span data-stu-id="46139-119">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 <span data-ttu-id="46139-120">介绍如何使用 .NET Framework 进行异步编程。</span><span class="sxs-lookup"><span data-stu-id="46139-120">Describes asynchronous programming with the .NET Framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46139-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="46139-121">See also</span></span>

* <xref:System.Delegate>
