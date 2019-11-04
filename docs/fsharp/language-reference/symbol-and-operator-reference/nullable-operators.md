---
title: 可以为 null 的运算符
description: 了解F#编程语言中可用的可以为 null 的运算符。
ms.date: 05/16/2016
ms.openlocfilehash: 9c747cf5c2e07ca9f80cef741d71d892fb437b3a
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424046"
---
# <a name="nullable-operators"></a>可以为 null 的运算符

可以为 null 的运算符是在一侧或两侧使用可以为 null 的算术类型的二进制算法或比较运算符。 如果你使用的数据源（例如允许 null 代替实际值的数据库）使用数据，则会经常出现可为 null 的类型。 在查询表达式中经常使用可以为 null 的运算符。 除了用于算术和比较的可以为 null 的运算符以外，转换运算符还可用于在可以为 null 的类型之间进行转换。 某些查询运算符还可以是可以为 null 的版本。

## <a name="table-of-nullable-operators"></a>可以为 Null 的运算符表

下表列出了该语言支持的可以F#为 null 的运算符。

|左空|在右侧可以为 null|两边可以为 null|
|---|---|---|
|[？ > =](https://msdn.microsoft.com/library/94d29e32-a204-4f60-a527-6b0af86268f3)|[> =？](https://msdn.microsoft.com/library/0a255d8e-8cae-4160-ae61-243a5d96583f)|[？ > =？](https://msdn.microsoft.com/library/3051a50f-d276-4c84-9d73-bf2efeddef94)|
|[？ >](https://msdn.microsoft.com/library/62dc0021-1312-4ac3-be87-798b60b81bb6)|[>？](https://msdn.microsoft.com/library/0ad1284b-de48-4a04-83d8-b6f13c9c8936)|[？ >？](https://msdn.microsoft.com/library/dc18b6fa-30c4-47b0-9057-794439378a05)|
|[？ < =](https://msdn.microsoft.com/library/56fddf0a-e4ca-4891-a3be-fad1876be3b6)|[< =？](https://msdn.microsoft.com/library/02454a0f-30ca-4e77-ad84-ee7837461804)|[？ < =？](https://msdn.microsoft.com/library/5c37c28c-0b57-4da5-be11-5a123f7e8ee4)|
|[？ <](https://msdn.microsoft.com/library/b71897f0-6e29-4c58-b0a7-a5bfa6f88917)|[<？](https://msdn.microsoft.com/library/be9ea40f-a67f-4e98-8067-a14046752e8b)|[？ <？](https://msdn.microsoft.com/library/6f1962c8-5605-468c-94ae-f379ae98e17d)|
|[?=](https://msdn.microsoft.com/library/5cdc8ff6-244b-49cf-9376-69ecf249fd7c)|[=?](https://msdn.microsoft.com/library/d2102894-6a51-475d-890a-735568c31f87)|[?=?](https://msdn.microsoft.com/library/5f793f29-1084-4570-b1c1-17c1b7ef764b)|
|[？ < >](https://msdn.microsoft.com/library/3643a5a8-2ea5-4ad6-82c4-83927c3884a0)|[< >？](https://msdn.microsoft.com/library/3179aace-70c4-4911-9258-619592214976)|[？ < >？](https://msdn.microsoft.com/library/5da813d8-ee75-45b8-9ef4-146dcb6d394d)|
|[?+](https://msdn.microsoft.com/library/2e8ddd05-b3f3-41b3-9d73-938d9e540f3f)|[+?](https://msdn.microsoft.com/library/74772ea8-f010-493e-bdb5-ba347f2fd4f1)|[?+?](https://msdn.microsoft.com/library/57f28137-0f42-43d2-92af-cad8c6c9d05f)|
|[?-](https://msdn.microsoft.com/library/f237a7a6-89f2-48b2-a2fe-f0b98a2bedc2)|[-?](https://msdn.microsoft.com/library/4a345c07-314a-48f1-b557-ce072583589c)|[?-?](https://msdn.microsoft.com/library/e0024142-1d2a-4607-a39c-1eb1e86fa25a)|
|[?*](https://msdn.microsoft.com/library/519da708-5ad6-4075-9d74-d00441cd6078)|[*?](https://msdn.microsoft.com/library/04c47870-de7b-480d-98a0-f47593b4ffac)|[?*?](https://msdn.microsoft.com/library/e57057ba-9c3a-40ec-8401-150c2b25f75b)|
|[?/](https://msdn.microsoft.com/library/add02a42-f556-40a7-a168-fbf2053322e3)|[/?](https://msdn.microsoft.com/library/1de07646-3778-476d-8c61-5d37495d463c)|[?/?](https://msdn.microsoft.com/library/b17be0ac-bf98-4590-861d-a4dd6c6fa535)|
|[?%](https://msdn.microsoft.com/library/44297bba-1bd9-4ed2-a848-f1e1e598db87)|[%?](https://msdn.microsoft.com/library/a4c178e5-eec4-42e8-847f-90b24fc609fe)|[?%?](https://msdn.microsoft.com/library/dd555f20-1be3-4b8d-81f1-bf1921e62fda)|

## <a name="remarks"></a>备注

可为 null 的运算符包含在命名空间[NullableOperators](https://msdn.microsoft.com/library/2c3633c5-3f31-4d62-a9f8-272ad6b19007)中的[fsharp.core](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d)模块中。 可以为 null 的数据 `System.Nullable<'T>`的类型。

在查询表达式中，从允许空值而不是值的数据源中选择数据时，可以为 null 的类型。 在 SQL Server 数据库中，表中的每个数据列都有一个属性，该属性指示是否允许 null 值。 如果允许使用 null 值，则从数据库返回的数据可能包含不能用基元数据类型（如 `int`、`float`等）表示的 null 值。 因此，数据将作为 `System.Nullable<int>` 而不是 `int`返回，而不是 `float``System.Nullable<float>`。 可以通过使用 `Value` 属性从 `System.Nullable<'T>` 对象获取实际值，并且可以通过调用 `HasValue` 方法来确定 `System.Nullable<'T>` 对象是否具有值。 另一种有用的方法是 `System.Nullable<'T>.GetValueOrDefault` 方法，该方法允许您获取适当类型的值或默认值。 默认值为 "零" 值的某种形式，例如0、0.0 或 `false`。

可以为 null 的类型使用常用转换运算符（如 `int` 或 `float`）转换为不可为 null 的基元类型。 使用可以为 null 的类型的转换运算符，还可以从一个可以为 null 的类型转换为另一个可以为 null 的类型。 适当的转换运算符与标准的转换运算符具有相同的名称，但它们位于单独的模块中，这是[fsharp.core](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d)命名空间中的[可为 null](https://msdn.microsoft.com/library/e7a4ea13-28cc-462e-bc3a-33131ace976e)的模块。 通常，在使用查询表达式时打开此命名空间。 在这种情况下，可以通过将前缀 `Nullable.` 添加到相应的转换运算符来使用可以为 null 的转换运算符，如下面的代码所示。

```fsharp
open Microsoft.FSharp.Linq

let nullableInt = new System.Nullable<int>(10)

// Use the Nullable.float conversion operator to convert from one nullable type to another nullable type.
let nullableFloat = Nullable.float nullableInt

// Use the regular non-nullable float operator to convert to a non-nullable float.
printfn "%f" (float nullableFloat)
```

输出为 `10.000000`。

可以为 null 的数据字段（如 `sumByNullable`）上的查询运算符也存在，可用于查询表达式中。 不可以为 null 的类型的查询运算符与可为 null 的类型不兼容，因此，当你使用可以为 null 的数据值时，必须使用适当查询运算符的可为 null 版本。 有关详细信息，请参阅[查询表达式](../query-expressions.md)。

下面的示例演示如何在F#查询表达式中使用可以为 null 的运算符。 第一个查询显示了如何在没有可为 null 的运算符的情况下编写查询;第二个查询显示使用可以为 null 的运算符的等效查询。 有关完整的上下文，包括如何将数据库设置为使用此示例代码，请参阅[演练：使用类型提供程序访问 SQL 数据库](../../tutorials/type-providers/index.md)。

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

- [类型提供程序](../../tutorials/type-providers/index.md)
- [查询表达式](../query-expressions.md)
