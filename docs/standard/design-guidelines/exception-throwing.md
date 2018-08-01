---
title: 异常引发
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a493e6591d90ce05a652e48807f63fa90764a91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573716"
---
# <a name="exception-throwing"></a><span data-ttu-id="e0521-102">异常引发</span><span class="sxs-lookup"><span data-stu-id="e0521-102">Exception Throwing</span></span>
<span data-ttu-id="e0521-103">在本部分中所述的异常引发准则需要正确定义的执行失败的含义。</span><span class="sxs-lookup"><span data-stu-id="e0521-103">Exception-throwing guidelines described in this section require a good definition of the meaning of execution failure.</span></span> <span data-ttu-id="e0521-104">执行失败每当某一成员不能执行其设计目的 （什么成员名称所暗示的）。</span><span class="sxs-lookup"><span data-stu-id="e0521-104">Execution failure occurs whenever a member cannot do what it was designed to do (what the member name implies).</span></span> <span data-ttu-id="e0521-105">例如，如果`OpenFile`方法无法返回到调用方的一个打开的文件句柄，它将被认为执行失败。</span><span class="sxs-lookup"><span data-stu-id="e0521-105">For example, if the `OpenFile` method cannot return an opened file handle to the caller, it would be considered an execution failure.</span></span>  
  
 <span data-ttu-id="e0521-106">大多数开发人员已经熟悉使用由零或 null 引用异常如除法用法错误。</span><span class="sxs-lookup"><span data-stu-id="e0521-106">Most developers have become comfortable with using exceptions for usage errors such as division by zero or null references.</span></span> <span data-ttu-id="e0521-107">在框架中，异常用于所有错误条件，包括执行错误。</span><span class="sxs-lookup"><span data-stu-id="e0521-107">In the Framework, exceptions are used for all error conditions, including execution errors.</span></span>  
  
 <span data-ttu-id="e0521-108">**X DO NOT**返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="e0521-108">**X DO NOT** return error codes.</span></span>  
  
 <span data-ttu-id="e0521-109">例外情况是报告框架中的错误的主要方式。</span><span class="sxs-lookup"><span data-stu-id="e0521-109">Exceptions are the primary means of reporting errors in frameworks.</span></span>  
  
 <span data-ttu-id="e0521-110">**✓ DO**引发异常来报告执行失败数。</span><span class="sxs-lookup"><span data-stu-id="e0521-110">**✓ DO** report execution failures by throwing exceptions.</span></span>  
  
 <span data-ttu-id="e0521-111">**✓ CONSIDER**通过调用来终止进程`System.Environment.FailFast`（.NET Framework 2.0 功能） 而不是引发异常，如果你的代码遇到进一步执行不安全的情况。</span><span class="sxs-lookup"><span data-stu-id="e0521-111">**✓ CONSIDER** terminating the process by calling `System.Environment.FailFast` (.NET Framework 2.0 feature) instead of throwing an exception if your code encounters a situation where it is unsafe for further execution.</span></span>  
  
 <span data-ttu-id="e0521-112">**X DO NOT**正常流控制，如有可能使用异常。</span><span class="sxs-lookup"><span data-stu-id="e0521-112">**X DO NOT** use exceptions for the normal flow of control, if possible.</span></span>  
  
 <span data-ttu-id="e0521-113">系统故障和具有潜在的争用情况的操作，除外 framework 设计器应设计 Api，以便用户可以编写不引发异常的代码。</span><span class="sxs-lookup"><span data-stu-id="e0521-113">Except for system failures and operations with potential race conditions, framework designers should design APIs so users can write code that does not throw exceptions.</span></span> <span data-ttu-id="e0521-114">例如，你可以提供了如何在调用成员，因此用户可以编写不引发异常的代码之前检查前置条件。</span><span class="sxs-lookup"><span data-stu-id="e0521-114">For example, you can provide a way to check preconditions before calling a member so users can write code that does not throw exceptions.</span></span>  
  
 <span data-ttu-id="e0521-115">用于检查另一个成员的前置条件的成员通常称为测试人员，而实际执行该操作，该成员称为 doer。</span><span class="sxs-lookup"><span data-stu-id="e0521-115">The member used to check preconditions of another member is often referred to as a tester, and the member that actually does the work is called a doer.</span></span>  
  
 <span data-ttu-id="e0521-116">有某些情况下可能带来严重的性能开销，Tester-doer 模式。</span><span class="sxs-lookup"><span data-stu-id="e0521-116">There are cases when the Tester-Doer Pattern can have an unacceptable performance overhead.</span></span> <span data-ttu-id="e0521-117">在这种情况下，应考虑所谓的重分析模式 (请参阅[异常和性能](../../../docs/standard/design-guidelines/exceptions-and-performance.md)有关详细信息)。</span><span class="sxs-lookup"><span data-stu-id="e0521-117">In such cases, the so-called Try-Parse Pattern should be considered (see [Exceptions and Performance](../../../docs/standard/design-guidelines/exceptions-and-performance.md) for more information).</span></span>  
  
 <span data-ttu-id="e0521-118">**✓ CONSIDER**引发异常的性能影响。</span><span class="sxs-lookup"><span data-stu-id="e0521-118">**✓ CONSIDER** the performance implications of throwing exceptions.</span></span> <span data-ttu-id="e0521-119">每秒 100 以上 throw 率很可能会显著影响大多数应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="e0521-119">Throw rates above 100 per second are likely to noticeably impact the performance of most applications.</span></span>  
  
 <span data-ttu-id="e0521-120">**✓ DO**由于的成员冲突而引发的公开可调用的成员的所有异常协定 （而不是系统故障），并将它们视为协定的一部分的文档。</span><span class="sxs-lookup"><span data-stu-id="e0521-120">**✓ DO** document all exceptions thrown by publicly callable members because of a violation of the member contract (rather than a system failure) and treat them as part of your contract.</span></span>  
  
 <span data-ttu-id="e0521-121">协定的一部分的异常应不从一个版本更改为下一步 （即，不能更改异常类型，并且不应添加新异常）。</span><span class="sxs-lookup"><span data-stu-id="e0521-121">Exceptions that are a part of the contract should not change from one version to the next (i.e., exception type should not change, and new exceptions should not be added).</span></span>  
  
 <span data-ttu-id="e0521-122">**X DO NOT**具有或不会引发的公共成员根据某些选项。</span><span class="sxs-lookup"><span data-stu-id="e0521-122">**X DO NOT** have public members that can either throw or not based on some option.</span></span>  
  
 <span data-ttu-id="e0521-123">**X DO NOT**具有作为返回值返回异常的公共成员或`out`参数。</span><span class="sxs-lookup"><span data-stu-id="e0521-123">**X DO NOT** have public members that return exceptions as the return value or an `out` parameter.</span></span>  
  
 <span data-ttu-id="e0521-124">返回从公共 Api 而不是引发这些异常会使无效的许多优势的基于异常的错误报告。</span><span class="sxs-lookup"><span data-stu-id="e0521-124">Returning exceptions from public APIs instead of throwing them defeats many of the benefits of exception-based error reporting.</span></span>  
  
 <span data-ttu-id="e0521-125">**✓ CONSIDER**使用异常生成器方法。</span><span class="sxs-lookup"><span data-stu-id="e0521-125">**✓ CONSIDER** using exception builder methods.</span></span>  
  
 <span data-ttu-id="e0521-126">很容易从不同位置引发同一异常。</span><span class="sxs-lookup"><span data-stu-id="e0521-126">It is common to throw the same exception from different places.</span></span> <span data-ttu-id="e0521-127">若要避免代码膨胀，使用使用帮助器方法创建异常并初始化其属性。</span><span class="sxs-lookup"><span data-stu-id="e0521-127">To avoid code bloat, use helper methods that create exceptions and initialize their properties.</span></span>  
  
 <span data-ttu-id="e0521-128">此外，不会引发异常的成员进行内联。</span><span class="sxs-lookup"><span data-stu-id="e0521-128">Also, members that throw exceptions are not getting inlined.</span></span> <span data-ttu-id="e0521-129">移动生成器 throw 语句可能会使成员进行内联。</span><span class="sxs-lookup"><span data-stu-id="e0521-129">Moving the throw statement inside the builder might allow the member to be inlined.</span></span>  
  
 <span data-ttu-id="e0521-130">**X DO NOT**异常筛选器块中引发异常。</span><span class="sxs-lookup"><span data-stu-id="e0521-130">**X DO NOT** throw exceptions from exception filter blocks.</span></span>  
  
 <span data-ttu-id="e0521-131">当异常筛选器引发异常时，默认情况下，异常由 CLR，并且筛选器返回 false。</span><span class="sxs-lookup"><span data-stu-id="e0521-131">When an exception filter raises an exception, the exception is caught by the CLR, and the filter returns false.</span></span> <span data-ttu-id="e0521-132">此行为是不能与区分从筛选器执行，并显式返回 false，因此很难进行调试。</span><span class="sxs-lookup"><span data-stu-id="e0521-132">This behavior is indistinguishable from the filter executing and returning false explicitly and is therefore very difficult to debug.</span></span>  
  
 <span data-ttu-id="e0521-133">**X AVOID**显式引发 finally 块中的异常。</span><span class="sxs-lookup"><span data-stu-id="e0521-133">**X AVOID** explicitly throwing exceptions from finally blocks.</span></span> <span data-ttu-id="e0521-134">隐式引发的异常导致调用引发的方法均可接受。</span><span class="sxs-lookup"><span data-stu-id="e0521-134">Implicitly thrown exceptions resulting from calling methods that throw are acceptable.</span></span>  
  
 <span data-ttu-id="e0521-135">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="e0521-135">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e0521-136">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="e0521-136">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0521-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0521-137">See Also</span></span>  
 [<span data-ttu-id="e0521-138">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="e0521-138">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="e0521-139">异常的设计准则</span><span class="sxs-lookup"><span data-stu-id="e0521-139">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
