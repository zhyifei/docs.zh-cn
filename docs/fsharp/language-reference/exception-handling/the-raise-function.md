---
title: "异常：raise 函数 (F#)"
description: "了解如何使用 F # 引发函数以指示已发生的错误或异常情况。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b00da469-4789-4cdd-9f77-7a2e29f28637
ms.openlocfilehash: dc524a06d075b982a6aa1fd266769bfc7d883517
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="570b1-104">异常：raise 函数</span><span class="sxs-lookup"><span data-stu-id="570b1-104">Exceptions: the raise Function</span></span>

<span data-ttu-id="570b1-105">`raise`函数用于指示已发生的错误或异常情况。</span><span class="sxs-lookup"><span data-stu-id="570b1-105">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="570b1-106">在异常对象中捕获有关错误的信息。</span><span class="sxs-lookup"><span data-stu-id="570b1-106">Information about the error is captured in an exception object.</span></span>


## <a name="syntax"></a><span data-ttu-id="570b1-107">语法</span><span class="sxs-lookup"><span data-stu-id="570b1-107">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="570b1-108">备注</span><span class="sxs-lookup"><span data-stu-id="570b1-108">Remarks</span></span>
<span data-ttu-id="570b1-109">`raise`函数将生成的异常对象，并启动堆栈展开过程。</span><span class="sxs-lookup"><span data-stu-id="570b1-109">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="570b1-110">在堆栈展开过程是由公共语言运行时 (CLR) 托管，因此此进程的行为是相同因为它是任何其他.NET 语言中。</span><span class="sxs-lookup"><span data-stu-id="570b1-110">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="570b1-111">在堆栈展开过程是一个搜索匹配所生成的异常的异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="570b1-111">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="570b1-112">在当前开始搜索`try...with`表达式，如果有一个。</span><span class="sxs-lookup"><span data-stu-id="570b1-112">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="570b1-113">在每个模式`with`按顺序块检查。</span><span class="sxs-lookup"><span data-stu-id="570b1-113">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="570b1-114">当找到匹配的异常处理程序时，将异常认为是已处理。否则，堆栈的展开和`with`直到找到匹配的处理，则检查调用链中向上的块。</span><span class="sxs-lookup"><span data-stu-id="570b1-114">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="570b1-115">任何`finally`当堆栈展开，按顺序还执行的调用链中遇到的块。</span><span class="sxs-lookup"><span data-stu-id="570b1-115">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="570b1-116">`raise`函数等同于`throw`C# 或 c + +。</span><span class="sxs-lookup"><span data-stu-id="570b1-116">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="570b1-117">使用`reraise`catch 处理程序来传播此同一异常向上的调用链中。</span><span class="sxs-lookup"><span data-stu-id="570b1-117">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="570b1-118">下面的代码示例阐释使用`raise`函数生成异常。</span><span class="sxs-lookup"><span data-stu-id="570b1-118">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="570b1-119">`raise`函数还可引发.NET 异常，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="570b1-119">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]
    
## <a name="see-also"></a><span data-ttu-id="570b1-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="570b1-120">See Also</span></span>
[<span data-ttu-id="570b1-121">异常处理</span><span class="sxs-lookup"><span data-stu-id="570b1-121">Exception Handling</span></span>](index.md)

[<span data-ttu-id="570b1-122">异常类型</span><span class="sxs-lookup"><span data-stu-id="570b1-122">Exception Types</span></span>](exception-types.md)

[<span data-ttu-id="570b1-123">异常：`try...with` 表达式</span><span class="sxs-lookup"><span data-stu-id="570b1-123">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)

[<span data-ttu-id="570b1-124">异常：`try...finally` 表达式</span><span class="sxs-lookup"><span data-stu-id="570b1-124">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)

[<span data-ttu-id="570b1-125">异常：`failwith` 函数</span><span class="sxs-lookup"><span data-stu-id="570b1-125">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)

[<span data-ttu-id="570b1-126">异常：`invalidArg` 函数</span><span class="sxs-lookup"><span data-stu-id="570b1-126">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)
