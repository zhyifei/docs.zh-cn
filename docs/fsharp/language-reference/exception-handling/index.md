---
title: 异常处理 (F#)
description: 了解中的异常处理的基础知识F#并找到异常处理的表达式和函数的链接。
ms.date: 05/16/2016
ms.openlocfilehash: fc89feb0d21bc823cb105e435413f8309cd6174c
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "33564321"
---
# <a name="exception-handling"></a><span data-ttu-id="41bdf-103">异常处理</span><span class="sxs-lookup"><span data-stu-id="41bdf-103">Exception Handling</span></span>

<span data-ttu-id="41bdf-104">此部分包含 F# 语言中的异常处理支持信息。</span><span class="sxs-lookup"><span data-stu-id="41bdf-104">This section contains information about exception handling support in the F# language.</span></span>


## <a name="exception-handling-basics"></a><span data-ttu-id="41bdf-105">异常处理基本知识</span><span class="sxs-lookup"><span data-stu-id="41bdf-105">Exception Handling Basics</span></span>
<span data-ttu-id="41bdf-106">异常处理是在 .NET Framework 中处理错误条件的标准方法。</span><span class="sxs-lookup"><span data-stu-id="41bdf-106">Exception handling is the standard way of handling error conditions in the .NET Framework.</span></span> <span data-ttu-id="41bdf-107">因此，任何 .NET 语言都必须支持此机制，包括 F# 在内。</span><span class="sxs-lookup"><span data-stu-id="41bdf-107">Thus, any .NET language must support this mechanism, including F#.</span></span> <span data-ttu-id="41bdf-108">异常是一个封装了有关错误的信息的对象。</span><span class="sxs-lookup"><span data-stu-id="41bdf-108">An *exception* is an object that encapsulates information about an error.</span></span> <span data-ttu-id="41bdf-109">发生错误时，将引发异常，并停止常规执行。</span><span class="sxs-lookup"><span data-stu-id="41bdf-109">When errors occur, exceptions are raised and regular execution stops.</span></span> <span data-ttu-id="41bdf-110">而运行时将搜索适当的处理程序来处理异常。</span><span class="sxs-lookup"><span data-stu-id="41bdf-110">Instead, the runtime searches for an appropriate handler for the exception.</span></span> <span data-ttu-id="41bdf-111">运行时先从当前函数开始搜索，然后在堆栈中向上搜索调用程序的各个层，直至找到匹配的处理程序。</span><span class="sxs-lookup"><span data-stu-id="41bdf-111">The search starts in the current function, and proceeds up the stack through the layers of callers until a matching handler is found.</span></span> <span data-ttu-id="41bdf-112">然后，执行找到的处理程序。</span><span class="sxs-lookup"><span data-stu-id="41bdf-112">Then the handler is executed.</span></span>

<span data-ttu-id="41bdf-113">此外，随着堆栈的展开，运行时会执行 `finally` 块中的任何代码，从而保证在展开过程中正确地清理对象。</span><span class="sxs-lookup"><span data-stu-id="41bdf-113">In addition, as the stack is unwound, the runtime executes any code in `finally` blocks, to guarantee that objects are cleaned up correctly during the unwinding process.</span></span>


## <a name="related-topics"></a><span data-ttu-id="41bdf-114">相关主题</span><span class="sxs-lookup"><span data-stu-id="41bdf-114">Related Topics</span></span>

|<span data-ttu-id="41bdf-115">标题</span><span class="sxs-lookup"><span data-stu-id="41bdf-115">Title</span></span>|<span data-ttu-id="41bdf-116">描述</span><span class="sxs-lookup"><span data-stu-id="41bdf-116">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="41bdf-117">异常类型</span><span class="sxs-lookup"><span data-stu-id="41bdf-117">Exception Types</span></span>](exception-types.md)|<span data-ttu-id="41bdf-118">介绍如何声明异常类型。</span><span class="sxs-lookup"><span data-stu-id="41bdf-118">Describes how to declare an exception type.</span></span>|
|[<span data-ttu-id="41bdf-119">异常：`try...with` 表达式</span><span class="sxs-lookup"><span data-stu-id="41bdf-119">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)|<span data-ttu-id="41bdf-120">介绍支持异常处理的语言构造。</span><span class="sxs-lookup"><span data-stu-id="41bdf-120">Describes the language construct that supports exception handling.</span></span>|
|[<span data-ttu-id="41bdf-121">异常：`try...finally` 表达式</span><span class="sxs-lookup"><span data-stu-id="41bdf-121">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)|<span data-ttu-id="41bdf-122">介绍一种语言构造，如果在堆栈展开的过程中出现异常，可以通过这种语言构造执行清理代码。</span><span class="sxs-lookup"><span data-stu-id="41bdf-122">Describes the language construct that enables you to execute clean-up code as the stack unwinds when an exception is thrown.</span></span>|
|[<span data-ttu-id="41bdf-123">异常：`raise` 函数</span><span class="sxs-lookup"><span data-stu-id="41bdf-123">Exceptions: the `raise` Function</span></span>](the-raise-Function.md)|<span data-ttu-id="41bdf-124">介绍如何引发异常对象。</span><span class="sxs-lookup"><span data-stu-id="41bdf-124">Describes how to throw an exception object.</span></span>|
|[<span data-ttu-id="41bdf-125">异常：`failwith` 函数</span><span class="sxs-lookup"><span data-stu-id="41bdf-125">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)|<span data-ttu-id="41bdf-126">介绍如何生成常规的 F# 异常。</span><span class="sxs-lookup"><span data-stu-id="41bdf-126">Describes how to generate a general F# exception.</span></span>|
|[<span data-ttu-id="41bdf-127">异常：`invalidArg` 函数</span><span class="sxs-lookup"><span data-stu-id="41bdf-127">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)|<span data-ttu-id="41bdf-128">介绍如何生成无效的参数异常。</span><span class="sxs-lookup"><span data-stu-id="41bdf-128">Describes how to generate an invalid argument exception.</span></span>|
