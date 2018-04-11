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
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers-and-entities"></a>演练：使用类型提供程序和实体访问 SQL 数据库

> [!NOTE]
此指南专门针对 F # 3.0 编写，并将更新。  请参阅 [FSharp.Data](https://fsharp.github.io/FSharp.Data/) 了解最新的跨平台类型提供程序。

> [!NOTE]
API 参考链接将转到 MSDN。  Docs.microsoft.com API 参考尚未完成。

此针对 F# 3.0 的演练演示如何根据 ADO.NET 实体数据模型访问 SQL 数据库的类型化数据。 此演练演示如何设置 F# `SqlEntityConnection` 类型提供程序以将其与 SQL 数据库一起使用、如何针对数据编写查询、如何对数据库调用存储过程以及如何使用某些 ADO.NET Entity Framework 类型和方法来更新数据库。

此演练演示了下列任务，你应按以下顺序执行这些任务才能成功完成演练：


- 创建 School 数据库
<br />

- 创建并配置 F# 项目
<br />

- 配置类型提供程序并连接到实体数据模型
<br />

- 查询数据库
<br />

- 更新数据库
<br />


## <a name="prerequisites"></a>系统必备
你必须能够访问正在运行可从中创建数据库的 SQL Server 的服务器才能完成这些步骤。

## <a name="create-the-school-database"></a>创建 School 数据库
你可以在正在运行你对其具有管理访问权的 SQL Server 的任何服务器上创建 School 数据库，也可使用 LocalDB。


#### <a name="to-create-the-school-database"></a>创建 School 数据库

1. 在**服务器资源管理器**，打开快捷菜单**数据连接**节点，然后选择**添加连接**。
<br />  **添加连接**对话框随即出现。
<br />

2. 在**服务器名称**框中，指定您对其具有管理访问权限的 SQL Server 实例的名称或指定 (localdb \ v11.0)，如果你没有访问服务器。
<br />  SQL Server Express LocalDB 提供了轻型数据库服务器以便在你的计算机上进行开发和测试。 有关 LocalDB 的详细信息，请参阅[演练： 在 Visual Studio 中创建本地数据库文件](https://msdn.microsoft.com/library/ms233763.aspx)。
<br />  在中创建一个新的节点**服务器资源管理器**下**数据连接**。
<br />

3. 打开新连接节点的快捷菜单，然后选择**新查询**。
<br />

4. 打开[创建 School 示例数据库](https://msdn.microsoft.com/library/bb399731(v=vs.100).aspx)上的 Microsoft 网站，然后复制和粘贴数据库脚本创建的 School 数据库到编辑器窗口。
<br />


## <a name="BKMK_CreateConfigFSProj"> </a>

## <a name="create-and-configure-an-f-project"></a>创建并配置 F# 项目
在此步骤中，你将创建一个项目并将其设置为使用类型提供程序。


#### <a name="to-create-and-configure-an-f-project"></a>创建并配置 F# 项目

1. 关闭前一个项目，创建另一个项目，并将其命名**SchoolEDM**。
<br />

2. 在**解决方案资源管理器**，打开快捷菜单**引用**，然后选择**添加引用**。
<br />

3. 选择**Framework**节点，然后在**Framework**列表中，选择**System.Data**， **System.Data.Entity**，和**System.Data.Linq**。
<br />

4. 选择**扩展**节点，添加对的引用[FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3)程序集，然后选择**确定**按钮以关闭对话框。
<br />

5. 添加以下代码以定义一个内部模块并打开相应的命名空间。 该类型提供程序只能将类型注入私有或内部命名空间。
<br />

```fsharp
module internal SchoolEDM

open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

6. 在本演练中以交互方式作为脚本而不是已编译的程序中运行的代码，请打开项目节点的快捷菜单，选择**添加新项**，添加 F # 脚本文件，然后将每个步骤中的代码添加到该脚本。 若要加载程序集引用，请添加下列行。
<br />

```fsharp
#r "System.Data.Entity.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

7. 在添加代码块时突出显示该块，并选择 Alt + Enter 键以在 F# Interactive 中运行它。
<br />

## <a name="configure-the-type-provider-and-connect-to-the-entity-data-model"></a>配置类型提供程序并连接到实体数据模型
在此步骤中，你将使用数据连接设置类型提供程序并获取允许你处理数据的数据上下文。


#### <a name="to-configure-the-type-provider-and-connect-to-the-entity-data-model"></a>配置类型提供程序并连接到实体数据模型

1. 输入以下代码来配置 `SqlEntityConnection` 类型提供程序，该提供程序根据你之前创建的实体数据模型来生成 F# 类型。 仅使用 SQL 连接字符串，而不是使用完全 EDMX 连接字符串。
<br />

```fsharp
type private EntityConnection = SqlEntityConnection<ConnectionString="Server=SERVER\InstanceName;Initial Catalog=School;Integrated Security=SSPI;MultipleActiveResultSets=true",Pluralize = true>
```

  此操作使用你之前创建的数据库连接设置类型提供程序。 使用 ADO.NET Entity Framework 时需要 `MultipleActiveResultSets` 属性，因为该属性允许在一次连接中对数据库异步执行多个命令，此情况在 ADO.NET Entity Framework 代码中经常出现。 有关详细信息，请参阅[多个活动结果集 (MARS)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars)。
<br />

2. 获取数据上下文，它是一个将数据库表作为属性包含并将数据库存储过程和函数作为方法包含的对象。
<br />

```fsharp
let context = EntityConnection.GetDataContext()
```

## <a name="querying-the-database"></a>查询数据库
在此步骤中，你使用 F# 查询表达式对数据库执行各种查询。


#### <a name="to-query-the-data"></a>查询数据

- 输入以下代码可查询实体数据模型中的数据。 请注意，如果 Pluralize = true，则会将数据库表 Course 更改为 Courses，并将 Person 更改为 People。
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

## <a name="updating-the-database"></a>更新数据库
若要更新数据库，请使用 Entity Framework 类和方法。 你可以将两种类型的数据上下文与 SQLEntityConnection 类型提供程序一起使用。 首先，`ServiceTypes.SimpleDataContextTypes.EntityContainer` 是简化的数据上下文，它只包括表示数据库表和列的提供的属性。 其次，完整数据上下文是 Entity Framework 类 `System.Data.Objects.ObjectContext` 的实例，其中包含用于将行添加到数据库的 `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)` 方法。 实体框架识别表及其相互关系，因此它会强制实现数据库一致性。


#### <a name="to-update-the-database"></a>更新数据库

1. 将以下代码添加到你的程序中。 在此示例中，你添加两个对象（二者之间存在关系）并添加一个教师和一个办公室分配。 表 `OfficeAssignments` 包含 `InstructorID` 列，该列引用 `PersonID` 表中的 `Person` 列。
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

在调用 `System.Data.Objects.ObjectContext.SaveChanges` 之前，未更改数据库中的任何内容。
<br />

2. 现在，通过删除你添加的对象来将数据库还原到其先前的状态。
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
当你使用查询表达式时，必须记住查询会受到延迟计算的限制。 因此，该数据库在所有链接的计算期间（例如，在每个查询表达式后的 lambda 表达式块中）仍将打开以便读取。 在读取操作完成后，必须执行任何显式或隐式使用事务的数据库操作。


## <a name="next-steps"></a>后续步骤
查看中可用的查询运算符，了解其他查询选项[查询表达式](../../language-reference/query-expressions.md)，并还查看[ADO.NET 实体框架](https://msdn.microsoft.com/library/bb399572)以了解哪些功能可供你时使用此类型提供程序。


## <a name="see-also"></a>另请参阅
[类型提供程序](index.md)  
[SqlEntityConnection 类型提供程序](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqlentityconnection-type-provider-%5bfsharp%5d)  
[演练： 根据 EDMX 架构文件生成 F # 类型](generating-fsharp-types-from-edmx.md)  
[ADO.NET 实体框架](https://msdn.microsoft.com/library/bb399572)  
[.edmx 文件概述](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
[EDM 生成器&#40;EdmGen.exe&#41;](https://msdn.microsoft.com/library/bb387165)  
