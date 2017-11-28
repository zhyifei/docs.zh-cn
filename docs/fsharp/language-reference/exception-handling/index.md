---
title: "异常处理 (F#)"
description: "了解在 F # 中处理的异常的基础知识和查找异常处理表达式和函数的链接。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ad475c4a-d94e-47d9-b27b-3ff000b65f8e
ms.openlocfilehash: b61af66e0a70fdf9b86df37418c0284957d1f99e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="exception-handling"></a><span data-ttu-id="f7796-104">异常处理</span><span class="sxs-lookup"><span data-stu-id="f7796-104">Exception Handling</span></span>

<span data-ttu-id="f7796-105">此部分包含 F# 语言中的异常处理支持信息。</span><span class="sxs-lookup"><span data-stu-id="f7796-105">This section contains information about exception handling support in the F# language.</span></span>


## <a name="exception-handling-basics"></a><span data-ttu-id="f7796-106">异常处理基本知识</span><span class="sxs-lookup"><span data-stu-id="f7796-106">Exception Handling Basics</span></span>
<span data-ttu-id="f7796-107">异常处理是在 .NET Framework 中处理错误条件的标准方法。</span><span class="sxs-lookup"><span data-stu-id="f7796-107">Exception handling is the standard way of handling error conditions in the .NET Framework.</span></span> <span data-ttu-id="f7796-108">因此，任何 .NET 语言都必须支持此机制，包括 F# 在内。</span><span class="sxs-lookup"><span data-stu-id="f7796-108">Thus, any .NET language must support this mechanism, including F#.</span></span> <span data-ttu-id="f7796-109">异常是一个封装了有关错误的信息的对象。</span><span class="sxs-lookup"><span data-stu-id="f7796-109">An *exception* is an object that encapsulates information about an error.</span></span> <span data-ttu-id="f7796-110">发生错误时，将引发异常，并停止常规执行。</span><span class="sxs-lookup"><span data-stu-id="f7796-110">When errors occur, exceptions are raised and regular execution stops.</span></span> <span data-ttu-id="f7796-111">而运行时将搜索适当的处理程序来处理异常。</span><span class="sxs-lookup"><span data-stu-id="f7796-111">Instead, the runtime searches for an appropriate handler for the exception.</span></span> <span data-ttu-id="f7796-112">运行时先从当前函数开始搜索，然后在堆栈中向上搜索调用程序的各个层，直至找到匹配的处理程序。</span><span class="sxs-lookup"><span data-stu-id="f7796-112">The search starts in the current function, and proceeds up the stack through the layers of callers until a matching handler is found.</span></span> <span data-ttu-id="f7796-113">然后，执行找到的处理程序。</span><span class="sxs-lookup"><span data-stu-id="f7796-113">Then the handler is executed.</span></span>

<span data-ttu-id="f7796-114">此外，随着堆栈的展开，运行时会执行 `finally` 块中的任何代码，从而保证在展开过程中正确地清理对象。</span><span class="sxs-lookup"><span data-stu-id="f7796-114">In addition, as the stack is unwound, the runtime executes any code in `finally` blocks, to guarantee that objects are cleaned up correctly during the unwinding process.</span></span>


## <a name="related-topics"></a><span data-ttu-id="f7796-115">相关主题</span><span class="sxs-lookup"><span data-stu-id="f7796-115">Related Topics</span></span>

|<span data-ttu-id="f7796-116">标题</span><span class="sxs-lookup"><span data-stu-id="f7796-116">Title</span></span>|<span data-ttu-id="f7796-117">说明</span><span class="sxs-lookup"><span data-stu-id="f7796-117">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="f7796-118">异常类型</span><span class="sxs-lookup"><span data-stu-id="f7796-118">Exception Types</span></span>](exception-types.md)|<span data-ttu-id="f7796-119">介绍如何声明异常类型。</span><span class="sxs-lookup"><span data-stu-id="f7796-119">Describes how to declare an exception type.</span></span>|
|[<span data-ttu-id="f7796-120">异常：`try...with` 表达式</span><span class="sxs-lookup"><span data-stu-id="f7796-120">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)|<span data-ttu-id="f7796-121">介绍支持异常处理的语言构造。</span><span class="sxs-lookup"><span data-stu-id="f7796-121">Describes the language construct that supports exception handling.</span></span>|
|[<span data-ttu-id="f7796-122">异常：`try...finally` 表达式</span><span class="sxs-lookup"><span data-stu-id="f7796-122">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)|<span data-ttu-id="f7796-123">介绍一种语言构造，如果在堆栈展开的过程中出现异常，可以通过这种语言构造执行清理代码。</span><span class="sxs-lookup"><span data-stu-id="f7796-123">Describes the language construct that enables you to execute clean-up code as the stack unwinds when an exception is thrown.</span></span>|
|[<span data-ttu-id="f7796-124">异常：`raise` 函数</span><span class="sxs-lookup"><span data-stu-id="f7796-124">Exceptions: the `raise` Function</span></span>](the-raise-Function.md)|<span data-ttu-id="f7796-125">介绍如何引发异常对象。</span><span class="sxs-lookup"><span data-stu-id="f7796-125">Describes how to throw an exception object.</span></span>|
|[<span data-ttu-id="f7796-126">异常：`failwith` 函数</span><span class="sxs-lookup"><span data-stu-id="f7796-126">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)|<span data-ttu-id="f7796-127">介绍如何生成常规的 F# 异常。</span><span class="sxs-lookup"><span data-stu-id="f7796-127">Describes how to generate a general F# exception.</span></span>|
|[<span data-ttu-id="f7796-128">异常：`invalidArg` 函数</span><span class="sxs-lookup"><span data-stu-id="f7796-128">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)|<span data-ttu-id="f7796-129">介绍如何生成无效的参数异常。</span><span class="sxs-lookup"><span data-stu-id="f7796-129">Describes how to generate an invalid argument exception.</span></span>|
