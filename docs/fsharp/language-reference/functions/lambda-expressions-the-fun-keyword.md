---
title: "Lambda 表达式：fun 关键字 (F#)"
description: "了解如何使用 F # 的有趣关键字定义 lambda 表达式，这是一个匿名函数。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e5d3565c-d7cc-433f-a619-886ed92523a7
ms.openlocfilehash: 09f1c1787bbb4b86ec40f9e973e08104919631aa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="lambda-expressions-the-fun-keyword-f"></a><span data-ttu-id="416bc-104">Lambda 表达式：fun 关键字 (F#)</span><span class="sxs-lookup"><span data-stu-id="416bc-104">Lambda Expressions: The fun Keyword (F#)</span></span>

<span data-ttu-id="416bc-105">`fun`关键字用于定义 lambda 表达式，即一个匿名函数。</span><span class="sxs-lookup"><span data-stu-id="416bc-105">The `fun` keyword is used to define a lambda expression, that is, an anonymous function.</span></span>


## <a name="syntax"></a><span data-ttu-id="416bc-106">语法</span><span class="sxs-lookup"><span data-stu-id="416bc-106">Syntax</span></span>

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a><span data-ttu-id="416bc-107">备注</span><span class="sxs-lookup"><span data-stu-id="416bc-107">Remarks</span></span>
<span data-ttu-id="416bc-108">*参数列表*通常由名称和参数类型，（可选） 组成。</span><span class="sxs-lookup"><span data-stu-id="416bc-108">The *parameter-list* typically consists of names and, optionally, types of parameters.</span></span> <span data-ttu-id="416bc-109">一般来说，*参数列表*可由任何 F # 模式组成。</span><span class="sxs-lookup"><span data-stu-id="416bc-109">More generally, the *parameter-list* can be composed of any F# patterns.</span></span> <span data-ttu-id="416bc-110">有关可能模式的完整列表，请参阅[模式匹配](../pattern-matching.md)。</span><span class="sxs-lookup"><span data-stu-id="416bc-110">For a full list of possible patterns, see [Pattern Matching](../pattern-matching.md).</span></span> <span data-ttu-id="416bc-111">有效参数列表包含下面的示例。</span><span class="sxs-lookup"><span data-stu-id="416bc-111">Lists of valid parameters include the following examples.</span></span>

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

<span data-ttu-id="416bc-112">*表达式*是的函数，其中的最后一个表达式将生成一个返回值的正文。</span><span class="sxs-lookup"><span data-stu-id="416bc-112">The *expression* is the body of the function, the last expression of which generates a return value.</span></span> <span data-ttu-id="416bc-113">有效的 lambda 表达式的示例包括：</span><span class="sxs-lookup"><span data-stu-id="416bc-113">Examples of valid lambda expressions include the following:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]
    
## <a name="using-lambda-expressions"></a><span data-ttu-id="416bc-114">使用 Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="416bc-114">Using Lambda Expressions</span></span>
<span data-ttu-id="416bc-115">如果你想要对列表或其他集合执行操作并想要避免定义函数的额外工作，lambda 表达式是特别有用。</span><span class="sxs-lookup"><span data-stu-id="416bc-115">Lambda expressions are especially useful when you want to perform operations on a list or other collection and want to avoid the extra work of defining a function.</span></span> <span data-ttu-id="416bc-116">许多 F # 库函数采用函数值作为参数，而且还会特别方便在这些情况下使用 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="416bc-116">Many F# library functions take function values as arguments, and it can be especially convenient to use a lambda expression in those cases.</span></span> <span data-ttu-id="416bc-117">下面的代码将 lambda 表达式应用于列表中的元素。</span><span class="sxs-lookup"><span data-stu-id="416bc-117">The following code applies a lambda expression to elements of a list.</span></span> <span data-ttu-id="416bc-118">在这种情况下，匿名函数将 1 添加到列表中的每个元素。</span><span class="sxs-lookup"><span data-stu-id="416bc-118">In this case, the anonymous function adds 1 to every element of a list.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]
    
## <a name="see-also"></a><span data-ttu-id="416bc-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="416bc-119">See Also</span></span>
[<span data-ttu-id="416bc-120">函数</span><span class="sxs-lookup"><span data-stu-id="416bc-120">Functions</span></span>](index.md)
