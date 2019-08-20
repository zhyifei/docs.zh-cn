---
title: 代码引用
description: 了解F#代码引用, 它是一种语言功能, 可用于以编程方式F#生成和使用代码表达式。
ms.date: 05/16/2016
ms.openlocfilehash: c6ec0078c685a6452f49edd289b01491dd62e3db
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630413"
---
# <a name="code-quotations"></a><span data-ttu-id="41858-103">代码引用</span><span class="sxs-lookup"><span data-stu-id="41858-103">Code Quotations</span></span>

> [!NOTE]
> <span data-ttu-id="41858-104">API 参考链接将转至 MSDN。</span><span class="sxs-lookup"><span data-stu-id="41858-104">The API reference link will take you to MSDN.</span></span>  <span data-ttu-id="41858-105">Docs.microsoft.com API 参考尚未完成。</span><span class="sxs-lookup"><span data-stu-id="41858-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="41858-106">本主题介绍*代码引用*, 它是一种语言功能, 可用于以编程F#方式生成和使用代码表达式。</span><span class="sxs-lookup"><span data-stu-id="41858-106">This topic describes *code quotations*, a language feature that enables you to generate and work with F# code expressions programmatically.</span></span> <span data-ttu-id="41858-107">利用此功能, 您可以生成一个表示F#代码的抽象语法树。</span><span class="sxs-lookup"><span data-stu-id="41858-107">This feature lets you generate an abstract syntax tree that represents F# code.</span></span> <span data-ttu-id="41858-108">然后, 可以根据应用程序的需要遍历和处理抽象语法树。</span><span class="sxs-lookup"><span data-stu-id="41858-108">The abstract syntax tree can then be traversed and processed according to the needs of your application.</span></span> <span data-ttu-id="41858-109">例如, 您可以使用树生成F#代码或以某种其他语言生成代码。</span><span class="sxs-lookup"><span data-stu-id="41858-109">For example, you can use the tree to generate F# code or generate code in some other language.</span></span>

## <a name="quoted-expressions"></a><span data-ttu-id="41858-110">带引号的表达式</span><span class="sxs-lookup"><span data-stu-id="41858-110">Quoted Expressions</span></span>

<span data-ttu-id="41858-111">*带引号的表达式*是F#代码中的一个表达式, 它以不作为程序的一部分进行编译, 而是编译为表示F#表达式的对象。</span><span class="sxs-lookup"><span data-stu-id="41858-111">A *quoted expression* is an F# expression in your code that is delimited in such a way that it is not compiled as part of your program, but instead is compiled into an object that represents an F# expression.</span></span> <span data-ttu-id="41858-112">可以通过以下两种方式之一来标记带引号的表达式: 使用类型信息或不包含类型信息。</span><span class="sxs-lookup"><span data-stu-id="41858-112">You can mark a quoted expression in one of two ways: either with type information or without type information.</span></span> <span data-ttu-id="41858-113">如果要包括类型信息, 请使用符号`<@`并`@>`分隔带引号的表达式。</span><span class="sxs-lookup"><span data-stu-id="41858-113">If you want to include type information, you use the symbols `<@` and `@>` to delimit the quoted expression.</span></span> <span data-ttu-id="41858-114">如果不需要类型信息, 则使用符号`<@@`和。 `@@>`</span><span class="sxs-lookup"><span data-stu-id="41858-114">If you do not need type information, you use the symbols `<@@` and `@@>`.</span></span> <span data-ttu-id="41858-115">下面的代码显示类型化和非类型化的引用。</span><span class="sxs-lookup"><span data-stu-id="41858-115">The following code shows typed and untyped quotations.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

<span data-ttu-id="41858-116">如果不包含类型信息, 遍历大型表达式树的速度将更快。</span><span class="sxs-lookup"><span data-stu-id="41858-116">Traversing a large expression tree is faster if you do not include type information.</span></span> <span data-ttu-id="41858-117">使用类型化符号括起来的表达式的结果类型为`Expr<'T>`, 其中类型参数具有由F#编译器的类型推理算法确定的表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="41858-117">The resulting type of an expression quoted with the typed symbols is `Expr<'T>`, where the type parameter has the type of the expression as determined by the F# compiler's type inference algorithm.</span></span> <span data-ttu-id="41858-118">使用不带类型信息的代码引用时, 带引号的表达式的类型为非泛型类型[Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65)。</span><span class="sxs-lookup"><span data-stu-id="41858-118">When you use code quotations without type information, the type of the quoted expression is the non-generic type [Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65).</span></span> <span data-ttu-id="41858-119">可以调用类型化[Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) `Expr`类的原始属性来获取非类型化`Expr`对象。</span><span class="sxs-lookup"><span data-stu-id="41858-119">You can call the [Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) property on the typed `Expr` class to obtain the untyped `Expr` object.</span></span>

<span data-ttu-id="41858-120">有多种静态方法可让你在F# `Expr`类中以编程方式生成表达式对象, 而无需使用带引号的表达式。</span><span class="sxs-lookup"><span data-stu-id="41858-120">There are a variety of static methods that allow you to generate F# expression objects programmatically in the `Expr` class without using quoted expressions.</span></span>

<span data-ttu-id="41858-121">请注意, 代码引号必须包含完整的表达式。</span><span class="sxs-lookup"><span data-stu-id="41858-121">Note that a code quotation must include a complete expression.</span></span> <span data-ttu-id="41858-122">例如, 对于绑定, 需要绑定名称和使用绑定的其他表达式的定义。 `let`</span><span class="sxs-lookup"><span data-stu-id="41858-122">For a `let` binding, for example, you need both the definition of the bound name and an additional expression that uses the binding.</span></span> <span data-ttu-id="41858-123">在详细语法中, 这是跟在`in`关键字后面的表达式。</span><span class="sxs-lookup"><span data-stu-id="41858-123">In verbose syntax, this is an expression that follows the `in` keyword.</span></span> <span data-ttu-id="41858-124">在模块的顶层, 这只是模块中的下一个表达式, 但在引号中, 它是显式必需的。</span><span class="sxs-lookup"><span data-stu-id="41858-124">At the top-level in a module, this is just the next expression in the module, but in a quotation, it is explicitly required.</span></span>

<span data-ttu-id="41858-125">因此, 下面的表达式无效。</span><span class="sxs-lookup"><span data-stu-id="41858-125">Therefore, the following expression is not valid.</span></span>

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

<span data-ttu-id="41858-126">但下面的表达式是有效的。</span><span class="sxs-lookup"><span data-stu-id="41858-126">But the following expressions are valid.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

<span data-ttu-id="41858-127">若要F#评估报价, 必须使用[ F#引号计算器](https://github.com/fsprojects/FSharp.Quotations.Evaluator)。</span><span class="sxs-lookup"><span data-stu-id="41858-127">To evaluate F# quotations, you must use the [F# Quotation Evaluator](https://github.com/fsprojects/FSharp.Quotations.Evaluator).</span></span> <span data-ttu-id="41858-128">它提供对计算和执行F#表达式对象的支持。</span><span class="sxs-lookup"><span data-stu-id="41858-128">It provides support for evaluating and executing F# expression objects.</span></span>

## <a name="expr-type"></a><span data-ttu-id="41858-129">Expr 类型</span><span class="sxs-lookup"><span data-stu-id="41858-129">Expr Type</span></span>

<span data-ttu-id="41858-130">`Expr`类型的实例表示F#表达式。</span><span class="sxs-lookup"><span data-stu-id="41858-130">An instance of the `Expr` type represents an F# expression.</span></span> <span data-ttu-id="41858-131">库文档中记录了泛型和非`Expr`泛型类型。 F#</span><span class="sxs-lookup"><span data-stu-id="41858-131">Both the generic and the non-generic `Expr` types are documented in the F# library documentation.</span></span> <span data-ttu-id="41858-132">有关详细信息, 请参阅[Fsharp.core 命名空间](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d)和[引号。](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d)</span><span class="sxs-lookup"><span data-stu-id="41858-132">For more information, see [Microsoft.FSharp.Quotations Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) and [Quotations.Expr Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d).</span></span>

## <a name="splicing-operators"></a><span data-ttu-id="41858-133">拼接运算符</span><span class="sxs-lookup"><span data-stu-id="41858-133">Splicing Operators</span></span>

<span data-ttu-id="41858-134">拼接使你能够将文本代码引用与你以编程方式或从其他代码引用创建的表达式组合在一起。</span><span class="sxs-lookup"><span data-stu-id="41858-134">Splicing enables you to combine literal code quotations with expressions that you have created programmatically or from another code quotation.</span></span> <span data-ttu-id="41858-135">使用`%`和`%%`运算符可以将F#表达式对象添加到代码引用中。</span><span class="sxs-lookup"><span data-stu-id="41858-135">The `%` and `%%` operators enable you to add an F# expression object into a code quotation.</span></span> <span data-ttu-id="41858-136">使用`%`运算符将类型化表达式对象插入类型化的引用中; `%%`使用运算符将非类型化的表达式对象插入非类型化的引用。</span><span class="sxs-lookup"><span data-stu-id="41858-136">You use the `%` operator to insert a typed expression object into a typed quotation; you use the `%%` operator to insert an untyped expression object into an untyped quotation.</span></span> <span data-ttu-id="41858-137">这两个运算符均为一元前缀运算符。</span><span class="sxs-lookup"><span data-stu-id="41858-137">Both operators are unary prefix operators.</span></span> <span data-ttu-id="41858-138">因此, `expr`如果是类型`Expr`的非类型化表达式, 以下代码是有效的。</span><span class="sxs-lookup"><span data-stu-id="41858-138">Thus if `expr` is an untyped expression of type `Expr`, the following code is valid.</span></span>

```fsharp
<@@ 1 + %%expr @@>
```

<span data-ttu-id="41858-139">如果`expr`是类型`Expr<int>`的类型化的引号, 则以下代码有效。</span><span class="sxs-lookup"><span data-stu-id="41858-139">And if `expr` is a typed quotation of type `Expr<int>`, the following code is valid.</span></span>

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a><span data-ttu-id="41858-140">示例</span><span class="sxs-lookup"><span data-stu-id="41858-140">Example</span></span>

### <a name="description"></a><span data-ttu-id="41858-141">描述</span><span class="sxs-lookup"><span data-stu-id="41858-141">Description</span></span>

<span data-ttu-id="41858-142">下面的示例演示如何使用代码引用将代码放F#入 expression 对象, 然后打印表示该表达式F#的代码。</span><span class="sxs-lookup"><span data-stu-id="41858-142">The following example illustrates the use of code quotations to put F# code into an expression object and then print the F# code that represents the expression.</span></span> <span data-ttu-id="41858-143">定义了`println`一个函数, 该函数包含一个`print`递归函数, F#该函数以友好格式`Expr`显示 expression 对象 (类型为)。</span><span class="sxs-lookup"><span data-stu-id="41858-143">A function `println` is defined that contains a recursive function `print` that displays an F# expression object (of type `Expr`) in a friendly format.</span></span> <span data-ttu-id="41858-144">可以使用[fsharp.core](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4)和[DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd)模块中的几个活动模式来分析表达式对象, 这种模式可用于分析表达式对象。</span><span class="sxs-lookup"><span data-stu-id="41858-144">There are several active patterns in the [Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) and [Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) modules that can be used to analyze expression objects.</span></span> <span data-ttu-id="41858-145">此示例不包括可能出现在F#表达式中的所有可能的模式。</span><span class="sxs-lookup"><span data-stu-id="41858-145">This example does not include all the possible patterns that might appear in an F# expression.</span></span> <span data-ttu-id="41858-146">任何无法识别的模式都会触发与通配符模式 (`_`) 的匹配, 并通过`ToString`使用方法呈现, 该方法`Expr`可让你了解要添加到匹配表达式的活动模式。</span><span class="sxs-lookup"><span data-stu-id="41858-146">Any unrecognized pattern triggers a match to the wildcard pattern (`_`) and is rendered by using the `ToString` method, which, on the `Expr` type, lets you know the active pattern to add to your match expression.</span></span>

### <a name="code"></a><span data-ttu-id="41858-147">代码</span><span class="sxs-lookup"><span data-stu-id="41858-147">Code</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a><span data-ttu-id="41858-148">Output</span><span class="sxs-lookup"><span data-stu-id="41858-148">Output</span></span>

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a><span data-ttu-id="41858-149">示例</span><span class="sxs-lookup"><span data-stu-id="41858-149">Example</span></span>

### <a name="description"></a><span data-ttu-id="41858-150">描述</span><span class="sxs-lookup"><span data-stu-id="41858-150">Description</span></span>

<span data-ttu-id="41858-151">您还可以使用[exprshape.rebuildshapecombination 模块](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de)中的三个活动模式来遍历具有较少活动模式的表达式树。</span><span class="sxs-lookup"><span data-stu-id="41858-151">You can also use the three active patterns in the [ExprShape module](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) to traverse expression trees with fewer active patterns.</span></span> <span data-ttu-id="41858-152">当你希望遍历树但你不需要大多数节点中的所有信息时, 这些活动模式会很有用。</span><span class="sxs-lookup"><span data-stu-id="41858-152">These active patterns can be useful when you want to traverse a tree but you do not need all the information in most of the nodes.</span></span> <span data-ttu-id="41858-153">当使用这些模式时, 任何F#表达式都将与以下三种模式之一`ShapeVar`匹配: 如果表达式为变量, `ShapeLambda`则为; 如果表达式是 lambda 表达式, `ShapeCombination`则为; 否则为。</span><span class="sxs-lookup"><span data-stu-id="41858-153">When you use these patterns, any F# expression matches one of the following three patterns: `ShapeVar` if the expression is a variable, `ShapeLambda` if the expression is a lambda expression, or `ShapeCombination` if the expression is anything else.</span></span> <span data-ttu-id="41858-154">如果使用活动模式遍历表达式树, 如前面的代码示例所示, 您必须使用更多的模式来处理所有可能F#的表达式类型, 并且您的代码将更复杂。</span><span class="sxs-lookup"><span data-stu-id="41858-154">If you traverse an expression tree by using the active patterns as in the previous code example, you have to use many more patterns to handle all possible F# expression types, and your code will be more complex.</span></span> <span data-ttu-id="41858-155">有关详细信息, 请参阅[exprshape.rebuildshapecombination.&#124;ShapeVar&#124;ShapeLambda ShapeCombination Active Pattern](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d)。</span><span class="sxs-lookup"><span data-stu-id="41858-155">For more information, see [ExprShape.ShapeVar&#124;ShapeLambda&#124;ShapeCombination Active Pattern](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d).</span></span>

<span data-ttu-id="41858-156">下面的代码示例可用作更复杂的遍历的基础。</span><span class="sxs-lookup"><span data-stu-id="41858-156">The following code example can be used as a basis for more complex traversals.</span></span> <span data-ttu-id="41858-157">在此代码中, 将为包含函数调用`add`的表达式创建表达式树。</span><span class="sxs-lookup"><span data-stu-id="41858-157">In this code, an expression tree is created for an expression that involves a function call, `add`.</span></span> <span data-ttu-id="41858-158">[SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d)活动模式用于检测对`add`表达式树中的任何调用。</span><span class="sxs-lookup"><span data-stu-id="41858-158">The [SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) active pattern is used to detect any call to `add` in the expression tree.</span></span> <span data-ttu-id="41858-159">此活动模式将调用的参数分配给`exprList`值。</span><span class="sxs-lookup"><span data-stu-id="41858-159">This active pattern assigns the arguments of the call to the `exprList` value.</span></span> <span data-ttu-id="41858-160">在这种情况下, 只有两个, 因此会将其拉出, 并以递归方式对参数调用函数。</span><span class="sxs-lookup"><span data-stu-id="41858-160">In this case, there are only two, so these are pulled out and the function is called recursively on the arguments.</span></span> <span data-ttu-id="41858-161">`mul`通过使用拼接运算符 (`%%`) 将结果插入到表示对的调用的代码中。</span><span class="sxs-lookup"><span data-stu-id="41858-161">The results are inserted into a code quotation that represents a call to `mul` by using the splice operator (`%%`).</span></span> <span data-ttu-id="41858-162">上`println`一示例中的函数用于显示结果。</span><span class="sxs-lookup"><span data-stu-id="41858-162">The `println` function from the previous example is used to display the results.</span></span>

<span data-ttu-id="41858-163">其他活动模式分支中的代码只是重新生成相同的表达式树, 因此, 结果表达式中的唯一更改是从`add`到`mul`的更改。</span><span class="sxs-lookup"><span data-stu-id="41858-163">The code in the other active pattern branches just regenerates the same expression tree, so the only change in the resulting expression is the change from `add` to `mul`.</span></span>

### <a name="code"></a><span data-ttu-id="41858-164">代码</span><span class="sxs-lookup"><span data-stu-id="41858-164">Code</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a><span data-ttu-id="41858-165">Output</span><span class="sxs-lookup"><span data-stu-id="41858-165">Output</span></span>

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a><span data-ttu-id="41858-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="41858-166">See also</span></span>

- [<span data-ttu-id="41858-167">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="41858-167">F# Language Reference</span></span>](index.md)
