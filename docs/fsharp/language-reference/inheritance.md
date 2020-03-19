---
title: 继承
description: 了解如何使用"继承"关键字指定 F# 继承关系。
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401129"
---
# <a name="inheritance"></a><span data-ttu-id="a08b1-103">继承</span><span class="sxs-lookup"><span data-stu-id="a08b1-103">Inheritance</span></span>

<span data-ttu-id="a08b1-104">继承用于在面向对象的编程中对"is-a"关系或子类型化建模。</span><span class="sxs-lookup"><span data-stu-id="a08b1-104">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>

## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="a08b1-105">指定继承关系</span><span class="sxs-lookup"><span data-stu-id="a08b1-105">Specifying Inheritance Relationships</span></span>

<span data-ttu-id="a08b1-106">通过在类声明中使用 关键字`inherit`指定继承关系。</span><span class="sxs-lookup"><span data-stu-id="a08b1-106">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="a08b1-107">基本语法形式如下例所示。</span><span class="sxs-lookup"><span data-stu-id="a08b1-107">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="a08b1-108">类最多只能有一个直接基类。</span><span class="sxs-lookup"><span data-stu-id="a08b1-108">A class can have at most one direct base class.</span></span> <span data-ttu-id="a08b1-109">如果不使用`inherit`关键字指定基类，则类隐式继承从`System.Object`。</span><span class="sxs-lookup"><span data-stu-id="a08b1-109">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>

## <a name="inherited-members"></a><span data-ttu-id="a08b1-110">继承成员</span><span class="sxs-lookup"><span data-stu-id="a08b1-110">Inherited Members</span></span>

<span data-ttu-id="a08b1-111">如果类从其他类继承，则派生类的用户可以使用基类的方法和成员，就像它们是派生类的直接成员一样。</span><span class="sxs-lookup"><span data-stu-id="a08b1-111">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="a08b1-112">任何 let 绑定和构造函数参数都是类的私有参数，因此无法从派生类访问。</span><span class="sxs-lookup"><span data-stu-id="a08b1-112">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="a08b1-113">关键字`base`在派生类中可用，并引用基类实例。</span><span class="sxs-lookup"><span data-stu-id="a08b1-113">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="a08b1-114">它像自标识符一样使用。</span><span class="sxs-lookup"><span data-stu-id="a08b1-114">It is used like the self-identifier.</span></span>

## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="a08b1-115">虚拟方法和重写</span><span class="sxs-lookup"><span data-stu-id="a08b1-115">Virtual Methods and Overrides</span></span>

<span data-ttu-id="a08b1-116">与其他 .NET 语言相比，虚拟方法（和属性）在 F# 中的工作方式略有不同。</span><span class="sxs-lookup"><span data-stu-id="a08b1-116">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="a08b1-117">要声明新的虚拟成员，请使用 关键字`abstract`。</span><span class="sxs-lookup"><span data-stu-id="a08b1-117">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="a08b1-118">无论是否为该方法提供默认实现，都可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a08b1-118">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="a08b1-119">因此，基类中虚拟方法的完整定义遵循此模式：</span><span class="sxs-lookup"><span data-stu-id="a08b1-119">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="a08b1-120">在派生类中，此虚拟方法的重写遵循此模式：</span><span class="sxs-lookup"><span data-stu-id="a08b1-120">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="a08b1-121">如果在基类中省略默认实现，则基类将成为抽象类。</span><span class="sxs-lookup"><span data-stu-id="a08b1-121">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="a08b1-122">以下代码示例演示了基类中新虚拟方法`function1`的声明以及如何在派生类中重写它。</span><span class="sxs-lookup"><span data-stu-id="a08b1-122">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a><span data-ttu-id="a08b1-123">构造函数和继承</span><span class="sxs-lookup"><span data-stu-id="a08b1-123">Constructors and Inheritance</span></span>

<span data-ttu-id="a08b1-124">基类的构造函数必须在派生类中调用。</span><span class="sxs-lookup"><span data-stu-id="a08b1-124">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="a08b1-125">基类构造函数的参数出现在`inherit`子句中的参数列表中。</span><span class="sxs-lookup"><span data-stu-id="a08b1-125">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="a08b1-126">使用的值必须根据提供给派生类构造函数的参数确定。</span><span class="sxs-lookup"><span data-stu-id="a08b1-126">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="a08b1-127">以下代码显示基类和派生类，其中派生类调用继承子句中的基类构造函数：</span><span class="sxs-lookup"><span data-stu-id="a08b1-127">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="a08b1-128">在多个构造函数的情况下，可以使用以下代码。</span><span class="sxs-lookup"><span data-stu-id="a08b1-128">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="a08b1-129">派生类构造函数的第一行是`inherit`子句，字段显示为使用 关键字声明的`val`显式字段。</span><span class="sxs-lookup"><span data-stu-id="a08b1-129">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="a08b1-130">有关详细信息，请参阅[显式字段：`val`关键字](./members/explicit-fields-the-val-keyword.md)。</span><span class="sxs-lookup"><span data-stu-id="a08b1-130">For more information, see [Explicit Fields: The `val` Keyword](./members/explicit-fields-the-val-keyword.md).</span></span>

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

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="a08b1-131">继承的替代方法</span><span class="sxs-lookup"><span data-stu-id="a08b1-131">Alternatives to Inheritance</span></span>

<span data-ttu-id="a08b1-132">如果需要对类型进行细微修改，请考虑使用对象表达式作为继承的替代方法。</span><span class="sxs-lookup"><span data-stu-id="a08b1-132">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="a08b1-133">以下示例说明了使用对象表达式作为创建新派生类型的替代方法：</span><span class="sxs-lookup"><span data-stu-id="a08b1-133">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="a08b1-134">有关对象表达式的详细信息，请参阅[对象表达式](object-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="a08b1-134">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="a08b1-135">创建对象层次结构时，请考虑使用受歧视的联合而不是继承。</span><span class="sxs-lookup"><span data-stu-id="a08b1-135">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="a08b1-136">受歧视的联合还可以对共享公共整体类型的不同对象的不同行为建模。</span><span class="sxs-lookup"><span data-stu-id="a08b1-136">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="a08b1-137">单个受歧视的联合通常可以消除对一些派生类的需求，这些类彼此的微小变化。</span><span class="sxs-lookup"><span data-stu-id="a08b1-137">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="a08b1-138">有关受歧视工会的信息，请参阅[歧视工会](discriminated-unions.md)。</span><span class="sxs-lookup"><span data-stu-id="a08b1-138">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a08b1-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a08b1-139">See also</span></span>

- [<span data-ttu-id="a08b1-140">对象表达式</span><span class="sxs-lookup"><span data-stu-id="a08b1-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="a08b1-141">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="a08b1-141">F# Language Reference</span></span>](index.md)
