---
title: "event（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- event
- remove
- event_CSharpKeyword
- add
dev_langs:
- CSharp
helpviewer_keywords:
- event keyword [C#]
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 674e36625a68243afff75f6c5028309dc7aff02a
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="event-c-reference"></a><span data-ttu-id="e2371-102">event（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="e2371-102">event (C# Reference)</span></span>
<span data-ttu-id="e2371-103">`event` 关键字用于声明发布服务器类中的事件。</span><span class="sxs-lookup"><span data-stu-id="e2371-103">The `event` keyword is used to declare an event in a publisher class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2371-104">示例</span><span class="sxs-lookup"><span data-stu-id="e2371-104">Example</span></span>  
 <span data-ttu-id="e2371-105">下面的示例演示如何声明和引发使用 <xref:System.EventHandler> 作为基础委托类型的事件。</span><span class="sxs-lookup"><span data-stu-id="e2371-105">The following example shows how to declare and raise an event that uses <xref:System.EventHandler> as the underlying delegate type.</span></span> <span data-ttu-id="e2371-106">有关演示如何使用泛型 <xref:System.EventHandler%601> 委托类型以及如何订阅事件并创建事件处理程序方法的完整的代码示例，请参阅[如何：发布符合 .NET Framework 准则的事件](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)。</span><span class="sxs-lookup"><span data-stu-id="e2371-106">For the complete code example that also shows how to use the generic <xref:System.EventHandler%601> delegate type and how to subscribe to an event and create an event handler method, see [How to: Publish Events that Conform to .NET Framework Guidelines](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).</span></span>  
  
 <span data-ttu-id="e2371-107">[!code-cs[csrefKeywordsModifiers#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/event_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e2371-107">[!code-cs[csrefKeywordsModifiers#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/event_1.cs)]</span></span>  
  
 <span data-ttu-id="e2371-108">事件是一种特殊的多播委托，仅可以从声明事件的类或结构（发布服务器类）中对其进行调用。</span><span class="sxs-lookup"><span data-stu-id="e2371-108">Events are a special kind of multicast delegate that can only be invoked from within the class or struct where they are declared (the publisher class).</span></span> <span data-ttu-id="e2371-109">如果其他类或结构订阅该事件，则在发布服务器类引发该事件时，将调用其事件处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="e2371-109">If other classes or structs subscribe to the event, their event handler methods will be called when the publisher class raises the event.</span></span> <span data-ttu-id="e2371-110">有关详细信息和代码示例，请参阅[事件](../../../csharp/programming-guide/events/index.md)和[委托](../../../csharp/programming-guide/delegates/index.md)。</span><span class="sxs-lookup"><span data-stu-id="e2371-110">For more information and code examples, see [Events](../../../csharp/programming-guide/events/index.md) and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
 <span data-ttu-id="e2371-111">可以将事件标记为[公共](../../../csharp/language-reference/keywords/public.md)、[专用](../../../csharp/language-reference/keywords/private.md)、[受保护](../../../csharp/language-reference/keywords/protected.md)、[内部](../../../csharp/language-reference/keywords/internal.md)或 `protected internal`。</span><span class="sxs-lookup"><span data-stu-id="e2371-111">Events can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or `protected internal`.</span></span> <span data-ttu-id="e2371-112">这些访问修饰符定义该类的用户访问该事件的方式。</span><span class="sxs-lookup"><span data-stu-id="e2371-112">These access modifiers define how users of the class can access the event.</span></span> <span data-ttu-id="e2371-113">有关详细信息，请参阅[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="e2371-113">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
## <a name="keywords-and-events"></a><span data-ttu-id="e2371-114">关键字和事件</span><span class="sxs-lookup"><span data-stu-id="e2371-114">Keywords and Events</span></span>  
 <span data-ttu-id="e2371-115">下列关键字应用于事件。</span><span class="sxs-lookup"><span data-stu-id="e2371-115">The following keywords apply to events.</span></span>  
  
|<span data-ttu-id="e2371-116">关键字</span><span class="sxs-lookup"><span data-stu-id="e2371-116">Keyword</span></span>|<span data-ttu-id="e2371-117">描述</span><span class="sxs-lookup"><span data-stu-id="e2371-117">Description</span></span>|<span data-ttu-id="e2371-118">更多相关信息</span><span class="sxs-lookup"><span data-stu-id="e2371-118">For more information</span></span>|  
|-------------|-----------------|--------------------------|  
|[<span data-ttu-id="e2371-119">static</span><span class="sxs-lookup"><span data-stu-id="e2371-119">static</span></span>](../../../csharp/language-reference/keywords/static.md)|<span data-ttu-id="e2371-120">使事件可供调用方在任何时候进行调用，即使不存在类的实例。</span><span class="sxs-lookup"><span data-stu-id="e2371-120">Makes the event available to callers at any time, even if no instance of the class exists.</span></span>|[<span data-ttu-id="e2371-121">静态类和静态类成员</span><span class="sxs-lookup"><span data-stu-id="e2371-121">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)|  
|[<span data-ttu-id="e2371-122">virtual</span><span class="sxs-lookup"><span data-stu-id="e2371-122">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)|<span data-ttu-id="e2371-123">允许派生类使用[重写](../../../csharp/language-reference/keywords/override.md)关键字重写事件行为。</span><span class="sxs-lookup"><span data-stu-id="e2371-123">Allows derived classes to override the event behavior by using the [override](../../../csharp/language-reference/keywords/override.md) keyword.</span></span>|[<span data-ttu-id="e2371-124">继承</span><span class="sxs-lookup"><span data-stu-id="e2371-124">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)|  
|[<span data-ttu-id="e2371-125">sealed</span><span class="sxs-lookup"><span data-stu-id="e2371-125">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)|<span data-ttu-id="e2371-126">指定对于派生类，它不再是虚拟的。</span><span class="sxs-lookup"><span data-stu-id="e2371-126">Specifies that for derived classes it is no longer virtual.</span></span>||  
|[<span data-ttu-id="e2371-127">abstract</span><span class="sxs-lookup"><span data-stu-id="e2371-127">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)|<span data-ttu-id="e2371-128">编译器不会生成 `add` 和 `remove` 事件访问器块，因此派生类必须提供其自己的实现。</span><span class="sxs-lookup"><span data-stu-id="e2371-128">The compiler will not generate the `add` and `remove` event accessor blocks and therefore derived classes must provide their own implementation.</span></span>||  
  
 <span data-ttu-id="e2371-129">可以通过使用[静态](../../../csharp/language-reference/keywords/static.md)关键字将事件声明为静态事件。</span><span class="sxs-lookup"><span data-stu-id="e2371-129">An event may be declared as a static event by using the [static](../../../csharp/language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="e2371-130">这可使事件可供调用方在任何时候进行调用，即使不存在类的实例。</span><span class="sxs-lookup"><span data-stu-id="e2371-130">This makes the event available to callers at any time, even if no instance of the class exists.</span></span> <span data-ttu-id="e2371-131">有关详细信息，请参阅[静态类和静态类成员](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)。</span><span class="sxs-lookup"><span data-stu-id="e2371-131">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="e2371-132">可以通过使用[虚拟](../../../csharp/language-reference/keywords/virtual.md)关键字将事件标记为虚事件。</span><span class="sxs-lookup"><span data-stu-id="e2371-132">An event can be marked as a virtual event by using the [virtual](../../../csharp/language-reference/keywords/virtual.md) keyword.</span></span> <span data-ttu-id="e2371-133">这可使派生类使用[重写](../../../csharp/language-reference/keywords/override.md)关键字重写事件行为。</span><span class="sxs-lookup"><span data-stu-id="e2371-133">This enables derived classes to override the event behavior by using the [override](../../../csharp/language-reference/keywords/override.md) keyword.</span></span> <span data-ttu-id="e2371-134">有关详细信息，请参阅[继承](../../../csharp/programming-guide/classes-and-structs/inheritance.md)。</span><span class="sxs-lookup"><span data-stu-id="e2371-134">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span> <span data-ttu-id="e2371-135">重写虚拟事件的事件也可以为[密封](../../../csharp/language-reference/keywords/sealed.md)，指定对于派生类，它不再是虚拟的。</span><span class="sxs-lookup"><span data-stu-id="e2371-135">An event overriding a virtual event can also be [sealed](../../../csharp/language-reference/keywords/sealed.md), which specifies that for derived classes it is no longer virtual.</span></span> <span data-ttu-id="e2371-136">最后，可以声明事件为[抽象](../../../csharp/language-reference/keywords/abstract.md)，这意味着编译器将不会生成 `add` 和 `remove` 事件访问器块。</span><span class="sxs-lookup"><span data-stu-id="e2371-136">Lastly, an event can be declared [abstract](../../../csharp/language-reference/keywords/abstract.md), which means that the compiler will not generate the `add` and `remove` event accessor blocks.</span></span> <span data-ttu-id="e2371-137">因此，派生类必须提供其自己的实现。</span><span class="sxs-lookup"><span data-stu-id="e2371-137">Therefore derived classes must provide their own implementation.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e2371-138">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="e2371-138">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e2371-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2371-139">See Also</span></span>  
 <span data-ttu-id="e2371-140">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e2371-140">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e2371-141">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e2371-141">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e2371-142">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="e2371-142">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="e2371-143">[添加](../../../csharp/language-reference/keywords/add.md) </span><span class="sxs-lookup"><span data-stu-id="e2371-143">[add](../../../csharp/language-reference/keywords/add.md) </span></span>  
 <span data-ttu-id="e2371-144">[删除](../../../csharp/language-reference/keywords/remove.md) </span><span class="sxs-lookup"><span data-stu-id="e2371-144">[remove](../../../csharp/language-reference/keywords/remove.md) </span></span>  
 <span data-ttu-id="e2371-145">[修饰符](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="e2371-145">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 [<span data-ttu-id="e2371-146">如何：合并委托（多播委托）</span><span class="sxs-lookup"><span data-stu-id="e2371-146">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)

