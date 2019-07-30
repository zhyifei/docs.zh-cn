---
title: 接口
description: 了解接口F#如何指定其他类实现的相关成员集。
ms.date: 05/16/2016
ms.openlocfilehash: 8f054a668ad0fbc2453a45883e8052471280eca3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627646"
---
# <a name="interfaces"></a><span data-ttu-id="93def-103">接口</span><span class="sxs-lookup"><span data-stu-id="93def-103">Interfaces</span></span>

<span data-ttu-id="93def-104">*接口*指定其他类实现的一组相关成员。</span><span class="sxs-lookup"><span data-stu-id="93def-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="93def-105">语法</span><span class="sxs-lookup"><span data-stu-id="93def-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="93def-106">备注</span><span class="sxs-lookup"><span data-stu-id="93def-106">Remarks</span></span>

<span data-ttu-id="93def-107">接口声明类似于类声明, 但没有任何成员实现。</span><span class="sxs-lookup"><span data-stu-id="93def-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="93def-108">相反, 所有成员都是抽象的, 如关键字`abstract`所示。</span><span class="sxs-lookup"><span data-stu-id="93def-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="93def-109">您不提供抽象方法的方法体。</span><span class="sxs-lookup"><span data-stu-id="93def-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="93def-110">但是, 还可以提供默认实现, 方法是将成员的单独定义同时包含为方法和`default`关键字。</span><span class="sxs-lookup"><span data-stu-id="93def-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="93def-111">这样做等效于在其他 .NET 语言的基类中创建虚方法。</span><span class="sxs-lookup"><span data-stu-id="93def-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="93def-112">可在实现接口的类中重写此类虚方法。</span><span class="sxs-lookup"><span data-stu-id="93def-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="93def-113">接口的默认可访问性`public`为。</span><span class="sxs-lookup"><span data-stu-id="93def-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="93def-114">您可以根据需要使用常规F#语法为每个方法参数指定名称:</span><span class="sxs-lookup"><span data-stu-id="93def-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="93def-115">在上面`ISprintable`的示例中`Print` , 方法具有名称`format`为的类型`string`的单个参数。</span><span class="sxs-lookup"><span data-stu-id="93def-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="93def-116">可以通过两种方法实现接口: 使用对象表达式和使用类类型。</span><span class="sxs-lookup"><span data-stu-id="93def-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="93def-117">在任一情况下, 类类型或对象表达式都提供接口的抽象方法的方法体。</span><span class="sxs-lookup"><span data-stu-id="93def-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="93def-118">实现特定于实现接口的每个类型。</span><span class="sxs-lookup"><span data-stu-id="93def-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="93def-119">因此, 不同类型的接口方法可能不同。</span><span class="sxs-lookup"><span data-stu-id="93def-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="93def-120">使用轻`interface`量`end`语法时, 用于标记定义的开始和结束的关键字和 (可选) 是可选的。</span><span class="sxs-lookup"><span data-stu-id="93def-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="93def-121">如果不使用这些关键字, 编译器将尝试通过分析你使用的构造来推断该类型是类还是接口。</span><span class="sxs-lookup"><span data-stu-id="93def-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="93def-122">如果定义成员或使用其他类语法, 则会将该类型解释为类。</span><span class="sxs-lookup"><span data-stu-id="93def-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="93def-123">.NET 编码样式是以大写字母`I`开头的所有接口。</span><span class="sxs-lookup"><span data-stu-id="93def-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>

## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="93def-124">使用类类型实现接口</span><span class="sxs-lookup"><span data-stu-id="93def-124">Implementing Interfaces by Using Class Types</span></span>

<span data-ttu-id="93def-125">您可以通过使用`interface`关键字、接口的名称`with`和关键字以及接口成员定义来实现类类型中的一个或多个接口, 如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="93def-125">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="93def-126">接口实现是继承的, 因此任何派生类都不需要重新实现它们。</span><span class="sxs-lookup"><span data-stu-id="93def-126">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>

## <a name="calling-interface-methods"></a><span data-ttu-id="93def-127">调用接口方法</span><span class="sxs-lookup"><span data-stu-id="93def-127">Calling Interface Methods</span></span>

<span data-ttu-id="93def-128">接口方法只能通过接口调用, 而不能通过实现接口的类型的任何对象进行调用。</span><span class="sxs-lookup"><span data-stu-id="93def-128">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="93def-129">因此, 你可能必须通过使用`:>`运算符`upcast`或运算符来向上转换到接口类型, 才能调用这些方法。</span><span class="sxs-lookup"><span data-stu-id="93def-129">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="93def-130">若要在具有类型`SomeClass`为的对象时调用接口方法, 必须将对象向上转换为接口类型, 如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="93def-130">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="93def-131">一种替代方法是在对象上声明一个方法, 该方法向上转换和调用接口方法, 如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="93def-131">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="93def-132">使用对象表达式实现接口</span><span class="sxs-lookup"><span data-stu-id="93def-132">Implementing Interfaces by Using Object Expressions</span></span>

<span data-ttu-id="93def-133">对象表达式提供了一种简单的方法来实现接口。</span><span class="sxs-lookup"><span data-stu-id="93def-133">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="93def-134">当不必创建命名类型并且只需要支持接口方法的对象, 而无需任何其他方法时, 它们非常有用。</span><span class="sxs-lookup"><span data-stu-id="93def-134">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="93def-135">下面的代码演示了对象表达式。</span><span class="sxs-lookup"><span data-stu-id="93def-135">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a><span data-ttu-id="93def-136">接口继承</span><span class="sxs-lookup"><span data-stu-id="93def-136">Interface Inheritance</span></span>

<span data-ttu-id="93def-137">接口可从一个或多个基接口继承。</span><span class="sxs-lookup"><span data-stu-id="93def-137">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a><span data-ttu-id="93def-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="93def-138">See also</span></span>

- [<span data-ttu-id="93def-139">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="93def-139">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="93def-140">对象表达式</span><span class="sxs-lookup"><span data-stu-id="93def-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="93def-141">类</span><span class="sxs-lookup"><span data-stu-id="93def-141">Classes</span></span>](classes.md)
