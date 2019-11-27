---
title: 如何：使用 LINQ 查询数据库
ms.date: 07/20/2015
helpviewer_keywords:
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
ms.openlocfilehash: f4b2510bad2b23d7a0e179383b34c4e425e6564e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344961"
---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="fd9b5-102">如何：使用 LINQ 查询数据库 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd9b5-102">How to: Query a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="fd9b5-103">使用语言集成查询（LINQ），可以轻松地访问数据库信息和执行查询。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="fd9b5-104">下面的示例演示如何创建一个新应用程序，用于对 SQL Server 数据库执行查询。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="fd9b5-105">本主题中的示例使用 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="fd9b5-106">如果你的开发计算机上没有此数据库，可以从 Microsoft 下载中心进行下载。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="fd9b5-107">有关说明，请参阅[下载示例数据库](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="fd9b5-108">创建与数据库的连接</span><span class="sxs-lookup"><span data-stu-id="fd9b5-108">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="fd9b5-109">在 Visual Studio 中，通过单击 "**视图**"**菜单上的** **服务器资源管理器**/数据库资源管理器来打开**服务器资源管理器**/**数据库资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="fd9b5-110">右键单击**服务器资源管理器**/**数据库资源管理器**中的 "**数据连接**"，然后单击 "**添加连接**"。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="fd9b5-111">指定与 Northwind 示例数据库的有效连接。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="fd9b5-112">添加包含 LINQ to SQL 文件的项目</span><span class="sxs-lookup"><span data-stu-id="fd9b5-112">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="fd9b5-113">在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="fd9b5-114">选择 Visual Basic **Windows 窗体应用程序**作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="fd9b5-115">在 **“项目”** 菜单上，单击 **“添加新项”** 。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="fd9b5-116">选择 " **LINQ to SQL 类**" 项模板。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="fd9b5-117">为 `northwind.dbml` 文件命名。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="fd9b5-118">单击 **“添加”** 。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-118">Click **Add**.</span></span> <span data-ttu-id="fd9b5-119">为 northwind 文件打开对象关系设计器（O/R 设计器）。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-119">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="fd9b5-120">添加要查询到 O/R 设计器的表</span><span class="sxs-lookup"><span data-stu-id="fd9b5-120">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="fd9b5-121">在**服务器资源管理器**/**数据库资源管理器**中，展开与 Northwind 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="fd9b5-122">展开 "**表**" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="fd9b5-123">如果关闭了 O/R 设计器，则可以通过双击先前添加的 northwind 文件来重新打开它。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-123">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="fd9b5-124">单击 "Customers" 表，并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-124">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="fd9b5-125">单击 "Orders" 表，并将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-125">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="fd9b5-126">设计器将为您的项目创建新的 `Customer` 和 `Order` 对象。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-126">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="fd9b5-127">请注意，设计器将自动检测表之间的关系，并创建相关对象的子属性。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-127">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="fd9b5-128">例如，IntelliSense 将显示 `Customer` 对象具有与该客户相关的所有订单的 `Orders` 属性。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-128">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="fd9b5-129">保存更改并关闭设计器。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-129">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="fd9b5-130">保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-130">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="fd9b5-131">添加代码以查询数据库并显示结果</span><span class="sxs-lookup"><span data-stu-id="fd9b5-131">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="fd9b5-132">从 "**工具箱**" 中，将 "<xref:System.Windows.Forms.DataGridView>" 控件拖动到项目的默认 Windows 窗体 "Form1"。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="fd9b5-133">双击 "Form1"，将代码添加到窗体的 `Load` 事件。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-133">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="fd9b5-134">在将表添加到 O/R 设计器后，设计器将为您的项目添加 <xref:System.Data.Linq.DataContext> 对象。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-134">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="fd9b5-135">除每个表的单个对象和集合外，此对象还包含访问这些表所需的代码。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-135">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="fd9b5-136">项目的 <xref:System.Data.Linq.DataContext> 对象根据 .dbml 文件的名称进行命名。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-136">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="fd9b5-137">对于此项目，<xref:System.Data.Linq.DataContext> 对象名为 `northwindDataContext`。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="fd9b5-138">您可以在代码中创建 <xref:System.Data.Linq.DataContext> 的实例，并查询由 O/R 设计器指定的表。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="fd9b5-139">将以下代码添加到 `Load` 事件以查询作为数据上下文的属性公开的表。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-139">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#3)]  
  
4. <span data-ttu-id="fd9b5-140">按 F5 运行项目并查看结果。</span><span class="sxs-lookup"><span data-stu-id="fd9b5-140">Press F5 to run your project and view the results.</span></span>  
  
5. <span data-ttu-id="fd9b5-141">下面是一些可以尝试执行的其他查询：</span><span class="sxs-lookup"><span data-stu-id="fd9b5-141">Following are some additional queries that you can try:</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#4)]  
    [!code-vb[VbLINQToSQLHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="fd9b5-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd9b5-142">See also</span></span>

- [<span data-ttu-id="fd9b5-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="fd9b5-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="fd9b5-144">查询</span><span class="sxs-lookup"><span data-stu-id="fd9b5-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="fd9b5-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="fd9b5-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="fd9b5-146">DataContext 方法（O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="fd9b5-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
