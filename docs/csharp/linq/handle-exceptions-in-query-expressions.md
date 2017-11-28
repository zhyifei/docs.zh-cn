---
title: "在查询表达式中处理异常"
description: "如何在查询表达式中处理异常。"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.openlocfilehash: 376bd461bfeb51653471fd374a2215aa15872976
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="handle-exceptions-in-query-expressions"></a><span data-ttu-id="f7a4e-104">在查询表达式中处理异常</span><span class="sxs-lookup"><span data-stu-id="f7a4e-104">Handle exceptions in query expressions</span></span>

<span data-ttu-id="f7a4e-105">在查询表达式的上下文中可以调用任何方法。</span><span class="sxs-lookup"><span data-stu-id="f7a4e-105">It is possible to call any method in the context of a query expression.</span></span> <span data-ttu-id="f7a4e-106">但是，我们建议避免在查询表达式中调用任何会产生副作用（如修改数据源内容或引发异常）的方法。</span><span class="sxs-lookup"><span data-stu-id="f7a4e-106">However, we recommend that you avoid calling any method in a query expression that can create a side effect such as modifying the contents of the data source or throwing an exception.</span></span> <span data-ttu-id="f7a4e-107">此示例演示在查询表达式中调用方法时如何避免引发异常，而不违反有关异常处理的常规 .NET Framework 指南。</span><span class="sxs-lookup"><span data-stu-id="f7a4e-107">This example shows how to avoid raising exceptions when you call methods in a query expression without violating the general .NET Framework guidelines on exception handling.</span></span> <span data-ttu-id="f7a4e-108">这些指南阐明，当你理解在给定上下文中为何会引发异常时，捕获到该特定异常是可以接受的。</span><span class="sxs-lookup"><span data-stu-id="f7a4e-108">Those guidelines state that it is acceptable to catch a specific exception when you understand why it will be thrown in a given context.</span></span> <span data-ttu-id="f7a4e-109">有关详细信息，请参阅[异常的最佳做法](../../standard/exceptions/best-practices-for-exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="f7a4e-109">For more information, see [Best Practices for Exceptions](../../standard/exceptions/best-practices-for-exceptions.md).</span></span>  
  
 <span data-ttu-id="f7a4e-110">最后的示例演示了在执行查询期间必须引发异常时，该如何处理这种情况。</span><span class="sxs-lookup"><span data-stu-id="f7a4e-110">The final example shows how to handle those cases when you must throw an exception during execution of a query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7a4e-111">示例</span><span class="sxs-lookup"><span data-stu-id="f7a4e-111">Example</span></span>  

 <span data-ttu-id="f7a4e-112">以下示例演示如何将异常处理代码移到查询表达式外。</span><span class="sxs-lookup"><span data-stu-id="f7a4e-112">The following example shows how to move exception handling code outside a query expression.</span></span> <span data-ttu-id="f7a4e-113">只有当方法不取决于查询的任何本地变量时，才可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="f7a4e-113">This is only possible when the method does not depend on any variables local to the query.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#10](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="f7a4e-114">示例</span><span class="sxs-lookup"><span data-stu-id="f7a4e-114">Example</span></span> 

 <span data-ttu-id="f7a4e-115">在某些情况下，针对由查询内部引发的异常的最佳措施可能是立即停止执行查询。</span><span class="sxs-lookup"><span data-stu-id="f7a4e-115">In some cases, the best response to an exception that is thrown from within a query might be to stop the query execution immediately.</span></span> <span data-ttu-id="f7a4e-116">下面的示例演示如何处理可能在查询正文内部引发的异常。</span><span class="sxs-lookup"><span data-stu-id="f7a4e-116">The following example shows how to handle exceptions that might be thrown from inside a query body.</span></span> <span data-ttu-id="f7a4e-117">假定 `SomeMethodThatMightThrow` 可能导致要求停止执行查询的异常。</span><span class="sxs-lookup"><span data-stu-id="f7a4e-117">Assume that `SomeMethodThatMightThrow` can potentially cause an exception that requires the query execution to stop.</span></span>  
  
 <span data-ttu-id="f7a4e-118">请注意，`try` 块封装 `foreach` 循环，且不对自身进行查询。</span><span class="sxs-lookup"><span data-stu-id="f7a4e-118">Note that the `try` block encloses the `foreach` loop, and not the query itself.</span></span> <span data-ttu-id="f7a4e-119">这是由于 `foreach` 循环正是实际执行查询时的点。</span><span class="sxs-lookup"><span data-stu-id="f7a4e-119">This is because the `foreach` loop is the point at which the query is actually executed.</span></span> <span data-ttu-id="f7a4e-120">有关详细信息，请参阅 [LINQ 查询简介](../programming-guide/concepts/linq/introduction-to-linq-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="f7a4e-120">For more information, see [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!code-csharp[csProgGuideLINQ#12](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]  
  

## <a name="see-also"></a><span data-ttu-id="f7a4e-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7a4e-121">See Also</span></span>  
 [<span data-ttu-id="f7a4e-122">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="f7a4e-122">LINQ query expressions</span></span>](index.md)
