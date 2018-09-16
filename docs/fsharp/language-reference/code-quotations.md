---
title: 代码引用 (F#)
description: '了解有关 F # 的代码引号，一种语言功能，可用于生成和以编程方式使用 F # 代码表达式。'
ms.date: 05/16/2016
ms.openlocfilehash: 27e9cf1d99e2b5955cc6359653fc87bdbe824cc7
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45666715"
---
# <a name="code-quotations"></a><span data-ttu-id="bbff7-103">代码引用</span><span class="sxs-lookup"><span data-stu-id="bbff7-103">Code Quotations</span></span>

> [!NOTE]
<span data-ttu-id="bbff7-104">API 参考链接将转至 MSDN。</span><span class="sxs-lookup"><span data-stu-id="bbff7-104">The API reference link will take you to MSDN.</span></span>  <span data-ttu-id="bbff7-105">Docs.microsoft.com API 参考尚未完成。</span><span class="sxs-lookup"><span data-stu-id="bbff7-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="bbff7-106">本主题介绍*代码引用*，一种语言功能，可用于生成和以编程方式使用 F # 代码表达式。</span><span class="sxs-lookup"><span data-stu-id="bbff7-106">This topic describes *code quotations*, a language feature that enables you to generate and work with F# code expressions programmatically.</span></span> <span data-ttu-id="bbff7-107">此功能允许您生成一个表示 F # 代码的抽象语法树。</span><span class="sxs-lookup"><span data-stu-id="bbff7-107">This feature lets you generate an abstract syntax tree that represents F# code.</span></span> <span data-ttu-id="bbff7-108">然后可以遍历并根据应用程序需要处理的抽象语法树。</span><span class="sxs-lookup"><span data-stu-id="bbff7-108">The abstract syntax tree can then be traversed and processed according to the needs of your application.</span></span> <span data-ttu-id="bbff7-109">例如，可以使用树来生成 F # 代码或一些其他语言生成代码。</span><span class="sxs-lookup"><span data-stu-id="bbff7-109">For example, you can use the tree to generate F# code or generate code in some other language.</span></span>

## <a name="quoted-expressions"></a><span data-ttu-id="bbff7-110">带引号的表达式</span><span class="sxs-lookup"><span data-stu-id="bbff7-110">Quoted Expressions</span></span>

<span data-ttu-id="bbff7-111">一个*带引号的表达式*是 F # 表达式在代码中的分隔方式作为应用程序的一部分不编译，但被编译为一个对象，表示 F # 表达式。</span><span class="sxs-lookup"><span data-stu-id="bbff7-111">A *quoted expression* is an F# expression in your code that is delimited in such a way that it is not compiled as part of your program, but instead is compiled into an object that represents an F# expression.</span></span> <span data-ttu-id="bbff7-112">您可以将标记引用的表达式有两种： 使用类型信息或不带类型信息。</span><span class="sxs-lookup"><span data-stu-id="bbff7-112">You can mark a quoted expression in one of two ways: either with type information or without type information.</span></span> <span data-ttu-id="bbff7-113">如果你想要包括类型信息，则使用符号`<@`和`@>`来分隔带引号的表达式。</span><span class="sxs-lookup"><span data-stu-id="bbff7-113">If you want to include type information, you use the symbols `<@` and `@>` to delimit the quoted expression.</span></span> <span data-ttu-id="bbff7-114">如果不需要类型信息，则使用符号`<@@`和`@@>`。</span><span class="sxs-lookup"><span data-stu-id="bbff7-114">If you do not need type information, you use the symbols `<@@` and `@@>`.</span></span> <span data-ttu-id="bbff7-115">下面的代码显示了类型化和非类型化引用。</span><span class="sxs-lookup"><span data-stu-id="bbff7-115">The following code shows typed and untyped quotations.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

<span data-ttu-id="bbff7-116">遍历一个大型的表达式树速度更快，如果不包括类型信息。</span><span class="sxs-lookup"><span data-stu-id="bbff7-116">Traversing a large expression tree is faster if you do not include type information.</span></span> <span data-ttu-id="bbff7-117">带引号的使用类型化的符号的表达式的结果类型是`Expr<'T>`，其中类型参数都有由 F # 编译器的类型推断算法确定表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="bbff7-117">The resulting type of an expression quoted with the typed symbols is `Expr<'T>`, where the type parameter has the type of the expression as determined by the F# compiler's type inference algorithm.</span></span> <span data-ttu-id="bbff7-118">当使用不含类型信息的代码引用时，带引号的表达式的类型为非泛型类型[Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65)。</span><span class="sxs-lookup"><span data-stu-id="bbff7-118">When you use code quotations without type information, the type of the quoted expression is the non-generic type [Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65).</span></span> <span data-ttu-id="bbff7-119">您可以调用[Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2)属性的类型化`Expr`类来获取的非类型化`Expr`对象。</span><span class="sxs-lookup"><span data-stu-id="bbff7-119">You can call the [Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) property on the typed `Expr` class to obtain the untyped `Expr` object.</span></span>

<span data-ttu-id="bbff7-120">有多种静态方法，可用于生成 F # 表达式对象中以编程方式`Expr`类，而无需使用带引号的表达式。</span><span class="sxs-lookup"><span data-stu-id="bbff7-120">There are a variety of static methods that allow you to generate F# expression objects programmatically in the `Expr` class without using quoted expressions.</span></span>

<span data-ttu-id="bbff7-121">请注意，代码引号必须包含完整的表达式。</span><span class="sxs-lookup"><span data-stu-id="bbff7-121">Note that a code quotation must include a complete expression.</span></span> <span data-ttu-id="bbff7-122">有关`let`绑定，例如，您需要定义绑定的名称和使用该绑定的其他表达式。</span><span class="sxs-lookup"><span data-stu-id="bbff7-122">For a `let` binding, for example, you need both the definition of the bound name and an additional expression that uses the binding.</span></span> <span data-ttu-id="bbff7-123">在详细语法中，这是一个表达式，遵循`in`关键字。</span><span class="sxs-lookup"><span data-stu-id="bbff7-123">In verbose syntax, this is an expression that follows the `in` keyword.</span></span> <span data-ttu-id="bbff7-124">在顶级模块中，这是只需在模块中下, 一个表达式，但在报价，它是明确要求。</span><span class="sxs-lookup"><span data-stu-id="bbff7-124">At the top-level in a module, this is just the next expression in the module, but in a quotation, it is explicitly required.</span></span>

<span data-ttu-id="bbff7-125">因此，下面的表达式不是有效的。</span><span class="sxs-lookup"><span data-stu-id="bbff7-125">Therefore, the following expression is not valid.</span></span>

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

<span data-ttu-id="bbff7-126">但以下表达式是有效的。</span><span class="sxs-lookup"><span data-stu-id="bbff7-126">But the following expressions are valid.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

<span data-ttu-id="bbff7-127">若要使用的代码引用，必须添加导入声明 (使用`open`关键字)，用于在打开[Microsoft.FSharp.Quotations](https://msdn.microsoft.com/library/e9ce8a3a-e00c-4190-bad5-cce52ee089b2)命名空间。</span><span class="sxs-lookup"><span data-stu-id="bbff7-127">To use code quotations, you must add an import declaration (by using the `open` keyword) that opens the [Microsoft.FSharp.Quotations](https://msdn.microsoft.com/library/e9ce8a3a-e00c-4190-bad5-cce52ee089b2) namespace.</span></span>

<span data-ttu-id="bbff7-128">F # PowerPack 提供支持，用于计算和执行 F # 表达式对象。</span><span class="sxs-lookup"><span data-stu-id="bbff7-128">The F# PowerPack provides support for evaluating and executing F# expression objects.</span></span>

## <a name="expr-type"></a><span data-ttu-id="bbff7-129">Expr 类型</span><span class="sxs-lookup"><span data-stu-id="bbff7-129">Expr Type</span></span>

<span data-ttu-id="bbff7-130">实例`Expr`类型表示的 F # 表达式。</span><span class="sxs-lookup"><span data-stu-id="bbff7-130">An instance of the `Expr` type represents an F# expression.</span></span> <span data-ttu-id="bbff7-131">泛型和非泛型`Expr`类型均记录在 F # 库文档。</span><span class="sxs-lookup"><span data-stu-id="bbff7-131">Both the generic and the non-generic `Expr` types are documented in the F# library documentation.</span></span> <span data-ttu-id="bbff7-132">有关详细信息，请参阅[Microsoft.FSharp.Quotations Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d)并[Quotations.Expr 类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d)。</span><span class="sxs-lookup"><span data-stu-id="bbff7-132">For more information, see [Microsoft.FSharp.Quotations Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) and [Quotations.Expr Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d).</span></span>

## <a name="splicing-operators"></a><span data-ttu-id="bbff7-133">拼接运算符</span><span class="sxs-lookup"><span data-stu-id="bbff7-133">Splicing Operators</span></span>

<span data-ttu-id="bbff7-134">拼接可以合并使用而创建了以编程方式或从另一个代码引用的表达式的原义代码引用。</span><span class="sxs-lookup"><span data-stu-id="bbff7-134">Splicing enables you to combine literal code quotations with expressions that you have created programmatically or from another code quotation.</span></span> <span data-ttu-id="bbff7-135">`%`和`%%`运算符，您可以将 F # 表达式对象添加到代码引号。</span><span class="sxs-lookup"><span data-stu-id="bbff7-135">The `%` and `%%` operators enable you to add an F# expression object into a code quotation.</span></span> <span data-ttu-id="bbff7-136">您使用`%`运算符将类型化的表达式对象插入类型化引起来; 您可以使用`%%`运算符以将非类型化的表达式对象插入非类型化引起来。</span><span class="sxs-lookup"><span data-stu-id="bbff7-136">You use the `%` operator to insert a typed expression object into a typed quotation; you use the `%%` operator to insert an untyped expression object into an untyped quotation.</span></span> <span data-ttu-id="bbff7-137">这两个运算符是一元前缀运算符。</span><span class="sxs-lookup"><span data-stu-id="bbff7-137">Both operators are unary prefix operators.</span></span> <span data-ttu-id="bbff7-138">因此如果`expr`类型的非类型化表达式`Expr`，以下代码是有效的。</span><span class="sxs-lookup"><span data-stu-id="bbff7-138">Thus if `expr` is an untyped expression of type `Expr`, the following code is valid.</span></span>

```fsharp
<@@ 1 + %%expr @@>
```

<span data-ttu-id="bbff7-139">如果`expr`是类型化的引用`Expr<int>`，以下代码是有效的。</span><span class="sxs-lookup"><span data-stu-id="bbff7-139">And if `expr` is a typed quotation of type `Expr<int>`, the following code is valid.</span></span>

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a><span data-ttu-id="bbff7-140">示例</span><span class="sxs-lookup"><span data-stu-id="bbff7-140">Example</span></span>

### <a name="description"></a><span data-ttu-id="bbff7-141">描述</span><span class="sxs-lookup"><span data-stu-id="bbff7-141">Description</span></span>

<span data-ttu-id="bbff7-142">下面的示例演示如何使用代码引用放入表达式对象的 F # 代码，然后打印表示表达式的 F # 代码。</span><span class="sxs-lookup"><span data-stu-id="bbff7-142">The following example illustrates the use of code quotations to put F# code into an expression object and then print the F# code that represents the expression.</span></span> <span data-ttu-id="bbff7-143">一个函数`println`定义包含递归函数`print`显示 F # 表达式对象 (类型的`Expr`) 以友好格式。</span><span class="sxs-lookup"><span data-stu-id="bbff7-143">A function `println` is defined that contains a recursive function `print` that displays an F# expression object (of type `Expr`) in a friendly format.</span></span> <span data-ttu-id="bbff7-144">有几种活动模式在[Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4)并[Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd)模块，它们可以用于分析表达式对象。</span><span class="sxs-lookup"><span data-stu-id="bbff7-144">There are several active patterns in the [Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) and [Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) modules that can be used to analyze expression objects.</span></span> <span data-ttu-id="bbff7-145">此示例不包括在 F # 表达式中可能会出现的所有可能的模式。</span><span class="sxs-lookup"><span data-stu-id="bbff7-145">This example does not include all the possible patterns that might appear in an F# expression.</span></span> <span data-ttu-id="bbff7-146">任何无法识别的模式将触发与通配符模式匹配的项 (`_`) 和通过使用呈现`ToString`方法，而后者在`Expr`类型，可以知道要向匹配表达式中添加的活动模式。</span><span class="sxs-lookup"><span data-stu-id="bbff7-146">Any unrecognized pattern triggers a match to the wildcard pattern (`_`) and is rendered by using the `ToString` method, which, on the `Expr` type, lets you know the active pattern to add to your match expression.</span></span>

### <a name="code"></a><span data-ttu-id="bbff7-147">代码</span><span class="sxs-lookup"><span data-stu-id="bbff7-147">Code</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a><span data-ttu-id="bbff7-148">输出</span><span class="sxs-lookup"><span data-stu-id="bbff7-148">Output</span></span>

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a><span data-ttu-id="bbff7-149">示例</span><span class="sxs-lookup"><span data-stu-id="bbff7-149">Example</span></span>

### <a name="description"></a><span data-ttu-id="bbff7-150">描述</span><span class="sxs-lookup"><span data-stu-id="bbff7-150">Description</span></span>

<span data-ttu-id="bbff7-151">此外可以使用中的三个活动模式[ExprShape 模块](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de)遍历表达式树，使用更少的活动模式。</span><span class="sxs-lookup"><span data-stu-id="bbff7-151">You can also use the three active patterns in the [ExprShape module](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) to traverse expression trees with fewer active patterns.</span></span> <span data-ttu-id="bbff7-152">如果想要遍历树，但不是需要大多数节点中的所有信息，这些活动模式会很有用。</span><span class="sxs-lookup"><span data-stu-id="bbff7-152">These active patterns can be useful when you want to traverse a tree but you do not need all the information in most of the nodes.</span></span> <span data-ttu-id="bbff7-153">任何 F # 表达式时使用这些模式，与以下三种模式之一匹配：`ShapeVar`表达式是一个变量，如果`ShapeLambda`如果表达式为 lambda 表达式或`ShapeCombination`如果表达式为任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="bbff7-153">When you use these patterns, any F# expression matches one of the following three patterns: `ShapeVar` if the expression is a variable, `ShapeLambda` if the expression is a lambda expression, or `ShapeCombination` if the expression is anything else.</span></span> <span data-ttu-id="bbff7-154">如果通过使用如前面的代码示例中所示的活动模式遍历表达式树，必须为使用更多的模式来处理所有可能的 F # 表达式类型，并且你的代码将会更加复杂。</span><span class="sxs-lookup"><span data-stu-id="bbff7-154">If you traverse an expression tree by using the active patterns as in the previous code example, you have to use many more patterns to handle all possible F# expression types, and your code will be more complex.</span></span> <span data-ttu-id="bbff7-155">有关详细信息，请参阅[ExprShape.ShapeVar&#124;ShapeLambda&#124;ShapeCombination 活动模式](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d)。</span><span class="sxs-lookup"><span data-stu-id="bbff7-155">For more information, see [ExprShape.ShapeVar&#124;ShapeLambda&#124;ShapeCombination Active Pattern](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d).</span></span>

<span data-ttu-id="bbff7-156">下面的代码示例可以用作更复杂的遍历基础。</span><span class="sxs-lookup"><span data-stu-id="bbff7-156">The following code example can be used as a basis for more complex traversals.</span></span> <span data-ttu-id="bbff7-157">在此代码中，为涉及函数调用的表达式创建表达式树`add`。</span><span class="sxs-lookup"><span data-stu-id="bbff7-157">In this code, an expression tree is created for an expression that involves a function call, `add`.</span></span> <span data-ttu-id="bbff7-158">[SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d)活动的模式用于检测到的任何调用`add`表达式树中。</span><span class="sxs-lookup"><span data-stu-id="bbff7-158">The [SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) active pattern is used to detect any call to `add` in the expression tree.</span></span> <span data-ttu-id="bbff7-159">此活动的模式将分配到调用的参数`exprList`值。</span><span class="sxs-lookup"><span data-stu-id="bbff7-159">This active pattern assigns the arguments of the call to the `exprList` value.</span></span> <span data-ttu-id="bbff7-160">在这种情况下，有只有两种，因此这些拉出且对自变量以递归方式调用该函数。</span><span class="sxs-lookup"><span data-stu-id="bbff7-160">In this case, there are only two, so these are pulled out and the function is called recursively on the arguments.</span></span> <span data-ttu-id="bbff7-161">结果插入到表示对的调用的代码引用`mul`通过使用接合运算符 (`%%`)。</span><span class="sxs-lookup"><span data-stu-id="bbff7-161">The results are inserted into a code quotation that represents a call to `mul` by using the splice operator (`%%`).</span></span> <span data-ttu-id="bbff7-162">`println`上一示例中的函数用于显示结果。</span><span class="sxs-lookup"><span data-stu-id="bbff7-162">The `println` function from the previous example is used to display the results.</span></span>

<span data-ttu-id="bbff7-163">其他活动的模式分支中的代码只是重新生成相同的表达式树，因此所生成的表达式中的唯一更改是从更改`add`到`mul`。</span><span class="sxs-lookup"><span data-stu-id="bbff7-163">The code in the other active pattern branches just regenerates the same expression tree, so the only change in the resulting expression is the change from `add` to `mul`.</span></span>

### <a name="code"></a><span data-ttu-id="bbff7-164">代码</span><span class="sxs-lookup"><span data-stu-id="bbff7-164">Code</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a><span data-ttu-id="bbff7-165">输出</span><span class="sxs-lookup"><span data-stu-id="bbff7-165">Output</span></span>

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a><span data-ttu-id="bbff7-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbff7-166">See also</span></span>

- [<span data-ttu-id="bbff7-167">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="bbff7-167">F# Language Reference</span></span>](index.md)
