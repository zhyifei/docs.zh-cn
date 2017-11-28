---
title: "方法 (F#)"
description: "了解如何与用于公开和实现的功能和行为的对象和类型的类型关联的函数的 F # 方法。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1febab3b-c922-49c6-889f-c22db107710c
ms.openlocfilehash: dae31abe6bb0773671b889646c9cceb410a492cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="methods"></a><span data-ttu-id="c7e9e-104">方法</span><span class="sxs-lookup"><span data-stu-id="c7e9e-104">Methods</span></span>

<span data-ttu-id="c7e9e-105">A*方法*是一个函数，则与该类型关联。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-105">A *method* is a function that is associated with a type.</span></span> <span data-ttu-id="c7e9e-106">在面向对象编程中，方法用于公开和实现的功能和行为的对象和类型。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-106">In object-oriented programming, methods are used to expose and implement the functionality and behavior of objects and types.</span></span>


## <a name="syntax"></a><span data-ttu-id="c7e9e-107">语法</span><span class="sxs-lookup"><span data-stu-id="c7e9e-107">Syntax</span></span>

```fsharp
// Instance method definition.
[ attributes ]
member [inline] self-identifier.method-nameparameter-list [ : return-type ]=
    method-body

// Static method definition.
[ attributes ]
static member [inline] method-nameparameter-list [ : return-type ]=
    method-body

// Abstract method declaration or virtual dispatch slot.
[ attributes ]
abstract member self-identifier.method-name : type-signature

// Virtual method declaration and default implementation.
[ attributes ]
abstract member [inline] self-identifier.method-name : type-signature
[ attributes ]
default member [inline] self-identifier.method-nameparameter-list[ : return-type ] =
    method-body

// Override of inherited virtual method.
[ attributes ]
override member [inline] self-identifier.method-nameparameter-list [ : return-type ]=
    method-body

// Optional and DefaultParameterValue attributes on input parameters
[ attributes ]
[ modifier ] member [inline] self-identifier.method-name ([<Optional; DefaultParameterValue([ default-value ])>] input) [ : return-type ]
```

## <a name="remarks"></a><span data-ttu-id="c7e9e-108">备注</span><span class="sxs-lookup"><span data-stu-id="c7e9e-108">Remarks</span></span>
<span data-ttu-id="c7e9e-109">在上述语法中，你可以看到各种形式的方法声明和定义。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-109">In the previous syntax, you can see the various forms of method declarations and definitions.</span></span> <span data-ttu-id="c7e9e-110">在更长的方法体合并等号 （=） 后, 跟换行符和缩进整个方法体。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-110">In longer method bodies, a line break follows the equal sign (=), and the whole method body is indented.</span></span>

<span data-ttu-id="c7e9e-111">特性可以应用于任何方法声明中。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-111">Attributes can be applied to any method declaration.</span></span> <span data-ttu-id="c7e9e-112">它们位于方法定义的语法，并且通常在单独的行上列出。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-112">They precede the syntax for a method definition and are usually listed on a separate line.</span></span> <span data-ttu-id="c7e9e-113">有关更多信息，请参阅[特性](../attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-113">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="c7e9e-114">可以将方法标记为`inline`。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-114">Methods can be marked `inline`.</span></span> <span data-ttu-id="c7e9e-115">有关 `inline` 的信息，请参阅[内联函数](../functions/inline-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-115">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

<span data-ttu-id="c7e9e-116">可以使用以递归方式在类型; 非内联的方法。没有无需显式使用`rec`关键字。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-116">Non-inline methods can be used recursively within the type; there is no need to explicitly use the `rec` keyword.</span></span>


## <a name="instance-methods"></a><span data-ttu-id="c7e9e-117">实例方法</span><span class="sxs-lookup"><span data-stu-id="c7e9e-117">Instance Methods</span></span>
<span data-ttu-id="c7e9e-118">实例方法声明与`member`关键字和*自我标识符*后, 跟一个句点 （.） 的方法名称和参数。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-118">Instance methods are declared with the `member` keyword and a *self-identifier*, followed by a period (.) and the method name and parameters.</span></span> <span data-ttu-id="c7e9e-119">这种情况原样`let`绑定，*参数列表*可以是一种模式。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-119">As is the case for `let` bindings, the *parameter-list* can be a pattern.</span></span> <span data-ttu-id="c7e9e-120">通常情况下，你括在圆括号中元组形式，即方式方法的参数出现的方法 F # 创建在其他.NET Framework 语言时。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-120">Typically, you enclose method parameters in parentheses in a tuple form, which is the way methods appear in F# when they are created in other .NET Framework languages.</span></span> <span data-ttu-id="c7e9e-121">但是，扩充窗体 （由空格分隔参数） 也很常见，并且还支持其他模式。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-121">However, the curried form (parameters separated by spaces) is also common, and other patterns are supported also.</span></span>

<span data-ttu-id="c7e9e-122">下面的示例阐释的定义和使用非抽象实例方法。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-122">The following example illustrates the definition and use of a non-abstract instance method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

<span data-ttu-id="c7e9e-123">实例方法内不要到由使用 let 的绑定定义的访问字段使用自我标识符。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-123">Within instance methods, do not use the self identifier to access fields defined by using let bindings.</span></span> <span data-ttu-id="c7e9e-124">访问其他成员和属性时，请使用自我标识符。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-124">Use the self identifier when accessing other members and properties.</span></span>


## <a name="static-methods"></a><span data-ttu-id="c7e9e-125">静态方法</span><span class="sxs-lookup"><span data-stu-id="c7e9e-125">Static Methods</span></span>
<span data-ttu-id="c7e9e-126">关键字`static`可用于指定一种方法，可以调用实例情况下并不是与对象实例相关联。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-126">The keyword `static` is used to specify that a method can be called without an instance and is not associated with an object instance.</span></span> <span data-ttu-id="c7e9e-127">否则，方法是实例方法。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-127">Otherwise, methods are instance methods.</span></span>

<span data-ttu-id="c7e9e-128">下一节中的示例演示使用声明的字段`let`关键字，使用声明的属性成员`member`关键字，然后使用声明的静态方法`static`关键字。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-128">The example in the next section shows fields declared with the `let` keyword, property members declared with the `member` keyword, and a static method declared with the `static` keyword.</span></span>

<span data-ttu-id="c7e9e-129">下面的示例阐释的定义和使用静态方法。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-129">The following example illustrates the definition and use of static methods.</span></span> <span data-ttu-id="c7e9e-130">假定这些方法定义中`SomeType`上一节中的类。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-130">Assume that these method definitions are in the `SomeType` class in the previous section.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="c7e9e-131">抽象方法和虚方法</span><span class="sxs-lookup"><span data-stu-id="c7e9e-131">Abstract and Virtual Methods</span></span>
<span data-ttu-id="c7e9e-132">关键字`abstract`表示一种方法是具有虚拟调度槽，可能没有一个定义的类中。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-132">The keyword `abstract` indicates that a method has a virtual dispatch slot and might not have a definition in the class.</span></span> <span data-ttu-id="c7e9e-133">A*虚拟调度槽*是面向对象的类型中的调用在运行时中用于查找虚函数的函数的内部维护表中的条目。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-133">A *virtual dispatch slot* is an entry in an internally maintained table of functions that is used at run time to look up virtual function calls in an object-oriented type.</span></span> <span data-ttu-id="c7e9e-134">虚拟调度机制是实现的机制*多态性*，面向对象的编程的一个重要功能。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-134">The virtual dispatch mechanism is the mechanism that implements *polymorphism*, an important feature of object-oriented programming.</span></span> <span data-ttu-id="c7e9e-135">具有至少一个抽象方法没有定义的类是*抽象类*，这意味着该类的情况下，可以创建任何实例。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-135">A class that has at least one abstract method without a definition is an *abstract class*, which means that no instances can be created of that class.</span></span> <span data-ttu-id="c7e9e-136">有关抽象类的详细信息，请参阅[抽象类](../abstract-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-136">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

<span data-ttu-id="c7e9e-137">抽象方法声明不包含方法体。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-137">Abstract method declarations do not include a method body.</span></span> <span data-ttu-id="c7e9e-138">相反，该方法的名称后跟一个冒号 （:） 和方法的类型签名。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-138">Instead, the name of the method is followed by a colon (:) and a type signature for the method.</span></span> <span data-ttu-id="c7e9e-139">一种方法的类型签名是所示 intellisense，当你将鼠标指针悬停方法名称在 Visual Studio 代码编辑器中，除不使用参数名称相同。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-139">The type signature of a method is the same as that shown by IntelliSense when you pause the mouse pointer over a method name in the Visual Studio Code Editor, except without parameter names.</span></span> <span data-ttu-id="c7e9e-140">当您正在以交互方式，解释器，fsi.exe，也会显示类型签名。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-140">Type signatures are also displayed by the interpreter, fsi.exe, when you are working interactively.</span></span> <span data-ttu-id="c7e9e-141">方法的类型签名格式则为 out 参数，返回类型，使用适当的分隔符符号后跟类型的列表。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-141">The type signature of a method is formed by listing out the types of the parameters, followed by the return type, with appropriate separator symbols.</span></span> <span data-ttu-id="c7e9e-142">扩充的参数由分隔`->`元组参数隔开`*`。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-142">Curried parameters are separated by `->` and tuple parameters are separated by `*`.</span></span> <span data-ttu-id="c7e9e-143">返回值始终从由自变量分隔`->`符号。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-143">The return value is always separated from the arguments by a `->` symbol.</span></span> <span data-ttu-id="c7e9e-144">可以使用括号，组复杂的参数，如当一种函数类型是一个参数，或者以指示当元组将被视为单个参数，而不是两个参数。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-144">Parentheses can be used to group complex parameters, such as when a function type is a parameter, or to indicate when a tuple is treated as a single parameter rather than as two parameters.</span></span>

<span data-ttu-id="c7e9e-145">此外可以为抽象方法默认定义通过向类添加定义和使用`default`关键字，如本主题中的语法块中所示。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-145">You can also give abstract methods default definitions by adding the definition to the class and using the `default` keyword, as shown in the syntax block in this topic.</span></span> <span data-ttu-id="c7e9e-146">具有同一类中定义一个抽象方法相当于其他.NET Framework 语言中的虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-146">An abstract method that has a definition in the same class is equivalent to a virtual method in other .NET Framework languages.</span></span> <span data-ttu-id="c7e9e-147">定义是否存在，`abstract`关键字虚函数表类中创建一个新的调度槽。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-147">Whether or not a definition exists, the `abstract` keyword creates a new dispatch slot in the virtual function table for the class.</span></span>

<span data-ttu-id="c7e9e-148">无论是否基类实现其抽象方法，派生的类可以提供抽象方法的实现。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-148">Regardless of whether a base class implements its abstract methods, derived classes can provide implementations of abstract methods.</span></span> <span data-ttu-id="c7e9e-149">若要实现派生类中的一个抽象方法，定义一个方法在派生类中，除使用具有相同名称和签名`override`或`default`关键字，并提供方法体。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-149">To implement an abstract method in a derived class, define a method that has the same name and signature in the derived class, except use the `override` or `default` keyword, and provide the method body.</span></span> <span data-ttu-id="c7e9e-150">关键字`override`和`default`意味着完全相同的目标。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-150">The keywords `override` and `default` mean exactly the same thing.</span></span> <span data-ttu-id="c7e9e-151">使用`override`的新方法重写的基类实现; 如果使用`default`当你创建与原始的抽象声明相同的类中实现。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-151">Use `override` if the new method overrides a base class implementation; use `default` when you create an implementation in the same class as the original abstract declaration.</span></span> <span data-ttu-id="c7e9e-152">不要使用`abstract`实现抽象基类中声明的方法的方法上关键字。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-152">Do not use the `abstract` keyword on the method that implements the method that was declared abstract in the base class.</span></span>

<span data-ttu-id="c7e9e-153">下面的示例演示一个抽象方法`Rotate`、 具有默认实现，.NET Framework 虚方法的等效项。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-153">The following example illustrates an abstract method `Rotate` that has a default implementation, the equivalent of a .NET Framework virtual method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

<span data-ttu-id="c7e9e-154">下面的示例阐释派生的类重写基类方法。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-154">The following example illustrates a derived class that overrides a base class method.</span></span> <span data-ttu-id="c7e9e-155">在这种情况下，重写更改行为，以便该方法不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-155">In this case, the override changes the behavior so that the method does nothing.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a><span data-ttu-id="c7e9e-156">重载方法</span><span class="sxs-lookup"><span data-stu-id="c7e9e-156">Overloaded Methods</span></span>
<span data-ttu-id="c7e9e-157">重载的方法是在给定类型中具有相同名称但具有不同的自变量的方法。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-157">Overloaded methods are methods that have identical names in a given type but that have different arguments.</span></span> <span data-ttu-id="c7e9e-158">在 F # 中，可选自变量通常使用而不是重载方法。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-158">In F#, optional arguments are usually used instead of overloaded methods.</span></span> <span data-ttu-id="c7e9e-159">但是，重载的方法允许在语言中，自变量中的元组形式，不是扩充形式。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-159">However, overloaded methods are permitted in the language, provided that the arguments are in tuple form, not curried form.</span></span>

## <a name="optional-arguments"></a><span data-ttu-id="c7e9e-160">可选实参</span><span class="sxs-lookup"><span data-stu-id="c7e9e-160">Optional Arguments</span></span>

<span data-ttu-id="c7e9e-161">F # 4.1 开始，你还可以使用默认参数值的可选自变量在方法中。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-161">Starting with F# 4.1, you can also have optional arguments with a default parameter value in methods.</span></span>  <span data-ttu-id="c7e9e-162">这是为了帮助实现包含 C# 代码间的互操作。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-162">This is to help facilitate interoperation with C# code.</span></span>  <span data-ttu-id="c7e9e-163">下面的示例演示的语法：</span><span class="sxs-lookup"><span data-stu-id="c7e9e-163">The following example demonstrates the syntax:</span></span>

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

<span data-ttu-id="c7e9e-164">请注意，传递的值时为`DefaultParameterValue`必须匹配的输入的类型。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-164">Note that the value passed in for `DefaultParameterValue` must match the input type.</span></span>  <span data-ttu-id="c7e9e-165">在上面的示例中，它是`int`。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-165">In the above sample, it is an `int`.</span></span>  <span data-ttu-id="c7e9e-166">尝试传递非整数值转换为`DefaultParameterValue`将导致编译错误。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-166">Attempting to pass a non-integer value into `DefaultParameterValue` would result in a compile error.</span></span>

## <a name="example-properties-and-methods"></a><span data-ttu-id="c7e9e-167">示例： 属性和方法</span><span class="sxs-lookup"><span data-stu-id="c7e9e-167">Example: Properties and Methods</span></span>
<span data-ttu-id="c7e9e-168">下面的示例包含具有字段、 私有函数、 属性和静态方法的示例的类型。</span><span class="sxs-lookup"><span data-stu-id="c7e9e-168">The following example contains a type that has examples of fields, private functions, properties, and a static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a><span data-ttu-id="c7e9e-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7e9e-169">See Also</span></span>
[<span data-ttu-id="c7e9e-170">成员</span><span class="sxs-lookup"><span data-stu-id="c7e9e-170">Members</span></span>](index.md)
