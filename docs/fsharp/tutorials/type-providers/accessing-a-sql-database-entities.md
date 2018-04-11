---
title: 演练：使用类型提供程序和实体访问 SQL 数据库 (F#)
description: '了解如何访问 SQL 数据库基于 ADO.NET 实体数据模型在 F # 3.0 中的类型化的数据。'
keywords: visual f#, f#, 函数编程
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dc82a932-5401-4d19-9fb3-92c50d8db514
ms.openlocfilehash: 153050f27ade0152741bdc2d77ab85eefa8418e9
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/10/2018
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers-and-entities"></a><span data-ttu-id="2ad4c-104">演练：使用类型提供程序和实体访问 SQL 数据库</span><span class="sxs-lookup"><span data-stu-id="2ad4c-104">Walkthrough: Accessing a SQL Database by Using Type Providers and Entities</span></span>

> [!NOTE]
<span data-ttu-id="2ad4c-105">此指南专门针对 F # 3.0 编写，并将更新。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="2ad4c-106">请参阅 [FSharp.Data](https://fsharp.github.io/FSharp.Data/) 了解最新的跨平台类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="2ad4c-107">API 参考链接将转到 MSDN。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="2ad4c-108">Docs.microsoft.com API 参考尚未完成。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="2ad4c-109">此针对 F# 3.0 的演练演示如何根据 ADO.NET 实体数据模型访问 SQL 数据库的类型化数据。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-109">This walkthrough for F# 3.0 shows you how to access typed data for a SQL database based on the ADO.NET Entity Data Model.</span></span> <span data-ttu-id="2ad4c-110">此演练演示如何设置 F# `SqlEntityConnection` 类型提供程序以将其与 SQL 数据库一起使用、如何针对数据编写查询、如何对数据库调用存储过程以及如何使用某些 ADO.NET Entity Framework 类型和方法来更新数据库。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-110">This walkthrough shows you how to set up the F# `SqlEntityConnection` type provider for use with a SQL database, how to write queries against the data, how to call stored procedures on the database, as well as how to use some of the ADO.NET Entity Framework types and methods to update the database.</span></span>

<span data-ttu-id="2ad4c-111">此演练演示了下列任务，你应按以下顺序执行这些任务才能成功完成演练：</span><span class="sxs-lookup"><span data-stu-id="2ad4c-111">This walkthrough illustrates the following tasks, which you should perform in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="2ad4c-112">创建 School 数据库</span><span class="sxs-lookup"><span data-stu-id="2ad4c-112">Create the School database</span></span>
<br />

- <span data-ttu-id="2ad4c-113">创建并配置 F# 项目</span><span class="sxs-lookup"><span data-stu-id="2ad4c-113">Create and configure an F# project</span></span>
<br />

- <span data-ttu-id="2ad4c-114">配置类型提供程序并连接到实体数据模型</span><span class="sxs-lookup"><span data-stu-id="2ad4c-114">Configure the type provider and connect to the Entity Data Model</span></span>
<br />

- <span data-ttu-id="2ad4c-115">查询数据库</span><span class="sxs-lookup"><span data-stu-id="2ad4c-115">Query the database</span></span>
<br />

- <span data-ttu-id="2ad4c-116">更新数据库</span><span class="sxs-lookup"><span data-stu-id="2ad4c-116">Updating the database</span></span>
<br />


## <a name="prerequisites"></a><span data-ttu-id="2ad4c-117">系统必备</span><span class="sxs-lookup"><span data-stu-id="2ad4c-117">Prerequisites</span></span>
<span data-ttu-id="2ad4c-118">你必须能够访问正在运行可从中创建数据库的 SQL Server 的服务器才能完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-118">You must have access to a server that's running SQL Server where you can create a database to complete these steps.</span></span>

## <a name="create-the-school-database"></a><span data-ttu-id="2ad4c-119">创建 School 数据库</span><span class="sxs-lookup"><span data-stu-id="2ad4c-119">Create the School database</span></span>
<span data-ttu-id="2ad4c-120">你可以在正在运行你对其具有管理访问权的 SQL Server 的任何服务器上创建 School 数据库，也可使用 LocalDB。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-120">You can create the School database on any server that's running SQL Server to which you have administrative access, or you can use LocalDB.</span></span>


#### <a name="to-create-the-school-database"></a><span data-ttu-id="2ad4c-121">创建 School 数据库</span><span class="sxs-lookup"><span data-stu-id="2ad4c-121">To create the School database</span></span>

1. <span data-ttu-id="2ad4c-122">在**服务器资源管理器**，打开快捷菜单**数据连接**节点，然后选择**添加连接**。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-122">In **Server Explorer**, open the shortcut menu for the **Data Connections** node, and then choose **Add Connection**.</span></span>
<br />  <span data-ttu-id="2ad4c-123">**添加连接**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-123">The **Add Connection** dialog box appears.</span></span>
<br />

2. <span data-ttu-id="2ad4c-124">在**服务器名称**框中，指定您对其具有管理访问权限的 SQL Server 实例的名称或指定 (localdb \ v11.0)，如果你没有访问服务器。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-124">In the **Server name** box, specify the name of an instance of SQL Server to which you have administrative access, or specify (localdb\v11.0) if you don't have access to a server.</span></span>
<br />  <span data-ttu-id="2ad4c-125">SQL Server Express LocalDB 提供了轻型数据库服务器以便在你的计算机上进行开发和测试。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-125">SQL Server Express LocalDB provides a lightweight database server for development and testing on your machine.</span></span> <span data-ttu-id="2ad4c-126">有关 LocalDB 的详细信息，请参阅[演练： 在 Visual Studio 中创建本地数据库文件](https://msdn.microsoft.com/library/ms233763.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-126">For more information about LocalDB, see [Walkthrough: Creating a Local Database File in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span></span>
<br />  <span data-ttu-id="2ad4c-127">在中创建一个新的节点**服务器资源管理器**下**数据连接**。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-127">A new node is created in **Server Explorer** under **Data Connections**.</span></span>
<br />

3. <span data-ttu-id="2ad4c-128">打开新连接节点的快捷菜单，然后选择**新查询**。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-128">Open the shortcut menu for the new connection node, and then choose **New Query**.</span></span>
<br />

4. <span data-ttu-id="2ad4c-129">打开[创建 School 示例数据库](https://msdn.microsoft.com/library/bb399731(v=vs.100).aspx)上的 Microsoft 网站，然后复制和粘贴数据库脚本创建的 School 数据库到编辑器窗口。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-129">Open [Creating the School Sample Database](https://msdn.microsoft.com/library/bb399731(v=vs.100).aspx) on the Microsoft website, and then copy and paste the database script that creates the School database into the editor window.</span></span>
<br />


## <span data-ttu-id="2ad4c-130"><a name="BKMK_CreateConfigFSProj"> </a></span><span class="sxs-lookup"><span data-stu-id="2ad4c-130"><a name="BKMK_CreateConfigFSProj"> </a></span></span>

## <a name="create-and-configure-an-f-project"></a><span data-ttu-id="2ad4c-131">创建并配置 F# 项目</span><span class="sxs-lookup"><span data-stu-id="2ad4c-131">Create and configure an F# project</span></span>
<span data-ttu-id="2ad4c-132">在此步骤中，你将创建一个项目并将其设置为使用类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-132">In this step, you create a project and set it up to use a type provider.</span></span>


#### <a name="to-create-and-configure-an-f-project"></a><span data-ttu-id="2ad4c-133">创建并配置 F# 项目</span><span class="sxs-lookup"><span data-stu-id="2ad4c-133">To create and configure an F# project</span></span>

1. <span data-ttu-id="2ad4c-134">关闭前一个项目，创建另一个项目，并将其命名**SchoolEDM**。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-134">Close the previous project, create another project, and name it **SchoolEDM**.</span></span>
<br />

2. <span data-ttu-id="2ad4c-135">在**解决方案资源管理器**，打开快捷菜单**引用**，然后选择**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-135">In **Solution Explorer**, open the shortcut menu for **References**, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="2ad4c-136">选择**Framework**节点，然后在**Framework**列表中，选择**System.Data**， **System.Data.Entity**，和**System.Data.Linq**。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-136">Choose the **Framework** node, and then, in the **Framework** list, choose **System.Data**, **System.Data.Entity**,  and **System.Data.Linq**.</span></span>
<br />

4. <span data-ttu-id="2ad4c-137">选择**扩展**节点，添加对的引用[FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3)程序集，然后选择**确定**按钮以关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-137">Choose the **Extensions** node, add a reference to the [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3) assembly, and then choose the **OK** button to dismiss the dialog box.</span></span>
<br />

5. <span data-ttu-id="2ad4c-138">添加以下代码以定义一个内部模块并打开相应的命名空间。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-138">Add the following code to define an internal module and open appropriate namespaces.</span></span> <span data-ttu-id="2ad4c-139">该类型提供程序只能将类型注入私有或内部命名空间。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-139">The type provider can inject types only into a private or internal namespace.</span></span>
<br />

```fsharp
module internal SchoolEDM

open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

6. <span data-ttu-id="2ad4c-140">在本演练中以交互方式作为脚本而不是已编译的程序中运行的代码，请打开项目节点的快捷菜单，选择**添加新项**，添加 F # 脚本文件，然后将每个步骤中的代码添加到该脚本。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-140">To run the code in this walkthrough interactively as a script instead of as a compiled program, open the shortcut menu for the project node, choose **Add New Item**, add an F# script file, and then add the code in each step to the script.</span></span> <span data-ttu-id="2ad4c-141">若要加载程序集引用，请添加下列行。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-141">To load the assembly references, add the following lines.</span></span>
<br />

```fsharp
#r "System.Data.Entity.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

7. <span data-ttu-id="2ad4c-142">在添加代码块时突出显示该块，并选择 Alt + Enter 键以在 F# Interactive 中运行它。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-142">Highlight each block of code as you add it, and choose the Alt + Enter keys to run it in F# Interactive.</span></span>
<br />

## <a name="configure-the-type-provider-and-connect-to-the-entity-data-model"></a><span data-ttu-id="2ad4c-143">配置类型提供程序并连接到实体数据模型</span><span class="sxs-lookup"><span data-stu-id="2ad4c-143">Configure the type provider, and connect to the Entity Data Model</span></span>
<span data-ttu-id="2ad4c-144">在此步骤中，你将使用数据连接设置类型提供程序并获取允许你处理数据的数据上下文。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-144">In this step, you set up a type provider with a data connection and obtain a data context that allows you to work with data.</span></span>


#### <a name="to-configure-the-type-provider-and-connect-to-the-entity-data-model"></a><span data-ttu-id="2ad4c-145">配置类型提供程序并连接到实体数据模型</span><span class="sxs-lookup"><span data-stu-id="2ad4c-145">To configure the type provider, and connect to the Entity Data Model</span></span>

1. <span data-ttu-id="2ad4c-146">输入以下代码来配置 `SqlEntityConnection` 类型提供程序，该提供程序根据你之前创建的实体数据模型来生成 F# 类型。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-146">Enter the following code to configure the `SqlEntityConnection` type provider that generates F# types based on the Entity Data Model that you created previously.</span></span> <span data-ttu-id="2ad4c-147">仅使用 SQL 连接字符串，而不是使用完全 EDMX 连接字符串。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-147">Instead of the full EDMX connection string, use only the SQL connection string.</span></span>
<br />

```fsharp
type private EntityConnection = SqlEntityConnection<ConnectionString="Server=SERVER\InstanceName;Initial Catalog=School;Integrated Security=SSPI;MultipleActiveResultSets=true",Pluralize = true>
```

  <span data-ttu-id="2ad4c-148">此操作使用你之前创建的数据库连接设置类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-148">This action sets up a type provider with the database connection that you created earlier.</span></span> <span data-ttu-id="2ad4c-149">使用 ADO.NET Entity Framework 时需要 `MultipleActiveResultSets` 属性，因为该属性允许在一次连接中对数据库异步执行多个命令，此情况在 ADO.NET Entity Framework 代码中经常出现。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-149">The property `MultipleActiveResultSets` is needed when you use the ADO.NET Entity Framework because this property allows multiple commands to execute asynchronously on the database in one connection, which can occur frequently in ADO.NET Entity Framework code.</span></span> <span data-ttu-id="2ad4c-150">有关详细信息，请参阅[多个活动结果集 (MARS)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars)。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-150">For more information, see [Multiple Active Result Sets (MARS)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars).</span></span>
<br />

2. <span data-ttu-id="2ad4c-151">获取数据上下文，它是一个将数据库表作为属性包含并将数据库存储过程和函数作为方法包含的对象。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-151">Get the data context, which is an object that contains the database tables as properties and the database stored procedures and functions as methods.</span></span>
<br />

```fsharp
let context = EntityConnection.GetDataContext()
```

## <a name="querying-the-database"></a><span data-ttu-id="2ad4c-152">查询数据库</span><span class="sxs-lookup"><span data-stu-id="2ad4c-152">Querying the database</span></span>
<span data-ttu-id="2ad4c-153">在此步骤中，你使用 F# 查询表达式对数据库执行各种查询。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-153">In this step, you use F# query expressions to execute various queries on the database.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="2ad4c-154">查询数据</span><span class="sxs-lookup"><span data-stu-id="2ad4c-154">To query the data</span></span>

- <span data-ttu-id="2ad4c-155">输入以下代码可查询实体数据模型中的数据。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-155">Enter the following code to query the data from the entity data model.</span></span> <span data-ttu-id="2ad4c-156">请注意，如果 Pluralize = true，则会将数据库表 Course 更改为 Courses，并将 Person 更改为 People。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-156">Note the effect of Pluralize = true, which changes the database table Course to Courses and Person to People.</span></span>
<br />

```fsharp
query { 
  for course in context.Courses do
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.People do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results.
query {
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables.
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="updating-the-database"></a><span data-ttu-id="2ad4c-157">更新数据库</span><span class="sxs-lookup"><span data-stu-id="2ad4c-157">Updating the database</span></span>
<span data-ttu-id="2ad4c-158">若要更新数据库，请使用 Entity Framework 类和方法。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-158">To update the database, you use the Entity Framework classes and methods.</span></span> <span data-ttu-id="2ad4c-159">你可以将两种类型的数据上下文与 SQLEntityConnection 类型提供程序一起使用。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-159">You can use two types of data context with the SQLEntityConnection type provider.</span></span> <span data-ttu-id="2ad4c-160">首先，`ServiceTypes.SimpleDataContextTypes.EntityContainer` 是简化的数据上下文，它只包括表示数据库表和列的提供的属性。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-160">First, `ServiceTypes.SimpleDataContextTypes.EntityContainer` is the simplified data context, which includes only the provided properties that represent database tables and columns.</span></span> <span data-ttu-id="2ad4c-161">其次，完整数据上下文是 Entity Framework 类 `System.Data.Objects.ObjectContext` 的实例，其中包含用于将行添加到数据库的 `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)` 方法。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-161">Second, the full data context is an instance of the Entity Framework class `System.Data.Objects.ObjectContext`, which contains the method `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)` to add rows to the database.</span></span> <span data-ttu-id="2ad4c-162">实体框架识别表及其相互关系，因此它会强制实现数据库一致性。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-162">The Entity Framework recognizes the tables and the relationships between them, so it enforces database consistency.</span></span>


#### <a name="to-update-the-database"></a><span data-ttu-id="2ad4c-163">更新数据库</span><span class="sxs-lookup"><span data-stu-id="2ad4c-163">To update the database</span></span>

1. <span data-ttu-id="2ad4c-164">将以下代码添加到你的程序中。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-164">Add the following code to your program.</span></span> <span data-ttu-id="2ad4c-165">在此示例中，你添加两个对象（二者之间存在关系）并添加一个教师和一个办公室分配。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-165">In this example, you add two objects with a relationship between them, and you add an instructor and an office assignment.</span></span> <span data-ttu-id="2ad4c-166">表 `OfficeAssignments` 包含 `InstructorID` 列，该列引用 `PersonID` 表中的 `Person` 列。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-166">The table `OfficeAssignments` contains the `InstructorID` column, which references the `PersonID` column in the `Person` table.</span></span>
<br />

```fsharp
// The full data context
let fullContext = context.DataContext

// A helper function.
let nullable value = new System.Nullable<_>(value)

let addInstructor(lastName, firstName, hireDate, office) =
  let hireDate = DateTime.Parse(hireDate)
  let newPerson = new EntityConnection.ServiceTypes.Person(LastName = lastName,
                                                           FirstName = firstName,
                                                           HireDate = nullable hireDate)
  fullContext.AddObject("People", newPerson)

  let newOffice = new EntityConnection.ServiceTypes.OfficeAssignment(Location = office)

  fullContext.AddObject("OfficeAssignments", newOffice)
  fullContext.CommandTimeout <- nullable 1000
  fullContext.SaveChanges() |> printfn "Saved changes: %d object(s) modified."

addInstructor("Parker", "Darren", "1/1/1998", "41/3720")
```

<span data-ttu-id="2ad4c-167">在调用 `System.Data.Objects.ObjectContext.SaveChanges` 之前，未更改数据库中的任何内容。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-167">Nothing is changed in the database until you call `System.Data.Objects.ObjectContext.SaveChanges`.</span></span>
<br />

2. <span data-ttu-id="2ad4c-168">现在，通过删除你添加的对象来将数据库还原到其先前的状态。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-168">Now restore the database to its earlier state by deleting the objects that you added.</span></span>
<br />

```fsharp
let deleteInstructor(lastName, firstName) =
  query {
    for person in context.People do
    where (person.FirstName = firstName &&
           person.LastName = lastName)
    select person
  } |> Seq.iter (fun person->
                    query {
                      for officeAssignment in context.OfficeAssignments do
                      where (officeAssignment.Person.PersonID = person.PersonID)
                      select officeAssignment
                    } |> Seq.iter (fun officeAssignment -> fullContext.DeleteObject(officeAssignment))

                    fullContext.DeleteObject(person))

  // The call to SaveChanges should be outside of any iteration on the queries.
  fullContext.SaveChanges() |> printfn "Saved changed: %d object(s) modified."

deleteInstructor("Parker", "Darren")
```

>[!WARNING] 
<span data-ttu-id="2ad4c-169">当你使用查询表达式时，必须记住查询会受到延迟计算的限制。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-169">When you use a query expression, you must remember that the query is subject to lazy evaluation.</span></span> <span data-ttu-id="2ad4c-170">因此，该数据库在所有链接的计算期间（例如，在每个查询表达式后的 lambda 表达式块中）仍将打开以便读取。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-170">Therefore, the database is still open for reading during any chained evaluations, such as in the lambda expression blocks after each query expression.</span></span> <span data-ttu-id="2ad4c-171">在读取操作完成后，必须执行任何显式或隐式使用事务的数据库操作。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-171">Any database operation that explicitly or implicitly uses a transaction must occur after the read operations have completed.</span></span>


## <a name="next-steps"></a><span data-ttu-id="2ad4c-172">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2ad4c-172">Next Steps</span></span>
<span data-ttu-id="2ad4c-173">查看中可用的查询运算符，了解其他查询选项[查询表达式](../../language-reference/query-expressions.md)，并还查看[ADO.NET 实体框架](https://msdn.microsoft.com/library/bb399572)以了解哪些功能可供你时使用此类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="2ad4c-173">Explore other query options by reviewing the query operators available in [Query Expressions](../../language-reference/query-expressions.md), and also review the [ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572) to understand what functionality is available to you when you use this type provider.</span></span>


## <a name="see-also"></a><span data-ttu-id="2ad4c-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ad4c-174">See Also</span></span>
[<span data-ttu-id="2ad4c-175">类型提供程序</span><span class="sxs-lookup"><span data-stu-id="2ad4c-175">Type Providers</span></span>](index.md)  
[<span data-ttu-id="2ad4c-176">SqlEntityConnection 类型提供程序</span><span class="sxs-lookup"><span data-stu-id="2ad4c-176">SqlEntityConnection Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqlentityconnection-type-provider-%5bfsharp%5d)  
[<span data-ttu-id="2ad4c-177">演练： 根据 EDMX 架构文件生成 F # 类型</span><span class="sxs-lookup"><span data-stu-id="2ad4c-177">Walkthrough: Generating F# Types from an EDMX Schema File</span></span>](generating-fsharp-types-from-edmx.md)  
[<span data-ttu-id="2ad4c-178">ADO.NET 实体框架</span><span class="sxs-lookup"><span data-stu-id="2ad4c-178">ADO.NET Entity Framework</span></span>](https://msdn.microsoft.com/library/bb399572)  
[<span data-ttu-id="2ad4c-179">.edmx 文件概述</span><span class="sxs-lookup"><span data-stu-id="2ad4c-179">.edmx File Overview</span></span>](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
[<span data-ttu-id="2ad4c-180">EDM 生成器&#40;EdmGen.exe&#41;</span><span class="sxs-lookup"><span data-stu-id="2ad4c-180">EDM Generator &#40;EdmGen.exe&#41;</span></span>](https://msdn.microsoft.com/library/bb387165)  
