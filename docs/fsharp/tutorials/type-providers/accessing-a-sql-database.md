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
ms.openlocfilehash: 7177eca33ded712308bbc6198040d833b7364d55
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2017
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers"></a><span data-ttu-id="fb0ba-104">演练：使用类型提供程序访问 SQL 数据库</span><span class="sxs-lookup"><span data-stu-id="fb0ba-104">Walkthrough: Accessing a SQL Database by Using Type Providers</span></span>

> [!NOTE]
<span data-ttu-id="fb0ba-105">此指南专门针对 F # 3.0 编写，并将更新。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="fb0ba-106">请参阅 [FSharp.Data](http://fsharp.github.io/FSharp.Data/) 了解最新的跨平台类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-106">See [FSharp.Data](http://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="fb0ba-107">API 参考链接将转到 MSDN。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="fb0ba-108">Docs.microsoft.com API 参考尚未完成。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="fb0ba-109">本演练说明了如何使用 SqlDataConnection (LINQ to SQL) 类型提供程序会出现在 F # 3.0 时必须与数据库的实时连接 SQL 数据库中生成数据的类型。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-109">This walkthrough explains how to use the SqlDataConnection (LINQ to SQL) type provider that is available in F# 3.0 to generate types for data in a SQL database when you have a live connection to a database.</span></span> <span data-ttu-id="fb0ba-110">如果你没有实时连接到数据库，但必须 LINQ to SQL 架构文件 （DBML 文件），请参阅[演练： 从 DBML 文件生成 F # 类型](generating-fsharp-types-from-dbml.md)。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-110">If you do not have a live connection to a database, but you do have a LINQ to SQL schema file (DBML file), see [Walkthrough: Generating F# Types from a DBML File](generating-fsharp-types-from-dbml.md).</span></span>

<span data-ttu-id="fb0ba-111">本演练阐释了以下任务。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-111">This walkthrough illustrates the following tasks.</span></span> <span data-ttu-id="fb0ba-112">必须按才能成功完成演练以下顺序执行这些任务：</span><span class="sxs-lookup"><span data-stu-id="fb0ba-112">These tasks must be performed in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="fb0ba-113">准备测试数据库</span><span class="sxs-lookup"><span data-stu-id="fb0ba-113">Preparing a test database</span></span>

- <span data-ttu-id="fb0ba-114">创建项目</span><span class="sxs-lookup"><span data-stu-id="fb0ba-114">Creating the project</span></span>

- <span data-ttu-id="fb0ba-115">设置类型提供程序</span><span class="sxs-lookup"><span data-stu-id="fb0ba-115">Setting up a type provider</span></span>

- <span data-ttu-id="fb0ba-116">查询数据</span><span class="sxs-lookup"><span data-stu-id="fb0ba-116">Querying the data</span></span>

- <span data-ttu-id="fb0ba-117">使用可以为 null 的字段</span><span class="sxs-lookup"><span data-stu-id="fb0ba-117">Working with nullable fields</span></span>

- <span data-ttu-id="fb0ba-118">调用存储过程</span><span class="sxs-lookup"><span data-stu-id="fb0ba-118">Calling a stored procedure</span></span>

- <span data-ttu-id="fb0ba-119">更新数据库</span><span class="sxs-lookup"><span data-stu-id="fb0ba-119">Updating the database</span></span>

- <span data-ttu-id="fb0ba-120">执行 TRANSACT-SQL 代码</span><span class="sxs-lookup"><span data-stu-id="fb0ba-120">Executing Transact-SQL code</span></span>

- <span data-ttu-id="fb0ba-121">使用完整数据上下文</span><span class="sxs-lookup"><span data-stu-id="fb0ba-121">Using the full data context</span></span>

- <span data-ttu-id="fb0ba-122">删除数据</span><span class="sxs-lookup"><span data-stu-id="fb0ba-122">Deleting data</span></span>

- <span data-ttu-id="fb0ba-123">创建一个测试数据库 （如需要）</span><span class="sxs-lookup"><span data-stu-id="fb0ba-123">Create a test database (as needed)</span></span>

## <a name="preparing-a-test-database"></a><span data-ttu-id="fb0ba-124">准备测试数据库</span><span class="sxs-lookup"><span data-stu-id="fb0ba-124">Preparing a Test Database</span></span>
<span data-ttu-id="fb0ba-125">在服务器上运行 SQL Server，创建用于测试目的的数据库。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-125">On a server that's running SQL Server, create a database for testing purposes.</span></span> <span data-ttu-id="fb0ba-126">你可以使用数据库在此页底部的部分中创建脚本[创建测试数据库](#creating-a-test-database)要这样做。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-126">You can use the database create script at the bottom of this page in the section [Creating a test database](#creating-a-test-database) to do this.</span></span>


#### <a name="to-prepare-a-test-database"></a><span data-ttu-id="fb0ba-127">若要准备测试数据库</span><span class="sxs-lookup"><span data-stu-id="fb0ba-127">To prepare a test database</span></span>

<span data-ttu-id="fb0ba-128">若要运行 MyDatabase 创建脚本，请打开**视图**菜单，然后选择**SQL Server 对象资源管理器**或选择 Ctrl +\, Ctrl + S 键。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-128">To run the MyDatabase Create Script, open the **View** menu, and then choose **SQL Server Object Explorer** or choose the Ctrl+\, Ctrl+S keys.</span></span> <span data-ttu-id="fb0ba-129">在**SQL Server 对象资源管理器**窗口中，打开相应的实例的快捷菜单，选择**新查询**复制底部的此页上，该脚本，然后将脚本粘贴到编辑器。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-129">In **SQL Server Object Explorer** window, open the shortcut menu for the appropriate instance, choose **New Query**, copy the script at the bottom of this page, and then paste the script into the editor.</span></span> <span data-ttu-id="fb0ba-130">若要运行 SQL 脚本，请选择工具栏上的图标三角形符号，或选择 Ctrl + Q 键。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-130">To run the SQL script, choose the toolbar icon with the triangular symbol, or choose the Ctrl+Q keys.</span></span> <span data-ttu-id="fb0ba-131">有关详细信息**SQL Server 对象资源管理器**，请参阅[连接的数据库开发](https://msdn.microsoft.com/library/hh272679(VS.103).aspx)。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-131">For more information about **SQL Server Object Explorer**, see [Connected Database Development](https://msdn.microsoft.com/library/hh272679(VS.103).aspx).</span></span>


## <a name="creating-the-project"></a><span data-ttu-id="fb0ba-132">创建项目</span><span class="sxs-lookup"><span data-stu-id="fb0ba-132">Creating the project</span></span>
<span data-ttu-id="fb0ba-133">接下来，你创建的 F # 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-133">Next, you create an F# application project.</span></span>


#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="fb0ba-134">创建并设置项目</span><span class="sxs-lookup"><span data-stu-id="fb0ba-134">To create and set up the project</span></span>

1. <span data-ttu-id="fb0ba-135">创建新的 F # 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-135">Create a new F# Application project.</span></span>

2. <span data-ttu-id="fb0ba-136">将引用添加到[FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3)，以及`System.Data`，和`System.Data.Linq`。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-136">Add references to [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3), as well as `System.Data`, and `System.Data.Linq`.</span></span>

3. <span data-ttu-id="fb0ba-137">通过将以下代码行添加到你 F # 代码文件的顶部 Program.fs 打开相应的命名空间。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-137">Open the appropriate namespaces by adding the following lines of code to the top of your F# code file Program.fs.</span></span>

  ```fsharp
open System
open System.Data
open System.Data.Linq
open Microsoft.FSharp.Data.TypeProviders
open Microsoft.FSharp.Linq
```

4. <span data-ttu-id="fb0ba-138">与大多数 F # 程序，你可以在作为编译的程序，本演练中执行代码，或作为脚本，可以以交互方式运行它。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-138">As with most F# programs, you can execute the code in this walkthrough as a compiled program, or you can run it interactively as a script.</span></span> <span data-ttu-id="fb0ba-139">如果想要使用脚本，打开选择的项目节点的快捷菜单**添加新项**，添加 F # 脚本文件，并向该脚本每个步骤中添加代码。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-139">If you prefer to use scripts, open the shortcut menu for the project node, select **Add New Item**, add an F# script file, and add the code in each step to the script.</span></span> <span data-ttu-id="fb0ba-140">你将需要在要加载的程序集引用的文件的顶部添加以下行。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-140">You will need to add the following lines at the top of the file to load the assembly references.</span></span>

  ```fsharp
#r "System.Data.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

  <span data-ttu-id="fb0ba-141">然后，您可以选择每个代码块，如将其添加并按 Alt + Enter 以在 F # Interactive 中运行它。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-141">You can then select each block of code as you add it and press Alt+Enter to run it in F# Interactive.</span></span>

## <a name="setting-up-a-type-provider"></a><span data-ttu-id="fb0ba-142">设置类型提供程序</span><span class="sxs-lookup"><span data-stu-id="fb0ba-142">Setting up a type provider</span></span>
<span data-ttu-id="fb0ba-143">在此步骤中，为你的数据库架构创建类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-143">In this step, you create a type provider for your database schema.</span></span>


#### <a name="to-set-up-the-type-provider-from-a-direct-database-connection"></a><span data-ttu-id="fb0ba-144">若要设置类型提供程序从直接的数据库连接</span><span class="sxs-lookup"><span data-stu-id="fb0ba-144">To set up the type provider from a direct database connection</span></span>

<span data-ttu-id="fb0ba-145">有两个关键行的所需创建可用于查询 SQL 数据库使用类型提供程序的类型的代码。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-145">There are two critical lines of code that you need in order to create the types that you can use to query a SQL database using the type provider.</span></span> <span data-ttu-id="fb0ba-146">首先，您实例化类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-146">First, you instantiate the type provider.</span></span> <span data-ttu-id="fb0ba-147">若要执行此操作，创建如下所示的类型缩写`SqlDataConnection`与静态泛型参数。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-147">To do this, create what looks like a type abbreviation for a `SqlDataConnection` with a static generic parameter.</span></span> <span data-ttu-id="fb0ba-148">`SqlDataConnection`是 SQL 类型提供程序，并且不应与混淆`SqlConnection`类型，ADO.NET 编程中使用。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-148">`SqlDataConnection` is a SQL type provider, and should not be confused with `SqlConnection` type that is used in ADO.NET programming.</span></span> <span data-ttu-id="fb0ba-149">如果你有一个你想要连接到的数据库，并具有一个连接字符串，使用下面的代码来调用类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-149">If you have a database that you want to connect to, and have a connection string, use the following code to invoke the type provider.</span></span> <span data-ttu-id="fb0ba-150">替换给定的示例字符串自己连接字符串。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-150">Substitute your own connection string for the example string given.</span></span> <span data-ttu-id="fb0ba-151">例如，如果你的服务器是 MYSERVER 和数据库实例是实例、 数据库名称是 MyDatabase，并且你想要使用 Windows 身份验证访问数据库，则连接字符串是作为提供在下面的示例代码。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-151">For example, if your server is MYSERVER and the database instance is INSTANCE, the database name is MyDatabase, and you want to use Windows Authentication to access the database, then the connection string would be as given in the following example code.</span></span>

```fsharp
type dbSchema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;">
let db = dbSchema.GetDataContext()

// Enable the logging of database activity to the console.
db.DataContext.Log <- System.Console.Out
```

<span data-ttu-id="fb0ba-152">现在你拥有一种类型， `dbSchema`，这是一个父类型，包含表示数据库表的所有生成的类型。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-152">Now you have a type, `dbSchema`, which is a parent type that contains all the generated types that represent database tables.</span></span> <span data-ttu-id="fb0ba-153">您也有一个对象， `db`，它具有作为其成员数据库中的所有表。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-153">You also have an object, `db`, which has as its members all the tables in the database.</span></span> <span data-ttu-id="fb0ba-154">表名称属性，并且这些属性的类型生成的 F # 编译器。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-154">The table names are properties, and the type of these properties is generated by the F# compiler.</span></span> <span data-ttu-id="fb0ba-155">本身的类型显示为在下的嵌套类型`dbSchema.ServiceTypes`。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-155">The types themselves appear as nested types under `dbSchema.ServiceTypes`.</span></span> <span data-ttu-id="fb0ba-156">因此，为这些表的行检索任何数据将为该表生成的相应类型的实例。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-156">Therefore, any data retrieved for rows of these tables is an instance of the appropriate type that was generated for that table.</span></span> <span data-ttu-id="fb0ba-157">类型的名称是`ServiceTypes.Table1`。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-157">The name of the type is `ServiceTypes.Table1`.</span></span>

<span data-ttu-id="fb0ba-158">若要熟悉的 F # 语言如何解释为 SQL 查询的查询，查看设置行`Log`上的数据上下文的属性。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-158">To familiarize yourself with how the F# language interprets queries into SQL queries, review the line that sets the `Log` property on the data context.</span></span>

<span data-ttu-id="fb0ba-159">若要进一步浏览类型提供程序创建的类型，添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-159">To further explore the types created by the type provider, add the following code.</span></span>

```fsharp
let table1 = db.Table1
```

<span data-ttu-id="fb0ba-160">将鼠标悬停在`table1`以查看其类型。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-160">Hover over `table1` to see its type.</span></span> <span data-ttu-id="fb0ba-161">其类型是`System.Data.Linq.Table<dbSchema.ServiceTypes.Table1>`和泛型参数意味着每个行的类型生成的类型， `dbSchema.ServiceTypes.Table1`。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-161">Its type is `System.Data.Linq.Table<dbSchema.ServiceTypes.Table1>` and the generic argument implies that the type of each row is the generated type, `dbSchema.ServiceTypes.Table1`.</span></span> <span data-ttu-id="fb0ba-162">编译器在数据库中创建类似类型的每个表。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-162">The compiler creates a similar type for each table in the database.</span></span>

## <a name="querying-the-data"></a><span data-ttu-id="fb0ba-163">查询数据</span><span class="sxs-lookup"><span data-stu-id="fb0ba-163">Querying the data</span></span>
<span data-ttu-id="fb0ba-164">在此步骤中，你可以编写一个查询使用 F # 查询表达式。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-164">In this step, you write a query using F# query expressions.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="fb0ba-165">查询数据</span><span class="sxs-lookup"><span data-stu-id="fb0ba-165">To query the data</span></span>

1. <span data-ttu-id="fb0ba-166">现在在数据库中创建该表的查询。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-166">Now create a query for that table in the database.</span></span> <span data-ttu-id="fb0ba-167">添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-167">Add the following code.</span></span>

  ```fsharp
   let query1 =
     query {
       for row in db.Table1 do
       select row
     }
   query1 |> Seq.iter (fun row -> printfn "%s %d" row.Name row.TestData1)
```

  <span data-ttu-id="fb0ba-168">Word 的外观`query`指示这是一个查询表达式，生成类似的典型数据库查询的结果的集合的计算表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-168">The appearance of the word `query` indicates that this is a query expression, a type of computation expression that generates a collection of results similar of a typical database query.</span></span> <span data-ttu-id="fb0ba-169">如果你将鼠标悬停在查询，你将看到它是实例[Linq.QueryBuilder 类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.querybuilder-class-%5bfsharp%5d)，用于定义 query 计算表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-169">If you hover over query, you will see that it is an instance of [Linq.QueryBuilder Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.querybuilder-class-%5bfsharp%5d), a type that defines the query computation expression.</span></span> <span data-ttu-id="fb0ba-170">如果将鼠标悬停在`query1`，你将看到它是实例`System.Linq.IQueryable`。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-170">If you hover over `query1`, you will see that it is an instance of `System.Linq.IQueryable`.</span></span> <span data-ttu-id="fb0ba-171">顾名思义，`System.Linq.IQueryable`表示数据可能无法进行查询，不是查询的结果。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-171">As the name suggests, `System.Linq.IQueryable` represents data that may be queried, not the result of a query.</span></span> <span data-ttu-id="fb0ba-172">查询时要遵守迟缓计算中，数据库才这意味着查询何时计算查询。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-172">A query is subject to lazy evaluation, which means that the database is only queried when the query is evaluated.</span></span> <span data-ttu-id="fb0ba-173">最后一行将通过查询传递`Seq.iter`。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-173">The final line passes the query through `Seq.iter`.</span></span> <span data-ttu-id="fb0ba-174">查询可枚举，可能会像序列循环访问。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-174">Queries are enumerable and may be iterated like sequences.</span></span> <span data-ttu-id="fb0ba-175">有关详细信息，请参阅[查询表达式](../../language-reference/query-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-175">For more information, see [Query Expressions](../../language-reference/query-expressions.md).</span></span>

2. <span data-ttu-id="fb0ba-176">向查询添加查询运算符。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-176">Now add a query operator to the query.</span></span> <span data-ttu-id="fb0ba-177">有大量的查询运算符可以用来构造更复杂的查询。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-177">There are a number of query operators available that you can use to construct more complex queries.</span></span> <span data-ttu-id="fb0ba-178">此示例还显示您可以消除查询变量并改为使用管道运算符。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-178">This example also shows that you can eliminate the query variable and use a pipeline operator instead.</span></span>

  ```fsharp
   query {
     for row in db.Table1 do
     where (row.TestData1 > 2)
     select row
   } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

3. <span data-ttu-id="fb0ba-179">添加具有两个表的联接更复杂的查询。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-179">Add a more complex query with a join of two tables.</span></span>

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

4. <span data-ttu-id="fb0ba-180">在现实世界代码中，在查询中的参数通常是值或变量、 不是编译时常量。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-180">In real-world code, the parameters in your query are usually values or variables, not compile-time constants.</span></span> <span data-ttu-id="fb0ba-181">添加以下代码，将查询包装在一个函数，它接受一个参数，并随后调用该函数中的使用值 10。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-181">Add the following code that wraps a query in a function that takes a parameter, and then calls that function with the value 10.</span></span>

  ```fsharp
   let findData param =
     query {
       for row in db.Table1 do
       where (row.TestData1 = param)
       select row
     }

   findData 10 |> Seq.iter (fun row -> printfn "Found row: %d %d %f %s" row.Id row.TestData1 row.TestData2 row.Name)
```

## <a name="working-with-nullable-fields"></a><span data-ttu-id="fb0ba-182">使用可以为 null 的字段</span><span class="sxs-lookup"><span data-stu-id="fb0ba-182">Working with nullable fields</span></span>
<span data-ttu-id="fb0ba-183">在数据库中，字段通常允许 null 值。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-183">In databases, fields often allow null values.</span></span> <span data-ttu-id="fb0ba-184">在.NET 类型系统中，你不能用于允许使用 null 因为这些类型不具有 null 值作为可能的值的数据的普通的数值数据类型。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-184">In the .NET type system, you cannot use the ordinary numerical data types for data that allows nulls because those types do not have null as a possible value.</span></span> <span data-ttu-id="fb0ba-185">因此，这些值由的实例表示`System.Nullable`类型。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-185">Therefore, these values are represented by instances of `System.Nullable` type.</span></span> <span data-ttu-id="fb0ba-186">而不是访问此类字段的值直接与字段的名称，你需要添加一些附加步骤。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-186">Instead of accessing the value of such fields directly with the name of the field, you need to add some extra steps.</span></span> <span data-ttu-id="fb0ba-187">你可以使用`System.Nullable.Value`属性来访问基础值的 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-187">You can use the `System.Nullable.Value` property to access the underlying value of a nullable type.</span></span> <span data-ttu-id="fb0ba-188">`System.Nullable.Value`属性而不是具有值 null 的对象是否引发异常。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-188">The `System.Nullable.Value` property throws an exception if the object is null rather than having a value.</span></span> <span data-ttu-id="fb0ba-189">你可以使用`System.Nullable.HasValue`布尔方法以确定是否存在一个值，或使用`System.Nullable.GetValueOrDefault()`以确保在所有情况下具有一个实际值。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-189">You can use the `System.Nullable.HasValue` Boolean method to determine if a value exists, or use `System.Nullable.GetValueOrDefault()` to ensure that you have an actual value in all cases.</span></span> <span data-ttu-id="fb0ba-190">如果你使用`System.Nullable.GetValueOrDefault()`并在数据库中，没有 null 然后则替换它与一个值，如字符串类型的空字符串，0 表示整数类型或对浮点 0.0 点类型。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-190">If you use `System.Nullable.GetValueOrDefault()` and there is a null in the database, then it is replaced with a value such as an empty string for string types, 0 for integral types or 0.0 for floating point types.</span></span>

<span data-ttu-id="fb0ba-191">当你需要执行中可以为 null 值的相等性测试或比较`where`在查询中的子句，你可以使用可以为 null 的运算符中找到[Linq.NullableOperators 模块](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d)。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-191">When you need to perform equality tests or comparisons on nullable values in a `where` clause in a query, you can use the nullable operators found in the [Linq.NullableOperators Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d).</span></span> <span data-ttu-id="fb0ba-192">这些是正则比较运算符一样`=`， `>`， `<=`，依此类推，只不过将显示一个问号左侧或右侧的运算符的可以为 null 的值是。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-192">These are like the regular comparison operators `=`, `>`, `<=`, and so on, except that a question mark appears on the left or right of the operator where the nullable values are.</span></span> <span data-ttu-id="fb0ba-193">例如，运算符`>?`大于-比右侧可以为 null 值的运算符。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-193">For example, the operator `>?` is a greater-than operator with a nullable value on the right.</span></span> <span data-ttu-id="fb0ba-194">这些运算符的工作的方式是，如果任意一侧的表达式为 null，表达式计算结果为`false`。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-194">The way these operators work is that if either side of the expression is null, the expression evaluates to `false`.</span></span> <span data-ttu-id="fb0ba-195">在`where`子句，这通常意味着，不选中并不返回查询结果中包含 null 字段的行。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-195">In a `where` clause, this generally means that the rows that contain null fields are not selected and not returned in the query results.</span></span>


#### <a name="to-work-with-nullable-fields"></a><span data-ttu-id="fb0ba-196">可以使用可以为 null 的字段</span><span class="sxs-lookup"><span data-stu-id="fb0ba-196">To work with nullable fields</span></span>

<span data-ttu-id="fb0ba-197">下面的代码演示使用可以为 null 值;假定**TestData1**是一个整数字段，允许空值。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-197">The following code shows working with nullable values; assume that **TestData1** is an integer field that allows nulls.</span></span>

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

## <a name="calling-a-stored-procedure"></a><span data-ttu-id="fb0ba-198">调用存储过程</span><span class="sxs-lookup"><span data-stu-id="fb0ba-198">Calling a stored procedure</span></span>
<span data-ttu-id="fb0ba-199">在数据库上的任何存储的过程可以从 F # 中调用。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-199">Any stored procedures on the database can be called from F#.</span></span> <span data-ttu-id="fb0ba-200">必须设置静态参数`StoredProcedures`到`true`中的类型提供程序实例化。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-200">You must set the static parameter `StoredProcedures` to `true` in the type provider instantiation.</span></span> <span data-ttu-id="fb0ba-201">类型提供程序`SqlDataConnection`包含可用于配置生成的类型的若干静态方法。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-201">The type provider `SqlDataConnection` contains several static methods that you can use to configure the types that are generated.</span></span> <span data-ttu-id="fb0ba-202">有关这些的完整说明，请参阅[SqlDataConnection 类型提供程序](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d)。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-202">For a complete description of these, see [SqlDataConnection Type Provider](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d).</span></span> <span data-ttu-id="fb0ba-203">为每个存储过程生成的数据上下文类型上的方法。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-203">A method on the data context type is generated for each stored procedure.</span></span>


#### <a name="to-call-a-stored-procedure"></a><span data-ttu-id="fb0ba-204">调用存储过程</span><span class="sxs-lookup"><span data-stu-id="fb0ba-204">To call a stored procedure</span></span>

<span data-ttu-id="fb0ba-205">如果存储的过程采用可以为 null 的参数，请将传递相应`System.Nullable`值。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-205">If the stored procedures takes parameters that are nullable, you need to pass an appropriate `System.Nullable` value.</span></span> <span data-ttu-id="fb0ba-206">返回一个标量或表的存储的过程方法的返回值是`System.Data.Linq.ISingleResult`，其中包含使你能够访问返回的数据的属性。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-206">The return value of a stored procedure method that returns a scalar or a table is `System.Data.Linq.ISingleResult`, which contains properties that enable you to access the returned data.</span></span> <span data-ttu-id="fb0ba-207">类型参数`System.Data.Linq.ISingleResult`取决于特定过程和也是它在类型提供程序生成的类型。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-207">The type argument for `System.Data.Linq.ISingleResult` depends on the specific procedure and is also one of the types that the type provider generates.</span></span> <span data-ttu-id="fb0ba-208">存储过程名为`Procedure1`，该类型是`Procedure1Result`。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-208">For a stored procedure named `Procedure1`, the type is `Procedure1Result`.</span></span> <span data-ttu-id="fb0ba-209">类型`Procedure1Result`包含名称的列中返回的表，或者，对于返回标量值的存储过程，它表示的返回值。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-209">The type `Procedure1Result` contains the names of the columns in a returned table, or, for a stored procedure that returns a scalar value, it represents the return value.</span></span>

<span data-ttu-id="fb0ba-210">下面的代码假定有一个过程`Procedure1`采用两个可以为 null 整数作为参数的数据库上运行该查询将返回一个名为列`TestData1`，并返回一个整数。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-210">The following code assumes that there is a procedure `Procedure1` on the database that takes two nullable integers as parameters, runs a query that returns a column named `TestData1`, and returns an integer.</span></span>

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

## <a name="updating-the-database"></a><span data-ttu-id="fb0ba-211">更新数据库</span><span class="sxs-lookup"><span data-stu-id="fb0ba-211">Updating the database</span></span>
<span data-ttu-id="fb0ba-212">LINQ DataContext 类型包含更加轻松地在生成的类型以完全类型化形式中执行事务处理的数据库更新的方法。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-212">The LINQ DataContext type contains methods that make it easier to perform transacted database updates in a fully typed fashion with the generated types.</span></span>


#### <a name="to-update-the-database"></a><span data-ttu-id="fb0ba-213">更新数据库</span><span class="sxs-lookup"><span data-stu-id="fb0ba-213">To update the database</span></span>

1. <span data-ttu-id="fb0ba-214">在下面的代码中，多个行添加到数据库中。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-214">In the following code, several rows are added to the database.</span></span> <span data-ttu-id="fb0ba-215">如果你仅在添加行，则可以使用`System.Data.Linq.Table.InsertOnSubmit()`来指定要添加的新行。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-215">If you are only adding a row, you can use `System.Data.Linq.Table.InsertOnSubmit()` to specify the new row to add.</span></span> <span data-ttu-id="fb0ba-216">如果你在插入多行，应将其放到一个集合并调用`System.Data.Linq.Table.InsertAllOnSubmit(System.Collections.Generic.IEnumerable)`。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-216">If you are inserting multiple rows, you should put them into a collection and call `System.Data.Linq.Table.InsertAllOnSubmit(System.Collections.Generic.IEnumerable)`.</span></span> <span data-ttu-id="fb0ba-217">在调用这些方法之一时，不立即更改数据库。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-217">When you call either of these methods, the database is not immediately changed.</span></span> <span data-ttu-id="fb0ba-218">必须调用`System.Data.Linq.DataContext.SubmitChanges`实际提交所做的更改。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-218">You must call `System.Data.Linq.DataContext.SubmitChanges` to actually commit the changes.</span></span> <span data-ttu-id="fb0ba-219">默认情况下，在你之前执行的所有调用`System.Data.Linq.DataContext.SubmitChanges`是隐式在同一事务的一部分。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-219">By default, everything that you do before you call `System.Data.Linq.DataContext.SubmitChanges` is implicitly part of the same transaction.</span></span>

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

2. <span data-ttu-id="fb0ba-220">现在来清理行调用删除操作。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-220">Now clean up the rows by calling a delete operation.</span></span>

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

## <a name="executing-transact-sql-code"></a><span data-ttu-id="fb0ba-221">执行 TRANSACT-SQL 代码</span><span class="sxs-lookup"><span data-stu-id="fb0ba-221">Executing Transact-SQL code</span></span>
<span data-ttu-id="fb0ba-222">此外可以直接通过使用指定 TRANSACT-SQL`System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])`方法`DataContext`类。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-222">You can also specify Transact-SQL directly by using the `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` method on the `DataContext` class.</span></span>


#### <a name="to-execute-custom-sql-commands"></a><span data-ttu-id="fb0ba-223">执行自定义 SQL 命令</span><span class="sxs-lookup"><span data-stu-id="fb0ba-223">To execute custom SQL commands</span></span>

<span data-ttu-id="fb0ba-224">下面的代码演示如何发送 SQL 命令以将一个记录插入表以及从表中删除一条记录。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-224">The following code shows how to send SQL commands to insert a record into a table and also to delete a record from a table.</span></span>

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

## <a name="using-the-full-data-context"></a><span data-ttu-id="fb0ba-225">使用完整数据上下文</span><span class="sxs-lookup"><span data-stu-id="fb0ba-225">Using the full data context</span></span>
<span data-ttu-id="fb0ba-226">在前面的示例中，`GetDataContext`方法用于获取所谓*简化的数据上下文*为数据库架构。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-226">In the previous examples, the `GetDataContext` method was used to get what is called the *simplified data context* for the database schema.</span></span> <span data-ttu-id="fb0ba-227">简化的数据上下文是更轻松地使用当你在构造查询，因为没有尽可能多的成员。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-227">The simplified data context is easier to use when you are constructing queries because there are not as many members available.</span></span> <span data-ttu-id="fb0ba-228">因此，当您浏览在 IntelliSense 中的属性，你可以专注于数据库结构，如表和存储的过程。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-228">Therefore, when you browse the properties in IntelliSense, you can focus on the database structure, such as the tables and stored procedures.</span></span> <span data-ttu-id="fb0ba-229">但是，没有限制你可以使用简化的数据上下文做什么。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-229">However, there is a limit to what you can do with the simplified data context.</span></span> <span data-ttu-id="fb0ba-230">提供的功能来执行其他操作的完整数据上下文。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-230">A full data context that provides the ability to perform other actions.</span></span> <span data-ttu-id="fb0ba-231">也可用它位于`ServiceTypes`和具有名称的*DataContext*如果你提供的静态参数。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-231">is also available This is located in the `ServiceTypes` and has the name of the *DataContext* static parameter if you provided it.</span></span> <span data-ttu-id="fb0ba-232">如果未提供，数据上下文类型的名称为你生成通过 SqlMetal.exe 根据其他输入。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-232">If you did not provide it, the name of the data context type is generated for you by SqlMetal.exe based on the other input.</span></span> <span data-ttu-id="fb0ba-233">完整数据上下文继承自`System.Data.Linq.DataContext`，并公开其基本类，其中包括对 ADO.NET 数据类型的引用，例如成员`Connection`对象、 等方法`System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])`和`System.Data.Linq.DataContext.ExecuteQuery(System.String,System.Object[])`可用于在 SQL 中，编写查询和另一种方式来显式使用事务。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-233">The full data context inherits from `System.Data.Linq.DataContext` and exposes the members of its base class, including references to ADO.NET data types such as the `Connection` object, methods such as `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` and `System.Data.Linq.DataContext.ExecuteQuery(System.String,System.Object[])` that you can use to write queries in SQL, and also a means to work with transactions explicitly.</span></span>


#### <a name="to-use-the-full-data-context"></a><span data-ttu-id="fb0ba-234">若要使用完整数据上下文</span><span class="sxs-lookup"><span data-stu-id="fb0ba-234">To use the full data context</span></span>

<span data-ttu-id="fb0ba-235">下面的代码演示获取完整数据上下文对象，并使用它来直接对数据库执行命令。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-235">The following code demonstrates getting a full data context object and using it to execute commands directly against the database.</span></span> <span data-ttu-id="fb0ba-236">在这种情况下，两个命令将作为同一事务的一部分执行。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-236">In this case, two commands are executed as part of the same transaction.</span></span>

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

## <a name="deleting-data"></a><span data-ttu-id="fb0ba-237">删除数据</span><span class="sxs-lookup"><span data-stu-id="fb0ba-237">Deleting data</span></span>
<span data-ttu-id="fb0ba-238">此步骤演示了如何删除数据表中的行。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-238">This step shows you how to delete rows from a data table.</span></span>


#### <a name="to-delete-rows-from-the-database"></a><span data-ttu-id="fb0ba-239">若要从数据库中删除行</span><span class="sxs-lookup"><span data-stu-id="fb0ba-239">To delete rows from the database</span></span>

<span data-ttu-id="fb0ba-240">现在，清除任何通过编写指定的表中的实例删除行的函数添加行`System.Data.Linq.Table`类。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-240">Now, clean up any added rows by writing a function that deletes rows from a specified table, an instance of the `System.Data.Linq.Table` class.</span></span> <span data-ttu-id="fb0ba-241">编写查询以查找所有你想要删除的行，然后通过管道传递到查询的结果`deleteRows`函数。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-241">Then write a query to find all the rows that you want to delete, and pipe the results of the query into the `deleteRows` function.</span></span> <span data-ttu-id="fb0ba-242">此代码利用提供的函数自变量的部分应用的功能。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-242">This code takes advantage of the ability to provide partial application of function arguments.</span></span>

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

## <a name="creating-a-test-database"></a><span data-ttu-id="fb0ba-243">创建一个测试数据库</span><span class="sxs-lookup"><span data-stu-id="fb0ba-243">Creating a test database</span></span>
<span data-ttu-id="fb0ba-244">本部分演示如何将测试数据库设置为在此演练中使用。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-244">This section shows you how to set up the test database to use in this walkthrough.</span></span>

<span data-ttu-id="fb0ba-245">请注意，是否你更改该数据库，以某种方式，你将需要重置类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-245">Note that if you alter the database in some way, you will have to reset the type provider.</span></span> <span data-ttu-id="fb0ba-246">若要重置类型提供程序，请重新生成或清理包含类型提供程序的项目。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-246">To reset the type provider, rebuild or clean the project that contains the type provider.</span></span>


#### <a name="to-create-the-test-database"></a><span data-ttu-id="fb0ba-247">若要创建测试数据库</span><span class="sxs-lookup"><span data-stu-id="fb0ba-247">To create the test database</span></span>

1. <span data-ttu-id="fb0ba-248">在**服务器资源管理器**，打开快捷菜单**数据连接**节点，然后选择**添加连接**。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-248">In **Server Explorer**, open the shortcut menu for the **Data Connections** node, and choose **Add Connection**.</span></span> <span data-ttu-id="fb0ba-249">**添加连接**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-249">The **Add Connection** dialog box appears.</span></span>

2. <span data-ttu-id="fb0ba-250">在**服务器名称**框中，指定具有管理访问权，SQL Server 实例的名称或如果你没有访问服务器，指定 (localdb \ v11.0)。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-250">In the **Server name** box, specify the name of an instance of SQL Server that you have administrative access to, or if you do not have access to a server, specify (localdb\v11.0).</span></span> <span data-ttu-id="fb0ba-251">SQL Express LocalDB 提供了轻型数据库服务器进行开发和测试您的计算机上。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-251">SQL Express LocalDB provides a lightweight database server for development and testing on your machine.</span></span> <span data-ttu-id="fb0ba-252">在中创建一个新的节点**服务器资源管理器**下**数据连接**。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-252">A new node is created in **Server Explorer** under **Data Connections**.</span></span> <span data-ttu-id="fb0ba-253">有关 LocalDB 的详细信息，请参阅[演练： 在 Visual Studio 中创建本地数据库文件](https://msdn.microsoft.com/library/ms233763.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-253">For more information about LocalDB, see [Walkthrough: Creating a Local Database File in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span></span>

3. <span data-ttu-id="fb0ba-254">打开新连接节点的快捷菜单，然后选择**新查询**。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-254">Open the shortcut menu for the new connection node, and select **New Query**.</span></span>

4. <span data-ttu-id="fb0ba-255">复制以下 SQL 脚本，将其粘贴到查询编辑器中，，然后选择**执行**按钮在工具栏上，或选择 Ctrl + Shift + E 键。</span><span class="sxs-lookup"><span data-stu-id="fb0ba-255">Copy the following SQL script, paste it into the query editor, and then choose the **Execute** button on the toolbar or choose the Ctrl+Shift+E keys.</span></span>

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


## <a name="see-also"></a><span data-ttu-id="fb0ba-256">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb0ba-256">See Also</span></span>
[<span data-ttu-id="fb0ba-257">类型提供程序</span><span class="sxs-lookup"><span data-stu-id="fb0ba-257">Type Providers</span></span>](index.md)

[<span data-ttu-id="fb0ba-258">SqlDataConnection 类型提供程序</span><span class="sxs-lookup"><span data-stu-id="fb0ba-258">SqlDataConnection Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d)

[<span data-ttu-id="fb0ba-259">演练： 根据 DBML 文件生成 F # 类型</span><span class="sxs-lookup"><span data-stu-id="fb0ba-259">Walkthrough: Generating F# Types from a DBML File</span></span>](generating-fsharp-types-from-dbml.md)

[<span data-ttu-id="fb0ba-260">查询表达式</span><span class="sxs-lookup"><span data-stu-id="fb0ba-260">Query Expressions</span></span>](../../language-reference/query-expressions.md)

[<span data-ttu-id="fb0ba-261">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="fb0ba-261">LINQ to SQL</span></span>](../../../../docs/framework/data/adonet/sql/linq/index.md)

[<span data-ttu-id="fb0ba-262">SqlMetal.exe &#40;代码生成工具 &#41;</span><span class="sxs-lookup"><span data-stu-id="fb0ba-262">SqlMetal.exe &#40;Code Generation Tool&#41;</span></span>](https://msdn.microsoft.com/library/bb386987)
