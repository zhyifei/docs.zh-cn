---
title: 异常：try...finally 表达式
description: 了解F# "try .。。finally 表达式使你可以执行清理代码, 即使代码块引发异常也是如此。
ms.date: 05/16/2016
ms.openlocfilehash: 03fbda1ef5d55560232f0217f603fc04c0af0eb4
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630272"
---
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="25a64-103">异常：try...finally 表达式</span><span class="sxs-lookup"><span data-stu-id="25a64-103">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="25a64-104">`try...finally`表达式使你可以执行清理代码, 即使代码块引发异常也是如此。</span><span class="sxs-lookup"><span data-stu-id="25a64-104">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="25a64-105">语法</span><span class="sxs-lookup"><span data-stu-id="25a64-105">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="25a64-106">备注</span><span class="sxs-lookup"><span data-stu-id="25a64-106">Remarks</span></span>

<span data-ttu-id="25a64-107">表达式可用于执行前面语法中的表达式2中的代码, 而不管是否在执行*表达式*2 的过程中生成了异常。 `try...finally`</span><span class="sxs-lookup"><span data-stu-id="25a64-107">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="25a64-108">*表达式*2 的类型不影响整个表达式的值;异常不发生时返回的类型是*表达式*= 值中的最后一个值。</span><span class="sxs-lookup"><span data-stu-id="25a64-108">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="25a64-109">发生异常时, 不会返回任何值, 并且在调用堆栈上, 控制流传输到下一个匹配的异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="25a64-109">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="25a64-110">如果未找到异常处理程序, 程序将终止。</span><span class="sxs-lookup"><span data-stu-id="25a64-110">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="25a64-111">在执行匹配处理程序中的代码或程序终止之前, 执行`finally`分支中的代码。</span><span class="sxs-lookup"><span data-stu-id="25a64-111">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="25a64-112">下面的代码演示如何使用`try...finally`表达式。</span><span class="sxs-lookup"><span data-stu-id="25a64-112">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="25a64-113">控制台的输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="25a64-113">The output to the console is as follows.</span></span>

```
Closing stream
Exception handled.
```

<span data-ttu-id="25a64-114">正如您从输出中看到的那样, 流在外部异常处理前关闭, 并且该文件`test.txt`包含文本, 该文本`test1`指示缓冲区已刷新并写入磁盘 (即使传输的异常除外)对外部异常处理程序的控制。</span><span class="sxs-lookup"><span data-stu-id="25a64-114">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="25a64-115">请注意, `try...with`构造是一个独立`try...finally`于构造的构造。</span><span class="sxs-lookup"><span data-stu-id="25a64-115">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="25a64-116">因此, 如果代码需要`with`块`finally`和块, 则必须嵌套两个构造, 如下面的代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="25a64-116">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="25a64-117">在计算表达式 (包括序列表达式和异步工作流) 的上下文中,**尝试 .。。finally**表达式可以具有自定义实现。</span><span class="sxs-lookup"><span data-stu-id="25a64-117">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="25a64-118">有关详细信息, 请参阅[计算表达式](../computation-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="25a64-118">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="25a64-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="25a64-119">See also</span></span>

- [<span data-ttu-id="25a64-120">异常处理</span><span class="sxs-lookup"><span data-stu-id="25a64-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="25a64-121">异常：`try...with`表达式</span><span class="sxs-lookup"><span data-stu-id="25a64-121">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
