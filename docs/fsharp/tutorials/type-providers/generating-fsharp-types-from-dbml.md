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
ms.openlocfilehash: 50e0a2bb6378c82b5c6425589da8a982b5fc496a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-generating-f-types-from-a-dbml-file"></a>演练：根据 DBML 文件生成 F# 类型 

> [!NOTE]
此指南专门针对 F # 3.0 编写，并将更新。  请参阅 [FSharp.Data](http://fsharp.github.io/FSharp.Data/) 了解最新的跨平台类型提供程序。

> [!NOTE]
API 参考链接将转到 MSDN。  Docs.microsoft.com API 参考尚未完成。

此针对 F # 3.0 的演练介绍如何从数据库中创建数据的类型，如果必须在.dbml 文件中编码的架构信息。 LINQ to SQL 使用这种文件格式来表示数据库架构。 在 Visual Studio 中，你可以使用对象关系 (O/R) 的设计器生成 LINQ to SQL 架构文件。 有关详细信息，请参阅[O/R 设计器概述](https://msdn.microsoft.com/library/bb384511.aspx)和[LINQ to SQL 中的代码生成](https://msdn.microsoft.com/library/bb386976)。

数据库标记语言 (DBML) 类型提供程序允许你编写使用基于数据库架构，而无需在编译时指定静态连接字符串的类型的代码。 这可能是需要考虑到最终应用程序将使用不同的数据库、 不同的凭据或与用于开发应用程序的不同的连接字符串的可能性的情况下很有用。 如果你具有可以在编译时使用的直接数据库连接，这是同一个数据库和你最终将在你生成的应用程序中使用的凭据，你还可以使用 SQLDataConnection 类型提供程序。 有关详细信息，请参阅[演练： 访问 SQL 数据库使用类型提供程序](accessing-a-sql-database.md)。

本演练阐释了以下任务。 它们应按才能成功完成演练以下顺序完成：


- 创建一个.dbml 文件
<br />

- 创建和设置 F # 项目
<br />

- 配置类型提供程序和生成类型
<br />

- 查询数据库
<br />


## <a name="prerequisites"></a>先决条件

## <a name="creating-a-dbml-file"></a>创建一个.dbml 文件
如果你不具有数据库上测试，创建一个在底部的说明[演练： 访问 SQL 数据库使用类型提供程序](accessing-a-sql-database.md)。 如果你按照这些说明操作，将创建名为 MyDatabase 包含几个简单的表和 SQL Server 上的存储的过程的数据库。

如果你已有一个.dbml 文件，则可以跳到部分，**创建并设置 F # 项目**。 否则为你可以创建给出的现有 SQL 数据库的.dbml 文件，并通过使用命令行工具 SqlMetal.exe。


#### <a name="to-create-a-dbml-file-by-using-sqlmetalexe"></a>若要使用 SqlMetal.exe 创建.dbml 文件

1. 打开**开发人员命令提示**。
<br />

2. 确保通过输入有权访问 SqlMetal.exe`SqlMetal.exe /?`在命令提示符。 SqlMetal.exe 通常安装在**Microsoft Sdk**文件夹中的**Program Files**或**Program Files (x86)**。
<br />

3. 使用以下命令行选项运行 SqlMetal.exe。 替换代替了正确的路径`c:\destpath`若要创建.dbml 文件中，并将数据库服务器的相应值插入，实例名称和数据库名称。
<br />

```
  SqlMetal.exe /sprocs /dbml:C:\destpath\MyDatabase.dbml /server:SERVER\INSTANCE /database:MyDatabase
```

>[!NOTE]
如果 SqlMetal.exe 具有创建文件由于权限问题造成的问题，将当前目录更改为具有写访问权限的文件夹中。


4. 你还可以查看其他可用命令行选项。 例如，有如果你想视图和包含在生成的类型中的 SQL 函数可以使用的选项。 有关详细信息，请参阅[SqlMetal.exe &#40;代码生成工具 &#41;](https://msdn.microsoft.com/library/bb386987).
<br />


## <a name="creating-and-setting-up-an-f-project"></a>创建和设置 F # 项目
在此步骤中，你可以创建项目并添加相应的引用以使用 DBML 类型提供程序。


#### <a name="to-create-and-set-up-an-f-project"></a>创建并设置 F# 项目

1. 将新的 F # 控制台应用程序项目添加到你的解决方案。
<br />

2. 在**解决方案资源管理器**，打开快捷菜单**引用**，然后选择**添加引用**。
<br />

3. 在**程序集**区域中，选择**Framework**节点，然后在可用的程序集列表中，选择**System.Data**和**System.Data.Linq**程序集。
<br />

4. 在**程序集**区域中，选择**扩展**，然后在可用的程序集列表中，选择**FSharp.Data.TypeProviders**。
<br />

5. 选择**确定**按钮将对这些程序集的引用添加到你的项目。
<br />

6. （可选）。 复制你在前一步骤中创建的.dbml 文件并在为你的项目的主文件夹中粘贴文件。 此文件夹包含的项目文件 (.fsproj) 和代码文件。 在菜单栏上，选择**项目**，**添加现有项**，然后指定要将其添加到你的项目的.dbml 文件。 如果你完成这些步骤，你可以忽略下一步 ResolutionFolder 静态参数。
<br />

## <a name="configuring-the-type-provider"></a>配置类型提供程序
在本部分中，你将创建类型提供程序，并从.dbml 文件中描述的架构生成类型。


#### <a name="to-configure-the-type-provider-and-generate-the-types"></a>若要配置类型提供程序和生成类型

- 添加代码，打开该**TypeProviders**命名空间和实例化的.dbml 文件，你想要使用的类型提供程序。 如果将.dbml 文件添加到你的项目中时，可以省略 ResolutionFolder 静态参数。
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ResolutionFolder = @"<path-to-folder-that-contains-.dbml-file>">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let dataContext = new dbml.Mydatabase(connectionString)
```

DataContext 类型提供对所有生成的类型的访问，并继承自`System.Data.Linq.DataContext`。 DbmlFile 类型提供程序具有各种可以设置的静态参数。 例如，可以通过指定使用 DataContext 类型的不同名称`DataContext=MyDataContext`。 在这种情况下，你的代码类似于下面的示例：
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ContextTypeName = "MyDataContext">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let db = new dbml.MyDataContext(connectionString)
```

## <a name="querying-the-database"></a>查询数据库
在本部分中，使用 F # 查询表达式查询数据库。


#### <a name="to-query-the-data"></a>查询数据

- 添加代码以查询数据库。
<br />

```fsharp
  query {
    for row in db.Table1 do
    where (row.TestData1 > 2)
    select row
  } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

## <a name="next-steps"></a>后续步骤
你可以继续使用其他查询表达式，或从数据上下文获取数据库连接并执行正常的 ADO.NET 数据操作。 有关其他步骤，请参阅部分后"查询数据"中[演练： 访问 SQL 数据库使用类型提供程序](accessing-a-sql-database.md)。


## <a name="see-also"></a>另请参阅
[DbmlFile 类型提供程序](https://msdn.microsoft.com/visualfsharpdocs/conceptual/dbmlfile-type-provider-%5bfsharp%5d)

[类型提供程序](index.md)

[演练：使用类型提供程序访问 SQL 数据库](accessing-a-sql-database.md)

[SqlMetal.exe &#40;代码生成工具 &#41;](https://msdn.microsoft.com/library/bb386987)

[查询表达式](../../language-reference/query-expressions.md)
