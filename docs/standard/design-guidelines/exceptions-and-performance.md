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
ms.openlocfilehash: d664b7b61394bd9bfe6d0abd7130f9f0191e7a03
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083541"
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="b7a66-102">异常和性能</span><span class="sxs-lookup"><span data-stu-id="b7a66-102">Exceptions and Performance</span></span>
<span data-ttu-id="b7a66-103">一个常见的问题与异常相关，如果使用异常来进行定期失败的代码，实现的性能都是不可接受。</span><span class="sxs-lookup"><span data-stu-id="b7a66-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="b7a66-104">这是关注点。</span><span class="sxs-lookup"><span data-stu-id="b7a66-104">This is a valid concern.</span></span> <span data-ttu-id="b7a66-105">当成员引发了异常时，其性能可以是数量级。</span><span class="sxs-lookup"><span data-stu-id="b7a66-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="b7a66-106">但是，就可以实现良好性能，同时严格符合不允许使用错误代码的异常指导原则。</span><span class="sxs-lookup"><span data-stu-id="b7a66-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="b7a66-107">在本部分中所述的两种模式建议执行此操作的方法。</span><span class="sxs-lookup"><span data-stu-id="b7a66-107">Two patterns described in this section suggest ways to do this.</span></span>  
  
 <span data-ttu-id="b7a66-108">**X DO NOT** 由于异常可能会对性能产生负面影响的问题，因此使用错误代码。</span><span class="sxs-lookup"><span data-stu-id="b7a66-108">**X DO NOT** use error codes because of concerns that exceptions might affect performance negatively.</span></span>  
  
 <span data-ttu-id="b7a66-109">若要提高性能，则可以使用 Tester-doer 模式或重分析模式，接下来的两部分中所述。</span><span class="sxs-lookup"><span data-stu-id="b7a66-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>  
  
## <a name="tester-doer-pattern"></a><span data-ttu-id="b7a66-110">Tester-doer 模式</span><span class="sxs-lookup"><span data-stu-id="b7a66-110">Tester-Doer Pattern</span></span>  
 <span data-ttu-id="b7a66-111">有时可以通过拆分为两个成员改进了引发异常的成员的性能。</span><span class="sxs-lookup"><span data-stu-id="b7a66-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="b7a66-112">让我们看看<xref:System.Collections.Generic.ICollection%601.Add%2A>方法的<xref:System.Collections.Generic.ICollection%601>接口。</span><span class="sxs-lookup"><span data-stu-id="b7a66-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 <span data-ttu-id="b7a66-113">该方法`Add`集合为只读时引发。</span><span class="sxs-lookup"><span data-stu-id="b7a66-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="b7a66-114">这可能是在方法调用的地方通常失败的情况下性能问题。</span><span class="sxs-lookup"><span data-stu-id="b7a66-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="b7a66-115">若要缓解此问题的方法之一是测试是否集合然后再尝试添加一个值是可写。</span><span class="sxs-lookup"><span data-stu-id="b7a66-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 <span data-ttu-id="b7a66-116">用于测试条件，它在我们的示例中为该属性的成员`IsReadOnly`，称为测试人员。</span><span class="sxs-lookup"><span data-stu-id="b7a66-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="b7a66-117">用于执行可能引发的操作，该成员`Add`方法在本示例中，被称为 doer。</span><span class="sxs-lookup"><span data-stu-id="b7a66-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>  
  
 <span data-ttu-id="b7a66-118">**✓ CONSIDER** 可能会引发异常的成员 Tester-doer 模式在常见方案以避免性能问题与异常相关。</span><span class="sxs-lookup"><span data-stu-id="b7a66-118">**✓ CONSIDER** the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
## <a name="try-parse-pattern"></a><span data-ttu-id="b7a66-119">尝试分析模式</span><span class="sxs-lookup"><span data-stu-id="b7a66-119">Try-Parse Pattern</span></span>  
 <span data-ttu-id="b7a66-120">对于极高性能 Api，应使用更快的运行模式比上一节中所述的 Tester-doer 模式。</span><span class="sxs-lookup"><span data-stu-id="b7a66-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="b7a66-121">该模式需要调整要明确定义测试案例的成员语义的一部分的成员名称。</span><span class="sxs-lookup"><span data-stu-id="b7a66-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="b7a66-122">例如，<xref:System.DateTime>定义<xref:System.DateTime.Parse%2A>字符串的分析失败时引发异常的方法。</span><span class="sxs-lookup"><span data-stu-id="b7a66-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="b7a66-123">它还定义了相应<xref:System.DateTime.TryParse%2A>，将尝试进行分析，但如果方法返回 false 分析失败并返回成功分析使用结果`out`参数。</span><span class="sxs-lookup"><span data-stu-id="b7a66-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>  
  
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
  
 <span data-ttu-id="b7a66-124">使用此模式时，务必在严格的术语定义的重试功能。</span><span class="sxs-lookup"><span data-stu-id="b7a66-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="b7a66-125">如果成员以外定义完善的重试由于任何原因失败，该成员必须仍会引发相应异常。</span><span class="sxs-lookup"><span data-stu-id="b7a66-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>  
  
 <span data-ttu-id="b7a66-126">**✓ CONSIDER** 可能会引发异常的成员尝试分析模式在常见方案以避免性能问题与异常相关。</span><span class="sxs-lookup"><span data-stu-id="b7a66-126">**✓ CONSIDER** the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
 <span data-ttu-id="b7a66-127">**✓ DO** 方法实现此模式中使用前缀"Try"和布尔值返回的类型。</span><span class="sxs-lookup"><span data-stu-id="b7a66-127">**✓ DO** use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>  
  
 <span data-ttu-id="b7a66-128">**✓ DO** 每个成员使用 Try 分析模式提供的异常引发的成员。</span><span class="sxs-lookup"><span data-stu-id="b7a66-128">**✓ DO** provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>  
  
 <span data-ttu-id="b7a66-129">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="b7a66-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b7a66-130">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="b7a66-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7a66-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7a66-131">See also</span></span>

- [<span data-ttu-id="b7a66-132">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="b7a66-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="b7a66-133">异常的设计准则</span><span class="sxs-lookup"><span data-stu-id="b7a66-133">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
