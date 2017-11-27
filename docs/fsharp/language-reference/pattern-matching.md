---
title: "模式匹配 (F#)"
description: "了解如何使用模式在 F # 中进行比较的逻辑结构的数据、 将数据分解为组成部分，或从数据中提取信息。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 5562ee98-e2f1-4dcd-8e2f-16ae27baaade
ms.openlocfilehash: 7c7a3110a8f34c0c96c12d4584010a9ac4b485fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="pattern-matching"></a><span data-ttu-id="5d9bd-104">模式匹配</span><span class="sxs-lookup"><span data-stu-id="5d9bd-104">Pattern Matching</span></span>

<span data-ttu-id="5d9bd-105">模式是用于转换输入的数据的规则。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-105">Patterns are rules for transforming input data.</span></span> <span data-ttu-id="5d9bd-106">它们整个都使用 F # 语言比较使用逻辑结构或结构的数据、 将数据分解为组成部分，或从以各种方式的数据中提取信息。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-106">They are used throughout the F# language to compare data with a logical structure or structures, decompose data into constituent parts, or extract information from data in various ways.</span></span>


## <a name="remarks"></a><span data-ttu-id="5d9bd-107">备注</span><span class="sxs-lookup"><span data-stu-id="5d9bd-107">Remarks</span></span>
<span data-ttu-id="5d9bd-108">在许多语言构造，如用于模式`match`表达式。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-108">Patterns are used in many language constructs, such as the `match` expression.</span></span> <span data-ttu-id="5d9bd-109">当处理函数的自变量使用它们`let`绑定、 lambda 表达式，并在与关联的异常处理`try...with`表达式。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-109">They are used when you are processing arguments for functions in `let` bindings, lambda expressions, and in the exception handlers associated with the `try...with` expression.</span></span> <span data-ttu-id="5d9bd-110">有关详细信息，请参阅[匹配表达式](match-expressions.md)， [let 绑定](functions/let-bindings.md)， [Lambda 表达式：`fun`关键字](functions/lambda-expressions-the-fun-keyword.md)，和[异常： `try...with`表达式](exception-handling/the-try-with-expression.md)。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-110">For more information, see [Match Expressions](match-expressions.md), [let Bindings](functions/let-bindings.md), [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md), and [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>

<span data-ttu-id="5d9bd-111">例如，在`match`表达式，*模式*是什么遵循管道符号。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-111">For example, in the `match` expression, the *pattern* is what follows the pipe symbol.</span></span>

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

<span data-ttu-id="5d9bd-112">每个模式充当转换输入以某种方式的规则。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-112">Each pattern acts as a rule for transforming input in some way.</span></span> <span data-ttu-id="5d9bd-113">在`match`表达式，每个模式将反过来检查以确定输入的数据是否与模式兼容。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-113">In the `match` expression, each pattern is examined in turn to see if the input data is compatible with the pattern.</span></span> <span data-ttu-id="5d9bd-114">如果找到匹配项，则执行的结果表达式。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-114">If a match is found, the result expression is executed.</span></span> <span data-ttu-id="5d9bd-115">如果未找到匹配项，则测试的下一个模式规则。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-115">If a match is not found, the next pattern rule is tested.</span></span> <span data-ttu-id="5d9bd-116">可选在*条件*一部分述[匹配表达式](match-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-116">The optional when *condition* part is explained in [Match Expressions](match-expressions.md).</span></span>

<span data-ttu-id="5d9bd-117">支持的模式均显示下表中。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-117">Supported patterns are shown in the following table.</span></span> <span data-ttu-id="5d9bd-118">在运行时，输入测试针对每个表中列出的顺序中的以下模式和模式都是以递归方式应用，从第一次到最后一个要与出现在代码中，并从左到右的模式的每个行。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-118">At run time, the input is tested against each of the following patterns in the order listed in the table, and patterns are applied recursively, from first to last as they appear in your code, and from left to right for the patterns on each line.</span></span>

|<span data-ttu-id="5d9bd-119">名称</span><span class="sxs-lookup"><span data-stu-id="5d9bd-119">Name</span></span>|<span data-ttu-id="5d9bd-120">描述</span><span class="sxs-lookup"><span data-stu-id="5d9bd-120">Description</span></span>|<span data-ttu-id="5d9bd-121">示例</span><span class="sxs-lookup"><span data-stu-id="5d9bd-121">Example</span></span>|
|----|-----------|-------|
|<span data-ttu-id="5d9bd-122">常量模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-122">Constant pattern</span></span>|<span data-ttu-id="5d9bd-123">任何数字、 字符或字符串文本、 枚举常量或定义的文本标识符</span><span class="sxs-lookup"><span data-stu-id="5d9bd-123">Any numeric, character, or string literal, an enumeration constant, or a defined literal identifier</span></span>|<span data-ttu-id="5d9bd-124">`1.0`, `"test"`, `30`, `Color.Red`</span><span class="sxs-lookup"><span data-stu-id="5d9bd-124">`1.0`, `"test"`, `30`, `Color.Red`</span></span>|
|<span data-ttu-id="5d9bd-125">标识符模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-125">Identifier pattern</span></span>|<span data-ttu-id="5d9bd-126">可区分的联合、 异常标签或活动模式用例的用例值</span><span class="sxs-lookup"><span data-stu-id="5d9bd-126">A case value of a discriminated union, an exception label, or an active pattern case</span></span>|`Some(x)`<br /><br />`Failure(msg)`|
|<span data-ttu-id="5d9bd-127">变量模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-127">Variable pattern</span></span>|<span data-ttu-id="5d9bd-128">*identifier*</span><span class="sxs-lookup"><span data-stu-id="5d9bd-128">*identifier*</span></span>|`a`|
|<span data-ttu-id="5d9bd-129">`as`模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-129">`as` pattern</span></span>|<span data-ttu-id="5d9bd-130">*模式*作为*标识符*</span><span class="sxs-lookup"><span data-stu-id="5d9bd-130">*pattern* as *identifier*</span></span>|`(a, b) as tuple1`|
|<span data-ttu-id="5d9bd-131">或模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-131">OR pattern</span></span>|<span data-ttu-id="5d9bd-132">*模式 1* &#124;*模式 2*</span><span class="sxs-lookup"><span data-stu-id="5d9bd-132">*pattern1* &#124; *pattern2*</span></span>|<code>([h] &#124; [h; _])</code>|
|<span data-ttu-id="5d9bd-133">和模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-133">AND pattern</span></span>|<span data-ttu-id="5d9bd-134">*模式 1* &amp; *模式 2*</span><span class="sxs-lookup"><span data-stu-id="5d9bd-134">*pattern1* &amp; *pattern2*</span></span>|`(a, b) & (_, "test")`|
|<span data-ttu-id="5d9bd-135">Cons 模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-135">Cons pattern</span></span>|<span data-ttu-id="5d9bd-136">*标识符*::*列表标识符*</span><span class="sxs-lookup"><span data-stu-id="5d9bd-136">*identifier* :: *list-identifier*</span></span>|`h :: t`|
|<span data-ttu-id="5d9bd-137">列表模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-137">List pattern</span></span>|<span data-ttu-id="5d9bd-138">[*模式 1*;...;*模式 n* ]</span><span class="sxs-lookup"><span data-stu-id="5d9bd-138">[ *pattern_1*; ... ; *pattern_n* ]</span></span>|`[ a; b; c ]`|
|<span data-ttu-id="5d9bd-139">数组模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-139">Array pattern</span></span>|<span data-ttu-id="5d9bd-140">[&#124;*模式 1*;..;*模式 n* &#124;]</span><span class="sxs-lookup"><span data-stu-id="5d9bd-140">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span></span>|<code>[&#124; a; b; c &#124;]</code>|
|<span data-ttu-id="5d9bd-141">带括号模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-141">Parenthesized pattern</span></span>|<span data-ttu-id="5d9bd-142">(*模式*)</span><span class="sxs-lookup"><span data-stu-id="5d9bd-142">( *pattern* )</span></span>|`( a )`|
|<span data-ttu-id="5d9bd-143">元组模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-143">Tuple pattern</span></span>|<span data-ttu-id="5d9bd-144">(*模式 1*，...，*模式 n* )</span><span class="sxs-lookup"><span data-stu-id="5d9bd-144">( *pattern_1*, ... , *pattern_n* )</span></span>|`( a, b )`|
|<span data-ttu-id="5d9bd-145">记录模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-145">Record pattern</span></span>|<span data-ttu-id="5d9bd-146">{ *identifier1* = *模式 1*;...;*标识符 n* = *模式 n* }</span><span class="sxs-lookup"><span data-stu-id="5d9bd-146">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span></span>|`{ Name = name; }`|
|<span data-ttu-id="5d9bd-147">通配符模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-147">Wildcard pattern</span></span>|<span data-ttu-id="5d9bd-148">_</span><span class="sxs-lookup"><span data-stu-id="5d9bd-148">_</span></span>|`_`|
|<span data-ttu-id="5d9bd-149">带有类型批注的模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-149">Pattern together with type annotation</span></span>|<span data-ttu-id="5d9bd-150">*模式*:*类型*</span><span class="sxs-lookup"><span data-stu-id="5d9bd-150">*pattern* : *type*</span></span>|`a : int`|
|<span data-ttu-id="5d9bd-151">类型测试模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-151">Type test pattern</span></span>|<span data-ttu-id="5d9bd-152">:?</span><span class="sxs-lookup"><span data-stu-id="5d9bd-152">:?</span></span> <span data-ttu-id="5d9bd-153">*类型*[作为*标识符*]</span><span class="sxs-lookup"><span data-stu-id="5d9bd-153">*type* [ as *identifier* ]</span></span>|`:? System.DateTime as dt`|
|<span data-ttu-id="5d9bd-154">Null 模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-154">Null pattern</span></span>|<span data-ttu-id="5d9bd-155">null</span><span class="sxs-lookup"><span data-stu-id="5d9bd-155">null</span></span>|`null`|

## <a name="constant-patterns"></a><span data-ttu-id="5d9bd-156">常量模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-156">Constant Patterns</span></span>
<span data-ttu-id="5d9bd-157">常量模式是数字、 字符和字符串文本、 枚举常量 （包括枚举类型名称）。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-157">Constant patterns are numeric, character, and string literals, enumeration constants (with the enumeration type name included).</span></span> <span data-ttu-id="5d9bd-158">A`match`只有常量模式的表达式可以与其他语言中的 case 语句进行比较。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-158">A `match` expression that has only constant patterns can be compared to a case statement in other languages.</span></span> <span data-ttu-id="5d9bd-159">输入比较的文字值，并且如果这些值相等，则匹配模式。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-159">The input is compared with the literal value and the pattern matches if the values are equal.</span></span> <span data-ttu-id="5d9bd-160">文本的类型必须与输入的类型兼容。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-160">The type of the literal must be compatible with the type of the input.</span></span>

<span data-ttu-id="5d9bd-161">下面的示例演示如何使用文本模式，并使用一个变量的模式和或模式。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-161">The following example demonstrates the use of literal patterns, and also uses a variable pattern and an OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

<span data-ttu-id="5d9bd-162">文本模式的另一个示例是基于枚举常量的模式。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-162">Another example of a literal pattern is a pattern based on enumeration constants.</span></span> <span data-ttu-id="5d9bd-163">当你使用枚举常量时，必须指定枚举类型名称。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-163">You must specify the enumeration type name when you use enumeration constants.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a><span data-ttu-id="5d9bd-164">标识符模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-164">Identifier Patterns</span></span>
<span data-ttu-id="5d9bd-165">如果该模式受窗体是有效的标识符的字符串，该标识符的形式将确定如何匹配的模式。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-165">If the pattern is a string of characters that forms a valid identifier, the form of the identifier determines how the pattern is matched.</span></span> <span data-ttu-id="5d9bd-166">如果标识符的长度超过单个字符，并且开头大写字符，编译器会尝试对标识符模式进行匹配。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-166">If the identifier is longer than a single character and starts with an uppercase character, the compiler tries to make a match to the identifier pattern.</span></span> <span data-ttu-id="5d9bd-167">此模式的标识符可能是标记的文本属性、 可区分联合用例、 异常标识符或活动模式用例的值。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-167">The identifier for this pattern could be a value marked with the Literal attribute, a discriminated union case, an exception identifier, or an active pattern case.</span></span> <span data-ttu-id="5d9bd-168">如果不找到任何匹配的标识符，则匹配失败和下一步模式规则，变量的模式中，输入与进行比较。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-168">If no matching identifier is found, the match fails and the next pattern rule, the variable pattern, is compared to the input.</span></span>

<span data-ttu-id="5d9bd-169">可区分联合模式可以是简单的名为情况下，或者它们可具有一个值或包含多个值的元组。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-169">Discriminated union patterns can be simple named cases or they can have a value, or a tuple containing multiple values.</span></span> <span data-ttu-id="5d9bd-170">如果没有一个值，则必须指定值的标识符。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-170">If there is a value, you must specify an identifier for the value.</span></span> <span data-ttu-id="5d9bd-171">对于一个元组，必须提供具有元组的每个元素的标识符或具有一个的字段名称的标识符的元组模式或多个命名联合的字段。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-171">In the case of a tuple, you must supply a tuple pattern with an identifier for each element of the tuple or an identifier with a field name for one or more named union fields.</span></span> <span data-ttu-id="5d9bd-172">请参阅本部分中用于示例的代码示例。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-172">See the code examples in this section for examples.</span></span>

<span data-ttu-id="5d9bd-173">`option`类型是具有两种情况下，可区分的联合`Some`和`None`。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-173">The `option` type is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="5d9bd-174">一种情况下 (`Some`) 具有一个值，而另 (`None`) 是只是命名的用例。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-174">One case (`Some`) has a value, but the other (`None`) is just a named case.</span></span> <span data-ttu-id="5d9bd-175">因此，`Some`需要具有与关联的值的变量`Some`分大小写，但`None`必须单独出现。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-175">Therefore, `Some` needs to have a variable for the value associated with the `Some` case, but `None` must appear by itself.</span></span> <span data-ttu-id="5d9bd-176">在下面的代码中，变量`var1`都提供了获得的匹配值`Some`用例。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-176">In the following code, the variable `var1` is given the value that is obtained by matching to the `Some` case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

<span data-ttu-id="5d9bd-177">在下面的示例中，`PersonName`可区分的联合包含混合的字符串和字符表示可能形式的名称。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-177">In the following example, the `PersonName` discriminated union contains a mixture of strings and characters that represent possible forms of names.</span></span> <span data-ttu-id="5d9bd-178">可区分联合的情形是`FirstOnly`， `LastOnly`，和`FirstLast`。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-178">The cases of the discriminated union are `FirstOnly`, `LastOnly`, and `FirstLast`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

<span data-ttu-id="5d9bd-179">对于已命名的字段的可区分联合，你使用等号 （=） 提取命名字段的值。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-179">For discriminated unions that have named fields, you use the equals sign (=) to extract the value of a named field.</span></span> <span data-ttu-id="5d9bd-180">例如，考虑如下所示的声明的可区分的联合。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-180">For example, consider a discriminated union with a declaration like the following.</span></span>

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

<span data-ttu-id="5d9bd-181">可以使用模式匹配的表达式中的命名的字段，如下所示。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-181">You can use the named fields in a pattern matching expression as follows.</span></span>

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

<span data-ttu-id="5d9bd-182">使用命名的字段是可选的因此在前面的示例中，同时`Circle(r)`和`Circle(radius = r)`具有相同的效果。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-182">The use of the named field is optional, so in the previous example, both `Circle(r)` and `Circle(radius = r)` have the same effect.</span></span>

<span data-ttu-id="5d9bd-183">当指定多个字段时，请使用分号 （;） 作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-183">When you specify multiple fields, use the semicolon (;) as a separator.</span></span>

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

<span data-ttu-id="5d9bd-184">活动模式，可定义更复杂的自定义模式匹配。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-184">Active patterns enable you to define more complex custom pattern matching.</span></span> <span data-ttu-id="5d9bd-185">有关活动模式的详细信息，请参阅[活动模式](active-patterns.md)。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-185">For more information about active patterns, see [Active Patterns](active-patterns.md).</span></span>

<span data-ttu-id="5d9bd-186">异常处理程序的上下文中匹配的模式中所用顺序标识符是一个例外的情况。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-186">The case in which the identifier is an exception is used in pattern matching in the context of exception handlers.</span></span> <span data-ttu-id="5d9bd-187">有关异常处理中的模式匹配的信息，请参阅[异常：`try...with`表达式](exception-handling/the-try-with-expression.md)。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-187">For information about pattern matching in exception handling, see [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>


## <a name="variable-patterns"></a><span data-ttu-id="5d9bd-188">变量模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-188">Variable Patterns</span></span>
<span data-ttu-id="5d9bd-189">变量模式将与变量名称，然后在右侧的执行表达式中使用该名称匹配的值分配`->`符号。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-189">The variable pattern assigns the value being matched to a variable name, which is then available for use in the execution expression to the right of the `->` symbol.</span></span> <span data-ttu-id="5d9bd-190">变量模式单独匹配任何输入，但变量模式通常出现在其他模式，因此启用更复杂的结构，例如，元组和阵列可以分解为变量。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-190">A variable pattern alone matches any input, but variable patterns often appear within other patterns, therefore enabling more complex structures such as tuples and arrays to be decomposed into variables.</span></span>

<span data-ttu-id="5d9bd-191">下面的示例演示在元组模式变量模式。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-191">The following example demonstrates a variable pattern within a tuple pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a><span data-ttu-id="5d9bd-192">as 模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-192">as Pattern</span></span>
<span data-ttu-id="5d9bd-193">`as`模式是一种模式具有`as`子句附加到它。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-193">The `as` pattern is a pattern that has an `as` clause appended to it.</span></span> <span data-ttu-id="5d9bd-194">`as`子句将匹配的值绑定到一个名称，可以用于在执行表达式的`match`表达式，或在此模式中的使用位置的情况下`let`绑定，名称将添加为一种绑定到本地作用域。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-194">The `as` clause binds the matched value to a name that can be used in the execution expression of a `match` expression, or, in the case where this pattern is used in a `let` binding, the name is added as a binding to the local scope.</span></span>

<span data-ttu-id="5d9bd-195">下面的示例使用`as`模式。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-195">The following example uses an `as` pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a><span data-ttu-id="5d9bd-196">或模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-196">OR Pattern</span></span>
<span data-ttu-id="5d9bd-197">当输入的数据可匹配多个模式，而你想要因此执行相同的代码，则使用 OR 模式。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-197">The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result.</span></span> <span data-ttu-id="5d9bd-198">OR 模式的两侧的类型必须兼容。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-198">The types of both sides of the OR pattern must be compatible.</span></span>

<span data-ttu-id="5d9bd-199">下面的示例演示 OR 模式。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-199">The following example demonstrates the OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a><span data-ttu-id="5d9bd-200">和模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-200">AND Pattern</span></span>
<span data-ttu-id="5d9bd-201">AND 模式要求输入匹配两种模式。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-201">The AND pattern requires that the input match two patterns.</span></span> <span data-ttu-id="5d9bd-202">AND 模式的两侧的类型必须兼容。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-202">The types of both sides of the AND pattern must be compatible.</span></span>

<span data-ttu-id="5d9bd-203">以下示例类似，`detectZeroTuple`中所示[元组模式](https://msdn.microsoft.com/library/#tuple)更高版本中本主题中，但此处这两个部分`var1`和`var2`通过使用 AND 模式获得作为值。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-203">The following example is like `detectZeroTuple` shown in the [Tuple Pattern](https://msdn.microsoft.com/library/#tuple) section later in this topic, but here both `var1` and `var2` are obtained as values by using the AND pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a><span data-ttu-id="5d9bd-204">Cons 模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-204">Cons Pattern</span></span>
<span data-ttu-id="5d9bd-205">Cons 模式用于将列表分解为第一个元素，*头*，并包含剩余元素的列表*结尾*。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-205">The cons pattern is used to decompose a list into the first element, the *head*, and a list that contains the remaining elements, the *tail*.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a><span data-ttu-id="5d9bd-206">列表模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-206">List Pattern</span></span>
<span data-ttu-id="5d9bd-207">列表模式使列表以分解成的元素数。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-207">The list pattern enables lists to be decomposed into a number of elements.</span></span> <span data-ttu-id="5d9bd-208">列表模式本身可以匹配的特定数量的元素组成的列表。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-208">The list pattern itself can match only lists of a specific number of elements.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a><span data-ttu-id="5d9bd-209">数组模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-209">Array Pattern</span></span>
<span data-ttu-id="5d9bd-210">数组模式与列表模式相似，并且可以用于将分解特定长度的数组。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-210">The array pattern resembles the list pattern and can be used to decompose arrays of a specific length.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a><span data-ttu-id="5d9bd-211">带括号模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-211">Parenthesized Pattern</span></span>
<span data-ttu-id="5d9bd-212">可以围绕模式以实现所需的关联性分组括号。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-212">Parentheses can be grouped around patterns to achieve the desired associativity.</span></span> <span data-ttu-id="5d9bd-213">在下面的示例中，使用括号来控制 AND 模式和 cons 模式之间的关联性。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-213">In the following example, parentheses are used to control associativity between an AND pattern and a cons pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a><span data-ttu-id="5d9bd-214">元组模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-214">Tuple Pattern</span></span>
<span data-ttu-id="5d9bd-215">元组模式与输入元组形式匹配并启用要进行分解为其构成元素，通过使用模式匹配的元组中每个位置的变量的元组。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-215">The tuple pattern matches input in tuple form and enables the tuple to be decomposed into its constituent elements by using pattern matching variables for each position in the tuple.</span></span>

<span data-ttu-id="5d9bd-216">下面的示例演示元组模式，并使用文本模式、 变量模式和通配符模式。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-216">The following example demonstrates the tuple pattern and also uses literal patterns, variable patterns, and the wildcard pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a><span data-ttu-id="5d9bd-217">记录模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-217">Record Pattern</span></span>
<span data-ttu-id="5d9bd-218">记录模式用于将分解记录提取字段的值。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-218">The record pattern is used to decompose records to extract the values of fields.</span></span> <span data-ttu-id="5d9bd-219">不需要引用所有字段的记录; 该记录模式任何省略的字段只需不参与匹配，然后将不会提取。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-219">The pattern does not have to reference all fields of the record; any omitted fields just do not participate in matching and are not extracted.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a><span data-ttu-id="5d9bd-220">通配符模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-220">Wildcard Pattern</span></span>
<span data-ttu-id="5d9bd-221">通配符模式由下划线 (`_`) 字符并匹配任何输入，就像的变量的模式一样，只不过输入将被丢弃而不是分配给变量。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-221">The wildcard pattern is represented by the underscore (`_`) character and matches any input, just like the variable pattern, except that the input is discarded instead of assigned to a variable.</span></span> <span data-ttu-id="5d9bd-222">通配符模式通常用于在其他模式作为占位符且无需在右侧的表达式的值`->`符号。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-222">The wildcard pattern is often used within other patterns as a placeholder for values that are not needed in the expression to the right of the `->` symbol.</span></span> <span data-ttu-id="5d9bd-223">也经常在模式的列表的末尾使用通配符模式匹配任何不匹配的输入。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-223">The wildcard pattern is also frequently used at the end of a list of patterns to match any unmatched input.</span></span> <span data-ttu-id="5d9bd-224">在本主题中的许多代码示例演示了通配符模式。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-224">The wildcard pattern is demonstrated in many code examples in this topic.</span></span> <span data-ttu-id="5d9bd-225">请参阅前面的代码示例。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-225">See the preceding code for one example.</span></span>


## <a name="patterns-that-have-type-annotations"></a><span data-ttu-id="5d9bd-226">具有类型批注的模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-226">Patterns That Have Type Annotations</span></span>
<span data-ttu-id="5d9bd-227">模式可以有类型批注。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-227">Patterns can have type annotations.</span></span> <span data-ttu-id="5d9bd-228">这些行为类似于其他类型批注和指导推理等其他类型批注。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-228">These behave like other type annotations and guide inference like other type annotations.</span></span> <span data-ttu-id="5d9bd-229">类型批注中模式要求使用括号。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-229">Parentheses are required around type annotations in patterns.</span></span> <span data-ttu-id="5d9bd-230">下面的代码演示具有的类型批注的模式。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-230">The following code shows a pattern that has a type annotation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a><span data-ttu-id="5d9bd-231">类型测试模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-231">Type Test Pattern</span></span>
<span data-ttu-id="5d9bd-232">类型测试模式用于匹配针对一种类型的输入。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-232">The type test pattern is used to match the input against a type.</span></span> <span data-ttu-id="5d9bd-233">如果输入的类型与匹配的项 （或派生的类型的） 都会成功在模式中，匹配指定的类型。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-233">If the input type is a match to (or a derived type of) the type specified in the pattern, the match succeeds.</span></span>

<span data-ttu-id="5d9bd-234">下面的示例演示类型测试模式。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-234">The following example demonstrates the type test pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a><span data-ttu-id="5d9bd-235">Null 模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-235">Null Pattern</span></span>
<span data-ttu-id="5d9bd-236">Null 模式匹配时你正在使用允许 null 值的类型，可能出现的 null 值。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-236">The null pattern matches the null value that can appear when you are working with types that allow a null value.</span></span> <span data-ttu-id="5d9bd-237">与.NET Framework 代码交互操作时，经常使用 null 模式。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-237">Null patterns are frequently used when interoperating with .NET Framework code.</span></span> <span data-ttu-id="5d9bd-238">例如，.NET API 的返回值可能的输入`match`表达式。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-238">For example, the return value of a .NET API might be the input to a `match` expression.</span></span> <span data-ttu-id="5d9bd-239">你可以控制程序流基于是否返回值为 null，并且也将在返回的值的其他特征。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-239">You can control program flow based on whether the return value is null, and also on other characteristics of the returned value.</span></span> <span data-ttu-id="5d9bd-240">Null 模式可用于防止 null 值传播到你的程序的其余部分。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-240">You can use the null pattern to prevent null values from propagating to the rest of your program.</span></span>

<span data-ttu-id="5d9bd-241">下面的示例使用 null 模式和变量的模式。</span><span class="sxs-lookup"><span data-stu-id="5d9bd-241">The following example uses the null pattern and the variable pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a><span data-ttu-id="5d9bd-242">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d9bd-242">See Also</span></span>
[<span data-ttu-id="5d9bd-243">match 表达式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-243">Match Expressions</span></span>](match-expressions.md)

[<span data-ttu-id="5d9bd-244">活动模式</span><span class="sxs-lookup"><span data-stu-id="5d9bd-244">Active Patterns</span></span>](active-patterns.md)

[<span data-ttu-id="5d9bd-245">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="5d9bd-245">F# Language Reference</span></span>](index.md)
