---
title: 构造函数 (F#)
description: '了解如何定义和使用在 F # 中的构造函数来创建和初始化类和结构对象。'
ms.date: 05/16/2016
ms.openlocfilehash: ff2463f890034cce0bbaa85d9a5c93e50427cd03
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45508429"
---
# <a name="constructors"></a><span data-ttu-id="c4b6e-103">构造函数</span><span class="sxs-lookup"><span data-stu-id="c4b6e-103">Constructors</span></span>

<span data-ttu-id="c4b6e-104">本主题介绍如何定义和使用构造函数来创建和初始化类和结构的对象。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-104">This topic describes how to define and use constructors to create and initialize class and structure objects.</span></span>

## <a name="construction-of-class-objects"></a><span data-ttu-id="c4b6e-105">类对象的构造</span><span class="sxs-lookup"><span data-stu-id="c4b6e-105">Construction of Class Objects</span></span>

<span data-ttu-id="c4b6e-106">类类型的对象具有构造函数。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-106">Objects of class types have constructors.</span></span> <span data-ttu-id="c4b6e-107">有两种类型的构造函数。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-107">There are two kinds of constructors.</span></span> <span data-ttu-id="c4b6e-108">一个是主构造函数，其参数的类型名称之后出现在括号内。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-108">One is the primary constructor, whose parameters appear in parentheses just after the type name.</span></span> <span data-ttu-id="c4b6e-109">使用指定另一个可选的附加构造函数`new`关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-109">You specify other, optional additional constructors by using the `new` keyword.</span></span> <span data-ttu-id="c4b6e-110">任何此类其他构造函数必须调用主构造函数。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-110">Any such additional constructors must call the primary constructor.</span></span>

<span data-ttu-id="c4b6e-111">主构造函数包含`let`和`do`类定义开头显示的绑定。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-111">The primary constructor contains `let` and `do` bindings that appear at the start of the class definition.</span></span> <span data-ttu-id="c4b6e-112">一个`let`绑定声明的私有字段和方法的类;`do`绑定执行代码。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-112">A `let` binding declares private fields and methods of the class; a `do` binding executes code.</span></span> <span data-ttu-id="c4b6e-113">有关详细信息`let`绑定中类构造函数，请参阅[`let`类中的绑定](let-bindings-in-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-113">For more information about `let` bindings in class constructors, see [`let` Bindings in Classes](let-bindings-in-classes.md).</span></span> <span data-ttu-id="c4b6e-114">有关详细信息`do`绑定中的构造函数，请参阅[`do`类中的绑定](do-bindings-in-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-114">For more information about `do` bindings in constructors, see [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

<span data-ttu-id="c4b6e-115">无论你想要调用的构造函数是主构造函数或另一个构造函数，可以通过使用创建对象`new`表达式，带或不带可选`new`关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-115">Regardless of whether the constructor you want to call is a primary constructor or an additional constructor, you can create objects by using a `new` expression, with or without the optional `new` keyword.</span></span> <span data-ttu-id="c4b6e-116">您初始化您的对象以及构造函数参数，通过列出顺序中的自变量和通过以逗号分隔并括在括号中，或通过在括号中使用命名的参数和值。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-116">You initialize your objects together with constructor arguments, either by listing the arguments in order and separated by commas and enclosed in parentheses, or by using named arguments and values in parentheses.</span></span> <span data-ttu-id="c4b6e-117">您还可以设置属性的对象上的对象的构造期间使用的属性名称并分配值，就像您使用名为构造函数自变量。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-117">You can also set properties on an object during the construction of the object by using the property names and assigning values just as you use named constructor arguments.</span></span>

<span data-ttu-id="c4b6e-118">以下代码演示了具有一个构造函数和创建对象的各种方法的类。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-118">The following code illustrates a class that has a constructor and various ways of creating objects.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

<span data-ttu-id="c4b6e-119">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-119">The output is as follows.</span></span>

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a><span data-ttu-id="c4b6e-120">构造的结构</span><span class="sxs-lookup"><span data-stu-id="c4b6e-120">Construction of Structures</span></span>

<span data-ttu-id="c4b6e-121">结构按照类的所有规则。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-121">Structures follow all the rules of classes.</span></span> <span data-ttu-id="c4b6e-122">因此，可以具有主构造函数，并可以使用来提供其他构造函数`new`。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-122">Therefore, you can have a primary constructor, and you can provide additional constructors by using `new`.</span></span> <span data-ttu-id="c4b6e-123">但是，没有结构和类之间的一个重要区别： 结构可以具有默认构造函数 （即，一个不带任何参数），即使没有主构造函数定义。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-123">However, there is one important difference between structures and classes: structures can have a default constructor (that is, one with no arguments) even if no primary constructor is defined.</span></span> <span data-ttu-id="c4b6e-124">默认构造函数初始化为默认值为该类型，通常为零或其等效的所有字段。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-124">The default constructor initializes all the fields to the default value for that type, usually zero or its equivalent.</span></span> <span data-ttu-id="c4b6e-125">为结构定义任何构造函数必须具有至少一个参数，以便使用默认构造函数不冲突。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-125">Any constructors that you define for structures must have at least one argument so that they do not conflict with the default constructor.</span></span>

<span data-ttu-id="c4b6e-126">此外，结构通常具有通过使用创建的字段`val`关键字; 类还可以具有这些字段。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-126">Also, structures often have fields that are created by using the `val` keyword; classes can also have these fields.</span></span> <span data-ttu-id="c4b6e-127">结构和类具有使用定义的字段的`val`关键字可以也在中初始化其他构造函数通过使用记录表达式，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-127">Structures and classes that have fields defined by using the `val` keyword can also be initialized in additional constructors by using record expressions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

<span data-ttu-id="c4b6e-128">有关详细信息，请参阅[显式字段：`val`关键字](explicit-fields-the-val-keyword.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-128">For more information, see [Explicit Fields: The `val` Keyword](explicit-fields-the-val-keyword.md).</span></span>

## <a name="executing-side-effects-in-constructors"></a><span data-ttu-id="c4b6e-129">在构造函数中执行的负面影响</span><span class="sxs-lookup"><span data-stu-id="c4b6e-129">Executing Side Effects in Constructors</span></span>

<span data-ttu-id="c4b6e-130">在类中的主构造函数可以执行中的代码`do`绑定。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-130">A primary constructor in a class can execute code in a `do` binding.</span></span> <span data-ttu-id="c4b6e-131">但是，如果您需要在另一个构造函数，而不执行代码`do`绑定？</span><span class="sxs-lookup"><span data-stu-id="c4b6e-131">However, what if you have to execute code in an additional constructor, without a `do` binding?</span></span> <span data-ttu-id="c4b6e-132">若要执行此操作，应使用`then`关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-132">To do this, you use the `then` keyword.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

<span data-ttu-id="c4b6e-133">主构造函数的副作用仍能执行。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-133">The side effects of the primary constructor still execute.</span></span> <span data-ttu-id="c4b6e-134">因此，输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-134">Therefore, the output is as follows.</span></span>

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a><span data-ttu-id="c4b6e-135">在构造函数中的自我标识符</span><span class="sxs-lookup"><span data-stu-id="c4b6e-135">Self Identifiers in Constructors</span></span>

<span data-ttu-id="c4b6e-136">在其他成员提供每个成员的定义中的当前对象的名称。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-136">In other members, you provide a name for the current object in the definition of each member.</span></span> <span data-ttu-id="c4b6e-137">此外可以将自我标识符的类定义的第一行上使用`as`紧跟构造函数参数的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-137">You can also put the self identifier on the first line of the class definition by using the `as` keyword immediately following the constructor parameters.</span></span> <span data-ttu-id="c4b6e-138">下面的示例说明了此语法。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-138">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

<span data-ttu-id="c4b6e-139">在其他构造函数，您还可以定义自我标识符放`as`子句之后的构造函数参数。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-139">In additional constructors, you can also define a self identifier by putting the `as` clause right after the constructor parameters.</span></span> <span data-ttu-id="c4b6e-140">下面的示例说明了此语法。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-140">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

<span data-ttu-id="c4b6e-141">尝试之前已完全定义使用一个对象，则会出现问题。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-141">Problems can occur when you try to use an object before it is fully defined.</span></span> <span data-ttu-id="c4b6e-142">因此，使用自我标识符会导致编译器发出警告并插入其他检查，以确保该对象初始化之前不会访问对象的成员。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-142">Therefore, uses of the self identifier can cause the compiler to emit a warning and insert additional checks to ensure the members of an object are not accessed before the object is initialized.</span></span> <span data-ttu-id="c4b6e-143">只应使用中的自我标识符`do`绑定的主构造函数，或之后`then`其他构造函数中的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-143">You should only use the self identifier in the `do` bindings of the primary constructor, or after the `then` keyword in additional constructors.</span></span>

<span data-ttu-id="c4b6e-144">自我标识符的名称不一定要`this`。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-144">The name of the self identifier does not have to be `this`.</span></span> <span data-ttu-id="c4b6e-145">它可以是任何有效的标识符。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-145">It can be any valid identifier.</span></span>

## <a name="assigning-values-to-properties-at-initialization"></a><span data-ttu-id="c4b6e-146">将值分配给在初始化的属性</span><span class="sxs-lookup"><span data-stu-id="c4b6e-146">Assigning Values to Properties at Initialization</span></span>

<span data-ttu-id="c4b6e-147">可以通过追加格式的赋值的列表中的初始化代码的类对象的属性分配值`property = value`到一个构造函数的参数列表。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-147">You can assign values to the properties of a class object in the initialization code by appending a list of assignments of the form `property = value` to the argument list for a constructor.</span></span> <span data-ttu-id="c4b6e-148">下面的代码示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-148">This is shown in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="c4b6e-149">前面的代码中的以下版本说明了普通自变量、 可选参数和一个构造函数调用中的属性设置的组合。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-149">The following version of the previous code illustrates the combination of ordinary arguments, optional arguments, and property settings in one constructor call.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]

## <a name="constructors-in-inherited-class"></a><span data-ttu-id="c4b6e-150">中继承的类的构造函数</span><span class="sxs-lookup"><span data-stu-id="c4b6e-150">Constructors in inherited class</span></span>

<span data-ttu-id="c4b6e-151">从具有一个构造函数的基类继承时，必须在继承子句中指定其自变量。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-151">When inheriting from a base class that has a constructor, you must specify its arguments in the inherit clause.</span></span> <span data-ttu-id="c4b6e-152">有关详细信息，请参阅[构造函数和继承](../inheritance.md#constructors-and-inheritance)。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-152">For more information, see [Constructors and inheritance](../inheritance.md#constructors-and-inheritance).</span></span>

## <a name="static-constructors-or-type-constructors"></a><span data-ttu-id="c4b6e-153">静态构造函数或类型构造函数</span><span class="sxs-lookup"><span data-stu-id="c4b6e-153">Static Constructors or Type Constructors</span></span>

<span data-ttu-id="c4b6e-154">除了指定代码用于创建对象，静态`let`和`do`绑定可以在执行之前首先使用的类型来执行初始化在类型级别的类类型中编写。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-154">In addition to specifying code for creating objects, static `let` and `do` bindings can be authored in class types that execute before the type is first used to perform initialization at the type level.</span></span> <span data-ttu-id="c4b6e-155">有关详细信息，请参阅[`let`类中的绑定](let-bindings-in-classes.md)并[`do`类中的绑定](do-bindings-in-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b6e-155">For more information, see [`let` Bindings in Classes](let-bindings-in-classes.md) and [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c4b6e-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4b6e-156">See also</span></span>

- [<span data-ttu-id="c4b6e-157">成员</span><span class="sxs-lookup"><span data-stu-id="c4b6e-157">Members</span></span>](index.md)
