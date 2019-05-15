---
title: 泛型
description: 了解如何使用F#泛型函数和类型，以便你能够编写代码，而无需重复代码适用于不同的类型。
ms.date: 05/16/2016
ms.openlocfilehash: e30b00343e48d3a8abd51f62c003ba0d1984db18
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641854"
---
# <a name="generics"></a><span data-ttu-id="b1fa5-103">泛型</span><span class="sxs-lookup"><span data-stu-id="b1fa5-103">Generics</span></span>

<span data-ttu-id="b1fa5-104">F# 函式值、方法、属性和聚合类型（如类、记录和可区分联合）都可以是“泛型”。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-104">F# function values, methods, properties, and aggregate types such as classes, records, and discriminated unions can be *generic*.</span></span> <span data-ttu-id="b1fa5-105">泛型构造至少包含一个类型参数，该类型参数通常由泛型构造的用户提供。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-105">Generic constructs contain at least one type parameter, which is usually supplied by the user of the generic construct.</span></span> <span data-ttu-id="b1fa5-106">通过泛型函数和类型，可编写可用于各种类型的代码，而无需针对每个类型重复编写代码。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-106">Generic functions and types enable you to write code that works with a variety of types without repeating the code for each type.</span></span> <span data-ttu-id="b1fa5-107">利用 F# 编写泛型代码很简单，这是因为编译器的类型推理和自动泛化机制通常会将代码隐式地推断为泛型代码。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-107">Making your code generic can be simple in F#, because often your code is implicitly inferred to be generic by the compiler's type inference and automatic generalization mechanisms.</span></span>

## <a name="syntax"></a><span data-ttu-id="b1fa5-108">语法</span><span class="sxs-lookup"><span data-stu-id="b1fa5-108">Syntax</span></span>

```fsharp
// Explicitly generic function.
let function-name<type-parameters> parameter-list =
function-body

// Explicitly generic method.
[ static ] member object-identifer.method-name<type-parameters> parameter-list [ return-type ] =
method-body

// Explicitly generic class, record, interface, structure,
// or discriminated union.
type type-name<type-parameters> type-definition
```

## <a name="remarks"></a><span data-ttu-id="b1fa5-109">备注</span><span class="sxs-lookup"><span data-stu-id="b1fa5-109">Remarks</span></span>

<span data-ttu-id="b1fa5-110">显式泛型函数或类型的声明与非泛型函数或类型的声明非常相似，但类型参数的规范（和用法）不同，它们位于函数或类型名称后面的尖括号中。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-110">The declaration of an explicitly generic function or type is much like that of a non-generic function or type, except for the specification (and use) of the type parameters, in angle brackets after the function or type name.</span></span>

<span data-ttu-id="b1fa5-111">声明通常为隐式泛型。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-111">Declarations are often implicitly generic.</span></span> <span data-ttu-id="b1fa5-112">如果未完全指定用于组合函数或类型的每个参数的类型，编译器将尝试从所编写的代码中推断每个参数、值和变量的类型。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-112">If you do not fully specify the type of every parameter that is used to compose a function or type, the compiler attempts to infer the type of each parameter, value, and variable from the code you write.</span></span> <span data-ttu-id="b1fa5-113">有关更多信息，请参见[类型推理](../type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-113">For more information, see [Type Inference](../type-inference.md).</span></span> <span data-ttu-id="b1fa5-114">如果类型或函数的代码没有约束参数的类型，则该函数或类型为隐式泛型。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-114">If the code for your type or function does not otherwise constrain the types of parameters, the function or type is implicitly generic.</span></span> <span data-ttu-id="b1fa5-115">此过程被称为自动泛化。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-115">This process is named *automatic generalization*.</span></span> <span data-ttu-id="b1fa5-116">自动泛化有一些限制。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-116">There are some limits on automatic generalization.</span></span> <span data-ttu-id="b1fa5-117">例如，如果 F# 编译器无法推断泛型构造的类型，编译器会报告错误，指出存在一个称作“值限制”的限制。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-117">For example, if the F# compiler is unable to infer the types for a generic construct, the compiler reports an error that refers to a restriction called the *value restriction*.</span></span> <span data-ttu-id="b1fa5-118">在此情况下，可能必须添加一些类型批注。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-118">In that case, you may have to add some type annotations.</span></span> <span data-ttu-id="b1fa5-119">有关自动泛化和值限制以及如何更改代码来解决问题的更多信息，请参见[自动泛化](automatic-generalization.md)。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-119">For more information about automatic generalization and the value restriction, and how to change your code to address the problem, see [Automatic Generalization](automatic-generalization.md).</span></span>

<span data-ttu-id="b1fa5-120">在之前的语法中，*type-parameters* 是一个表示未知类型的参数的逗号分隔列表，其中每个参数都以单引号开头，并且可选择包含一个约束子句，用来进一步限制可用于该类型参数的类型。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-120">In the previous syntax, *type-parameters* is a comma-separated list of parameters that represent unknown types, each of which starts with a single quotation mark, optionally with a constraint clause that further limits what types may be used for that type parameter.</span></span> <span data-ttu-id="b1fa5-121">有关各种约束子句的语法以及有关约束的其他信息，请参见[约束](constraints.md)。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-121">For the syntax for constraint clauses of various kinds and other information about constraints, see [Constraints](constraints.md).</span></span>

<span data-ttu-id="b1fa5-122">语法中的 *type-definition* 与非泛型类型的类型定义相同。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-122">The *type-definition* in the syntax is the same as the type definition for a non-generic type.</span></span> <span data-ttu-id="b1fa5-123">它包括类类型的构造函数参数、可选的 `as` 子句、等号、记录字段、`inherit` 子句、可区分联合的选项、`let` 绑定和 `do` 绑定、成员定义，以及非泛型类型定义中允许的任何其他内容。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-123">It includes the constructor parameters for a class type, an optional `as` clause, the equal symbol, the record fields, the `inherit` clause, the choices for a discriminated union, `let` and `do` bindings, member definitions, and anything else permitted in a non-generic type definition.</span></span>

<span data-ttu-id="b1fa5-124">其他语法元素与非泛型函数和类型的语法元素相同。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-124">The other syntax elements are the same as those for non-generic functions and types.</span></span> <span data-ttu-id="b1fa5-125">例如，*object-identifier* 是一个表示包含对象本身的标识符。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-125">For example, *object-identifier* is an identifier that represents the containing object itself.</span></span>

<span data-ttu-id="b1fa5-126">属性、字段和构造函数不能比封闭类型更加泛型化。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-126">Properties, fields, and constructors cannot be more generic than the enclosing type.</span></span> <span data-ttu-id="b1fa5-127">此外，模块中的值不能为泛型。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-127">Also, values in a module cannot be generic.</span></span>

## <a name="implicitly-generic-constructs"></a><span data-ttu-id="b1fa5-128">隐式泛型构造</span><span class="sxs-lookup"><span data-stu-id="b1fa5-128">Implicitly Generic Constructs</span></span>

<span data-ttu-id="b1fa5-129">当 F# 编译器推断代码中的类型时，会自动将任何可以为泛型的函数视为泛型。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-129">When the F# compiler infers the types in your code, it automatically treats any function that can be generic as generic.</span></span> <span data-ttu-id="b1fa5-130">如果显式指定某个类型（例如参数类型），则将阻止自动泛化。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-130">If you specify a type explicitly, such as a parameter type, you prevent automatic generalization.</span></span>

<span data-ttu-id="b1fa5-131">在以下代码示例中，`makeList` 为泛型，尽管未将它或它的参数显式声明为泛型。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-131">In the following code example, `makeList` is generic, even though neither it nor its parameters are explicitly declared as generic.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1700.fs)]

<span data-ttu-id="b1fa5-132">该函数的签名被推断为 `'a -> 'a -> 'a list`。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-132">The signature of the function is inferred to be `'a -> 'a -> 'a list`.</span></span> <span data-ttu-id="b1fa5-133">请注意，本示例中的 `a` 和 `b` 被推断为具有相同的类型。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-133">Note that `a` and `b` in this example are inferred to have the same type.</span></span> <span data-ttu-id="b1fa5-134">这是因为它们一起包括在一个列表中，并且列表中的所有元素必须是相同类型的元素。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-134">This is because they are included in a list together, and all elements of a list must be of the same type.</span></span>

<span data-ttu-id="b1fa5-135">还可以通过在类型批注中使用单引号语法来指示参数类型是泛型类型参数，从而使一个函数成为泛型函数。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-135">You can also make a function generic by using the single quotation mark syntax in a type annotation to indicate that a parameter type is a generic type parameter.</span></span> <span data-ttu-id="b1fa5-136">在以下代码示例中，`function1` 为泛型，因为其参数以这种方式被声明为类型参数。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-136">In the following code, `function1` is generic because its parameters are declared in this manner, as type parameters.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1701.fs)]

## <a name="explicitly-generic-constructs"></a><span data-ttu-id="b1fa5-137">显式泛型构造</span><span class="sxs-lookup"><span data-stu-id="b1fa5-137">Explicitly Generic Constructs</span></span>

<span data-ttu-id="b1fa5-138">还可以通过在尖括号 (`<type-parameter>`) 中显式声明函数的类型参数来使一个函数成为泛型函数。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-138">You can also make a function generic by explicitly declaring its type parameters in angle brackets (`<type-parameter>`).</span></span> <span data-ttu-id="b1fa5-139">下面的代码阐释这一点。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-139">The following code illustrates this.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1703.fs)]

## <a name="using-generic-constructs"></a><span data-ttu-id="b1fa5-140">使用泛型构造</span><span class="sxs-lookup"><span data-stu-id="b1fa5-140">Using Generic Constructs</span></span>

<span data-ttu-id="b1fa5-141">使用泛型函数或方法时，不必指定类型参数。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-141">When you use generic functions or methods, you might not have to specify the type arguments.</span></span> <span data-ttu-id="b1fa5-142">编译器使用类型推理来推断适当的类型参数。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-142">The compiler uses type inference to infer the appropriate type arguments.</span></span> <span data-ttu-id="b1fa5-143">如果仍然存在多义性，则可以在尖括号中提供类型参数，并用逗号分隔多个类型参数。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-143">If there is still an ambiguity, you can supply type arguments in angle brackets, separating multiple type arguments with commas.</span></span>

<span data-ttu-id="b1fa5-144">以下代码显示之前部分中定义的函数的用法。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-144">The following code shows the use of the functions that are defined in the previous sections.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1702.fs)]

> [!NOTE]
> <span data-ttu-id="b1fa5-145">有两种方法可以通过名称指代泛型类型。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-145">There are two ways to refer to a generic type by name.</span></span> <span data-ttu-id="b1fa5-146">例如，`list<int>` 和 `int list` 这两种方法可用来指代具有单个类型参数 `list` 的泛型类型 `int`。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-146">For example, `list<int>` and `int list` are two ways to refer to a generic type `list` that has a single type argument `int`.</span></span> <span data-ttu-id="b1fa5-147">后一种形式通常只用于内置 F# 类型，例如 `list` 和 `option`。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-147">The latter form is conventionally used only with built-in F# types such as `list` and `option`.</span></span> <span data-ttu-id="b1fa5-148">如果存在多个类型参数，通常会使用语法 `Dictionary<int, string>`，但还可使用语法 `(int, string) Dictionary`。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-148">If there are multiple type arguments, you normally use the syntax `Dictionary<int, string>` but you can also use the syntax `(int, string) Dictionary`.</span></span>

## <a name="wildcards-as-type-arguments"></a><span data-ttu-id="b1fa5-149">通配符作为类型参数</span><span class="sxs-lookup"><span data-stu-id="b1fa5-149">Wildcards as Type Arguments</span></span>

<span data-ttu-id="b1fa5-150">若要指定应由编译器推断类型参数，可以使用下划线或通配符 (`_`)，而不要使用已命名的类型参数。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-150">To specify that a type argument should be inferred by the compiler, you can use the underscore, or wildcard symbol (`_`), instead of a named type argument.</span></span> <span data-ttu-id="b1fa5-151">以下代码对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-151">This is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1704.fs)]

## <a name="constraints-in-generic-types-and-functions"></a><span data-ttu-id="b1fa5-152">泛型类型和函数中的约束</span><span class="sxs-lookup"><span data-stu-id="b1fa5-152">Constraints in Generic Types and Functions</span></span>

<span data-ttu-id="b1fa5-153">在泛型类型或函数定义中，只可使用那些已知可用于泛型类型参数的构造。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-153">In a generic type or function definition, you can use only those constructs that are known to be available on the generic type parameter.</span></span> <span data-ttu-id="b1fa5-154">这对于在编译时启用对函数调用和方法调用的验证是必需的。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-154">This is required to enable the verification of function and method calls at compile time.</span></span> <span data-ttu-id="b1fa5-155">如果显式声明类型参数，则可对泛型类型参数应用显式约束，以通知编译器某些方法和函数是可用的。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-155">If you declare your type parameters explicitly, you can apply an explicit constraint to a generic type parameter to notify the compiler that certain methods and functions are available.</span></span> <span data-ttu-id="b1fa5-156">但是，如果允许 F# 编译器推断泛型参数类型，它将为你确定适当的约束。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-156">However, if you allow the F# compiler to infer your generic parameter types, it will determine the appropriate constraints for you.</span></span> <span data-ttu-id="b1fa5-157">有关详细信息，请参见[约束](constraints.md)。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-157">For more information, see [Constraints](constraints.md).</span></span>

## <a name="statically-resolved-type-parameters"></a><span data-ttu-id="b1fa5-158">静态解析的类型参数</span><span class="sxs-lookup"><span data-stu-id="b1fa5-158">Statically Resolved Type Parameters</span></span>

<span data-ttu-id="b1fa5-159">有两种可在 F# 程序中使用的类型参数。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-159">There are two kinds of type parameters that can be used in F# programs.</span></span> <span data-ttu-id="b1fa5-160">第一种类型参数是上一部分中描述的那种泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-160">The first are generic type parameters of the kind described in the previous sections.</span></span> <span data-ttu-id="b1fa5-161">这种类型参数等效于在 Visual Basic 和 C# 等语言中使用的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-161">This first kind of type parameter is equivalent to the generic type parameters that are used in languages such as Visual Basic and C#.</span></span> <span data-ttu-id="b1fa5-162">另一种类型参数为 F# 专用，被称为“静态解析的类型参数”。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-162">Another kind of type parameter is specific to F# and is referred to as a *statically resolved type parameter*.</span></span> <span data-ttu-id="b1fa5-163">有关这些构造的信息，请参阅[静态解析的类型参数](statically-resolved-type-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="b1fa5-163">For information about these constructs, see [Statically Resolved Type Parameters](statically-resolved-type-parameters.md).</span></span>

## <a name="examples"></a><span data-ttu-id="b1fa5-164">示例</span><span class="sxs-lookup"><span data-stu-id="b1fa5-164">Examples</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1705.fs)]

## <a name="see-also"></a><span data-ttu-id="b1fa5-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1fa5-165">See also</span></span>

- [<span data-ttu-id="b1fa5-166">语言参考</span><span class="sxs-lookup"><span data-stu-id="b1fa5-166">Language Reference</span></span>](../index.md)
- [<span data-ttu-id="b1fa5-167">类型</span><span class="sxs-lookup"><span data-stu-id="b1fa5-167">Types</span></span>](../fsharp-types.md)
- [<span data-ttu-id="b1fa5-168">静态解析的类型参数</span><span class="sxs-lookup"><span data-stu-id="b1fa5-168">Statically Resolved Type Parameters</span></span>](statically-resolved-type-parameters.md)
- [<span data-ttu-id="b1fa5-169">.NET Framework 中的泛型</span><span class="sxs-lookup"><span data-stu-id="b1fa5-169">Generics in the .NET Framework</span></span>](~/docs/standard/generics/index.md)
- [<span data-ttu-id="b1fa5-170">自动泛化</span><span class="sxs-lookup"><span data-stu-id="b1fa5-170">Automatic Generalization</span></span>](automatic-generalization.md)
- [<span data-ttu-id="b1fa5-171">约束</span><span class="sxs-lookup"><span data-stu-id="b1fa5-171">Constraints</span></span>](constraints.md)
