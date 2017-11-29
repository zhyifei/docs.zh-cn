---
title: "match 表达式 (F#)"
description: "了解如何 F # 匹配表达式提供基于表达式与一组模式进行比较的分支控制。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8854b713-255a-408d-942a-e80ab52fd2a4
ms.openlocfilehash: c8b9be744cfa7bc76f0d663b12abd66f8757fc56
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="match-expressions"></a><span data-ttu-id="a8240-104">match 表达式</span><span class="sxs-lookup"><span data-stu-id="a8240-104">Match Expressions</span></span>

<span data-ttu-id="a8240-105">`match`表达式提供基于表达式与一组模式进行比较的分支控制。</span><span class="sxs-lookup"><span data-stu-id="a8240-105">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="a8240-106">语法</span><span class="sxs-lookup"><span data-stu-id="a8240-106">Syntax</span></span>

```fsharp
// Match expression.
match test-expression with
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...

// Pattern matching function.
function
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...
```

## <a name="remarks"></a><span data-ttu-id="a8240-107">备注</span><span class="sxs-lookup"><span data-stu-id="a8240-107">Remarks</span></span>

<span data-ttu-id="a8240-108">模式匹配表达式允许基于与一组模式的测试表达式比较复杂分支。</span><span class="sxs-lookup"><span data-stu-id="a8240-108">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="a8240-109">在`match`表达式，*测试表达式*中打开，并找到匹配项，相应与每个模式进行比较*结果表达式*计算和生成的值返回作为匹配表达式的值。</span><span class="sxs-lookup"><span data-stu-id="a8240-109">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="a8240-110">匹配函数在上述语法中所示的模式是 lambda 表达式的模式中执行匹配立即对的自变量。</span><span class="sxs-lookup"><span data-stu-id="a8240-110">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="a8240-111">等效于以下的模式匹配函数在上述语法中所示。</span><span class="sxs-lookup"><span data-stu-id="a8240-111">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```    

<span data-ttu-id="a8240-112">有关 lambda 表达式的详细信息，请参阅[Lambda 表达式：`fun`关键字](functions/lambda-expressions-the-fun-keyword.md)。</span><span class="sxs-lookup"><span data-stu-id="a8240-112">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="a8240-113">模式的整个集应涵盖所有可能的匹配项的输入变量。</span><span class="sxs-lookup"><span data-stu-id="a8240-113">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="a8240-114">通常，使用通配符模式 (`_`) 作为要匹配任何以前不匹配的输入的值的最后一个模式。</span><span class="sxs-lookup"><span data-stu-id="a8240-114">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="a8240-115">下面的代码演示了几种在其中`match`使用表达式。</span><span class="sxs-lookup"><span data-stu-id="a8240-115">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="a8240-116">有关引用和可用的所有可能模式的示例，请参阅[模式匹配](pattern-matching.md)。</span><span class="sxs-lookup"><span data-stu-id="a8240-116">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="a8240-117">模式的先决条件</span><span class="sxs-lookup"><span data-stu-id="a8240-117">Guards on Patterns</span></span>

<span data-ttu-id="a8240-118">你可以使用`when`子句指定的变量必须满足与模式匹配的其他条件。</span><span class="sxs-lookup"><span data-stu-id="a8240-118">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="a8240-119">这样的子句被称为*防止*。</span><span class="sxs-lookup"><span data-stu-id="a8240-119">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="a8240-120">表达式以下`when`除非到与该防护关联的模式进行匹配，则不会评估关键字。</span><span class="sxs-lookup"><span data-stu-id="a8240-120">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="a8240-121">下面的示例演示如何使用临界来指定变量的模式的数值范围。</span><span class="sxs-lookup"><span data-stu-id="a8240-121">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="a8240-122">请注意，多个条件将结合使用布尔运算符。</span><span class="sxs-lookup"><span data-stu-id="a8240-122">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="a8240-123">请注意，因为文本以外的值不能使用模式中，你必须使用`when`子句，前提部分输入与某个值进行比较。</span><span class="sxs-lookup"><span data-stu-id="a8240-123">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="a8240-124">以下代码对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="a8240-124">This is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

## <a name="see-also"></a><span data-ttu-id="a8240-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8240-125">See Also</span></span>

[<span data-ttu-id="a8240-126">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="a8240-126">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="a8240-127">活动模式</span><span class="sxs-lookup"><span data-stu-id="a8240-127">Active Patterns</span></span>](active-patterns.md)

[<span data-ttu-id="a8240-128">模式匹配</span><span class="sxs-lookup"><span data-stu-id="a8240-128">Pattern Matching</span></span>](pattern-matching.md)
