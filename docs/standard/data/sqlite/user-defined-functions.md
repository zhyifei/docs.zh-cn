---
title: 用户定义的函数
ms.date: 12/13/2019
description: 了解如何创建用户定义的标量函数和聚合函数。
ms.openlocfilehash: 9ee3fbac73215353c8dc82199203b0d25e580cdb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450410"
---
# <a name="user-defined-functions"></a><span data-ttu-id="6ae43-103">用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="6ae43-103">User-defined functions</span></span>

<span data-ttu-id="6ae43-104">大多数数据库都具有 SQL 的过程方言，可用于定义自己的函数。</span><span class="sxs-lookup"><span data-stu-id="6ae43-104">Most databases have a procedural dialect of SQL that you can use to define your own functions.</span></span> <span data-ttu-id="6ae43-105">但是，在应用程序的进程内运行。</span><span class="sxs-lookup"><span data-stu-id="6ae43-105">SQLite however, runs in-process with your app.</span></span> <span data-ttu-id="6ae43-106">无需学习新的 SQL 方言，只需使用应用的编程语言即可。</span><span class="sxs-lookup"><span data-stu-id="6ae43-106">Instead of having to learn a new dialect of SQL, you can just use the programming language of your app.</span></span>

## <a name="scalar-functions"></a><span data-ttu-id="6ae43-107">标量函数</span><span class="sxs-lookup"><span data-stu-id="6ae43-107">Scalar functions</span></span>

<span data-ttu-id="6ae43-108">标量函数为查询中的每行返回单个标量值。</span><span class="sxs-lookup"><span data-stu-id="6ae43-108">Scalar functions return a single, scalar value for each row in a query.</span></span> <span data-ttu-id="6ae43-109">定义新的标量函数，并使用 <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>覆盖内置的函数。</span><span class="sxs-lookup"><span data-stu-id="6ae43-109">Define new scalar functions and override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>.</span></span>

<span data-ttu-id="6ae43-110">有关支持的参数和返回类型的列表，请参阅[数据类型](types.md)`func` 参数。</span><span class="sxs-lookup"><span data-stu-id="6ae43-110">See [Data types](types.md) for a list of supported parameter and return types for the `func` argument.</span></span>

<span data-ttu-id="6ae43-111">指定 `state` 参数会将该值传递给函数的每个调用。</span><span class="sxs-lookup"><span data-stu-id="6ae43-111">Specifying the `state` argument will pass that value into every invocation of the function.</span></span> <span data-ttu-id="6ae43-112">使用此来避免闭包。</span><span class="sxs-lookup"><span data-stu-id="6ae43-112">Use this to avoid closures.</span></span>

<span data-ttu-id="6ae43-113">如果函数具有确定性，则指定 `isDeterministic`，以便在编译查询时允许 SQLite 使用其他优化。</span><span class="sxs-lookup"><span data-stu-id="6ae43-113">Specify `isDeterministic` if your function is deterministic to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="6ae43-114">下面的示例演示如何添加标量函数以计算圆柱体的半径。</span><span class="sxs-lookup"><span data-stu-id="6ae43-114">The following example shows how to add a scalar function to calculate the radius of a cylinder.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ScalarFunctionSample/Program.cs?name=snippet_CreateFunction)]

## <a name="operators"></a><span data-ttu-id="6ae43-115">运算符</span><span class="sxs-lookup"><span data-stu-id="6ae43-115">Operators</span></span>

<span data-ttu-id="6ae43-116">以下 SQLite 运算符是通过相应的标量函数实现的。</span><span class="sxs-lookup"><span data-stu-id="6ae43-116">The following SQLite operators are implemented by corresponding scalar functions.</span></span> <span data-ttu-id="6ae43-117">在应用程序中定义这些标量函数将覆盖这些运算符的行为。</span><span class="sxs-lookup"><span data-stu-id="6ae43-117">Defining these scalar functions in your app will override the behavior of these operators.</span></span>

| <span data-ttu-id="6ae43-118">运算符</span><span class="sxs-lookup"><span data-stu-id="6ae43-118">Operator</span></span>          | <span data-ttu-id="6ae43-119">函数</span><span class="sxs-lookup"><span data-stu-id="6ae43-119">Function</span></span>      |
| ----------------- | ------------- |
| <span data-ttu-id="6ae43-120">X GLOB Y</span><span class="sxs-lookup"><span data-stu-id="6ae43-120">X GLOB Y</span></span>          | <span data-ttu-id="6ae43-121">glob （Y，X）</span><span class="sxs-lookup"><span data-stu-id="6ae43-121">glob(Y, X)</span></span>    |
| <span data-ttu-id="6ae43-122">X 像 Y</span><span class="sxs-lookup"><span data-stu-id="6ae43-122">X LIKE Y</span></span>          | <span data-ttu-id="6ae43-123">like （Y，X）</span><span class="sxs-lookup"><span data-stu-id="6ae43-123">like(Y, X)</span></span>    |
| <span data-ttu-id="6ae43-124">X 像 Y ESCAPE Z</span><span class="sxs-lookup"><span data-stu-id="6ae43-124">X LIKE Y ESCAPE Z</span></span> | <span data-ttu-id="6ae43-125">like （Y，X，Z）</span><span class="sxs-lookup"><span data-stu-id="6ae43-125">like(Y, X, Z)</span></span> |
| <span data-ttu-id="6ae43-126">X 匹配 Y</span><span class="sxs-lookup"><span data-stu-id="6ae43-126">X MATCH Y</span></span>         | <span data-ttu-id="6ae43-127">match （Y，X）</span><span class="sxs-lookup"><span data-stu-id="6ae43-127">match(Y, X)</span></span>   |
| <span data-ttu-id="6ae43-128">X REGEXP Y</span><span class="sxs-lookup"><span data-stu-id="6ae43-128">X REGEXP Y</span></span>        | <span data-ttu-id="6ae43-129">regexp （Y，X）</span><span class="sxs-lookup"><span data-stu-id="6ae43-129">regexp(Y, X)</span></span>  |

<span data-ttu-id="6ae43-130">下面的示例演示如何定义 regexp 函数以启用其相应的运算符。</span><span class="sxs-lookup"><span data-stu-id="6ae43-130">The following example shows how to define the regexp function to enable its corresponding operator.</span></span> <span data-ttu-id="6ae43-131">SQLite 不包括 regexp 函数的默认实现。</span><span class="sxs-lookup"><span data-stu-id="6ae43-131">SQLite doesn't include a default implementation of the regexp function.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/RegularExpressionSample/Program.cs?name=snippet_Regex)]

## <a name="aggregate-functions"></a><span data-ttu-id="6ae43-132">聚合函数</span><span class="sxs-lookup"><span data-stu-id="6ae43-132">Aggregate functions</span></span>

<span data-ttu-id="6ae43-133">聚合函数返回查询中所有行的单个聚合值。</span><span class="sxs-lookup"><span data-stu-id="6ae43-133">Aggregate functions return a single, aggregated value for all the rows in a query.</span></span> <span data-ttu-id="6ae43-134">使用 <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>定义和重写聚合函数。</span><span class="sxs-lookup"><span data-stu-id="6ae43-134">Define and override aggregate functions using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>.</span></span>

<span data-ttu-id="6ae43-135">`seed` 参数指定上下文的初始状态。</span><span class="sxs-lookup"><span data-stu-id="6ae43-135">The `seed` argument specifies the initial state of the context.</span></span> <span data-ttu-id="6ae43-136">使用此来避免同时出现闭包。</span><span class="sxs-lookup"><span data-stu-id="6ae43-136">Use this to avoid closures also.</span></span>

<span data-ttu-id="6ae43-137">每行调用一次 `func` 参数。</span><span class="sxs-lookup"><span data-stu-id="6ae43-137">The `func` argument is invoked once per row.</span></span> <span data-ttu-id="6ae43-138">使用上下文积累最终结果。</span><span class="sxs-lookup"><span data-stu-id="6ae43-138">Use the context to accumulate a final result.</span></span> <span data-ttu-id="6ae43-139">返回上下文。</span><span class="sxs-lookup"><span data-stu-id="6ae43-139">Return the context.</span></span> <span data-ttu-id="6ae43-140">此模式允许上下文是值类型或不可变的。</span><span class="sxs-lookup"><span data-stu-id="6ae43-140">This pattern allows the context to be a value type or immutable.</span></span>

<span data-ttu-id="6ae43-141">如果未指定 `resultSelector`，上下文的最终状态将用作结果。</span><span class="sxs-lookup"><span data-stu-id="6ae43-141">If no `resultSelector` is specified, the final state of the context is used as the result.</span></span> <span data-ttu-id="6ae43-142">这可以简化函数（如 sum 和 count）的定义，这些函数只需递增每行的数字并返回它。</span><span class="sxs-lookup"><span data-stu-id="6ae43-142">This can simplify the definition of functions like sum and count that only need to increment a number each row and return it.</span></span>

<span data-ttu-id="6ae43-143">指定 `resultSelector` 以在遍历所有行后计算上下文中的最终结果。</span><span class="sxs-lookup"><span data-stu-id="6ae43-143">Specify `resultSelector` to calculate the final result from the context after iterating through all the rows.</span></span>

<span data-ttu-id="6ae43-144">有关 `resultSelector`的 `func` 参数和返回类型的支持参数类型的列表，请参阅[数据类型](types.md)。</span><span class="sxs-lookup"><span data-stu-id="6ae43-144">See [Data types](types.md) for a list of supported parameter types for the `func` argument and return types for `resultSelector`.</span></span>

<span data-ttu-id="6ae43-145">如果函数是确定性的，则指定在编译查询时允许 SQLite 使用其他优化的 `isDeterministic`。</span><span class="sxs-lookup"><span data-stu-id="6ae43-145">If your function is deterministic, specify `isDeterministic` to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="6ae43-146">下面的示例定义了一个聚合函数，用于计算列的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="6ae43-146">The following example defines an aggregate function to calculate the standard deviation of a column.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AggregateFunctionSample/Program.cs?name=snippet_CreateAggregate)]

## <a name="errors"></a><span data-ttu-id="6ae43-147">错误</span><span class="sxs-lookup"><span data-stu-id="6ae43-147">Errors</span></span>

<span data-ttu-id="6ae43-148">如果用户定义函数引发异常，则该消息将返回到 SQLite。</span><span class="sxs-lookup"><span data-stu-id="6ae43-148">If a user-defined function throws an exception, the message is returned to SQLite.</span></span> <span data-ttu-id="6ae43-149">然后，SQLite 将引发错误，并且 SqliteException 将引发一个错误。</span><span class="sxs-lookup"><span data-stu-id="6ae43-149">SQLite will then raise an error and Microsoft.Data.Sqlite will throw a SqliteException.</span></span> <span data-ttu-id="6ae43-150">有关详细信息，请参阅[数据库错误](database-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="6ae43-150">For more information, see [Database errors](database-errors.md).</span></span>

<span data-ttu-id="6ae43-151">默认情况下，错误 SQLite 错误代码将 SQLITE_ERROR （或1）。</span><span class="sxs-lookup"><span data-stu-id="6ae43-151">By default, the error SQLite error code will be SQLITE_ERROR (or 1).</span></span> <span data-ttu-id="6ae43-152">但是，可以通过在函数中引发 <xref:Microsoft.Data.Sqlite.SqliteException> 并指定所需 <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> 来更改它。</span><span class="sxs-lookup"><span data-stu-id="6ae43-152">You can, however, change it by throwing a <xref:Microsoft.Data.Sqlite.SqliteException> in your function with the desired <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> specified.</span></span>

## <a name="debugging"></a><span data-ttu-id="6ae43-153">调试</span><span class="sxs-lookup"><span data-stu-id="6ae43-153">Debugging</span></span>

<span data-ttu-id="6ae43-154">SQLite 直接调用实现。</span><span class="sxs-lookup"><span data-stu-id="6ae43-154">SQLite calls your implementation directly.</span></span> <span data-ttu-id="6ae43-155">这样，便可以添加在 SQLite 计算查询时触发的断点。</span><span class="sxs-lookup"><span data-stu-id="6ae43-155">This lets you add breakpoints that trigger while SQLite is evaluating queries.</span></span> <span data-ttu-id="6ae43-156">完整的 .NET 调试体验可帮助您创建用户定义函数。</span><span class="sxs-lookup"><span data-stu-id="6ae43-156">The full .NET debugging experience is available to help you create your user-defined functions.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ae43-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ae43-157">See also</span></span>

* [<span data-ttu-id="6ae43-158">数据类型</span><span class="sxs-lookup"><span data-stu-id="6ae43-158">Data types</span></span>](types.md)
* [<span data-ttu-id="6ae43-159">SQLite 核心函数</span><span class="sxs-lookup"><span data-stu-id="6ae43-159">SQLite Core functions</span></span>](https://www.sqlite.org/lang_corefunc.html)
* [<span data-ttu-id="6ae43-160">SQLite 聚合函数</span><span class="sxs-lookup"><span data-stu-id="6ae43-160">SQLite Aggregate Functions</span></span>](https://www.sqlite.org/lang_aggfunc.html)
