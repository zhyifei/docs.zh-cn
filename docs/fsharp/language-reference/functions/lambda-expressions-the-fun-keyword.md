---
title: Lambda 表达式:趣味关键字
description: 了解如何使用F# "趣味" 关键字定义 lambda 表达式, 这是匿名函数。
ms.date: 05/16/2016
ms.openlocfilehash: 9818724686dd83a7e352fb36819289fa19b002df
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630664"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a><span data-ttu-id="88236-103">Lambda 表达式:趣味关键字 (F#)</span><span class="sxs-lookup"><span data-stu-id="88236-103">Lambda Expressions: The fun Keyword (F#)</span></span>

<span data-ttu-id="88236-104">`fun`关键字用于定义 lambda 表达式, 即匿名函数。</span><span class="sxs-lookup"><span data-stu-id="88236-104">The `fun` keyword is used to define a lambda expression, that is, an anonymous function.</span></span>

## <a name="syntax"></a><span data-ttu-id="88236-105">语法</span><span class="sxs-lookup"><span data-stu-id="88236-105">Syntax</span></span>

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a><span data-ttu-id="88236-106">备注</span><span class="sxs-lookup"><span data-stu-id="88236-106">Remarks</span></span>

<span data-ttu-id="88236-107">*参数列表*通常包含名称和参数类型 (可选)。</span><span class="sxs-lookup"><span data-stu-id="88236-107">The *parameter-list* typically consists of names and, optionally, types of parameters.</span></span> <span data-ttu-id="88236-108">更常见的情况是,*参数列表*可以包含任何F#模式。</span><span class="sxs-lookup"><span data-stu-id="88236-108">More generally, the *parameter-list* can be composed of any F# patterns.</span></span> <span data-ttu-id="88236-109">有关可能模式的完整列表, 请参阅[模式匹配](../pattern-matching.md)。</span><span class="sxs-lookup"><span data-stu-id="88236-109">For a full list of possible patterns, see [Pattern Matching](../pattern-matching.md).</span></span> <span data-ttu-id="88236-110">有效参数的列表包括以下示例。</span><span class="sxs-lookup"><span data-stu-id="88236-110">Lists of valid parameters include the following examples.</span></span>

```fsharp
// Lambda expressions with parameter lists.
fun a b c -> ...
fun (a: int) b c -> ...
fun (a : int) (b : string) (c:float) -> ...

// A lambda expression with a tuple pattern.
fun (a, b) -> …

// A lambda expression with a list pattern.
fun head :: tail -> …
```

<span data-ttu-id="88236-111">*表达式*是函数的主体, 后者是生成返回值的的最后一个表达式。</span><span class="sxs-lookup"><span data-stu-id="88236-111">The *expression* is the body of the function, the last expression of which generates a return value.</span></span> <span data-ttu-id="88236-112">有效的 lambda 表达式的示例包括:</span><span class="sxs-lookup"><span data-stu-id="88236-112">Examples of valid lambda expressions include the following:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet301.fs)]

## <a name="using-lambda-expressions"></a><span data-ttu-id="88236-113">使用 Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="88236-113">Using Lambda Expressions</span></span>

<span data-ttu-id="88236-114">如果要对列表或其他集合执行操作, 并且想要避免定义函数的额外工作, Lambda 表达式特别有用。</span><span class="sxs-lookup"><span data-stu-id="88236-114">Lambda expressions are especially useful when you want to perform operations on a list or other collection and want to avoid the extra work of defining a function.</span></span> <span data-ttu-id="88236-115">许多F#库函数将函数值作为参数使用, 在这种情况下, 使用 lambda 表达式会非常方便。</span><span class="sxs-lookup"><span data-stu-id="88236-115">Many F# library functions take function values as arguments, and it can be especially convenient to use a lambda expression in those cases.</span></span> <span data-ttu-id="88236-116">下面的代码将 lambda 表达式应用于列表的元素。</span><span class="sxs-lookup"><span data-stu-id="88236-116">The following code applies a lambda expression to elements of a list.</span></span> <span data-ttu-id="88236-117">在这种情况下, 匿名函数向列表中的每个元素加1。</span><span class="sxs-lookup"><span data-stu-id="88236-117">In this case, the anonymous function adds 1 to every element of a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a><span data-ttu-id="88236-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="88236-118">See also</span></span>

- [<span data-ttu-id="88236-119">函数</span><span class="sxs-lookup"><span data-stu-id="88236-119">Functions</span></span>](index.md)
