---
title: 如何：在 Catch 块中使用特定异常
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try/catch blocks
- catch blocks
ms.assetid: 12af9ff3-8587-4f31-90cf-6c2244e0fdae
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3da35dae374018f0695f79022e83ad397e98cb88
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44202344"
---
# <a name="how-to-use-specific-exceptions-in-a-catch-block"></a><span data-ttu-id="ef09c-102">如何在 catch 块中使用特定异常</span><span class="sxs-lookup"><span data-stu-id="ef09c-102">How to use specific exceptions in a catch block</span></span>

<span data-ttu-id="ef09c-103">一般来说，编程最佳做法是，捕获特定类型的异常，而不是使用基本 `catch` 语句。</span><span class="sxs-lookup"><span data-stu-id="ef09c-103">In general, it's good programming practice to catch a specific type of exception rather than use a basic `catch` statement.</span></span>

<span data-ttu-id="ef09c-104">异常发生时，会在堆栈中向上传递，每个 catch 块都有机会处理异常。</span><span class="sxs-lookup"><span data-stu-id="ef09c-104">When an exception occurs, it is passed up the stack and each catch block is given the opportunity to handle it.</span></span> <span data-ttu-id="ef09c-105">Catch 语句的顺序非常重要。</span><span class="sxs-lookup"><span data-stu-id="ef09c-105">The order of catch statements is important.</span></span> <span data-ttu-id="ef09c-106">在一般异常 catch 块或编译器发出错误前，将 catch 块指向特定异常。</span><span class="sxs-lookup"><span data-stu-id="ef09c-106">Put catch blocks targeted to specific exceptions before a general exception catch block or the compiler might issue an error.</span></span> <span data-ttu-id="ef09c-107">通过匹配异常类型与 catch 块中指定的异常名称，确定合适的 catch 块。</span><span class="sxs-lookup"><span data-stu-id="ef09c-107">The proper catch block is determined by matching the type of the exception to the name of the exception specified in the catch block.</span></span> <span data-ttu-id="ef09c-108">如果没有特定的 catch 块，则将由一般 catch 块捕获异常（如果异常存在）。</span><span class="sxs-lookup"><span data-stu-id="ef09c-108">If there is no specific catch block, the exception is caught by a general catch block, if one exists.</span></span>

<span data-ttu-id="ef09c-109">下方代码示例使用 `try`/`catch` 块来捕获 <xref:System.InvalidCastException>。</span><span class="sxs-lookup"><span data-stu-id="ef09c-109">The following code example uses a `try`/`catch` block to catch an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="ef09c-110">该示例创建了一个名为 `Employee` 的类，其具有单一属性，雇员级别为 (`Emlevel`)。</span><span class="sxs-lookup"><span data-stu-id="ef09c-110">The sample creates a class called `Employee` with a single property, employee level (`Emlevel`).</span></span> <span data-ttu-id="ef09c-111">`PromoteEmployee` 方法接收对象并递增雇员级别。</span><span class="sxs-lookup"><span data-stu-id="ef09c-111">A method, `PromoteEmployee`, takes an object and increments the employee level.</span></span> <span data-ttu-id="ef09c-112"><xref:System.DateTime> 实例传递给 `PromoteEmployee` 方法时，<xref:System.InvalidCastException> 发生。</span><span class="sxs-lookup"><span data-stu-id="ef09c-112">An <xref:System.InvalidCastException> occurs when a <xref:System.DateTime> instance is passed to the `PromoteEmployee` method.</span></span>

[!code-cpp[CatchException#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception1.cpp#2)]
[!code-csharp[CatchException#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception1.cs#2)]
[!code-vb[CatchException#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception1.vb#2)] 

## <a name="see-also"></a><span data-ttu-id="ef09c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef09c-113">See also</span></span>

- [<span data-ttu-id="ef09c-114">异常</span><span class="sxs-lookup"><span data-stu-id="ef09c-114">Exceptions</span></span>](index.md)
