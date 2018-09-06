---
title: 继承 (F#)
description: '了解如何指定 F # 继承关系，使用继承关键字。'
ms.date: 05/16/2016
ms.openlocfilehash: e4d79244fb9bada5db0c5c4c7179d4bfe6e21f3d
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864464"
---
# <a name="inheritance"></a><span data-ttu-id="8290d-103">继承</span><span class="sxs-lookup"><span data-stu-id="8290d-103">Inheritance</span></span>

<span data-ttu-id="8290d-104">使用继承进行建模"是 a"关系或子类型化，在面向对象的编程。</span><span class="sxs-lookup"><span data-stu-id="8290d-104">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>

## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="8290d-105">指定继承关系</span><span class="sxs-lookup"><span data-stu-id="8290d-105">Specifying Inheritance Relationships</span></span>

<span data-ttu-id="8290d-106">使用指定继承关系`inherit`类声明中的关键字。</span><span class="sxs-lookup"><span data-stu-id="8290d-106">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="8290d-107">基本语法形式如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="8290d-107">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="8290d-108">一个类可以有最多一个直接基类。</span><span class="sxs-lookup"><span data-stu-id="8290d-108">A class can have at most one direct base class.</span></span> <span data-ttu-id="8290d-109">如果不执行操作通过使用指定的基类`inherit`类的关键字，隐式继承自`System.Object`。</span><span class="sxs-lookup"><span data-stu-id="8290d-109">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>

## <a name="inherited-members"></a><span data-ttu-id="8290d-110">继承的成员</span><span class="sxs-lookup"><span data-stu-id="8290d-110">Inherited Members</span></span>

<span data-ttu-id="8290d-111">如果一个类继承自另一个类，则方法和类的基类的成员可供派生类的用户就像直接成员的派生类。</span><span class="sxs-lookup"><span data-stu-id="8290d-111">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="8290d-112">任何的 let 绑定和构造函数参数是专用于一个类，因此，不能从派生类访问。</span><span class="sxs-lookup"><span data-stu-id="8290d-112">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="8290d-113">关键字`base`可在派生类中，并且引用的基的类实例。</span><span class="sxs-lookup"><span data-stu-id="8290d-113">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="8290d-114">它被当做自我标识符。</span><span class="sxs-lookup"><span data-stu-id="8290d-114">It is used like the self-identifier.</span></span>

## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="8290d-115">虚方法和重写</span><span class="sxs-lookup"><span data-stu-id="8290d-115">Virtual Methods and Overrides</span></span>

<span data-ttu-id="8290d-116">虚方法 （和属性） 工作方式略有不同 F # 中与其他.NET 语言相比。</span><span class="sxs-lookup"><span data-stu-id="8290d-116">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="8290d-117">若要声明新的虚拟成员，请使用`abstract`关键字。</span><span class="sxs-lookup"><span data-stu-id="8290d-117">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="8290d-118">无论您是否提供的默认实现，该方法执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8290d-118">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="8290d-119">因此在基类中虚方法的完整定义采用这种模式：</span><span class="sxs-lookup"><span data-stu-id="8290d-119">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="8290d-120">和此虚拟方法的重写派生类中采用这种模式：</span><span class="sxs-lookup"><span data-stu-id="8290d-120">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="8290d-121">如果省略基类中的默认实现，基类将成为一个抽象类。</span><span class="sxs-lookup"><span data-stu-id="8290d-121">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="8290d-122">下面的代码示例说明了新的虚拟方法的声明`function1`基类以及如何在派生类中重写它。</span><span class="sxs-lookup"><span data-stu-id="8290d-122">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a><span data-ttu-id="8290d-123">构造函数和继承</span><span class="sxs-lookup"><span data-stu-id="8290d-123">Constructors and Inheritance</span></span>

<span data-ttu-id="8290d-124">必须在派生类中调用基类构造函数。</span><span class="sxs-lookup"><span data-stu-id="8290d-124">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="8290d-125">基类构造函数的参数的参数列表中显示`inherit`子句。</span><span class="sxs-lookup"><span data-stu-id="8290d-125">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="8290d-126">必须从提供给派生的类构造函数的参数确定所使用的值。</span><span class="sxs-lookup"><span data-stu-id="8290d-126">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="8290d-127">下面的代码显示了基类和派生的类中，其中派生的类调用基类构造函数中的继承子句：</span><span class="sxs-lookup"><span data-stu-id="8290d-127">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="8290d-128">在多个构造函数的情况下可以使用下面的代码。</span><span class="sxs-lookup"><span data-stu-id="8290d-128">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="8290d-129">在派生的类构造函数的第一行是`inherit`子句中，和字段显示为与声明的显式字段`val`关键字。</span><span class="sxs-lookup"><span data-stu-id="8290d-129">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="8290d-130">有关详细信息，请参阅[显式字段：`val`关键字](members/explicit-fields-the-val-keyword.md)。</span><span class="sxs-lookup"><span data-stu-id="8290d-130">For more information, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

```fsharp
type BaseClass =
    val string1 : string
    new (str) = { string1 = str }
    new () = { string1 = "" }

type DerivedClass =
    inherit BaseClass

    val string2 : string
    new (str1, str2) = { inherit BaseClass(str1); string2 = str2 }
    new (str2) = { inherit BaseClass(); string2 = str2 }

let obj1 = DerivedClass("A", "B")
let obj2 = DerivedClass("A")
```

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="8290d-131">继承的替代方法</span><span class="sxs-lookup"><span data-stu-id="8290d-131">Alternatives to Inheritance</span></span>

<span data-ttu-id="8290d-132">在需要稍作修改的一种类型的情况下，请考虑使用对象表达式作为继承的替代方法。</span><span class="sxs-lookup"><span data-stu-id="8290d-132">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="8290d-133">下面的示例演示如何使用对象表达式来创建新的派生的类型的替代方法：</span><span class="sxs-lookup"><span data-stu-id="8290d-133">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="8290d-134">对象表达式的详细信息，请参阅[对象表达式](object-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="8290d-134">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="8290d-135">当你创建的对象层次结构时，请考虑使用而不继承的可区分的联合。</span><span class="sxs-lookup"><span data-stu-id="8290d-135">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="8290d-136">可区分的联合还可以共享通用的整体类型的不同对象的模型不同的行为。</span><span class="sxs-lookup"><span data-stu-id="8290d-136">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="8290d-137">单个可区分的联合通常无需多个次要变体的每个其他派生类。</span><span class="sxs-lookup"><span data-stu-id="8290d-137">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="8290d-138">有关可区分联合的信息，请参阅[可区分联合](discriminated-unions.md)。</span><span class="sxs-lookup"><span data-stu-id="8290d-138">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8290d-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="8290d-139">See also</span></span>

- [<span data-ttu-id="8290d-140">对象表达式</span><span class="sxs-lookup"><span data-stu-id="8290d-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="8290d-141">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="8290d-141">F# Language Reference</span></span>](index.md)
