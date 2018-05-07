---
title: 可以为 null 的运算符 (F#)
description: '了解有关 F # 编程语言中可用的可以为 null 运算符。'
ms.date: 05/16/2016
ms.openlocfilehash: 63ad7da2d584b96eee8765b57fc671befbcbd38b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="nullable-operators"></a>可以为 null 的运算符

可以为 null 的运算符都是二元一端或两端使用可以为 null 的算术类型的算术或比较运算符。 经常当您使用如允许 null 值来代替实际值的数据库的源中的数据时，会出现可以为 null 的类型。 在查询表达式中经常使用可以为 null 的运算符。 除了算术运算符和比较的可以为 null 的运算符，可以使用转换运算符，可以为 null 的类型之间进行转换。 也有某些查询运算符的可以为 null 版本。


## <a name="table-of-nullable-operators"></a>可以为 Null 的运算符表
下表列出了 F # 语言中支持的可以为 null 运算符。

|在左侧的可以为 Null|右侧可以为 null|双方可以为 null|
|---|---|---|
|[?>=](https://msdn.microsoft.com/library/94d29e32-a204-4f60-a527-6b0af86268f3)|[>=?](https://msdn.microsoft.com/library/0a255d8e-8cae-4160-ae61-243a5d96583f)|[?>=?](https://msdn.microsoft.com/library/3051a50f-d276-4c84-9d73-bf2efeddef94)|
|[?>](https://msdn.microsoft.com/library/62dc0021-1312-4ac3-be87-798b60b81bb6)|[>?](https://msdn.microsoft.com/library/0ad1284b-de48-4a04-83d8-b6f13c9c8936)|[?>?](https://msdn.microsoft.com/library/dc18b6fa-30c4-47b0-9057-794439378a05)|
|[?<=](https://msdn.microsoft.com/library/56fddf0a-e4ca-4891-a3be-fad1876be3b6)|[<=?](https://msdn.microsoft.com/library/02454a0f-30ca-4e77-ad84-ee7837461804)|[?<=?](https://msdn.microsoft.com/library/5c37c28c-0b57-4da5-be11-5a123f7e8ee4)|
|[?<](https://msdn.microsoft.com/library/b71897f0-6e29-4c58-b0a7-a5bfa6f88917)|[<?](https://msdn.microsoft.com/library/be9ea40f-a67f-4e98-8067-a14046752e8b)|[?<?](https://msdn.microsoft.com/library/6f1962c8-5605-468c-94ae-f379ae98e17d)|
|[?=](https://msdn.microsoft.com/library/5cdc8ff6-244b-49cf-9376-69ecf249fd7c)|[=?](https://msdn.microsoft.com/library/d2102894-6a51-475d-890a-735568c31f87)|[?=?](https://msdn.microsoft.com/library/5f793f29-1084-4570-b1c1-17c1b7ef764b)|
|[?<>](https://msdn.microsoft.com/library/3643a5a8-2ea5-4ad6-82c4-83927c3884a0)|[<>?](https://msdn.microsoft.com/library/3179aace-70c4-4911-9258-619592214976)|[?<>?](https://msdn.microsoft.com/library/5da813d8-ee75-45b8-9ef4-146dcb6d394d)|
|[?+](https://msdn.microsoft.com/library/2e8ddd05-b3f3-41b3-9d73-938d9e540f3f)|[+?](https://msdn.microsoft.com/library/74772ea8-f010-493e-bdb5-ba347f2fd4f1)|[?+?](https://msdn.microsoft.com/library/57f28137-0f42-43d2-92af-cad8c6c9d05f)|
|[?-](https://msdn.microsoft.com/library/f237a7a6-89f2-48b2-a2fe-f0b98a2bedc2)|[-?](https://msdn.microsoft.com/library/4a345c07-314a-48f1-b557-ce072583589c)|[?-?](https://msdn.microsoft.com/library/e0024142-1d2a-4607-a39c-1eb1e86fa25a)|
|[?*](https://msdn.microsoft.com/library/519da708-5ad6-4075-9d74-d00441cd6078)|[*?](https://msdn.microsoft.com/library/04c47870-de7b-480d-98a0-f47593b4ffac)|[?*?](https://msdn.microsoft.com/library/e57057ba-9c3a-40ec-8401-150c2b25f75b)|
|[?/](https://msdn.microsoft.com/library/add02a42-f556-40a7-a168-fbf2053322e3)|[/?](https://msdn.microsoft.com/library/1de07646-3778-476d-8c61-5d37495d463c)|[?/?](https://msdn.microsoft.com/library/b17be0ac-bf98-4590-861d-a4dd6c6fa535)|
|[?%](https://msdn.microsoft.com/library/44297bba-1bd9-4ed2-a848-f1e1e598db87)|[%?](https://msdn.microsoft.com/library/a4c178e5-eec4-42e8-847f-90b24fc609fe)|[?%?](https://msdn.microsoft.com/library/dd555f20-1be3-4b8d-81f1-bf1921e62fda)|

## <a name="remarks"></a>备注
可以为 null 的运算符都将纳入[NullableOperators](https://msdn.microsoft.com/library/2c3633c5-3f31-4d62-a9f8-272ad6b19007)命名空间中的模块[Microsoft.FSharp.Linq](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d)。 对于可以为 null 的数据类型是`System.Nullable<'T>`。

在查询表达式中，选择允许空值而不是值的数据源的数据时，会出现可以为 null 的类型。 在 SQL Server 数据库中，表中的每个数据列具有属性，该值指示是否允许 null 值。 如果允许 null 值，从数据库中返回的数据可能包含不能如通过基元数据类型表示的 null `int`， `float`，依次类推。 因此，将数据返回为`System.Nullable<int>`而不是`int`，和`System.Nullable<float>`而不是`float`。 可以从获取的实际值`System.Nullable<'T>`对象使用`Value`属性，并且可以确定如果`System.Nullable<'T>`对象具有一个值，通过调用`HasValue`方法。 另一个有用方法是`System.Nullable<'T>.GetValueOrDefault`方法，使你能获取的值或相应类型的默认值。 默认值是某种形式的"零"值，例如 0，0.0，或`false`。

可以为 null 的类型可能转换为不可为 null 的基元类型，如使用常用转换运算符`int`或`float`。 还有可能将通过使用转换运算符适用于可以为 null 的类型从一种可以为 null 的类型转换为另一种可以为 null 的类型。 相应的转换运算符具有相同的名称的标准，但它们在单独模块中[可以为 Null](https://msdn.microsoft.com/library/e7a4ea13-28cc-462e-bc3a-33131ace976e)中的模块[Microsoft.FSharp.Linq](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d)命名空间。 通常情况下，使用查询表达式时打开此命名空间。 在这种情况下，可以通过添加前缀使用可以为 null 的转换运算符`Nullable.`到相应的转换运算符，如下面的代码中所示。

```fsharp
open Microsoft.FSharp.Linq

let nullableInt = new System.Nullable<int>(10)

// Use the Nullable.float conversion operator to convert from one nullable type to another nullable type.
let nullableFloat = Nullable.float nullableInt

// Use the regular non-nullable float operator to convert to a non-nullable float.
printfn "%f" (float nullableFloat)
```

输出为 `10.000000`。

查询运算符上可以为 null 的数据字段，如`sumByNullable`，也存在在查询表达式中使用。 不可为 null 的类型的查询运算符不与可以为 null 的类型的类型兼容，因此你必须使用相应的查询运算符的可以为 null 版本，当您正在使用可以为 null 数据值。 有关详细信息，请参阅[查询表达式](../query-expressions.md)。

下面的示例演示在 F # 查询表达式可以为 null 的运算符的使用。 第一个查询显示如何编写查询中不可以为 null 的运算符;第二个查询显示等效的查询使用可以为 null 的运算符。 有关完整的上下文，包括如何将数据库设置为使用此代码示例，请参阅[演练： 访问 SQL 数据库使用类型提供程序](../../tutorials/type-providers/accessing-a-sql-database.md)。

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

## <a name="see-also"></a>请参阅

[类型提供程序](../../tutorials/type-providers/index.md)

[查询表达式](../query-expressions.md)
