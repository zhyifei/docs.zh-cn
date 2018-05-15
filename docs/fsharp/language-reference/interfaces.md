---
title: 接口 (F#)
description: '了解如何 F # 接口指定的其他类实现的相关成员集。'
ms.date: 05/16/2016
ms.openlocfilehash: 54ae8a2840ce26814be25f08c3ed02e12df6b7c0
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2018
---
# <a name="interfaces"></a><span data-ttu-id="4a16f-103">接口</span><span class="sxs-lookup"><span data-stu-id="4a16f-103">Interfaces</span></span>

<span data-ttu-id="4a16f-104">*接口*指定的其他类实现的相关成员集。</span><span class="sxs-lookup"><span data-stu-id="4a16f-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="4a16f-105">语法</span><span class="sxs-lookup"><span data-stu-id="4a16f-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="4a16f-106">备注</span><span class="sxs-lookup"><span data-stu-id="4a16f-106">Remarks</span></span>
<span data-ttu-id="4a16f-107">接口声明类似于类声明，只不过未实现成员。</span><span class="sxs-lookup"><span data-stu-id="4a16f-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="4a16f-108">相反，所有成员都是抽象的由关键字`abstract`。</span><span class="sxs-lookup"><span data-stu-id="4a16f-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="4a16f-109">抽象方法不提供方法体。</span><span class="sxs-lookup"><span data-stu-id="4a16f-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="4a16f-110">但是，可以通过包括单独定义的成员作为连同方法提供的默认实现`default`关键字。</span><span class="sxs-lookup"><span data-stu-id="4a16f-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="4a16f-111">这样相当于在基类中其他.NET 语言中创建的虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="4a16f-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="4a16f-112">可以实现接口的类中重写此类的虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="4a16f-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="4a16f-113">接口的默认可访问性是`public`。</span><span class="sxs-lookup"><span data-stu-id="4a16f-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="4a16f-114">你可以根据需要为每个方法参数提供一个名称使用常规 F # 语法：</span><span class="sxs-lookup"><span data-stu-id="4a16f-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="4a16f-115">在上述`ISprintable`示例中，`Print`方法只有一个参数的类型`string`同名`format`。</span><span class="sxs-lookup"><span data-stu-id="4a16f-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="4a16f-116">有两种方法来实现接口： 通过使用对象表达式以及通过使用类类型。</span><span class="sxs-lookup"><span data-stu-id="4a16f-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="4a16f-117">在任一情况下，类类型或对象表达式提供接口的抽象方法的方法体合并。</span><span class="sxs-lookup"><span data-stu-id="4a16f-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="4a16f-118">实现都是特定于每个实现接口的类型。</span><span class="sxs-lookup"><span data-stu-id="4a16f-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="4a16f-119">因此，对不同类型的接口方法可能彼此不同。</span><span class="sxs-lookup"><span data-stu-id="4a16f-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="4a16f-120">关键字`interface`和`end`，如果你使用轻量语法用于标记的开始和结束的定义，则可选。</span><span class="sxs-lookup"><span data-stu-id="4a16f-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="4a16f-121">如果不使用这些关键字，编译器将尝试推断类型通过分析你使用的构造是否是一个类或接口。</span><span class="sxs-lookup"><span data-stu-id="4a16f-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="4a16f-122">如果你定义成员，或使用其他类的语法，类型将被解释为一个类。</span><span class="sxs-lookup"><span data-stu-id="4a16f-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="4a16f-123">将开始带有大写字母的所有接口的.NET 编码样式的`I`。</span><span class="sxs-lookup"><span data-stu-id="4a16f-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>


## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="4a16f-124">通过使用类类型实现接口</span><span class="sxs-lookup"><span data-stu-id="4a16f-124">Implementing Interfaces by Using Class Types</span></span>
<span data-ttu-id="4a16f-125">你可以通过使用类类型中实现一个或多个接口`interface`关键字，该接口的名称和`with`关键字后, 跟接口成员定义，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="4a16f-125">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="4a16f-126">继承接口实现，因此任何派生的类不需要重新实现它们。</span><span class="sxs-lookup"><span data-stu-id="4a16f-126">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>


## <a name="calling-interface-methods"></a><span data-ttu-id="4a16f-127">调用接口方法</span><span class="sxs-lookup"><span data-stu-id="4a16f-127">Calling Interface Methods</span></span>
<span data-ttu-id="4a16f-128">可以仅通过该接口，不能通过实现接口的类型的任何对象调用接口方法。</span><span class="sxs-lookup"><span data-stu-id="4a16f-128">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="4a16f-129">因此，可能来向上转换的接口类型必须通过使用`:>`运算符或`upcast`以调用这些方法的运算符。</span><span class="sxs-lookup"><span data-stu-id="4a16f-129">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="4a16f-130">若要在具有类型的对象时调用的接口方法`SomeClass`，你必须将向上转换为接口类型的对象，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="4a16f-130">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="4a16f-131">一种替代方法是向上转换的对象上声明一个方法，并调用接口方法，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="4a16f-131">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]
    
## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="4a16f-132">通过使用对象表达式实现接口</span><span class="sxs-lookup"><span data-stu-id="4a16f-132">Implementing Interfaces by Using Object Expressions</span></span>
<span data-ttu-id="4a16f-133">对象表达式提供了一种快捷的方法来实现接口。</span><span class="sxs-lookup"><span data-stu-id="4a16f-133">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="4a16f-134">当不需要创建一个名为的类型，而你只是需要支持的接口方法，而无需任何其他方法的对象，它们非常有用。</span><span class="sxs-lookup"><span data-stu-id="4a16f-134">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="4a16f-135">对象表达式是下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="4a16f-135">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]
    
## <a name="interface-inheritance"></a><span data-ttu-id="4a16f-136">接口继承</span><span class="sxs-lookup"><span data-stu-id="4a16f-136">Interface Inheritance</span></span>
<span data-ttu-id="4a16f-137">接口可从一个或多个基接口继承。</span><span class="sxs-lookup"><span data-stu-id="4a16f-137">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]
    
## <a name="see-also"></a><span data-ttu-id="4a16f-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a16f-138">See Also</span></span>
[<span data-ttu-id="4a16f-139">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="4a16f-139">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="4a16f-140">对象表达式</span><span class="sxs-lookup"><span data-stu-id="4a16f-140">Object Expressions</span></span>](object-expressions.md)

[<span data-ttu-id="4a16f-141">类</span><span class="sxs-lookup"><span data-stu-id="4a16f-141">Classes</span></span>](classes.md)
