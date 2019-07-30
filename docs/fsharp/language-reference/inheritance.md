---
title: 继承
description: 了解如何使用 " F# inherit" 关键字指定继承关系。
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627663"
---
# <a name="inheritance"></a><span data-ttu-id="f25fd-103">继承</span><span class="sxs-lookup"><span data-stu-id="f25fd-103">Inheritance</span></span>

<span data-ttu-id="f25fd-104">在面向对象的编程中, 使用继承来为 "is a" 关系或子类型化建模。</span><span class="sxs-lookup"><span data-stu-id="f25fd-104">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>

## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="f25fd-105">指定继承关系</span><span class="sxs-lookup"><span data-stu-id="f25fd-105">Specifying Inheritance Relationships</span></span>

<span data-ttu-id="f25fd-106">在类声明中使用`inherit`关键字指定继承关系。</span><span class="sxs-lookup"><span data-stu-id="f25fd-106">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="f25fd-107">下面的示例演示了基本语法形式。</span><span class="sxs-lookup"><span data-stu-id="f25fd-107">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="f25fd-108">一个类最多只能有一个直接基类。</span><span class="sxs-lookup"><span data-stu-id="f25fd-108">A class can have at most one direct base class.</span></span> <span data-ttu-id="f25fd-109">如果未使用`inherit`关键字指定基类, 则该类将隐式继承自`System.Object`。</span><span class="sxs-lookup"><span data-stu-id="f25fd-109">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>

## <a name="inherited-members"></a><span data-ttu-id="f25fd-110">继承成员</span><span class="sxs-lookup"><span data-stu-id="f25fd-110">Inherited Members</span></span>

<span data-ttu-id="f25fd-111">如果某个类继承自另一个类, 则派生类的用户可以使用基类的方法和成员, 就像它们是派生类的直接成员。</span><span class="sxs-lookup"><span data-stu-id="f25fd-111">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="f25fd-112">任何 let 绑定和构造函数参数都是类的专用, 因此无法从派生类访问。</span><span class="sxs-lookup"><span data-stu-id="f25fd-112">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="f25fd-113">关键字`base`可用于派生类, 引用基类实例。</span><span class="sxs-lookup"><span data-stu-id="f25fd-113">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="f25fd-114">它与自标识符一样使用。</span><span class="sxs-lookup"><span data-stu-id="f25fd-114">It is used like the self-identifier.</span></span>

## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="f25fd-115">虚方法和重写</span><span class="sxs-lookup"><span data-stu-id="f25fd-115">Virtual Methods and Overrides</span></span>

<span data-ttu-id="f25fd-116">与其他 .NET 语言相比, 虚方法 (和F#属性) 在中的工作方式有些不同。</span><span class="sxs-lookup"><span data-stu-id="f25fd-116">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="f25fd-117">若要声明新的虚拟成员, 请使用`abstract`关键字。</span><span class="sxs-lookup"><span data-stu-id="f25fd-117">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="f25fd-118">不管是否为该方法提供默认实现, 都可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="f25fd-118">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="f25fd-119">因此, 基类中的虚方法的完整定义遵循此模式:</span><span class="sxs-lookup"><span data-stu-id="f25fd-119">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="f25fd-120">在派生类中, 此虚方法的重写遵循此模式:</span><span class="sxs-lookup"><span data-stu-id="f25fd-120">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="f25fd-121">如果在基类中省略默认实现, 则基类成为抽象类。</span><span class="sxs-lookup"><span data-stu-id="f25fd-121">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="f25fd-122">下面的代码示例演示了基类中新虚方法`function1`的声明, 以及如何在派生类中重写它。</span><span class="sxs-lookup"><span data-stu-id="f25fd-122">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a><span data-ttu-id="f25fd-123">构造函数和继承</span><span class="sxs-lookup"><span data-stu-id="f25fd-123">Constructors and Inheritance</span></span>

<span data-ttu-id="f25fd-124">必须在派生类中调用基类的构造函数。</span><span class="sxs-lookup"><span data-stu-id="f25fd-124">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="f25fd-125">基类构造函数的自变量出现在`inherit`子句中的参数列表中。</span><span class="sxs-lookup"><span data-stu-id="f25fd-125">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="f25fd-126">必须从提供给派生类构造函数的参数确定所使用的值。</span><span class="sxs-lookup"><span data-stu-id="f25fd-126">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="f25fd-127">下面的代码演示基类和派生类, 其中派生的类在 inherit 子句中调用基类构造函数:</span><span class="sxs-lookup"><span data-stu-id="f25fd-127">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="f25fd-128">对于多个构造函数, 可以使用以下代码。</span><span class="sxs-lookup"><span data-stu-id="f25fd-128">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="f25fd-129">派生类构造函数的第一行是`inherit`子句, 字段显示为`val`用关键字声明的显式字段。</span><span class="sxs-lookup"><span data-stu-id="f25fd-129">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="f25fd-130">有关详细信息, 请[参阅显式字段:`val`关键字。](./members/explicit-fields-the-val-keyword.md)</span><span class="sxs-lookup"><span data-stu-id="f25fd-130">For more information, see [Explicit Fields: The `val` Keyword](./members/explicit-fields-the-val-keyword.md).</span></span>

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

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="f25fd-131">继承的替代方法</span><span class="sxs-lookup"><span data-stu-id="f25fd-131">Alternatives to Inheritance</span></span>

<span data-ttu-id="f25fd-132">如果需要对类型进行次要修改, 请考虑使用对象表达式作为继承的替代方法。</span><span class="sxs-lookup"><span data-stu-id="f25fd-132">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="f25fd-133">下面的示例演示了如何使用对象表达式来创建新的派生类型:</span><span class="sxs-lookup"><span data-stu-id="f25fd-133">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="f25fd-134">有关对象表达式的详细信息, 请参阅[对象表达式](object-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="f25fd-134">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="f25fd-135">创建对象层次结构时, 请考虑使用可区分联合, 而不是继承。</span><span class="sxs-lookup"><span data-stu-id="f25fd-135">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="f25fd-136">可区分联合还可以为共享公共总体类型的不同对象建模各种行为。</span><span class="sxs-lookup"><span data-stu-id="f25fd-136">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="f25fd-137">单个的可区分联合通常可以避免需要多个派生类, 这些派生类是彼此之间的细微差异。</span><span class="sxs-lookup"><span data-stu-id="f25fd-137">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="f25fd-138">有关可区分联合的信息, 请参阅可[区分联合](discriminated-unions.md)。</span><span class="sxs-lookup"><span data-stu-id="f25fd-138">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f25fd-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="f25fd-139">See also</span></span>

- [<span data-ttu-id="f25fd-140">对象表达式</span><span class="sxs-lookup"><span data-stu-id="f25fd-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="f25fd-141">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="f25fd-141">F# Language Reference</span></span>](index.md)
