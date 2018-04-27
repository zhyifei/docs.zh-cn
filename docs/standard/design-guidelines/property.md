---
title: 属性设计
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6dcb164daea6809f0d0e9c221f182d5019385bc1
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="property-design"></a><span data-ttu-id="dc71c-102">属性设计</span><span class="sxs-lookup"><span data-stu-id="dc71c-102">Property Design</span></span>
<span data-ttu-id="dc71c-103">虽然从技术上讲非常类似于方法属性，但它们是在其使用情况方面有很大差异。</span><span class="sxs-lookup"><span data-stu-id="dc71c-103">Although properties are technically very similar to methods, they are quite different in terms of their usage scenarios.</span></span> <span data-ttu-id="dc71c-104">它们应被视为智能字段。</span><span class="sxs-lookup"><span data-stu-id="dc71c-104">They should be seen as smart fields.</span></span> <span data-ttu-id="dc71c-105">它们具有字段，调用语法和方法的灵活性。</span><span class="sxs-lookup"><span data-stu-id="dc71c-105">They have the calling syntax of fields, and the flexibility of methods.</span></span>  
  
 <span data-ttu-id="dc71c-106">**✓ 执行**创建仅限 get 的属性，如果调用方应不能更改属性的值。</span><span class="sxs-lookup"><span data-stu-id="dc71c-106">**✓ DO** create get-only properties if the caller should not be able to change the value of the property.</span></span>  
  
 <span data-ttu-id="dc71c-107">请记住，如果类型的属性是可变的引用类型，可以更改属性值，即使该属性是只 get。</span><span class="sxs-lookup"><span data-stu-id="dc71c-107">Keep in mind that if the type of the property is a mutable reference type, the property value can be changed even if the property is get-only.</span></span>  
  
 <span data-ttu-id="dc71c-108">**X 不**仅属性的 setter 具有更广泛的可访问性比 getter 提供。</span><span class="sxs-lookup"><span data-stu-id="dc71c-108">**X DO NOT** provide set-only properties or properties with the setter having broader accessibility than the getter.</span></span>  
  
 <span data-ttu-id="dc71c-109">例如，请使用公共 setter 和受保护的 getter 使用属性。</span><span class="sxs-lookup"><span data-stu-id="dc71c-109">For example, do not use properties with a public setter and a protected getter.</span></span>  
  
 <span data-ttu-id="dc71c-110">如果不能提供属性 getter，请改为实现作为一种方法的功能。</span><span class="sxs-lookup"><span data-stu-id="dc71c-110">If the property getter cannot be provided, implement the functionality as a method instead.</span></span> <span data-ttu-id="dc71c-111">请考虑启动的方法名`Set`并在后面加什么您将已命名属性。</span><span class="sxs-lookup"><span data-stu-id="dc71c-111">Consider starting the method name with `Set` and follow with what you would have named the property.</span></span> <span data-ttu-id="dc71c-112">例如，<xref:System.AppDomain>具有一个方法`SetCachePath`而不是让一个名为仅属性`CachePath`。</span><span class="sxs-lookup"><span data-stu-id="dc71c-112">For example, <xref:System.AppDomain> has a method called `SetCachePath` instead of having a set-only property called `CachePath`.</span></span>  
  
 <span data-ttu-id="dc71c-113">**✓ 执行**提供的所有属性，确保，默认值不会导致安全漏洞或您对此低效代码的意义的默认值。</span><span class="sxs-lookup"><span data-stu-id="dc71c-113">**✓ DO** provide sensible default values for all properties, ensuring that the defaults do not result in a security hole or terribly inefficient code.</span></span>  
  
 <span data-ttu-id="dc71c-114">**✓ 执行**允许将属性按任何顺序设置，即使这会导致临时无效状态的对象。</span><span class="sxs-lookup"><span data-stu-id="dc71c-114">**✓ DO** allow properties to be set in any order even if this results in a temporary invalid state of the object.</span></span>  
  
 <span data-ttu-id="dc71c-115">它是常见的两个或多个要到其中一个属性的某些值也可能是无效的点又彼此相关的属性对同一个对象提供的其他属性的值。</span><span class="sxs-lookup"><span data-stu-id="dc71c-115">It is common for two or more properties to be interrelated to a point where some values of one property might be invalid given the values of other properties on the same object.</span></span> <span data-ttu-id="dc71c-116">在这种情况下，从无效的状态导致的异常应会推迟，直到又彼此相关的属性实际一起使用的对象。</span><span class="sxs-lookup"><span data-stu-id="dc71c-116">In such cases, exceptions resulting from the invalid state should be postponed until the interrelated properties are actually used together by the object.</span></span>  
  
 <span data-ttu-id="dc71c-117">**✓ 执行**保留以前的值，如果属性 setter 将引发异常。</span><span class="sxs-lookup"><span data-stu-id="dc71c-117">**✓ DO** preserve the previous value if a property setter throws an exception.</span></span>  
  
 <span data-ttu-id="dc71c-118">**请避免 x**属性 getter 从引发异常。</span><span class="sxs-lookup"><span data-stu-id="dc71c-118">**X AVOID** throwing exceptions from property getters.</span></span>  
  
 <span data-ttu-id="dc71c-119">属性 getter 应该是简单的操作，并且不应具有任何前置条件。</span><span class="sxs-lookup"><span data-stu-id="dc71c-119">Property getters should be simple operations and should not have any preconditions.</span></span> <span data-ttu-id="dc71c-120">如果 getter 可能会引发异常，它应可能重新设计是一种方法。</span><span class="sxs-lookup"><span data-stu-id="dc71c-120">If a getter can throw an exception, it should probably be redesigned to be a method.</span></span> <span data-ttu-id="dc71c-121">请注意，此规则不适用于索引器，我们执行预期异常导致验证自变量的位置。</span><span class="sxs-lookup"><span data-stu-id="dc71c-121">Notice that this rule does not apply to indexers, where we do expect exceptions as a result of validating the arguments.</span></span>  
  
### <a name="indexed-property-design"></a><span data-ttu-id="dc71c-122">索引的属性设计</span><span class="sxs-lookup"><span data-stu-id="dc71c-122">Indexed Property Design</span></span>  
 <span data-ttu-id="dc71c-123">索引的属性是一个特殊属性，可以具有的参数，并且可以使用类似于数组索引的特殊语法调用。</span><span class="sxs-lookup"><span data-stu-id="dc71c-123">An indexed property is a special property that can have parameters and can be called with special syntax similar to array indexing.</span></span>  
  
 <span data-ttu-id="dc71c-124">索引的属性通常称为索引器。</span><span class="sxs-lookup"><span data-stu-id="dc71c-124">Indexed properties are commonly referred to as indexers.</span></span> <span data-ttu-id="dc71c-125">应仅在提供对逻辑集合中的项的访问的 Api 中使用索引器。</span><span class="sxs-lookup"><span data-stu-id="dc71c-125">Indexers should be used only in APIs that provide access to items in a logical collection.</span></span> <span data-ttu-id="dc71c-126">例如，一个字符串是字符和上的索引器的集合<xref:System.String?displayProperty=nameWithType>添加了来访问它的字符。</span><span class="sxs-lookup"><span data-stu-id="dc71c-126">For example, a string is a collection of characters, and the indexer on <xref:System.String?displayProperty=nameWithType> was added to access its characters.</span></span>  
  
 <span data-ttu-id="dc71c-127">**请考虑 ✓**使用索引器以提供对存储在内部数组中的数据访问。</span><span class="sxs-lookup"><span data-stu-id="dc71c-127">**✓ CONSIDER** using indexers to provide access to data stored in an internal array.</span></span>  
  
 <span data-ttu-id="dc71c-128">**请考虑 ✓**提供索引器上表示的项的集合的类型。</span><span class="sxs-lookup"><span data-stu-id="dc71c-128">**✓ CONSIDER** providing indexers on types representing collections of items.</span></span>  
  
 <span data-ttu-id="dc71c-129">**请避免 x**使用索引与多个参数的属性。</span><span class="sxs-lookup"><span data-stu-id="dc71c-129">**X AVOID** using indexed properties with more than one parameter.</span></span>  
  
 <span data-ttu-id="dc71c-130">如果设计需要多个参数，请重新考虑是否属性确实表示一个访问器对逻辑集合。</span><span class="sxs-lookup"><span data-stu-id="dc71c-130">If the design requires multiple parameters, reconsider whether the property really represents an accessor to a logical collection.</span></span> <span data-ttu-id="dc71c-131">如果不存在，请改为使用方法。</span><span class="sxs-lookup"><span data-stu-id="dc71c-131">If it does not, use methods instead.</span></span> <span data-ttu-id="dc71c-132">请考虑启动的方法名`Get`或`Set`。</span><span class="sxs-lookup"><span data-stu-id="dc71c-132">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="dc71c-133">**请避免 x**具有以外的其他参数类型的索引器<xref:System.Int32?displayProperty=nameWithType>， <xref:System.Int64?displayProperty=nameWithType>， <xref:System.String?displayProperty=nameWithType>， <xref:System.Object?displayProperty=nameWithType>，或枚举。</span><span class="sxs-lookup"><span data-stu-id="dc71c-133">**X AVOID** indexers with parameter types other than <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, or an enum.</span></span>  
  
 <span data-ttu-id="dc71c-134">如果设计需要其他类型的参数，强重新评估是否 API 确实表示一个访问器对逻辑集合。</span><span class="sxs-lookup"><span data-stu-id="dc71c-134">If the design requires other types of parameters, strongly reevaluate whether the API really represents an accessor to a logical collection.</span></span> <span data-ttu-id="dc71c-135">如果不存在，请使用方法。</span><span class="sxs-lookup"><span data-stu-id="dc71c-135">If it does not, use a method.</span></span> <span data-ttu-id="dc71c-136">请考虑启动的方法名`Get`或`Set`。</span><span class="sxs-lookup"><span data-stu-id="dc71c-136">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="dc71c-137">**✓ 执行**使用名称`Item`的索引属性，除非有显然更好的名称 (例如，请参阅<xref:System.String.Chars%2A>属性`System.String`)。</span><span class="sxs-lookup"><span data-stu-id="dc71c-137">**✓ DO** use the name `Item` for indexed properties unless there is an obviously better name (e.g., see the <xref:System.String.Chars%2A> property on `System.String`).</span></span>  
  
 <span data-ttu-id="dc71c-138">在 C# 中，索引器在默认情况下都将名为项。</span><span class="sxs-lookup"><span data-stu-id="dc71c-138">In C#, indexers are by default named Item.</span></span> <span data-ttu-id="dc71c-139"><xref:System.Runtime.CompilerServices.IndexerNameAttribute>可以用于自定义此名称。</span><span class="sxs-lookup"><span data-stu-id="dc71c-139">The <xref:System.Runtime.CompilerServices.IndexerNameAttribute> can be used to customize this name.</span></span>  
  
 <span data-ttu-id="dc71c-140">**X 不**提供索引器和在语义上等效的方法。</span><span class="sxs-lookup"><span data-stu-id="dc71c-140">**X DO NOT** provide both an indexer and methods that are semantically equivalent.</span></span>  
  
 <span data-ttu-id="dc71c-141">**X 不**提供多个系列中一种类型的重载索引器。</span><span class="sxs-lookup"><span data-stu-id="dc71c-141">**X DO NOT** provide more than one family of overloaded indexers in one type.</span></span>  
  
 <span data-ttu-id="dc71c-142">这是由 C# 编译器实施的。</span><span class="sxs-lookup"><span data-stu-id="dc71c-142">This is enforced by the C# compiler.</span></span>  
  
 <span data-ttu-id="dc71c-143">**X 不**使用非默认索引属性。</span><span class="sxs-lookup"><span data-stu-id="dc71c-143">**X DO NOT** use nondefault indexed properties.</span></span>  
  
 <span data-ttu-id="dc71c-144">这是由 C# 编译器实施的。</span><span class="sxs-lookup"><span data-stu-id="dc71c-144">This is enforced by the C# compiler.</span></span>  
  
### <a name="property-change-notification-events"></a><span data-ttu-id="dc71c-145">属性更改通知事件</span><span class="sxs-lookup"><span data-stu-id="dc71c-145">Property Change Notification Events</span></span>  
 <span data-ttu-id="dc71c-146">有时很有用提供通知中的属性值的更改的用户的事件。</span><span class="sxs-lookup"><span data-stu-id="dc71c-146">Sometimes it is useful to provide an event notifying the user of changes in a property value.</span></span> <span data-ttu-id="dc71c-147">例如，`System.Windows.Forms.Control`引发`TextChanged`后的值的事件其`Text`属性已更改。</span><span class="sxs-lookup"><span data-stu-id="dc71c-147">For example, `System.Windows.Forms.Control` raises a `TextChanged` event after the value of its `Text` property has changed.</span></span>  
  
 <span data-ttu-id="dc71c-148">**请考虑 ✓**引发更改通知事件修改高级 Api （通常是设计器组件） 中的属性值时。</span><span class="sxs-lookup"><span data-stu-id="dc71c-148">**✓ CONSIDER** raising change notification events when property values in high-level APIs (usually designer components) are modified.</span></span>  
  
 <span data-ttu-id="dc71c-149">如果没有一种情况最用户知道当更改对象的属性，该对象应引发更改通知事件的属性。</span><span class="sxs-lookup"><span data-stu-id="dc71c-149">If there is a good scenario for a user to know when a property of an object is changing, the object should raise a change notification event for the property.</span></span>  
  
 <span data-ttu-id="dc71c-150">但是，很可能是值得的开销，若要此类事件针对低级别 Api，如基类型或集合。</span><span class="sxs-lookup"><span data-stu-id="dc71c-150">However, it is unlikely to be worth the overhead to raise such events for low-level APIs such as base types or collections.</span></span> <span data-ttu-id="dc71c-151">例如，<xref:System.Collections.Generic.List%601>不会引发一个新项添加到列表时，此类事件和`Count`属性更改。</span><span class="sxs-lookup"><span data-stu-id="dc71c-151">For example, <xref:System.Collections.Generic.List%601> would not raise such events when a new item is added to the list and the `Count` property changes.</span></span>  
  
 <span data-ttu-id="dc71c-152">**请考虑 ✓**引发更改通知事件的属性的值更改通过外部强制时。</span><span class="sxs-lookup"><span data-stu-id="dc71c-152">**✓ CONSIDER** raising change notification events when the value of a property changes via external forces.</span></span>  
  
 <span data-ttu-id="dc71c-153">如果属性值更改通过某种外部因素 （以通过在对象上调用方法以外的其他方式），则引发事件指示向开发人员值正在更改和已更改。</span><span class="sxs-lookup"><span data-stu-id="dc71c-153">If a property value changes via some external force (in a way other than by calling methods on the object), raise events indicate to the developer that the value is changing and has changed.</span></span> <span data-ttu-id="dc71c-154">一个很好示例是`Text`文本框控件的属性。</span><span class="sxs-lookup"><span data-stu-id="dc71c-154">A good example is the `Text` property of a text box control.</span></span> <span data-ttu-id="dc71c-155">当用户输入中的文本`TextBox`，会自动更改的属性值。</span><span class="sxs-lookup"><span data-stu-id="dc71c-155">When the user types text in a `TextBox`, the property value automatically changes.</span></span>  
  
 <span data-ttu-id="dc71c-156">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="dc71c-156">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="dc71c-157">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="dc71c-157">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc71c-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="dc71c-158">See Also</span></span>  
 [<span data-ttu-id="dc71c-159">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="dc71c-159">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="dc71c-160">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="dc71c-160">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
