---
title: 异常和性能
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfffc2a1c0f607541194a7f51717d5bf8a8537f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575331"
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="8798d-102">异常和性能</span><span class="sxs-lookup"><span data-stu-id="8798d-102">Exceptions and Performance</span></span>
<span data-ttu-id="8798d-103">与异常相关的一个常见问题是，如果使用异常来进行例行失败的代码，实现的性能将无法接受。</span><span class="sxs-lookup"><span data-stu-id="8798d-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="8798d-104">这是一个有效的问题。</span><span class="sxs-lookup"><span data-stu-id="8798d-104">This is a valid concern.</span></span> <span data-ttu-id="8798d-105">在成员引发了异常，其性能可能会极大地速度较慢。</span><span class="sxs-lookup"><span data-stu-id="8798d-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="8798d-106">但是，很可能来实现良好性能时严格符合禁止使用错误代码的异常指导原则。</span><span class="sxs-lookup"><span data-stu-id="8798d-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="8798d-107">本节中所述的两种模式建议执行此操作的方法。</span><span class="sxs-lookup"><span data-stu-id="8798d-107">Two patterns described in this section suggest ways to do this.</span></span>  
  
 <span data-ttu-id="8798d-108">**X DO NOT** 由于异常可能会对性能产生负面影响的问题，因此使用错误代码。</span><span class="sxs-lookup"><span data-stu-id="8798d-108">**X DO NOT** use error codes because of concerns that exceptions might affect performance negatively.</span></span>  
  
 <span data-ttu-id="8798d-109">若要提高性能，它是可以使用 Tester-doer 模式或尝试分析模式，接下来的两部分中所述。</span><span class="sxs-lookup"><span data-stu-id="8798d-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>  
  
## <a name="tester-doer-pattern"></a><span data-ttu-id="8798d-110">Tester-doer 模式</span><span class="sxs-lookup"><span data-stu-id="8798d-110">Tester-Doer Pattern</span></span>  
 <span data-ttu-id="8798d-111">有时可通过成员拆分为两个改善性能的异常引发的成员。</span><span class="sxs-lookup"><span data-stu-id="8798d-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="8798d-112">让我们看一下<xref:System.Collections.Generic.ICollection%601.Add%2A>方法<xref:System.Collections.Generic.ICollection%601>接口。</span><span class="sxs-lookup"><span data-stu-id="8798d-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 <span data-ttu-id="8798d-113">该方法`Add`引发如果该集合为只读的。</span><span class="sxs-lookup"><span data-stu-id="8798d-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="8798d-114">这可能会在方法调用的地方通常失败的情况下造成性能问题。</span><span class="sxs-lookup"><span data-stu-id="8798d-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="8798d-115">一种以缓解问题的是测试集合是否是可写之前尝试添加一个值。</span><span class="sxs-lookup"><span data-stu-id="8798d-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 <span data-ttu-id="8798d-116">用于测试条件，它在我们的示例中为该属性的成员`IsReadOnly`，简称为测试人员。</span><span class="sxs-lookup"><span data-stu-id="8798d-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="8798d-117">用于执行可能引发的操作，该成员`Add`方法在本示例中，称为 doer。</span><span class="sxs-lookup"><span data-stu-id="8798d-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>  
  
 <span data-ttu-id="8798d-118">**✓ CONSIDER** 可能会引发异常的成员 Tester-doer 模式在常见方案以避免性能问题与异常相关。</span><span class="sxs-lookup"><span data-stu-id="8798d-118">**✓ CONSIDER** the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
## <a name="try-parse-pattern"></a><span data-ttu-id="8798d-119">尝试分析模式</span><span class="sxs-lookup"><span data-stu-id="8798d-119">Try-Parse Pattern</span></span>  
 <span data-ttu-id="8798d-120">对于极性能敏感的 Api，应使用一种更快的运行模式，比上一节中所述的 Tester-doer 模式。</span><span class="sxs-lookup"><span data-stu-id="8798d-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="8798d-121">模式需要调整定义完善的测试案例成员语义的一部分的成员名称。</span><span class="sxs-lookup"><span data-stu-id="8798d-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="8798d-122">例如，<xref:System.DateTime>定义<xref:System.DateTime.Parse%2A>字符串的分析失败时引发异常的方法。</span><span class="sxs-lookup"><span data-stu-id="8798d-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="8798d-123">它还定义相应<xref:System.DateTime.TryParse%2A>，尝试进行分析，但如果方法返回 false 分析失败并返回成功分析使用结果`out`参数。</span><span class="sxs-lookup"><span data-stu-id="8798d-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>  
  
```  
public struct DateTime {  
    public static DateTime Parse(string dateTime){   
        ...   
    }  
    public static bool TryParse(string dateTime, out DateTime result){  
        ...  
    }  
}  
```  
  
 <span data-ttu-id="8798d-124">在使用此模式时，务必在术语中严格定义的重试功能。</span><span class="sxs-lookup"><span data-stu-id="8798d-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="8798d-125">如果成员的定义完善的重试任何原因失败，该成员必须仍会引发相应异常。</span><span class="sxs-lookup"><span data-stu-id="8798d-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>  
  
 <span data-ttu-id="8798d-126">**✓ CONSIDER** 可能会引发异常的成员尝试分析模式在常见方案以避免性能问题与异常相关。</span><span class="sxs-lookup"><span data-stu-id="8798d-126">**✓ CONSIDER** the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
 <span data-ttu-id="8798d-127">**✓ DO** 方法实现此模式中使用前缀"Try"和布尔值返回的类型。</span><span class="sxs-lookup"><span data-stu-id="8798d-127">**✓ DO** use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>  
  
 <span data-ttu-id="8798d-128">**✓ DO** 每个成员使用 Try 分析模式提供的异常引发的成员。</span><span class="sxs-lookup"><span data-stu-id="8798d-128">**✓ DO** provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>  
  
 <span data-ttu-id="8798d-129">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="8798d-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="8798d-130">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="8798d-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8798d-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="8798d-131">See Also</span></span>  
 [<span data-ttu-id="8798d-132">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="8798d-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="8798d-133">异常的设计准则</span><span class="sxs-lookup"><span data-stu-id="8798d-133">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
