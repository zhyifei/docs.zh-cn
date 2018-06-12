---
title: 如何：使用 LINQ 排序查询结果 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- sorting query results, multiple columns
- sorting data [Visual Basic]
- sorting data [LINQ in Visual Basic]
- sorting query results [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], sorting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 07a4584d-9fd8-4a1d-b7d9-ccf2efa5c84e
ms.openlocfilehash: 40baa1d7ae463b4193e4af5a9b79d29116b179b4
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2018
ms.locfileid: "34826901"
---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="a1412-102">如何：使用 LINQ 排序查询结果 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1412-102">How to: Sort Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="a1412-103">语言集成查询 (LINQ)，可以轻松地访问数据库信息和执行查询。</span><span class="sxs-lookup"><span data-stu-id="a1412-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="a1412-104">下面的示例演示如何创建新的应用程序，对 SQL Server 数据库执行查询对按多个字段对结果进行排序通过使用`Order By`子句。</span><span class="sxs-lookup"><span data-stu-id="a1412-104">The following example shows how to create a new application that performs queries against a SQL Server database and sorts the results by multiple fields by using the `Order By` clause.</span></span> <span data-ttu-id="a1412-105">可以按升序或降序每个字段的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="a1412-105">The sort order for each field can be ascending order or descending order.</span></span> <span data-ttu-id="a1412-106">有关详细信息，请参阅[Order By 子句](../../../../visual-basic/language-reference/queries/order-by-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="a1412-106">For more information, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="a1412-107">本主题中的示例使用 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="a1412-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="a1412-108">如果你的开发计算机上没有此数据库，您可以从 Microsoft 下载中心下载它。</span><span class="sxs-lookup"><span data-stu-id="a1412-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="a1412-109">有关说明，请参阅[下载示例数据库](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="a1412-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="a1412-110">若要创建与数据库的连接</span><span class="sxs-lookup"><span data-stu-id="a1412-110">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="a1412-111">在 Visual Studio 中，打开**服务器资源管理器**/**数据库资源管理器**通过单击**服务器资源管理器**/**数据库资源管理器**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="a1412-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="a1412-112">右键单击**数据连接**中**服务器资源管理器**/**数据库资源管理器**，然后单击**添加连接**。</span><span class="sxs-lookup"><span data-stu-id="a1412-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="a1412-113">指定到 Northwind 示例数据库的有效连接。</span><span class="sxs-lookup"><span data-stu-id="a1412-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="a1412-114">若要添加包含 LINQ to SQL 文件的项目</span><span class="sxs-lookup"><span data-stu-id="a1412-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="a1412-115">在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="a1412-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="a1412-116">选择 Visual Basic **Windows 窗体应用程序**作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="a1412-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="a1412-117">在 **“项目”** 菜单上，单击 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="a1412-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="a1412-118">选择**LINQ to SQL 类**项模板。</span><span class="sxs-lookup"><span data-stu-id="a1412-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="a1412-119">为 `northwind.dbml` 文件命名。</span><span class="sxs-lookup"><span data-stu-id="a1412-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="a1412-120">单击 **添加**。</span><span class="sxs-lookup"><span data-stu-id="a1412-120">Click **Add**.</span></span> <span data-ttu-id="a1412-121">此时，northwind.dbml 文件打开的对象关系设计器 （O/R 设计器）。</span><span class="sxs-lookup"><span data-stu-id="a1412-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="a1412-122">若要添加到 O/R 设计器查询的表</span><span class="sxs-lookup"><span data-stu-id="a1412-122">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="a1412-123">在**服务器资源管理器**/**数据库资源管理器**，展开包含到 Northwind 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="a1412-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="a1412-124">展开**表**文件夹。</span><span class="sxs-lookup"><span data-stu-id="a1412-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="a1412-125">如果你已经关闭 O/R 设计器，你可以通过双击前面添加的 northwind.dbml 文件重新打开它。</span><span class="sxs-lookup"><span data-stu-id="a1412-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="a1412-126">单击客户表并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="a1412-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="a1412-127">单击订单表并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="a1412-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="a1412-128">设计器创建新`Customer`和`Order`为你的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="a1412-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="a1412-129">请注意，设计器会自动检测表之间的关系并创建子相关对象的属性。</span><span class="sxs-lookup"><span data-stu-id="a1412-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="a1412-130">例如，IntelliSense 将显示`Customer`对象具有`Orders`与该客户相关的所有订单的属性。</span><span class="sxs-lookup"><span data-stu-id="a1412-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="a1412-131">保存所做的更改并关闭设计器。</span><span class="sxs-lookup"><span data-stu-id="a1412-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="a1412-132">保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="a1412-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="a1412-133">若要添加代码以查询数据库并显示结果</span><span class="sxs-lookup"><span data-stu-id="a1412-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="a1412-134">从**工具箱**，拖动<xref:System.Windows.Forms.DataGridView>控件拖到你的项目，form1 的默认设置 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="a1412-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="a1412-135">双击 Form1 以将代码添加到`Load`窗体的事件。</span><span class="sxs-lookup"><span data-stu-id="a1412-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="a1412-136">当表添加到 O/R 设计器时，设计器添加<xref:System.Data.Linq.DataContext>到你的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="a1412-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="a1412-137">此对象包含必须具有访问这些表，并访问单个对象和集合的每个表的代码。</span><span class="sxs-lookup"><span data-stu-id="a1412-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="a1412-138"><xref:System.Data.Linq.DataContext>对象命名为你的项目基于.dbml 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="a1412-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="a1412-139">对于此项目，<xref:System.Data.Linq.DataContext>对象命名为`northwindDataContext`。</span><span class="sxs-lookup"><span data-stu-id="a1412-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="a1412-140">你可以创建的实例<xref:System.Data.Linq.DataContext>在你的代码和查询表指定由 O/R 设计器。</span><span class="sxs-lookup"><span data-stu-id="a1412-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="a1412-141">以下代码添加到`Load`事件，以查询公开为属性的数据上下文和对结果进行排序的表。</span><span class="sxs-lookup"><span data-stu-id="a1412-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context and sort the results.</span></span> <span data-ttu-id="a1412-142">按客户订单，按降序顺序数，查询对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="a1412-142">The query sorts the results by the number of customer orders, in descending order.</span></span> <span data-ttu-id="a1412-143">具有相同数量的订单的客户按公司名称的升序 （默认值） 排序。</span><span class="sxs-lookup"><span data-stu-id="a1412-143">Customers that have the same number of orders are ordered by company name in ascending order (the default).</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#10](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-sort-query-results-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="a1412-144">按 F5 运行项目，并查看结果。</span><span class="sxs-lookup"><span data-stu-id="a1412-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1412-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1412-145">See Also</span></span>  
 [<span data-ttu-id="a1412-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="a1412-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="a1412-147">查询</span><span class="sxs-lookup"><span data-stu-id="a1412-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="a1412-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a1412-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="a1412-149">DataContext 方法 （O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="a1412-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
