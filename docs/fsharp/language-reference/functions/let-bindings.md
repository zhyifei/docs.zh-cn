---
title: let 绑定
description: 了解如何使用F#let 绑定，将一个标识符关联的值或函数。
ms.date: 05/16/2016
ms.openlocfilehash: ac33ee761cd4881f3d82d6680a07f62a1d7e77e5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641900"
---
# <a name="let-bindings"></a><span data-ttu-id="03d51-103">let 绑定</span><span class="sxs-lookup"><span data-stu-id="03d51-103">let Bindings</span></span>

<span data-ttu-id="03d51-104">一个*绑定*标识符相关联的值或函数。</span><span class="sxs-lookup"><span data-stu-id="03d51-104">A *binding* associates an identifier with a value or function.</span></span> <span data-ttu-id="03d51-105">您使用`let`关键字将绑定到值或函数的名称。</span><span class="sxs-lookup"><span data-stu-id="03d51-105">You use the `let` keyword to bind a name to a value or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="03d51-106">语法</span><span class="sxs-lookup"><span data-stu-id="03d51-106">Syntax</span></span>

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a><span data-ttu-id="03d51-107">备注</span><span class="sxs-lookup"><span data-stu-id="03d51-107">Remarks</span></span>

<span data-ttu-id="03d51-108">`let`关键字用于绑定表达式来定义值或函数值的一个或多个名称。</span><span class="sxs-lookup"><span data-stu-id="03d51-108">The `let` keyword is used in binding expressions to define values or function values for one or more names.</span></span> <span data-ttu-id="03d51-109">最简单的形式`let`表达式将一个名称，如下所示绑定到一个简单的值。</span><span class="sxs-lookup"><span data-stu-id="03d51-109">The simplest form of the `let` expression binds a name to a simple value, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

<span data-ttu-id="03d51-110">如果使用新行分隔标识符中的表达式，必须缩进每一行的表达式，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="03d51-110">If you separate the expression from the identifier by using a new line, you must indent each line of the expression, as in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

<span data-ttu-id="03d51-111">而不是只是一个名称，可以指定包含名称的模式，例如，一个元组，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="03d51-111">Instead of just a name, a pattern that contains names can be specified, for example, a tuple, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

<span data-ttu-id="03d51-112">*正文表达式*是在其中使用这些名称的表达式。</span><span class="sxs-lookup"><span data-stu-id="03d51-112">The *body-expression* is the expression in which the names are used.</span></span> <span data-ttu-id="03d51-113">主体表达式出现在其自己的行，缩进到行向上完全的第一个字符`let`关键字：</span><span class="sxs-lookup"><span data-stu-id="03d51-113">The body expression appears on its own line, indented to line up exactly with the first character in the `let` keyword:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

<span data-ttu-id="03d51-114">一个`let`绑定可以出现在模块级别，类类型的定义中或在本地作用域，例如函数定义。</span><span class="sxs-lookup"><span data-stu-id="03d51-114">A `let` binding can appear at the module level, in the definition of a class type, or in local scopes, such as in a function definition.</span></span> <span data-ttu-id="03d51-115">一个`let`在顶层模块中或在类类型的绑定不需要具有正文表达式，但在其他作用域级别，正文表达式是必需。</span><span class="sxs-lookup"><span data-stu-id="03d51-115">A `let` binding at the top level in a module or in a class type does not need to have a body expression, but at other scope levels, the body expression is required.</span></span> <span data-ttu-id="03d51-116">绑定的名称是可用的定义，但不是能在之前的时间点后`let`绑定将出现，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="03d51-116">The bound names are usable after the point of definition, but not at any point before the `let` binding appears, as is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a><span data-ttu-id="03d51-117">函数绑定</span><span class="sxs-lookup"><span data-stu-id="03d51-117">Function Bindings</span></span>

<span data-ttu-id="03d51-118">函数绑定遵循值绑定的规则，只不过函数的绑定包括函数名称和参数，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="03d51-118">Function bindings follow the rules for value bindings, except that function bindings include the function name and the parameters, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

<span data-ttu-id="03d51-119">一般情况下，参数是模式，例如元组模式：</span><span class="sxs-lookup"><span data-stu-id="03d51-119">In general, parameters are patterns, such as a tuple pattern:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

<span data-ttu-id="03d51-120">一个`let`绑定表达式的计算结果为最后一个表达式的值。</span><span class="sxs-lookup"><span data-stu-id="03d51-120">A `let` binding expression evaluates to the value of the last expression.</span></span> <span data-ttu-id="03d51-121">因此，在下面的代码示例的值`result`计算得出`100 * function3 (1, 2)`，其计算结果为`300`。</span><span class="sxs-lookup"><span data-stu-id="03d51-121">Therefore, in the following code example, the value of `result` is computed from `100 * function3 (1, 2)`, which evaluates to `300`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

<span data-ttu-id="03d51-122">有关详细信息，请参阅[函数](index.md)。</span><span class="sxs-lookup"><span data-stu-id="03d51-122">For more information, see [Functions](index.md).</span></span>

## <a name="type-annotations"></a><span data-ttu-id="03d51-123">类型批注</span><span class="sxs-lookup"><span data-stu-id="03d51-123">Type Annotations</span></span>

<span data-ttu-id="03d51-124">可以通过包括所有括在括号中的类型名称后跟一个冒号 （:） 指定为参数的类型。</span><span class="sxs-lookup"><span data-stu-id="03d51-124">You can specify types for parameters by including a colon (:) followed by a type name, all enclosed in parentheses.</span></span> <span data-ttu-id="03d51-125">此外可以通过在最后一个参数的后面追加冒号和类型指定的返回值的类型。</span><span class="sxs-lookup"><span data-stu-id="03d51-125">You can also specify the type of the return value by appending the colon and type after the last parameter.</span></span> <span data-ttu-id="03d51-126">完整类型批注`function1`，作为参数类型的整数，是不可能按如下所示。</span><span class="sxs-lookup"><span data-stu-id="03d51-126">The full type annotations for `function1`, with integers as the parameter types, would be as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

<span data-ttu-id="03d51-127">类型推理时没有显式类型参数，用于确定函数的参数的类型。</span><span class="sxs-lookup"><span data-stu-id="03d51-127">When there are no explicit type parameters, type inference is used to determine the types of parameters of functions.</span></span> <span data-ttu-id="03d51-128">这可能包括自动泛化参数用作泛型类型。</span><span class="sxs-lookup"><span data-stu-id="03d51-128">This can include automatically generalizing the type of a parameter to be generic.</span></span>

<span data-ttu-id="03d51-129">有关详细信息，请参阅[自动泛化](../generics/automatic-generalization.md)并[类型推理](../type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="03d51-129">For more information, see [Automatic Generalization](../generics/automatic-generalization.md) and [Type Inference](../type-inference.md).</span></span>

## <a name="let-bindings-in-classes"></a><span data-ttu-id="03d51-130">类中的 let 绑定</span><span class="sxs-lookup"><span data-stu-id="03d51-130">let Bindings in Classes</span></span>

<span data-ttu-id="03d51-131">一个`let`绑定可以出现在类类型，但不是在结构或记录类型。</span><span class="sxs-lookup"><span data-stu-id="03d51-131">A `let` binding can appear in a class type but not in a structure or record type.</span></span> <span data-ttu-id="03d51-132">若要使用的类类型中的 let 绑定，类必须具有主构造函数。</span><span class="sxs-lookup"><span data-stu-id="03d51-132">To use a let binding in a class type, the class must have a primary constructor.</span></span> <span data-ttu-id="03d51-133">构造函数参数必须出现在类定义中的类型名称之后。</span><span class="sxs-lookup"><span data-stu-id="03d51-133">Constructor parameters must appear after the type name in the class definition.</span></span> <span data-ttu-id="03d51-134">一个`let`中的类类型的绑定定义私有字段和成员的类类型的并连同`do`在类型中，绑定窗体类型的主构造函数的代码。</span><span class="sxs-lookup"><span data-stu-id="03d51-134">A `let` binding in a class type defines private fields and members for that class type and, together with `do` bindings in the type, forms the code for the primary constructor for the type.</span></span> <span data-ttu-id="03d51-135">下面的代码示例显示了一个类`MyClass`私有字段具有`field1`和`field2`。</span><span class="sxs-lookup"><span data-stu-id="03d51-135">The following code examples show a class `MyClass` with private fields `field1` and `field2`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

<span data-ttu-id="03d51-136">作用域`field1`和`field2`仅限于在其中声明它们的类型。</span><span class="sxs-lookup"><span data-stu-id="03d51-136">The scopes of `field1` and `field2` are limited to the type in which they are declared.</span></span> <span data-ttu-id="03d51-137">有关详细信息，请参阅[`let`类中的绑定](../members/let-bindings-in-classes.md)并[类](../classes.md)。</span><span class="sxs-lookup"><span data-stu-id="03d51-137">For more information, see [`let` Bindings in Classes](../members/let-bindings-in-classes.md) and [Classes](../classes.md).</span></span>

## <a name="type-parameters-in-let-bindings"></a><span data-ttu-id="03d51-138">中的类型参数的 let 绑定</span><span class="sxs-lookup"><span data-stu-id="03d51-138">Type Parameters in let Bindings</span></span>

<span data-ttu-id="03d51-139">一个`let`在模块级别，在类型中，或在计算表达式中的绑定可以具有显式类型参数。</span><span class="sxs-lookup"><span data-stu-id="03d51-139">A `let` binding at the module level, in a type, or in a computation expression can have explicit type parameters.</span></span> <span data-ttu-id="03d51-140">中的 let 绑定表达式，例如在函数定义中，不能有类型参数。</span><span class="sxs-lookup"><span data-stu-id="03d51-140">A let binding in an expression, such as within a function definition, cannot have type parameters.</span></span> <span data-ttu-id="03d51-141">有关详细信息，请参阅[泛型](../generics/index.md)。</span><span class="sxs-lookup"><span data-stu-id="03d51-141">For more information, see [Generics](../generics/index.md).</span></span>

## <a name="attributes-on-let-bindings"></a><span data-ttu-id="03d51-142">上的属性的 let 绑定</span><span class="sxs-lookup"><span data-stu-id="03d51-142">Attributes on let Bindings</span></span>

<span data-ttu-id="03d51-143">属性可应用于顶级`let`绑定在模块中，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="03d51-143">Attributes can be applied to top-level `let` bindings in a module, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a><span data-ttu-id="03d51-144">作用域和辅助功能的 Let 绑定</span><span class="sxs-lookup"><span data-stu-id="03d51-144">Scope and Accessibility of Let Bindings</span></span>

<span data-ttu-id="03d51-145">使用 let 绑定声明的实体的作用域被限制到部分包含的绑定出现后 （如函数、 模块、 文件或类） 作用域。</span><span class="sxs-lookup"><span data-stu-id="03d51-145">The scope of an entity declared with a let binding is limited to the portion of the containing scope (such as a function, module, file or class) after the binding appears.</span></span> <span data-ttu-id="03d51-146">因此，可以认为 let 的绑定到作用域中引入了一个名称。</span><span class="sxs-lookup"><span data-stu-id="03d51-146">Therefore, it can be said that a let binding introduces a name into a scope.</span></span> <span data-ttu-id="03d51-147">在模块中，let 绑定值或函数都可以访问客户端的一个模块，只要该模块是可访问，因为在模块中的 let 的绑定会编译到模块的公共函数。</span><span class="sxs-lookup"><span data-stu-id="03d51-147">In a module, a let-bound value or function is accessible to clients of a module as long as the module is accessible, since the let bindings in a module are compiled into public functions of the module.</span></span> <span data-ttu-id="03d51-148">与此相反，在类中的 let 的绑定是私有的类。</span><span class="sxs-lookup"><span data-stu-id="03d51-148">By contrast, let bindings in a class are private to the class.</span></span>

<span data-ttu-id="03d51-149">通常情况下，模块中的函数必须由时使用的客户端代码的模块的名称限定。</span><span class="sxs-lookup"><span data-stu-id="03d51-149">Normally, functions in modules must be qualified by the name of the module when used by client code.</span></span> <span data-ttu-id="03d51-150">例如，如果一个模块`Module1`有一个函数`function1`，用户将指定`Module1.function1`来引用该函数。</span><span class="sxs-lookup"><span data-stu-id="03d51-150">For example, if a module `Module1` has a function `function1`, users would specify `Module1.function1` to refer to the function.</span></span>

<span data-ttu-id="03d51-151">模块的用户可使用导入声明不按模块名称限定的情况下使该模块中的函数可供使用。</span><span class="sxs-lookup"><span data-stu-id="03d51-151">Users of a module may use an import declaration to make the functions within that module available for use without being qualified by the module name.</span></span> <span data-ttu-id="03d51-152">在刚刚提到的示例中，模块的用户可以在这种情况下打开模块通过使用导入声明开放`Module1`和之后是指`function1`直接。</span><span class="sxs-lookup"><span data-stu-id="03d51-152">In the example just mentioned, users of the module can in that case open the module by using the import declaration open `Module1` and thereafter refer to `function1` directly.</span></span>

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

<span data-ttu-id="03d51-153">某些模块具有属性[RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15)，这意味着，必须使用的模块的名称限定它们公开的函数。</span><span class="sxs-lookup"><span data-stu-id="03d51-153">Some modules have the attribute [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), which means that the functions that they expose must be qualified with the name of the module.</span></span> <span data-ttu-id="03d51-154">例如，F#列表模块具有此属性。</span><span class="sxs-lookup"><span data-stu-id="03d51-154">For example, the F# List module has this attribute.</span></span>

<span data-ttu-id="03d51-155">模块和访问控制的详细信息，请参阅[模块](../modules.md)并[访问控制](../access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="03d51-155">For more information on modules and access control, see [Modules](../modules.md) and [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="03d51-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="03d51-156">See also</span></span>

- [<span data-ttu-id="03d51-157">函数</span><span class="sxs-lookup"><span data-stu-id="03d51-157">Functions</span></span>](index.md)
- [<span data-ttu-id="03d51-158">类中的 `let` 绑定</span><span class="sxs-lookup"><span data-stu-id="03d51-158">`let` Bindings in Classes</span></span>](../members/let-bindings-in-classes.md)
