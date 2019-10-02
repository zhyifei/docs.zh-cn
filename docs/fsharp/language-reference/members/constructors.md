---
title: 构造函数
description: 了解如何在中F#定义和使用构造函数来创建和初始化类和结构对象。
ms.date: 05/16/2016
ms.openlocfilehash: 6769ec7fc6768090d8ae68e21946a58829b6eea0
ms.sourcegitcommit: 878ca7550b653114c3968ef8906da2b3e60e3c7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736850"
---
# <a name="constructors"></a><span data-ttu-id="1d94e-103">构造函数</span><span class="sxs-lookup"><span data-stu-id="1d94e-103">Constructors</span></span>

<span data-ttu-id="1d94e-104">本文介绍如何定义和使用构造函数来创建和初始化类和结构对象。</span><span class="sxs-lookup"><span data-stu-id="1d94e-104">This article describes how to define and use constructors to create and initialize class and structure objects.</span></span>

## <a name="construction-of-class-objects"></a><span data-ttu-id="1d94e-105">类对象的构造</span><span class="sxs-lookup"><span data-stu-id="1d94e-105">Construction of class objects</span></span>

<span data-ttu-id="1d94e-106">类类型的对象具有构造函数。</span><span class="sxs-lookup"><span data-stu-id="1d94e-106">Objects of class types have constructors.</span></span> <span data-ttu-id="1d94e-107">有两种类型的构造函数。</span><span class="sxs-lookup"><span data-stu-id="1d94e-107">There are two kinds of constructors.</span></span> <span data-ttu-id="1d94e-108">一个是主构造函数, 其参数出现在括号中紧跟在类型名称后的括号中。</span><span class="sxs-lookup"><span data-stu-id="1d94e-108">One is the primary constructor, whose parameters appear in parentheses just after the type name.</span></span> <span data-ttu-id="1d94e-109">使用`new`关键字指定其他可选的其他构造函数。</span><span class="sxs-lookup"><span data-stu-id="1d94e-109">You specify other, optional additional constructors by using the `new` keyword.</span></span> <span data-ttu-id="1d94e-110">任何此类附加构造函数都必须调用主构造函数。</span><span class="sxs-lookup"><span data-stu-id="1d94e-110">Any such additional constructors must call the primary constructor.</span></span>

<span data-ttu-id="1d94e-111">主构造函数包含`let`和`do`绑定, 它们显示在类定义的开头。</span><span class="sxs-lookup"><span data-stu-id="1d94e-111">The primary constructor contains `let` and `do` bindings that appear at the start of the class definition.</span></span> <span data-ttu-id="1d94e-112">绑定声明类的私有字段和方法`do` ; 绑定执行代码。 `let`</span><span class="sxs-lookup"><span data-stu-id="1d94e-112">A `let` binding declares private fields and methods of the class; a `do` binding executes code.</span></span> <span data-ttu-id="1d94e-113">有关类构造函数`let`中的绑定的详细信息, 请参阅[ `let`类中的绑定](let-bindings-in-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="1d94e-113">For more information about `let` bindings in class constructors, see [`let` Bindings in Classes](let-bindings-in-classes.md).</span></span> <span data-ttu-id="1d94e-114">有关构造函数中`do`的绑定的详细信息, 请参阅[ `do`类中的绑定](do-bindings-in-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="1d94e-114">For more information about `do` bindings in constructors, see [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

<span data-ttu-id="1d94e-115">无论你要调用的构造函数是主构造函数还是附加构造函数, 都可以通过使用`new`带有或不带可选`new`关键字的表达式来创建对象。</span><span class="sxs-lookup"><span data-stu-id="1d94e-115">Regardless of whether the constructor you want to call is a primary constructor or an additional constructor, you can create objects by using a `new` expression, with or without the optional `new` keyword.</span></span> <span data-ttu-id="1d94e-116">您可以将对象与构造函数参数一起初始化, 方法是按顺序列出参数, 并以逗号分隔并括在括号中, 或者通过使用括号中的命名参数和值。</span><span class="sxs-lookup"><span data-stu-id="1d94e-116">You initialize your objects together with constructor arguments, either by listing the arguments in order and separated by commas and enclosed in parentheses, or by using named arguments and values in parentheses.</span></span> <span data-ttu-id="1d94e-117">您还可以通过使用属性名称和赋值来设置对象的属性, 就像使用命名构造函数参数一样。</span><span class="sxs-lookup"><span data-stu-id="1d94e-117">You can also set properties on an object during the construction of the object by using the property names and assigning values just as you use named constructor arguments.</span></span>

<span data-ttu-id="1d94e-118">下面的代码演示一个类，该类具有构造函数和用于创建对象的各种方式：</span><span class="sxs-lookup"><span data-stu-id="1d94e-118">The following code illustrates a class that has a constructor and various ways of creating objects:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

<span data-ttu-id="1d94e-119">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="1d94e-119">The output is as follows:</span></span>

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a><span data-ttu-id="1d94e-120">结构的构造</span><span class="sxs-lookup"><span data-stu-id="1d94e-120">Construction of structures</span></span>

<span data-ttu-id="1d94e-121">结构遵循类的所有规则。</span><span class="sxs-lookup"><span data-stu-id="1d94e-121">Structures follow all the rules of classes.</span></span> <span data-ttu-id="1d94e-122">因此, 您可以有一个主构造函数, 并且可以通过使用`new`提供其他构造函数。</span><span class="sxs-lookup"><span data-stu-id="1d94e-122">Therefore, you can have a primary constructor, and you can provide additional constructors by using `new`.</span></span> <span data-ttu-id="1d94e-123">但结构和类之间存在一个重要的区别: 结构可以有一个无参数的构造函数 (即, 没有参数的构造函数), 即使未定义主构造函数也是如此。</span><span class="sxs-lookup"><span data-stu-id="1d94e-123">However, there is one important difference between structures and classes: structures can have a parameterless constructor (that is, one with no arguments) even if no primary constructor is defined.</span></span> <span data-ttu-id="1d94e-124">无参数构造函数将所有字段初始化为该类型的默认值, 通常为零或其等效的值。</span><span class="sxs-lookup"><span data-stu-id="1d94e-124">The parameterless constructor initializes all the fields to the default value for that type, usually zero or its equivalent.</span></span> <span data-ttu-id="1d94e-125">为结构定义的任何构造函数都必须具有至少一个参数，使其不会与无参数构造函数发生冲突。</span><span class="sxs-lookup"><span data-stu-id="1d94e-125">Any constructors that you define for structures must have at least one argument so that they do not conflict with the parameterless constructor.</span></span>

<span data-ttu-id="1d94e-126">此外, 结构通常包含使用`val`关键字创建的字段; 类也可以包含这些字段。</span><span class="sxs-lookup"><span data-stu-id="1d94e-126">Also, structures often have fields that are created by using the `val` keyword; classes can also have these fields.</span></span> <span data-ttu-id="1d94e-127">具有使用`val`关键字定义的字段的结构和类也可以通过使用记录表达式在其他构造函数中进行初始化, 如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="1d94e-127">Structures and classes that have fields defined by using the `val` keyword can also be initialized in additional constructors by using record expressions, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

<span data-ttu-id="1d94e-128">有关详细信息, 请[参阅显式字段:`val`关键字。](explicit-fields-the-val-keyword.md)</span><span class="sxs-lookup"><span data-stu-id="1d94e-128">For more information, see [Explicit Fields: The `val` Keyword](explicit-fields-the-val-keyword.md).</span></span>

## <a name="executing-side-effects-in-constructors"></a><span data-ttu-id="1d94e-129">在构造函数中执行副作用</span><span class="sxs-lookup"><span data-stu-id="1d94e-129">Executing side effects in constructors</span></span>

<span data-ttu-id="1d94e-130">类中的主构造函数可执行`do`绑定中的代码。</span><span class="sxs-lookup"><span data-stu-id="1d94e-130">A primary constructor in a class can execute code in a `do` binding.</span></span> <span data-ttu-id="1d94e-131">但是, 如果必须在没有绑定的`do`情况下在其他构造函数中执行代码怎么办？</span><span class="sxs-lookup"><span data-stu-id="1d94e-131">However, what if you have to execute code in an additional constructor, without a `do` binding?</span></span> <span data-ttu-id="1d94e-132">为此, 请使用`then`关键字。</span><span class="sxs-lookup"><span data-stu-id="1d94e-132">To do this, you use the `then` keyword.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

<span data-ttu-id="1d94e-133">主构造函数的副作用仍在执行。</span><span class="sxs-lookup"><span data-stu-id="1d94e-133">The side effects of the primary constructor still execute.</span></span> <span data-ttu-id="1d94e-134">因此，输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="1d94e-134">Therefore, the output is as follows:</span></span>

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a><span data-ttu-id="1d94e-135">构造函数中的自我标识符</span><span class="sxs-lookup"><span data-stu-id="1d94e-135">Self identifiers in constructors</span></span>

<span data-ttu-id="1d94e-136">在其他成员中, 您可以在每个成员的定义中提供当前对象的名称。</span><span class="sxs-lookup"><span data-stu-id="1d94e-136">In other members, you provide a name for the current object in the definition of each member.</span></span> <span data-ttu-id="1d94e-137">你还可以使用`as`紧跟构造函数参数的关键字, 将自标识符置于类定义的第一行。</span><span class="sxs-lookup"><span data-stu-id="1d94e-137">You can also put the self identifier on the first line of the class definition by using the `as` keyword immediately following the constructor parameters.</span></span> <span data-ttu-id="1d94e-138">下面的示例演示了此语法。</span><span class="sxs-lookup"><span data-stu-id="1d94e-138">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

<span data-ttu-id="1d94e-139">在其他构造函数中, 还可以通过将`as`子句置于构造函数参数之后来定义自定义标识符。</span><span class="sxs-lookup"><span data-stu-id="1d94e-139">In additional constructors, you can also define a self identifier by putting the `as` clause right after the constructor parameters.</span></span> <span data-ttu-id="1d94e-140">下面的示例演示了此语法：</span><span class="sxs-lookup"><span data-stu-id="1d94e-140">The following example illustrates this syntax:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

<span data-ttu-id="1d94e-141">当你尝试在完全定义对象之前使用对象时, 可能会出现问题。</span><span class="sxs-lookup"><span data-stu-id="1d94e-141">Problems can occur when you try to use an object before it is fully defined.</span></span> <span data-ttu-id="1d94e-142">因此, 使用 self 标识符可能导致编译器发出警告并插入其他检查, 以确保在初始化对象之前不会访问对象的成员。</span><span class="sxs-lookup"><span data-stu-id="1d94e-142">Therefore, uses of the self identifier can cause the compiler to emit a warning and insert additional checks to ensure the members of an object are not accessed before the object is initialized.</span></span> <span data-ttu-id="1d94e-143">只应在主构造函数的`do`绑定中使用自标识符, 或在其他构造函数的`then`关键字之后使用。</span><span class="sxs-lookup"><span data-stu-id="1d94e-143">You should only use the self identifier in the `do` bindings of the primary constructor, or after the `then` keyword in additional constructors.</span></span>

<span data-ttu-id="1d94e-144">自身标识符的名称不必是`this`。</span><span class="sxs-lookup"><span data-stu-id="1d94e-144">The name of the self identifier does not have to be `this`.</span></span> <span data-ttu-id="1d94e-145">它可以是任何有效的标识符。</span><span class="sxs-lookup"><span data-stu-id="1d94e-145">It can be any valid identifier.</span></span>

## <a name="assigning-values-to-properties-at-initialization"></a><span data-ttu-id="1d94e-146">在初始化时将值分配给属性</span><span class="sxs-lookup"><span data-stu-id="1d94e-146">Assigning values to properties at initialization</span></span>

<span data-ttu-id="1d94e-147">您可以通过将窗体`property = value`赋值的列表追加到构造函数的参数列表, 将值分配给初始化代码中类对象的属性。</span><span class="sxs-lookup"><span data-stu-id="1d94e-147">You can assign values to the properties of a class object in the initialization code by appending a list of assignments of the form `property = value` to the argument list for a constructor.</span></span> <span data-ttu-id="1d94e-148">下面的代码示例对此进行了演示：</span><span class="sxs-lookup"><span data-stu-id="1d94e-148">This is shown in the following code example:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="1d94e-149">以下版本的前面的代码演示了一个构造函数调用中的普通参数、可选参数和属性设置的组合：</span><span class="sxs-lookup"><span data-stu-id="1d94e-149">The following version of the previous code illustrates the combination of ordinary arguments, optional arguments, and property settings in one constructor call:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]

## <a name="constructors-in-inherited-class"></a><span data-ttu-id="1d94e-150">继承类中的构造函数</span><span class="sxs-lookup"><span data-stu-id="1d94e-150">Constructors in inherited class</span></span>

<span data-ttu-id="1d94e-151">从具有构造函数的基类继承时, 必须在 inherit 子句中指定其参数。</span><span class="sxs-lookup"><span data-stu-id="1d94e-151">When inheriting from a base class that has a constructor, you must specify its arguments in the inherit clause.</span></span> <span data-ttu-id="1d94e-152">有关详细信息, 请参阅[构造函数和继承](../inheritance.md#constructors-and-inheritance)。</span><span class="sxs-lookup"><span data-stu-id="1d94e-152">For more information, see [Constructors and inheritance](../inheritance.md#constructors-and-inheritance).</span></span>

## <a name="static-constructors-or-type-constructors"></a><span data-ttu-id="1d94e-153">静态构造函数或类型构造函数</span><span class="sxs-lookup"><span data-stu-id="1d94e-153">Static constructors or type constructors</span></span>

<span data-ttu-id="1d94e-154">除了指定用于创建对象的代码以外, 还`let`可以`do`在类类型中创作静态和绑定, 该类型首先用于在类型级别执行初始化。</span><span class="sxs-lookup"><span data-stu-id="1d94e-154">In addition to specifying code for creating objects, static `let` and `do` bindings can be authored in class types that execute before the type is first used to perform initialization at the type level.</span></span> <span data-ttu-id="1d94e-155">有关详细信息, 请[ `let` ](let-bindings-in-classes.md)参阅类中的绑定和[ `do`类中的绑定](do-bindings-in-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="1d94e-155">For more information, see [`let` Bindings in Classes](let-bindings-in-classes.md) and [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1d94e-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="1d94e-156">See also</span></span>

- [<span data-ttu-id="1d94e-157">成员</span><span class="sxs-lookup"><span data-stu-id="1d94e-157">Members</span></span>](index.md)
