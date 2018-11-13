---
title: 方法 (F#)
description: 了解如何与用于公开和实现的功能和行为的对象和类型的类型相关联的函数的 F# 方法。
ms.date: 05/16/2016
ms.openlocfilehash: 02d5a7d22d1ce79a06e15462637c373b33623f61
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "44253203"
---
# <a name="methods"></a><span data-ttu-id="2935c-103">方法</span><span class="sxs-lookup"><span data-stu-id="2935c-103">Methods</span></span>

<span data-ttu-id="2935c-104">一个*方法*是与类型相关联的函数。</span><span class="sxs-lookup"><span data-stu-id="2935c-104">A *method* is a function that is associated with a type.</span></span> <span data-ttu-id="2935c-105">在面向对象的编程中，使用方法来公开和实现的功能和行为的对象和类型。</span><span class="sxs-lookup"><span data-stu-id="2935c-105">In object-oriented programming, methods are used to expose and implement the functionality and behavior of objects and types.</span></span>

## <a name="syntax"></a><span data-ttu-id="2935c-106">语法</span><span class="sxs-lookup"><span data-stu-id="2935c-106">Syntax</span></span>

```fsharp
// Instance method definition.
[ attributes ]
member [inline] self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Static method definition.
[ attributes ]
static member [inline] method-name parameter-list [ : return-type ] =
    method-body

// Abstract method declaration or virtual dispatch slot.
[ attributes ]
abstract member method-name : type-signature

// Virtual method declaration and default implementation.
[ attributes ]
abstract member method-name : type-signature
[ attributes ]
default self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Override of inherited virtual method.
[ attributes ]
override self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Optional and DefaultParameterValue attributes on input parameters
[ attributes ]
[ modifier ] member [inline] self-identifier.method-name ([<Optional; DefaultParameterValue( default-value )>] input) [ : return-type ]
```

## <a name="remarks"></a><span data-ttu-id="2935c-107">备注</span><span class="sxs-lookup"><span data-stu-id="2935c-107">Remarks</span></span>

<span data-ttu-id="2935c-108">在上述语法中，可以看到各种形式的方法声明和定义。</span><span class="sxs-lookup"><span data-stu-id="2935c-108">In the previous syntax, you can see the various forms of method declarations and definitions.</span></span> <span data-ttu-id="2935c-109">在较长的方法体，等号 （=） 后, 跟换行符和缩进整个方法主体。</span><span class="sxs-lookup"><span data-stu-id="2935c-109">In longer method bodies, a line break follows the equal sign (=), and the whole method body is indented.</span></span>

<span data-ttu-id="2935c-110">特性可以应用于任何方法声明。</span><span class="sxs-lookup"><span data-stu-id="2935c-110">Attributes can be applied to any method declaration.</span></span> <span data-ttu-id="2935c-111">它们位于方法定义的语法，并且通常列在单独的行。</span><span class="sxs-lookup"><span data-stu-id="2935c-111">They precede the syntax for a method definition and are usually listed on a separate line.</span></span> <span data-ttu-id="2935c-112">有关更多信息，请参阅[特性](../attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="2935c-112">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="2935c-113">可以将方法标记为`inline`。</span><span class="sxs-lookup"><span data-stu-id="2935c-113">Methods can be marked `inline`.</span></span> <span data-ttu-id="2935c-114">有关 `inline` 的信息，请参阅[内联函数](../functions/inline-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="2935c-114">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

<span data-ttu-id="2935c-115">可以在类型; 中的递归使用的非内联的方法。无需显式使用`rec`关键字。</span><span class="sxs-lookup"><span data-stu-id="2935c-115">Non-inline methods can be used recursively within the type; there is no need to explicitly use the `rec` keyword.</span></span>

## <a name="instance-methods"></a><span data-ttu-id="2935c-116">实例方法</span><span class="sxs-lookup"><span data-stu-id="2935c-116">Instance Methods</span></span>

<span data-ttu-id="2935c-117">实例方法声明具有`member`关键字和一个*自我标识符*后, 跟一个句点 （.） 的方法名称和参数。</span><span class="sxs-lookup"><span data-stu-id="2935c-117">Instance methods are declared with the `member` keyword and a *self-identifier*, followed by a period (.) and the method name and parameters.</span></span> <span data-ttu-id="2935c-118">对于这种情况`let`绑定，*参数列表*可以是一种模式。</span><span class="sxs-lookup"><span data-stu-id="2935c-118">As is the case for `let` bindings, the *parameter-list* can be a pattern.</span></span> <span data-ttu-id="2935c-119">通常情况下，则将的方法参数括在圆括号中元组形式，这是方法方法出现在 F# 时在其他.NET Framework 语言中创建。</span><span class="sxs-lookup"><span data-stu-id="2935c-119">Typically, you enclose method parameters in parentheses in a tuple form, which is the way methods appear in F# when they are created in other .NET Framework languages.</span></span> <span data-ttu-id="2935c-120">但是，扩充的形式 （用空格分隔的参数） 也很常见，并且还支持其他模式。</span><span class="sxs-lookup"><span data-stu-id="2935c-120">However, the curried form (parameters separated by spaces) is also common, and other patterns are supported also.</span></span>

<span data-ttu-id="2935c-121">下面的示例演示定义和使用非抽象实例方法。</span><span class="sxs-lookup"><span data-stu-id="2935c-121">The following example illustrates the definition and use of a non-abstract instance method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

<span data-ttu-id="2935c-122">在实例方法中，不要使用 let 的绑定定义的访问权限字段使用自我标识符。</span><span class="sxs-lookup"><span data-stu-id="2935c-122">Within instance methods, do not use the self identifier to access fields defined by using let bindings.</span></span> <span data-ttu-id="2935c-123">访问其他成员和属性时，请使用自我标识符。</span><span class="sxs-lookup"><span data-stu-id="2935c-123">Use the self identifier when accessing other members and properties.</span></span>

## <a name="static-methods"></a><span data-ttu-id="2935c-124">静态方法</span><span class="sxs-lookup"><span data-stu-id="2935c-124">Static Methods</span></span>

<span data-ttu-id="2935c-125">关键字`static`用于指定可以没有实例调用的方法，并且不相关联的对象实例。</span><span class="sxs-lookup"><span data-stu-id="2935c-125">The keyword `static` is used to specify that a method can be called without an instance and is not associated with an object instance.</span></span> <span data-ttu-id="2935c-126">否则，方法是实例方法。</span><span class="sxs-lookup"><span data-stu-id="2935c-126">Otherwise, methods are instance methods.</span></span>

<span data-ttu-id="2935c-127">下一节中的示例显示了使用声明的字段`let`关键字，使用声明的属性成员`member`关键字，并且使用声明的静态方法`static`关键字。</span><span class="sxs-lookup"><span data-stu-id="2935c-127">The example in the next section shows fields declared with the `let` keyword, property members declared with the `member` keyword, and a static method declared with the `static` keyword.</span></span>

<span data-ttu-id="2935c-128">下面的示例演示定义和使用静态方法。</span><span class="sxs-lookup"><span data-stu-id="2935c-128">The following example illustrates the definition and use of static methods.</span></span> <span data-ttu-id="2935c-129">假定这些方法定义中`SomeType`上一节中的类。</span><span class="sxs-lookup"><span data-stu-id="2935c-129">Assume that these method definitions are in the `SomeType` class in the previous section.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="2935c-130">抽象方法和虚方法</span><span class="sxs-lookup"><span data-stu-id="2935c-130">Abstract and Virtual Methods</span></span>

<span data-ttu-id="2935c-131">关键字`abstract`指示一种方法都有一个虚拟调度和可能不具有在类中定义。</span><span class="sxs-lookup"><span data-stu-id="2935c-131">The keyword `abstract` indicates that a method has a virtual dispatch slot and might not have a definition in the class.</span></span> <span data-ttu-id="2935c-132">一个*虚拟调度槽*是面向对象的类型中的调用在运行时中用于查找虚函数在内部维护函数的表中的条目。</span><span class="sxs-lookup"><span data-stu-id="2935c-132">A *virtual dispatch slot* is an entry in an internally maintained table of functions that is used at run time to look up virtual function calls in an object-oriented type.</span></span> <span data-ttu-id="2935c-133">虚拟调度机制是实现的机制*多态性*，面向对象的编程的一个重要功能。</span><span class="sxs-lookup"><span data-stu-id="2935c-133">The virtual dispatch mechanism is the mechanism that implements *polymorphism*, an important feature of object-oriented programming.</span></span> <span data-ttu-id="2935c-134">具有至少一个抽象方法没有定义的类是*抽象类*，这意味着该类的可以创建任何实例。</span><span class="sxs-lookup"><span data-stu-id="2935c-134">A class that has at least one abstract method without a definition is an *abstract class*, which means that no instances can be created of that class.</span></span> <span data-ttu-id="2935c-135">有关抽象类的详细信息，请参阅[抽象类](../abstract-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="2935c-135">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

<span data-ttu-id="2935c-136">抽象方法声明不包括方法体。</span><span class="sxs-lookup"><span data-stu-id="2935c-136">Abstract method declarations do not include a method body.</span></span> <span data-ttu-id="2935c-137">相反，该方法的名称后跟一个冒号 （:） 和方法的类型签名。</span><span class="sxs-lookup"><span data-stu-id="2935c-137">Instead, the name of the method is followed by a colon (:) and a type signature for the method.</span></span> <span data-ttu-id="2935c-138">一种方法的类型签名是您将鼠标指针悬停通过方法名称在 Visual Studio 代码编辑器中，除而无需参数名称时，intellisense 所示相同的。</span><span class="sxs-lookup"><span data-stu-id="2935c-138">The type signature of a method is the same as that shown by IntelliSense when you pause the mouse pointer over a method name in the Visual Studio Code Editor, except without parameter names.</span></span> <span data-ttu-id="2935c-139">当您正在以交互方式，解释器，fsi.exe，也会显示类型签名。</span><span class="sxs-lookup"><span data-stu-id="2935c-139">Type signatures are also displayed by the interpreter, fsi.exe, when you are working interactively.</span></span> <span data-ttu-id="2935c-140">Out 参数后, 跟具有相应的分隔符的返回类型的类型的列表格式是一种方法的类型签名。</span><span class="sxs-lookup"><span data-stu-id="2935c-140">The type signature of a method is formed by listing out the types of the parameters, followed by the return type, with appropriate separator symbols.</span></span> <span data-ttu-id="2935c-141">扩充的参数由分隔`->`分隔元组参数`*`。</span><span class="sxs-lookup"><span data-stu-id="2935c-141">Curried parameters are separated by `->` and tuple parameters are separated by `*`.</span></span> <span data-ttu-id="2935c-142">返回值始终与通过参数分隔开来`->`符号。</span><span class="sxs-lookup"><span data-stu-id="2935c-142">The return value is always separated from the arguments by a `->` symbol.</span></span> <span data-ttu-id="2935c-143">可以使用括号，到组复杂的参数，例如，当函数类型是一个参数，或者用于指示当元组被视为单个参数而不是两个参数。</span><span class="sxs-lookup"><span data-stu-id="2935c-143">Parentheses can be used to group complex parameters, such as when a function type is a parameter, or to indicate when a tuple is treated as a single parameter rather than as two parameters.</span></span>

<span data-ttu-id="2935c-144">你还可以允许抽象方法默认定义通过添加到类定义并使用`default`关键字，如本主题中的语法块中所示。</span><span class="sxs-lookup"><span data-stu-id="2935c-144">You can also give abstract methods default definitions by adding the definition to the class and using the `default` keyword, as shown in the syntax block in this topic.</span></span> <span data-ttu-id="2935c-145">同一类中都有一个定义一个抽象方法相当于其他.NET Framework 语言中的虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="2935c-145">An abstract method that has a definition in the same class is equivalent to a virtual method in other .NET Framework languages.</span></span> <span data-ttu-id="2935c-146">是否存在的定义，`abstract`关键字在类的虚函数表中创建一个新的调度槽。</span><span class="sxs-lookup"><span data-stu-id="2935c-146">Whether or not a definition exists, the `abstract` keyword creates a new dispatch slot in the virtual function table for the class.</span></span>

<span data-ttu-id="2935c-147">无论是否基类实现其抽象方法，派生的类可以提供抽象方法的实现。</span><span class="sxs-lookup"><span data-stu-id="2935c-147">Regardless of whether a base class implements its abstract methods, derived classes can provide implementations of abstract methods.</span></span> <span data-ttu-id="2935c-148">若要在派生类中实现一个抽象方法，定义在派生类中，除使用具有相同名称和签名的方法`override`或`default`关键字，并提供方法体。</span><span class="sxs-lookup"><span data-stu-id="2935c-148">To implement an abstract method in a derived class, define a method that has the same name and signature in the derived class, except use the `override` or `default` keyword, and provide the method body.</span></span> <span data-ttu-id="2935c-149">关键字`override`和`default`意味着完全相同的目标。</span><span class="sxs-lookup"><span data-stu-id="2935c-149">The keywords `override` and `default` mean exactly the same thing.</span></span> <span data-ttu-id="2935c-150">使用`override`的新方法重写基类实现; 如果使用`default`时您创建与原始的抽象声明相同的类中实现。</span><span class="sxs-lookup"><span data-stu-id="2935c-150">Use `override` if the new method overrides a base class implementation; use `default` when you create an implementation in the same class as the original abstract declaration.</span></span> <span data-ttu-id="2935c-151">不要使用`abstract`关键字上实现抽象基类中声明的方法的方法。</span><span class="sxs-lookup"><span data-stu-id="2935c-151">Do not use the `abstract` keyword on the method that implements the method that was declared abstract in the base class.</span></span>

<span data-ttu-id="2935c-152">下面的示例演示一个抽象方法`Rotate`，其默认实现，.NET Framework 的虚方法的等效项。</span><span class="sxs-lookup"><span data-stu-id="2935c-152">The following example illustrates an abstract method `Rotate` that has a default implementation, the equivalent of a .NET Framework virtual method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

<span data-ttu-id="2935c-153">下面的示例演示一个重写基类方法的派生的类。</span><span class="sxs-lookup"><span data-stu-id="2935c-153">The following example illustrates a derived class that overrides a base class method.</span></span> <span data-ttu-id="2935c-154">在这种情况下，重写更改的行为，以便该方法不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="2935c-154">In this case, the override changes the behavior so that the method does nothing.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a><span data-ttu-id="2935c-155">重载方法</span><span class="sxs-lookup"><span data-stu-id="2935c-155">Overloaded Methods</span></span>

<span data-ttu-id="2935c-156">重载的方法是在给定类型中具有相同名称但具有不同参数的方法。</span><span class="sxs-lookup"><span data-stu-id="2935c-156">Overloaded methods are methods that have identical names in a given type but that have different arguments.</span></span> <span data-ttu-id="2935c-157">在 F# 中，而不是重载方法通常用于可选参数。</span><span class="sxs-lookup"><span data-stu-id="2935c-157">In F#, optional arguments are usually used instead of overloaded methods.</span></span> <span data-ttu-id="2935c-158">但是，重载的方法允许在语言中，参数是在元组形式中，不是扩充形式。</span><span class="sxs-lookup"><span data-stu-id="2935c-158">However, overloaded methods are permitted in the language, provided that the arguments are in tuple form, not curried form.</span></span>

## <a name="optional-arguments"></a><span data-ttu-id="2935c-159">可选实参</span><span class="sxs-lookup"><span data-stu-id="2935c-159">Optional Arguments</span></span>

<span data-ttu-id="2935c-160">从 F# 4.1 开始，你还可以使用默认参数值的可选参数在方法中。</span><span class="sxs-lookup"><span data-stu-id="2935c-160">Starting with F# 4.1, you can also have optional arguments with a default parameter value in methods.</span></span>  <span data-ttu-id="2935c-161">这是为了便于与 C# 代码的互操作。</span><span class="sxs-lookup"><span data-stu-id="2935c-161">This is to help facilitate interoperation with C# code.</span></span>  <span data-ttu-id="2935c-162">下面的示例演示了该语法：</span><span class="sxs-lookup"><span data-stu-id="2935c-162">The following example demonstrates the syntax:</span></span>

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

<span data-ttu-id="2935c-163">请注意，为传入的值`DefaultParameterValue`必须与输入的类型匹配。</span><span class="sxs-lookup"><span data-stu-id="2935c-163">Note that the value passed in for `DefaultParameterValue` must match the input type.</span></span>  <span data-ttu-id="2935c-164">在上面的示例，它是`int`。</span><span class="sxs-lookup"><span data-stu-id="2935c-164">In the above sample, it is an `int`.</span></span>  <span data-ttu-id="2935c-165">尝试将传递到一个非整数值`DefaultParameterValue`将导致编译错误。</span><span class="sxs-lookup"><span data-stu-id="2935c-165">Attempting to pass a non-integer value into `DefaultParameterValue` would result in a compile error.</span></span>

## <a name="example-properties-and-methods"></a><span data-ttu-id="2935c-166">示例： 属性和方法</span><span class="sxs-lookup"><span data-stu-id="2935c-166">Example: Properties and Methods</span></span>

<span data-ttu-id="2935c-167">下面的示例包含具有字段、 私有函数、 属性和静态方法的示例的类型。</span><span class="sxs-lookup"><span data-stu-id="2935c-167">The following example contains a type that has examples of fields, private functions, properties, and a static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a><span data-ttu-id="2935c-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="2935c-168">See also</span></span>

- [<span data-ttu-id="2935c-169">成员</span><span class="sxs-lookup"><span data-stu-id="2935c-169">Members</span></span>](index.md)
