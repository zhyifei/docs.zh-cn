---
title: 如何：使用 LINQ 查找查询结果中的最小值或最大值
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
ms.openlocfilehash: bddb90baa0b01fd9d724583b472af9f9fa7569e5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344970"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a><span data-ttu-id="fef43-102">如何：使用 LINQ 查找查询结果中的最小值或最大值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fef43-102">How to: Find the Minimum or Maximum Value in a Query Result by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="fef43-103">使用语言集成查询（LINQ），可以轻松地访问数据库信息和执行查询。</span><span class="sxs-lookup"><span data-stu-id="fef43-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="fef43-104">下面的示例演示如何创建一个新应用程序，用于对 SQL Server 数据库执行查询。</span><span class="sxs-lookup"><span data-stu-id="fef43-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="fef43-105">该示例通过使用 `Aggregate` 和 `Group By` 子句来确定结果的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="fef43-105">The sample determines the minimum and maximum values for the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="fef43-106">有关详细信息，请参阅[Aggregate 子句](../../../../visual-basic/language-reference/queries/aggregate-clause.md)和[Group By 子句](../../../../visual-basic/language-reference/queries/group-by-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="fef43-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="fef43-107">本主题中的示例使用 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="fef43-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="fef43-108">如果你的开发计算机上没有此数据库，可以从 Microsoft 下载中心进行下载。</span><span class="sxs-lookup"><span data-stu-id="fef43-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="fef43-109">有关说明，请参阅[下载示例数据库](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="fef43-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="fef43-110">创建与数据库的连接</span><span class="sxs-lookup"><span data-stu-id="fef43-110">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="fef43-111">在 Visual Studio 中，通过单击 "**视图**"**菜单上的** **服务器资源管理器**/数据库资源管理器来打开**服务器资源管理器**/**数据库资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="fef43-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="fef43-112">右键单击**服务器资源管理器**/**数据库资源管理器**中的 "**数据连接**"，然后单击 "**添加连接**"。</span><span class="sxs-lookup"><span data-stu-id="fef43-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="fef43-113">指定与 Northwind 示例数据库的有效连接。</span><span class="sxs-lookup"><span data-stu-id="fef43-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="fef43-114">添加包含 LINQ to SQL 文件的项目</span><span class="sxs-lookup"><span data-stu-id="fef43-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="fef43-115">在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="fef43-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="fef43-116">选择 Visual Basic **Windows 窗体应用程序**作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="fef43-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="fef43-117">在 **“项目”** 菜单上，单击 **“添加新项”** 。</span><span class="sxs-lookup"><span data-stu-id="fef43-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="fef43-118">选择 " **LINQ to SQL 类**" 项模板。</span><span class="sxs-lookup"><span data-stu-id="fef43-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="fef43-119">为 `northwind.dbml` 文件命名。</span><span class="sxs-lookup"><span data-stu-id="fef43-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="fef43-120">单击 **“添加”** 。</span><span class="sxs-lookup"><span data-stu-id="fef43-120">Click **Add**.</span></span> <span data-ttu-id="fef43-121">为 northwind 文件打开对象关系设计器（O/R 设计器）。</span><span class="sxs-lookup"><span data-stu-id="fef43-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="fef43-122">添加要查询到 O/R 设计器的表</span><span class="sxs-lookup"><span data-stu-id="fef43-122">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="fef43-123">在**服务器资源管理器**/**数据库资源管理器**中，展开与 Northwind 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="fef43-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="fef43-124">展开 "**表**" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="fef43-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="fef43-125">如果关闭了 O/R 设计器，则可以通过双击先前添加的 northwind 文件来重新打开它。</span><span class="sxs-lookup"><span data-stu-id="fef43-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="fef43-126">单击 "Customers" 表，并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="fef43-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="fef43-127">单击 "Orders" 表，并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="fef43-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="fef43-128">设计器将为您的项目创建新的 `Customer` 和 `Order` 对象。</span><span class="sxs-lookup"><span data-stu-id="fef43-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="fef43-129">请注意，设计器将自动检测表之间的关系，并创建相关对象的子属性。</span><span class="sxs-lookup"><span data-stu-id="fef43-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="fef43-130">例如，IntelliSense 将显示 `Customer` 对象具有与该客户相关的所有订单的 `Orders` 属性。</span><span class="sxs-lookup"><span data-stu-id="fef43-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="fef43-131">保存更改并关闭设计器。</span><span class="sxs-lookup"><span data-stu-id="fef43-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="fef43-132">保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="fef43-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="fef43-133">添加代码以查询数据库并显示结果</span><span class="sxs-lookup"><span data-stu-id="fef43-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="fef43-134">从 "**工具箱**" 中，将 "<xref:System.Windows.Forms.DataGridView>" 控件拖动到项目的默认 Windows 窗体 "Form1"。</span><span class="sxs-lookup"><span data-stu-id="fef43-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="fef43-135">双击 "Form1"，将代码添加到窗体的 `Load` 事件。</span><span class="sxs-lookup"><span data-stu-id="fef43-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="fef43-136">在将表添加到 O/R 设计器后，设计器将为您的项目添加 <xref:System.Data.Linq.DataContext> 对象。</span><span class="sxs-lookup"><span data-stu-id="fef43-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="fef43-137">除每个表的单个对象和集合外，此对象还包含访问这些表所需的代码。</span><span class="sxs-lookup"><span data-stu-id="fef43-137">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="fef43-138">项目的 <xref:System.Data.Linq.DataContext> 对象根据 .dbml 文件的名称进行命名。</span><span class="sxs-lookup"><span data-stu-id="fef43-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="fef43-139">对于此项目，<xref:System.Data.Linq.DataContext> 对象名为 `northwindDataContext`。</span><span class="sxs-lookup"><span data-stu-id="fef43-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="fef43-140">您可以在代码中创建 <xref:System.Data.Linq.DataContext> 的实例，并查询由 O/R 设计器指定的表。</span><span class="sxs-lookup"><span data-stu-id="fef43-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="fef43-141">将以下代码添加到 `Load` 事件。</span><span class="sxs-lookup"><span data-stu-id="fef43-141">Add the following code to the `Load` event.</span></span> <span data-ttu-id="fef43-142">此代码查询作为数据上下文的属性公开的表，并确定结果的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="fef43-142">This code queries the tables that are exposed as properties of your data context and determines the minimum and maximum values for the results.</span></span> <span data-ttu-id="fef43-143">该示例使用 he `Aggregate` 子句来查询单个结果，并使用 `Group By` 子句来显示分组结果的平均值。</span><span class="sxs-lookup"><span data-stu-id="fef43-143">The sample uses he `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. <span data-ttu-id="fef43-144">按 F5 运行项目并查看结果。</span><span class="sxs-lookup"><span data-stu-id="fef43-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fef43-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fef43-145">See also</span></span>

- [<span data-ttu-id="fef43-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="fef43-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="fef43-147">查询</span><span class="sxs-lookup"><span data-stu-id="fef43-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="fef43-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="fef43-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="fef43-149">DataContext 方法（O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="fef43-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
