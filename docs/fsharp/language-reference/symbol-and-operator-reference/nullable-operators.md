---
title: 可以为 null 的运算符
description: 了解有关中可用的可以为 null 运算符的信息F#编程语言。
ms.date: 05/16/2016
ms.openlocfilehash: b17c0de2d81a1ef88b31d833a49ff9e3f9d34e8d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61960454"
---
# <a name="nullable-operators"></a><span data-ttu-id="22b77-103">可以为 null 的运算符</span><span class="sxs-lookup"><span data-stu-id="22b77-103">Nullable Operators</span></span>

<span data-ttu-id="22b77-104">可以为 null 的运算符是二元一端或两端使用可以为 null 的算术类型的算术或比较运算符。</span><span class="sxs-lookup"><span data-stu-id="22b77-104">Nullable operators are binary arithmetic or comparison operators that work with nullable arithmetic types on one or both sides.</span></span> <span data-ttu-id="22b77-105">使用源如允许使用空值来替代实际值的数据库中的数据时经常会出现可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="22b77-105">Nullable types arise frequently when you work with data from sources such as databases that allow nulls in place of actual values.</span></span> <span data-ttu-id="22b77-106">在查询表达式中通常使用可以为 null 的运算符。</span><span class="sxs-lookup"><span data-stu-id="22b77-106">Nullable operators are used frequently in query expressions.</span></span> <span data-ttu-id="22b77-107">除了可以为 null 的算术运算符和比较运算符，可以使用转换运算符可以为 null 的类型之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="22b77-107">In addition to nullable operators for arithmetic and comparison, conversion operators can be used to convert between nullable types.</span></span> <span data-ttu-id="22b77-108">也有某些查询运算符的为空版本。</span><span class="sxs-lookup"><span data-stu-id="22b77-108">There are also nullable versions of certain query operators.</span></span>

## <a name="table-of-nullable-operators"></a><span data-ttu-id="22b77-109">可以为 Null 的运算符的表</span><span class="sxs-lookup"><span data-stu-id="22b77-109">Table of Nullable Operators</span></span>

<span data-ttu-id="22b77-110">下表列出了可以为 null 的运算符中支持F#语言。</span><span class="sxs-lookup"><span data-stu-id="22b77-110">The following table lists nullable operators supported in the F# language.</span></span>

|<span data-ttu-id="22b77-111">在左侧可以为 null</span><span class="sxs-lookup"><span data-stu-id="22b77-111">Nullable on left</span></span>|<span data-ttu-id="22b77-112">右侧可以为 null</span><span class="sxs-lookup"><span data-stu-id="22b77-112">Nullable on right</span></span>|<span data-ttu-id="22b77-113">双方可以为 null</span><span class="sxs-lookup"><span data-stu-id="22b77-113">Both sides nullable</span></span>|
|---|---|---|
|[<span data-ttu-id="22b77-114">?>=</span><span class="sxs-lookup"><span data-stu-id="22b77-114">?>=</span></span>](https://msdn.microsoft.com/library/94d29e32-a204-4f60-a527-6b0af86268f3)|[<span data-ttu-id="22b77-115">>=?</span><span class="sxs-lookup"><span data-stu-id="22b77-115">>=?</span></span>](https://msdn.microsoft.com/library/0a255d8e-8cae-4160-ae61-243a5d96583f)|[<span data-ttu-id="22b77-116">?>=?</span><span class="sxs-lookup"><span data-stu-id="22b77-116">?>=?</span></span>](https://msdn.microsoft.com/library/3051a50f-d276-4c84-9d73-bf2efeddef94)|
|[<span data-ttu-id="22b77-117">?></span><span class="sxs-lookup"><span data-stu-id="22b77-117">?></span></span>](https://msdn.microsoft.com/library/62dc0021-1312-4ac3-be87-798b60b81bb6)|[<span data-ttu-id="22b77-118">>?</span><span class="sxs-lookup"><span data-stu-id="22b77-118">>?</span></span>](https://msdn.microsoft.com/library/0ad1284b-de48-4a04-83d8-b6f13c9c8936)|[<span data-ttu-id="22b77-119">?>?</span><span class="sxs-lookup"><span data-stu-id="22b77-119">?>?</span></span>](https://msdn.microsoft.com/library/dc18b6fa-30c4-47b0-9057-794439378a05)|
|[<span data-ttu-id="22b77-120">?<=</span><span class="sxs-lookup"><span data-stu-id="22b77-120">?<=</span></span>](https://msdn.microsoft.com/library/56fddf0a-e4ca-4891-a3be-fad1876be3b6)|[<span data-ttu-id="22b77-121"><=?</span><span class="sxs-lookup"><span data-stu-id="22b77-121"><=?</span></span>](https://msdn.microsoft.com/library/02454a0f-30ca-4e77-ad84-ee7837461804)|[<span data-ttu-id="22b77-122">?<=?</span><span class="sxs-lookup"><span data-stu-id="22b77-122">?<=?</span></span>](https://msdn.microsoft.com/library/5c37c28c-0b57-4da5-be11-5a123f7e8ee4)|
|[<span data-ttu-id="22b77-123">?<</span><span class="sxs-lookup"><span data-stu-id="22b77-123">?<</span></span>](https://msdn.microsoft.com/library/b71897f0-6e29-4c58-b0a7-a5bfa6f88917)|[<span data-ttu-id="22b77-124"><?</span><span class="sxs-lookup"><span data-stu-id="22b77-124"><?</span></span>](https://msdn.microsoft.com/library/be9ea40f-a67f-4e98-8067-a14046752e8b)|[<span data-ttu-id="22b77-125">?<?</span><span class="sxs-lookup"><span data-stu-id="22b77-125">?<?</span></span>](https://msdn.microsoft.com/library/6f1962c8-5605-468c-94ae-f379ae98e17d)|
|[<span data-ttu-id="22b77-126">?=</span><span class="sxs-lookup"><span data-stu-id="22b77-126">?=</span></span>](https://msdn.microsoft.com/library/5cdc8ff6-244b-49cf-9376-69ecf249fd7c)|[<span data-ttu-id="22b77-127">=?</span><span class="sxs-lookup"><span data-stu-id="22b77-127">=?</span></span>](https://msdn.microsoft.com/library/d2102894-6a51-475d-890a-735568c31f87)|[<span data-ttu-id="22b77-128">?=?</span><span class="sxs-lookup"><span data-stu-id="22b77-128">?=?</span></span>](https://msdn.microsoft.com/library/5f793f29-1084-4570-b1c1-17c1b7ef764b)|
|[<span data-ttu-id="22b77-129">?<></span><span class="sxs-lookup"><span data-stu-id="22b77-129">?<></span></span>](https://msdn.microsoft.com/library/3643a5a8-2ea5-4ad6-82c4-83927c3884a0)|[<span data-ttu-id="22b77-130"><>?</span><span class="sxs-lookup"><span data-stu-id="22b77-130"><>?</span></span>](https://msdn.microsoft.com/library/3179aace-70c4-4911-9258-619592214976)|[<span data-ttu-id="22b77-131">?<>?</span><span class="sxs-lookup"><span data-stu-id="22b77-131">?<>?</span></span>](https://msdn.microsoft.com/library/5da813d8-ee75-45b8-9ef4-146dcb6d394d)|
|[<span data-ttu-id="22b77-132">?+</span><span class="sxs-lookup"><span data-stu-id="22b77-132">?+</span></span>](https://msdn.microsoft.com/library/2e8ddd05-b3f3-41b3-9d73-938d9e540f3f)|[<span data-ttu-id="22b77-133">+?</span><span class="sxs-lookup"><span data-stu-id="22b77-133">+?</span></span>](https://msdn.microsoft.com/library/74772ea8-f010-493e-bdb5-ba347f2fd4f1)|[<span data-ttu-id="22b77-134">?+?</span><span class="sxs-lookup"><span data-stu-id="22b77-134">?+?</span></span>](https://msdn.microsoft.com/library/57f28137-0f42-43d2-92af-cad8c6c9d05f)|
|[<span data-ttu-id="22b77-135">?-</span><span class="sxs-lookup"><span data-stu-id="22b77-135">?-</span></span>](https://msdn.microsoft.com/library/f237a7a6-89f2-48b2-a2fe-f0b98a2bedc2)|[<span data-ttu-id="22b77-136">-?</span><span class="sxs-lookup"><span data-stu-id="22b77-136">-?</span></span>](https://msdn.microsoft.com/library/4a345c07-314a-48f1-b557-ce072583589c)|[<span data-ttu-id="22b77-137">?-?</span><span class="sxs-lookup"><span data-stu-id="22b77-137">?-?</span></span>](https://msdn.microsoft.com/library/e0024142-1d2a-4607-a39c-1eb1e86fa25a)|
|[<span data-ttu-id="22b77-138">?\*</span><span class="sxs-lookup"><span data-stu-id="22b77-138">?\*</span></span>](https://msdn.microsoft.com/library/519da708-5ad6-4075-9d74-d00441cd6078)|[<span data-ttu-id="22b77-139">\*?</span><span class="sxs-lookup"><span data-stu-id="22b77-139">\*?</span></span>](https://msdn.microsoft.com/library/04c47870-de7b-480d-98a0-f47593b4ffac)|[<span data-ttu-id="22b77-140">?\*?</span><span class="sxs-lookup"><span data-stu-id="22b77-140">?\*?</span></span>](https://msdn.microsoft.com/library/e57057ba-9c3a-40ec-8401-150c2b25f75b)|
|[<span data-ttu-id="22b77-141">?/</span><span class="sxs-lookup"><span data-stu-id="22b77-141">?/</span></span>](https://msdn.microsoft.com/library/add02a42-f556-40a7-a168-fbf2053322e3)|[<span data-ttu-id="22b77-142">/?</span><span class="sxs-lookup"><span data-stu-id="22b77-142">/?</span></span>](https://msdn.microsoft.com/library/1de07646-3778-476d-8c61-5d37495d463c)|[<span data-ttu-id="22b77-143">?/?</span><span class="sxs-lookup"><span data-stu-id="22b77-143">?/?</span></span>](https://msdn.microsoft.com/library/b17be0ac-bf98-4590-861d-a4dd6c6fa535)|
|[<span data-ttu-id="22b77-144">?%</span><span class="sxs-lookup"><span data-stu-id="22b77-144">?%</span></span>](https://msdn.microsoft.com/library/44297bba-1bd9-4ed2-a848-f1e1e598db87)|[<span data-ttu-id="22b77-145">%?</span><span class="sxs-lookup"><span data-stu-id="22b77-145">%?</span></span>](https://msdn.microsoft.com/library/a4c178e5-eec4-42e8-847f-90b24fc609fe)|[<span data-ttu-id="22b77-146">?%?</span><span class="sxs-lookup"><span data-stu-id="22b77-146">?%?</span></span>](https://msdn.microsoft.com/library/dd555f20-1be3-4b8d-81f1-bf1921e62fda)|

## <a name="remarks"></a><span data-ttu-id="22b77-147">备注</span><span class="sxs-lookup"><span data-stu-id="22b77-147">Remarks</span></span>

<span data-ttu-id="22b77-148">中包含的可以为 null 的运算符[NullableOperators](https://msdn.microsoft.com/library/2c3633c5-3f31-4d62-a9f8-272ad6b19007)命名空间中的模块[Microsoft.FSharp.Linq](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d)。</span><span class="sxs-lookup"><span data-stu-id="22b77-148">The nullable operators are included in the [NullableOperators](https://msdn.microsoft.com/library/2c3633c5-3f31-4d62-a9f8-272ad6b19007) module in the namespace [Microsoft.FSharp.Linq](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d).</span></span> <span data-ttu-id="22b77-149">对于可以为 null 的数据类型是`System.Nullable<'T>`。</span><span class="sxs-lookup"><span data-stu-id="22b77-149">The type for nullable data is `System.Nullable<'T>`.</span></span>

<span data-ttu-id="22b77-150">在查询表达式中，选择从允许空值而不是值的数据源的数据时，会出现可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="22b77-150">In query expressions, nullable types arise when selecting data from a data source that allows nulls instead of values.</span></span> <span data-ttu-id="22b77-151">在 SQL Server 数据库中，表中的每个数据列具有一个属性，指示是否允许 null 值。</span><span class="sxs-lookup"><span data-stu-id="22b77-151">In a SQL Server database, each data column in a table has an attribute that indicates whether nulls are allowed.</span></span> <span data-ttu-id="22b77-152">如果允许空值，从数据库返回的数据可以包含 null 值的基元数据类型如不能表示`int`， `float`，依次类推。</span><span class="sxs-lookup"><span data-stu-id="22b77-152">If nulls are allowed, the data returned from the database can contain nulls that cannot be represented by a primitive data type such as `int`, `float`, and so on.</span></span> <span data-ttu-id="22b77-153">因此，作为返回的数据`System.Nullable<int>`而不是`int`，并`System.Nullable<float>`而不是`float`。</span><span class="sxs-lookup"><span data-stu-id="22b77-153">Therefore, the data is returned as a `System.Nullable<int>` instead of `int`, and `System.Nullable<float>` instead of `float`.</span></span> <span data-ttu-id="22b77-154">可以从获取实际值`System.Nullable<'T>`通过使用对象`Value`属性，并且可以确定是否`System.Nullable<'T>`的对象的值通过调用`HasValue`方法。</span><span class="sxs-lookup"><span data-stu-id="22b77-154">The actual value can be obtained from a `System.Nullable<'T>` object by using the `Value` property, and you can determine if a `System.Nullable<'T>` object has a value by calling the `HasValue` method.</span></span> <span data-ttu-id="22b77-155">另一个有用的方法是`System.Nullable<'T>.GetValueOrDefault`方法，让你能够获取的值或默认值为适当的类型。</span><span class="sxs-lookup"><span data-stu-id="22b77-155">Another useful method is the `System.Nullable<'T>.GetValueOrDefault` method, which allows you to get the value or a default value of the appropriate type.</span></span> <span data-ttu-id="22b77-156">默认值是某种形式的"零"值，例如 0、 0.0 或`false`。</span><span class="sxs-lookup"><span data-stu-id="22b77-156">The default value is some form of "zero" value, such as 0, 0.0, or `false`.</span></span>

<span data-ttu-id="22b77-157">可能会为 null 的类型转换为不可为 null 的基元类型，如使用常用转换运算符`int`或`float`。</span><span class="sxs-lookup"><span data-stu-id="22b77-157">Nullable types may be converted to non-nullable primitive types using the usual conversion operators such as `int` or `float`.</span></span> <span data-ttu-id="22b77-158">还有可能要从一种可以为 null 的类型转换为另一种可以为 null 的类型，通过使用转换运算符可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="22b77-158">It is also possible to convert from one nullable type to another nullable type by using the conversion operators for nullable types.</span></span> <span data-ttu-id="22b77-159">适当的转换运算符具有相同的名称作为标准的但它们是在单独的模块， [Nullable](https://msdn.microsoft.com/library/e7a4ea13-28cc-462e-bc3a-33131ace976e)中的模块[Microsoft.FSharp.Linq](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d)命名空间。</span><span class="sxs-lookup"><span data-stu-id="22b77-159">The appropriate conversion operators have the same name as the standard ones, but they are in a separate module, the [Nullable](https://msdn.microsoft.com/library/e7a4ea13-28cc-462e-bc3a-33131ace976e) module in the [Microsoft.FSharp.Linq](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d) namespace.</span></span> <span data-ttu-id="22b77-160">通常情况下，使用查询表达式时打开此命名空间。</span><span class="sxs-lookup"><span data-stu-id="22b77-160">Typically, you open this namespace when working with query expressions.</span></span> <span data-ttu-id="22b77-161">在这种情况下，可以通过添加前缀使用可以为 null 的转换运算符`Nullable.`到适当的转换运算符，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="22b77-161">In that case, you can use the nullable conversion operators by adding the prefix `Nullable.` to the appropriate conversion operator, as shown in the following code.</span></span>

```fsharp
open Microsoft.FSharp.Linq

let nullableInt = new System.Nullable<int>(10)

// Use the Nullable.float conversion operator to convert from one nullable type to another nullable type.
let nullableFloat = Nullable.float nullableInt

// Use the regular non-nullable float operator to convert to a non-nullable float.
printfn "%f" (float nullableFloat)
```

<span data-ttu-id="22b77-162">输出为 `10.000000`。</span><span class="sxs-lookup"><span data-stu-id="22b77-162">The output is `10.000000`.</span></span>

<span data-ttu-id="22b77-163">查询运算符可以为 null 的数据字段，如`sumByNullable`，也存在在查询表达式中使用。</span><span class="sxs-lookup"><span data-stu-id="22b77-163">Query operators on nullable data fields, such as `sumByNullable`, also exist for use in query expressions.</span></span> <span data-ttu-id="22b77-164">不可以为 null 的类型的查询运算符不兼容的类型与 null 的类型，因此使用可以为 null 数据值时，必须使用相应的查询运算符的可以为 null 版本。</span><span class="sxs-lookup"><span data-stu-id="22b77-164">The query operators for non-nullable types are not type-compatible with nullable types, so you must use the nullable version of the appropriate query operator when you are working with nullable data values.</span></span> <span data-ttu-id="22b77-165">有关详细信息，请参阅[查询表达式](../query-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="22b77-165">For more information, see [Query Expressions](../query-expressions.md).</span></span>

<span data-ttu-id="22b77-166">下面的示例演示如何使用可以为 null 的运算符中的F#查询表达式。</span><span class="sxs-lookup"><span data-stu-id="22b77-166">The following example shows the use of nullable operators in an F# query expression.</span></span> <span data-ttu-id="22b77-167">第一个查询显示如何编写查询中不可以为 null 的运算符;第二个查询显示了使用可以为 null 的运算符的等效查询。</span><span class="sxs-lookup"><span data-stu-id="22b77-167">The first query shows how you would write a query without a nullable operator; the second query shows an equivalent query that uses a nullable operator.</span></span> <span data-ttu-id="22b77-168">有关完整的上下文，包括如何将数据库设置为使用此代码示例，请参阅[演练：使用类型提供程序访问 SQL 数据库](../../tutorials/type-providers/accessing-a-sql-database.md)。</span><span class="sxs-lookup"><span data-stu-id="22b77-168">For the full context, including how to set up the database to use this sample code, see [Walkthrough: Accessing a SQL Database by Using Type Providers](../../tutorials/type-providers/accessing-a-sql-database.md).</span></span>

```fsharp
open System
open System.Data
open System.Data.Linq
open Microsoft.FSharp.Data.TypeProviders
open Microsoft.FSharp.Linq

[<Generate>]
type dbSchema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;">

let db = dbSchema.GetDataContext()

query {
    for row in db.Table2 do
    where (row.TestData1.HasValue && row.TestData1.Value > 2)
    select row
} |> Seq.iter (fun row -> printfn "%d %s" row.TestData1.Value row.Name)

query {
    for row in db.Table2 do
    // Use a nullable operator ?>
    where (row.TestData1 ?> 2)
    select row
} |> Seq.iter (fun row -> printfn "%d %s" (row.TestData1.GetValueOrDefault()) row.Name)
```

## <a name="see-also"></a><span data-ttu-id="22b77-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="22b77-169">See also</span></span>

- [<span data-ttu-id="22b77-170">类型提供程序</span><span class="sxs-lookup"><span data-stu-id="22b77-170">Type Providers</span></span>](../../tutorials/type-providers/index.md)
- [<span data-ttu-id="22b77-171">查询表达式</span><span class="sxs-lookup"><span data-stu-id="22b77-171">Query Expressions</span></span>](../query-expressions.md)