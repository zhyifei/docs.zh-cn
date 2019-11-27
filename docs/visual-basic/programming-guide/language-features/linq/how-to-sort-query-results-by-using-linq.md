---
title: 如何：使用 LINQ 对查询结果进行排序
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
ms.openlocfilehash: 020e4a3800515329b29e2941baf50d3d8add4605
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354170"
---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="47e64-102">如何：使用 LINQ 排序查询结果 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47e64-102">How to: Sort Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="47e64-103">使用语言集成查询（LINQ），可以轻松地访问数据库信息和执行查询。</span><span class="sxs-lookup"><span data-stu-id="47e64-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="47e64-104">下面的示例演示如何创建一个新的应用程序，该应用程序对 SQL Server 数据库执行查询，并通过使用 `Order By` 子句按多个字段对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="47e64-104">The following example shows how to create a new application that performs queries against a SQL Server database and sorts the results by multiple fields by using the `Order By` clause.</span></span> <span data-ttu-id="47e64-105">每个字段的排序顺序可以是升序或降序。</span><span class="sxs-lookup"><span data-stu-id="47e64-105">The sort order for each field can be ascending order or descending order.</span></span> <span data-ttu-id="47e64-106">有关详细信息，请参阅[Order By 子句](../../../../visual-basic/language-reference/queries/order-by-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="47e64-106">For more information, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="47e64-107">本主题中的示例使用 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="47e64-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="47e64-108">如果你的开发计算机上没有此数据库，可以从 Microsoft 下载中心进行下载。</span><span class="sxs-lookup"><span data-stu-id="47e64-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="47e64-109">有关说明，请参阅[下载示例数据库](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="47e64-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="47e64-110">创建与数据库的连接</span><span class="sxs-lookup"><span data-stu-id="47e64-110">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="47e64-111">在 Visual Studio 中，通过单击 "**视图**"**菜单上的** **服务器资源管理器**/数据库资源管理器来打开**服务器资源管理器**/**数据库资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="47e64-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="47e64-112">右键单击**服务器资源管理器**/**数据库资源管理器**中的 "**数据连接**"，然后单击 "**添加连接**"。</span><span class="sxs-lookup"><span data-stu-id="47e64-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="47e64-113">指定与 Northwind 示例数据库的有效连接。</span><span class="sxs-lookup"><span data-stu-id="47e64-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="47e64-114">添加包含 LINQ to SQL 文件的项目</span><span class="sxs-lookup"><span data-stu-id="47e64-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="47e64-115">在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="47e64-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="47e64-116">选择 Visual Basic **Windows 窗体应用程序**作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="47e64-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="47e64-117">在 **“项目”** 菜单上，单击 **“添加新项”** 。</span><span class="sxs-lookup"><span data-stu-id="47e64-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="47e64-118">选择 " **LINQ to SQL 类**" 项模板。</span><span class="sxs-lookup"><span data-stu-id="47e64-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="47e64-119">为 `northwind.dbml` 文件命名。</span><span class="sxs-lookup"><span data-stu-id="47e64-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="47e64-120">单击 **“添加”** 。</span><span class="sxs-lookup"><span data-stu-id="47e64-120">Click **Add**.</span></span> <span data-ttu-id="47e64-121">为 northwind 文件打开对象关系设计器（O/R 设计器）。</span><span class="sxs-lookup"><span data-stu-id="47e64-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="47e64-122">添加要查询到 O/R 设计器的表</span><span class="sxs-lookup"><span data-stu-id="47e64-122">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="47e64-123">在**服务器资源管理器**/**数据库资源管理器**中，展开与 Northwind 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="47e64-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="47e64-124">展开 "**表**" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="47e64-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="47e64-125">如果关闭了 O/R 设计器，则可以通过双击先前添加的 northwind 文件来重新打开它。</span><span class="sxs-lookup"><span data-stu-id="47e64-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="47e64-126">单击 "Customers" 表，并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="47e64-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="47e64-127">单击 "Orders" 表，并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="47e64-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="47e64-128">设计器将为您的项目创建新的 `Customer` 和 `Order` 对象。</span><span class="sxs-lookup"><span data-stu-id="47e64-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="47e64-129">请注意，设计器将自动检测表之间的关系，并创建相关对象的子属性。</span><span class="sxs-lookup"><span data-stu-id="47e64-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="47e64-130">例如，IntelliSense 将显示 `Customer` 对象具有与该客户相关的所有订单的 `Orders` 属性。</span><span class="sxs-lookup"><span data-stu-id="47e64-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="47e64-131">保存更改并关闭设计器。</span><span class="sxs-lookup"><span data-stu-id="47e64-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="47e64-132">保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="47e64-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="47e64-133">添加代码以查询数据库并显示结果</span><span class="sxs-lookup"><span data-stu-id="47e64-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="47e64-134">从 "**工具箱**" 中，将 "<xref:System.Windows.Forms.DataGridView>" 控件拖动到项目的默认 Windows 窗体 "Form1"。</span><span class="sxs-lookup"><span data-stu-id="47e64-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="47e64-135">双击 "Form1"，将代码添加到窗体的 `Load` 事件。</span><span class="sxs-lookup"><span data-stu-id="47e64-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="47e64-136">将表添加到 O/R 设计器后，设计器会将 <xref:System.Data.Linq.DataContext> 对象添加到项目。</span><span class="sxs-lookup"><span data-stu-id="47e64-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="47e64-137">此对象包含访问这些表所需的代码，以及访问每个表的单个对象和集合的代码。</span><span class="sxs-lookup"><span data-stu-id="47e64-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="47e64-138">项目的 <xref:System.Data.Linq.DataContext> 对象根据 .dbml 文件的名称进行命名。</span><span class="sxs-lookup"><span data-stu-id="47e64-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="47e64-139">对于此项目，<xref:System.Data.Linq.DataContext> 对象名为 `northwindDataContext`。</span><span class="sxs-lookup"><span data-stu-id="47e64-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="47e64-140">您可以在代码中创建 <xref:System.Data.Linq.DataContext> 的实例，并查询由 O/R 设计器指定的表。</span><span class="sxs-lookup"><span data-stu-id="47e64-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="47e64-141">将以下代码添加到 `Load` 事件，以查询作为数据上下文的属性公开的表并对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="47e64-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context and sort the results.</span></span> <span data-ttu-id="47e64-142">查询按客户订单数对结果进行排序，并按降序排列。</span><span class="sxs-lookup"><span data-stu-id="47e64-142">The query sorts the results by the number of customer orders, in descending order.</span></span> <span data-ttu-id="47e64-143">具有相同订单数的客户按公司名称升序排序（默认值）。</span><span class="sxs-lookup"><span data-stu-id="47e64-143">Customers that have the same number of orders are ordered by company name in ascending order (the default).</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form4.vb#10)]  
  
4. <span data-ttu-id="47e64-144">按 F5 运行项目并查看结果。</span><span class="sxs-lookup"><span data-stu-id="47e64-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47e64-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47e64-145">See also</span></span>

- [<span data-ttu-id="47e64-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="47e64-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="47e64-147">查询</span><span class="sxs-lookup"><span data-stu-id="47e64-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="47e64-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="47e64-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="47e64-149">DataContext 方法（O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="47e64-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
