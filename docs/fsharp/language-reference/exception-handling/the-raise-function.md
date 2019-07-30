---
title: 异常：raise 函数
description: 了解如何使用F# "raise" 函数指示发生了错误或异常情况。
ms.date: 05/16/2016
ms.openlocfilehash: e0cc8da8310203c537b8081af8a225671bd8c6a3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630286"
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="14801-103">异常：raise 函数</span><span class="sxs-lookup"><span data-stu-id="14801-103">Exceptions: the raise Function</span></span>

<span data-ttu-id="14801-104">`raise`函数用于指示发生了错误或异常情况。</span><span class="sxs-lookup"><span data-stu-id="14801-104">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="14801-105">有关错误的信息在异常对象中捕获。</span><span class="sxs-lookup"><span data-stu-id="14801-105">Information about the error is captured in an exception object.</span></span>

## <a name="syntax"></a><span data-ttu-id="14801-106">语法</span><span class="sxs-lookup"><span data-stu-id="14801-106">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="14801-107">备注</span><span class="sxs-lookup"><span data-stu-id="14801-107">Remarks</span></span>

<span data-ttu-id="14801-108">`raise`函数生成异常对象并启动堆栈展开过程。</span><span class="sxs-lookup"><span data-stu-id="14801-108">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="14801-109">堆栈展开进程由公共语言运行时 (CLR) 管理, 因此此进程的行为与任何其他 .NET 语言中的行为相同。</span><span class="sxs-lookup"><span data-stu-id="14801-109">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="14801-110">堆栈展开过程是一个搜索与生成的异常匹配的异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="14801-110">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="14801-111">搜索从当前`try...with`表达式开始 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="14801-111">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="14801-112">将按顺序检查`with`块中的每个模式。</span><span class="sxs-lookup"><span data-stu-id="14801-112">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="14801-113">当找到匹配的异常处理程序时, 该异常将被视为已处理;否则, 将展开堆栈并`with`检查调用链, 直到找到匹配的处理程序。</span><span class="sxs-lookup"><span data-stu-id="14801-113">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="14801-114">如果`finally`堆栈展开, 则在调用链中遇到的任何块也将按顺序执行。</span><span class="sxs-lookup"><span data-stu-id="14801-114">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="14801-115">函数等效于或C++中的C# `throw` `raise`</span><span class="sxs-lookup"><span data-stu-id="14801-115">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="14801-116">在`reraise` catch 处理程序中使用以在调用链中向上传播相同的异常。</span><span class="sxs-lookup"><span data-stu-id="14801-116">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="14801-117">下面的代码示例演示了如何使用`raise`函数生成异常。</span><span class="sxs-lookup"><span data-stu-id="14801-117">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="14801-118">`raise`函数还可用于引发 .net 异常, 如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="14801-118">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a><span data-ttu-id="14801-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="14801-119">See also</span></span>

- [<span data-ttu-id="14801-120">异常处理</span><span class="sxs-lookup"><span data-stu-id="14801-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="14801-121">异常类型</span><span class="sxs-lookup"><span data-stu-id="14801-121">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="14801-122">异常：`try...with`表达式</span><span class="sxs-lookup"><span data-stu-id="14801-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
- [<span data-ttu-id="14801-123">异常：`try...finally`表达式</span><span class="sxs-lookup"><span data-stu-id="14801-123">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
- [<span data-ttu-id="14801-124">异常：`failwith`函数</span><span class="sxs-lookup"><span data-stu-id="14801-124">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)
- [<span data-ttu-id="14801-125">异常：`invalidArg`函数</span><span class="sxs-lookup"><span data-stu-id="14801-125">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)
