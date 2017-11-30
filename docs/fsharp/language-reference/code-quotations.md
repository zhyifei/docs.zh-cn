---
title: "代码引用 (F#)"
description: "了解有关 F # 代码引用，使你可以生成并以编程方式使用 F # 的代码表达式的语言功能。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4559e659-2b04-48bd-8a0b-8527920eec95
ms.openlocfilehash: f7a08013bc6487b570a62576bb01ca2dd65ce8b1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="code-quotations"></a><span data-ttu-id="2af24-104">代码引用</span><span class="sxs-lookup"><span data-stu-id="2af24-104">Code Quotations</span></span>

> [!NOTE]
<span data-ttu-id="2af24-105">API 参考链接将转至 MSDN。</span><span class="sxs-lookup"><span data-stu-id="2af24-105">The API reference link will take you to MSDN.</span></span>  <span data-ttu-id="2af24-106">Docs.microsoft.com API 参考尚未完成。</span><span class="sxs-lookup"><span data-stu-id="2af24-106">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="2af24-107">本主题介绍*代码引用*，使你可以生成并以编程方式使用 F # 的代码表达式的语言功能。</span><span class="sxs-lookup"><span data-stu-id="2af24-107">This topic describes *code quotations*, a language feature that enables you to generate and work with F# code expressions programmatically.</span></span> <span data-ttu-id="2af24-108">此功能允许你生成一个表示 F # 代码的抽象语法树。</span><span class="sxs-lookup"><span data-stu-id="2af24-108">This feature lets you generate an abstract syntax tree that represents F# code.</span></span> <span data-ttu-id="2af24-109">可以然后遍历抽象语法树，并为其根据你的应用程序的需要处理。</span><span class="sxs-lookup"><span data-stu-id="2af24-109">The abstract syntax tree can then be traversed and processed according to the needs of your application.</span></span> <span data-ttu-id="2af24-110">例如，可以使用树来生成 F # 代码，或者某些其他语言生成代码。</span><span class="sxs-lookup"><span data-stu-id="2af24-110">For example, you can use the tree to generate F# code or generate code in some other language.</span></span>


## <a name="quoted-expressions"></a><span data-ttu-id="2af24-111">用引号括起来的表达式</span><span class="sxs-lookup"><span data-stu-id="2af24-111">Quoted Expressions</span></span>
<span data-ttu-id="2af24-112">A*带引号的表达式*是在代码中分隔它未编译的程序中，一部分的方式，但会编译成一个对象，表示 F # 表达式的 F # 表达式。</span><span class="sxs-lookup"><span data-stu-id="2af24-112">A *quoted expression* is an F# expression in your code that is delimited in such a way that it is not compiled as part of your program, but instead is compiled into an object that represents an F# expression.</span></span> <span data-ttu-id="2af24-113">你可以将标记的表达式用引号括起来的两种方式之一： 使用类型信息或没有类型信息。</span><span class="sxs-lookup"><span data-stu-id="2af24-113">You can mark a quoted expression in one of two ways: either with type information or without type information.</span></span> <span data-ttu-id="2af24-114">如果你想要包括类型信息，则使用符号`<@`和`@>`来分隔用引号括起来的表达式。</span><span class="sxs-lookup"><span data-stu-id="2af24-114">If you want to include type information, you use the symbols `<@` and `@>` to delimit the quoted expression.</span></span> <span data-ttu-id="2af24-115">如果不需要类型信息，则使用符号`<@@`和`@@>`。</span><span class="sxs-lookup"><span data-stu-id="2af24-115">If you do not need type information, you use the symbols `<@@` and `@@>`.</span></span> <span data-ttu-id="2af24-116">下面的代码演示了类型化和非类型化的引用。</span><span class="sxs-lookup"><span data-stu-id="2af24-116">The following code shows typed and untyped quotations.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

<span data-ttu-id="2af24-117">大型表达式树的遍历是不包括类型信息的情况下更快。</span><span class="sxs-lookup"><span data-stu-id="2af24-117">Traversing a large expression tree is faster if you do not include type information.</span></span> <span data-ttu-id="2af24-118">使用类型化的符号引起来的表达式的结果类型是`Expr<'T>`，其中类型参数都有由 F # 编译器的类型推理算法确定表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="2af24-118">The resulting type of an expression quoted with the typed symbols is `Expr<'T>`, where the type parameter has the type of the expression as determined by the F# compiler's type inference algorithm.</span></span> <span data-ttu-id="2af24-119">当使用不包含类型信息的代码引用时，用引号括起来的表达式的类型为非泛型类型[Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65)。</span><span class="sxs-lookup"><span data-stu-id="2af24-119">When you use code quotations without type information, the type of the quoted expression is the non-generic type [Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65).</span></span> <span data-ttu-id="2af24-120">你可以调用[Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2)上类型化的属性`Expr`类来获取的非类型化`Expr`对象。</span><span class="sxs-lookup"><span data-stu-id="2af24-120">You can call the [Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) property on the typed `Expr` class to obtain the untyped `Expr` object.</span></span>

<span data-ttu-id="2af24-121">有大量的静态方法可让你可以生成 F # 表达式对象以编程方式在`Expr`类而不使用带引号的表达式。</span><span class="sxs-lookup"><span data-stu-id="2af24-121">There are a variety of static methods that allow you to generate F# expression objects programmatically in the `Expr` class without using quoted expressions.</span></span>

<span data-ttu-id="2af24-122">请注意，代码引号必须包含一个完整的表达式。</span><span class="sxs-lookup"><span data-stu-id="2af24-122">Note that a code quotation must include a complete expression.</span></span> <span data-ttu-id="2af24-123">有关`let`绑定，例如，你需要定义的绑定的名称和其他表达式使用的绑定。</span><span class="sxs-lookup"><span data-stu-id="2af24-123">For a `let` binding, for example, you need both the definition of the bound name and an additional expression that uses the binding.</span></span> <span data-ttu-id="2af24-124">在详细语法中，这是一个表达式后面`in`关键字。</span><span class="sxs-lookup"><span data-stu-id="2af24-124">In verbose syntax, this is an expression that follows the `in` keyword.</span></span> <span data-ttu-id="2af24-125">在顶级模块中，这是仅在模块中下, 一个表达式，但在引号中，它是明确要求。</span><span class="sxs-lookup"><span data-stu-id="2af24-125">At the top-level in a module, this is just the next expression in the module, but in a quotation, it is explicitly required.</span></span>

<span data-ttu-id="2af24-126">因此，下面的表达式不是有效的。</span><span class="sxs-lookup"><span data-stu-id="2af24-126">Therefore, the following expression is not valid.</span></span>

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

<span data-ttu-id="2af24-127">但是，以下表达式均无效。</span><span class="sxs-lookup"><span data-stu-id="2af24-127">But the following expressions are valid.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

<span data-ttu-id="2af24-128">若要使用代码引用，必须添加导入声明 (使用`open`关键字)，这将打开[Microsoft.FSharp.Quotations](https://msdn.microsoft.com/library/e9ce8a3a-e00c-4190-bad5-cce52ee089b2)命名空间。</span><span class="sxs-lookup"><span data-stu-id="2af24-128">To use code quotations, you must add an import declaration (by using the `open` keyword) that opens the [Microsoft.FSharp.Quotations](https://msdn.microsoft.com/library/e9ce8a3a-e00c-4190-bad5-cce52ee089b2) namespace.</span></span>

<span data-ttu-id="2af24-129">F # PowerPack 评估和执行 F # 表达式对象提供支持。</span><span class="sxs-lookup"><span data-stu-id="2af24-129">The F# PowerPack provides support for evaluating and executing F# expression objects.</span></span>


## <a name="expr-type"></a><span data-ttu-id="2af24-130">Expr 类型</span><span class="sxs-lookup"><span data-stu-id="2af24-130">Expr Type</span></span>
<span data-ttu-id="2af24-131">实例`Expr`类型表示的 F # 表达式。</span><span class="sxs-lookup"><span data-stu-id="2af24-131">An instance of the `Expr` type represents an F# expression.</span></span> <span data-ttu-id="2af24-132">泛型和非泛型`Expr`类型均记录在 F # 库文档。</span><span class="sxs-lookup"><span data-stu-id="2af24-132">Both the generic and the non-generic `Expr` types are documented in the F# library documentation.</span></span> <span data-ttu-id="2af24-133">有关详细信息，请参阅[Microsoft.FSharp.Quotations Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d)和[Quotations.Expr 类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d)。</span><span class="sxs-lookup"><span data-stu-id="2af24-133">For more information, see [Microsoft.FSharp.Quotations Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) and [Quotations.Expr Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d).</span></span>


## <a name="splicing-operators"></a><span data-ttu-id="2af24-134">拼接运算符</span><span class="sxs-lookup"><span data-stu-id="2af24-134">Splicing Operators</span></span>
<span data-ttu-id="2af24-135">将接合允许用户将组合使用您已创建了以编程方式或从另一个代码引用的表达式的文本的代码引用。</span><span class="sxs-lookup"><span data-stu-id="2af24-135">Splicing enables you to combine literal code quotations with expressions that you have created programmatically or from another code quotation.</span></span> <span data-ttu-id="2af24-136">`%`和`%%`运算符使您能够将 F # 表达式对象添加到代码引号。</span><span class="sxs-lookup"><span data-stu-id="2af24-136">The `%` and `%%` operators enable you to add an F# expression object into a code quotation.</span></span> <span data-ttu-id="2af24-137">你使用`%`运算符将类型化的表达式对象插入的类型化的引用; 你可以使用`%%`运算符以将非类型化的表达式对象插入非类型化的引号。</span><span class="sxs-lookup"><span data-stu-id="2af24-137">You use the `%` operator to insert a typed expression object into a typed quotation; you use the `%%` operator to insert an untyped expression object into an untyped quotation.</span></span> <span data-ttu-id="2af24-138">这两个运算符是一元前缀运算符。</span><span class="sxs-lookup"><span data-stu-id="2af24-138">Both operators are unary prefix operators.</span></span> <span data-ttu-id="2af24-139">因此如果`expr`类型的非类型化表达式`Expr`，下面的代码是有效。</span><span class="sxs-lookup"><span data-stu-id="2af24-139">Thus if `expr` is an untyped expression of type `Expr`, the following code is valid.</span></span>

```fsharp
<@@ 1 + %%expr @@>
```

<span data-ttu-id="2af24-140">如果`expr`是类型的类型化的引用`Expr<int>`，下面的代码是有效。</span><span class="sxs-lookup"><span data-stu-id="2af24-140">And if `expr` is a typed quotation of type `Expr<int>`, the following code is valid.</span></span>

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a><span data-ttu-id="2af24-141">示例</span><span class="sxs-lookup"><span data-stu-id="2af24-141">Example</span></span>

### <a name="description"></a><span data-ttu-id="2af24-142">描述</span><span class="sxs-lookup"><span data-stu-id="2af24-142">Description</span></span>
<span data-ttu-id="2af24-143">下面的示例演示如何使用 F # 代码放入到表达式对象，然后打印表示表达式的 F # 代码的代码引用。</span><span class="sxs-lookup"><span data-stu-id="2af24-143">The following example illustrates the use of code quotations to put F# code into an expression object and then print the F# code that represents the expression.</span></span> <span data-ttu-id="2af24-144">函数`println`定义包含递归函数`print`显示 F # 表达式对象 (类型的`Expr`) 中的友好的格式。</span><span class="sxs-lookup"><span data-stu-id="2af24-144">A function `println` is defined that contains a recursive function `print` that displays an F# expression object (of type `Expr`) in a friendly format.</span></span> <span data-ttu-id="2af24-145">有几个活动模式中的[Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4)和[Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd)模块，它们可以用于分析表达式对象。</span><span class="sxs-lookup"><span data-stu-id="2af24-145">There are several active patterns in the [Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) and [Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) modules that can be used to analyze expression objects.</span></span> <span data-ttu-id="2af24-146">此示例不包括在 F # 表达式中可能会出现的所有可能的模式。</span><span class="sxs-lookup"><span data-stu-id="2af24-146">This example does not include all the possible patterns that might appear in an F# expression.</span></span> <span data-ttu-id="2af24-147">任何无法识别的模式将触发与通配符模式匹配的项 (`_`) 并通过使用呈现`ToString`方法，而后者上`Expr`键入，让您知道要将添加到你匹配表达式的活动模式。</span><span class="sxs-lookup"><span data-stu-id="2af24-147">Any unrecognized pattern triggers a match to the wildcard pattern (`_`) and is rendered by using the `ToString` method, which, on the `Expr` type, lets you know the active pattern to add to your match expression.</span></span>


### <a name="code"></a><span data-ttu-id="2af24-148">代码</span><span class="sxs-lookup"><span data-stu-id="2af24-148">Code</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet601.fs)]
    
### <a name="output"></a><span data-ttu-id="2af24-149">输出</span><span class="sxs-lookup"><span data-stu-id="2af24-149">Output</span></span>

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a><span data-ttu-id="2af24-150">示例</span><span class="sxs-lookup"><span data-stu-id="2af24-150">Example</span></span>

### <a name="description"></a><span data-ttu-id="2af24-151">描述</span><span class="sxs-lookup"><span data-stu-id="2af24-151">Description</span></span>
<span data-ttu-id="2af24-152">你还可以使用中的三个活动模式[ExprShape 模块](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de)遍历较少活动模式与表达式树。</span><span class="sxs-lookup"><span data-stu-id="2af24-152">You can also use the three active patterns in the [ExprShape module](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) to traverse expression trees with fewer active patterns.</span></span> <span data-ttu-id="2af24-153">当你想要遍历树，但不是需要其中大部分节点中的所有信息时，这些活动模式很有用。</span><span class="sxs-lookup"><span data-stu-id="2af24-153">These active patterns can be useful when you want to traverse a tree but you do not need all the information in most of the nodes.</span></span> <span data-ttu-id="2af24-154">当你使用这些模式时，任何 F # 表达式匹配的以下三种模式之一：`ShapeVar`如果表达式是一个变量，`ShapeLambda`如果表达式是 lambda 表达式，或`ShapeCombination`如果表达式为任何其他内容。</span><span class="sxs-lookup"><span data-stu-id="2af24-154">When you use these patterns, any F# expression matches one of the following three patterns: `ShapeVar` if the expression is a variable, `ShapeLambda` if the expression is a lambda expression, or `ShapeCombination` if the expression is anything else.</span></span> <span data-ttu-id="2af24-155">如果通过使用如前面的代码示例所示的活动模式遍历表达式树，你需要使用更多的模式来处理所有可能的 F # 表达式类型，并且你的代码将更复杂。</span><span class="sxs-lookup"><span data-stu-id="2af24-155">If you traverse an expression tree by using the active patterns as in the previous code example, you have to use many more patterns to handle all possible F# expression types, and your code will be more complex.</span></span> <span data-ttu-id="2af24-156">有关详细信息，请参阅[ExprShape.ShapeVar &#124;ShapeLambda &#124;ShapeCombination 活动模式](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d)。</span><span class="sxs-lookup"><span data-stu-id="2af24-156">For more information, see [ExprShape.ShapeVar&#124;ShapeLambda&#124;ShapeCombination Active Pattern](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d).</span></span>

<span data-ttu-id="2af24-157">下面的代码示例可以用作更为复杂的遍历基础。</span><span class="sxs-lookup"><span data-stu-id="2af24-157">The following code example can be used as a basis for more complex traversals.</span></span> <span data-ttu-id="2af24-158">在此代码中，为包含函数调用的表达式创建表达式树`add`。</span><span class="sxs-lookup"><span data-stu-id="2af24-158">In this code, an expression tree is created for an expression that involves a function call, `add`.</span></span> <span data-ttu-id="2af24-159">[SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d)活动模式用于检测到任何调用`add`的表达式树中。</span><span class="sxs-lookup"><span data-stu-id="2af24-159">The [SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) active pattern is used to detect any call to `add` in the expression tree.</span></span> <span data-ttu-id="2af24-160">此活动的模式将分配到调用的自变量`exprList`值。</span><span class="sxs-lookup"><span data-stu-id="2af24-160">This active pattern assigns the arguments of the call to the `exprList` value.</span></span> <span data-ttu-id="2af24-161">在这种情况下，有只有两个，因此这些拉出和的自变量以递归方式调用该函数。</span><span class="sxs-lookup"><span data-stu-id="2af24-161">In this case, there are only two, so these are pulled out and the function is called recursively on the arguments.</span></span> <span data-ttu-id="2af24-162">结果插入到表示对的调用的代码引用`mul`使用接合运算符 (`%%`)。</span><span class="sxs-lookup"><span data-stu-id="2af24-162">The results are inserted into a code quotation that represents a call to `mul` by using the splice operator (`%%`).</span></span> <span data-ttu-id="2af24-163">`println`上一示例中的函数用于显示结果。</span><span class="sxs-lookup"><span data-stu-id="2af24-163">The `println` function from the previous example is used to display the results.</span></span>

<span data-ttu-id="2af24-164">其他活动模式分支中的代码只是重新生成相同的表达式树，因此生成的表达式中的唯一更改是从更改`add`到`mul`。</span><span class="sxs-lookup"><span data-stu-id="2af24-164">The code in the other active pattern branches just regenerates the same expression tree, so the only change in the resulting expression is the change from `add` to `mul`.</span></span>


### <a name="code"></a><span data-ttu-id="2af24-165">代码</span><span class="sxs-lookup"><span data-stu-id="2af24-165">Code</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet701.fs)]
    
### <a name="output"></a><span data-ttu-id="2af24-166">输出</span><span class="sxs-lookup"><span data-stu-id="2af24-166">Output</span></span>

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a><span data-ttu-id="2af24-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2af24-167">See Also</span></span>
[<span data-ttu-id="2af24-168">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="2af24-168">F# Language Reference</span></span>](index.md)

