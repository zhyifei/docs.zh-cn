---
title: 在查询表达式中处理异常（C# 中的 LINQ）
description: 了解如何在 C# 中的 LINQ 查询表达式中处理异常。
ms.date: 12/1/2016
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.openlocfilehash: 344d11129814516a5ed3dcf0eba73a5ecbb96981
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37403834"
---
# <a name="handle-exceptions-in-query-expressions"></a><span data-ttu-id="5b09f-103">在查询表达式中处理异常</span><span class="sxs-lookup"><span data-stu-id="5b09f-103">Handle exceptions in query expressions</span></span>

<span data-ttu-id="5b09f-104">在查询表达式的上下文中可以调用任何方法。</span><span class="sxs-lookup"><span data-stu-id="5b09f-104">It's possible to call any method in the context of a query expression.</span></span> <span data-ttu-id="5b09f-105">但是，我们建议避免在查询表达式中调用任何会产生副作用（如修改数据源内容或引发异常）的方法。</span><span class="sxs-lookup"><span data-stu-id="5b09f-105">However, we recommend that you avoid calling any method in a query expression that can create a side effect such as modifying the contents of the data source or throwing an exception.</span></span> <span data-ttu-id="5b09f-106">此示例演示在查询表达式中调用方法时如何避免引发异常，而不违反有关异常处理的常规 .NET 指南。</span><span class="sxs-lookup"><span data-stu-id="5b09f-106">This example shows how to avoid raising exceptions when you call methods in a query expression without violating the general .NET guidelines on exception handling.</span></span> <span data-ttu-id="5b09f-107">这些指南阐明，当你理解在给定上下文中为何会引发异常时，捕获到该特定异常是可以接受的。</span><span class="sxs-lookup"><span data-stu-id="5b09f-107">Those guidelines state that it's acceptable to catch a specific exception when you understand why it's thrown in a given context.</span></span> <span data-ttu-id="5b09f-108">有关详细信息，请参阅[异常的最佳做法](../../standard/exceptions/best-practices-for-exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="5b09f-108">For more information, see [Best Practices for Exceptions](../../standard/exceptions/best-practices-for-exceptions.md).</span></span>

<span data-ttu-id="5b09f-109">最后的示例演示了在执行查询期间必须引发异常时，该如何处理这种情况。</span><span class="sxs-lookup"><span data-stu-id="5b09f-109">The final example shows how to handle those cases when you must throw an exception during execution of a query.</span></span>

## <a name="example"></a><span data-ttu-id="5b09f-110">示例</span><span class="sxs-lookup"><span data-stu-id="5b09f-110">Example</span></span>

<span data-ttu-id="5b09f-111">以下示例演示如何将异常处理代码移到查询表达式外。</span><span class="sxs-lookup"><span data-stu-id="5b09f-111">The following example shows how to move exception handling code outside a query expression.</span></span> <span data-ttu-id="5b09f-112">只有当方法不取决于查询的任何本地变量时，才可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5b09f-112">This is only possible when the method does not depend on any variables local to the query.</span></span>

[!code-csharp[csProgGuideLINQ#10](~/samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]

## <a name="example"></a><span data-ttu-id="5b09f-113">示例</span><span class="sxs-lookup"><span data-stu-id="5b09f-113">Example</span></span>

<span data-ttu-id="5b09f-114">在某些情况下，针对由查询内部引发的异常的最佳措施可能是立即停止执行查询。</span><span class="sxs-lookup"><span data-stu-id="5b09f-114">In some cases, the best response to an exception that is thrown from within a query might be to stop the query execution immediately.</span></span> <span data-ttu-id="5b09f-115">下面的示例演示如何处理可能在查询正文内部引发的异常。</span><span class="sxs-lookup"><span data-stu-id="5b09f-115">The following example shows how to handle exceptions that might be thrown from inside a query body.</span></span> <span data-ttu-id="5b09f-116">假定 `SomeMethodThatMightThrow` 可能导致要求停止执行查询的异常。</span><span class="sxs-lookup"><span data-stu-id="5b09f-116">Assume that `SomeMethodThatMightThrow` can potentially cause an exception that requires the query execution to stop.</span></span>

<span data-ttu-id="5b09f-117">请注意，`try` 块封装 `foreach` 循环，且不对自身进行查询。</span><span class="sxs-lookup"><span data-stu-id="5b09f-117">Note that the `try` block encloses the `foreach` loop, and not the query itself.</span></span> <span data-ttu-id="5b09f-118">这是由于 `foreach` 循环正是实际执行查询时的点。</span><span class="sxs-lookup"><span data-stu-id="5b09f-118">This is because the `foreach` loop is the point at which the query is actually executed.</span></span> <span data-ttu-id="5b09f-119">有关详细信息，请参阅 [LINQ 查询简介](../programming-guide/concepts/linq/introduction-to-linq-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="5b09f-119">For more information, see [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

[!code-csharp[csProgGuideLINQ#12](~/samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]

## <a name="see-also"></a><span data-ttu-id="5b09f-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b09f-120">See also</span></span>

[<span data-ttu-id="5b09f-121">语言集成查询 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="5b09f-121">Language Integrated Query (LINQ)</span></span>](index.md)  
