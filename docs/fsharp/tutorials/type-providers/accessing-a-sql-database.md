---
title: "演练：使用类型提供程序访问 SQL 数据库 (F#)"
description: "了解如何使用 F # 3.0 (LINQ to SQL) SqlDataConnection 类型提供程序生成为 SQL 数据库的类型时具有的实时数据库连接。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1c413eb0-16a5-4c1a-9a4e-ad6877e645d6
ms.openlocfilehash: dbc5d889fb7883b4327180fdf34accf45bf519e7
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers"></a>演练：使用类型提供程序访问 SQL 数据库

> [!NOTE]
此指南专门针对 F # 3.0 编写，并将更新。  请参阅 [FSharp.Data](https://fsharp.github.io/FSharp.Data/) 了解最新的跨平台类型提供程序。

> [!NOTE]
API 参考链接将转到 MSDN。  Docs.microsoft.com API 参考尚未完成。

本演练说明了如何使用 SqlDataConnection (LINQ to SQL) 类型提供程序会出现在 F # 3.0 时必须与数据库的实时连接 SQL 数据库中生成数据的类型。 如果你没有实时连接到数据库，但必须 LINQ to SQL 架构文件 （DBML 文件），请参阅[演练： 从 DBML 文件生成 F # 类型](generating-fsharp-types-from-dbml.md)。

本演练阐释了以下任务。 必须按才能成功完成演练以下顺序执行这些任务：


- 准备测试数据库

- 创建项目

- 设置类型提供程序

- 查询数据

- 使用可以为 null 的字段

- 调用存储过程

- 更新数据库

- 执行 TRANSACT-SQL 代码

- 使用完整数据上下文

- 删除数据

- 创建一个测试数据库 （如需要）

## <a name="preparing-a-test-database"></a>准备测试数据库
在服务器上运行 SQL Server，创建用于测试目的的数据库。 你可以使用数据库在此页底部的部分中创建脚本[创建测试数据库](#creating-a-test-database)要这样做。


#### <a name="to-prepare-a-test-database"></a>若要准备测试数据库

若要运行 MyDatabase 创建脚本，请打开**视图**菜单，然后选择**SQL Server 对象资源管理器**或选择 Ctrl +\, Ctrl + S 键。 在**SQL Server 对象资源管理器**窗口中，打开相应的实例的快捷菜单，选择**新查询**复制底部的此页上，该脚本，然后将脚本粘贴到编辑器。 若要运行 SQL 脚本，请选择工具栏上的图标三角形符号，或选择 Ctrl + Q 键。 有关详细信息**SQL Server 对象资源管理器**，请参阅[连接的数据库开发](https://msdn.microsoft.com/library/hh272679(VS.103).aspx)。


## <a name="creating-the-project"></a>创建项目
接下来，你创建的 F # 应用程序项目。


#### <a name="to-create-and-set-up-the-project"></a>创建并设置项目

1. 创建新的 F # 应用程序项目。

2. 将引用添加到[FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3)，以及`System.Data`，和`System.Data.Linq`。

3. 通过将以下代码行添加到你 F # 代码文件的顶部 Program.fs 打开相应的命名空间。

  ```fsharp
open System
open System.Data
open System.Data.Linq
open Microsoft.FSharp.Data.TypeProviders
open Microsoft.FSharp.Linq
```

4. 与大多数 F # 程序，你可以在作为编译的程序，本演练中执行代码，或作为脚本，可以以交互方式运行它。 如果想要使用脚本，打开选择的项目节点的快捷菜单**添加新项**，添加 F # 脚本文件，并向该脚本每个步骤中添加代码。 你将需要在要加载的程序集引用的文件的顶部添加以下行。

  ```fsharp
#r "System.Data.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

  然后，您可以选择每个代码块，如将其添加并按 Alt + Enter 以在 F # Interactive 中运行它。

## <a name="setting-up-a-type-provider"></a>设置类型提供程序
在此步骤中，为你的数据库架构创建类型提供程序。


#### <a name="to-set-up-the-type-provider-from-a-direct-database-connection"></a>若要设置类型提供程序从直接的数据库连接

有两个关键行的所需创建可用于查询 SQL 数据库使用类型提供程序的类型的代码。 首先，您实例化类型提供程序。 若要执行此操作，创建如下所示的类型缩写`SqlDataConnection`与静态泛型参数。 `SqlDataConnection` 是 SQL 类型提供程序，并且不应与混淆`SqlConnection`类型，ADO.NET 编程中使用。 如果你有一个你想要连接到的数据库，并具有一个连接字符串，使用下面的代码来调用类型提供程序。 替换给定的示例字符串自己连接字符串。 例如，如果你的服务器是 MYSERVER 和数据库实例是实例、 数据库名称是 MyDatabase，并且你想要使用 Windows 身份验证访问数据库，则连接字符串是作为提供在下面的示例代码。

```fsharp
type dbSchema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;">
let db = dbSchema.GetDataContext()

// Enable the logging of database activity to the console.
db.DataContext.Log <- System.Console.Out
```

现在你拥有一种类型， `dbSchema`，这是一个父类型，包含表示数据库表的所有生成的类型。 您也有一个对象， `db`，它具有作为其成员数据库中的所有表。 表名称属性，并且这些属性的类型生成的 F # 编译器。 本身的类型显示为在下的嵌套类型`dbSchema.ServiceTypes`。 因此，为这些表的行检索任何数据将为该表生成的相应类型的实例。 类型的名称是`ServiceTypes.Table1`。

若要熟悉的 F # 语言如何解释为 SQL 查询的查询，查看设置行`Log`上的数据上下文的属性。

若要进一步浏览类型提供程序创建的类型，添加以下代码。

```fsharp
let table1 = db.Table1
```

将鼠标悬停在`table1`以查看其类型。 其类型是`System.Data.Linq.Table<dbSchema.ServiceTypes.Table1>`和泛型参数意味着每个行的类型生成的类型， `dbSchema.ServiceTypes.Table1`。 编译器在数据库中创建类似类型的每个表。

## <a name="querying-the-data"></a>查询数据
在此步骤中，你可以编写一个查询使用 F # 查询表达式。


#### <a name="to-query-the-data"></a>查询数据

1. 现在在数据库中创建该表的查询。 添加以下代码。

  ```fsharp
   let query1 =
     query {
       for row in db.Table1 do
       select row
     }
   query1 |> Seq.iter (fun row -> printfn "%s %d" row.Name row.TestData1)
```

  Word 的外观`query`指示这是一个查询表达式，生成类似的典型数据库查询的结果的集合的计算表达式的类型。 如果你将鼠标悬停在查询，你将看到它是实例[Linq.QueryBuilder 类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.querybuilder-class-%5bfsharp%5d)，用于定义 query 计算表达式的类型。 如果将鼠标悬停在`query1`，你将看到它是实例`System.Linq.IQueryable`。 顾名思义，`System.Linq.IQueryable`表示数据可能无法进行查询，不是查询的结果。 查询时要遵守迟缓计算中，数据库才这意味着查询何时计算查询。 最后一行将通过查询传递`Seq.iter`。 查询可枚举，可能会像序列循环访问。 有关详细信息，请参阅[查询表达式](../../language-reference/query-expressions.md)。

2. 向查询添加查询运算符。 有大量的查询运算符可以用来构造更复杂的查询。 此示例还显示您可以消除查询变量并改为使用管道运算符。

  ```fsharp
   query {
     for row in db.Table1 do
     where (row.TestData1 > 2)
     select row
   } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

3. 添加具有两个表的联接更复杂的查询。

  ```fsharp
   query {
     for row1 in db.Table1 do
     join row2 in db.Table2 on (row1.Id = row2.Id)
     select (row1, row2)
   } |> Seq.iteri (fun index (row1, row2) ->
                   if (index = 0) then printfn "Table1.Id TestData1 TestData2 Name Table2.Id TestData1 TestData2 Name"
                   printfn "%d %d %f %s %d %d %f %s" row1.Id row1.TestData1 row1.TestData2 row1.Name
                     row2.Id (row2.TestData1.GetValueOrDefault()) (row2.TestData2.GetValueOrDefault()) row2.Name)
```

4. 在现实世界代码中，在查询中的参数通常是值或变量、 不是编译时常量。 添加以下代码，将查询包装在一个函数，它接受一个参数，并随后调用该函数中的使用值 10。

  ```fsharp
   let findData param =
     query {
       for row in db.Table1 do
       where (row.TestData1 = param)
       select row
     }

   findData 10 |> Seq.iter (fun row -> printfn "Found row: %d %d %f %s" row.Id row.TestData1 row.TestData2 row.Name)
```

## <a name="working-with-nullable-fields"></a>使用可以为 null 的字段
在数据库中，字段通常允许 null 值。 在.NET 类型系统中，你不能用于允许使用 null 因为这些类型不具有 null 值作为可能的值的数据的普通的数值数据类型。 因此，这些值由的实例表示`System.Nullable`类型。 而不是访问此类字段的值直接与字段的名称，你需要添加一些附加步骤。 你可以使用`System.Nullable.Value`属性来访问基础值的 null 的类型。 `System.Nullable.Value`属性而不是具有值 null 的对象是否引发异常。 你可以使用`System.Nullable.HasValue`布尔方法以确定是否存在一个值，或使用`System.Nullable.GetValueOrDefault()`以确保在所有情况下具有一个实际值。 如果你使用`System.Nullable.GetValueOrDefault()`并在数据库中，没有 null 然后则替换它与一个值，如字符串类型的空字符串，0 表示整数类型或对浮点 0.0 点类型。

当你需要执行中可以为 null 值的相等性测试或比较`where`在查询中的子句，你可以使用可以为 null 的运算符中找到[Linq.NullableOperators 模块](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d)。 这些是正则比较运算符一样`=`， `>`， `<=`，依此类推，只不过将显示一个问号左侧或右侧的运算符的可以为 null 的值是。 例如，运算符`>?`大于-比右侧可以为 null 值的运算符。 这些运算符的工作的方式是，如果任意一侧的表达式为 null，表达式计算结果为`false`。 在`where`子句，这通常意味着，不选中并不返回查询结果中包含 null 字段的行。


#### <a name="to-work-with-nullable-fields"></a>可以使用可以为 null 的字段

下面的代码演示使用可以为 null 值;假定**TestData1**是一个整数字段，允许空值。

```fsharp
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

## <a name="calling-a-stored-procedure"></a>调用存储过程
在数据库上的任何存储的过程可以从 F # 中调用。 必须设置静态参数`StoredProcedures`到`true`中的类型提供程序实例化。 类型提供程序`SqlDataConnection`包含可用于配置生成的类型的若干静态方法。 有关这些的完整说明，请参阅[SqlDataConnection 类型提供程序](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d)。 为每个存储过程生成的数据上下文类型上的方法。


#### <a name="to-call-a-stored-procedure"></a>调用存储过程

如果存储的过程采用可以为 null 的参数，请将传递相应`System.Nullable`值。 返回一个标量或表的存储的过程方法的返回值是`System.Data.Linq.ISingleResult`，其中包含使你能够访问返回的数据的属性。 类型参数`System.Data.Linq.ISingleResult`取决于特定过程和也是它在类型提供程序生成的类型。 存储过程名为`Procedure1`，该类型是`Procedure1Result`。 类型`Procedure1Result`包含名称的列中返回的表，或者，对于返回标量值的存储过程，它表示的返回值。

下面的代码假定有一个过程`Procedure1`采用两个可以为 null 整数作为参数的数据库上运行该查询将返回一个名为列`TestData1`，并返回一个整数。

```fsharp
type schema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;", StoredProcedures = true>

let testdb = schema.GetDataContext()

let nullable value = new System.Nullable<_>(value)

let callProcedure1 a b =
  let results = testdb.Procedure1(nullable a, nullable b)
  for result in results do
    printfn "%d" (result.TestData1.GetValueOrDefault())
  results.ReturnValue :?> int

printfn "Return Value: %d" (callProcedure1 10 20)
```

## <a name="updating-the-database"></a>更新数据库
LINQ DataContext 类型包含更加轻松地在生成的类型以完全类型化形式中执行事务处理的数据库更新的方法。


#### <a name="to-update-the-database"></a>更新数据库

1. 在下面的代码中，多个行添加到数据库中。 如果你仅在添加行，则可以使用`System.Data.Linq.Table.InsertOnSubmit()`来指定要添加的新行。 如果你在插入多行，应将其放到一个集合并调用`System.Data.Linq.Table.InsertAllOnSubmit(System.Collections.Generic.IEnumerable)`。 在调用这些方法之一时，不立即更改数据库。 必须调用`System.Data.Linq.DataContext.SubmitChanges`实际提交所做的更改。 默认情况下，在你之前执行的所有调用`System.Data.Linq.DataContext.SubmitChanges`是隐式在同一事务的一部分。

 ```fsharp
   let newRecord = new dbSchema.ServiceTypes.Table1(Id = 100,
                                                    TestData1 = 35, 
                                                    TestData2 = 2.0,
                                                    Name = "Testing123")

   let newValues =
     [ for i in [1 .. 10] ->
       new dbSchema.ServiceTypes.Table3(Id = 700 + i,
         Name = "Testing" + i.ToString(),
         Data = i) ]

   // Insert the new data into the database.
   db.Table1.InsertOnSubmit(newRecord)
   db.Table3.InsertAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully inserted new rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

2. 现在来清理行调用删除操作。

  ```fsharp
   // Now delete what was added.
   db.Table1.DeleteOnSubmit(newRecord)
   db.Table3.DeleteAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully deleted all pending rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="executing-transact-sql-code"></a>执行 TRANSACT-SQL 代码
此外可以直接通过使用指定 TRANSACT-SQL`System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])`方法`DataContext`类。


#### <a name="to-execute-custom-sql-commands"></a>执行自定义 SQL 命令

下面的代码演示如何发送 SQL 命令以将一个记录插入表以及从表中删除一条记录。

```fsharp
try
  db.DataContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'Testing', 55)") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message

try //AND Name = 'Testing' AND Data = 55
  db.DataContext.ExecuteCommand("DELETE FROM Table3 WHERE Id = 102 ") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="using-the-full-data-context"></a>使用完整数据上下文
在前面的示例中，`GetDataContext`方法用于获取所谓*简化的数据上下文*为数据库架构。 简化的数据上下文是更轻松地使用当你在构造查询，因为没有尽可能多的成员。 因此，当您浏览在 IntelliSense 中的属性，你可以专注于数据库结构，如表和存储的过程。 但是，没有限制你可以使用简化的数据上下文做什么。 提供的功能来执行其他操作的完整数据上下文。 也可用它位于`ServiceTypes`和具有名称的*DataContext*如果你提供的静态参数。 如果未提供，数据上下文类型的名称为你生成通过 SqlMetal.exe 根据其他输入。 完整数据上下文继承自`System.Data.Linq.DataContext`，并公开其基本类，其中包括对 ADO.NET 数据类型的引用，例如成员`Connection`对象、 等方法`System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])`和`System.Data.Linq.DataContext.ExecuteQuery(System.String,System.Object[])`可用于在 SQL 中，编写查询和另一种方式来显式使用事务。


#### <a name="to-use-the-full-data-context"></a>若要使用完整数据上下文

下面的代码演示获取完整数据上下文对象，并使用它来直接对数据库执行命令。 在这种情况下，两个命令将作为同一事务的一部分执行。

```fsharp
let dbConnection = testdb.Connection
let fullContext = new dbSchema.ServiceTypes.MyDatabase(dbConnection)

dbConnection.Open()

let transaction = dbConnection.BeginTransaction()
fullContext.Transaction <- transaction

try
  let result1 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'A', 55)")
  printfn "ExecuteCommand Result: %d" result1
  let result2 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (103, 'B', -2)")
  printfn "ExecuteCommand Result: %d" result2
  if (result1 <> 1 || result2 <> 1) then
    transaction.Rollback()
    printfn "Rolled back creation of two new rows."
  else
    transaction.Commit()
  printfn "Successfully committed two new rows."
with
| exn ->
  transaction.Rollback()
  printfn "Rolled back creation of two new rows due to exception:\n%s" exn.Message

dbConnection.Close()
```

## <a name="deleting-data"></a>删除数据
此步骤演示了如何删除数据表中的行。


#### <a name="to-delete-rows-from-the-database"></a>若要从数据库中删除行

现在，清除任何通过编写指定的表中的实例删除行的函数添加行`System.Data.Linq.Table`类。 编写查询以查找所有你想要删除的行，然后通过管道传递到查询的结果`deleteRows`函数。 此代码利用提供的函数自变量的部分应用的功能。

```fsharp
let deleteRowsFrom (table:Table<_>) rows =
  table.DeleteAllOnSubmit(rows)

query {
  for rows in db.Table3 do
  where (rows.Id > 10)
  select rows
} |> deleteRowsFrom db.Table3

db.DataContext.SubmitChanges()
printfn "Successfully deleted rows with Id greater than 10 in Table3."
```

## <a name="creating-a-test-database"></a>创建一个测试数据库
本部分演示如何将测试数据库设置为在此演练中使用。

请注意，是否你更改该数据库，以某种方式，你将需要重置类型提供程序。 若要重置类型提供程序，请重新生成或清理包含类型提供程序的项目。


#### <a name="to-create-the-test-database"></a>若要创建测试数据库

1. 在**服务器资源管理器**，打开快捷菜单**数据连接**节点，然后选择**添加连接**。 **添加连接**对话框随即出现。

2. 在**服务器名称**框中，指定具有管理访问权，SQL Server 实例的名称或如果你没有访问服务器，指定 (localdb \ v11.0)。 SQL Express LocalDB 提供了轻型数据库服务器进行开发和测试您的计算机上。 在中创建一个新的节点**服务器资源管理器**下**数据连接**。 有关 LocalDB 的详细信息，请参阅[演练： 在 Visual Studio 中创建本地数据库文件](https://msdn.microsoft.com/library/ms233763.aspx)。

3. 打开新连接节点的快捷菜单，然后选择**新查询**。

4. 复制以下 SQL 脚本，将其粘贴到查询编辑器中，，然后选择**执行**按钮在工具栏上，或选择 Ctrl + Shift + E 键。

```sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

USE [master];
GO

IF EXISTS (SELECT * FROM sys.databases WHERE name = 'MyDatabase')
  DROP DATABASE MyDatabase;
GO

-- Create the MyDatabase database.
CREATE DATABASE MyDatabase;
GO

-- Specify a simple recovery model 
-- to keep the log growth to a minimum.
ALTER DATABASE MyDatabase 
SET RECOVERY SIMPLE;
GO

USE MyDatabase;
GO

-- Create the Table1 table.
CREATE TABLE [dbo].[Table1] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NOT NULL,
  [TestData2] FLOAT (53) NOT NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);

-- Create the Table2 table.
CREATE TABLE [dbo].[Table2] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NULL,
  [TestData2] FLOAT (53) NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);


-- Create the Table3 table.
CREATE TABLE [dbo].[Table3] (
  [Id]   INT           NOT NULL,
  [Name] NVARCHAR (50) NOT NULL,
  [Data] INT           NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
  );
GO

CREATE PROCEDURE [dbo].[Procedure1]
  @param1 int = 0,
  @param2 int
AS
SELECT TestData1 FROM Table1
RETURN 0
GO

USE MyDatabase

-- Insert data into the Table1 table.
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');

-- Insert data into the Table2 table.
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(3, NULL, NULL, 'Testing3');

-- Insert data into the Table3 table.
INSERT INTO Table3 (Id, Name, Data)
  VALUES (1, 'Testing1', 10);
INSERT INTO Table3 (Id, Name, Data)
  VALUES (2, 'Testing2', 100);
```


## <a name="see-also"></a>请参阅
[类型提供程序](index.md)

[SqlDataConnection 类型提供程序](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d)

[演练： 根据 DBML 文件生成 F # 类型](generating-fsharp-types-from-dbml.md)

[查询表达式](../../language-reference/query-expressions.md)

[LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)

[SqlMetal.exe &#40;代码生成工具 &#41;](https://msdn.microsoft.com/library/bb386987)
