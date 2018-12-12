---
title: 属性设计
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
author: KrzysztofCwalina
ms.openlocfilehash: 1d119b48f0524b3e997aa2cb9ea2cbbd855afdf0
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131451"
---
# <a name="property-design"></a><span data-ttu-id="98749-102">属性设计</span><span class="sxs-lookup"><span data-stu-id="98749-102">Property Design</span></span>
<span data-ttu-id="98749-103">尽管从技术上讲非常类似于方法属性，但它们是在其使用情况方面大不相同。</span><span class="sxs-lookup"><span data-stu-id="98749-103">Although properties are technically very similar to methods, they are quite different in terms of their usage scenarios.</span></span> <span data-ttu-id="98749-104">它们应视为智能字段。</span><span class="sxs-lookup"><span data-stu-id="98749-104">They should be seen as smart fields.</span></span> <span data-ttu-id="98749-105">它们具有的字段中，调用语法和方法的灵活性。</span><span class="sxs-lookup"><span data-stu-id="98749-105">They have the calling syntax of fields, and the flexibility of methods.</span></span>  
  
 <span data-ttu-id="98749-106">**✓ DO** 创建仅限 get 的属性，如果调用方应不能更改属性的值。</span><span class="sxs-lookup"><span data-stu-id="98749-106">**✓ DO** create get-only properties if the caller should not be able to change the value of the property.</span></span>  
  
 <span data-ttu-id="98749-107">请记住，如果类型的属性为可变引用类型，可以更改属性值，即使该属性是只读属性。</span><span class="sxs-lookup"><span data-stu-id="98749-107">Keep in mind that if the type of the property is a mutable reference type, the property value can be changed even if the property is get-only.</span></span>  
  
 <span data-ttu-id="98749-108">**X DO NOT** 仅属性的 setter 具有更广泛的可访问性比 getter 提供。</span><span class="sxs-lookup"><span data-stu-id="98749-108">**X DO NOT** provide set-only properties or properties with the setter having broader accessibility than the getter.</span></span>  
  
 <span data-ttu-id="98749-109">例如，请使用公共 setter 和受保护的 getter 使用属性。</span><span class="sxs-lookup"><span data-stu-id="98749-109">For example, do not use properties with a public setter and a protected getter.</span></span>  
  
 <span data-ttu-id="98749-110">如果不能提供的属性 getter，改为实现了与一种方法的功能。</span><span class="sxs-lookup"><span data-stu-id="98749-110">If the property getter cannot be provided, implement the functionality as a method instead.</span></span> <span data-ttu-id="98749-111">请考虑从开始使用的方法名称`Set`并在后面加什么将已命名属性。</span><span class="sxs-lookup"><span data-stu-id="98749-111">Consider starting the method name with `Set` and follow with what you would have named the property.</span></span> <span data-ttu-id="98749-112">例如，<xref:System.AppDomain>有一个名为`SetCachePath`而不是让一个名为仅限组的属性`CachePath`。</span><span class="sxs-lookup"><span data-stu-id="98749-112">For example, <xref:System.AppDomain> has a method called `SetCachePath` instead of having a set-only property called `CachePath`.</span></span>  
  
 <span data-ttu-id="98749-113">**✓ DO** 提供的所有属性，确保，默认值不会导致安全漏洞或您对此低效代码的意义的默认值。</span><span class="sxs-lookup"><span data-stu-id="98749-113">**✓ DO** provide sensible default values for all properties, ensuring that the defaults do not result in a security hole or terribly inefficient code.</span></span>  
  
 <span data-ttu-id="98749-114">**✓ DO** 允许将属性按任何顺序设置，即使这会导致临时无效状态的对象。</span><span class="sxs-lookup"><span data-stu-id="98749-114">**✓ DO** allow properties to be set in any order even if this results in a temporary invalid state of the object.</span></span>  
  
 <span data-ttu-id="98749-115">提供对同一个对象的其他属性的值是常见的两个或多个要相互关联到一个属性的某些值可能无效的点的属性。</span><span class="sxs-lookup"><span data-stu-id="98749-115">It is common for two or more properties to be interrelated to a point where some values of one property might be invalid given the values of other properties on the same object.</span></span> <span data-ttu-id="98749-116">在这种情况下，从无效状态的异常应会推迟，直到实际对象一起使用相互关联的属性。</span><span class="sxs-lookup"><span data-stu-id="98749-116">In such cases, exceptions resulting from the invalid state should be postponed until the interrelated properties are actually used together by the object.</span></span>  
  
 <span data-ttu-id="98749-117">**✓ DO** 保留以前的值，如果属性 setter 将引发异常。</span><span class="sxs-lookup"><span data-stu-id="98749-117">**✓ DO** preserve the previous value if a property setter throws an exception.</span></span>  
  
 <span data-ttu-id="98749-118">**X AVOID** 属性 getter 从引发异常。</span><span class="sxs-lookup"><span data-stu-id="98749-118">**X AVOID** throwing exceptions from property getters.</span></span>  
  
 <span data-ttu-id="98749-119">属性 getter 应简单的操作，并且不应具有任何前置条件。</span><span class="sxs-lookup"><span data-stu-id="98749-119">Property getters should be simple operations and should not have any preconditions.</span></span> <span data-ttu-id="98749-120">如果一个 getter 可能会引发异常，它应可能重新设计是一种方法。</span><span class="sxs-lookup"><span data-stu-id="98749-120">If a getter can throw an exception, it should probably be redesigned to be a method.</span></span> <span data-ttu-id="98749-121">请注意，此规则不适用于索引器，我们执行预期结果验证自变量异常的位置。</span><span class="sxs-lookup"><span data-stu-id="98749-121">Notice that this rule does not apply to indexers, where we do expect exceptions as a result of validating the arguments.</span></span>  
  
### <a name="indexed-property-design"></a><span data-ttu-id="98749-122">索引的属性设计</span><span class="sxs-lookup"><span data-stu-id="98749-122">Indexed Property Design</span></span>  
 <span data-ttu-id="98749-123">索引的属性是一个特殊属性，可以有参数，可以在调用使用特殊语法类似于数组索引。</span><span class="sxs-lookup"><span data-stu-id="98749-123">An indexed property is a special property that can have parameters and can be called with special syntax similar to array indexing.</span></span>  
  
 <span data-ttu-id="98749-124">索引的属性通常被称为索引器。</span><span class="sxs-lookup"><span data-stu-id="98749-124">Indexed properties are commonly referred to as indexers.</span></span> <span data-ttu-id="98749-125">应仅在提供的逻辑集合中的项的访问权限的 Api 中使用索引器。</span><span class="sxs-lookup"><span data-stu-id="98749-125">Indexers should be used only in APIs that provide access to items in a logical collection.</span></span> <span data-ttu-id="98749-126">例如，字符串是一系列字符，并使用索引器<xref:System.String?displayProperty=nameWithType>添加了以访问其中的字符。</span><span class="sxs-lookup"><span data-stu-id="98749-126">For example, a string is a collection of characters, and the indexer on <xref:System.String?displayProperty=nameWithType> was added to access its characters.</span></span>  
  
 <span data-ttu-id="98749-127">**✓ CONSIDER** 使用索引器以提供对存储在内部数组中的数据访问。</span><span class="sxs-lookup"><span data-stu-id="98749-127">**✓ CONSIDER** using indexers to provide access to data stored in an internal array.</span></span>  
  
 <span data-ttu-id="98749-128">**✓ CONSIDER** 提供索引器上表示的项的集合的类型。</span><span class="sxs-lookup"><span data-stu-id="98749-128">**✓ CONSIDER** providing indexers on types representing collections of items.</span></span>  
  
 <span data-ttu-id="98749-129">**X AVOID** 使用索引与多个参数的属性。</span><span class="sxs-lookup"><span data-stu-id="98749-129">**X AVOID** using indexed properties with more than one parameter.</span></span>  
  
 <span data-ttu-id="98749-130">如果设计需要多个参数，请重新考虑是否将属性确实表示对逻辑集合取值函数。</span><span class="sxs-lookup"><span data-stu-id="98749-130">If the design requires multiple parameters, reconsider whether the property really represents an accessor to a logical collection.</span></span> <span data-ttu-id="98749-131">如果未显示，而是使用方法。</span><span class="sxs-lookup"><span data-stu-id="98749-131">If it does not, use methods instead.</span></span> <span data-ttu-id="98749-132">请考虑从开始使用的方法名称`Get`或`Set`。</span><span class="sxs-lookup"><span data-stu-id="98749-132">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="98749-133">**X AVOID** 具有以外的其他参数类型的索引器<xref:System.Int32?displayProperty=nameWithType>， <xref:System.Int64?displayProperty=nameWithType>， <xref:System.String?displayProperty=nameWithType>， <xref:System.Object?displayProperty=nameWithType>，或枚举。</span><span class="sxs-lookup"><span data-stu-id="98749-133">**X AVOID** indexers with parameter types other than <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, or an enum.</span></span>  
  
 <span data-ttu-id="98749-134">如果设计需要其他类型的参数，强重新评估是否 API 确实表示对逻辑集合取值函数。</span><span class="sxs-lookup"><span data-stu-id="98749-134">If the design requires other types of parameters, strongly reevaluate whether the API really represents an accessor to a logical collection.</span></span> <span data-ttu-id="98749-135">如果不是，使用一种方法。</span><span class="sxs-lookup"><span data-stu-id="98749-135">If it does not, use a method.</span></span> <span data-ttu-id="98749-136">请考虑从开始使用的方法名称`Get`或`Set`。</span><span class="sxs-lookup"><span data-stu-id="98749-136">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="98749-137">**✓ DO** 使用名称`Item`的索引属性，除非有显然更好的名称 (例如，请参阅<xref:System.String.Chars%2A>属性`System.String`)。</span><span class="sxs-lookup"><span data-stu-id="98749-137">**✓ DO** use the name `Item` for indexed properties unless there is an obviously better name (e.g., see the <xref:System.String.Chars%2A> property on `System.String`).</span></span>  
  
 <span data-ttu-id="98749-138">在 C# 中，索引器的默认命名项。</span><span class="sxs-lookup"><span data-stu-id="98749-138">In C#, indexers are by default named Item.</span></span> <span data-ttu-id="98749-139"><xref:System.Runtime.CompilerServices.IndexerNameAttribute>可用于自定义此名称。</span><span class="sxs-lookup"><span data-stu-id="98749-139">The <xref:System.Runtime.CompilerServices.IndexerNameAttribute> can be used to customize this name.</span></span>  
  
 <span data-ttu-id="98749-140">**X DO NOT** 提供索引器和在语义上等效的方法。</span><span class="sxs-lookup"><span data-stu-id="98749-140">**X DO NOT** provide both an indexer and methods that are semantically equivalent.</span></span>  
  
 <span data-ttu-id="98749-141">**X DO NOT** 提供多个系列中一种类型的重载索引器。</span><span class="sxs-lookup"><span data-stu-id="98749-141">**X DO NOT** provide more than one family of overloaded indexers in one type.</span></span>  
  
 <span data-ttu-id="98749-142">C# 编译器强制这一点。</span><span class="sxs-lookup"><span data-stu-id="98749-142">This is enforced by the C# compiler.</span></span>  
  
 <span data-ttu-id="98749-143">**X DO NOT** 使用非默认索引属性。</span><span class="sxs-lookup"><span data-stu-id="98749-143">**X DO NOT** use nondefault indexed properties.</span></span>  
  
 <span data-ttu-id="98749-144">C# 编译器强制这一点。</span><span class="sxs-lookup"><span data-stu-id="98749-144">This is enforced by the C# compiler.</span></span>  
  
### <a name="property-change-notification-events"></a><span data-ttu-id="98749-145">属性更改通知事件</span><span class="sxs-lookup"><span data-stu-id="98749-145">Property Change Notification Events</span></span>  
 <span data-ttu-id="98749-146">有时是可用于提供事件通知用户中的属性值的更改。</span><span class="sxs-lookup"><span data-stu-id="98749-146">Sometimes it is useful to provide an event notifying the user of changes in a property value.</span></span> <span data-ttu-id="98749-147">例如，`System.Windows.Forms.Control`将引发`TextChanged`的值之后的事件及其`Text`属性已更改。</span><span class="sxs-lookup"><span data-stu-id="98749-147">For example, `System.Windows.Forms.Control` raises a `TextChanged` event after the value of its `Text` property has changed.</span></span>  
  
 <span data-ttu-id="98749-148">**✓ CONSIDER** 引发更改通知事件修改高级 Api （通常是设计器组件） 中的属性值时。</span><span class="sxs-lookup"><span data-stu-id="98749-148">**✓ CONSIDER** raising change notification events when property values in high-level APIs (usually designer components) are modified.</span></span>  
  
 <span data-ttu-id="98749-149">如果用户可以知道当更改对象的属性的一个不错的方案，该对象会引发更改通知事件的属性。</span><span class="sxs-lookup"><span data-stu-id="98749-149">If there is a good scenario for a user to know when a property of an object is changing, the object should raise a change notification event for the property.</span></span>  
  
 <span data-ttu-id="98749-150">但是，它不太可能值得对于之类的基类型或集合的低级 Api 引发此类事件的开销。</span><span class="sxs-lookup"><span data-stu-id="98749-150">However, it is unlikely to be worth the overhead to raise such events for low-level APIs such as base types or collections.</span></span> <span data-ttu-id="98749-151">例如，<xref:System.Collections.Generic.List%601>不会引发此类事件时向列表添加新项和`Count`属性更改。</span><span class="sxs-lookup"><span data-stu-id="98749-151">For example, <xref:System.Collections.Generic.List%601> would not raise such events when a new item is added to the list and the `Count` property changes.</span></span>  
  
 <span data-ttu-id="98749-152">**✓ CONSIDER** 引发更改通知事件的属性的值更改通过外部强制时。</span><span class="sxs-lookup"><span data-stu-id="98749-152">**✓ CONSIDER** raising change notification events when the value of a property changes via external forces.</span></span>  
  
 <span data-ttu-id="98749-153">如果在属性值更改通过某种外部因素 （以通过在对象上调用方法以外的其他方式），则引发事件指示向开发人员的值正在更改和已更改。</span><span class="sxs-lookup"><span data-stu-id="98749-153">If a property value changes via some external force (in a way other than by calling methods on the object), raise events indicate to the developer that the value is changing and has changed.</span></span> <span data-ttu-id="98749-154">一个典型示例是`Text`文本框控件的属性。</span><span class="sxs-lookup"><span data-stu-id="98749-154">A good example is the `Text` property of a text box control.</span></span> <span data-ttu-id="98749-155">当用户键入文本中的`TextBox`，会自动更改的属性值。</span><span class="sxs-lookup"><span data-stu-id="98749-155">When the user types text in a `TextBox`, the property value automatically changes.</span></span>  
  
 <span data-ttu-id="98749-156">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="98749-156">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="98749-157">*通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*</span><span class="sxs-lookup"><span data-stu-id="98749-157">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98749-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="98749-158">See also</span></span>

- [<span data-ttu-id="98749-159">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="98749-159">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="98749-160">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="98749-160">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
