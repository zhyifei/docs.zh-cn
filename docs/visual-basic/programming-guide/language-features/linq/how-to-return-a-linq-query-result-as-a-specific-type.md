---
title: "如何：以特定类型返回 LINQ 查询结果 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 33b79a00533e4ad8960c7f3cb512aafbe36e50b0
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a><span data-ttu-id="8b73e-102">如何：以特定类型返回 LINQ 查询结果 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b73e-102">How to: Return a LINQ Query Result as a Specific Type (Visual Basic)</span></span>
<span data-ttu-id="8b73e-103">语言集成查询 (LINQ)，可以轻松地访问数据库信息和执行查询。</span><span class="sxs-lookup"><span data-stu-id="8b73e-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span> <span data-ttu-id="8b73e-104">默认情况下，LINQ 查询以匿名类型返回的对象的列表。</span><span class="sxs-lookup"><span data-stu-id="8b73e-104">By default, LINQ queries return a list of objects as an anonymous type.</span></span> <span data-ttu-id="8b73e-105">你还可以指定查询返回特定类型的列表，通过使用`Select`子句。</span><span class="sxs-lookup"><span data-stu-id="8b73e-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span></span>  
  
 <span data-ttu-id="8b73e-106">下面的示例演示如何创建的新应用程序对 SQL Server 数据库执行查询并将结果投影为特定的命名类型。</span><span class="sxs-lookup"><span data-stu-id="8b73e-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span></span> <span data-ttu-id="8b73e-107">有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)和[Select 子句](../../../../visual-basic/language-reference/queries/select-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="8b73e-107">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
 <span data-ttu-id="8b73e-108">本主题中的示例使用 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="8b73e-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="8b73e-109">如果你的开发计算机上没有 Northwind 示例数据库，您可以下载它从[Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web 站点。</span><span class="sxs-lookup"><span data-stu-id="8b73e-109">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="8b73e-110">有关说明，请参阅[下载示例数据库](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="8b73e-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="8b73e-111">若要创建与数据库的连接</span><span class="sxs-lookup"><span data-stu-id="8b73e-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="8b73e-112">在 Visual Studio 中，打开**服务器资源管理器**/**数据库资源管理器**通过单击**服务器资源管理器**/**数据库资源管理器**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="8b73e-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="8b73e-113">右键单击**数据连接**中**服务器资源管理器**/**数据库资源管理器**，然后单击**添加连接**。</span><span class="sxs-lookup"><span data-stu-id="8b73e-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="8b73e-114">指定到 Northwind 示例数据库的有效连接。</span><span class="sxs-lookup"><span data-stu-id="8b73e-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="8b73e-115">若要添加包含 LINQ to SQL 文件的项目</span><span class="sxs-lookup"><span data-stu-id="8b73e-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="8b73e-116">在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="8b73e-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="8b73e-117">选择 Visual Basic **Windows 窗体应用程序**作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="8b73e-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="8b73e-118">在 **“项目”** 菜单上，单击 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="8b73e-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="8b73e-119">选择**LINQ to SQL 类**项模板。</span><span class="sxs-lookup"><span data-stu-id="8b73e-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="8b73e-120">为 `northwind.dbml` 文件命名。</span><span class="sxs-lookup"><span data-stu-id="8b73e-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="8b73e-121">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="8b73e-121">Click **Add**.</span></span> <span data-ttu-id="8b73e-122">此时，northwind.dbml 文件打开的对象关系设计器 （O/R 设计器）。</span><span class="sxs-lookup"><span data-stu-id="8b73e-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="8b73e-123">若要添加到 O/R 设计器查询的表</span><span class="sxs-lookup"><span data-stu-id="8b73e-123">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="8b73e-124">在**服务器资源管理器**/**数据库资源管理器**，展开包含到 Northwind 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="8b73e-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="8b73e-125">展开**表**文件夹。</span><span class="sxs-lookup"><span data-stu-id="8b73e-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="8b73e-126">如果你已经关闭 O/R 设计器，你可以通过双击前面添加的 northwind.dbml 文件重新打开它。</span><span class="sxs-lookup"><span data-stu-id="8b73e-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="8b73e-127">单击客户表并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="8b73e-127">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="8b73e-128">设计器创建一个新`Customer`为你的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="8b73e-128">The designer creates a new `Customer` object for your project.</span></span> <span data-ttu-id="8b73e-129">可以投影查询结果映射为`Customer`类型或为你创建的类型。</span><span class="sxs-lookup"><span data-stu-id="8b73e-129">You can project a query result as the `Customer` type or as a type that you create.</span></span> <span data-ttu-id="8b73e-130">此示例将在后面的过程中创建新的类型，并将查询结果映射为该类型。</span><span class="sxs-lookup"><span data-stu-id="8b73e-130">This sample will create a new type in a later procedure and project a query result as that type.</span></span>  
  
3.  <span data-ttu-id="8b73e-131">保存所做的更改并关闭设计器。</span><span class="sxs-lookup"><span data-stu-id="8b73e-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="8b73e-132">保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="8b73e-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="8b73e-133">若要添加代码以查询数据库并显示结果</span><span class="sxs-lookup"><span data-stu-id="8b73e-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="8b73e-134">从**工具箱**，拖动<xref:System.Windows.Forms.DataGridView>控件拖到你的项目，form1 的默认设置 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="8b73e-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="8b73e-135">双击 Form1 以修改 Form1 类。</span><span class="sxs-lookup"><span data-stu-id="8b73e-135">Double-click Form1 to modify the Form1 class.</span></span>  
  
3.  <span data-ttu-id="8b73e-136">后`End Class`Form1 类的语句添加以下代码以创建`CustomerInfo`类型以保存此示例的查询结果。</span><span class="sxs-lookup"><span data-stu-id="8b73e-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#16](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_1.vb)]  
  
4.  <span data-ttu-id="8b73e-137">当表添加到 O/R 设计器时，设计器添加<xref:System.Data.Linq.DataContext>到你的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="8b73e-137">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="8b73e-138">此对象包含必须具有访问这些表，并访问单个对象和集合的每个表的代码。</span><span class="sxs-lookup"><span data-stu-id="8b73e-138">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="8b73e-139"><xref:System.Data.Linq.DataContext>对象命名为你的项目基于.dbml 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="8b73e-139">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="8b73e-140">对于此项目，<xref:System.Data.Linq.DataContext>对象命名为`northwindDataContext`。</span><span class="sxs-lookup"><span data-stu-id="8b73e-140">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="8b73e-141">你可以创建的实例<xref:System.Data.Linq.DataContext>在你的代码和查询表指定由 O/R 设计器。</span><span class="sxs-lookup"><span data-stu-id="8b73e-141">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="8b73e-142">在`Load`Form1 类的事件添加以下代码以查询公开为属性的数据上下文的表。</span><span class="sxs-lookup"><span data-stu-id="8b73e-142">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="8b73e-143">`Select`查询子句将创建一个新`CustomerInfo`而不是匿名类型的每个项的查询结果的类型。</span><span class="sxs-lookup"><span data-stu-id="8b73e-143">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#15](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_2.vb)]  
  
5.  <span data-ttu-id="8b73e-144">按 F5 运行项目，并查看结果。</span><span class="sxs-lookup"><span data-stu-id="8b73e-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b73e-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b73e-145">See Also</span></span>  
 [<span data-ttu-id="8b73e-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="8b73e-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="8b73e-147">查询</span><span class="sxs-lookup"><span data-stu-id="8b73e-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="8b73e-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8b73e-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="8b73e-149">DataContext 方法 （O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="8b73e-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
