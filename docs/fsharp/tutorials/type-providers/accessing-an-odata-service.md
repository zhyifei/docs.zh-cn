---
title: "演练：使用类型提供程序访问 OData 服务 (F#)"
description: "了解如何使用 F # 3.0 F # ODataService 类型提供程序生成的 OData 服务的客户端类型，并查询数据馈送的服务提供。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0adae84c-b0fa-455f-994b-274ecdc6df30
ms.openlocfilehash: 750407c36a989cece30c0c0654ff905c8eee3b33
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-accessing-an-odata-service-by-using-type-providers"></a>演练：使用类型提供程序访问 OData 服务

> [!NOTE]
此指南专门针对 F # 3.0 编写，并将更新。  请参阅 [FSharp.Data](https://fsharp.github.io/FSharp.Data/) 了解最新的跨平台类型提供程序。

> [!NOTE]
API 参考链接将转到 MSDN。  Docs.microsoft.com API 参考尚未完成。

OData 中，这意味着开放数据协议，是用于通过 Internet 传输数据的协议。 许多数据提供程序公开的发布的 OData web 服务访问其数据。 你可以从 F # 3.0 中使用数据类型自动生成的任何 OData 源访问数据`ODataService`类型提供程序。 有关 OData 的详细信息，请参阅 https://msdn.microsoft.com/library/da3380cc-f6da-4c6c-bdb2-bb86afa59d62。

本演练演示如何使用 F # ODataService 类型提供程序生成的 OData 服务的客户端类型，并查询数据馈送的服务提供。

此演练演示了下列任务，你应按以下顺序执行这些任务才能成功完成演练：


- 配置用于 OData 服务的客户端项目
<br />

- 访问 OData 类型
<br />

- 查询 OData 服务
<br />

- 验证 OData 请求
<br />


## <a name="configuring-a-client-project-for-an-odata-service"></a>配置用于 OData 服务的客户端项目
在此步骤中，你将设置一个项目使用的 OData 类型提供程序。


#### <a name="to-configure-a-client-project-for-an-odata-service"></a>若要配置用于 OData 服务的客户端项目

- 打开 F # 控制台应用程序项目，并将对引用`System.Data.Services.Client`Framework 程序集。
<br />

- 下`Extensions`，添加对的引用`FSharp.Data.TypeProviders`程序集。
<br />

## <a name="accessing-odata-types"></a>访问 OData 类型
在此步骤中，你创建的类型提供程序提供的 OData 服务的类型和数据的访问权限。


#### <a name="to-access-odata-types"></a>若要访问 OData 类型

- 在代码编辑器中，打开 F # 源代码文件，然后输入下面的代码。
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type Northwind = ODataService<"https://services.odata.org/Northwind/Northwind.svc/">

let db = Northwind.GetDataContext()
let fullContext = Northwind.ServiceTypes.NorthwindEntities()
```

在此示例中，你已调用 F # 类型提供程序，并且指示它创建的一组基于你指定 OData URI 的类型。 两个对象均可包含的数据; 信息一个是简化的数据上下文，`db`在示例中。 此对象仅包含数据类型关联数据库，包括表或源的类型。 另一个对象，`fullContext`在此示例中，是的一个实例`System.Data.Linq.DataContext`和包含许多其他属性、 方法和事件。
<br />


## <a name="querying-an-odata-service"></a>查询 OData 服务
在此步骤中，你可以使用 F # 查询表达式查询 OData 服务。


#### <a name="to-query-an-odata-service"></a>若要查询的 OData 服务

1. 现在，你已设置类型提供程序，你可以查询 OData 服务。
<br />  OData 支持的可用查询操作的一个子集。 支持以下操作和其相应的关键字：
<br />
  - 投影 (`select`)
<br />

  - 筛选 (`where`、 通过使用字符串和日期操作)
<br />

  - 分页 (`skip`， `take`)
<br />

  - 排序 (`orderBy`， `thenBy`)
<br />

  - `AddQueryOption` 和`Expand`，这是 OData 特定的操作
<br />

  有关详细信息，请参阅[LINQ 注意事项 &#40;WCF 数据服务 &#41;](https://msdn.microsoft.com/library/ee622463.aspx).
<br />  如果您需要所有源或表中的条目，则使用查询表达式，如以下代码所示的最简单形式：
<br />

```fsharp
query {
  for customer in db.Customers do
  select customer
} |> Seq.iter (fun customer ->
                  printfn "ID: %s\nCompany: %s" customer.CustomerID customer.CompanyName
                  printfn "Contact: %s\nAddress: %s" customer.ContactName customer.Address
                  printfn "         %s, %s %s" customer.City customer.Region customer.PostalCode
                  printfn "%s\n" customer.Phone)
```

2. 指定的字段或 select 关键字后使用一个元组所需的列。
<br />

```fsharp
  query { 
    for cat in db.Categories do
    select (cat.CategoryID, cat.CategoryName, cat.Description)
  } |> Seq.iter (fun (id, name, description) ->
                    printfn "ID: %d\nCategory: %s\nDescription: %s\n" id name description)
```

3. 通过使用指定条件`where`子句。
<br />

```fsharp
query {
  for employee in db.Employees do
  where (employee.EmployeeID = 9)
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID))
```

4. 通过使用指定的子字符串条件对查询`System.String.Contains(System.String)`方法。 下面的查询返回其名称中有"Chef"的所有产品。 此外请注意，使用`System.Nullable<'T>.GetValueOrDefault()`。 `UnitPrice`是可以为 null 的值，因此你必须要么获取的值，通过使用`Value`属性，或你必须调用`System.Nullable<'T>.GetValueOrDefault()`。
<br />

```fsharp
query { 
  for product in db.Products do
  where (product.ProductName.Contains("Chef"))
  select product
} |> Seq.iter (fun product ->
                  printfn "ID: %d Product: %s" product.ProductID product.ProductName
                  printfn "Price: %M\n" (product.UnitPrice.GetValueOrDefault()))
```

5. 使用`System.String.EndsWith(System.String)`方法，以指定字符串结尾以特定子。
<br />

```fsharp
query {
  for product in db.Products do
  where (product.ProductName.EndsWith("u"))
  select product
} |> Seq.iter (fun product ->
                  printfn "ID: %d Product: %s" product.ProductID product.ProductName
                  printfn "Price: %M\n" (product.UnitPrice.GetValueOrDefault()))
```

6. 将条件组合在 where 子句使用`&&`运算符。
<br />

```fsharp
// Open this module to use the nullable operators ?> and ?<.
open Microsoft.FSharp.Linq.NullableOperators

let salesIn1997 = query { 
  for sales in db.Category_Sales_for_1997 do
  where (sales.CategorySales ?> 50000.00M && sales.CategorySales ?< 60000.0M)
  select sales }

salesIn1997
|> Seq.iter (fun sales ->
                printfn "Category: %s Sales: %M" sales.CategoryName (sales.CategorySales.GetValueOrDefault()))
```

运算符`?>`和`?<`是可以为 null 的运算符。 你可以使用一套完整的可以为 null 的相等和比较运算符。 有关详细信息，请参阅[Linq.NullableOperators 模块](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d)。
<br />

7. 使用`sortBy`查询运算符来指定排序，并使用`thenBy`指定的排序的另一个级别。 请注意，还使用一个元组中的查询的 select 部分。 因此，查询必须为元素类型的元组。
<br />

```fsharp
printfn "Freight for some orders: "

query { 
  for order in db.Orders do
  sortBy (order.OrderDate.Value)
  thenBy (order.OrderID)
  select (order.OrderDate, order.OrderID, order.Customer.CompanyName)
} |> Seq.iter (fun (orderDate, orderID, company) ->
                  printfn "OrderDate: %s" (orderDate.GetValueOrDefault().ToString())
                  printfn "OrderID: %d Company: %s\n" orderID company)
```

8. 通过使用 skip 运算符，忽略指定的数目的记录，并使用 take 运算符来指定要返回的记录数。 这种方式，则可以在数据源实现分页。
<br />

```fsharp
printfn "Get the first page of 2 employees."

query { 
  for employee in db.Employees do
  take 2
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID)) 

printfn "Get the next 2 employees."

query { 
  for employee in db.Employees do
  skip 2
  take 2
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID))
```

## <a name="verifying-the-odata-request"></a>验证 OData 请求
每个 OData 查询将转换为特定的 OData 请求 URI。 你可以验证，URI，可能是用于调试目的，通过添加到事件处理程序`SendingRequest`完整数据上下文对象上的事件。


#### <a name="to-verify-the-odata-request"></a>若要验证 OData 请求

- 若要验证 OData 请求 URI，请使用下面的代码：
<br />

```fsharp
// The DataContext property returns the full data context.
db.DataContext.SendingRequest.Add (fun eventArgs -> printfn "Requesting %A" eventArgs.Request.RequestUri)
```

前面的代码的输出为：
<br />`requesting https://services.odata.org/Northwind/Northwind.svc/Orders()?$orderby=ShippedDate&amp;$select=OrderID,ShippedDate`


## <a name="see-also"></a>请参阅
[查询表达式](../../language-reference/query-expressions.md)

[LINQ 注意事项 （WCF 数据服务）](https://msdn.microsoft.com/library/ee622463.aspx)

[ODataService 类型提供程序 （F #）](https://msdn.microsoft.com/visualfsharpdocs/conceptual/odataservice-type-provider-%5bfsharp%5d)
