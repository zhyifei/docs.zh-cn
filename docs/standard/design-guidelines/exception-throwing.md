---
title: 异常引发
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
ms.openlocfilehash: 7d1b63e5fde57cbe37a1250d16b6bf74a2d5dc8e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709395"
---
# <a name="exception-throwing"></a><span data-ttu-id="b9550-102">异常引发</span><span class="sxs-lookup"><span data-stu-id="b9550-102">Exception Throwing</span></span>
<span data-ttu-id="b9550-103">本部分介绍的异常引发准则要求对执行失败的含义进行明确定义。</span><span class="sxs-lookup"><span data-stu-id="b9550-103">Exception-throwing guidelines described in this section require a good definition of the meaning of execution failure.</span></span> <span data-ttu-id="b9550-104">只要成员无法执行其指定操作（成员名称所体现的含义），就会导致执行失败。</span><span class="sxs-lookup"><span data-stu-id="b9550-104">Execution failure occurs whenever a member cannot do what it was designed to do (what the member name implies).</span></span> <span data-ttu-id="b9550-105">例如，如果 `OpenFile` 方法无法将打开的文件句柄返回给调用方，则视为执行失败。</span><span class="sxs-lookup"><span data-stu-id="b9550-105">For example, if the `OpenFile` method cannot return an opened file handle to the caller, it would be considered an execution failure.</span></span>  
  
 <span data-ttu-id="b9550-106">大多数开发人员已经习惯使用异常来处理用法错误，例如除零或空引用。</span><span class="sxs-lookup"><span data-stu-id="b9550-106">Most developers have become comfortable with using exceptions for usage errors such as division by zero or null references.</span></span> <span data-ttu-id="b9550-107">在框架中，异常用于所有错误情况，包括执行错误。</span><span class="sxs-lookup"><span data-stu-id="b9550-107">In the Framework, exceptions are used for all error conditions, including execution errors.</span></span>  
  
 <span data-ttu-id="b9550-108">**X DO NOT** 返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="b9550-108">**X DO NOT** return error codes.</span></span>  
  
 <span data-ttu-id="b9550-109">异常是框架中报告错误的主要方式。</span><span class="sxs-lookup"><span data-stu-id="b9550-109">Exceptions are the primary means of reporting errors in frameworks.</span></span>  
  
 <span data-ttu-id="b9550-110">**✓ DO** 引发异常来报告执行失败数。</span><span class="sxs-lookup"><span data-stu-id="b9550-110">**✓ DO** report execution failures by throwing exceptions.</span></span>  
  
 <span data-ttu-id="b9550-111">**✓ CONSIDER** 通过调用来终止进程`System.Environment.FailFast`（.NET Framework 2.0 功能） 而不是引发异常，如果你的代码遇到进一步执行不安全的情况。</span><span class="sxs-lookup"><span data-stu-id="b9550-111">**✓ CONSIDER** terminating the process by calling `System.Environment.FailFast` (.NET Framework 2.0 feature) instead of throwing an exception if your code encounters a situation where it is unsafe for further execution.</span></span>  
  
 <span data-ttu-id="b9550-112">**X DO NOT** 正常流控制，如有可能使用异常。</span><span class="sxs-lookup"><span data-stu-id="b9550-112">**X DO NOT** use exceptions for the normal flow of control, if possible.</span></span>  
  
 <span data-ttu-id="b9550-113">除系统故障和存在潜在争用条件的操作这两种情况外，框架设计者应设计 API，以便用户可以编写不会引发异常的代码。</span><span class="sxs-lookup"><span data-stu-id="b9550-113">Except for system failures and operations with potential race conditions, framework designers should design APIs so users can write code that does not throw exceptions.</span></span> <span data-ttu-id="b9550-114">例如，可以提供在调用成员之前检查前提条件的方法，以便用户可以编写不会引发异常的代码。</span><span class="sxs-lookup"><span data-stu-id="b9550-114">For example, you can provide a way to check preconditions before calling a member so users can write code that does not throw exceptions.</span></span>  
  
 <span data-ttu-id="b9550-115">用于检查另一个成员的前提条件的成员通常被称为 tester（测试者），实际执行该工作的成员称为 doer（实施者）。</span><span class="sxs-lookup"><span data-stu-id="b9550-115">The member used to check preconditions of another member is often referred to as a tester, and the member that actually does the work is called a doer.</span></span>  
  
 <span data-ttu-id="b9550-116">有些情况下，Tester-Doer 模式可能会产生不可接受的性能开销。</span><span class="sxs-lookup"><span data-stu-id="b9550-116">There are cases when the Tester-Doer Pattern can have an unacceptable performance overhead.</span></span> <span data-ttu-id="b9550-117">在这种情况下，应考虑使用所谓的 Try-Parse 模式（有关详细信息，请参阅[异常和性能](../../../docs/standard/design-guidelines/exceptions-and-performance.md)）。</span><span class="sxs-lookup"><span data-stu-id="b9550-117">In such cases, the so-called Try-Parse Pattern should be considered (see [Exceptions and Performance](../../../docs/standard/design-guidelines/exceptions-and-performance.md) for more information).</span></span>  
  
 <span data-ttu-id="b9550-118">**✓ CONSIDER** 引发异常的性能影响。</span><span class="sxs-lookup"><span data-stu-id="b9550-118">**✓ CONSIDER** the performance implications of throwing exceptions.</span></span> <span data-ttu-id="b9550-119">每秒以上100的引发率可能会显著影响大多数应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="b9550-119">Throw rates above 100 per second are likely to noticeably impact the performance of most applications.</span></span>  
  
 <span data-ttu-id="b9550-120">**✓ DO** 由于的成员冲突而引发的公开可调用的成员的所有异常协定 （而不是系统故障），并将它们视为协定的一部分的文档。</span><span class="sxs-lookup"><span data-stu-id="b9550-120">**✓ DO** document all exceptions thrown by publicly callable members because of a violation of the member contract (rather than a system failure) and treat them as part of your contract.</span></span>  
  
 <span data-ttu-id="b9550-121">作为协定一部分的异常在协定的不同版本中应保持一致（即，不应更改异常类型，并且不应添加新的异常）。</span><span class="sxs-lookup"><span data-stu-id="b9550-121">Exceptions that are a part of the contract should not change from one version to the next (i.e., exception type should not change, and new exceptions should not be added).</span></span>  
  
 <span data-ttu-id="b9550-122">**X DO NOT** 具有或不会引发的公共成员根据某些选项。</span><span class="sxs-lookup"><span data-stu-id="b9550-122">**X DO NOT** have public members that can either throw or not based on some option.</span></span>  
  
 <span data-ttu-id="b9550-123">**X DO NOT** 具有作为返回值返回异常的公共成员或`out`参数。</span><span class="sxs-lookup"><span data-stu-id="b9550-123">**X DO NOT** have public members that return exceptions as the return value or an `out` parameter.</span></span>  
  
 <span data-ttu-id="b9550-124">如果选择从公共 API 返回异常而不是引发它们，会丧失基于异常的错误报告的优势。</span><span class="sxs-lookup"><span data-stu-id="b9550-124">Returning exceptions from public APIs instead of throwing them defeats many of the benefits of exception-based error reporting.</span></span>  
  
 <span data-ttu-id="b9550-125">**✓ CONSIDER** 使用异常生成器方法。</span><span class="sxs-lookup"><span data-stu-id="b9550-125">**✓ CONSIDER** using exception builder methods.</span></span>  
  
 <span data-ttu-id="b9550-126">从不同位置引发相同的异常是很常见的。</span><span class="sxs-lookup"><span data-stu-id="b9550-126">It is common to throw the same exception from different places.</span></span> <span data-ttu-id="b9550-127">为避免代码膨胀，请使用可创建异常并初始化其属性的辅助方法。</span><span class="sxs-lookup"><span data-stu-id="b9550-127">To avoid code bloat, use helper methods that create exceptions and initialize their properties.</span></span>  
  
 <span data-ttu-id="b9550-128">此外，引发异常的成员不会被内联。</span><span class="sxs-lookup"><span data-stu-id="b9550-128">Also, members that throw exceptions are not getting inlined.</span></span> <span data-ttu-id="b9550-129">或可通过将引发语句移动到生成器内来实现成员内联。</span><span class="sxs-lookup"><span data-stu-id="b9550-129">Moving the throw statement inside the builder might allow the member to be inlined.</span></span>  
  
 <span data-ttu-id="b9550-130">**X DO NOT** 异常筛选器块中引发异常。</span><span class="sxs-lookup"><span data-stu-id="b9550-130">**X DO NOT** throw exceptions from exception filter blocks.</span></span>  
  
 <span data-ttu-id="b9550-131">当异常筛选器引发异常时，CLR 会捕获该异常，筛选器会返回 false。</span><span class="sxs-lookup"><span data-stu-id="b9550-131">When an exception filter raises an exception, the exception is caught by the CLR, and the filter returns false.</span></span> <span data-ttu-id="b9550-132">此行为与执行并显式返回 false 的过滤器行为无法区分，因此很难进行调试。</span><span class="sxs-lookup"><span data-stu-id="b9550-132">This behavior is indistinguishable from the filter executing and returning false explicitly and is therefore very difficult to debug.</span></span>  
  
 <span data-ttu-id="b9550-133">**X AVOID** 显式引发 finally 块中的异常。</span><span class="sxs-lookup"><span data-stu-id="b9550-133">**X AVOID** explicitly throwing exceptions from finally blocks.</span></span> <span data-ttu-id="b9550-134">调用引发的方法可接受隐式引发的异常。</span><span class="sxs-lookup"><span data-stu-id="b9550-134">Implicitly thrown exceptions resulting from calling methods that throw are acceptable.</span></span>  
  
 <span data-ttu-id="b9550-135">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="b9550-135">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b9550-136">\*在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。</span><span class="sxs-lookup"><span data-stu-id="b9550-136">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9550-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9550-137">See also</span></span>

- [<span data-ttu-id="b9550-138">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="b9550-138">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="b9550-139">异常的设计准则</span><span class="sxs-lookup"><span data-stu-id="b9550-139">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
