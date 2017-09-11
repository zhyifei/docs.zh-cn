---
title: illegalPrepareConstrainedRegion MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- PrepareConstrainedRegions method
- managed debugging assistants (MDAs), illegal PrepareConstrainedRegions
- try/catch exception handling, managed debugging assistants
- IllegalPrepareConstrainedRegions MDA
- MDAs (managed debugging assistants), illegal PrepareConstrainedRegions
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
caps.latest.revision: 15
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6cc4e8f1ff53288206aae8f6bafe5784bbab18d8
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="illegalprepareconstrainedregion-mda"></a><span data-ttu-id="73ed1-102">illegalPrepareConstrainedRegion MDA</span><span class="sxs-lookup"><span data-stu-id="73ed1-102">illegalPrepareConstrainedRegion MDA</span></span>
<span data-ttu-id="73ed1-103"><xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=fullName> 方法调用不立即出现在异常处理程序的 `try` 语句之前时，会激活 `illegalPrepareConstrainedRegion` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="73ed1-103">The `illegalPrepareConstrainedRegion` managed debugging assistant (MDA) is activated when a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=fullName> method call does not immediately precede the `try` statement of the exception handler.</span></span> <span data-ttu-id="73ed1-104">此限制处于 MSIL 级别，因此允许调用和 `try` 之间存在非代码生成的源，比如注释。</span><span class="sxs-lookup"><span data-stu-id="73ed1-104">This restriction is at the MSIL level, so it is permissible to have non-code-generating source between the call and the `try`, such as comments.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="73ed1-105">症状</span><span class="sxs-lookup"><span data-stu-id="73ed1-105">Symptoms</span></span>  
 <span data-ttu-id="73ed1-106">受约束的执行区域 (CER) 从未以这种方式处理，而是作为简单的异常处理块（`finally` 或 `catch`）处理。</span><span class="sxs-lookup"><span data-stu-id="73ed1-106">A constrained execution region (CER) that is never treated as such, but as a simple exception handling block (`finally` or `catch`).</span></span> <span data-ttu-id="73ed1-107">因此，如果内存不足或线程中止，此区域不会运行。</span><span class="sxs-lookup"><span data-stu-id="73ed1-107">As a consequence, the region does not run in the event of an out-of-memory condition or a thread abort.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="73ed1-108">原因</span><span class="sxs-lookup"><span data-stu-id="73ed1-108">Cause</span></span>  
 <span data-ttu-id="73ed1-109">CER 的准备模式未正确执行。</span><span class="sxs-lookup"><span data-stu-id="73ed1-109">The preparation pattern for a CER is not followed correctly.</span></span>  <span data-ttu-id="73ed1-110">这是一个错误事件。</span><span class="sxs-lookup"><span data-stu-id="73ed1-110">This is an error event.</span></span> <span data-ttu-id="73ed1-111">用于将异常处理程序标记为在其 `catch`/`finally`/`fault`/`filter` 块中引入 CER 的 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 方法调用必须在 `try` 语句之前立即使用。</span><span class="sxs-lookup"><span data-stu-id="73ed1-111">The <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>method call used to mark exception handlers as introducing a CER in their `catch`/`finally`/`fault`/`filter` blocks must be used immediately before the `try` statement.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="73ed1-112">解决方法</span><span class="sxs-lookup"><span data-stu-id="73ed1-112">Resolution</span></span>  
 <span data-ttu-id="73ed1-113">确保对 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 的调用在 `try` 语句之前立即发生。</span><span class="sxs-lookup"><span data-stu-id="73ed1-113">Ensure that the call to <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> happens immediately before the `try` statement.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="73ed1-114">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="73ed1-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="73ed1-115">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="73ed1-115">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="73ed1-116">输出</span><span class="sxs-lookup"><span data-stu-id="73ed1-116">Output</span></span>  
 <span data-ttu-id="73ed1-117">MDA 显示调用 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 方法的方法名称、MSIL 偏移，以及指示调用不会立即出现在 try 块开头的消息。</span><span class="sxs-lookup"><span data-stu-id="73ed1-117">The MDA displays the name of the method calling the <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method, the MSIL offset, and a message indicating the call does not immediately precede the beginning of the try block.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="73ed1-118">配置</span><span class="sxs-lookup"><span data-stu-id="73ed1-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="73ed1-119">示例</span><span class="sxs-lookup"><span data-stu-id="73ed1-119">Example</span></span>  
 <span data-ttu-id="73ed1-120">以下示例代码演示导致激活此 MDA 的模式。</span><span class="sxs-lookup"><span data-stu-id="73ed1-120">The following code example demonstrates the pattern that causes this MDA to be activated.</span></span>  
  
```  
void MethodWithInvalidPCR()  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    Object o = new Object();  
    try  
    {  
        …  
    }  
    finally  
    {  
        …  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="73ed1-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73ed1-121">See Also</span></span>  
 <span data-ttu-id="73ed1-122"><xref:System.Runtime.InteropServices.MarshalAsAttribute></span><span class="sxs-lookup"><span data-stu-id="73ed1-122"><xref:System.Runtime.InteropServices.MarshalAsAttribute></span></span>   
 <span data-ttu-id="73ed1-123"><xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A></span><span class="sxs-lookup"><span data-stu-id="73ed1-123"><xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A></span></span>   
 <span data-ttu-id="73ed1-124">[使用托管调试助手诊断错误](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md) </span><span class="sxs-lookup"><span data-stu-id="73ed1-124">[Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md) </span></span>  
 [<span data-ttu-id="73ed1-125">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="73ed1-125">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)

