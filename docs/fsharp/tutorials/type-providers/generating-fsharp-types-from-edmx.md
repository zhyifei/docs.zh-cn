---
title: 演练：根据 EDMX 架构文件生成 F# 类型 (F#)
description: '了解如何创建 F # 表示在 F # 3.0 中，为.edmx 文件中指定了的架构由实体数据模型 (EDM) 的数据类型。'
keywords: visual f#, f#, 函数编程
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 81adb2eb-625f-4ad8-aeaa-8f672a6d79a2
ms.openlocfilehash: 901457dce358f768b4f4c980703e09f6c744918e
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/10/2018
---
# <a name="walkthrough-generating-f-types-from-an-edmx-schema-file"></a>演练：根据 EDMX 架构文件生成 F# 类型

> [!NOTE]
此指南专门针对 F # 3.0 编写，并将更新。  请参阅 [FSharp.Data](https://fsharp.github.io/FSharp.Data/) 了解最新的跨平台类型提供程序。

> [!NOTE]
API 参考链接将转到 MSDN。  Docs.microsoft.com API 参考尚未完成。

此针对 F# 3.0 的演练演示如何创建由实体数据模型 (EDM)（在 .edmx 文件中指定的架构）表示的数据的类型。 此演练还演示如何使用 EdmxFile 类型提供程序。 开始之前，请考虑 SqlEntityConnection 类型提供程序是否为更适当的类型提供程序选项。 SqlEntityConnection 类型提供程序最适合以下方案：在项目的开发阶段，你具有可连接到的实时数据库，并且你不介意在编译时指定连接字符串。 但是，此类型提供程序还会受到限制，它公开的数据库功能没有 EdmxFile 类型提供程序公开的数据库功能那样多。 此外，如果你不具有使用实体数据模型的数据库项目的实时数据库连接，则可使用 .edmx 文件针对数据库进行编码。 在你使用 EdmxFile 类型提供程序时，F# 编译器将运行 EdmGen.exe 以生成其提供的类型。

此演练演示了下列任务，你必须按以下顺序执行这些任务才能成功完成演练：


- 创建 EDMX 文件
<br />

- 创建项目
<br />

- 查找或创建实体数据模型连接字符串
<br />

- 配置类型提供程序
<br />

- 查询数据
<br />

- 调用存储过程
<br />


## <a name="prerequisites"></a>系统必备

## <a name="creating-an-edmx-file"></a>创建 EDMX 文件
如果你已具有 EDMX 文件，则可跳过此步骤。


#### <a name="to-create-an-edmx-file"></a>创建 EDMX 文件

- 如果你还没有 EDMX 文件，则可以按照步骤在本演练末尾的说明进行操作[配置实体数据模型](generating-fsharp-types-from-edmx.md#configuring-the-entity-data-model)。
<br />

## <a name="creating-the-project"></a>创建项目
在此步骤中，创建一个项目并添加对该项目的适当引用以使用 EDMX 类型提供程序。


#### <a name="to-create-and-set-up-an-f-project"></a>创建并设置 F# 项目

1. 关闭前一个项目并创建另一个项目，然后将其命名为 SchoolEDM。
<br />

2. 在**解决方案资源管理器**，打开快捷菜单**引用**，然后选择**添加引用**。
<br />

3. 在**程序集**区域中，选择**Framework**节点。
<br />

4. 在可用的程序集列表中，选择**System.Data.Entity**和**System.Data.Linq**程序集，然后选择**添加**按钮将引用添加到这些到你的项目的程序集。
<br />

5. 在**程序集**区域中，选择**扩展**节点。
<br />

6. 在可用扩展的列表中，添加对 FSharp.Data.TypeProviders 程序集的引用。
<br />

7. 添加以下代码以打开相应的命名空间。
<br />

```fsharp
open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

## <a name="finding-or-creating-the-connection-string-for-the-entity-data-model"></a>查找或创建实体数据模型的连接字符串
实体数据模型的连接字符串（EDMX 连接字符串）不仅包括数据库提供程序的连接字符串，还包括附加信息。 例如，简单 SQL Server 数据库的 EDMX 连接字符串类似于以下代码。

```fsharp
let edmConnectionString = "metadata=res://*/;provider=System.Data.SqlClient;Provider Connection String='Server=SERVER\Instance;Initial Catalog=DatabaseName;Integrated Security=SSPI;'"
```

有关 EDMX 连接字符串的详细信息，请参阅[连接字符串](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)。


#### <a name="to-find-or-create-the-connection-string-for-the-entity-data-model"></a>查找或创建实体数据模型的连接字符串

1. EDMX 连接字符串难以手动生成，因此你可以通过编程方式生成该字符串来节省时间。 如果你知道 EDMX 连接字符串，则可绕过此步骤，只需在下一步中使用该字符串即可。 如果你不知道该字符串，请使用以下代码从你提供的数据库连接字符串生成 EDMX 连接字符串。
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

## <a name="configuring-the-type-provider"></a>配置类型提供程序
在此步骤中，你使用 EDMX 连接字符串创建并配置类型提供程序，并为 .edmx 文件中定义的架构生成类型。


#### <a name="to-configure-the-type-provider-and-generate-types"></a>配置类型提供程序和生成类型

1. 将本演练的步骤 1 中生成的 .edmx 文件复制到你的项目文件夹。
<br />

2. 打开你的 F # 项目中的项目节点的快捷菜单选择**添加现有项**，然后选择.edmx 文件以将其添加到你的项目。
<br />

3. 输入以下代码以激活 .edmx 文件的类型提供程序。 替换*服务器*\*实例 * 替换为你正在运行 SQL Server 和你实例的名称，并且使用本演练中的第一个步骤中.edmx 文件的名称的服务器的名称。
<br />

```fsharp
type edmx = EdmxFile<"Model1.edmx", ResolutionFolder = @"<path-tofolder-that-containsyour.edmx-file>">

use edmConnection =
  getEDMConnection("Data Source=SERVER\instance;Initial Catalog=School;Integrated Security=true;")
use context = new edmx.SchoolModel.SchoolEntities(edmConnection)
```

## <a name="querying-the-data"></a>查询数据
在此步骤中，你使用 F# 查询表达式查询数据库。


#### <a name="to-query-the-data"></a>查询数据

- 输入以下代码以查询实体数据模型中的数据。
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

## <a name="calling-a-stored-procedure"></a>调用存储过程
你可使用 EDMX 类型提供程序来调用存储过程。 在下面的过程中，School 数据库包含存储的过程、 **UpdatePerson**，这样可以更新的记录，提供了新值的列。 你可以使用此存储过程，因为该过程已作为 DataContext 类型的方法公开。


#### <a name="to-call-a-stored-procedure"></a>调用存储过程

- 添加以下代码以更新记录。
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

如果操作成功，则结果为 1。 请注意， **exactlyOne**用在查询表达式可确保只有一个结果是返回; 否则为将引发异常。 此外，若要更轻松地使用可以为 null 值，可以使用简单**可以为 null**创建利用一般值可以为 null 值此代码中定义的函数。

<br />

## <a name="configuring-the-entity-data-model"></a>配置实体数据模型
应仅在你需要了解如何从数据库生成完整的实体数据模型且你不具有要测试的数据库时，完成该过程。


#### <a name="to-configure-the-entity-data-model"></a>配置实体数据模型

1. 在菜单栏上，选择**SQL**， **TRANSACT-SQL 编辑器**，**新查询**创建数据库。 如果系统提示你，请指定你的数据库服务器和实例。
<br />

2. 复制并粘贴创建学生数据库中，数据库脚本的内容中所述[实体框架文档](https://msdn.microsoft.com/data/JJ614587.aspx)数据开发人员中心中。
<br />

3. 通过选择具有三角形符号的工具栏按钮或选择 Ctrl + Q 键中运行 SQL 脚本。
<br />

4. 在**服务器资源管理器**，打开快捷菜单**数据连接**，选择**添加连接**，然后输入数据库服务器上，实例名称的名称的名称和 School 数据库。
<br />

5. 创建 C# 或 Visual Basic 控制台应用程序项目，打开其快捷菜单，选择**添加新项**，然后选择**ADO.NET 实体数据模型**。
<br />  实体数据模型向导随即打开。 通过使用此向导，你可以选择所需的创建实体数据模型的方式。
<br />

6. 下**选择模型内容**，选择**从数据库生成**复选框。
<br />

7. 在下一页上，选择新创建的 School 数据库作为数据连接。
<br />  此连接应类似于 **&lt;servername&gt;。&lt;instancename&gt;。School.dbo**。
<br />

8. 将实体连接字符串复制到剪贴板，因为该字符串稍后可能会很重要。
<br />

9. 请确保该复选框以保存到的实体连接字符串**App.Config**文件已选中，然后在文本框中，这将帮助你更高版本，找到该连接字符串，如果需要记下的字符串值。
<br />

10. 在下一页上，选择**表**和**存储过程和函数**。
<br />  通过选择这些顶级节点，可以选择所有表、存储过程和函数。 如果需要，也可以单独选择这些项。
<br />

11. 确保选中其他设置所对应的复选框。
<br />  第一个**单复数形式或所生成的对象名称**复选框指示是否将单数形式更改为复数形式以匹配的命名对象表示数据库表中的约定。 **模型中包括外键列**复选框确定是否包含的字段的用途是为其联接到其他字段中为数据库架构生成的对象类型。 第三个复选框指示是否在模型中包括存储过程和函数。
<br />

12. 选择**完成**按钮以生成包含基于 School 数据库的实体数据模型的.edmx 文件。
<br />  一个文件， **Model1.edmx**，添加到你的项目，并且数据库关系图会出现。
<br />

13. 在菜单栏上，选择**视图**，**其他窗口**，**实体数据模型浏览器**以查看模型的所有详细信息或**实体数据模型映射详细信息**以打开一个窗口，其中显示生成的对象模型如何映射到数据库表和列。
<br />


## <a name="next-steps"></a>后续步骤
通过查看可用的查询运算符中列出浏览其他查询[查询表达式](../../language-reference/query-expressions.md)。


## <a name="see-also"></a>另请参阅
[类型提供程序](index.md)

[EdmxFile 类型提供程序](https://msdn.microsoft.com/visualfsharpdocs/conceptual/edmxfile-type-provider-%5bfsharp%5d)

[演练：使用类型提供程序和实体访问 SQL 数据库](accessing-a-sql-database-entities.md)

[Entity Framework](https://msdn.microsoft.com/data/ef)

[.edmx 文件概述](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)

[EDM 生成器&#40;EdmGen.exe&#41;](https://msdn.microsoft.com/library/bb387165)

