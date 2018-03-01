---
title: "演练：根据 EDMX 架构文件生成 F# 类型 (F#)"
description: "了解如何创建 F # 表示在 F # 3.0 中，为.edmx 文件中指定了的架构由实体数据模型 (EDM) 的数据类型。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 81adb2eb-625f-4ad8-aeaa-8f672a6d79a2
ms.openlocfilehash: 901457dce358f768b4f4c980703e09f6c744918e
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-generating-f-types-from-an-edmx-schema-file"></a><span data-ttu-id="98238-104">演练：根据 EDMX 架构文件生成 F# 类型</span><span class="sxs-lookup"><span data-stu-id="98238-104">Walkthrough: Generating F# Types from an EDMX Schema File</span></span>

> [!NOTE]
<span data-ttu-id="98238-105">此指南专门针对 F # 3.0 编写，并将更新。</span><span class="sxs-lookup"><span data-stu-id="98238-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="98238-106">请参阅 [FSharp.Data](https://fsharp.github.io/FSharp.Data/) 了解最新的跨平台类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="98238-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="98238-107">API 参考链接将转到 MSDN。</span><span class="sxs-lookup"><span data-stu-id="98238-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="98238-108">Docs.microsoft.com API 参考尚未完成。</span><span class="sxs-lookup"><span data-stu-id="98238-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="98238-109">此针对 F# 3.0 的演练演示如何创建由实体数据模型 (EDM)（在 .edmx 文件中指定的架构）表示的数据的类型。</span><span class="sxs-lookup"><span data-stu-id="98238-109">This walkthrough for F# 3.0 shows you how to create types for data that is represented by the Entity Data Model (EDM), the schema for which is specified in an .edmx file.</span></span> <span data-ttu-id="98238-110">此演练还演示如何使用 EdmxFile 类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="98238-110">This walkthrough also shows how to use the EdmxFile type provider.</span></span> <span data-ttu-id="98238-111">开始之前，请考虑 SqlEntityConnection 类型提供程序是否为更适当的类型提供程序选项。</span><span class="sxs-lookup"><span data-stu-id="98238-111">Before you begin, consider whether a SqlEntityConnection type provider is a more appropriate type provider option.</span></span> <span data-ttu-id="98238-112">SqlEntityConnection 类型提供程序最适合以下方案：在项目的开发阶段，你具有可连接到的实时数据库，并且你不介意在编译时指定连接字符串。</span><span class="sxs-lookup"><span data-stu-id="98238-112">The SqlEntityConnection type provider works best for scenarios where you have a live database that you can connect to during the development phase of your project, and you do not mind specifying the connection string at compile time.</span></span> <span data-ttu-id="98238-113">但是，此类型提供程序还会受到限制，它公开的数据库功能没有 EdmxFile 类型提供程序公开的数据库功能那样多。</span><span class="sxs-lookup"><span data-stu-id="98238-113">However, this type provider is also limited in that it doesn't expose as much database functionality as the EdmxFile type provider.</span></span> <span data-ttu-id="98238-114">此外，如果你不具有使用实体数据模型的数据库项目的实时数据库连接，则可使用 .edmx 文件针对数据库进行编码。</span><span class="sxs-lookup"><span data-stu-id="98238-114">Also, if you don't have a live database connection for a database project that uses the Entity Data Model, you can use the .edmx file to code against the database.</span></span> <span data-ttu-id="98238-115">在你使用 EdmxFile 类型提供程序时，F# 编译器将运行 EdmGen.exe 以生成其提供的类型。</span><span class="sxs-lookup"><span data-stu-id="98238-115">When you use the EdmxFile type provider, the F# compiler runs EdmGen.exe to generate the types that it provides.</span></span>

<span data-ttu-id="98238-116">此演练演示了下列任务，你必须按以下顺序执行这些任务才能成功完成演练：</span><span class="sxs-lookup"><span data-stu-id="98238-116">This walkthrough illustrates the following tasks, which you must perform in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="98238-117">创建 EDMX 文件</span><span class="sxs-lookup"><span data-stu-id="98238-117">Creating an EDMX file</span></span>
<br />

- <span data-ttu-id="98238-118">创建项目</span><span class="sxs-lookup"><span data-stu-id="98238-118">Creating the project</span></span>
<br />

- <span data-ttu-id="98238-119">查找或创建实体数据模型连接字符串</span><span class="sxs-lookup"><span data-stu-id="98238-119">Finding or creating the entity data model connection string</span></span>
<br />

- <span data-ttu-id="98238-120">配置类型提供程序</span><span class="sxs-lookup"><span data-stu-id="98238-120">Configuring the type provider</span></span>
<br />

- <span data-ttu-id="98238-121">查询数据</span><span class="sxs-lookup"><span data-stu-id="98238-121">Querying the data</span></span>
<br />

- <span data-ttu-id="98238-122">调用存储过程</span><span class="sxs-lookup"><span data-stu-id="98238-122">Calling a stored procedure</span></span>
<br />


## <a name="prerequisites"></a><span data-ttu-id="98238-123">系统必备</span><span class="sxs-lookup"><span data-stu-id="98238-123">Prerequisites</span></span>

## <a name="creating-an-edmx-file"></a><span data-ttu-id="98238-124">创建 EDMX 文件</span><span class="sxs-lookup"><span data-stu-id="98238-124">Creating an EDMX file</span></span>
<span data-ttu-id="98238-125">如果你已具有 EDMX 文件，则可跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="98238-125">If you already have an EDMX file, you can skip this step.</span></span>


#### <a name="to-create-an-edmx-file"></a><span data-ttu-id="98238-126">创建 EDMX 文件</span><span class="sxs-lookup"><span data-stu-id="98238-126">To create an EDMX file</span></span>

- <span data-ttu-id="98238-127">如果你还没有 EDMX 文件，则可以按照步骤在本演练末尾的说明进行操作[配置实体数据模型](generating-fsharp-types-from-edmx.md#configuring-the-entity-data-model)。</span><span class="sxs-lookup"><span data-stu-id="98238-127">If you don't already have an EDMX file, you can follow the instructions at the end of this walkthrough in the step [Configuring the Entity Data Model](generating-fsharp-types-from-edmx.md#configuring-the-entity-data-model).</span></span>
<br />

## <a name="creating-the-project"></a><span data-ttu-id="98238-128">创建项目</span><span class="sxs-lookup"><span data-stu-id="98238-128">Creating the project</span></span>
<span data-ttu-id="98238-129">在此步骤中，创建一个项目并添加对该项目的适当引用以使用 EDMX 类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="98238-129">In this step, you create a project and add appropriate references to it to use the EDMX type provider.</span></span>


#### <a name="to-create-and-set-up-an-f-project"></a><span data-ttu-id="98238-130">创建并设置 F# 项目</span><span class="sxs-lookup"><span data-stu-id="98238-130">To create and set up an F# project</span></span>

1. <span data-ttu-id="98238-131">关闭前一个项目并创建另一个项目，然后将其命名为 SchoolEDM。</span><span class="sxs-lookup"><span data-stu-id="98238-131">Close the previous project, create another project, and name it SchoolEDM.</span></span>
<br />

2. <span data-ttu-id="98238-132">在**解决方案资源管理器**，打开快捷菜单**引用**，然后选择**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="98238-132">In **Solution Explorer**, open the shortcut menu for **References**, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="98238-133">在**程序集**区域中，选择**Framework**节点。</span><span class="sxs-lookup"><span data-stu-id="98238-133">In the **Assemblies** area, choose the **Framework** node.</span></span>
<br />

4. <span data-ttu-id="98238-134">在可用的程序集列表中，选择**System.Data.Entity**和**System.Data.Linq**程序集，然后选择**添加**按钮将引用添加到这些到你的项目的程序集。</span><span class="sxs-lookup"><span data-stu-id="98238-134">In the list of available assemblies, choose the **System.Data.Entity** and **System.Data.Linq** assemblies, and then choose the **Add** button to add references to these assemblies to your project.</span></span>
<br />

5. <span data-ttu-id="98238-135">在**程序集**区域中，选择**扩展**节点。</span><span class="sxs-lookup"><span data-stu-id="98238-135">In the **Assemblies** area, select the **Extensions** node.</span></span>
<br />

6. <span data-ttu-id="98238-136">在可用扩展的列表中，添加对 FSharp.Data.TypeProviders 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="98238-136">In the  list of available extensions, add a reference to the FSharp.Data.TypeProviders assembly.</span></span>
<br />

7. <span data-ttu-id="98238-137">添加以下代码以打开相应的命名空间。</span><span class="sxs-lookup"><span data-stu-id="98238-137">Add the following code to open the appropriate namespaces.</span></span>
<br />

```fsharp
open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

## <a name="finding-or-creating-the-connection-string-for-the-entity-data-model"></a><span data-ttu-id="98238-138">查找或创建实体数据模型的连接字符串</span><span class="sxs-lookup"><span data-stu-id="98238-138">Finding or creating the connection string for the Entity Data Model</span></span>
<span data-ttu-id="98238-139">实体数据模型的连接字符串（EDMX 连接字符串）不仅包括数据库提供程序的连接字符串，还包括附加信息。</span><span class="sxs-lookup"><span data-stu-id="98238-139">The connection string for the Entity Data Model (EDMX connection string) includes not only the connection string for the database provider but also additional information.</span></span> <span data-ttu-id="98238-140">例如，简单 SQL Server 数据库的 EDMX 连接字符串类似于以下代码。</span><span class="sxs-lookup"><span data-stu-id="98238-140">For example, EDMX connection string for a simple SQL Server database resembles the following code.</span></span>

```fsharp
let edmConnectionString = "metadata=res://*/;provider=System.Data.SqlClient;Provider Connection String='Server=SERVER\Instance;Initial Catalog=DatabaseName;Integrated Security=SSPI;'"
```

<span data-ttu-id="98238-141">有关 EDMX 连接字符串的详细信息，请参阅[连接字符串](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)。</span><span class="sxs-lookup"><span data-stu-id="98238-141">For more information about EDMX connection strings, see [Connection Strings](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).</span></span>


#### <a name="to-find-or-create-the-connection-string-for-the-entity-data-model"></a><span data-ttu-id="98238-142">查找或创建实体数据模型的连接字符串</span><span class="sxs-lookup"><span data-stu-id="98238-142">To find or create the connection string for the Entity Data Model</span></span>

1. <span data-ttu-id="98238-143">EDMX 连接字符串难以手动生成，因此你可以通过编程方式生成该字符串来节省时间。</span><span class="sxs-lookup"><span data-stu-id="98238-143">EDMX connection strings can be difficult to generate by hand, so you can save time by generating it programmatically.</span></span> <span data-ttu-id="98238-144">如果你知道 EDMX 连接字符串，则可绕过此步骤，只需在下一步中使用该字符串即可。</span><span class="sxs-lookup"><span data-stu-id="98238-144">If you know your EDMX connection string, you can bypass this step and simply use that string in the next step.</span></span> <span data-ttu-id="98238-145">如果你不知道该字符串，请使用以下代码从你提供的数据库连接字符串生成 EDMX 连接字符串。</span><span class="sxs-lookup"><span data-stu-id="98238-145">If not, use the following code to generate the EDMX connection string from a database connection string that you provide.</span></span>
<br />

```fsharp
open System
open System.Data
open System.Data.SqlClient
open System.Data.EntityClient
open System.Data.Metadata.Edm

let getEDMConnection(dbConnectionString) =
  let dbConnection = new SqlConnection(dbConnectionString)
  let resourceArray = [| "res://*/" |]
  let assemblyList = [| System.Reflection.Assembly.GetCallingAssembly() |]
  let metaData = MetadataWorkspace(resourceArray, assemblyList)
  new EntityConnection(metaData, dbConnection)
```

## <a name="configuring-the-type-provider"></a><span data-ttu-id="98238-146">配置类型提供程序</span><span class="sxs-lookup"><span data-stu-id="98238-146">Configuring the type provider</span></span>
<span data-ttu-id="98238-147">在此步骤中，你使用 EDMX 连接字符串创建并配置类型提供程序，并为 .edmx 文件中定义的架构生成类型。</span><span class="sxs-lookup"><span data-stu-id="98238-147">In this step, you create and configure the type provider with the EDMX connection string, and you generate types for the schema that's defined in the .edmx file.</span></span>


#### <a name="to-configure-the-type-provider-and-generate-types"></a><span data-ttu-id="98238-148">配置类型提供程序和生成类型</span><span class="sxs-lookup"><span data-stu-id="98238-148">To configure the type provider and generate types</span></span>

1. <span data-ttu-id="98238-149">将本演练的步骤 1 中生成的 .edmx 文件复制到你的项目文件夹。</span><span class="sxs-lookup"><span data-stu-id="98238-149">Copy the .edmx file that you generated in the first step of this walkthrough to your project folder.</span></span>
<br />

2. <span data-ttu-id="98238-150">打开你的 F # 项目中的项目节点的快捷菜单选择**添加现有项**，然后选择.edmx 文件以将其添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="98238-150">Open the shortcut menu for the project node in your F# project, choose **Add Existing Item**, and then choose the .edmx file to add it to your project.</span></span>
<br />

3. <span data-ttu-id="98238-151">输入以下代码以激活 .edmx 文件的类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="98238-151">Enter the following code to activate the type provider for your .edmx file.</span></span> <span data-ttu-id="98238-152">替换*服务器*\*实例 * 替换为你正在运行 SQL Server 和你实例的名称，并且使用本演练中的第一个步骤中.edmx 文件的名称的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="98238-152">Replace *Server*\*Instance* with the name of your server that's running SQL Server and the name of your instance, and use the name of your .edmx file from the first step in this walkthrough.</span></span>
<br />

```fsharp
type edmx = EdmxFile<"Model1.edmx", ResolutionFolder = @"<path-tofolder-that-containsyour.edmx-file>">

use edmConnection =
  getEDMConnection("Data Source=SERVER\instance;Initial Catalog=School;Integrated Security=true;")
use context = new edmx.SchoolModel.SchoolEntities(edmConnection)
```

## <a name="querying-the-data"></a><span data-ttu-id="98238-153">查询数据</span><span class="sxs-lookup"><span data-stu-id="98238-153">Querying the data</span></span>
<span data-ttu-id="98238-154">在此步骤中，你使用 F# 查询表达式查询数据库。</span><span class="sxs-lookup"><span data-stu-id="98238-154">In this step, you use F# query expressions to query the database.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="98238-155">查询数据</span><span class="sxs-lookup"><span data-stu-id="98238-155">To query the data</span></span>

- <span data-ttu-id="98238-156">输入以下代码以查询实体数据模型中的数据。</span><span class="sxs-lookup"><span data-stu-id="98238-156">Enter the following code to query the data in the entity data model.</span></span>
<br />

```fsharp
query { 
  for course in context.Courses do
  select course 
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.Person do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results
query { 
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="calling-a-stored-procedure"></a><span data-ttu-id="98238-157">调用存储过程</span><span class="sxs-lookup"><span data-stu-id="98238-157">Calling a stored procedure</span></span>
<span data-ttu-id="98238-158">你可使用 EDMX 类型提供程序来调用存储过程。</span><span class="sxs-lookup"><span data-stu-id="98238-158">You can call stored procedures by using the EDMX type provider.</span></span> <span data-ttu-id="98238-159">在下面的过程中，School 数据库包含存储的过程、 **UpdatePerson**，这样可以更新的记录，提供了新值的列。</span><span class="sxs-lookup"><span data-stu-id="98238-159">In the following procedure, the School database contains a stored procedure, **UpdatePerson**, which updates a record, given new values for the columns.</span></span> <span data-ttu-id="98238-160">你可以使用此存储过程，因为该过程已作为 DataContext 类型的方法公开。</span><span class="sxs-lookup"><span data-stu-id="98238-160">You can use this stored procedure because it's exposed as a method on the DataContext type.</span></span>


#### <a name="to-call-a-stored-procedure"></a><span data-ttu-id="98238-161">调用存储过程</span><span class="sxs-lookup"><span data-stu-id="98238-161">To call a stored procedure</span></span>

- <span data-ttu-id="98238-162">添加以下代码以更新记录。</span><span class="sxs-lookup"><span data-stu-id="98238-162">Add the following code to update records.</span></span>
<br />

```fsharp
// Call a stored procedure.
let nullable value = new System.Nullable<_>(value)

// Assume now that you must correct someone's hire date.
// Throw an exception if more than one matching person is found.
let changeHireDate(lastName, firstName, hireDate) =

  query { 
    for person in context.People do
    where (person.LastName = lastName &&
           person.FirstName = firstName)
    exactlyOne 
  } |> (fun person ->
            context.UpdatePerson(nullable person.PersonID, person.LastName, person.FirstName, nullable hireDate, person.EnrollmentDate))

changeHireDate("Abercrombie", "Kim", DateTime.Parse("1/12/1998"))
|> printfn "Result: %d"
```

<span data-ttu-id="98238-163">如果操作成功，则结果为 1。</span><span class="sxs-lookup"><span data-stu-id="98238-163">The result is 1 if you succeed.</span></span> <span data-ttu-id="98238-164">请注意， **exactlyOne**用在查询表达式可确保只有一个结果是返回; 否则为将引发异常。</span><span class="sxs-lookup"><span data-stu-id="98238-164">Notice that **exactlyOne** is used in the query expression to ensure that only one result is returned; otherwise, an exception is thrown.</span></span> <span data-ttu-id="98238-165">此外，若要更轻松地使用可以为 null 值，可以使用简单**可以为 null**创建利用一般值可以为 null 值此代码中定义的函数。</span><span class="sxs-lookup"><span data-stu-id="98238-165">Also, to work with nullable values more easily, you can use the simple **nullable** function that's defined in this code to create a nullable value out of an ordinary value.</span></span>

<br />

## <a name="configuring-the-entity-data-model"></a><span data-ttu-id="98238-166">配置实体数据模型</span><span class="sxs-lookup"><span data-stu-id="98238-166">Configuring the Entity Data Model</span></span>
<span data-ttu-id="98238-167">应仅在你需要了解如何从数据库生成完整的实体数据模型且你不具有要测试的数据库时，完成该过程。</span><span class="sxs-lookup"><span data-stu-id="98238-167">You should complete this procedure only if you want to know how to generate a full Entity Data Model from a database and you don't have a database with which to test.</span></span>


#### <a name="to-configure-the-entity-data-model"></a><span data-ttu-id="98238-168">配置实体数据模型</span><span class="sxs-lookup"><span data-stu-id="98238-168">To configure the Entity Data Model</span></span>

1. <span data-ttu-id="98238-169">在菜单栏上，选择**SQL**， **TRANSACT-SQL 编辑器**，**新查询**创建数据库。</span><span class="sxs-lookup"><span data-stu-id="98238-169">On the menu bar, choose **SQL**, **Transact-SQL Editor**, **New Query** to create a database.</span></span> <span data-ttu-id="98238-170">如果系统提示你，请指定你的数据库服务器和实例。</span><span class="sxs-lookup"><span data-stu-id="98238-170">If prompted, specify your database server and instance.</span></span>
<br />

2. <span data-ttu-id="98238-171">复制并粘贴创建学生数据库中，数据库脚本的内容中所述[实体框架文档](https://msdn.microsoft.com/data/JJ614587.aspx)数据开发人员中心中。</span><span class="sxs-lookup"><span data-stu-id="98238-171">Copy and paste the contents of the database script that creates the Student database, as described in the [Entity Framework documentation](https://msdn.microsoft.com/data/JJ614587.aspx) in the Data Developer Center.</span></span>
<br />

3. <span data-ttu-id="98238-172">通过选择具有三角形符号的工具栏按钮或选择 Ctrl + Q 键中运行 SQL 脚本。</span><span class="sxs-lookup"><span data-stu-id="98238-172">Run the SQL script by choosing the toolbar button with the triangle symbol or choosing the Ctrl+Q keys.</span></span>
<br />

4. <span data-ttu-id="98238-173">在**服务器资源管理器**，打开快捷菜单**数据连接**，选择**添加连接**，然后输入数据库服务器上，实例名称的名称的名称和 School 数据库。</span><span class="sxs-lookup"><span data-stu-id="98238-173">In **Server Explorer**, open the shortcut menu for **Data Connections**, choose **Add Connection**, and then enter the name of the database server, the name of the instance name, and the School database.</span></span>
<br />

5. <span data-ttu-id="98238-174">创建 C# 或 Visual Basic 控制台应用程序项目，打开其快捷菜单，选择**添加新项**，然后选择**ADO.NET 实体数据模型**。</span><span class="sxs-lookup"><span data-stu-id="98238-174">Create a C# or Visual Basic Console Application project, open its shortcut menu, choose **Add New Item**, and then choose **ADO.NET Entity Data Model**.</span></span>
<br />  <span data-ttu-id="98238-175">实体数据模型向导随即打开。</span><span class="sxs-lookup"><span data-stu-id="98238-175">The Entity Data Model Wizard opens.</span></span> <span data-ttu-id="98238-176">通过使用此向导，你可以选择所需的创建实体数据模型的方式。</span><span class="sxs-lookup"><span data-stu-id="98238-176">By using this wizard, you can choose how you want to create the Entity Data Model.</span></span>
<br />

6. <span data-ttu-id="98238-177">下**选择模型内容**，选择**从数据库生成**复选框。</span><span class="sxs-lookup"><span data-stu-id="98238-177">Under **Choose Model Contents**, select the **Generate from database** check box.</span></span>
<br />

7. <span data-ttu-id="98238-178">在下一页上，选择新创建的 School 数据库作为数据连接。</span><span class="sxs-lookup"><span data-stu-id="98238-178">On the next page, choose your newly created School database as the data connection.</span></span>
<br />  <span data-ttu-id="98238-179">此连接应类似于 **&lt;servername&gt;。&lt;instancename&gt;。School.dbo**。</span><span class="sxs-lookup"><span data-stu-id="98238-179">This connection should resemble **&lt;servername&gt;.&lt;instancename&gt;.School.dbo**.</span></span>
<br />

8. <span data-ttu-id="98238-180">将实体连接字符串复制到剪贴板，因为该字符串稍后可能会很重要。</span><span class="sxs-lookup"><span data-stu-id="98238-180">Copy your entity connection string to the Clipboard because that string might be important later.</span></span>
<br />

9. <span data-ttu-id="98238-181">请确保该复选框以保存到的实体连接字符串**App.Config**文件已选中，然后在文本框中，这将帮助你更高版本，找到该连接字符串，如果需要记下的字符串值。</span><span class="sxs-lookup"><span data-stu-id="98238-181">Make sure the check box to save the entity connection string to the **App.Config** file is selected, and make note of the string value in the text box, which should help you locate the connection string later, if needed.</span></span>
<br />

10. <span data-ttu-id="98238-182">在下一页上，选择**表**和**存储过程和函数**。</span><span class="sxs-lookup"><span data-stu-id="98238-182">On the next page, choose **Tables** and **Stored Procedures and Functions**.</span></span>
<br />  <span data-ttu-id="98238-183">通过选择这些顶级节点，可以选择所有表、存储过程和函数。</span><span class="sxs-lookup"><span data-stu-id="98238-183">By choosing these top-level nodes, you choose all tables, stored procedures, and functions.</span></span> <span data-ttu-id="98238-184">如果需要，也可以单独选择这些项。</span><span class="sxs-lookup"><span data-stu-id="98238-184">You can also choose these individually, if you want.</span></span>
<br />

11. <span data-ttu-id="98238-185">确保选中其他设置所对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="98238-185">Make sure that the check boxes for the other settings are selected.</span></span>
<br />  <span data-ttu-id="98238-186">第一个**单复数形式或所生成的对象名称**复选框指示是否将单数形式更改为复数形式以匹配的命名对象表示数据库表中的约定。</span><span class="sxs-lookup"><span data-stu-id="98238-186">The first **Pluralize or singularize generated object names** check box indicates whether to change singular forms to plural to match conventions in naming objects that represent database tables.</span></span> <span data-ttu-id="98238-187">**模型中包括外键列**复选框确定是否包含的字段的用途是为其联接到其他字段中为数据库架构生成的对象类型。</span><span class="sxs-lookup"><span data-stu-id="98238-187">The **Include foreign key columns in the model** check box determines whether to include fields for which the purpose is to join to other fields in the object types that are generated for the database schema.</span></span> <span data-ttu-id="98238-188">第三个复选框指示是否在模型中包括存储过程和函数。</span><span class="sxs-lookup"><span data-stu-id="98238-188">The third check box indicates whether to include stored procedures and functions in the model.</span></span>
<br />

12. <span data-ttu-id="98238-189">选择**完成**按钮以生成包含基于 School 数据库的实体数据模型的.edmx 文件。</span><span class="sxs-lookup"><span data-stu-id="98238-189">Select the **Finish** button to generate an .edmx file that contains an Entity Data Model that's based on the School database.</span></span>
<br />  <span data-ttu-id="98238-190">一个文件， **Model1.edmx**，添加到你的项目，并且数据库关系图会出现。</span><span class="sxs-lookup"><span data-stu-id="98238-190">A file, **Model1.edmx**, is added to your project, and a database diagram appears.</span></span>
<br />

13. <span data-ttu-id="98238-191">在菜单栏上，选择**视图**，**其他窗口**，**实体数据模型浏览器**以查看模型的所有详细信息或**实体数据模型映射详细信息**以打开一个窗口，其中显示生成的对象模型如何映射到数据库表和列。</span><span class="sxs-lookup"><span data-stu-id="98238-191">On the menu bar, choose **View**, **Other Windows**, **Entity Data Model Browser** to view all the details of the model or **Entity Data Model Mapping Details** to open a window that shows how the generated object model maps onto database tables and columns.</span></span>
<br />


## <a name="next-steps"></a><span data-ttu-id="98238-192">后续步骤</span><span class="sxs-lookup"><span data-stu-id="98238-192">Next Steps</span></span>
<span data-ttu-id="98238-193">通过查看可用的查询运算符中列出浏览其他查询[查询表达式](../../language-reference/query-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="98238-193">Explore other queries by looking at the available query operators as listed in [Query Expressions](../../language-reference/query-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="98238-194">请参阅</span><span class="sxs-lookup"><span data-stu-id="98238-194">See Also</span></span>
[<span data-ttu-id="98238-195">类型提供程序</span><span class="sxs-lookup"><span data-stu-id="98238-195">Type Providers</span></span>](index.md)

[<span data-ttu-id="98238-196">EdmxFile 类型提供程序</span><span class="sxs-lookup"><span data-stu-id="98238-196">EdmxFile Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/edmxfile-type-provider-%5bfsharp%5d)

[<span data-ttu-id="98238-197">演练：使用类型提供程序和实体访问 SQL 数据库</span><span class="sxs-lookup"><span data-stu-id="98238-197">Walkthrough: Accessing a SQL Database by Using Type Providers and Entities</span></span>](accessing-a-sql-database-entities.md)

[<span data-ttu-id="98238-198">Entity Framework</span><span class="sxs-lookup"><span data-stu-id="98238-198">Entity Framework</span></span>](https://msdn.microsoft.com/data/ef)

[<span data-ttu-id="98238-199">.edmx 文件概述</span><span class="sxs-lookup"><span data-stu-id="98238-199">.edmx File Overview</span></span>](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)

[<span data-ttu-id="98238-200">EDM 生成器 &#40;EdmGen.exe &#41;</span><span class="sxs-lookup"><span data-stu-id="98238-200">EDM Generator &#40;EdmGen.exe&#41;</span></span>](https://msdn.microsoft.com/library/bb387165)

