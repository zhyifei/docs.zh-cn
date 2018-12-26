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
# <a name="property-design"></a><span data-ttu-id="2c127-102">属性设计</span><span class="sxs-lookup"><span data-stu-id="2c127-102">Property Design</span></span>
<span data-ttu-id="2c127-103">虽然属性在技术上与方法非常相似，但它们的使用场景却截然不同。</span><span class="sxs-lookup"><span data-stu-id="2c127-103">Although properties are technically very similar to methods, they are quite different in terms of their usage scenarios.</span></span> <span data-ttu-id="2c127-104">属性应被视为聪明的字段。</span><span class="sxs-lookup"><span data-stu-id="2c127-104">They should be seen as smart fields.</span></span> <span data-ttu-id="2c127-105">它们兼具字段的调用语法和方法的灵活性。</span><span class="sxs-lookup"><span data-stu-id="2c127-105">They have the calling syntax of fields, and the flexibility of methods.</span></span>  
  
 <span data-ttu-id="2c127-106">**✓ 务必**创建 get-only 属性，如果调用方不能更改属性值的话。</span><span class="sxs-lookup"><span data-stu-id="2c127-106">**✓ DO** create get-only properties if the caller should not be able to change the value of the property.</span></span>  
  
 <span data-ttu-id="2c127-107">请记住，如果属性的类型是可变的引用类型，则即使属性为 get-only，也可以更改属性值。</span><span class="sxs-lookup"><span data-stu-id="2c127-107">Keep in mind that if the type of the property is a mutable reference type, the property value can be changed even if the property is get-only.</span></span>  
  
 <span data-ttu-id="2c127-108">**X 切忌**提供 set-only 属性，或其 setter 的可访问性比 getter 更广泛的属性。</span><span class="sxs-lookup"><span data-stu-id="2c127-108">**X DO NOT** provide set-only properties or properties with the setter having broader accessibility than the getter.</span></span>  
  
 <span data-ttu-id="2c127-109">例如，不要使用具有公共 setter 和受保护的 getter 的属性。</span><span class="sxs-lookup"><span data-stu-id="2c127-109">For example, do not use properties with a public setter and a protected getter.</span></span>  
  
 <span data-ttu-id="2c127-110">如果无法提供属性 getter，请将该功能实现为方法。</span><span class="sxs-lookup"><span data-stu-id="2c127-110">If the property getter cannot be provided, implement the functionality as a method instead.</span></span> <span data-ttu-id="2c127-111">考虑将方法名称以 `Set` 开始，在后面添加你对该属性的命名。</span><span class="sxs-lookup"><span data-stu-id="2c127-111">Consider starting the method name with `Set` and follow with what you would have named the property.</span></span> <span data-ttu-id="2c127-112">如，<xref:System.AppDomain> 有一个名为 `SetCachePath` 的方法，而不是一个名为 `CachePath` 的 set-only 属性。</span><span class="sxs-lookup"><span data-stu-id="2c127-112">For example, <xref:System.AppDomain> has a method called `SetCachePath` instead of having a set-only property called `CachePath`.</span></span>  
  
 <span data-ttu-id="2c127-113">**✓ 务必**为所有属性提供合理的默认值，确保默认值不会导致安全漏洞或严重低效的代码。</span><span class="sxs-lookup"><span data-stu-id="2c127-113">**✓ DO** provide sensible default values for all properties, ensuring that the defaults do not result in a security hole or terribly inefficient code.</span></span>  
  
 <span data-ttu-id="2c127-114">**✓ 务必**允许将属性按任何顺序设置，即使这会导致对象的临时无效状态。</span><span class="sxs-lookup"><span data-stu-id="2c127-114">**✓ DO** allow properties to be set in any order even if this results in a temporary invalid state of the object.</span></span>  
  
 <span data-ttu-id="2c127-115">在给定同一对象上的其他属性的值的情况下，一个属性的某些值可能是无效的，这是导致两个或多个属性相关联的一种常见况。</span><span class="sxs-lookup"><span data-stu-id="2c127-115">It is common for two or more properties to be interrelated to a point where some values of one property might be invalid given the values of other properties on the same object.</span></span> <span data-ttu-id="2c127-116">在这种情况下，无效状态导致的异常应该会推迟，直到对象实际将这些相关属性一起使用。</span><span class="sxs-lookup"><span data-stu-id="2c127-116">In such cases, exceptions resulting from the invalid state should be postponed until the interrelated properties are actually used together by the object.</span></span>  
  
 <span data-ttu-id="2c127-117">**✓ 务必**在属性 setter 引发异常时保留以前的值。</span><span class="sxs-lookup"><span data-stu-id="2c127-117">**✓ DO** preserve the previous value if a property setter throws an exception.</span></span>  
  
 <span data-ttu-id="2c127-118">**X 避免**从属性 getter 引发异常。</span><span class="sxs-lookup"><span data-stu-id="2c127-118">**X AVOID** throwing exceptions from property getters.</span></span>  
  
 <span data-ttu-id="2c127-119">属性 getter 应该是简单的操作，不应该有任何前置条件。</span><span class="sxs-lookup"><span data-stu-id="2c127-119">Property getters should be simple operations and should not have any preconditions.</span></span> <span data-ttu-id="2c127-120">如果某个 getter 可能会引发异常，则应该将其重新设计为方法。</span><span class="sxs-lookup"><span data-stu-id="2c127-120">If a getter can throw an exception, it should probably be redesigned to be a method.</span></span> <span data-ttu-id="2c127-121">请注意，此规则不适用于索引器，因为我们确实会因验证参数而导致异常。</span><span class="sxs-lookup"><span data-stu-id="2c127-121">Notice that this rule does not apply to indexers, where we do expect exceptions as a result of validating the arguments.</span></span>  
  
### <a name="indexed-property-design"></a><span data-ttu-id="2c127-122">索引属性设计</span><span class="sxs-lookup"><span data-stu-id="2c127-122">Indexed Property Design</span></span>  
 <span data-ttu-id="2c127-123">索引属性是一个特殊属性，可以具有参数，并且可以使用与数组索引类似的特殊语法进行调用。</span><span class="sxs-lookup"><span data-stu-id="2c127-123">An indexed property is a special property that can have parameters and can be called with special syntax similar to array indexing.</span></span>  
  
 <span data-ttu-id="2c127-124">索引属性通常称为索引器。</span><span class="sxs-lookup"><span data-stu-id="2c127-124">Indexed properties are commonly referred to as indexers.</span></span> <span data-ttu-id="2c127-125">索引器应仅用于提供对逻辑集合中项目的访问的 API。</span><span class="sxs-lookup"><span data-stu-id="2c127-125">Indexers should be used only in APIs that provide access to items in a logical collection.</span></span> <span data-ttu-id="2c127-126">例如，字符串是字符的集合，在索引器上添加了 <xref:System.String?displayProperty=nameWithType> 即可访问其字符。</span><span class="sxs-lookup"><span data-stu-id="2c127-126">For example, a string is a collection of characters, and the indexer on <xref:System.String?displayProperty=nameWithType> was added to access its characters.</span></span>  
  
 <span data-ttu-id="2c127-127">**✓ 考虑**使用索引器提供对存储在内部数组中的数据的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2c127-127">**✓ CONSIDER** using indexers to provide access to data stored in an internal array.</span></span>  
  
 <span data-ttu-id="2c127-128">**✓ 考虑**为表示项目集合的类型提供索引器。</span><span class="sxs-lookup"><span data-stu-id="2c127-128">**✓ CONSIDER** providing indexers on types representing collections of items.</span></span>  
  
 <span data-ttu-id="2c127-129">**X 避免**使用带有一个以上参数的索引属性。</span><span class="sxs-lookup"><span data-stu-id="2c127-129">**X AVOID** using indexed properties with more than one parameter.</span></span>  
  
 <span data-ttu-id="2c127-130">如果设计需要多个参数，请重新考虑该属性是否真正代表逻辑集合的访问者。</span><span class="sxs-lookup"><span data-stu-id="2c127-130">If the design requires multiple parameters, reconsider whether the property really represents an accessor to a logical collection.</span></span> <span data-ttu-id="2c127-131">如果不是，请改用方法。</span><span class="sxs-lookup"><span data-stu-id="2c127-131">If it does not, use methods instead.</span></span> <span data-ttu-id="2c127-132">考虑使用 `Get` 或 `Set` 开头的方法名称。</span><span class="sxs-lookup"><span data-stu-id="2c127-132">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="2c127-133">**X 避免** 使用具有 <xref:System.Int32?displayProperty=nameWithType>、<xref:System.Int64?displayProperty=nameWithType>、<xref:System.String?displayProperty=nameWithType>、<xref:System.Object?displayProperty=nameWithType> 以外参数类型的索引器，或枚举。</span><span class="sxs-lookup"><span data-stu-id="2c127-133">**X AVOID** indexers with parameter types other than <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, or an enum.</span></span>  
  
 <span data-ttu-id="2c127-134">如果设计需要其他类型的参数，请仔细重新评估 API 是否真正代表逻辑集合的访问者。</span><span class="sxs-lookup"><span data-stu-id="2c127-134">If the design requires other types of parameters, strongly reevaluate whether the API really represents an accessor to a logical collection.</span></span> <span data-ttu-id="2c127-135">如果不是，请使用方法。</span><span class="sxs-lookup"><span data-stu-id="2c127-135">If it does not, use a method.</span></span> <span data-ttu-id="2c127-136">考虑使用 `Get` 或 `Set` 开头的方法名称</span><span class="sxs-lookup"><span data-stu-id="2c127-136">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="2c127-137">**✓ 务必**使用 `Item` 作为索引属性的名称，除非有明显更好的名称（例如，请参阅 `System.String` 上的 <xref:System.String.Chars%2A>属性）。</span><span class="sxs-lookup"><span data-stu-id="2c127-137">**✓ DO** use the name `Item` for indexed properties unless there is an obviously better name (e.g., see the <xref:System.String.Chars%2A> property on `System.String`).</span></span>  
  
 <span data-ttu-id="2c127-138">在 C# 中，索引器默认名称为 Item。</span><span class="sxs-lookup"><span data-stu-id="2c127-138">In C#, indexers are by default named Item.</span></span> <span data-ttu-id="2c127-139"><xref:System.Runtime.CompilerServices.IndexerNameAttribute> 可用于自定义此名称。</span><span class="sxs-lookup"><span data-stu-id="2c127-139">The <xref:System.Runtime.CompilerServices.IndexerNameAttribute> can be used to customize this name.</span></span>  
  
 <span data-ttu-id="2c127-140">**X 切忌**提供在语义方面等效的索引器和方法。</span><span class="sxs-lookup"><span data-stu-id="2c127-140">**X DO NOT** provide both an indexer and methods that are semantically equivalent.</span></span>  
  
 <span data-ttu-id="2c127-141">**X 切忌**在一种类型中提供多个重载索引器系列。</span><span class="sxs-lookup"><span data-stu-id="2c127-141">**X DO NOT** provide more than one family of overloaded indexers in one type.</span></span>  
  
 <span data-ttu-id="2c127-142">此准则由 C# 编译器强制执行。</span><span class="sxs-lookup"><span data-stu-id="2c127-142">This is enforced by the C# compiler.</span></span>  
  
 <span data-ttu-id="2c127-143">**X 切忌**使用非默认索引属性。</span><span class="sxs-lookup"><span data-stu-id="2c127-143">**X DO NOT** use nondefault indexed properties.</span></span>  
  
 <span data-ttu-id="2c127-144">此准则由 C# 编译器强制执行。</span><span class="sxs-lookup"><span data-stu-id="2c127-144">This is enforced by the C# compiler.</span></span>  
  
### <a name="property-change-notification-events"></a><span data-ttu-id="2c127-145">属性更改通知事件</span><span class="sxs-lookup"><span data-stu-id="2c127-145">Property Change Notification Events</span></span>  
 <span data-ttu-id="2c127-146">有时，提供用于通知用户属性值更改的事件是很有用的。</span><span class="sxs-lookup"><span data-stu-id="2c127-146">Sometimes it is useful to provide an event notifying the user of changes in a property value.</span></span> <span data-ttu-id="2c127-147">例如，`System.Windows.Forms.Control` 在其 `Text` 属性的值发生变化后引发 `TextChanged` 事件。</span><span class="sxs-lookup"><span data-stu-id="2c127-147">For example, `System.Windows.Forms.Control` raises a `TextChanged` event after the value of its `Text` property has changed.</span></span>  
  
 <span data-ttu-id="2c127-148">**✓ 考虑**在修改高级API（通常是设计器组件）中的属性值时引发更改知事件。</span><span class="sxs-lookup"><span data-stu-id="2c127-148">**✓ CONSIDER** raising change notification events when property values in high-level APIs (usually designer components) are modified.</span></span>  
  
 <span data-ttu-id="2c127-149">如果具备可让用户知道对象的属性何时发生变化的有效方案，则该对象应该该属性引发更改通知事件。</span><span class="sxs-lookup"><span data-stu-id="2c127-149">If there is a good scenario for a user to know when a property of an object is changing, the object should raise a change notification event for the property.</span></span>  
  
 <span data-ttu-id="2c127-150">但是，可能并不值得为基础类型或集合等低级 API 引发此类事件。</span><span class="sxs-lookup"><span data-stu-id="2c127-150">However, it is unlikely to be worth the overhead to raise such events for low-level APIs such as base types or collections.</span></span> <span data-ttu-id="2c127-151">例如，向列表添加新项且 `Count` 属性更改时，<xref:System.Collections.Generic.List%601> 不会引发此类事件。</span><span class="sxs-lookup"><span data-stu-id="2c127-151">For example, <xref:System.Collections.Generic.List%601> would not raise such events when a new item is added to the list and the `Count` property changes.</span></span>  
  
 <span data-ttu-id="2c127-152">**✓ 考虑**当属性值因外力而变化时，引发更改通知事件。</span><span class="sxs-lookup"><span data-stu-id="2c127-152">**✓ CONSIDER** raising change notification events when the value of a property changes via external forces.</span></span>  
  
 <span data-ttu-id="2c127-153">如果属性值通过某种外力（通过调用对象上的方法以外的方式）发生更改。则引发事件向开发人员指示值正在更改并已更改。</span><span class="sxs-lookup"><span data-stu-id="2c127-153">If a property value changes via some external force (in a way other than by calling methods on the object), raise events indicate to the developer that the value is changing and has changed.</span></span> <span data-ttu-id="2c127-154">一个典型示例是文本框控件的 `Text` 属性。</span><span class="sxs-lookup"><span data-stu-id="2c127-154">A good example is the `Text` property of a text box control.</span></span> <span data-ttu-id="2c127-155">当用户在 `TextBox` 中键入文本时，属性值会自动更改。</span><span class="sxs-lookup"><span data-stu-id="2c127-155">When the user types text in a `TextBox`, the property value automatically changes.</span></span>  
  
 <span data-ttu-id="2c127-156">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="2c127-156">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="2c127-157">*通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*</span><span class="sxs-lookup"><span data-stu-id="2c127-157">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c127-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c127-158">See also</span></span>

- [<span data-ttu-id="2c127-159">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="2c127-159">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="2c127-160">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="2c127-160">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
