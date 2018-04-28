---
title: 递归函数：rec 关键字 (F#)
description: '了解如何 F # 建议关键字用于使用 let 关键字定义的递归函数。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 1f5302c125605d2186deab0bbeaf2e84cc51edc3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="5d981-103">递归函数：rec 关键字</span><span class="sxs-lookup"><span data-stu-id="5d981-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="5d981-104">`rec`连同使用关键字`let`关键字来定义的递归函数。</span><span class="sxs-lookup"><span data-stu-id="5d981-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>


## <a name="syntax"></a><span data-ttu-id="5d981-105">语法</span><span class="sxs-lookup"><span data-stu-id="5d981-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="5d981-106">备注</span><span class="sxs-lookup"><span data-stu-id="5d981-106">Remarks</span></span>
<span data-ttu-id="5d981-107">递归函数，自身，调用的函数进行显式标识的 F # 语言。</span><span class="sxs-lookup"><span data-stu-id="5d981-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="5d981-108">这使正在定义的标识符可在该函数的作用域。</span><span class="sxs-lookup"><span data-stu-id="5d981-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="5d981-109">下面的代码演示计算的递归函数*n*第斐波那契数。</span><span class="sxs-lookup"><span data-stu-id="5d981-109">The following code illustrates a recursive function that computes the *n*th Fibonacci number.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
<span data-ttu-id="5d981-110">在实践中，上面这类代码是一种浪费的内存和处理器时间，因为它涉及的以前计算的值重新计算功能。</span><span class="sxs-lookup"><span data-stu-id="5d981-110">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>


<span data-ttu-id="5d981-111">方法是隐式类型; 中的递归无需添加`rec`关键字。</span><span class="sxs-lookup"><span data-stu-id="5d981-111">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="5d981-112">类中的 let 的绑定不是隐式递归。</span><span class="sxs-lookup"><span data-stu-id="5d981-112">Let bindings within classes are not implicitly recursive.</span></span>


## <a name="mutually-recursive-functions"></a><span data-ttu-id="5d981-113">相互递归函数</span><span class="sxs-lookup"><span data-stu-id="5d981-113">Mutually Recursive Functions</span></span>
<span data-ttu-id="5d981-114">有时函数是*相互递归*，这意味着调用形成了循环，其中一个函数调用另后者又包含任意数量的调用将调用第一个之间。</span><span class="sxs-lookup"><span data-stu-id="5d981-114">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="5d981-115">你必须在一个一起定义此类函数`let`绑定，使用`and`关键字来将它们链接在一起。</span><span class="sxs-lookup"><span data-stu-id="5d981-115">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="5d981-116">下面的示例显示了两个相互递归函数。</span><span class="sxs-lookup"><span data-stu-id="5d981-116">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="5d981-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d981-117">See Also</span></span>
[<span data-ttu-id="5d981-118">函数</span><span class="sxs-lookup"><span data-stu-id="5d981-118">Functions</span></span>](index.md)
