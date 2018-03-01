---
title: "演练：根据 DBML 文件生成 F# 类型 (F#)"
description: "了解如何从 F # 3.0 中的数据库创建数据的 F # 类型，如果必须在.dbml 文件中编码的架构信息。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 6fbb6ccc-248f-4226-95e9-f6f99541dbe4
ms.openlocfilehash: 3cd8df9becac0d1a8842eb22e2f772eee6307acf
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-generating-f-types-from-a-dbml-file"></a><span data-ttu-id="d75c9-104">演练：根据 DBML 文件生成 F# 类型 </span><span class="sxs-lookup"><span data-stu-id="d75c9-104">Walkthrough: Generating F# Types from a DBML File</span></span>

> [!NOTE]
<span data-ttu-id="d75c9-105">此指南专门针对 F # 3.0 编写，并将更新。</span><span class="sxs-lookup"><span data-stu-id="d75c9-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="d75c9-106">请参阅 [FSharp.Data](https://fsharp.github.io/FSharp.Data/) 了解最新的跨平台类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="d75c9-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="d75c9-107">API 参考链接将转到 MSDN。</span><span class="sxs-lookup"><span data-stu-id="d75c9-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="d75c9-108">Docs.microsoft.com API 参考尚未完成。</span><span class="sxs-lookup"><span data-stu-id="d75c9-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="d75c9-109">此针对 F # 3.0 的演练介绍如何从数据库中创建数据的类型，如果必须在.dbml 文件中编码的架构信息。</span><span class="sxs-lookup"><span data-stu-id="d75c9-109">This walkthrough for F# 3.0 describes how to create types for data from a database when you have schema information encoded in a .dbml file.</span></span> <span data-ttu-id="d75c9-110">LINQ to SQL 使用这种文件格式来表示数据库架构。</span><span class="sxs-lookup"><span data-stu-id="d75c9-110">LINQ to SQL uses this file format to represent database schema.</span></span> <span data-ttu-id="d75c9-111">在 Visual Studio 中，你可以使用对象关系 (O/R) 的设计器生成 LINQ to SQL 架构文件。</span><span class="sxs-lookup"><span data-stu-id="d75c9-111">You can generate a LINQ to SQL schema file in Visual Studio by using the Object Relational (O/R) Designer.</span></span> <span data-ttu-id="d75c9-112">有关详细信息，请参阅[O/R 设计器概述](https://msdn.microsoft.com/library/bb384511.aspx)和[LINQ to SQL 中的代码生成](../../../../docs/framework/data/adonet/sql/linq/index.md)。</span><span class="sxs-lookup"><span data-stu-id="d75c9-112">For more information, see [O/R Designer Overview](https://msdn.microsoft.com/library/bb384511.aspx) and [Code Generation in LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>

<span data-ttu-id="d75c9-113">数据库标记语言 (DBML) 类型提供程序允许你编写使用基于数据库架构，而无需在编译时指定静态连接字符串的类型的代码。</span><span class="sxs-lookup"><span data-stu-id="d75c9-113">The Database Markup Language (DBML) type provider allows you to write code that uses types based on a database schema without requiring you to specify a static connection string at compile time.</span></span> <span data-ttu-id="d75c9-114">这可能是需要考虑到最终应用程序将使用不同的数据库、 不同的凭据或与用于开发应用程序的不同的连接字符串的可能性的情况下很有用。</span><span class="sxs-lookup"><span data-stu-id="d75c9-114">That can be useful if you need to allow for the possibility that the final application will use a different database, different credentials, or a different connection string than the one you use to develop the application.</span></span> <span data-ttu-id="d75c9-115">如果你具有可以在编译时使用的直接数据库连接，这是同一个数据库和你最终将在你生成的应用程序中使用的凭据，你还可以使用 SQLDataConnection 类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="d75c9-115">If you have a direct database connection that you can use at compile time and this is the same database and credentials that you will eventually use in your built application, you can also use the SQLDataConnection type provider.</span></span> <span data-ttu-id="d75c9-116">有关详细信息，请参阅[演练： 访问 SQL 数据库使用类型提供程序](accessing-a-sql-database.md)。</span><span class="sxs-lookup"><span data-stu-id="d75c9-116">For more information, see [Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md).</span></span>

<span data-ttu-id="d75c9-117">本演练阐释了以下任务。</span><span class="sxs-lookup"><span data-stu-id="d75c9-117">This walkthrough illustrates the following tasks.</span></span> <span data-ttu-id="d75c9-118">它们应按才能成功完成演练以下顺序完成：</span><span class="sxs-lookup"><span data-stu-id="d75c9-118">They should be completed in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="d75c9-119">创建一个.dbml 文件</span><span class="sxs-lookup"><span data-stu-id="d75c9-119">Creating a .dbml file</span></span>
<br />

- <span data-ttu-id="d75c9-120">创建和设置 F # 项目</span><span class="sxs-lookup"><span data-stu-id="d75c9-120">Creating and setting up an F# project</span></span>
<br />

- <span data-ttu-id="d75c9-121">配置类型提供程序和生成类型</span><span class="sxs-lookup"><span data-stu-id="d75c9-121">Configuring the type provider and generating the types</span></span>
<br />

- <span data-ttu-id="d75c9-122">查询数据库</span><span class="sxs-lookup"><span data-stu-id="d75c9-122">Querying the database</span></span>
<br />


## <a name="prerequisites"></a><span data-ttu-id="d75c9-123">系统必备</span><span class="sxs-lookup"><span data-stu-id="d75c9-123">Prerequisites</span></span>

## <a name="creating-a-dbml-file"></a><span data-ttu-id="d75c9-124">创建一个.dbml 文件</span><span class="sxs-lookup"><span data-stu-id="d75c9-124">Creating a .dbml file</span></span>
<span data-ttu-id="d75c9-125">如果你不具有数据库上测试，创建一个在底部的说明[演练： 访问 SQL 数据库使用类型提供程序](accessing-a-sql-database.md)。</span><span class="sxs-lookup"><span data-stu-id="d75c9-125">If you do not have a database to test on, create one by following the instructions at the bottom of [Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md).</span></span> <span data-ttu-id="d75c9-126">如果你按照这些说明操作，将创建名为 MyDatabase 包含几个简单的表和 SQL Server 上的存储的过程的数据库。</span><span class="sxs-lookup"><span data-stu-id="d75c9-126">If you follow these instructions, you will create a database called MyDatabase that contains a few simple tables and stored procedures on your SQL Server.</span></span>

<span data-ttu-id="d75c9-127">如果你已有一个.dbml 文件，则可以跳到部分，**创建并设置 F # 项目**。</span><span class="sxs-lookup"><span data-stu-id="d75c9-127">If you already have a .dbml file, you can skip to the section, **Create and Set Up an F# Project**.</span></span> <span data-ttu-id="d75c9-128">否则为你可以创建给出的现有 SQL 数据库的.dbml 文件，并通过使用命令行工具 SqlMetal.exe。</span><span class="sxs-lookup"><span data-stu-id="d75c9-128">Otherwise, you can create a .dbml file given an existing SQL database and by using the command-line tool SqlMetal.exe.</span></span>


#### <a name="to-create-a-dbml-file-by-using-sqlmetalexe"></a><span data-ttu-id="d75c9-129">若要使用 SqlMetal.exe 创建.dbml 文件</span><span class="sxs-lookup"><span data-stu-id="d75c9-129">To create a .dbml file by using SqlMetal.exe</span></span>

1. <span data-ttu-id="d75c9-130">打开**开发人员命令提示**。</span><span class="sxs-lookup"><span data-stu-id="d75c9-130">Open a **Developer Command Prompt**.</span></span>
<br />

2. <span data-ttu-id="d75c9-131">确保通过输入有权访问 SqlMetal.exe`SqlMetal.exe /?`在命令提示符。</span><span class="sxs-lookup"><span data-stu-id="d75c9-131">Ensure that you have access to SqlMetal.exe by entering `SqlMetal.exe /?` at the command prompt.</span></span> <span data-ttu-id="d75c9-132">SqlMetal.exe 通常安装在**Microsoft Sdk**文件夹中的**Program Files**或**Program Files (x86)**。</span><span class="sxs-lookup"><span data-stu-id="d75c9-132">SqlMetal.exe is typically installed under the **Microsoft SDKs** folder in **Program Files** or **Program Files (x86)**.</span></span>
<br />

3. <span data-ttu-id="d75c9-133">使用以下命令行选项运行 SqlMetal.exe。</span><span class="sxs-lookup"><span data-stu-id="d75c9-133">Run SqlMetal.exe with the following command-line options.</span></span> <span data-ttu-id="d75c9-134">替换代替了正确的路径`c:\destpath`若要创建.dbml 文件中，并将数据库服务器的相应值插入，实例名称和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="d75c9-134">Substitute an appropriate path in place of `c:\destpath` to create the .dbml file, and insert appropriate values for the database server, instance name, and database name.</span></span>
<br />

```
  SqlMetal.exe /sprocs /dbml:C:\destpath\MyDatabase.dbml /server:SERVER\INSTANCE /database:MyDatabase
```

>[!NOTE]
<span data-ttu-id="d75c9-135">如果 SqlMetal.exe 具有创建文件由于权限问题造成的问题，将当前目录更改为具有写访问权限的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d75c9-135">If SqlMetal.exe has trouble creating the file due to permissions issues, change the current directory to a folder that you have write access to.</span></span>


4. <span data-ttu-id="d75c9-136">你还可以查看其他可用命令行选项。</span><span class="sxs-lookup"><span data-stu-id="d75c9-136">You can also look at the other available command-line options.</span></span> <span data-ttu-id="d75c9-137">例如，有如果你想视图和包含在生成的类型中的 SQL 函数可以使用的选项。</span><span class="sxs-lookup"><span data-stu-id="d75c9-137">For example, there are options you can use if you want views and SQL functions included in the generated types.</span></span> <span data-ttu-id="d75c9-138">有关详细信息，请参阅[SqlMetal.exe &#40;代码生成工具 &#41;](https://msdn.microsoft.com/library/bb386987).</span><span class="sxs-lookup"><span data-stu-id="d75c9-138">For more information, see [SqlMetal.exe &#40;Code Generation Tool&#41;](https://msdn.microsoft.com/library/bb386987).</span></span>
<br />


## <a name="creating-and-setting-up-an-f-project"></a><span data-ttu-id="d75c9-139">创建和设置 F # 项目</span><span class="sxs-lookup"><span data-stu-id="d75c9-139">Creating and setting up an F# project</span></span>
<span data-ttu-id="d75c9-140">在此步骤中，你可以创建项目并添加相应的引用以使用 DBML 类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="d75c9-140">In this step, you create a project and add appropriate references to use the DBML type provider.</span></span>


#### <a name="to-create-and-set-up-an-f-project"></a><span data-ttu-id="d75c9-141">创建并设置 F# 项目</span><span class="sxs-lookup"><span data-stu-id="d75c9-141">To create and set up an F# project</span></span>

1. <span data-ttu-id="d75c9-142">将新的 F # 控制台应用程序项目添加到你的解决方案。</span><span class="sxs-lookup"><span data-stu-id="d75c9-142">Add a new F# Console Application project to your solution.</span></span>
<br />

2. <span data-ttu-id="d75c9-143">在**解决方案资源管理器**，打开快捷菜单**引用**，然后选择**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="d75c9-143">In **Solution Explorer**, open the shortcut menu for **References**, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="d75c9-144">在**程序集**区域中，选择**Framework**节点，然后在可用的程序集列表中，选择**System.Data**和**System.Data.Linq**程序集。</span><span class="sxs-lookup"><span data-stu-id="d75c9-144">In the **Assemblies** area, choose the **Framework** node, and then, in the list of available assemblies, choose the **System.Data** and **System.Data.Linq** assemblies.</span></span>
<br />

4. <span data-ttu-id="d75c9-145">在**程序集**区域中，选择**扩展**，然后在可用的程序集列表中，选择**FSharp.Data.TypeProviders**。</span><span class="sxs-lookup"><span data-stu-id="d75c9-145">In the **Assemblies** area, choose **Extensions**, and then, in the list of available assemblies, choose **FSharp.Data.TypeProviders**.</span></span>
<br />

5. <span data-ttu-id="d75c9-146">选择**确定**按钮将对这些程序集的引用添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="d75c9-146">Choose the **OK** button to add references to these assemblies to your project.</span></span>
<br />

6. <span data-ttu-id="d75c9-147">（可选）。</span><span class="sxs-lookup"><span data-stu-id="d75c9-147">(Optional).</span></span> <span data-ttu-id="d75c9-148">复制你在前一步骤中创建的.dbml 文件并在为你的项目的主文件夹中粘贴文件。</span><span class="sxs-lookup"><span data-stu-id="d75c9-148">Copy the .dbml file that you created in the previous step, and paste the file in the main folder for your project.</span></span> <span data-ttu-id="d75c9-149">此文件夹包含的项目文件 (.fsproj) 和代码文件。</span><span class="sxs-lookup"><span data-stu-id="d75c9-149">This folder contains the project file (.fsproj) and code files.</span></span> <span data-ttu-id="d75c9-150">在菜单栏上，选择**项目**，**添加现有项**，然后指定要将其添加到你的项目的.dbml 文件。</span><span class="sxs-lookup"><span data-stu-id="d75c9-150">On the menu bar, choose **Project**, **Add Existing Item**, and then specify the .dbml file to add it to your project.</span></span> <span data-ttu-id="d75c9-151">如果你完成这些步骤，你可以忽略下一步 ResolutionFolder 静态参数。</span><span class="sxs-lookup"><span data-stu-id="d75c9-151">If you complete these steps, you can omit the ResolutionFolder static parameter in the next step.</span></span>
<br />

## <a name="configuring-the-type-provider"></a><span data-ttu-id="d75c9-152">配置类型提供程序</span><span class="sxs-lookup"><span data-stu-id="d75c9-152">Configuring the type provider</span></span>
<span data-ttu-id="d75c9-153">在本部分中，你将创建类型提供程序，并从.dbml 文件中描述的架构生成类型。</span><span class="sxs-lookup"><span data-stu-id="d75c9-153">In this section, you create a type provider and generate types from the schema that’s described in the .dbml file.</span></span>


#### <a name="to-configure-the-type-provider-and-generate-the-types"></a><span data-ttu-id="d75c9-154">若要配置类型提供程序和生成类型</span><span class="sxs-lookup"><span data-stu-id="d75c9-154">To configure the type provider and generate the types</span></span>

- <span data-ttu-id="d75c9-155">添加代码，打开该**TypeProviders**命名空间和实例化的.dbml 文件，你想要使用的类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="d75c9-155">Add code that opens the **TypeProviders** namespace and instantiates the type provider for the .dbml file that you want to use.</span></span> <span data-ttu-id="d75c9-156">如果将.dbml 文件添加到你的项目中时，可以省略 ResolutionFolder 静态参数。</span><span class="sxs-lookup"><span data-stu-id="d75c9-156">If you added the .dbml file to your project, you can omit the ResolutionFolder static parameter.</span></span>
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ResolutionFolder = @"<path-to-folder-that-contains-.dbml-file>">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let dataContext = new dbml.Mydatabase(connectionString)
```

<span data-ttu-id="d75c9-157">DataContext 类型提供对所有生成的类型的访问，并继承自`System.Data.Linq.DataContext`。</span><span class="sxs-lookup"><span data-stu-id="d75c9-157">The DataContext type provides access to all the generated types and inherits from `System.Data.Linq.DataContext`.</span></span> <span data-ttu-id="d75c9-158">DbmlFile 类型提供程序具有各种可以设置的静态参数。</span><span class="sxs-lookup"><span data-stu-id="d75c9-158">The DbmlFile type provider has various static parameters that you can set.</span></span> <span data-ttu-id="d75c9-159">例如，可以通过指定使用 DataContext 类型的不同名称`DataContext=MyDataContext`。</span><span class="sxs-lookup"><span data-stu-id="d75c9-159">For example, you can use a different name for the DataContext type by specifying `DataContext=MyDataContext`.</span></span> <span data-ttu-id="d75c9-160">在这种情况下，你的代码类似于下面的示例：</span><span class="sxs-lookup"><span data-stu-id="d75c9-160">In that case, your code resembles the following example:</span></span>
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ContextTypeName = "MyDataContext">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let db = new dbml.MyDataContext(connectionString)
```

## <a name="querying-the-database"></a><span data-ttu-id="d75c9-161">查询数据库</span><span class="sxs-lookup"><span data-stu-id="d75c9-161">Querying the database</span></span>
<span data-ttu-id="d75c9-162">在本部分中，使用 F # 查询表达式查询数据库。</span><span class="sxs-lookup"><span data-stu-id="d75c9-162">In this section, you use F# query expressions to query the database.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="d75c9-163">查询数据</span><span class="sxs-lookup"><span data-stu-id="d75c9-163">To query the data</span></span>

- <span data-ttu-id="d75c9-164">添加代码以查询数据库。</span><span class="sxs-lookup"><span data-stu-id="d75c9-164">Add code to query the database.</span></span>
<br />

```fsharp
  query {
    for row in db.Table1 do
    where (row.TestData1 > 2)
    select row
  } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

## <a name="next-steps"></a><span data-ttu-id="d75c9-165">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d75c9-165">Next Steps</span></span>
<span data-ttu-id="d75c9-166">你可以继续使用其他查询表达式，或从数据上下文获取数据库连接并执行正常的 ADO.NET 数据操作。</span><span class="sxs-lookup"><span data-stu-id="d75c9-166">You can proceed to use other query expressions, or get a database connection from the data context and perform normal ADO.NET data operations.</span></span> <span data-ttu-id="d75c9-167">有关其他步骤，请参阅部分后"查询数据"中[演练： 访问 SQL 数据库使用类型提供程序](accessing-a-sql-database.md)。</span><span class="sxs-lookup"><span data-stu-id="d75c9-167">For additional steps, see the sections after "Query the Data" in [Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="d75c9-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="d75c9-168">See Also</span></span>
[<span data-ttu-id="d75c9-169">DbmlFile 类型提供程序</span><span class="sxs-lookup"><span data-stu-id="d75c9-169">DbmlFile Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/dbmlfile-type-provider-%5bfsharp%5d)

[<span data-ttu-id="d75c9-170">类型提供程序</span><span class="sxs-lookup"><span data-stu-id="d75c9-170">Type Providers</span></span>](index.md)

[<span data-ttu-id="d75c9-171">演练：使用类型提供程序访问 SQL 数据库</span><span class="sxs-lookup"><span data-stu-id="d75c9-171">Walkthrough: Accessing a SQL Database by Using Type Providers</span></span>](accessing-a-sql-database.md)

[<span data-ttu-id="d75c9-172">SqlMetal.exe &#40;代码生成工具 &#41;</span><span class="sxs-lookup"><span data-stu-id="d75c9-172">SqlMetal.exe &#40;Code Generation Tool&#41;</span></span>](https://msdn.microsoft.com/library/bb386987)

[<span data-ttu-id="d75c9-173">查询表达式</span><span class="sxs-lookup"><span data-stu-id="d75c9-173">Query Expressions</span></span>](../../language-reference/query-expressions.md)
