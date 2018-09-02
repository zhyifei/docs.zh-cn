---
title: 如何：使用 LINQ 筛选查询结果 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: f9854650b1f89a2330cfa81910187e3fb01c54b4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43424433"
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="f27a8-102">如何：使用 LINQ 筛选查询结果 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f27a8-102">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="f27a8-103">语言集成查询 (LINQ) 轻松地访问数据库的信息和执行查询。</span><span class="sxs-lookup"><span data-stu-id="f27a8-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="f27a8-104">下面的示例演示如何创建新应用程序对 SQL Server 数据库执行查询并使用特定值筛选结果`Where`子句。</span><span class="sxs-lookup"><span data-stu-id="f27a8-104">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="f27a8-105">有关详细信息，请参阅[Where 子句](../../../../visual-basic/language-reference/queries/where-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="f27a8-105">For more information, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
 <span data-ttu-id="f27a8-106">本主题中的示例使用 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="f27a8-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="f27a8-107">如果在开发计算机上没有此数据库，您可以从 Microsoft 下载中心下载它。</span><span class="sxs-lookup"><span data-stu-id="f27a8-107">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="f27a8-108">有关说明，请参阅[下载示例数据库](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="f27a8-108">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="f27a8-109">若要创建与数据库的连接</span><span class="sxs-lookup"><span data-stu-id="f27a8-109">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="f27a8-110">在 Visual Studio 中打开**服务器资源管理器**/**数据库资源管理器**通过单击**服务器资源管理器**/**数据库资源管理器**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="f27a8-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="f27a8-111">右键单击**数据连接**中**服务器资源管理器**/**数据库资源管理器**，然后单击**添加连接**。</span><span class="sxs-lookup"><span data-stu-id="f27a8-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="f27a8-112">指定到 Northwind 示例数据库的有效连接。</span><span class="sxs-lookup"><span data-stu-id="f27a8-112">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="f27a8-113">若要添加包含 LINQ to SQL 文件的项目</span><span class="sxs-lookup"><span data-stu-id="f27a8-113">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="f27a8-114">在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="f27a8-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="f27a8-115">选择 Visual Basic **Windows 窗体应用程序**作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="f27a8-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="f27a8-116">在 **“项目”** 菜单上，单击 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="f27a8-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="f27a8-117">选择**LINQ to SQL 类**项模板。</span><span class="sxs-lookup"><span data-stu-id="f27a8-117">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="f27a8-118">为 `northwind.dbml` 文件命名。</span><span class="sxs-lookup"><span data-stu-id="f27a8-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="f27a8-119">单击 **添加**。</span><span class="sxs-lookup"><span data-stu-id="f27a8-119">Click **Add**.</span></span> <span data-ttu-id="f27a8-120">此时，northwind.dbml 文件将打开对象关系设计器 （O/R 设计器）。</span><span class="sxs-lookup"><span data-stu-id="f27a8-120">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="f27a8-121">若要添加到 O/R 设计器查询的表</span><span class="sxs-lookup"><span data-stu-id="f27a8-121">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="f27a8-122">在中**服务器资源管理器**/**数据库资源管理器**，扩展连接到 Northwind 数据库。</span><span class="sxs-lookup"><span data-stu-id="f27a8-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="f27a8-123">展开**表**文件夹。</span><span class="sxs-lookup"><span data-stu-id="f27a8-123">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="f27a8-124">如果已关闭 O/R 设计器，您可以通过双击前面添加的 northwind.dbml 文件重新打开它。</span><span class="sxs-lookup"><span data-stu-id="f27a8-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="f27a8-125">单击客户表并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="f27a8-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="f27a8-126">单击订单表并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="f27a8-126">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="f27a8-127">在设计器创建新`Customer`和`Order`为你的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="f27a8-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="f27a8-128">请注意，在设计器会自动检测表之间的关系并创建子相关对象的属性。</span><span class="sxs-lookup"><span data-stu-id="f27a8-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="f27a8-129">例如，IntelliSense 将显示`Customer`对象具有`Orders`与该客户相关的所有订单的属性。</span><span class="sxs-lookup"><span data-stu-id="f27a8-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="f27a8-130">保存所做的更改并关闭设计器。</span><span class="sxs-lookup"><span data-stu-id="f27a8-130">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="f27a8-131">保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="f27a8-131">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="f27a8-132">添加代码以查询数据库并显示结果</span><span class="sxs-lookup"><span data-stu-id="f27a8-132">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="f27a8-133">从**工具箱**，拖动<xref:System.Windows.Forms.DataGridView>控件拖到你的项目，Form1 的默认 Windows 窗体上。</span><span class="sxs-lookup"><span data-stu-id="f27a8-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="f27a8-134">双击 Form1 以将代码添加到`Load`窗体的事件。</span><span class="sxs-lookup"><span data-stu-id="f27a8-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="f27a8-135">当表添加到 O/R 设计器时，在设计器添加<xref:System.Data.Linq.DataContext>为你的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="f27a8-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="f27a8-136">此对象包含必须具有访问这些表，除了单个对象和集合的每个表的代码。</span><span class="sxs-lookup"><span data-stu-id="f27a8-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="f27a8-137"><xref:System.Data.Linq.DataContext>对象将项目命名为根据.dbml 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="f27a8-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="f27a8-138">对于此项目，<xref:System.Data.Linq.DataContext>对象被命名为`northwindDataContext`。</span><span class="sxs-lookup"><span data-stu-id="f27a8-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="f27a8-139">可以创建的实例<xref:System.Data.Linq.DataContext>代码和查询中指定由 O/R 设计器的表。</span><span class="sxs-lookup"><span data-stu-id="f27a8-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="f27a8-140">将以下代码添加到`Load`事件以查询作为数据上下文的属性公开的表。</span><span class="sxs-lookup"><span data-stu-id="f27a8-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="f27a8-141">查询筛选结果，并返回位于中的客户`London`。</span><span class="sxs-lookup"><span data-stu-id="f27a8-141">The query filters the results and returns only customers that are located in `London`.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#11](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="f27a8-142">按 F5 以运行您的项目并查看结果。</span><span class="sxs-lookup"><span data-stu-id="f27a8-142">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="f27a8-143">以下是可以尝试一些其他筛选器。</span><span class="sxs-lookup"><span data-stu-id="f27a8-143">Following are some other filters that you can try.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#12](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f27a8-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="f27a8-144">See Also</span></span>  
 [<span data-ttu-id="f27a8-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="f27a8-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="f27a8-146">查询</span><span class="sxs-lookup"><span data-stu-id="f27a8-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="f27a8-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f27a8-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="f27a8-148">DataContext 方法（O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="f27a8-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
