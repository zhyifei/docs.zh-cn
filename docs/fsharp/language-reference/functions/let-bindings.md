---
title: "let 绑定 (F#)"
description: "了解如何使用 F # let 将标识符的值或函数与相关联的绑定。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: bee69edc-d5ae-46bd-8b56-f02d97725d0d
ms.openlocfilehash: a57c5572e4bb5a3777c928dd572b7a84d4f0a334
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="let-bindings"></a><span data-ttu-id="1cabb-104">let 绑定</span><span class="sxs-lookup"><span data-stu-id="1cabb-104">let Bindings</span></span>

<span data-ttu-id="1cabb-105">A*绑定*将标识符的值或函数与相关联。</span><span class="sxs-lookup"><span data-stu-id="1cabb-105">A *binding* associates an identifier with a value or function.</span></span> <span data-ttu-id="1cabb-106">你使用`let`关键字要绑定到一个值或函数的名称。</span><span class="sxs-lookup"><span data-stu-id="1cabb-106">You use the `let` keyword to bind a name to a value or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="1cabb-107">语法</span><span class="sxs-lookup"><span data-stu-id="1cabb-107">Syntax</span></span>

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a><span data-ttu-id="1cabb-108">备注</span><span class="sxs-lookup"><span data-stu-id="1cabb-108">Remarks</span></span>

<span data-ttu-id="1cabb-109">`let`关键字用于定义值或一个或多个名称的函数值的表达式绑定。</span><span class="sxs-lookup"><span data-stu-id="1cabb-109">The `let` keyword is used in binding expressions to define values or function values for one or more names.</span></span> <span data-ttu-id="1cabb-110">最简单形式`let`表达式将一个名称，如下所示绑定到一个简单的值。</span><span class="sxs-lookup"><span data-stu-id="1cabb-110">The simplest form of the `let` expression binds a name to a simple value, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

<span data-ttu-id="1cabb-111">如果使用新行分隔标识符中的表达式，你必须缩进的表达式，如以下代码所示的每一行。</span><span class="sxs-lookup"><span data-stu-id="1cabb-111">If you separate the expression from the identifier by using a new line, you must indent each line of the expression, as in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

<span data-ttu-id="1cabb-112">而不是只是名称，可以指定包含名称的模式，例如，一个元组，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="1cabb-112">Instead of just a name, a pattern that contains names can be specified, for example, a tuple, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

<span data-ttu-id="1cabb-113">*主体表达式*是在其中使用这些名称的表达式。</span><span class="sxs-lookup"><span data-stu-id="1cabb-113">The *body-expression* is the expression in which the names are used.</span></span> <span data-ttu-id="1cabb-114">主体表达式显示在其自己的行，缩进到行向上与中的第一个字符完全`let`关键字：</span><span class="sxs-lookup"><span data-stu-id="1cabb-114">The body expression appears on its own line, indented to line up exactly with the first character in the `let` keyword:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

<span data-ttu-id="1cabb-115">A`let`绑定可以出现在模块级别，类类型的定义中或在本地作用域，例如在函数定义。</span><span class="sxs-lookup"><span data-stu-id="1cabb-115">A `let` binding can appear at the module level, in the definition of a class type, or in local scopes, such as in a function definition.</span></span> <span data-ttu-id="1cabb-116">A`let`顶部级别模块中或在类类型的绑定不需要具有正文表达式，但其他作用域级别，主体表达式是必需的。</span><span class="sxs-lookup"><span data-stu-id="1cabb-116">A `let` binding at the top level in a module or in a class type does not need to have a body expression, but at other scope levels, the body expression is required.</span></span> <span data-ttu-id="1cabb-117">绑定的名称后可用的定义，但不是能在之前的点`let`绑定出现，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="1cabb-117">The bound names are usable after the point of definition, but not at any point before the `let` binding appears, as is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]
    
## <a name="function-bindings"></a><span data-ttu-id="1cabb-118">函数绑定</span><span class="sxs-lookup"><span data-stu-id="1cabb-118">Function Bindings</span></span>

<span data-ttu-id="1cabb-119">函数绑定符合规则的值绑定，只不过函数的绑定包括函数名称和参数，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="1cabb-119">Function bindings follow the rules for value bindings, except that function bindings include the function name and the parameters, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

<span data-ttu-id="1cabb-120">一般情况下，参数是模式，例如元组模式：</span><span class="sxs-lookup"><span data-stu-id="1cabb-120">In general, parameters are patterns, such as a tuple pattern:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

<span data-ttu-id="1cabb-121">A`let`绑定表达式的计算结果为最后一个表达式的值。</span><span class="sxs-lookup"><span data-stu-id="1cabb-121">A `let` binding expression evaluates to the value of the last expression.</span></span> <span data-ttu-id="1cabb-122">因此，在下面的代码示例的值`result`从计算`100 * function3 (1, 2)`，其计算结果为`300`。</span><span class="sxs-lookup"><span data-stu-id="1cabb-122">Therefore, in the following code example, the value of `result` is computed from `100 * function3 (1, 2)`, which evaluates to `300`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

<span data-ttu-id="1cabb-123">有关详细信息，请参阅[函数](index.md)。</span><span class="sxs-lookup"><span data-stu-id="1cabb-123">For more information, see [Functions](index.md).</span></span>

## <a name="type-annotations"></a><span data-ttu-id="1cabb-124">类型批注</span><span class="sxs-lookup"><span data-stu-id="1cabb-124">Type Annotations</span></span>

<span data-ttu-id="1cabb-125">你可以通过包含冒号 （:） 后, 跟类型名称，所有括在括号指定参数的类型。</span><span class="sxs-lookup"><span data-stu-id="1cabb-125">You can specify types for parameters by including a colon (:) followed by a type name, all enclosed in parentheses.</span></span> <span data-ttu-id="1cabb-126">此外可以通过在最后一个参数的后面追加的冒号和类型指定返回值的类型。</span><span class="sxs-lookup"><span data-stu-id="1cabb-126">You can also specify the type of the return value by appending the colon and type after the last parameter.</span></span> <span data-ttu-id="1cabb-127">完整类型批注`function1`，整数作为参数类型，是不可能，如下所示。</span><span class="sxs-lookup"><span data-stu-id="1cabb-127">The full type annotations for `function1`, with integers as the parameter types, would be as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

<span data-ttu-id="1cabb-128">类型推理时没有显式类型参数，用于确定函数的参数的类型。</span><span class="sxs-lookup"><span data-stu-id="1cabb-128">When there are no explicit type parameters, type inference is used to determine the types of parameters of functions.</span></span> <span data-ttu-id="1cabb-129">这可能包括自动通用化是通用参数的类型。</span><span class="sxs-lookup"><span data-stu-id="1cabb-129">This can include automatically generalizing the type of a parameter to be generic.</span></span>

<span data-ttu-id="1cabb-130">有关详细信息，请参阅[自动泛化](../generics/automatic-generalization.md)和[类型推理](../type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="1cabb-130">For more information, see [Automatic Generalization](../generics/automatic-generalization.md) and [Type Inference](../type-inference.md).</span></span>

## <a name="let-bindings-in-classes"></a><span data-ttu-id="1cabb-131">类中的 let 绑定</span><span class="sxs-lookup"><span data-stu-id="1cabb-131">let Bindings in Classes</span></span>

<span data-ttu-id="1cabb-132">A`let`绑定可以出现在类类型，但不是在结构或记录类型。</span><span class="sxs-lookup"><span data-stu-id="1cabb-132">A `let` binding can appear in a class type but not in a structure or record type.</span></span> <span data-ttu-id="1cabb-133">若要使用的类类型中的 let 绑定，此类必须具有主构造函数。</span><span class="sxs-lookup"><span data-stu-id="1cabb-133">To use a let binding in a class type, the class must have a primary constructor.</span></span> <span data-ttu-id="1cabb-134">构造函数参数必须出现在类定义中的类型名称之后。</span><span class="sxs-lookup"><span data-stu-id="1cabb-134">Constructor parameters must appear after the type name in the class definition.</span></span> <span data-ttu-id="1cabb-135">A`let`中的类类型的绑定定义私有字段和成员对此类类型，并连同`do`在类型中，绑定窗体类型的主构造函数的代码。</span><span class="sxs-lookup"><span data-stu-id="1cabb-135">A `let` binding in a class type defines private fields and members for that class type and, together with `do` bindings in the type, forms the code for the primary constructor for the type.</span></span> <span data-ttu-id="1cabb-136">下面的代码示例显示了一个类`MyClass`私有字段与`field1`和`field2`。</span><span class="sxs-lookup"><span data-stu-id="1cabb-136">The following code examples show a class `MyClass` with private fields `field1` and `field2`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

<span data-ttu-id="1cabb-137">作用域`field1`和`field2`仅限于在其中声明它们的类型。</span><span class="sxs-lookup"><span data-stu-id="1cabb-137">The scopes of `field1` and `field2` are limited to the type in which they are declared.</span></span> <span data-ttu-id="1cabb-138">有关详细信息，请参阅[`let`类中的绑定](../members/let-bindings-in-classes.md)和[类](../classes.md)。</span><span class="sxs-lookup"><span data-stu-id="1cabb-138">For more information, see [`let` Bindings in Classes](../members/let-bindings-in-classes.md) and [Classes](../classes.md).</span></span>

## <a name="type-parameters-in-let-bindings"></a><span data-ttu-id="1cabb-139">类型参数中的 let 绑定</span><span class="sxs-lookup"><span data-stu-id="1cabb-139">Type Parameters in let Bindings</span></span>

<span data-ttu-id="1cabb-140">A`let`在模块级别，在类型中，或在计算表达式中的绑定可以具有显式类型参数。</span><span class="sxs-lookup"><span data-stu-id="1cabb-140">A `let` binding at the module level, in a type, or in a computation expression can have explicit type parameters.</span></span> <span data-ttu-id="1cabb-141">中的 let 绑定表达式中，如在函数定义中，不能有类型参数。</span><span class="sxs-lookup"><span data-stu-id="1cabb-141">A let binding in an expression, such as within a function definition, cannot have type parameters.</span></span> <span data-ttu-id="1cabb-142">有关详细信息，请参阅[泛型](../generics/index.md)。</span><span class="sxs-lookup"><span data-stu-id="1cabb-142">For more information, see [Generics](../generics/index.md).</span></span>

## <a name="attributes-on-let-bindings"></a><span data-ttu-id="1cabb-143">上的属性的 let 绑定</span><span class="sxs-lookup"><span data-stu-id="1cabb-143">Attributes on let Bindings</span></span>

<span data-ttu-id="1cabb-144">特性可以应用到顶级`let`在模块中，如下面的代码中所示的绑定。</span><span class="sxs-lookup"><span data-stu-id="1cabb-144">Attributes can be applied to top-level `let` bindings in a module, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]
    
## <a name="scope-and-accessibility-of-let-bindings"></a><span data-ttu-id="1cabb-145">作用域和可访问性 Let 绑定</span><span class="sxs-lookup"><span data-stu-id="1cabb-145">Scope and Accessibility of Let Bindings</span></span>

<span data-ttu-id="1cabb-146">使用让绑定声明的实体的作用域仅限于包含的部分绑定显示后 （如函数、 模块、 文件或类） 作用域。</span><span class="sxs-lookup"><span data-stu-id="1cabb-146">The scope of an entity declared with a let binding is limited to the portion of the containing scope (such as a function, module, file or class) after the binding appears.</span></span> <span data-ttu-id="1cabb-147">因此，可以认为让的绑定到作用域中引入了一个名称。</span><span class="sxs-lookup"><span data-stu-id="1cabb-147">Therefore, it can be said that a let binding introduces a name into a scope.</span></span> <span data-ttu-id="1cabb-148">模块中的 let 绑定值或函数都可以访问的模块的客户端，只要该模块可以访问，因为模块中的 let 的绑定编译为公共函数的模块。</span><span class="sxs-lookup"><span data-stu-id="1cabb-148">In a module, a let-bound value or function is accessible to clients of a module as long as the module is accessible, since the let bindings in a module are compiled into public functions of the module.</span></span> <span data-ttu-id="1cabb-149">与此相反，类中的 let 的绑定是私有到类类型。</span><span class="sxs-lookup"><span data-stu-id="1cabb-149">By contrast, let bindings in a class are private to the class.</span></span>

<span data-ttu-id="1cabb-150">通常情况下，必须由模块时使用的客户端代码的名称限定模块中的函数。</span><span class="sxs-lookup"><span data-stu-id="1cabb-150">Normally, functions in modules must be qualified by the name of the module when used by client code.</span></span> <span data-ttu-id="1cabb-151">例如，如果模块`Module1`有一个函数`function1`，用户将指定`Module1.function1`来引用该函数。</span><span class="sxs-lookup"><span data-stu-id="1cabb-151">For example, if a module `Module1` has a function `function1`, users would specify `Module1.function1` to refer to the function.</span></span>

<span data-ttu-id="1cabb-152">模块的用户可使用的导入声明不在按模块名称限定的情况下做出该模块中的函数可供使用。</span><span class="sxs-lookup"><span data-stu-id="1cabb-152">Users of a module may use an import declaration to make the functions within that module available for use without being qualified by the module name.</span></span> <span data-ttu-id="1cabb-153">在刚刚提到的示例中，模块的用户可以在这种情况下打开该模块使用导入声明打开`Module1`和此后指`function1`直接。</span><span class="sxs-lookup"><span data-stu-id="1cabb-153">In the example just mentioned, users of the module can in that case open the module by using the import declaration open `Module1` and thereafter refer to `function1` directly.</span></span>

```fsharp
module Module1 =
    let function1 x = x + 1.0

module Module2 =
    let function2 x =
        Module1.function1 x

open Module1

let function3 x =
    function1 x
```

<span data-ttu-id="1cabb-154">一些模块具有属性[RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15)，这意味着它们公开的函数必须用模块的名称进行限定。</span><span class="sxs-lookup"><span data-stu-id="1cabb-154">Some modules have the attribute [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), which means that the functions that they expose must be qualified with the name of the module.</span></span> <span data-ttu-id="1cabb-155">例如，F # 列表模块具有此属性。</span><span class="sxs-lookup"><span data-stu-id="1cabb-155">For example, the F# List module has this attribute.</span></span>

<span data-ttu-id="1cabb-156">模块和访问控制的详细信息，请参阅[模块](../modules.md)和[访问控制](../access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="1cabb-156">For more information on modules and access control, see [Modules](../modules.md) and [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1cabb-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1cabb-157">See Also</span></span>

[<span data-ttu-id="1cabb-158">函数</span><span class="sxs-lookup"><span data-stu-id="1cabb-158">Functions</span></span>](index.md)

[<span data-ttu-id="1cabb-159">类中的 `let` 绑定</span><span class="sxs-lookup"><span data-stu-id="1cabb-159">`let` Bindings in Classes</span></span>](../members/let-bindings-in-classes.md)
