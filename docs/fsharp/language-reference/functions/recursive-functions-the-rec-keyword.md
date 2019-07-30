---
title: 递归函数:Rec 关键字
description: 了解如何将F# "rec" 关键字与 "let" 关键字一起使用, 以定义递归函数。
ms.date: 05/16/2016
ms.openlocfilehash: 7edaa7206b2109c7b1a405624b9b2330968f9c52
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630652"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="76a2e-103">递归函数:Rec 关键字</span><span class="sxs-lookup"><span data-stu-id="76a2e-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="76a2e-104">`rec` 关键字`let`与关键字一起用于定义递归函数。</span><span class="sxs-lookup"><span data-stu-id="76a2e-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="76a2e-105">语法</span><span class="sxs-lookup"><span data-stu-id="76a2e-105">Syntax</span></span>

```fsharp
// Recursive function:
let rec function-nameparameter-list =
function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
function1-body
and function2-nameparameter-list =
function2-body
...
```

## <a name="remarks"></a><span data-ttu-id="76a2e-106">备注</span><span class="sxs-lookup"><span data-stu-id="76a2e-106">Remarks</span></span>

<span data-ttu-id="76a2e-107">递归函数 (调用自身的函数) 是在F#语言中显式标识的。</span><span class="sxs-lookup"><span data-stu-id="76a2e-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="76a2e-108">这会使正在定义的标识符在函数作用域内可用。</span><span class="sxs-lookup"><span data-stu-id="76a2e-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="76a2e-109">下面的代码演示了计算<sup>第</sup> *n*个斐波那契数的递归函数。</span><span class="sxs-lookup"><span data-stu-id="76a2e-109">The following code illustrates a recursive function that computes the *n*<sup>th</sup> Fibonacci number.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> <span data-ttu-id="76a2e-110">在实践中, 类似于上面的代码会浪费内存和处理器时间, 因为它涉及到重新计算以前计算的值。</span><span class="sxs-lookup"><span data-stu-id="76a2e-110">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>

<span data-ttu-id="76a2e-111">方法在类型内隐式递归;无需添加`rec`关键字。</span><span class="sxs-lookup"><span data-stu-id="76a2e-111">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="76a2e-112">类中的 Let 绑定不隐式递归。</span><span class="sxs-lookup"><span data-stu-id="76a2e-112">Let bindings within classes are not implicitly recursive.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="76a2e-113">相互递归函数</span><span class="sxs-lookup"><span data-stu-id="76a2e-113">Mutually Recursive Functions</span></span>

<span data-ttu-id="76a2e-114">有时, 函数是*相互递归*的, 这意味着, 调用会形成一个圆圈, 其中一个函数调用另一个函数, 而后者又调用第一个, 并在之间进行任意数量的调用。</span><span class="sxs-lookup"><span data-stu-id="76a2e-114">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="76a2e-115">必须在一个`let`绑定中一起定义此类函数, `and`使用关键字将它们链接在一起。</span><span class="sxs-lookup"><span data-stu-id="76a2e-115">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="76a2e-116">下面的示例演示两个相互递归函数。</span><span class="sxs-lookup"><span data-stu-id="76a2e-116">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="76a2e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="76a2e-117">See also</span></span>

- [<span data-ttu-id="76a2e-118">函数</span><span class="sxs-lookup"><span data-stu-id="76a2e-118">Functions</span></span>](index.md)
