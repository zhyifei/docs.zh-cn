---
title: 接口 (F#)
description: '了解 F # 接口如何指定其他类实现的相关成员的集。'
ms.date: 05/16/2016
ms.openlocfilehash: 6d7f8ee9ea17d2294933f88577c30a96975ae5d4
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47115108"
---
# <a name="interfaces"></a><span data-ttu-id="01dd5-103">接口</span><span class="sxs-lookup"><span data-stu-id="01dd5-103">Interfaces</span></span>

<span data-ttu-id="01dd5-104">*接口*指定其他类实现的相关成员的集。</span><span class="sxs-lookup"><span data-stu-id="01dd5-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="01dd5-105">语法</span><span class="sxs-lookup"><span data-stu-id="01dd5-105">Syntax</span></span>

```fsharp
// Interface declaration:
[ attributes ]
type [accessibility-modifier] interface-name =
    [ interface ]     [ inherit base-interface-name ...]
    abstract member1 : [ argument-types1 -> ] return-type1
    abstract member2 : [ argument-types2 -> ] return-type2
    ...
[ end ]

// Implementing, inside a class type definition:
interface interface-name with
    member self-identifier.member1argument-list = method-body1
    member self-identifier.member2argument-list = method-body2

// Implementing, by using an object expression:
[ attributes ]
let class-name (argument-list) =
    { new interface-name with
        member self-identifier.member1argument-list = method-body1
        member self-identifier.member2argument-list = method-body2
        [ base-interface-definitions ]
    }
    member-list
```

## <a name="remarks"></a><span data-ttu-id="01dd5-106">备注</span><span class="sxs-lookup"><span data-stu-id="01dd5-106">Remarks</span></span>

<span data-ttu-id="01dd5-107">接口声明类似于类声明，只不过未实现成员。</span><span class="sxs-lookup"><span data-stu-id="01dd5-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="01dd5-108">相反，所有成员都是抽象的由关键字`abstract`。</span><span class="sxs-lookup"><span data-stu-id="01dd5-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="01dd5-109">抽象方法不提供方法体。</span><span class="sxs-lookup"><span data-stu-id="01dd5-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="01dd5-110">但是，可以通过包括单独定义的成员一起使用的方法提供默认实现`default`关键字。</span><span class="sxs-lookup"><span data-stu-id="01dd5-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="01dd5-111">执行此操作等效于在其他.NET 语言中的基类中创建的虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="01dd5-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="01dd5-112">可以在实现该接口的类中重写此类的虚方法。</span><span class="sxs-lookup"><span data-stu-id="01dd5-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="01dd5-113">接口的默认可访问性是`public`。</span><span class="sxs-lookup"><span data-stu-id="01dd5-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="01dd5-114">（可选） 可以对每个方法参数使用普通的 F # 语法进行命名：</span><span class="sxs-lookup"><span data-stu-id="01dd5-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="01dd5-115">在上面`ISprintable`示例中，`Print`方法具有单个类型的参数`string`同名`format`。</span><span class="sxs-lookup"><span data-stu-id="01dd5-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="01dd5-116">有两种方法来实现的接口： 通过使用对象表达式，并通过使用类类型。</span><span class="sxs-lookup"><span data-stu-id="01dd5-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="01dd5-117">在任一情况下，类类型或对象表达式为接口的抽象方法提供方法体。</span><span class="sxs-lookup"><span data-stu-id="01dd5-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="01dd5-118">实现是特定于每个类型实现接口。</span><span class="sxs-lookup"><span data-stu-id="01dd5-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="01dd5-119">因此，不同类型的接口方法可能彼此不同。</span><span class="sxs-lookup"><span data-stu-id="01dd5-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="01dd5-120">关键字`interface`和`end`，使用轻量语法时，用于标记的开始和结束的定义，将可选。</span><span class="sxs-lookup"><span data-stu-id="01dd5-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="01dd5-121">如果不使用这些关键字，编译器将尝试推断类型通过分析使用的构造是否是一个类或接口。</span><span class="sxs-lookup"><span data-stu-id="01dd5-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="01dd5-122">如果您定义一个成员，或使用其他类的语法，该类型将解释为一个类。</span><span class="sxs-lookup"><span data-stu-id="01dd5-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="01dd5-123">.NET 编码样式是开始使用大写的所有接口`I`。</span><span class="sxs-lookup"><span data-stu-id="01dd5-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>

## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="01dd5-124">通过使用类类型实现接口</span><span class="sxs-lookup"><span data-stu-id="01dd5-124">Implementing Interfaces by Using Class Types</span></span>

<span data-ttu-id="01dd5-125">可通过使用类类型中实现一个或多个接口`interface`关键字，接口的名称和`with`关键字后, 跟接口成员定义，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="01dd5-125">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="01dd5-126">继承接口实现，因此任何派生的类无需重新实现它们。</span><span class="sxs-lookup"><span data-stu-id="01dd5-126">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>

## <a name="calling-interface-methods"></a><span data-ttu-id="01dd5-127">调用接口方法</span><span class="sxs-lookup"><span data-stu-id="01dd5-127">Calling Interface Methods</span></span>

<span data-ttu-id="01dd5-128">可以仅通过该接口，不能通过类型实现接口的任何对象调用接口方法。</span><span class="sxs-lookup"><span data-stu-id="01dd5-128">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="01dd5-129">因此，可能向上转换为接口类型必须通过使用`:>`运算符或`upcast`为了调用这些方法的运算符。</span><span class="sxs-lookup"><span data-stu-id="01dd5-129">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="01dd5-130">若要调用接口方法具有类型的对象时`SomeClass`，如下面的代码中所示，必须将向上转换为接口类型的对象。</span><span class="sxs-lookup"><span data-stu-id="01dd5-130">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="01dd5-131">一种替代方法是在对象上的向上转换声明一个方法，并调用接口方法，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="01dd5-131">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="01dd5-132">通过使用对象表达式实现接口</span><span class="sxs-lookup"><span data-stu-id="01dd5-132">Implementing Interfaces by Using Object Expressions</span></span>

<span data-ttu-id="01dd5-133">对象表达式提供了一种快捷方法来实现接口。</span><span class="sxs-lookup"><span data-stu-id="01dd5-133">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="01dd5-134">不需要创建一个名为的类型，并只是想支持的接口方法，而无需任何其他方法的对象时很有用。</span><span class="sxs-lookup"><span data-stu-id="01dd5-134">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="01dd5-135">下面的代码说明了对象表达式。</span><span class="sxs-lookup"><span data-stu-id="01dd5-135">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a><span data-ttu-id="01dd5-136">接口继承</span><span class="sxs-lookup"><span data-stu-id="01dd5-136">Interface Inheritance</span></span>

<span data-ttu-id="01dd5-137">接口可以从一个或多个基接口继承。</span><span class="sxs-lookup"><span data-stu-id="01dd5-137">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a><span data-ttu-id="01dd5-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="01dd5-138">See also</span></span>

- [<span data-ttu-id="01dd5-139">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="01dd5-139">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="01dd5-140">对象表达式</span><span class="sxs-lookup"><span data-stu-id="01dd5-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="01dd5-141">类</span><span class="sxs-lookup"><span data-stu-id="01dd5-141">Classes</span></span>](classes.md)
