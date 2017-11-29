---
title: invalidCERCall MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- invalid CER calls
- InvalidCERCall MDA
- MDAs (managed debugging assistants), CER calls
- constrained execution regions
- CER calls
- managed debugging assistants (MDAs), CER calls
ms.assetid: c4577410-602e-44e5-9dab-fea7c55bcdfe
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0c051e1513f8e8ad1735085cb93f106b4fb9b0d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="invalidcercall-mda"></a><span data-ttu-id="e6a3c-102">invalidCERCall MDA</span><span class="sxs-lookup"><span data-stu-id="e6a3c-102">invalidCERCall MDA</span></span>
<span data-ttu-id="e6a3c-103">方法没有可靠性协定或具有过弱协定时，如果受约束的执行区域 (CER) 图内存在对此类方法的调用，将激活 `invalidCERCall` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-103">The `invalidCERCall` managed debugging assistant (MDA) is activated when there is a call within the constrained execution region (CER) graph to a method that has no reliability contract or an excessively weak contract.</span></span> <span data-ttu-id="e6a3c-104">弱协定是这样的一种协定：它声明最坏情况下的状态损坏的范围超出传递给调用的实例，即 <xref:System.AppDomain> 或进程状态可能会损坏，或者在 CER 中调用它时不可始终明确地计算其结果。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-104">A weak contract is a contract that declares that the worst case state corruption is of greater scope than the instance passed to the call, that is, the <xref:System.AppDomain> or process state may become corrupted or that its result is not always deterministically computable when called within a CER.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="e6a3c-105">症状</span><span class="sxs-lookup"><span data-stu-id="e6a3c-105">Symptoms</span></span>  
 <span data-ttu-id="e6a3c-106">在 CER 中执行代码时得到意外结果。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-106">Unexpected results when executing code in a CER.</span></span> <span data-ttu-id="e6a3c-107">这些症状并不明确。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-107">The symptoms are not specific.</span></span> <span data-ttu-id="e6a3c-108">它们可能是在调入不可靠的方法时发生的意外 <xref:System.OutOfMemoryException>、<xref:System.Threading.ThreadAbortException> 或其他异常，因为运行时没有预先准备该方法，或没有提供相应的保护以使它在运行时不引发 <xref:System.Threading.ThreadAbortException> 异常。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-108">They could be an unexpected <xref:System.OutOfMemoryException>, a <xref:System.Threading.ThreadAbortException>, or other exceptions at the call into the unreliable method because the runtime did not prepare it ahead of time or protect it from <xref:System.Threading.ThreadAbortException> exceptions at run time.</span></span> <span data-ttu-id="e6a3c-109">更大的威胁在于，该方法在运行时产生的任何异常可能将 <xref:System.AppDomain> 或进程置于不稳定状态，这违背了 CER 的目标。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-109">A greater threat is that any exception resulting from the method at run time could leave the <xref:System.AppDomain> or process in an unstable state, which is contrary to the objective of a CER.</span></span> <span data-ttu-id="e6a3c-110">创建 CER 的目的就是避免这样的状态损坏。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-110">The reason a CER is created is to avoid state corruptions such as this.</span></span> <span data-ttu-id="e6a3c-111">损坏状态的症状特定于应用程序，因为一致状态的定义在应用程序之间并不相同。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-111">The symptoms of corrupt state are application specific because the definition of consistent state is different between applications.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="e6a3c-112">原因</span><span class="sxs-lookup"><span data-stu-id="e6a3c-112">Cause</span></span>  
 <span data-ttu-id="e6a3c-113">CER 中的代码调用没有 <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> 或具有弱 <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> 的函数，该函数不适合在 CER 中运行。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-113">Code within a CER is calling a function with no <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> or with a weak <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> that is not compatible with running in a CER.</span></span>  
  
 <span data-ttu-id="e6a3c-114">根据可靠性协定语法，弱协定是未指定 <xref:System.Runtime.ConstrainedExecution.Consistency> 枚举值或指定 <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptProcess>、<xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptAppDomain> 或 <xref:System.Runtime.ConstrainedExecution.Cer.None> 的 <xref:System.Runtime.ConstrainedExecution.Consistency> 值的协定。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-114">In terms of reliability contract syntax, a weak contract is a contract that does not specify a <xref:System.Runtime.ConstrainedExecution.Consistency> enumeration value or specifies a <xref:System.Runtime.ConstrainedExecution.Consistency> value of <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptProcess>, <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptAppDomain>, or <xref:System.Runtime.ConstrainedExecution.Cer.None>.</span></span> <span data-ttu-id="e6a3c-115">上述任一条件均指示调用的代码可能妨碍 CER 中的其他代码维护一致状态的工作。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-115">Any of these conditions indicates that the code called may impede the efforts of the other code in the CER to maintain consistent state.</span></span>  <span data-ttu-id="e6a3c-116">CER 允许代码以非常明确的方式处理错误，维护对应用程序很重要的内部不变量并允许它在面对诸如内存不足异常之类的瞬态错误时继续运行。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-116">CERs allow code to treat errors in a very deterministic manner, maintaining internal invariants that are important to the application and allowing it to continue running in the face of transient errors such as out-of-memory exceptions.</span></span>  
  
 <span data-ttu-id="e6a3c-117">此 MDA 的激活指示一种可能性：CER 中正在调用的方法会以调用方未预期的方式或导致 <xref:System.AppDomain> 进程状态损坏或不可恢复的方式失败。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-117">The activation of this MDA indicates a possibility the method being called in the CER can fail in a way that the caller did not expect or that leaves the <xref:System.AppDomain> or process state corrupted or unrecoverable.</span></span> <span data-ttu-id="e6a3c-118">当然，调用的代码可能正确执行，并且问题只是缺少协定。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-118">Of course, the called code might execute correctly and the problem is simply a missing contract.</span></span> <span data-ttu-id="e6a3c-119">但是，编写可靠代码所涉及的是一些细微的问题，缺少协定是代码可能无法正确执行的一个很好的指示器。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-119">However, the issues involved in writing reliable code are subtle and the absence of a contract is a good indicator the code might not execute correctly.</span></span> <span data-ttu-id="e6a3c-120">协定是程序员已可靠地编写代码并承诺这些保证不会在将来的代码修订中改变的指示器。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-120">The contracts are indicators that the programmer has coded reliably and also promises that these guarantees will not change in future revisions of the code.</span></span>  <span data-ttu-id="e6a3c-121">也就是说，协定是意图声明，而不只是实现细节。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-121">That is, the contracts are declarations of intent and not just implementation details.</span></span>  
  
 <span data-ttu-id="e6a3c-122">由于具有弱协定或不具有协定的任何方法都有可能以多种不可预测的方式失败，运行时并不尝试从方法（例如由惰性 JIT 编译、泛型字典填充或线程中止所引入的方法）中删除它自己的任何不可预测的失败。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-122">Because any method with a weak or nonexistent contract can potentially fail in many unpredictable ways, the runtime does not attempt to remove any of its own unpredictable failures from the method  that are introduced by lazy JIT-compiling, generics dictionary population, or thread aborts, for example.</span></span> <span data-ttu-id="e6a3c-123">也就是说，当此 MDA 被激活时，它指示运行时不在所定义的 CER 中包括调用的方法；调用关系图在此节点终止，因为继续准备此子树将有助于掩蔽潜在的错误。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-123">That is, when this MDA is activated, it indicates that the runtime did not include the called method in the CER being defined; the call graph was terminated at this node because continuing to prepare this subtree would help mask the potential error.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="e6a3c-124">解决方法</span><span class="sxs-lookup"><span data-stu-id="e6a3c-124">Resolution</span></span>  
 <span data-ttu-id="e6a3c-125">向该函数添加有效的可靠性协定，或避免使用该函数调用。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-125">Add a valid reliability contract to the function or avoid using that function call.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="e6a3c-126">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="e6a3c-126">Effect on the Runtime</span></span>  
 <span data-ttu-id="e6a3c-127">从 CER 调用弱协定的影响可能是 CER 未能完成其操作。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-127">The effect of calling a weak contract from a CER could be the CER failure to complete its operations.</span></span> <span data-ttu-id="e6a3c-128">这可能导致 <xref:System.AppDomain> 进程状态的损坏。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-128">This could lead to corruption of the <xref:System.AppDomain> process state.</span></span>  
  
## <a name="output"></a><span data-ttu-id="e6a3c-129">输出</span><span class="sxs-lookup"><span data-stu-id="e6a3c-129">Output</span></span>  
 <span data-ttu-id="e6a3c-130">下面是来自此 MDA 的示例输出。</span><span class="sxs-lookup"><span data-stu-id="e6a3c-130">The following is sample output from this MDA.</span></span>  
  
 `Method 'MethodWithCer', while executing within a constrained execution region, makes a call at IL offset 0x000C to 'MethodWithWeakContract', which does not have a sufficiently strong reliability contract and might cause non-deterministic results.`  
  
## <a name="configuration"></a><span data-ttu-id="e6a3c-131">配置</span><span class="sxs-lookup"><span data-stu-id="e6a3c-131">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6a3c-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6a3c-132">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>  
 <xref:System.Runtime.ConstrainedExecution>  
 [<span data-ttu-id="e6a3c-133">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="e6a3c-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
