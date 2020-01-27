---
title: 예외 Throw
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
ms.openlocfilehash: 18927d242c2ed957d2bc9f8b481beeed775a4e4e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741676"
---
# <a name="exception-throwing"></a><span data-ttu-id="0e8d1-102">예외 Throw</span><span class="sxs-lookup"><span data-stu-id="0e8d1-102">Exception Throwing</span></span>
<span data-ttu-id="0e8d1-103">本部分介绍的异常引发准则要求对执行失败的含义进行明确定义。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-103">Exception-throwing guidelines described in this section require a good definition of the meaning of execution failure.</span></span> <span data-ttu-id="0e8d1-104">只要成员无法执行其指定操作（成员名称所体现的含义），就会导致执行失败。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-104">Execution failure occurs whenever a member cannot do what it was designed to do (what the member name implies).</span></span> <span data-ttu-id="0e8d1-105">例如，如果 `OpenFile` 方法无法将打开的文件句柄返回给调用方，则视为执行失败。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-105">For example, if the `OpenFile` method cannot return an opened file handle to the caller, it would be considered an execution failure.</span></span>

 <span data-ttu-id="0e8d1-106">大多数开发人员已经习惯使用异常来处理用法错误，例如除零或空引用。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-106">Most developers have become comfortable with using exceptions for usage errors such as division by zero or null references.</span></span> <span data-ttu-id="0e8d1-107">在框架中，异常用于所有错误情况，包括执行错误。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-107">In the Framework, exceptions are used for all error conditions, including execution errors.</span></span>

 <span data-ttu-id="0e8d1-108">❌ 不返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-108">❌ DO NOT return error codes.</span></span>

 <span data-ttu-id="0e8d1-109">异常是框架中报告错误的主要方式。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-109">Exceptions are the primary means of reporting errors in frameworks.</span></span>

 <span data-ttu-id="0e8d1-110">✔️通过引发异常来报告执行失败。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-110">✔️ DO report execution failures by throwing exceptions.</span></span>

 <span data-ttu-id="0e8d1-111">✔️考虑通过调用 `System.Environment.FailFast` （.NET Framework 2.0 功能）终止进程，而不是在代码遇到不安全的情况下引发异常，以便进一步执行。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-111">✔️ CONSIDER terminating the process by calling `System.Environment.FailFast` (.NET Framework 2.0 feature) instead of throwing an exception if your code encounters a situation where it is unsafe for further execution.</span></span>

 <span data-ttu-id="0e8d1-112">如果可能，❌ 不会对正常控制流使用异常。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-112">❌ DO NOT use exceptions for the normal flow of control, if possible.</span></span>

 <span data-ttu-id="0e8d1-113">除系统故障和存在潜在争用条件的操作这两种情况外，框架设计者应设计 API，以便用户可以编写不会引发异常的代码。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-113">Except for system failures and operations with potential race conditions, framework designers should design APIs so users can write code that does not throw exceptions.</span></span> <span data-ttu-id="0e8d1-114">例如，可以提供在调用成员之前检查前提条件的方法，以便用户可以编写不会引发异常的代码。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-114">For example, you can provide a way to check preconditions before calling a member so users can write code that does not throw exceptions.</span></span>

 <span data-ttu-id="0e8d1-115">用于检查另一个成员的前提条件的成员通常被称为 tester（测试者），实际执行该工作的成员称为 doer（实施者）。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-115">The member used to check preconditions of another member is often referred to as a tester, and the member that actually does the work is called a doer.</span></span>

 <span data-ttu-id="0e8d1-116">有些情况下，Tester-Doer 模式可能会产生不可接受的性能开销。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-116">There are cases when the Tester-Doer Pattern can have an unacceptable performance overhead.</span></span> <span data-ttu-id="0e8d1-117">在这种情况下，应考虑使用所谓的 Try-Parse 模式（有关详细信息，请参阅[异常和性能](../../../docs/standard/design-guidelines/exceptions-and-performance.md)）。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-117">In such cases, the so-called Try-Parse Pattern should be considered (see [Exceptions and Performance](../../../docs/standard/design-guidelines/exceptions-and-performance.md) for more information).</span></span>

 <span data-ttu-id="0e8d1-118">✔️考虑引发异常的性能影响。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-118">✔️ CONSIDER the performance implications of throwing exceptions.</span></span> <span data-ttu-id="0e8d1-119">每秒以上100的引发率可能会显著影响大多数应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-119">Throw rates above 100 per second are likely to noticeably impact the performance of most applications.</span></span>

 <span data-ttu-id="0e8d1-120">✔️会记录公共可调用成员引发的所有异常，因为违反了成员协定（而不是系统失败），并将它们视为协定的一部分。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-120">✔️ DO document all exceptions thrown by publicly callable members because of a violation of the member contract (rather than a system failure) and treat them as part of your contract.</span></span>

 <span data-ttu-id="0e8d1-121">作为协定一部分的异常在协定的不同版本中应保持一致（即，不应更改异常类型，并且不应添加新的异常）。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-121">Exceptions that are a part of the contract should not change from one version to the next (i.e., exception type should not change, and new exceptions should not be added).</span></span>

 <span data-ttu-id="0e8d1-122">❌ 没有可以引发或不基于某个选项的公共成员。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-122">❌ DO NOT have public members that can either throw or not based on some option.</span></span>

 <span data-ttu-id="0e8d1-123">❌ 没有将异常作为返回值或 `out` 参数返回的公共成员。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-123">❌ DO NOT have public members that return exceptions as the return value or an `out` parameter.</span></span>

 <span data-ttu-id="0e8d1-124">如果选择从公共 API 返回异常而不是引发它们，会丧失基于异常的错误报告的优势。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-124">Returning exceptions from public APIs instead of throwing them defeats many of the benefits of exception-based error reporting.</span></span>

 <span data-ttu-id="0e8d1-125">✔️考虑使用异常生成器方法。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-125">✔️ CONSIDER using exception builder methods.</span></span>

 <span data-ttu-id="0e8d1-126">从不同位置引发相同的异常是很常见的。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-126">It is common to throw the same exception from different places.</span></span> <span data-ttu-id="0e8d1-127">为避免代码膨胀，请使用可创建异常并初始化其属性的辅助方法。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-127">To avoid code bloat, use helper methods that create exceptions and initialize their properties.</span></span>

 <span data-ttu-id="0e8d1-128">此外，引发异常的成员不会被内联。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-128">Also, members that throw exceptions are not getting inlined.</span></span> <span data-ttu-id="0e8d1-129">或可通过将引发语句移动到生成器内来实现成员内联。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-129">Moving the throw statement inside the builder might allow the member to be inlined.</span></span>

 <span data-ttu-id="0e8d1-130">❌ 不会从异常筛选器块中引发异常。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-130">❌ DO NOT throw exceptions from exception filter blocks.</span></span>

 <span data-ttu-id="0e8d1-131">当异常筛选器引发异常时，CLR 会捕获该异常，筛选器会返回 false。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-131">When an exception filter raises an exception, the exception is caught by the CLR, and the filter returns false.</span></span> <span data-ttu-id="0e8d1-132">此行为与执行并显式返回 false 的过滤器行为无法区分，因此很难进行调试。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-132">This behavior is indistinguishable from the filter executing and returning false explicitly and is therefore very difficult to debug.</span></span>

 <span data-ttu-id="0e8d1-133">❌ 避免从 finally 块显式引发异常。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-133">❌ AVOID explicitly throwing exceptions from finally blocks.</span></span> <span data-ttu-id="0e8d1-134">调用引发的方法可接受隐式引发的异常。</span><span class="sxs-lookup"><span data-stu-id="0e8d1-134">Implicitly thrown exceptions resulting from calling methods that throw are acceptable.</span></span>

 <span data-ttu-id="0e8d1-135">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="0e8d1-135">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="0e8d1-136">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="0e8d1-136">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="0e8d1-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e8d1-137">See also</span></span>

- [<span data-ttu-id="0e8d1-138">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="0e8d1-138">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="0e8d1-139">예외 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="0e8d1-139">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
