---
title: 异常：raise 函数 (F#)
description: 了解如何使用 F# raise 函数来指示已发生的错误或异常情况。
ms.date: 05/16/2016
ms.openlocfilehash: 537d274659d29404380bfdd56310ac267372bb98
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "43778254"
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="d1768-103">异常：raise 函数</span><span class="sxs-lookup"><span data-stu-id="d1768-103">Exceptions: the raise Function</span></span>

<span data-ttu-id="d1768-104">`raise`函数用来指示已发生的错误或异常情况。</span><span class="sxs-lookup"><span data-stu-id="d1768-104">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="d1768-105">异常对象中捕获有关错误的信息。</span><span class="sxs-lookup"><span data-stu-id="d1768-105">Information about the error is captured in an exception object.</span></span>

## <a name="syntax"></a><span data-ttu-id="d1768-106">语法</span><span class="sxs-lookup"><span data-stu-id="d1768-106">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="d1768-107">备注</span><span class="sxs-lookup"><span data-stu-id="d1768-107">Remarks</span></span>

<span data-ttu-id="d1768-108">`raise`函数生成的异常对象，并启动堆栈展开过程。</span><span class="sxs-lookup"><span data-stu-id="d1768-108">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="d1768-109">在堆栈展开过程由公共语言运行时 (CLR) 管理，因此与任何其他.NET 语言在此过程的行为都将是相同。</span><span class="sxs-lookup"><span data-stu-id="d1768-109">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="d1768-110">在堆栈展开过程是一个搜索匹配生成的异常的异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="d1768-110">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="d1768-111">在当前开始搜索`try...with`表达式，如果有的话。</span><span class="sxs-lookup"><span data-stu-id="d1768-111">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="d1768-112">在每个模式`with`按顺序块检查。</span><span class="sxs-lookup"><span data-stu-id="d1768-112">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="d1768-113">当找到匹配的异常处理程序时，异常将被视为已处理。否则，堆栈的展开和`with`直到找到匹配的处理程序，则检查调用链的块。</span><span class="sxs-lookup"><span data-stu-id="d1768-113">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="d1768-114">任何`finally`当堆栈展开，按顺序还执行调用链中遇到的块。</span><span class="sxs-lookup"><span data-stu-id="d1768-114">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="d1768-115">`raise`函数等同于`throw`C# 或 c + +。</span><span class="sxs-lookup"><span data-stu-id="d1768-115">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="d1768-116">使用`reraise`传播调用链相同的异常的 catch 处理程序中。</span><span class="sxs-lookup"><span data-stu-id="d1768-116">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="d1768-117">下面的代码示例说明如何使用`raise`函数生成异常。</span><span class="sxs-lookup"><span data-stu-id="d1768-117">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="d1768-118">`raise`函数还可用来引发.NET 异常，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="d1768-118">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a><span data-ttu-id="d1768-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1768-119">See also</span></span>

- [<span data-ttu-id="d1768-120">异常处理</span><span class="sxs-lookup"><span data-stu-id="d1768-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="d1768-121">异常类型</span><span class="sxs-lookup"><span data-stu-id="d1768-121">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="d1768-122">异常：`try...with` 表达式</span><span class="sxs-lookup"><span data-stu-id="d1768-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
- [<span data-ttu-id="d1768-123">异常：`try...finally` 表达式</span><span class="sxs-lookup"><span data-stu-id="d1768-123">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
- [<span data-ttu-id="d1768-124">异常：`failwith` 函数</span><span class="sxs-lookup"><span data-stu-id="d1768-124">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)
- [<span data-ttu-id="d1768-125">异常：`invalidArg` 函数</span><span class="sxs-lookup"><span data-stu-id="d1768-125">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)
