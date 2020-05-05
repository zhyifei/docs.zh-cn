---
title: 用户定义的函数
ms.date: 12/13/2019
description: 了解如何创建用户定义的标量函数和聚合函数。
ms.openlocfilehash: 9ee3fbac73215353c8dc82199203b0d25e580cdb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450410"
---
# <a name="user-defined-functions"></a><span data-ttu-id="54656-103">用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="54656-103">User-defined functions</span></span>

<span data-ttu-id="54656-104">大多数数据库都具有 SQL 的过程方言，用户可以使用它定义自己的函数。</span><span class="sxs-lookup"><span data-stu-id="54656-104">Most databases have a procedural dialect of SQL that you can use to define your own functions.</span></span> <span data-ttu-id="54656-105">但是，SQLite 将在你的应用的进程内运行。</span><span class="sxs-lookup"><span data-stu-id="54656-105">SQLite however, runs in-process with your app.</span></span> <span data-ttu-id="54656-106">无需学习新的 SQL 方言，只需使用应用的编程语言即可。</span><span class="sxs-lookup"><span data-stu-id="54656-106">Instead of having to learn a new dialect of SQL, you can just use the programming language of your app.</span></span>

## <a name="scalar-functions"></a><span data-ttu-id="54656-107">标量函数</span><span class="sxs-lookup"><span data-stu-id="54656-107">Scalar functions</span></span>

<span data-ttu-id="54656-108">标量函数为查询中的每一行返回单个标量值。</span><span class="sxs-lookup"><span data-stu-id="54656-108">Scalar functions return a single, scalar value for each row in a query.</span></span> <span data-ttu-id="54656-109">定义新的标量函数，并使用 <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A> 覆盖内置函数。</span><span class="sxs-lookup"><span data-stu-id="54656-109">Define new scalar functions and override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>.</span></span>

<span data-ttu-id="54656-110">有关 `func` 参数的支持参数和返回类型的列表，请参阅[数据类型](types.md)。</span><span class="sxs-lookup"><span data-stu-id="54656-110">See [Data types](types.md) for a list of supported parameter and return types for the `func` argument.</span></span>

<span data-ttu-id="54656-111">指定 `state` 参数会将该值传递给函数的每个调用。</span><span class="sxs-lookup"><span data-stu-id="54656-111">Specifying the `state` argument will pass that value into every invocation of the function.</span></span> <span data-ttu-id="54656-112">使用它可以避免闭包。</span><span class="sxs-lookup"><span data-stu-id="54656-112">Use this to avoid closures.</span></span>

<span data-ttu-id="54656-113">如果函数具有确定性，则指定 `isDeterministic`，以便在编译查询时允许 SQLite 使用其他优化。</span><span class="sxs-lookup"><span data-stu-id="54656-113">Specify `isDeterministic` if your function is deterministic to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="54656-114">下面的示例展示如何添加标量函数以计算圆柱体的半径。</span><span class="sxs-lookup"><span data-stu-id="54656-114">The following example shows how to add a scalar function to calculate the radius of a cylinder.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ScalarFunctionSample/Program.cs?name=snippet_CreateFunction)]

## <a name="operators"></a><span data-ttu-id="54656-115">运算符</span><span class="sxs-lookup"><span data-stu-id="54656-115">Operators</span></span>

<span data-ttu-id="54656-116">以下 SQLite 运算符由相应的标量函数实现。</span><span class="sxs-lookup"><span data-stu-id="54656-116">The following SQLite operators are implemented by corresponding scalar functions.</span></span> <span data-ttu-id="54656-117">在应用中定义这些标量函数将覆盖这些运算符的行为。</span><span class="sxs-lookup"><span data-stu-id="54656-117">Defining these scalar functions in your app will override the behavior of these operators.</span></span>

| <span data-ttu-id="54656-118">运算符</span><span class="sxs-lookup"><span data-stu-id="54656-118">Operator</span></span>          | <span data-ttu-id="54656-119">函数</span><span class="sxs-lookup"><span data-stu-id="54656-119">Function</span></span>      |
| ----------------- | ------------- |
| <span data-ttu-id="54656-120">X GLOB Y</span><span class="sxs-lookup"><span data-stu-id="54656-120">X GLOB Y</span></span>          | <span data-ttu-id="54656-121">glob(Y, X)</span><span class="sxs-lookup"><span data-stu-id="54656-121">glob(Y, X)</span></span>    |
| <span data-ttu-id="54656-122">X LIKE Y</span><span class="sxs-lookup"><span data-stu-id="54656-122">X LIKE Y</span></span>          | <span data-ttu-id="54656-123">like(Y, X)</span><span class="sxs-lookup"><span data-stu-id="54656-123">like(Y, X)</span></span>    |
| <span data-ttu-id="54656-124">X LIKE Y ESCAPE Z</span><span class="sxs-lookup"><span data-stu-id="54656-124">X LIKE Y ESCAPE Z</span></span> | <span data-ttu-id="54656-125">like(Y, X, Z)</span><span class="sxs-lookup"><span data-stu-id="54656-125">like(Y, X, Z)</span></span> |
| <span data-ttu-id="54656-126">X MATCH Y</span><span class="sxs-lookup"><span data-stu-id="54656-126">X MATCH Y</span></span>         | <span data-ttu-id="54656-127">match(Y, X)</span><span class="sxs-lookup"><span data-stu-id="54656-127">match(Y, X)</span></span>   |
| <span data-ttu-id="54656-128">X REGEXP Y</span><span class="sxs-lookup"><span data-stu-id="54656-128">X REGEXP Y</span></span>        | <span data-ttu-id="54656-129">regexp(Y, X)</span><span class="sxs-lookup"><span data-stu-id="54656-129">regexp(Y, X)</span></span>  |

<span data-ttu-id="54656-130">下面的示例展示如何定义 regexp 函数以启用其相应的运算符。</span><span class="sxs-lookup"><span data-stu-id="54656-130">The following example shows how to define the regexp function to enable its corresponding operator.</span></span> <span data-ttu-id="54656-131">SQLite 不包括 regexp 函数的默认实现。</span><span class="sxs-lookup"><span data-stu-id="54656-131">SQLite doesn't include a default implementation of the regexp function.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/RegularExpressionSample/Program.cs?name=snippet_Regex)]

## <a name="aggregate-functions"></a><span data-ttu-id="54656-132">聚合函数</span><span class="sxs-lookup"><span data-stu-id="54656-132">Aggregate functions</span></span>

<span data-ttu-id="54656-133">聚合函数为查询中的所有行返回单个聚合值。</span><span class="sxs-lookup"><span data-stu-id="54656-133">Aggregate functions return a single, aggregated value for all the rows in a query.</span></span> <span data-ttu-id="54656-134">使用 <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A> 定义和重写聚合函数。</span><span class="sxs-lookup"><span data-stu-id="54656-134">Define and override aggregate functions using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>.</span></span>

<span data-ttu-id="54656-135">`seed` 参数指定上下文的初始状态。</span><span class="sxs-lookup"><span data-stu-id="54656-135">The `seed` argument specifies the initial state of the context.</span></span> <span data-ttu-id="54656-136">使用它也可以避免闭包。</span><span class="sxs-lookup"><span data-stu-id="54656-136">Use this to avoid closures also.</span></span>

<span data-ttu-id="54656-137">在每行调用一次 `func` 参数。</span><span class="sxs-lookup"><span data-stu-id="54656-137">The `func` argument is invoked once per row.</span></span> <span data-ttu-id="54656-138">使用上下文来累积最终结果。</span><span class="sxs-lookup"><span data-stu-id="54656-138">Use the context to accumulate a final result.</span></span> <span data-ttu-id="54656-139">返回上下文。</span><span class="sxs-lookup"><span data-stu-id="54656-139">Return the context.</span></span> <span data-ttu-id="54656-140">此模式允许上下文是值类型或不可变的。</span><span class="sxs-lookup"><span data-stu-id="54656-140">This pattern allows the context to be a value type or immutable.</span></span>

<span data-ttu-id="54656-141">如果未指定 `resultSelector`，则将上下文的最终状态用作结果。</span><span class="sxs-lookup"><span data-stu-id="54656-141">If no `resultSelector` is specified, the final state of the context is used as the result.</span></span> <span data-ttu-id="54656-142">这可以简化诸如求和和计数之类的函数的定义，这些函数只需要在每行增加一个数值并返回即可。</span><span class="sxs-lookup"><span data-stu-id="54656-142">This can simplify the definition of functions like sum and count that only need to increment a number each row and return it.</span></span>

<span data-ttu-id="54656-143">指定 `resultSelector` 以在遍历所有行后从上下文计算最终结果。</span><span class="sxs-lookup"><span data-stu-id="54656-143">Specify `resultSelector` to calculate the final result from the context after iterating through all the rows.</span></span>

<span data-ttu-id="54656-144">有关 `func` 参数的支持参数；类型和 `resultSelector` 的返回类型的列表，请参阅[数据类型](types.md)。</span><span class="sxs-lookup"><span data-stu-id="54656-144">See [Data types](types.md) for a list of supported parameter types for the `func` argument and return types for `resultSelector`.</span></span>

<span data-ttu-id="54656-145">如果函数具有确定性，则指定 `isDeterministic`，以便在编译查询时允许 SQLite 使用其他优化。</span><span class="sxs-lookup"><span data-stu-id="54656-145">If your function is deterministic, specify `isDeterministic` to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="54656-146">下面的示例定义了一个聚合函数，用于计算列的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="54656-146">The following example defines an aggregate function to calculate the standard deviation of a column.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AggregateFunctionSample/Program.cs?name=snippet_CreateAggregate)]

## <a name="errors"></a><span data-ttu-id="54656-147">错误</span><span class="sxs-lookup"><span data-stu-id="54656-147">Errors</span></span>

<span data-ttu-id="54656-148">如果用户定义函数引发异常，则会向 SQLite 返回该消息。</span><span class="sxs-lookup"><span data-stu-id="54656-148">If a user-defined function throws an exception, the message is returned to SQLite.</span></span> <span data-ttu-id="54656-149">然后，SQLite 将引发错误，并且 Microsoft.Data.Sqlite 将引发一个 SqliteException。</span><span class="sxs-lookup"><span data-stu-id="54656-149">SQLite will then raise an error and Microsoft.Data.Sqlite will throw a SqliteException.</span></span> <span data-ttu-id="54656-150">有关详细信息，请参阅[数据库错误](database-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="54656-150">For more information, see [Database errors](database-errors.md).</span></span>

<span data-ttu-id="54656-151">默认情况下，错误的 SQLite 错误代码为 SQLITE_ERROR（或 1）。</span><span class="sxs-lookup"><span data-stu-id="54656-151">By default, the error SQLite error code will be SQLITE_ERROR (or 1).</span></span> <span data-ttu-id="54656-152">但是，可以通过在函数中引发 <xref:Microsoft.Data.Sqlite.SqliteException> 并指定所需的 <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> 来更改它。</span><span class="sxs-lookup"><span data-stu-id="54656-152">You can, however, change it by throwing a <xref:Microsoft.Data.Sqlite.SqliteException> in your function with the desired <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> specified.</span></span>

## <a name="debugging"></a><span data-ttu-id="54656-153">调试</span><span class="sxs-lookup"><span data-stu-id="54656-153">Debugging</span></span>

<span data-ttu-id="54656-154">SQLite 直接调用你的实现。</span><span class="sxs-lookup"><span data-stu-id="54656-154">SQLite calls your implementation directly.</span></span> <span data-ttu-id="54656-155">这使你可以添加在 SQLite 评估查询时触发的断点。</span><span class="sxs-lookup"><span data-stu-id="54656-155">This lets you add breakpoints that trigger while SQLite is evaluating queries.</span></span> <span data-ttu-id="54656-156">完整的 .NET 调试体验可帮助你创建用户定义函数。</span><span class="sxs-lookup"><span data-stu-id="54656-156">The full .NET debugging experience is available to help you create your user-defined functions.</span></span>

## <a name="see-also"></a><span data-ttu-id="54656-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="54656-157">See also</span></span>

* [<span data-ttu-id="54656-158">数据类型</span><span class="sxs-lookup"><span data-stu-id="54656-158">Data types</span></span>](types.md)
* [<span data-ttu-id="54656-159">SQLite 核心函数</span><span class="sxs-lookup"><span data-stu-id="54656-159">SQLite Core functions</span></span>](https://www.sqlite.org/lang_corefunc.html)
* [<span data-ttu-id="54656-160">SQLite 聚合函数</span><span class="sxs-lookup"><span data-stu-id="54656-160">SQLite Aggregate Functions</span></span>](https://www.sqlite.org/lang_aggfunc.html)
