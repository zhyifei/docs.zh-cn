---
title: "延迟计算 (F#)"
description: "了解如何 F # 延迟计算可以提高应用程序和库的性能。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3499293e-1d53-4b02-b764-f687fbdaa7fe
ms.openlocfilehash: 984c96ab68a8919e2382eefe8260b07f191027dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="lazy-computations"></a><span data-ttu-id="6f9f2-104">延迟计算</span><span class="sxs-lookup"><span data-stu-id="6f9f2-104">Lazy Computations</span></span>

<span data-ttu-id="6f9f2-105">*延迟计算*是不立即计算的值，但需要结果时，将改为计算的计算。</span><span class="sxs-lookup"><span data-stu-id="6f9f2-105">*Lazy computations* are computations that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="6f9f2-106">这可以帮助提高你的代码的性能。</span><span class="sxs-lookup"><span data-stu-id="6f9f2-106">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="6f9f2-107">语法</span><span class="sxs-lookup"><span data-stu-id="6f9f2-107">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="6f9f2-108">备注</span><span class="sxs-lookup"><span data-stu-id="6f9f2-108">Remarks</span></span>

<span data-ttu-id="6f9f2-109">在上述语法中，*表达式*是仅当结果是必需的时, 计算的代码和*标识符*是将结果存储的值。</span><span class="sxs-lookup"><span data-stu-id="6f9f2-109">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="6f9f2-110">值的类型是[ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489)，其中的实际类型用于`'T`取决于该表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="6f9f2-110">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="6f9f2-111">延迟计算使您能够通过限制为仅需要结果时这种情况下计算执行改进性能。</span><span class="sxs-lookup"><span data-stu-id="6f9f2-111">Lazy computations enable you to improve performance by restricting the execution of a computation to only those situations in which a result is needed.</span></span>

<span data-ttu-id="6f9f2-112">若要强制要执行的计算，则调用方法`Force`。</span><span class="sxs-lookup"><span data-stu-id="6f9f2-112">To force the computation to be performed, you call the method `Force`.</span></span> <span data-ttu-id="6f9f2-113">`Force`会导致将仅执行一次执行。</span><span class="sxs-lookup"><span data-stu-id="6f9f2-113">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="6f9f2-114">后续调用`Force`返回相同的结果，但不是执行任何代码。</span><span class="sxs-lookup"><span data-stu-id="6f9f2-114">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="6f9f2-115">下面的代码演示延迟计算的使用和的`Force`。</span><span class="sxs-lookup"><span data-stu-id="6f9f2-115">The following code illustrates the use of lazy computation and the use of `Force`.</span></span> <span data-ttu-id="6f9f2-116">在此代码中的一种`result`是`Lazy<int>`，和`Force`方法返回`int`。</span><span class="sxs-lookup"><span data-stu-id="6f9f2-116">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="6f9f2-117">迟缓计算中，但不是`Lazy`类型，也可以用来序列。</span><span class="sxs-lookup"><span data-stu-id="6f9f2-117">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="6f9f2-118">有关详细信息，请参阅[序列](sequences.md)。</span><span class="sxs-lookup"><span data-stu-id="6f9f2-118">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6f9f2-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f9f2-119">See Also</span></span>

[<span data-ttu-id="6f9f2-120">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="6f9f2-120">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="6f9f2-121">LazyExtensions 模块</span><span class="sxs-lookup"><span data-stu-id="6f9f2-121">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
