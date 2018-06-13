---
title: 继承 (F#)
description: '了解如何指定使用继承关键字的 F # 继承关系。'
ms.date: 05/16/2016
ms.openlocfilehash: 3d0c0785fc595315a8283979b99d0ec4fc5cbc0d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564750"
---
# <a name="inheritance"></a><span data-ttu-id="8e1b6-103">继承</span><span class="sxs-lookup"><span data-stu-id="8e1b6-103">Inheritance</span></span>

<span data-ttu-id="8e1b6-104">继承用于模型"属于"关系，或 subtyping，在面向对象的编程。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-104">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>


## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="8e1b6-105">指定的继承关系</span><span class="sxs-lookup"><span data-stu-id="8e1b6-105">Specifying Inheritance Relationships</span></span>
<span data-ttu-id="8e1b6-106">通过使用指定的继承关系`inherit`类声明中的关键字。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-106">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="8e1b6-107">基本语法形式如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-107">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="8e1b6-108">一个类可以有最多一个直接基类。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-108">A class can have at most one direct base class.</span></span> <span data-ttu-id="8e1b6-109">如果不指定基的类使用`inherit`关键字，类隐式继承自`System.Object`。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-109">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>


## <a name="inherited-members"></a><span data-ttu-id="8e1b6-110">继承的成员</span><span class="sxs-lookup"><span data-stu-id="8e1b6-110">Inherited Members</span></span>
<span data-ttu-id="8e1b6-111">如果某个类继承自另一个类，方法和类的基类的成员可供派生的类的用户就像它们是直接成员的派生类。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-111">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="8e1b6-112">任何 let 绑定和构造函数参数是专用于一个类，因此，不能从派生类访问。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-112">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="8e1b6-113">关键字`base`是可用在派生类中，指的基的类实例。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-113">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="8e1b6-114">它使用类似自我标识符。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-114">It is used like the self-identifier.</span></span>


## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="8e1b6-115">虚方法和替代</span><span class="sxs-lookup"><span data-stu-id="8e1b6-115">Virtual Methods and Overrides</span></span>
<span data-ttu-id="8e1b6-116">虚方法 （和属性） 中的工作方式略有不同 F # 相比其他.NET 语言。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-116">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="8e1b6-117">若要声明新的虚拟成员，你可以使用`abstract`关键字。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-117">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="8e1b6-118">无论是否为提供的默认实现，该方法执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-118">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="8e1b6-119">因此在基类中的虚方法的完整定义遵循以下模式：</span><span class="sxs-lookup"><span data-stu-id="8e1b6-119">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="8e1b6-120">并在派生类中，此虚拟方法的重写遵循以下模式：</span><span class="sxs-lookup"><span data-stu-id="8e1b6-120">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="8e1b6-121">如果省略基类中的默认实现，则基类将成为一个抽象类。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-121">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="8e1b6-122">下面的代码示例说明了新的虚拟方法声明中`function1`基类以及如何在派生类中重写它。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-122">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]
    
## <a name="constructors-and-inheritance"></a><span data-ttu-id="8e1b6-123">构造函数和继承</span><span class="sxs-lookup"><span data-stu-id="8e1b6-123">Constructors and Inheritance</span></span>
<span data-ttu-id="8e1b6-124">必须在派生类中调用基类的构造函数。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-124">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="8e1b6-125">基类构造函数的参数的自变量列表中显示`inherit`子句。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-125">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="8e1b6-126">必须从提供给派生的类构造函数的自变量确定使用的值。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-126">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="8e1b6-127">下面的代码演示基类和派生的类，派生的类继承子句中调用基类构造函数的位置：</span><span class="sxs-lookup"><span data-stu-id="8e1b6-127">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="8e1b6-128">对于多个构造函数，可以使用下面的代码。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-128">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="8e1b6-129">派生的类构造函数的第一行是`inherit`子句和字段显示为声明中的显式字段`val`关键字。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-129">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="8e1b6-130">有关详细信息，请参阅[显式字段：`val`关键字](members/explicit-fields-the-val-keyword.md)。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-130">For more information, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

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

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="8e1b6-131">继承的替代方法</span><span class="sxs-lookup"><span data-stu-id="8e1b6-131">Alternatives to Inheritance</span></span>
<span data-ttu-id="8e1b6-132">在需要修改少量的一种类型时的情况下，请考虑使用对象表达式作为继承的替代方法。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-132">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="8e1b6-133">下面的示例演示如何使用对象表达式作为创建新的派生的类型的替代方法：</span><span class="sxs-lookup"><span data-stu-id="8e1b6-133">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="8e1b6-134">有关对象表达式的详细信息，请参阅[对象表达式](object-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-134">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="8e1b6-135">当你创建的对象层次结构时，请考虑使用而不继承的可区分的联合。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-135">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="8e1b6-136">可区分的联合还可以共享通用的总体类型的不同对象模型不同的行为。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-136">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="8e1b6-137">单个可区分的联合通常可以消除对大量之间差别很小的每个其他的派生类的需要。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-137">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="8e1b6-138">可区分联合有关的信息，请参阅[可区分联合](discriminated-unions.md)。</span><span class="sxs-lookup"><span data-stu-id="8e1b6-138">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="8e1b6-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e1b6-139">See Also</span></span>
[<span data-ttu-id="8e1b6-140">对象表达式</span><span class="sxs-lookup"><span data-stu-id="8e1b6-140">Object Expressions</span></span>](object-expressions.md)

[<span data-ttu-id="8e1b6-141">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="8e1b6-141">F# Language Reference</span></span>](index.md)
