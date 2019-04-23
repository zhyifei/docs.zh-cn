---
title: 如何：使用 LINQ (Visual Basic 中) 的查询结果进行排序
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
ms.openlocfilehash: d2114e908077ec947164a28f48841282abefda2e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59301212"
---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="71213-102">如何：使用 LINQ (Visual Basic 中) 的查询结果进行排序</span><span class="sxs-lookup"><span data-stu-id="71213-102">How to: Sort Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="71213-103">语言集成查询 (LINQ) 轻松地访问数据库的信息和执行查询。</span><span class="sxs-lookup"><span data-stu-id="71213-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="71213-104">下面的示例演示如何创建新应用程序对 SQL Server 数据库执行查询并对按多个字段对结果进行排序通过使用`Order By`子句。</span><span class="sxs-lookup"><span data-stu-id="71213-104">The following example shows how to create a new application that performs queries against a SQL Server database and sorts the results by multiple fields by using the `Order By` clause.</span></span> <span data-ttu-id="71213-105">可以按升序或降序排序的每个字段的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="71213-105">The sort order for each field can be ascending order or descending order.</span></span> <span data-ttu-id="71213-106">有关详细信息，请参阅[Order By 子句](../../../../visual-basic/language-reference/queries/order-by-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="71213-106">For more information, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="71213-107">本主题中的示例使用 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="71213-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="71213-108">如果在开发计算机上没有此数据库，您可以从 Microsoft 下载中心下载它。</span><span class="sxs-lookup"><span data-stu-id="71213-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="71213-109">有关说明，请参阅[下载示例数据库](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="71213-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="71213-110">若要创建与数据库的连接</span><span class="sxs-lookup"><span data-stu-id="71213-110">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="71213-111">在 Visual Studio 中打开**服务器资源管理器**/**数据库资源管理器**通过单击**服务器资源管理器**/**数据库资源管理器**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="71213-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="71213-112">右键单击**数据连接**中**服务器资源管理器**/**数据库资源管理器**，然后单击**添加连接**。</span><span class="sxs-lookup"><span data-stu-id="71213-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="71213-113">指定到 Northwind 示例数据库的有效连接。</span><span class="sxs-lookup"><span data-stu-id="71213-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="71213-114">若要添加包含 LINQ to SQL 文件的项目</span><span class="sxs-lookup"><span data-stu-id="71213-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="71213-115">在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="71213-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="71213-116">选择 Visual Basic **Windows 窗体应用程序**作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="71213-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="71213-117">在 **“项目”** 菜单上，单击 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="71213-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="71213-118">选择**LINQ to SQL 类**项模板。</span><span class="sxs-lookup"><span data-stu-id="71213-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="71213-119">为 `northwind.dbml` 文件命名。</span><span class="sxs-lookup"><span data-stu-id="71213-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="71213-120">单击 **添加**。</span><span class="sxs-lookup"><span data-stu-id="71213-120">Click **Add**.</span></span> <span data-ttu-id="71213-121">此时，northwind.dbml 文件打开时对象关系设计器 （O/R 设计器）。</span><span class="sxs-lookup"><span data-stu-id="71213-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="71213-122">若要添加到 O/R 设计器查询的表</span><span class="sxs-lookup"><span data-stu-id="71213-122">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="71213-123">在中**服务器资源管理器**/**数据库资源管理器**，扩展连接到 Northwind 数据库。</span><span class="sxs-lookup"><span data-stu-id="71213-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="71213-124">展开**表**文件夹。</span><span class="sxs-lookup"><span data-stu-id="71213-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="71213-125">如果已关闭 O/R 设计器，您可以通过双击前面添加的 northwind.dbml 文件重新打开它。</span><span class="sxs-lookup"><span data-stu-id="71213-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="71213-126">单击客户表并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="71213-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="71213-127">单击订单表并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="71213-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="71213-128">在设计器创建新`Customer`和`Order`为你的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="71213-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="71213-129">请注意，在设计器会自动检测表之间的关系并创建子相关对象的属性。</span><span class="sxs-lookup"><span data-stu-id="71213-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="71213-130">例如，IntelliSense 将显示`Customer`对象具有`Orders`与该客户相关的所有订单的属性。</span><span class="sxs-lookup"><span data-stu-id="71213-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="71213-131">保存所做的更改并关闭设计器。</span><span class="sxs-lookup"><span data-stu-id="71213-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="71213-132">保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="71213-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="71213-133">添加代码以查询数据库并显示结果</span><span class="sxs-lookup"><span data-stu-id="71213-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="71213-134">从**工具箱**，拖动<xref:System.Windows.Forms.DataGridView>控件拖到你的项目，Form1 的默认 Windows 窗体上。</span><span class="sxs-lookup"><span data-stu-id="71213-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="71213-135">双击 Form1 以将代码添加到`Load`窗体的事件。</span><span class="sxs-lookup"><span data-stu-id="71213-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="71213-136">当表添加到 O/R 设计器时，在设计器添加<xref:System.Data.Linq.DataContext>到你的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="71213-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="71213-137">此对象包含必须具有访问这些表，以及访问单个对象和集合的每个表的代码。</span><span class="sxs-lookup"><span data-stu-id="71213-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="71213-138"><xref:System.Data.Linq.DataContext>对象将项目命名为根据.dbml 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="71213-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="71213-139">对于此项目，<xref:System.Data.Linq.DataContext>对象被命名为`northwindDataContext`。</span><span class="sxs-lookup"><span data-stu-id="71213-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="71213-140">可以创建的实例<xref:System.Data.Linq.DataContext>代码和查询中指定由 O/R 设计器的表。</span><span class="sxs-lookup"><span data-stu-id="71213-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="71213-141">将以下代码添加到`Load`事件，以查询方式被称为数据上下文的属性和对结果进行排序的表。</span><span class="sxs-lookup"><span data-stu-id="71213-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context and sort the results.</span></span> <span data-ttu-id="71213-142">查询对客户的订单，按降序顺序数排序结果。</span><span class="sxs-lookup"><span data-stu-id="71213-142">The query sorts the results by the number of customer orders, in descending order.</span></span> <span data-ttu-id="71213-143">具有相同数目的订单的客户按升序排序 （默认值） 的公司名称进行排序。</span><span class="sxs-lookup"><span data-stu-id="71213-143">Customers that have the same number of orders are ordered by company name in ascending order (the default).</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form4.vb#10)]  
  
4. <span data-ttu-id="71213-144">按 F5 以运行您的项目并查看结果。</span><span class="sxs-lookup"><span data-stu-id="71213-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71213-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="71213-145">See also</span></span>

- [<span data-ttu-id="71213-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="71213-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="71213-147">查询</span><span class="sxs-lookup"><span data-stu-id="71213-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="71213-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="71213-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="71213-149">DataContext 方法（O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="71213-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
