---
title: 延迟计算 (F#)
description: '了解如何 F # 延迟计算可以提高应用程序和库的性能。'
ms.date: 05/16/2016
ms.openlocfilehash: 1c4eb6ab247c44a04a9d145185e2de7ec01b8e0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563927"
---
# <a name="lazy-computations"></a><span data-ttu-id="f3243-103">延迟计算</span><span class="sxs-lookup"><span data-stu-id="f3243-103">Lazy Computations</span></span>

<span data-ttu-id="f3243-104">*延迟计算*是不立即计算的值，但需要结果时，将改为计算的计算。</span><span class="sxs-lookup"><span data-stu-id="f3243-104">*Lazy computations* are computations that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="f3243-105">这可以帮助提高你的代码的性能。</span><span class="sxs-lookup"><span data-stu-id="f3243-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="f3243-106">语法</span><span class="sxs-lookup"><span data-stu-id="f3243-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="f3243-107">备注</span><span class="sxs-lookup"><span data-stu-id="f3243-107">Remarks</span></span>

<span data-ttu-id="f3243-108">在上述语法中，*表达式*是仅当结果是必需的时, 计算的代码和*标识符*是将结果存储的值。</span><span class="sxs-lookup"><span data-stu-id="f3243-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="f3243-109">值的类型是[ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489)，其中的实际类型用于`'T`取决于该表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="f3243-109">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="f3243-110">延迟计算使您能够通过限制为仅需要结果时这种情况下计算执行改进性能。</span><span class="sxs-lookup"><span data-stu-id="f3243-110">Lazy computations enable you to improve performance by restricting the execution of a computation to only those situations in which a result is needed.</span></span>

<span data-ttu-id="f3243-111">若要强制要执行的计算，则调用方法`Force`。</span><span class="sxs-lookup"><span data-stu-id="f3243-111">To force the computation to be performed, you call the method `Force`.</span></span> <span data-ttu-id="f3243-112">`Force` 会导致将仅执行一次执行。</span><span class="sxs-lookup"><span data-stu-id="f3243-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="f3243-113">后续调用`Force`返回相同的结果，但不是执行任何代码。</span><span class="sxs-lookup"><span data-stu-id="f3243-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="f3243-114">下面的代码演示延迟计算的使用和的`Force`。</span><span class="sxs-lookup"><span data-stu-id="f3243-114">The following code illustrates the use of lazy computation and the use of `Force`.</span></span> <span data-ttu-id="f3243-115">在此代码中的一种`result`是`Lazy<int>`，和`Force`方法返回`int`。</span><span class="sxs-lookup"><span data-stu-id="f3243-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="f3243-116">迟缓计算中，但不是`Lazy`类型，也可以用来序列。</span><span class="sxs-lookup"><span data-stu-id="f3243-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="f3243-117">有关详细信息，请参阅[序列](sequences.md)。</span><span class="sxs-lookup"><span data-stu-id="f3243-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f3243-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3243-118">See Also</span></span>

[<span data-ttu-id="f3243-119">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="f3243-119">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="f3243-120">LazyExtensions 模块</span><span class="sxs-lookup"><span data-stu-id="f3243-120">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
