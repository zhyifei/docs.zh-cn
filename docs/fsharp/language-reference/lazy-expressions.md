---
title: 延迟表达式
description: 了解如何F#延迟表达式可以提高性能的应用程序和库。
ms.date: 03/13/2019
ms.openlocfilehash: 6d53d53093f4e93f53e1c956b94e2f1e4a1bbd55
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904106"
---
# <a name="lazy-expressions"></a><span data-ttu-id="f4697-103">延迟表达式</span><span class="sxs-lookup"><span data-stu-id="f4697-103">Lazy Expressions</span></span>

<span data-ttu-id="f4697-104">*延迟表达式*是不会立即开始，但改为在需要结果时计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="f4697-104">*Lazy expressions* are expressions that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="f4697-105">这可以帮助提高代码的性能。</span><span class="sxs-lookup"><span data-stu-id="f4697-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="f4697-106">语法</span><span class="sxs-lookup"><span data-stu-id="f4697-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="f4697-107">备注</span><span class="sxs-lookup"><span data-stu-id="f4697-107">Remarks</span></span>

<span data-ttu-id="f4697-108">在上述语法中，*表达式*是仅时结果是必需的将计算的代码并*标识符*是将结果存储的值。</span><span class="sxs-lookup"><span data-stu-id="f4697-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="f4697-109">值为类型[ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489)，其中的实际类型用于`'T`根据表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="f4697-109">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="f4697-110">延迟表达式，可以通过限制仅需要结果时这种情况下对表达式的执行，从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="f4697-110">Lazy expressions enable you to improve performance by restricting the execution of an expressions to only those situations in which a result is needed.</span></span>

<span data-ttu-id="f4697-111">若要强制执行的表达式，则调用方法`Force`。</span><span class="sxs-lookup"><span data-stu-id="f4697-111">To force the expressions to be performed, you call the method `Force`.</span></span> <span data-ttu-id="f4697-112">`Force` 将导致执行要执行仅一次。</span><span class="sxs-lookup"><span data-stu-id="f4697-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="f4697-113">对后续调用`Force`返回相同的结果，但不是执行任何代码。</span><span class="sxs-lookup"><span data-stu-id="f4697-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="f4697-114">下面的代码演示使用延迟表达式以及如何使用`Force`。</span><span class="sxs-lookup"><span data-stu-id="f4697-114">The following code illustrates the use of lazy expressions and the use of `Force`.</span></span> <span data-ttu-id="f4697-115">在此代码的类型`result`是`Lazy<int>`，并`Force`方法将返回`int`。</span><span class="sxs-lookup"><span data-stu-id="f4697-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="f4697-116">延迟计算，但不是`Lazy`类型，还可用于序列。</span><span class="sxs-lookup"><span data-stu-id="f4697-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="f4697-117">有关详细信息，请参阅[序列](sequences.md)。</span><span class="sxs-lookup"><span data-stu-id="f4697-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f4697-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4697-118">See also</span></span>

- [<span data-ttu-id="f4697-119">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="f4697-119">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="f4697-120">LazyExtensions 模块</span><span class="sxs-lookup"><span data-stu-id="f4697-120">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
