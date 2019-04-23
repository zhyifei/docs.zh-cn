---
title: 如何：使用 LINQ (Visual Basic 中) 调用存储的过程
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: af25ebe10681ebb1c346f90afc0291e53224833a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59319568"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="a62da-102">如何：使用 LINQ (Visual Basic 中) 调用存储的过程</span><span class="sxs-lookup"><span data-stu-id="a62da-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="a62da-103">语言集成查询 (LINQ)，使得可以轻松地访问数据库的信息，包括数据库对象，如存储过程。</span><span class="sxs-lookup"><span data-stu-id="a62da-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="a62da-104">下面的示例演示如何创建 SQL Server 数据库中调用存储的过程的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a62da-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="a62da-105">此示例演示如何调用数据库中的两个不同的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="a62da-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="a62da-106">每个过程返回查询的结果。</span><span class="sxs-lookup"><span data-stu-id="a62da-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="a62da-107">一个过程将输入的参数，而其他过程不使用参数。</span><span class="sxs-lookup"><span data-stu-id="a62da-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="a62da-108">本主题中的示例使用 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="a62da-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="a62da-109">如果在开发计算机上没有此数据库，您可以从 Microsoft 下载中心下载它。</span><span class="sxs-lookup"><span data-stu-id="a62da-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="a62da-110">有关说明，请参阅[下载示例数据库](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="a62da-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="a62da-111">若要创建与数据库的连接</span><span class="sxs-lookup"><span data-stu-id="a62da-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="a62da-112">在 Visual Studio 中打开**服务器资源管理器**/**数据库资源管理器**通过单击**服务器资源管理器**/**数据库资源管理器**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="a62da-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="a62da-113">右键单击**数据连接**中**服务器资源管理器**/**数据库资源管理器**，然后单击**添加连接**。</span><span class="sxs-lookup"><span data-stu-id="a62da-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="a62da-114">指定到 Northwind 示例数据库的有效连接。</span><span class="sxs-lookup"><span data-stu-id="a62da-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="a62da-115">若要添加包含 LINQ to SQL 文件的项目</span><span class="sxs-lookup"><span data-stu-id="a62da-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="a62da-116">在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="a62da-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="a62da-117">选择 Visual Basic **Windows 窗体应用程序**作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="a62da-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="a62da-118">在 **“项目”** 菜单上，单击 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="a62da-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="a62da-119">选择**LINQ to SQL 类**项模板。</span><span class="sxs-lookup"><span data-stu-id="a62da-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="a62da-120">为 `northwind.dbml` 文件命名。</span><span class="sxs-lookup"><span data-stu-id="a62da-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="a62da-121">单击 **添加**。</span><span class="sxs-lookup"><span data-stu-id="a62da-121">Click **Add**.</span></span> <span data-ttu-id="a62da-122">此时，northwind.dbml 文件打开时对象关系设计器 （O/R 设计器）。</span><span class="sxs-lookup"><span data-stu-id="a62da-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="a62da-123">若要将存储的过程添加到 O/R 设计器</span><span class="sxs-lookup"><span data-stu-id="a62da-123">To add stored procedures to the O/R Designer</span></span>  
  
1. <span data-ttu-id="a62da-124">在中**服务器资源管理器**/**数据库资源管理器**，扩展连接到 Northwind 数据库。</span><span class="sxs-lookup"><span data-stu-id="a62da-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="a62da-125">展开**存储过程**文件夹。</span><span class="sxs-lookup"><span data-stu-id="a62da-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="a62da-126">如果已关闭 O/R 设计器，您可以通过双击前面添加的 northwind.dbml 文件重新打开它。</span><span class="sxs-lookup"><span data-stu-id="a62da-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="a62da-127">单击**基于年份的销售额**存储过程并将其拖到设计器的右窗格中。</span><span class="sxs-lookup"><span data-stu-id="a62da-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="a62da-128">单击**Ten Most Expensive Products**存储的过程将将其拖到设计器的右窗格中。</span><span class="sxs-lookup"><span data-stu-id="a62da-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3. <span data-ttu-id="a62da-129">保存所做的更改并关闭设计器。</span><span class="sxs-lookup"><span data-stu-id="a62da-129">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="a62da-130">保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="a62da-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="a62da-131">若要添加代码以显示存储过程的结果</span><span class="sxs-lookup"><span data-stu-id="a62da-131">To add code to display the results of the stored procedures</span></span>  
  
1. <span data-ttu-id="a62da-132">从**工具箱**，拖动<xref:System.Windows.Forms.DataGridView>控件拖到你的项目，Form1 的默认 Windows 窗体上。</span><span class="sxs-lookup"><span data-stu-id="a62da-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="a62da-133">双击 Form1 以将代码添加到其`Load`事件。</span><span class="sxs-lookup"><span data-stu-id="a62da-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3. <span data-ttu-id="a62da-134">当存储的过程添加到 O/R 设计器中时，在设计器添加<xref:System.Data.Linq.DataContext>为你的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="a62da-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="a62da-135">此对象包含必须具有访问这些过程的代码。</span><span class="sxs-lookup"><span data-stu-id="a62da-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="a62da-136"><xref:System.Data.Linq.DataContext>对象项目命名为根据.dbml 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="a62da-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="a62da-137">对于此项目，<xref:System.Data.Linq.DataContext>对象被命名为`northwindDataContext`。</span><span class="sxs-lookup"><span data-stu-id="a62da-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="a62da-138">可以创建的实例<xref:System.Data.Linq.DataContext>O/R 设计器中，代码并调用指定的存储的过程方法。</span><span class="sxs-lookup"><span data-stu-id="a62da-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="a62da-139">若要将绑定到<xref:System.Windows.Forms.DataGridView>对象，你可能必须强制查询立即执行通过调用<xref:System.Linq.Enumerable.ToList%2A>方法上的存储过程的结果。</span><span class="sxs-lookup"><span data-stu-id="a62da-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="a62da-140">将以下代码添加到`Load`事件以调用存储过程公开为数据上下文的方法之一。</span><span class="sxs-lookup"><span data-stu-id="a62da-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4. <span data-ttu-id="a62da-141">按 F5 以运行您的项目并查看结果。</span><span class="sxs-lookup"><span data-stu-id="a62da-141">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a62da-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="a62da-142">See also</span></span>

- [<span data-ttu-id="a62da-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="a62da-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="a62da-144">查询</span><span class="sxs-lookup"><span data-stu-id="a62da-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="a62da-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a62da-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="a62da-146">DataContext 方法（O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="a62da-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="a62da-147">如何：分配存储过程以便执行更新、插入和删除操作（O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="a62da-147">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
