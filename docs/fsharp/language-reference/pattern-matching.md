---
title: 模式匹配 (F#)
description: '了解如何使用模式在 F # 中的逻辑结构的数据进行比较、 将数据分解为各个构成部分，或从数据中提取信息。'
ms.date: 05/16/2016
ms.openlocfilehash: 5ad3d3e1a78246afdfa2948fd0fb84fa04686d30
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44216563"
---
# <a name="pattern-matching"></a><span data-ttu-id="33eec-103">模式匹配</span><span class="sxs-lookup"><span data-stu-id="33eec-103">Pattern Matching</span></span>

<span data-ttu-id="33eec-104">模式是用于转换输入的数据的规则。</span><span class="sxs-lookup"><span data-stu-id="33eec-104">Patterns are rules for transforming input data.</span></span> <span data-ttu-id="33eec-105">它们用于整个 F # 语言比较数据的逻辑结构或结构、 将数据分解为各个构成部分，或从以各种方式的数据中提取信息。</span><span class="sxs-lookup"><span data-stu-id="33eec-105">They are used throughout the F# language to compare data with a logical structure or structures, decompose data into constituent parts, or extract information from data in various ways.</span></span>

## <a name="remarks"></a><span data-ttu-id="33eec-106">备注</span><span class="sxs-lookup"><span data-stu-id="33eec-106">Remarks</span></span>

<span data-ttu-id="33eec-107">在许多语言构造，如使用模式`match`表达式。</span><span class="sxs-lookup"><span data-stu-id="33eec-107">Patterns are used in many language constructs, such as the `match` expression.</span></span> <span data-ttu-id="33eec-108">正在处理中的函数的参数时使用它们`let`绑定、 lambda 表达式和中与相关联的异常处理程序`try...with`表达式。</span><span class="sxs-lookup"><span data-stu-id="33eec-108">They are used when you are processing arguments for functions in `let` bindings, lambda expressions, and in the exception handlers associated with the `try...with` expression.</span></span> <span data-ttu-id="33eec-109">有关详细信息，请参阅[匹配表达式](match-expressions.md)， [let 绑定](functions/let-bindings.md)， [Lambda 表达式：`fun`关键字](functions/lambda-expressions-the-fun-keyword.md)，和[异常： `try...with`表达式](exception-handling/the-try-with-expression.md)。</span><span class="sxs-lookup"><span data-stu-id="33eec-109">For more information, see [Match Expressions](match-expressions.md), [let Bindings](functions/let-bindings.md), [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md), and [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>

<span data-ttu-id="33eec-110">例如，在`match`表达式中，*模式*是竖线的后面。</span><span class="sxs-lookup"><span data-stu-id="33eec-110">For example, in the `match` expression, the *pattern* is what follows the pipe symbol.</span></span>

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

<span data-ttu-id="33eec-111">每个模式都充当转换输入以某种方式的规则。</span><span class="sxs-lookup"><span data-stu-id="33eec-111">Each pattern acts as a rule for transforming input in some way.</span></span> <span data-ttu-id="33eec-112">在`match`又检查表达式中，每个模式来查看输入的数据是否与模式兼容。</span><span class="sxs-lookup"><span data-stu-id="33eec-112">In the `match` expression, each pattern is examined in turn to see if the input data is compatible with the pattern.</span></span> <span data-ttu-id="33eec-113">如果找到匹配项，则执行结果表达式。</span><span class="sxs-lookup"><span data-stu-id="33eec-113">If a match is found, the result expression is executed.</span></span> <span data-ttu-id="33eec-114">如果找不到匹配项，则测试下一个模式规则。</span><span class="sxs-lookup"><span data-stu-id="33eec-114">If a match is not found, the next pattern rule is tested.</span></span> <span data-ttu-id="33eec-115">可选 when*条件*一部分所述[匹配表达式](match-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="33eec-115">The optional when *condition* part is explained in [Match Expressions](match-expressions.md).</span></span>

<span data-ttu-id="33eec-116">受支持的模式下表所示。</span><span class="sxs-lookup"><span data-stu-id="33eec-116">Supported patterns are shown in the following table.</span></span> <span data-ttu-id="33eec-117">在运行时，对输入进行测试对每个表中列出的顺序中的以下模式和模式以递归方式应用，从第一次到最后一个出现在代码中，并从左到右的模式的每个行。</span><span class="sxs-lookup"><span data-stu-id="33eec-117">At run time, the input is tested against each of the following patterns in the order listed in the table, and patterns are applied recursively, from first to last as they appear in your code, and from left to right for the patterns on each line.</span></span>

|<span data-ttu-id="33eec-118">name</span><span class="sxs-lookup"><span data-stu-id="33eec-118">Name</span></span>|<span data-ttu-id="33eec-119">描述</span><span class="sxs-lookup"><span data-stu-id="33eec-119">Description</span></span>|<span data-ttu-id="33eec-120">示例</span><span class="sxs-lookup"><span data-stu-id="33eec-120">Example</span></span>|
|----|-----------|-------|
|<span data-ttu-id="33eec-121">常量模式</span><span class="sxs-lookup"><span data-stu-id="33eec-121">Constant pattern</span></span>|<span data-ttu-id="33eec-122">任何数字、 字符或字符串文本、 枚举常量或定义的文本标识符</span><span class="sxs-lookup"><span data-stu-id="33eec-122">Any numeric, character, or string literal, an enumeration constant, or a defined literal identifier</span></span>|<span data-ttu-id="33eec-123">`1.0`, `"test"`, `30`, `Color.Red`</span><span class="sxs-lookup"><span data-stu-id="33eec-123">`1.0`, `"test"`, `30`, `Color.Red`</span></span>|
|<span data-ttu-id="33eec-124">标识符模式</span><span class="sxs-lookup"><span data-stu-id="33eec-124">Identifier pattern</span></span>|<span data-ttu-id="33eec-125">可区分的联合、 异常标签或活动模式用例的用例值</span><span class="sxs-lookup"><span data-stu-id="33eec-125">A case value of a discriminated union, an exception label, or an active pattern case</span></span>|`Some(x)`<br /><br />`Failure(msg)`|
|<span data-ttu-id="33eec-126">变量模式</span><span class="sxs-lookup"><span data-stu-id="33eec-126">Variable pattern</span></span>|<span data-ttu-id="33eec-127">*identifier*</span><span class="sxs-lookup"><span data-stu-id="33eec-127">*identifier*</span></span>|`a`|
|<span data-ttu-id="33eec-128">`as` 模式</span><span class="sxs-lookup"><span data-stu-id="33eec-128">`as` pattern</span></span>|<span data-ttu-id="33eec-129">*模式*作为*标识符*</span><span class="sxs-lookup"><span data-stu-id="33eec-129">*pattern* as *identifier*</span></span>|`(a, b) as tuple1`|
|<span data-ttu-id="33eec-130">或模式</span><span class="sxs-lookup"><span data-stu-id="33eec-130">OR pattern</span></span>|<span data-ttu-id="33eec-131">*pattern1* &#124; *pattern2 下*</span><span class="sxs-lookup"><span data-stu-id="33eec-131">*pattern1* &#124; *pattern2*</span></span>|<code>([h] &#124; [h; _])</code>|
|<span data-ttu-id="33eec-132">和模式</span><span class="sxs-lookup"><span data-stu-id="33eec-132">AND pattern</span></span>|<span data-ttu-id="33eec-133">*pattern1* &amp; *pattern2 下*</span><span class="sxs-lookup"><span data-stu-id="33eec-133">*pattern1* &amp; *pattern2*</span></span>|`(a, b) & (_, "test")`|
|<span data-ttu-id="33eec-134">Cons 模式</span><span class="sxs-lookup"><span data-stu-id="33eec-134">Cons pattern</span></span>|<span data-ttu-id="33eec-135">*标识符*::*列表标识符*</span><span class="sxs-lookup"><span data-stu-id="33eec-135">*identifier* :: *list-identifier*</span></span>|`h :: t`|
|<span data-ttu-id="33eec-136">列表模式</span><span class="sxs-lookup"><span data-stu-id="33eec-136">List pattern</span></span>|<span data-ttu-id="33eec-137">[*模式 1*;...;*模式 n* ]</span><span class="sxs-lookup"><span data-stu-id="33eec-137">[ *pattern_1*; ... ; *pattern_n* ]</span></span>|`[ a; b; c ]`|
|<span data-ttu-id="33eec-138">数组模式</span><span class="sxs-lookup"><span data-stu-id="33eec-138">Array pattern</span></span>|<span data-ttu-id="33eec-139">[&#124; *模式 1*;..;*模式 n* &#124;]</span><span class="sxs-lookup"><span data-stu-id="33eec-139">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span></span>|<code>[&#124; a; b; c &#124;]</code>|
|<span data-ttu-id="33eec-140">带括号模式</span><span class="sxs-lookup"><span data-stu-id="33eec-140">Parenthesized pattern</span></span>|<span data-ttu-id="33eec-141">(*模式*)</span><span class="sxs-lookup"><span data-stu-id="33eec-141">( *pattern* )</span></span>|`( a )`|
|<span data-ttu-id="33eec-142">元组模式</span><span class="sxs-lookup"><span data-stu-id="33eec-142">Tuple pattern</span></span>|<span data-ttu-id="33eec-143">(*模式 1*、...、*模式 n* )</span><span class="sxs-lookup"><span data-stu-id="33eec-143">( *pattern_1*, ... , *pattern_n* )</span></span>|`( a, b )`|
|<span data-ttu-id="33eec-144">记录模式</span><span class="sxs-lookup"><span data-stu-id="33eec-144">Record pattern</span></span>|<span data-ttu-id="33eec-145">{ *identifier1* = *模式 1*;...;*标识符 n* = *模式 n* }</span><span class="sxs-lookup"><span data-stu-id="33eec-145">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span></span>|`{ Name = name; }`|
|<span data-ttu-id="33eec-146">通配符模式</span><span class="sxs-lookup"><span data-stu-id="33eec-146">Wildcard pattern</span></span>|<span data-ttu-id="33eec-147">_</span><span class="sxs-lookup"><span data-stu-id="33eec-147">_</span></span>|`_`|
|<span data-ttu-id="33eec-148">带有类型批注的模式</span><span class="sxs-lookup"><span data-stu-id="33eec-148">Pattern together with type annotation</span></span>|<span data-ttu-id="33eec-149">*模式*:*类型*</span><span class="sxs-lookup"><span data-stu-id="33eec-149">*pattern* : *type*</span></span>|`a : int`|
|<span data-ttu-id="33eec-150">类型测试模式</span><span class="sxs-lookup"><span data-stu-id="33eec-150">Type test pattern</span></span>|<span data-ttu-id="33eec-151">:?</span><span class="sxs-lookup"><span data-stu-id="33eec-151">:?</span></span> <span data-ttu-id="33eec-152">*类型*[作为*标识符*]</span><span class="sxs-lookup"><span data-stu-id="33eec-152">*type* [ as *identifier* ]</span></span>|`:? System.DateTime as dt`|
|<span data-ttu-id="33eec-153">Null 模式</span><span class="sxs-lookup"><span data-stu-id="33eec-153">Null pattern</span></span>|<span data-ttu-id="33eec-154">null</span><span class="sxs-lookup"><span data-stu-id="33eec-154">null</span></span>|`null`|

## <a name="constant-patterns"></a><span data-ttu-id="33eec-155">常量模式</span><span class="sxs-lookup"><span data-stu-id="33eec-155">Constant Patterns</span></span>

<span data-ttu-id="33eec-156">常量模式是数值、 字符和字符串文本、 枚举常量 （包括枚举类型名称）。</span><span class="sxs-lookup"><span data-stu-id="33eec-156">Constant patterns are numeric, character, and string literals, enumeration constants (with the enumeration type name included).</span></span> <span data-ttu-id="33eec-157">一个`match`只有常量模式的表达式可以比作其他语言中的 case 语句。</span><span class="sxs-lookup"><span data-stu-id="33eec-157">A `match` expression that has only constant patterns can be compared to a case statement in other languages.</span></span> <span data-ttu-id="33eec-158">输入与文本值进行比较，则模式匹配的值是否相等。</span><span class="sxs-lookup"><span data-stu-id="33eec-158">The input is compared with the literal value and the pattern matches if the values are equal.</span></span> <span data-ttu-id="33eec-159">文字的类型必须与输入的类型兼容。</span><span class="sxs-lookup"><span data-stu-id="33eec-159">The type of the literal must be compatible with the type of the input.</span></span>

<span data-ttu-id="33eec-160">下面的示例演示如何使用文本模式，并还使用了变量模式和 OR 模式。</span><span class="sxs-lookup"><span data-stu-id="33eec-160">The following example demonstrates the use of literal patterns, and also uses a variable pattern and an OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

<span data-ttu-id="33eec-161">文本模式的另一个示例是基于枚举常量的模式。</span><span class="sxs-lookup"><span data-stu-id="33eec-161">Another example of a literal pattern is a pattern based on enumeration constants.</span></span> <span data-ttu-id="33eec-162">使用枚举常量时，必须指定枚举类型名称。</span><span class="sxs-lookup"><span data-stu-id="33eec-162">You must specify the enumeration type name when you use enumeration constants.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a><span data-ttu-id="33eec-163">标识符模式</span><span class="sxs-lookup"><span data-stu-id="33eec-163">Identifier Patterns</span></span>

<span data-ttu-id="33eec-164">如果模式是形成有效标识符字符的字符串，该标识符的形式确定如何匹配该模式。</span><span class="sxs-lookup"><span data-stu-id="33eec-164">If the pattern is a string of characters that forms a valid identifier, the form of the identifier determines how the pattern is matched.</span></span> <span data-ttu-id="33eec-165">如果标识符的长度超过一个字符和大写字符开头，编译器将尝试与标识符模式进行匹配。</span><span class="sxs-lookup"><span data-stu-id="33eec-165">If the identifier is longer than a single character and starts with an uppercase character, the compiler tries to make a match to the identifier pattern.</span></span> <span data-ttu-id="33eec-166">此模式的标识符可以是标记为文本特性、 可区分联合用例、 异常标识符或活动模式用例的值。</span><span class="sxs-lookup"><span data-stu-id="33eec-166">The identifier for this pattern could be a value marked with the Literal attribute, a discriminated union case, an exception identifier, or an active pattern case.</span></span> <span data-ttu-id="33eec-167">如果不找到任何匹配的标识符，则匹配将失败下, 一个模式规则变量模式进行比较的输入。</span><span class="sxs-lookup"><span data-stu-id="33eec-167">If no matching identifier is found, the match fails and the next pattern rule, the variable pattern, is compared to the input.</span></span>

<span data-ttu-id="33eec-168">可区分联合模式可以是简单的命名用例或它们可能有一个值或包含多个值的元组。</span><span class="sxs-lookup"><span data-stu-id="33eec-168">Discriminated union patterns can be simple named cases or they can have a value, or a tuple containing multiple values.</span></span> <span data-ttu-id="33eec-169">如果没有一个值，则必须指定值的标识符。</span><span class="sxs-lookup"><span data-stu-id="33eec-169">If there is a value, you must specify an identifier for the value.</span></span> <span data-ttu-id="33eec-170">如果存在元组，必须提供一个元组模式与元组的每个元素的标识符或具有一个字段名称的标识符或多个命名联合的字段。</span><span class="sxs-lookup"><span data-stu-id="33eec-170">In the case of a tuple, you must supply a tuple pattern with an identifier for each element of the tuple or an identifier with a field name for one or more named union fields.</span></span> <span data-ttu-id="33eec-171">请参阅本部分中用于示例的代码示例。</span><span class="sxs-lookup"><span data-stu-id="33eec-171">See the code examples in this section for examples.</span></span>

<span data-ttu-id="33eec-172">`option`类型是具有两种情况下，一个可区分的联合`Some`和`None`。</span><span class="sxs-lookup"><span data-stu-id="33eec-172">The `option` type is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="33eec-173">一个用例 (`Some`) 的一个值，但其他 (`None`) 是只是命名用例。</span><span class="sxs-lookup"><span data-stu-id="33eec-173">One case (`Some`) has a value, but the other (`None`) is just a named case.</span></span> <span data-ttu-id="33eec-174">因此，`Some`需要具有与关联的值的变量`Some`，但`None`必须单独出现。</span><span class="sxs-lookup"><span data-stu-id="33eec-174">Therefore, `Some` needs to have a variable for the value associated with the `Some` case, but `None` must appear by itself.</span></span> <span data-ttu-id="33eec-175">在下面的代码中，变量`var1`都提供了通过到匹配值`Some`用例。</span><span class="sxs-lookup"><span data-stu-id="33eec-175">In the following code, the variable `var1` is given the value that is obtained by matching to the `Some` case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

<span data-ttu-id="33eec-176">在以下示例中，`PersonName`可区分的联合混合的字符串和表示可能的名称形式的字符。</span><span class="sxs-lookup"><span data-stu-id="33eec-176">In the following example, the `PersonName` discriminated union contains a mixture of strings and characters that represent possible forms of names.</span></span> <span data-ttu-id="33eec-177">可区分联合的情况下都`FirstOnly`， `LastOnly`，和`FirstLast`。</span><span class="sxs-lookup"><span data-stu-id="33eec-177">The cases of the discriminated union are `FirstOnly`, `LastOnly`, and `FirstLast`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

<span data-ttu-id="33eec-178">对于具有命名字段的可区分联合，你可以使用等号 （=） 中提取命名字段的值。</span><span class="sxs-lookup"><span data-stu-id="33eec-178">For discriminated unions that have named fields, you use the equals sign (=) to extract the value of a named field.</span></span> <span data-ttu-id="33eec-179">例如，考虑具有如下所示的声明的可区分的联合。</span><span class="sxs-lookup"><span data-stu-id="33eec-179">For example, consider a discriminated union with a declaration like the following.</span></span>

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

<span data-ttu-id="33eec-180">可以使用模式匹配表达式中的命名的字段，如下所示。</span><span class="sxs-lookup"><span data-stu-id="33eec-180">You can use the named fields in a pattern matching expression as follows.</span></span>

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

<span data-ttu-id="33eec-181">已命名字段的使用是可选的因此在上一示例中，同时`Circle(r)`和`Circle(radius = r)`具有相同的效果。</span><span class="sxs-lookup"><span data-stu-id="33eec-181">The use of the named field is optional, so in the previous example, both `Circle(r)` and `Circle(radius = r)` have the same effect.</span></span>

<span data-ttu-id="33eec-182">当指定多个字段时，请使用分号 （;） 作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="33eec-182">When you specify multiple fields, use the semicolon (;) as a separator.</span></span>

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

<span data-ttu-id="33eec-183">活动的模式，您可以定义更复杂的自定义模式匹配。</span><span class="sxs-lookup"><span data-stu-id="33eec-183">Active patterns enable you to define more complex custom pattern matching.</span></span> <span data-ttu-id="33eec-184">有关活动模式的详细信息，请参阅[活动模式](active-patterns.md)。</span><span class="sxs-lookup"><span data-stu-id="33eec-184">For more information about active patterns, see [Active Patterns](active-patterns.md).</span></span>

<span data-ttu-id="33eec-185">在其中标识符是异常的情况下用在模式匹配的异常处理程序上下文中。</span><span class="sxs-lookup"><span data-stu-id="33eec-185">The case in which the identifier is an exception is used in pattern matching in the context of exception handlers.</span></span> <span data-ttu-id="33eec-186">有关异常处理中的模式匹配的信息，请参阅[例外：`try...with`表达式](exception-handling/the-try-with-expression.md)。</span><span class="sxs-lookup"><span data-stu-id="33eec-186">For information about pattern matching in exception handling, see [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>

## <a name="variable-patterns"></a><span data-ttu-id="33eec-187">变量模式</span><span class="sxs-lookup"><span data-stu-id="33eec-187">Variable Patterns</span></span>

<span data-ttu-id="33eec-188">变量模式将与变量名称，然后可在右侧的执行表达式中使用该名称匹配的值分配`->`符号。</span><span class="sxs-lookup"><span data-stu-id="33eec-188">The variable pattern assigns the value being matched to a variable name, which is then available for use in the execution expression to the right of the `->` symbol.</span></span> <span data-ttu-id="33eec-189">变量模式单独匹配任何输入，但变量模式通常出现在其他模式，从而更复杂的结构，例如元组和数组分解为变量中。</span><span class="sxs-lookup"><span data-stu-id="33eec-189">A variable pattern alone matches any input, but variable patterns often appear within other patterns, therefore enabling more complex structures such as tuples and arrays to be decomposed into variables.</span></span>

<span data-ttu-id="33eec-190">下面的示例演示一个元组模式内的变量模式。</span><span class="sxs-lookup"><span data-stu-id="33eec-190">The following example demonstrates a variable pattern within a tuple pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a><span data-ttu-id="33eec-191">as 模式</span><span class="sxs-lookup"><span data-stu-id="33eec-191">as Pattern</span></span>

<span data-ttu-id="33eec-192">`as`模式是一种模式具有`as`子句附加到它。</span><span class="sxs-lookup"><span data-stu-id="33eec-192">The `as` pattern is a pattern that has an `as` clause appended to it.</span></span> <span data-ttu-id="33eec-193">`as`子句将匹配的值绑定到可用的执行表达式中的名称`match`表达式，或在此模式中的使用位置的情况下`let`绑定，将名称添加作为到局部范围的绑定。</span><span class="sxs-lookup"><span data-stu-id="33eec-193">The `as` clause binds the matched value to a name that can be used in the execution expression of a `match` expression, or, in the case where this pattern is used in a `let` binding, the name is added as a binding to the local scope.</span></span>

<span data-ttu-id="33eec-194">下面的示例使用`as`模式。</span><span class="sxs-lookup"><span data-stu-id="33eec-194">The following example uses an `as` pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a><span data-ttu-id="33eec-195">或模式</span><span class="sxs-lookup"><span data-stu-id="33eec-195">OR Pattern</span></span>

<span data-ttu-id="33eec-196">输入的数据可以与匹配多个模式，并且想要作为结果执行相同代码时，则使用 OR 模式。</span><span class="sxs-lookup"><span data-stu-id="33eec-196">The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result.</span></span> <span data-ttu-id="33eec-197">OR 模式两边的类型必须兼容。</span><span class="sxs-lookup"><span data-stu-id="33eec-197">The types of both sides of the OR pattern must be compatible.</span></span>

<span data-ttu-id="33eec-198">下面的示例演示 OR 模式。</span><span class="sxs-lookup"><span data-stu-id="33eec-198">The following example demonstrates the OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a><span data-ttu-id="33eec-199">和模式</span><span class="sxs-lookup"><span data-stu-id="33eec-199">AND Pattern</span></span>

<span data-ttu-id="33eec-200">AND 模式要求的输入匹配两种模式。</span><span class="sxs-lookup"><span data-stu-id="33eec-200">The AND pattern requires that the input match two patterns.</span></span> <span data-ttu-id="33eec-201">AND 模式两边的类型必须兼容。</span><span class="sxs-lookup"><span data-stu-id="33eec-201">The types of both sides of the AND pattern must be compatible.</span></span>

<span data-ttu-id="33eec-202">下面的示例就像`detectZeroTuple`中所示[元组模式](https://msdn.microsoft.com/library/#tuple)后面本主题中，但此处部分`var1`和`var2`通过使用 AND 模式获得作为值。</span><span class="sxs-lookup"><span data-stu-id="33eec-202">The following example is like `detectZeroTuple` shown in the [Tuple Pattern](https://msdn.microsoft.com/library/#tuple) section later in this topic, but here both `var1` and `var2` are obtained as values by using the AND pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a><span data-ttu-id="33eec-203">Cons 模式</span><span class="sxs-lookup"><span data-stu-id="33eec-203">Cons Pattern</span></span>

<span data-ttu-id="33eec-204">Cons 模式用于将列表分解为第一个元素， *head*，和一个列表，其中包含其余元素*结尾*。</span><span class="sxs-lookup"><span data-stu-id="33eec-204">The cons pattern is used to decompose a list into the first element, the *head*, and a list that contains the remaining elements, the *tail*.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a><span data-ttu-id="33eec-205">列表模式</span><span class="sxs-lookup"><span data-stu-id="33eec-205">List Pattern</span></span>

<span data-ttu-id="33eec-206">利用列表模式可将列表分解为多个元素。</span><span class="sxs-lookup"><span data-stu-id="33eec-206">The list pattern enables lists to be decomposed into a number of elements.</span></span> <span data-ttu-id="33eec-207">在列表模式本身可以匹配特定数量的元素组成的列表。</span><span class="sxs-lookup"><span data-stu-id="33eec-207">The list pattern itself can match only lists of a specific number of elements.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a><span data-ttu-id="33eec-208">数组模式</span><span class="sxs-lookup"><span data-stu-id="33eec-208">Array Pattern</span></span>

<span data-ttu-id="33eec-209">数组模式类似于列表模式，并且可用于将分解特定长度的数组。</span><span class="sxs-lookup"><span data-stu-id="33eec-209">The array pattern resembles the list pattern and can be used to decompose arrays of a specific length.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a><span data-ttu-id="33eec-210">带括号模式</span><span class="sxs-lookup"><span data-stu-id="33eec-210">Parenthesized Pattern</span></span>

<span data-ttu-id="33eec-211">可以围绕模式来实现所需的关联性分组括号。</span><span class="sxs-lookup"><span data-stu-id="33eec-211">Parentheses can be grouped around patterns to achieve the desired associativity.</span></span> <span data-ttu-id="33eec-212">在以下示例中，括号用于控制 AND 模式和 cons 模式之间的关联性。</span><span class="sxs-lookup"><span data-stu-id="33eec-212">In the following example, parentheses are used to control associativity between an AND pattern and a cons pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a><span data-ttu-id="33eec-213">元组模式</span><span class="sxs-lookup"><span data-stu-id="33eec-213">Tuple Pattern</span></span>

<span data-ttu-id="33eec-214">元组模式与元组形式的输入匹配，并启用要使用的模式匹配的元组中每个位置的变量分解为其构成元素的元组。</span><span class="sxs-lookup"><span data-stu-id="33eec-214">The tuple pattern matches input in tuple form and enables the tuple to be decomposed into its constituent elements by using pattern matching variables for each position in the tuple.</span></span>

<span data-ttu-id="33eec-215">以下示例演示元组模式，并且还使用文本模式、 变量模式和通配符模式。</span><span class="sxs-lookup"><span data-stu-id="33eec-215">The following example demonstrates the tuple pattern and also uses literal patterns, variable patterns, and the wildcard pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a><span data-ttu-id="33eec-216">记录模式</span><span class="sxs-lookup"><span data-stu-id="33eec-216">Record Pattern</span></span>

<span data-ttu-id="33eec-217">记录模式用于分解记录以提取字段的值。</span><span class="sxs-lookup"><span data-stu-id="33eec-217">The record pattern is used to decompose records to extract the values of fields.</span></span> <span data-ttu-id="33eec-218">该模式不必引用记录; 该记录的所有字段任何忽略的字段仅不参与匹配，并且不会提取。</span><span class="sxs-lookup"><span data-stu-id="33eec-218">The pattern does not have to reference all fields of the record; any omitted fields just do not participate in matching and are not extracted.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a><span data-ttu-id="33eec-219">通配符模式</span><span class="sxs-lookup"><span data-stu-id="33eec-219">Wildcard Pattern</span></span>

<span data-ttu-id="33eec-220">通配符模式均由下划线 (`_`) 字符，并匹配任何输入，就像变量模式一样，不同之处在于输入丢弃而不是分配给一个变量。</span><span class="sxs-lookup"><span data-stu-id="33eec-220">The wildcard pattern is represented by the underscore (`_`) character and matches any input, just like the variable pattern, except that the input is discarded instead of assigned to a variable.</span></span> <span data-ttu-id="33eec-221">通配符模式通常用于在其他模式内作为占位符在右侧的表达式中不需要的值`->`符号。</span><span class="sxs-lookup"><span data-stu-id="33eec-221">The wildcard pattern is often used within other patterns as a placeholder for values that are not needed in the expression to the right of the `->` symbol.</span></span> <span data-ttu-id="33eec-222">也经常模式的列表的末尾使用通配符模式匹配任何不匹配的输入。</span><span class="sxs-lookup"><span data-stu-id="33eec-222">The wildcard pattern is also frequently used at the end of a list of patterns to match any unmatched input.</span></span> <span data-ttu-id="33eec-223">本主题中的许多代码示例中演示的通配符模式。</span><span class="sxs-lookup"><span data-stu-id="33eec-223">The wildcard pattern is demonstrated in many code examples in this topic.</span></span> <span data-ttu-id="33eec-224">请参阅前面的代码查看一个示例。</span><span class="sxs-lookup"><span data-stu-id="33eec-224">See the preceding code for one example.</span></span>

## <a name="patterns-that-have-type-annotations"></a><span data-ttu-id="33eec-225">具有类型批注的模式</span><span class="sxs-lookup"><span data-stu-id="33eec-225">Patterns That Have Type Annotations</span></span>

<span data-ttu-id="33eec-226">模式可以有类型批注。</span><span class="sxs-lookup"><span data-stu-id="33eec-226">Patterns can have type annotations.</span></span> <span data-ttu-id="33eec-227">这些行为类似于其他类型批注，指导推理等其他类型批注。</span><span class="sxs-lookup"><span data-stu-id="33eec-227">These behave like other type annotations and guide inference like other type annotations.</span></span> <span data-ttu-id="33eec-228">类型批注的模式的模式要求使用括号。</span><span class="sxs-lookup"><span data-stu-id="33eec-228">Parentheses are required around type annotations in patterns.</span></span> <span data-ttu-id="33eec-229">下面的代码演示具有类型批注的模式。</span><span class="sxs-lookup"><span data-stu-id="33eec-229">The following code shows a pattern that has a type annotation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a><span data-ttu-id="33eec-230">类型测试模式</span><span class="sxs-lookup"><span data-stu-id="33eec-230">Type Test Pattern</span></span>

<span data-ttu-id="33eec-231">类型测试模式用于匹配类型的输入。</span><span class="sxs-lookup"><span data-stu-id="33eec-231">The type test pattern is used to match the input against a type.</span></span> <span data-ttu-id="33eec-232">如果输入的类型是与匹配的 （或派生的类型的） 成功的模式匹配中指定的类型。</span><span class="sxs-lookup"><span data-stu-id="33eec-232">If the input type is a match to (or a derived type of) the type specified in the pattern, the match succeeds.</span></span>

<span data-ttu-id="33eec-233">下面的示例演示类型测试模式。</span><span class="sxs-lookup"><span data-stu-id="33eec-233">The following example demonstrates the type test pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a><span data-ttu-id="33eec-234">Null 模式</span><span class="sxs-lookup"><span data-stu-id="33eec-234">Null Pattern</span></span>

<span data-ttu-id="33eec-235">Null 模式匹配时你正在使用允许 null 值的类型，可能出现 null 值。</span><span class="sxs-lookup"><span data-stu-id="33eec-235">The null pattern matches the null value that can appear when you are working with types that allow a null value.</span></span> <span data-ttu-id="33eec-236">与.NET Framework 代码交互操作时，经常使用 null 模式。</span><span class="sxs-lookup"><span data-stu-id="33eec-236">Null patterns are frequently used when interoperating with .NET Framework code.</span></span> <span data-ttu-id="33eec-237">例如，.NET API 的返回值可能是输入到`match`表达式。</span><span class="sxs-lookup"><span data-stu-id="33eec-237">For example, the return value of a .NET API might be the input to a `match` expression.</span></span> <span data-ttu-id="33eec-238">您可以控制是否返回值为 null，并且也返回的值的其他特征上基于的程序流。</span><span class="sxs-lookup"><span data-stu-id="33eec-238">You can control program flow based on whether the return value is null, and also on other characteristics of the returned value.</span></span> <span data-ttu-id="33eec-239">Null 模式可用于防止 null 值传播到应用程序的其余部分。</span><span class="sxs-lookup"><span data-stu-id="33eec-239">You can use the null pattern to prevent null values from propagating to the rest of your program.</span></span>

<span data-ttu-id="33eec-240">以下示例使用 null 模式和变量模式。</span><span class="sxs-lookup"><span data-stu-id="33eec-240">The following example uses the null pattern and the variable pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a><span data-ttu-id="33eec-241">请参阅</span><span class="sxs-lookup"><span data-stu-id="33eec-241">See also</span></span>

- [<span data-ttu-id="33eec-242">match 表达式</span><span class="sxs-lookup"><span data-stu-id="33eec-242">Match Expressions</span></span>](match-expressions.md)
- [<span data-ttu-id="33eec-243">活动模式</span><span class="sxs-lookup"><span data-stu-id="33eec-243">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="33eec-244">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="33eec-244">F# Language Reference</span></span>](index.md)
