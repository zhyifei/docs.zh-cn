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
ms.openlocfilehash: ef5f218cdcc7275f616486110825ad0b9df11cc3
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112357"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a><span data-ttu-id="e7e14-102">如何：使用 LINQ 查找查询结果中的最小值或最大值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7e14-102">How to: Find the Minimum or Maximum Value in a Query Result by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="e7e14-103">语言集成查询 （LINQ） 使访问数据库信息和执行查询变得容易。</span><span class="sxs-lookup"><span data-stu-id="e7e14-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="e7e14-104">下面的示例演示如何创建执行针对 SQL Server 数据库的查询的新应用程序。</span><span class="sxs-lookup"><span data-stu-id="e7e14-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="e7e14-105">该示例通过使用`Aggregate`和`Group By`子句确定结果的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="e7e14-105">The sample determines the minimum and maximum values for the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="e7e14-106">有关详细信息，请参阅[聚合子句](../../../../visual-basic/language-reference/queries/aggregate-clause.md)和[按子句分组](../../../../visual-basic/language-reference/queries/group-by-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="e7e14-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="e7e14-107">本主题中的示例使用北风示例数据库。</span><span class="sxs-lookup"><span data-stu-id="e7e14-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="e7e14-108">如果你的开发计算机上没有此数据库，可以从 Microsoft 下载中心进行下载。</span><span class="sxs-lookup"><span data-stu-id="e7e14-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="e7e14-109">有关说明，请参阅[下载示例数据库](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="e7e14-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="create-a-connection-to-a-database"></a><span data-ttu-id="e7e14-110">创建与数据库的连接</span><span class="sxs-lookup"><span data-stu-id="e7e14-110">Create a connection to a database</span></span>  
  
1. <span data-ttu-id="e7e14-111">在可视化工作室中，通过单击 **"视图"** 菜单上**的服务器资源管理器**/**数据库资源管理器**打开**服务器资源管理器**/**数据库资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="e7e14-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="e7e14-112">右键单击**服务器资源管理器**/**数据库资源管理器**中**的数据连接**，然后单击"**添加连接**"。</span><span class="sxs-lookup"><span data-stu-id="e7e14-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="e7e14-113">指定到北风样本数据库的有效连接。</span><span class="sxs-lookup"><span data-stu-id="e7e14-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="e7e14-114">将包含 LINQ 的项目添加到 SQL 文件</span><span class="sxs-lookup"><span data-stu-id="e7e14-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="e7e14-115">在可视化工作室中，在 **"文件"** 菜单上，指向 **"新建"，** 然后单击"**项目**"。</span><span class="sxs-lookup"><span data-stu-id="e7e14-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="e7e14-116">选择可视化基本**窗口窗体应用程序**作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="e7e14-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="e7e14-117">在 **“项目”** 菜单上，单击 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="e7e14-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="e7e14-118">选择**LINQ 到 SQL 类**项模板。</span><span class="sxs-lookup"><span data-stu-id="e7e14-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="e7e14-119">将该文件命名为 `northwind.dbml`。</span><span class="sxs-lookup"><span data-stu-id="e7e14-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="e7e14-120">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="e7e14-120">Click **Add**.</span></span> <span data-ttu-id="e7e14-121">为北风.dbml 文件打开对象关系设计器（O/R 设计器）。</span><span class="sxs-lookup"><span data-stu-id="e7e14-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="e7e14-122">将表添加到 O/R 设计器</span><span class="sxs-lookup"><span data-stu-id="e7e14-122">Add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="e7e14-123">在**服务器资源管理器**/**数据库资源管理器中**，展开与北风数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="e7e14-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="e7e14-124">展开 **“表”** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="e7e14-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="e7e14-125">如果已关闭 O/R 设计器，则可以通过双击之前添加的 Northwind.dbml 文件重新打开它。</span><span class="sxs-lookup"><span data-stu-id="e7e14-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="e7e14-126">单击"客户"表并将其拖动到设计器的左侧窗格。</span><span class="sxs-lookup"><span data-stu-id="e7e14-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="e7e14-127">单击"订单"表并将其拖动到设计器的左侧窗格。</span><span class="sxs-lookup"><span data-stu-id="e7e14-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="e7e14-128">设计器为项目`Customer`创建新`Order`对象和对象。</span><span class="sxs-lookup"><span data-stu-id="e7e14-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="e7e14-129">请注意，设计器会自动检测表之间的关系，并为相关对象创建子属性。</span><span class="sxs-lookup"><span data-stu-id="e7e14-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="e7e14-130">例如，IntelliSense 将显示`Customer`该对象具有与该客户`Orders`相关的所有订单的属性。</span><span class="sxs-lookup"><span data-stu-id="e7e14-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="e7e14-131">保存更改并关闭设计器。</span><span class="sxs-lookup"><span data-stu-id="e7e14-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="e7e14-132">保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="e7e14-132">Save your project.</span></span>  
  
## <a name="add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="e7e14-133">添加代码以查询数据库并显示结果</span><span class="sxs-lookup"><span data-stu-id="e7e14-133">Add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="e7e14-134">从**工具箱**中<xref:System.Windows.Forms.DataGridView>，将控件拖动到项目的默认 Windows 窗体窗体 Form1。</span><span class="sxs-lookup"><span data-stu-id="e7e14-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="e7e14-135">双击 Form1 可向窗体`Load`的事件添加代码。</span><span class="sxs-lookup"><span data-stu-id="e7e14-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="e7e14-136">将表添加到 O/R 设计器时，设计器会<xref:System.Data.Linq.DataContext>为项目添加对象。</span><span class="sxs-lookup"><span data-stu-id="e7e14-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="e7e14-137">除了每个表的各个对象和集合之外，此对象还包含访问这些表必须具有的代码。</span><span class="sxs-lookup"><span data-stu-id="e7e14-137">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="e7e14-138">项目<xref:System.Data.Linq.DataContext>的对象是根据 .dbml 文件的名称命名的。</span><span class="sxs-lookup"><span data-stu-id="e7e14-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="e7e14-139">对于此项目，<xref:System.Data.Linq.DataContext>对象名为`northwindDataContext`。</span><span class="sxs-lookup"><span data-stu-id="e7e14-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="e7e14-140">您可以在代码中创建 的<xref:System.Data.Linq.DataContext>实例，并查询 O/R 设计器指定的表。</span><span class="sxs-lookup"><span data-stu-id="e7e14-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="e7e14-141">将以下代码添加到事件`Load`。</span><span class="sxs-lookup"><span data-stu-id="e7e14-141">Add the following code to the `Load` event.</span></span> <span data-ttu-id="e7e14-142">此代码查询作为数据上下文的属性公开的表，并确定结果的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="e7e14-142">This code queries the tables that are exposed as properties of your data context and determines the minimum and maximum values for the results.</span></span> <span data-ttu-id="e7e14-143">该示例使用`Aggregate`子句查询单个结果，`Group By`子句显示分组结果的平均值。</span><span class="sxs-lookup"><span data-stu-id="e7e14-143">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. <span data-ttu-id="e7e14-144">按**F5**运行项目并查看结果。</span><span class="sxs-lookup"><span data-stu-id="e7e14-144">Press **F5** to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7e14-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7e14-145">See also</span></span>

- [<span data-ttu-id="e7e14-146">Linq</span><span class="sxs-lookup"><span data-stu-id="e7e14-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="e7e14-147">查询</span><span class="sxs-lookup"><span data-stu-id="e7e14-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="e7e14-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e7e14-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="e7e14-149">DataContext 方法（O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="e7e14-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
