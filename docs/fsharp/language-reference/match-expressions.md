---
title: 匹配表达式
description: 了解F# match 表达式如何提供基于表达式与一组模式比较的分支控件。
ms.date: 04/19/2018
ms.openlocfilehash: 222cb0604300039d86ed0c80293651631d212eb6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627606"
---
# <a name="match-expressions"></a><span data-ttu-id="b8923-103">匹配表达式</span><span class="sxs-lookup"><span data-stu-id="b8923-103">Match expressions</span></span>

<span data-ttu-id="b8923-104">`match`表达式提供基于表达式与一组模式比较的分支控件。</span><span class="sxs-lookup"><span data-stu-id="b8923-104">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="b8923-105">语法</span><span class="sxs-lookup"><span data-stu-id="b8923-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="b8923-106">备注</span><span class="sxs-lookup"><span data-stu-id="b8923-106">Remarks</span></span>

<span data-ttu-id="b8923-107">模式匹配表达式允许基于测试表达式与一组模式的比较来实现复杂的分支。</span><span class="sxs-lookup"><span data-stu-id="b8923-107">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="b8923-108">在表达式中,*测试表达式*依次与每个模式进行比较, 当找到匹配项时, 将计算相应的*结果表达式*, 并将结果值作为匹配表达式的值返回。 `match`</span><span class="sxs-lookup"><span data-stu-id="b8923-108">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="b8923-109">前面的语法中所示的模式匹配函数是一个 lambda 表达式, 该表达式中的模式匹配会立即在参数上执行。</span><span class="sxs-lookup"><span data-stu-id="b8923-109">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="b8923-110">上面的语法中所示的模式匹配函数等效于以下形式。</span><span class="sxs-lookup"><span data-stu-id="b8923-110">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

<span data-ttu-id="b8923-111">有关 lambda 表达式的详细信息, 请[参阅 lambda 表达式:`fun`关键字。](./functions/lambda-expressions-the-fun-keyword.md)</span><span class="sxs-lookup"><span data-stu-id="b8923-111">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](./functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="b8923-112">整个模式集应涵盖输入变量的所有可能的匹配项。</span><span class="sxs-lookup"><span data-stu-id="b8923-112">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="b8923-113">通常, 使用通配符模式 (`_`) 作为最后一种模式, 以匹配任何以前未匹配的输入值。</span><span class="sxs-lookup"><span data-stu-id="b8923-113">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="b8923-114">下面的代码演示了使用`match`表达式的部分方法。</span><span class="sxs-lookup"><span data-stu-id="b8923-114">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="b8923-115">有关可以使用的所有可能模式的参考和示例, 请参阅[模式匹配](pattern-matching.md)。</span><span class="sxs-lookup"><span data-stu-id="b8923-115">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="b8923-116">模式保护</span><span class="sxs-lookup"><span data-stu-id="b8923-116">Guards on patterns</span></span>

<span data-ttu-id="b8923-117">您可以使用`when`子句来指定变量为匹配模式而必须满足的附加条件。</span><span class="sxs-lookup"><span data-stu-id="b8923-117">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="b8923-118">此类子句称为*临界*。</span><span class="sxs-lookup"><span data-stu-id="b8923-118">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="b8923-119">除非对与该`when`保护关联的模式进行匹配, 否则不会计算关键字后面的表达式。</span><span class="sxs-lookup"><span data-stu-id="b8923-119">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="b8923-120">下面的示例说明了如何使用临界指定变量模式的数值范围。</span><span class="sxs-lookup"><span data-stu-id="b8923-120">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="b8923-121">请注意, 使用布尔运算符组合多个条件。</span><span class="sxs-lookup"><span data-stu-id="b8923-121">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="b8923-122">请注意, 由于不能在模式中使用文本以外的值, 因此, 如果`when`必须将部分输入与值进行比较, 则必须使用子句。</span><span class="sxs-lookup"><span data-stu-id="b8923-122">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="b8923-123">下面的代码对此进行了演示：</span><span class="sxs-lookup"><span data-stu-id="b8923-123">This is shown in the following code:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

<span data-ttu-id="b8923-124">请注意, 当联合模式被临界覆盖时, 此防护将应用于**所有**模式, 而不仅仅是最后一个。</span><span class="sxs-lookup"><span data-stu-id="b8923-124">Note that when a union pattern is covered by a guard, the guard applies to **all** of the patterns, not just the last one.</span></span> <span data-ttu-id="b8923-125">例如, 在以下代码中, guard `when a > 12`适用`A a`于和`B a`:</span><span class="sxs-lookup"><span data-stu-id="b8923-125">For example, given the following code, the guard `when a > 12` applies to both `A a` and `B a`:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b8923-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8923-126">See also</span></span>

- [<span data-ttu-id="b8923-127">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="b8923-127">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="b8923-128">活动模式</span><span class="sxs-lookup"><span data-stu-id="b8923-128">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="b8923-129">模式匹配</span><span class="sxs-lookup"><span data-stu-id="b8923-129">Pattern Matching</span></span>](pattern-matching.md)
