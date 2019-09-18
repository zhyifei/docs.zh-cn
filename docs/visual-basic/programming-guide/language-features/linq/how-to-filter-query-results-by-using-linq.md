---
title: 如何：使用 LINQ 筛选查询结果（Visual Basic）
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
ms.openlocfilehash: 1250f2fe0ccd7661b9bc1986000143ec4a15a9f0
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053280"
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="040d2-102">如何：使用 LINQ 筛选查询结果（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="040d2-102">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="040d2-103">使用语言集成查询（LINQ），可以轻松地访问数据库信息和执行查询。</span><span class="sxs-lookup"><span data-stu-id="040d2-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>

<span data-ttu-id="040d2-104">下面的示例演示如何创建一个新的应用程序，该应用程序对 SQL Server 数据库执行查询，并使用`Where`子句按特定值筛选结果。</span><span class="sxs-lookup"><span data-stu-id="040d2-104">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="040d2-105">有关详细信息，请参阅[Where 子句](../../../../visual-basic/language-reference/queries/where-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="040d2-105">For more information, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>

<span data-ttu-id="040d2-106">本主题中的示例使用 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="040d2-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="040d2-107">如果你的开发计算机上没有此数据库，可以从 Microsoft 下载中心下载它。</span><span class="sxs-lookup"><span data-stu-id="040d2-107">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="040d2-108">有关说明，请参阅[下载示例数据库](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="040d2-108">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="040d2-109">创建与数据库的连接</span><span class="sxs-lookup"><span data-stu-id="040d2-109">To create a connection to a database</span></span>

1. <span data-ttu-id="040d2-110">在 Visual Studio 中，单击 "**视图**" 菜单上的 "**服务器资源管理器**/"**数据库资源管理器**打开**服务器资源管理器**/**数据库资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="040d2-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>

2. <span data-ttu-id="040d2-111">右键单击**服务器资源管理器**/**数据库资源管理器**中的 "**数据连接**"，然后单击 "**添加连接**"。</span><span class="sxs-lookup"><span data-stu-id="040d2-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>

3. <span data-ttu-id="040d2-112">指定与 Northwind 示例数据库的有效连接。</span><span class="sxs-lookup"><span data-stu-id="040d2-112">Specify a valid connection to the Northwind sample database.</span></span>

## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="040d2-113">添加包含 LINQ to SQL 文件的项目</span><span class="sxs-lookup"><span data-stu-id="040d2-113">To add a project that contains a LINQ to SQL file</span></span>

1. <span data-ttu-id="040d2-114">在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="040d2-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="040d2-115">选择 Visual Basic **Windows 窗体应用程序**作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="040d2-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>

2. <span data-ttu-id="040d2-116">在 **“项目”** 菜单上，单击 **“添加新项”** 。</span><span class="sxs-lookup"><span data-stu-id="040d2-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="040d2-117">选择 " **LINQ to SQL 类**" 项模板。</span><span class="sxs-lookup"><span data-stu-id="040d2-117">Select the **LINQ to SQL Classes** item template.</span></span>

3. <span data-ttu-id="040d2-118">为 `northwind.dbml` 文件命名。</span><span class="sxs-lookup"><span data-stu-id="040d2-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="040d2-119">单击 **添加**。</span><span class="sxs-lookup"><span data-stu-id="040d2-119">Click **Add**.</span></span> <span data-ttu-id="040d2-120">将为 northwind 文件打开对象关系设计器（O/R 设计器）。</span><span class="sxs-lookup"><span data-stu-id="040d2-120">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>

## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="040d2-121">添加要查询到 O/R 设计器的表</span><span class="sxs-lookup"><span data-stu-id="040d2-121">To add tables to query to the O/R Designer</span></span>

1. <span data-ttu-id="040d2-122">在**服务器资源管理器**/**数据库资源管理器**中，展开与 Northwind 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="040d2-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="040d2-123">展开 "**表**" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="040d2-123">Expand the **Tables** folder.</span></span>

     <span data-ttu-id="040d2-124">如果关闭了 O/R 设计器，则可以通过双击先前添加的 northwind 文件来重新打开它。</span><span class="sxs-lookup"><span data-stu-id="040d2-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>

2. <span data-ttu-id="040d2-125">单击 "Customers" 表，并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="040d2-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="040d2-126">单击 "Orders" 表，并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="040d2-126">Click the Orders table and drag it to the left pane of the designer.</span></span>

     <span data-ttu-id="040d2-127">设计器将为`Customer`您`Order`的项目创建新的和对象。</span><span class="sxs-lookup"><span data-stu-id="040d2-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="040d2-128">请注意，设计器将自动检测表之间的关系，并创建相关对象的子属性。</span><span class="sxs-lookup"><span data-stu-id="040d2-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="040d2-129">例如，IntelliSense 将显示`Customer`对象`Orders`具有与该客户相关的所有订单的属性。</span><span class="sxs-lookup"><span data-stu-id="040d2-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>

3. <span data-ttu-id="040d2-130">保存更改并关闭设计器。</span><span class="sxs-lookup"><span data-stu-id="040d2-130">Save your changes and close the designer.</span></span>

4. <span data-ttu-id="040d2-131">保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="040d2-131">Save your project.</span></span>

## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="040d2-132">添加代码以查询数据库并显示结果</span><span class="sxs-lookup"><span data-stu-id="040d2-132">To add code to query the database and display the results</span></span>

1. <span data-ttu-id="040d2-133">从 "**工具箱**" 中， <xref:System.Windows.Forms.DataGridView>将控件拖动到项目的默认 Windows 窗体 "Form1"。</span><span class="sxs-lookup"><span data-stu-id="040d2-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>

2. <span data-ttu-id="040d2-134">双击 "Form1" `Load` ，将代码添加到窗体的事件中。</span><span class="sxs-lookup"><span data-stu-id="040d2-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>

3. <span data-ttu-id="040d2-135">在将表添加到 O/R 设计器后，设计器将<xref:System.Data.Linq.DataContext>为您的项目添加一个对象。</span><span class="sxs-lookup"><span data-stu-id="040d2-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="040d2-136">除每个表的单个对象和集合外，此对象还包含访问这些表所需的代码。</span><span class="sxs-lookup"><span data-stu-id="040d2-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="040d2-137">项目<xref:System.Data.Linq.DataContext>的对象根据 .dbml 文件的名称进行命名。</span><span class="sxs-lookup"><span data-stu-id="040d2-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="040d2-138">对于此项目，该<xref:System.Data.Linq.DataContext>对象的名称`northwindDataContext`为。</span><span class="sxs-lookup"><span data-stu-id="040d2-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>

    <span data-ttu-id="040d2-139">您可以在代码中创建的<xref:System.Data.Linq.DataContext>一个实例，并查询由 O/R 设计器指定的表。</span><span class="sxs-lookup"><span data-stu-id="040d2-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>

    <span data-ttu-id="040d2-140">将以下代码添加到`Load`事件，以查询作为数据上下文的属性公开的表。</span><span class="sxs-lookup"><span data-stu-id="040d2-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="040d2-141">查询对结果进行筛选，并仅返回位于中`London`的客户。</span><span class="sxs-lookup"><span data-stu-id="040d2-141">The query filters the results and returns only customers that are located in `London`.</span></span>

    [!code-vb[VbLINQToSQLHowTos#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#11)]

4. <span data-ttu-id="040d2-142">按 F5 运行项目并查看结果。</span><span class="sxs-lookup"><span data-stu-id="040d2-142">Press F5 to run your project and view the results.</span></span>

5. <span data-ttu-id="040d2-143">下面是可以尝试的一些其他筛选器。</span><span class="sxs-lookup"><span data-stu-id="040d2-143">Following are some other filters that you can try.</span></span>

    [!code-vb[VbLINQToSQLHowTos#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#12)]

## <a name="see-also"></a><span data-ttu-id="040d2-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="040d2-144">See also</span></span>

- [<span data-ttu-id="040d2-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="040d2-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="040d2-146">查询</span><span class="sxs-lookup"><span data-stu-id="040d2-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="040d2-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="040d2-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="040d2-148">DataContext 方法（O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="040d2-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
