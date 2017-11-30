---
title: "如何：使用 LINQ 筛选查询结果 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- filtering [Visual Basic]
- filtering data [LINQ in Visual Basic]
- filtering [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], filtering results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- filtering data [Visual Basic]
ms.assetid: ef103092-9bed-4134-97f4-2db696e83c12
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 09f2eb65858853fd759ae033f749151b348c124d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="13c63-102">如何：使用 LINQ 筛选查询结果 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13c63-102">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="13c63-103">语言集成查询 (LINQ)，可以轻松地访问数据库信息和执行查询。</span><span class="sxs-lookup"><span data-stu-id="13c63-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="13c63-104">下面的示例演示如何创建的新应用程序对 SQL Server 数据库执行查询并使用特定值来筛选结果`Where`子句。</span><span class="sxs-lookup"><span data-stu-id="13c63-104">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="13c63-105">有关详细信息，请参阅[Where 子句](../../../../visual-basic/language-reference/queries/where-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="13c63-105">For more information, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
 <span data-ttu-id="13c63-106">本主题中的示例使用 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="13c63-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="13c63-107">如果你的开发计算机上没有 Northwind 示例数据库，您可以下载它从[Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web 站点。</span><span class="sxs-lookup"><span data-stu-id="13c63-107">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="13c63-108">有关说明，请参阅[下载示例数据库](https://msdn.microsoft.com/library/bb399411)。</span><span class="sxs-lookup"><span data-stu-id="13c63-108">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="13c63-109">若要创建与数据库的连接</span><span class="sxs-lookup"><span data-stu-id="13c63-109">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="13c63-110">在 Visual Studio 中，打开**服务器资源管理器**/**数据库资源管理器**通过单击**服务器资源管理器**/**数据库资源管理器**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="13c63-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="13c63-111">右键单击**数据连接**中**服务器资源管理器**/**数据库资源管理器**，然后单击**添加连接**。</span><span class="sxs-lookup"><span data-stu-id="13c63-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="13c63-112">指定到 Northwind 示例数据库的有效连接。</span><span class="sxs-lookup"><span data-stu-id="13c63-112">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="13c63-113">若要添加包含 LINQ to SQL 文件的项目</span><span class="sxs-lookup"><span data-stu-id="13c63-113">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="13c63-114">在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="13c63-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="13c63-115">选择 Visual Basic **Windows 窗体应用程序**作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="13c63-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="13c63-116">在 **“项目”** 菜单上，单击 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="13c63-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="13c63-117">选择**LINQ to SQL 类**项模板。</span><span class="sxs-lookup"><span data-stu-id="13c63-117">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="13c63-118">为 `northwind.dbml` 文件命名。</span><span class="sxs-lookup"><span data-stu-id="13c63-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="13c63-119">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="13c63-119">Click **Add**.</span></span> <span data-ttu-id="13c63-120">此时，northwind.dbml 文件将打开对象关系设计器 （O/R 设计器）。</span><span class="sxs-lookup"><span data-stu-id="13c63-120">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="13c63-121">若要添加到 O/R 设计器查询的表</span><span class="sxs-lookup"><span data-stu-id="13c63-121">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="13c63-122">在**服务器资源管理器**/**数据库资源管理器**，展开包含到 Northwind 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="13c63-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="13c63-123">展开**表**文件夹。</span><span class="sxs-lookup"><span data-stu-id="13c63-123">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="13c63-124">如果你已经关闭 O/R 设计器，你可以通过双击前面添加的 northwind.dbml 文件重新打开它。</span><span class="sxs-lookup"><span data-stu-id="13c63-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="13c63-125">单击客户表并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="13c63-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="13c63-126">单击订单表并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="13c63-126">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="13c63-127">设计器创建新`Customer`和`Order`为你的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="13c63-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="13c63-128">请注意，设计器会自动检测表之间的关系并创建子相关对象的属性。</span><span class="sxs-lookup"><span data-stu-id="13c63-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="13c63-129">例如，IntelliSense 将显示`Customer`对象具有`Orders`与该客户相关的所有订单的属性。</span><span class="sxs-lookup"><span data-stu-id="13c63-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="13c63-130">保存所做的更改并关闭设计器。</span><span class="sxs-lookup"><span data-stu-id="13c63-130">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="13c63-131">保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="13c63-131">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="13c63-132">若要添加代码以查询数据库并显示结果</span><span class="sxs-lookup"><span data-stu-id="13c63-132">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="13c63-133">从**工具箱**，拖动<xref:System.Windows.Forms.DataGridView>控件拖到你的项目，form1 的默认设置 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="13c63-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="13c63-134">双击 Form1 以将代码添加到`Load`窗体的事件。</span><span class="sxs-lookup"><span data-stu-id="13c63-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="13c63-135">当表添加到 O/R 设计器时，设计器添加<xref:System.Data.Linq.DataContext>为你的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="13c63-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="13c63-136">此对象包含必须具有访问这些表，除了单个对象和集合的每个表的代码。</span><span class="sxs-lookup"><span data-stu-id="13c63-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="13c63-137"><xref:System.Data.Linq.DataContext>对象命名为你的项目基于.dbml 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="13c63-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="13c63-138">对于此项目，<xref:System.Data.Linq.DataContext>对象命名为`northwindDataContext`。</span><span class="sxs-lookup"><span data-stu-id="13c63-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="13c63-139">你可以创建的实例<xref:System.Data.Linq.DataContext>在你的代码和查询表指定由 O/R 设计器。</span><span class="sxs-lookup"><span data-stu-id="13c63-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="13c63-140">以下代码添加到`Load`事件以查询公开为属性的数据上下文的表。</span><span class="sxs-lookup"><span data-stu-id="13c63-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="13c63-141">查询筛选结果，并返回位于中的客户`London`。</span><span class="sxs-lookup"><span data-stu-id="13c63-141">The query filters the results and returns only customers that are located in `London`.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#11](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="13c63-142">按 F5 运行项目，并查看结果。</span><span class="sxs-lookup"><span data-stu-id="13c63-142">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="13c63-143">以下是你可以尝试的一些其他筛选器。</span><span class="sxs-lookup"><span data-stu-id="13c63-143">Following are some other filters that you can try.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#12](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="13c63-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13c63-144">See Also</span></span>  
 [<span data-ttu-id="13c63-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="13c63-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="13c63-146">查询</span><span class="sxs-lookup"><span data-stu-id="13c63-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="13c63-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="13c63-147">LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb386976)  
 [<span data-ttu-id="13c63-148">DataContext 方法 （O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="13c63-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
