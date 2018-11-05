---
title: 匹配表达式 （F#）
description: 了解 F# 匹配表达式如何提供基于的表达式与一组模式的比较结果的分支控制。
ms.date: 04/19/2018
ms.openlocfilehash: e4cb82f20fe82bff562736557c2346562c557f59
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "44221839"
---
# <a name="match-expressions"></a><span data-ttu-id="40041-103">匹配表达式</span><span class="sxs-lookup"><span data-stu-id="40041-103">Match expressions</span></span>

<span data-ttu-id="40041-104">`match`表达式提供的表达式与一组模式的比较结果为基础的分支控制。</span><span class="sxs-lookup"><span data-stu-id="40041-104">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="40041-105">语法</span><span class="sxs-lookup"><span data-stu-id="40041-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="40041-106">备注</span><span class="sxs-lookup"><span data-stu-id="40041-106">Remarks</span></span>

<span data-ttu-id="40041-107">模式匹配表达式允许基于与一组模式的测试表达式比较复杂的分支。</span><span class="sxs-lookup"><span data-stu-id="40041-107">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="40041-108">在中`match`表达式中，*测试表达式*中打开，并找到匹配项，相应与每个模式进行比较*结果表达式*计算和生成的值是返回与匹配表达式的值。</span><span class="sxs-lookup"><span data-stu-id="40041-108">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="40041-109">模式匹配上一个语法中所示的函数是在哪种模式匹配是立即对自变量执行一个 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="40041-109">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="40041-110">等效于以下模式匹配函数，在上述语法中所示。</span><span class="sxs-lookup"><span data-stu-id="40041-110">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

<span data-ttu-id="40041-111">有关 lambda 表达式的详细信息，请参阅[Lambda 表达式：`fun`关键字](functions/lambda-expressions-the-fun-keyword.md)。</span><span class="sxs-lookup"><span data-stu-id="40041-111">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="40041-112">整个组模式应涵盖输入变量的所有可能的匹配项。</span><span class="sxs-lookup"><span data-stu-id="40041-112">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="40041-113">通常，您可以使用通配符模式 (`_`) 作为要匹配任何以前不匹配的输入的值的最后一个模式。</span><span class="sxs-lookup"><span data-stu-id="40041-113">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="40041-114">下面的代码演示了几种在其中`match`使用表达式。</span><span class="sxs-lookup"><span data-stu-id="40041-114">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="40041-115">引用和可用的所有可能模式的示例，请参阅[模式匹配](pattern-matching.md)。</span><span class="sxs-lookup"><span data-stu-id="40041-115">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="40041-116">模式的先决条件</span><span class="sxs-lookup"><span data-stu-id="40041-116">Guards on patterns</span></span>

<span data-ttu-id="40041-117">可以使用`when`子句来指定该变量必须满足与模式匹配的附加条件。</span><span class="sxs-lookup"><span data-stu-id="40041-117">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="40041-118">这样的子句被称为*防止*。</span><span class="sxs-lookup"><span data-stu-id="40041-118">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="40041-119">后面的表达式`when`除非与先决条件关联的模式进行匹配，则不会评估关键字。</span><span class="sxs-lookup"><span data-stu-id="40041-119">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="40041-120">下面的示例演示如何使用临界指定变量模式的数值范围。</span><span class="sxs-lookup"><span data-stu-id="40041-120">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="40041-121">请注意多个条件将结合使用布尔运算符。</span><span class="sxs-lookup"><span data-stu-id="40041-121">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="40041-122">请注意，由于不能在模式中使用文本之外的值，因此您必须使用`when`子句有部分输入与某个值进行比较。</span><span class="sxs-lookup"><span data-stu-id="40041-122">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="40041-123">以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="40041-123">This is shown in the following code:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

<span data-ttu-id="40041-124">请注意，当联合模式受防护，临界适用于**所有**的模式，而不仅仅是最后一个。</span><span class="sxs-lookup"><span data-stu-id="40041-124">Note that when a union pattern is covered by a guard, the guard applies to **all** of the patterns, not just the last one.</span></span> <span data-ttu-id="40041-125">例如，给定以下代码，临界`when a > 12`同时适用于`A a`和`B a`:</span><span class="sxs-lookup"><span data-stu-id="40041-125">For example, given the following code, the guard `when a > 12` applies to both `A a` and `B a`:</span></span>

```fsharp
type Union =
    | A of int
    | B of int

let foo() =
    let test = A 42
    match test with
    | A a
    | B a when a > 41 -> a // the guard applies to both patterns
    | _ -> 1

foo() // returns 42
```

## <a name="see-also"></a><span data-ttu-id="40041-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="40041-126">See also</span></span>

- [<span data-ttu-id="40041-127">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="40041-127">F# Language Reference</span></span>](index.md)  
- [<span data-ttu-id="40041-128">活动模式</span><span class="sxs-lookup"><span data-stu-id="40041-128">Active Patterns</span></span>](active-patterns.md)  
- [<span data-ttu-id="40041-129">模式匹配</span><span class="sxs-lookup"><span data-stu-id="40041-129">Pattern Matching</span></span>](pattern-matching.md)  
