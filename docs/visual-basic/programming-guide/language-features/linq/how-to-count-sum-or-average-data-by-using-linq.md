---
title: "如何：使用 LINQ 对数据进行计数、求和与求平均值计算 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- average operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- queries [LINQ in Visual Basic], sum results
- Aggregate clause [Visual Basic]
- sum operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], counting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- count operator [LINQ in Visual Basic]
ms.assetid: 51ca1f59-7770-4884-8b76-113002e54fc0
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 48708af82ec4cc874d9ca3b8e6b231d5a862e004
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-count-sum-or-average-data-by-using-linq-visual-basic"></a><span data-ttu-id="b3ba3-102">如何：使用 LINQ 对数据进行计数、求和与求平均值计算 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3ba3-102">How to: Count, Sum, or Average Data by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="b3ba3-103">语言集成查询 (LINQ)，可以轻松地访问数据库信息和执行查询。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="b3ba3-104">下面的示例演示如何创建新的应用程序对 SQL Server 数据库执行查询。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="b3ba3-105">此示例计数、 求和、 并计算结果的平均值通过使用`Aggregate`和`Group By`子句。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-105">The sample counts, sums, and averages the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="b3ba3-106">有关详细信息，请参阅[Aggregate 子句](../../../../visual-basic/language-reference/queries/aggregate-clause.md)和[组 By 子句](../../../../visual-basic/language-reference/queries/group-by-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="b3ba3-107">本主题中的示例使用 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="b3ba3-108">如果你的开发计算机上没有 Northwind 示例数据库，您可以下载它从[Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web 站点。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-108">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="b3ba3-109">有关说明，请参阅[下载示例数据库](https://msdn.microsoft.com/library/bb399411)。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-109">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="b3ba3-110">若要创建与数据库的连接</span><span class="sxs-lookup"><span data-stu-id="b3ba3-110">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="b3ba3-111">在 Visual Studio 中，打开**服务器资源管理器**/**数据库资源管理器**通过单击**服务器资源管理器**/**数据库资源管理器**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="b3ba3-112">右键单击**数据连接**中**服务器资源管理器**/**数据库资源管理器**，然后单击**添加连接**。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="b3ba3-113">指定到 Northwind 示例数据库的有效连接。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="b3ba3-114">若要添加包含 LINQ to SQL 文件的项目</span><span class="sxs-lookup"><span data-stu-id="b3ba3-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="b3ba3-115">在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="b3ba3-116">选择 Visual Basic **Windows 窗体应用程序**作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="b3ba3-117">在 **“项目”** 菜单上，单击 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="b3ba3-118">选择**LINQ to SQL 类**项模板。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="b3ba3-119">为 `northwind.dbml` 文件命名。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="b3ba3-120">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-120">Click **Add**.</span></span> <span data-ttu-id="b3ba3-121">此时，northwind.dbml 文件打开的对象关系设计器 （O/R 设计器）。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="b3ba3-122">若要添加到 O/R 设计器查询的表</span><span class="sxs-lookup"><span data-stu-id="b3ba3-122">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="b3ba3-123">在**服务器资源管理器**/**数据库资源管理器**，展开包含到 Northwind 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="b3ba3-124">展开**表**文件夹。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="b3ba3-125">如果你已经关闭 O/R 设计器，你可以通过双击前面添加的 northwind.dbml 文件重新打开它。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="b3ba3-126">单击客户表并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="b3ba3-127">单击订单表并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="b3ba3-128">设计器创建新`Customer`和`Order`为你的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="b3ba3-129">请注意，设计器会自动检测表之间的关系并创建子相关对象的属性。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="b3ba3-130">例如，IntelliSense 将显示`Customer`对象具有`Orders`与该客户相关的所有订单的属性。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="b3ba3-131">保存所做的更改并关闭设计器。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="b3ba3-132">保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="b3ba3-133">若要添加代码以查询数据库并显示结果</span><span class="sxs-lookup"><span data-stu-id="b3ba3-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="b3ba3-134">从**工具箱**，拖动<xref:System.Windows.Forms.DataGridView>控件拖到你的项目，form1 的默认设置 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="b3ba3-135">双击 Form1 以将代码添加到`Load`窗体的事件。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="b3ba3-136">当表添加到 O/R 设计器时，设计器添加<xref:System.Data.Linq.DataContext>为你的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="b3ba3-137">此对象包含必须具有访问这些表，并访问单个对象和集合的每个表的代码。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="b3ba3-138"><xref:System.Data.Linq.DataContext>对象命名为你的项目基于.dbml 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="b3ba3-139">对于此项目，<xref:System.Data.Linq.DataContext>对象命名为`northwindDataContext`。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="b3ba3-140">你可以创建的实例<xref:System.Data.Linq.DataContext>在你的代码和查询表指定由 O/R 设计器。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="b3ba3-141">以下代码添加到`Load`事件来查询表中作为属性公开你<xref:System.Data.Linq.DataContext>和计数、 求和及平均结果。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your <xref:System.Data.Linq.DataContext> and count, sum, and average the results.</span></span> <span data-ttu-id="b3ba3-142">此示例使用`Aggregate`子句的单个结果的查询和`Group By`子句以显示有关平均值分组结果。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-142">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#13](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-count-sum-or-average-data-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="b3ba3-143">按 F5 运行项目，并查看结果。</span><span class="sxs-lookup"><span data-stu-id="b3ba3-143">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3ba3-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3ba3-144">See Also</span></span>  
 [<span data-ttu-id="b3ba3-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="b3ba3-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="b3ba3-146">查询</span><span class="sxs-lookup"><span data-stu-id="b3ba3-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="b3ba3-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b3ba3-147">LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb386976)  
 [<span data-ttu-id="b3ba3-148">DataContext 方法 （O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="b3ba3-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [<span data-ttu-id="b3ba3-149">Aggregate 子句</span><span class="sxs-lookup"><span data-stu-id="b3ba3-149">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="b3ba3-150">Group By 子句</span><span class="sxs-lookup"><span data-stu-id="b3ba3-150">Group By Clause</span></span>](../../../../visual-basic/language-reference/queries/group-by-clause.md)
