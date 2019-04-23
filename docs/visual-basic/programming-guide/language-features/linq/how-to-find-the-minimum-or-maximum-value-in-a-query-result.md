---
title: 如何：使用 LINQ (Visual Basic 中) 中的查询结果中查找最小值或最大值
ms.date: 07/20/2015
helpviewer_keywords:
- max operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- minimum values [LINQ in Visual Basic]
- min operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], minimum and maximum values
- Max property
- maximum values [LINQ in Visual Basic]
- Aggregate clause [Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 238b763b-7dcd-4b14-8050-b65500a4f71c
ms.openlocfilehash: af5f4bf829664057c40004a842df95d927cc5d71
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337469"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a><span data-ttu-id="3fddc-102">如何：使用 LINQ (Visual Basic 中) 中的查询结果中查找最小值或最大值</span><span class="sxs-lookup"><span data-stu-id="3fddc-102">How to: Find the Minimum or Maximum Value in a Query Result by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="3fddc-103">语言集成查询 (LINQ) 轻松地访问数据库的信息和执行查询。</span><span class="sxs-lookup"><span data-stu-id="3fddc-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="3fddc-104">下面的示例演示如何创建新的应用程序对 SQL Server 数据库执行查询。</span><span class="sxs-lookup"><span data-stu-id="3fddc-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="3fddc-105">该示例使用来确定结果的最小和最大值`Aggregate`和`Group By`子句。</span><span class="sxs-lookup"><span data-stu-id="3fddc-105">The sample determines the minimum and maximum values for the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="3fddc-106">有关详细信息，请参阅[Aggregate 子句](../../../../visual-basic/language-reference/queries/aggregate-clause.md)并[组 By 子句](../../../../visual-basic/language-reference/queries/group-by-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="3fddc-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="3fddc-107">本主题中的示例使用 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="3fddc-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="3fddc-108">如果在开发计算机上没有此数据库，您可以从 Microsoft 下载中心下载它。</span><span class="sxs-lookup"><span data-stu-id="3fddc-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="3fddc-109">有关说明，请参阅[下载示例数据库](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="3fddc-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="3fddc-110">若要创建与数据库的连接</span><span class="sxs-lookup"><span data-stu-id="3fddc-110">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="3fddc-111">在 Visual Studio 中打开**服务器资源管理器**/**数据库资源管理器**通过单击**服务器资源管理器**/**数据库资源管理器**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="3fddc-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="3fddc-112">右键单击**数据连接**中**服务器资源管理器**/**数据库资源管理器**，然后单击**添加连接**。</span><span class="sxs-lookup"><span data-stu-id="3fddc-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="3fddc-113">指定到 Northwind 示例数据库的有效连接。</span><span class="sxs-lookup"><span data-stu-id="3fddc-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="3fddc-114">若要添加包含 LINQ to SQL 文件的项目</span><span class="sxs-lookup"><span data-stu-id="3fddc-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="3fddc-115">在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="3fddc-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="3fddc-116">选择 Visual Basic **Windows 窗体应用程序**作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="3fddc-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="3fddc-117">在 **“项目”** 菜单上，单击 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="3fddc-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="3fddc-118">选择**LINQ to SQL 类**项模板。</span><span class="sxs-lookup"><span data-stu-id="3fddc-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="3fddc-119">为 `northwind.dbml` 文件命名。</span><span class="sxs-lookup"><span data-stu-id="3fddc-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="3fddc-120">单击 **添加**。</span><span class="sxs-lookup"><span data-stu-id="3fddc-120">Click **Add**.</span></span> <span data-ttu-id="3fddc-121">此时，northwind.dbml 文件打开时对象关系设计器 （O/R 设计器）。</span><span class="sxs-lookup"><span data-stu-id="3fddc-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="3fddc-122">若要添加到 O/R 设计器查询的表</span><span class="sxs-lookup"><span data-stu-id="3fddc-122">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="3fddc-123">在中**服务器资源管理器**/**数据库资源管理器**，扩展连接到 Northwind 数据库。</span><span class="sxs-lookup"><span data-stu-id="3fddc-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="3fddc-124">展开**表**文件夹。</span><span class="sxs-lookup"><span data-stu-id="3fddc-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="3fddc-125">如果已关闭 O/R 设计器，您可以通过双击前面添加的 northwind.dbml 文件重新打开它。</span><span class="sxs-lookup"><span data-stu-id="3fddc-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="3fddc-126">单击客户表并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="3fddc-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="3fddc-127">单击订单表并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="3fddc-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="3fddc-128">在设计器创建新`Customer`和`Order`为你的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="3fddc-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="3fddc-129">请注意，在设计器会自动检测表之间的关系并创建子相关对象的属性。</span><span class="sxs-lookup"><span data-stu-id="3fddc-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="3fddc-130">例如，IntelliSense 将显示`Customer`对象具有`Orders`与该客户相关的所有订单的属性。</span><span class="sxs-lookup"><span data-stu-id="3fddc-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="3fddc-131">保存所做的更改并关闭设计器。</span><span class="sxs-lookup"><span data-stu-id="3fddc-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="3fddc-132">保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="3fddc-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="3fddc-133">添加代码以查询数据库并显示结果</span><span class="sxs-lookup"><span data-stu-id="3fddc-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="3fddc-134">从**工具箱**，拖动<xref:System.Windows.Forms.DataGridView>控件拖到你的项目，Form1 的默认 Windows 窗体上。</span><span class="sxs-lookup"><span data-stu-id="3fddc-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="3fddc-135">双击 Form1 以将代码添加到`Load`窗体的事件。</span><span class="sxs-lookup"><span data-stu-id="3fddc-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="3fddc-136">当表添加到 O/R 设计器时，在设计器添加<xref:System.Data.Linq.DataContext>为你的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="3fddc-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="3fddc-137">此对象包含必须具有访问这些表，除了单个对象和集合的每个表的代码。</span><span class="sxs-lookup"><span data-stu-id="3fddc-137">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="3fddc-138"><xref:System.Data.Linq.DataContext>对象将项目命名为根据.dbml 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="3fddc-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="3fddc-139">对于此项目，<xref:System.Data.Linq.DataContext>对象被命名为`northwindDataContext`。</span><span class="sxs-lookup"><span data-stu-id="3fddc-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="3fddc-140">可以创建的实例<xref:System.Data.Linq.DataContext>代码和查询中指定由 O/R 设计器的表。</span><span class="sxs-lookup"><span data-stu-id="3fddc-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="3fddc-141">将以下代码添加到`Load`事件。</span><span class="sxs-lookup"><span data-stu-id="3fddc-141">Add the following code to the `Load` event.</span></span> <span data-ttu-id="3fddc-142">此代码将查询作为数据上下文的属性公开，并确定结果的最小和最大值的表。</span><span class="sxs-lookup"><span data-stu-id="3fddc-142">This code queries the tables that are exposed as properties of your data context and determines the minimum and maximum values for the results.</span></span> <span data-ttu-id="3fddc-143">此示例使用他`Aggregate`到单个结果的查询子句和`Group By`子句以显示为平均值分组结果。</span><span class="sxs-lookup"><span data-stu-id="3fddc-143">The sample uses he `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. <span data-ttu-id="3fddc-144">按 F5 以运行您的项目并查看结果。</span><span class="sxs-lookup"><span data-stu-id="3fddc-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fddc-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="3fddc-145">See also</span></span>

- [<span data-ttu-id="3fddc-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="3fddc-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="3fddc-147">查询</span><span class="sxs-lookup"><span data-stu-id="3fddc-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="3fddc-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="3fddc-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="3fddc-149">DataContext 方法（O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="3fddc-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
