---
title: 递归函数：rec 关键字 (F#)
description: 了解如何使用 let 关键字使用 F# rec 关键字定义的递归函数。
ms.date: 05/16/2016
ms.openlocfilehash: 5aab6ed8ab0fc3c0f0bcfc93c3ce6518ec53254f
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "48024514"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="fc47e-103">递归函数：rec 关键字</span><span class="sxs-lookup"><span data-stu-id="fc47e-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="fc47e-104">`rec`一起使用关键字`let`关键字来定义的递归函数。</span><span class="sxs-lookup"><span data-stu-id="fc47e-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="fc47e-105">语法</span><span class="sxs-lookup"><span data-stu-id="fc47e-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="fc47e-106">备注</span><span class="sxs-lookup"><span data-stu-id="fc47e-106">Remarks</span></span>

<span data-ttu-id="fc47e-107">递归函数，函数调用自身，F# 语言中显式标识。</span><span class="sxs-lookup"><span data-stu-id="fc47e-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="fc47e-108">这使正在定义的标识符可在函数的作用域中。</span><span class="sxs-lookup"><span data-stu-id="fc47e-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="fc47e-109">以下代码演示了递归函数，用于计算*n*<sup>th</sup>斐波纳契数。</span><span class="sxs-lookup"><span data-stu-id="fc47e-109">The following code illustrates a recursive function that computes the *n*<sup>th</sup> Fibonacci number.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
<span data-ttu-id="fc47e-110">在实践中，上面这类代码是一种浪费的内存和处理器时间，因为它涉及的以前计算的值重新计算。</span><span class="sxs-lookup"><span data-stu-id="fc47e-110">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>

<span data-ttu-id="fc47e-111">方法是隐式类型; 中递归无需添加`rec`关键字。</span><span class="sxs-lookup"><span data-stu-id="fc47e-111">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="fc47e-112">类中的 let 的绑定不是隐式递归。</span><span class="sxs-lookup"><span data-stu-id="fc47e-112">Let bindings within classes are not implicitly recursive.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="fc47e-113">相互递归函数</span><span class="sxs-lookup"><span data-stu-id="fc47e-113">Mutually Recursive Functions</span></span>

<span data-ttu-id="fc47e-114">函数是有时*相互递归*，这意味着调用形成了循环，其中一个函数调用另一个后者又调用第一个具有任意数量的调用之间。</span><span class="sxs-lookup"><span data-stu-id="fc47e-114">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="fc47e-115">您必须在一个一起定义此类函数`let`使用的绑定`and`关键字来将它们链接在一起。</span><span class="sxs-lookup"><span data-stu-id="fc47e-115">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="fc47e-116">下面的示例演示两个相互递归函数。</span><span class="sxs-lookup"><span data-stu-id="fc47e-116">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="fc47e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc47e-117">See also</span></span>

- [<span data-ttu-id="fc47e-118">函数</span><span class="sxs-lookup"><span data-stu-id="fc47e-118">Functions</span></span>](index.md)
