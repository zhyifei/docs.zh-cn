---
title: 如何：使用 LINQ 调用存储过程
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: f91ccda1842887b3785ce304fd41bdd020a55479
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345028"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="9d78a-102">如何：使用 LINQ 调用存储过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d78a-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="9d78a-103">使用语言集成查询（LINQ），可以轻松地访问数据库信息，其中包括数据库对象（如存储过程）。</span><span class="sxs-lookup"><span data-stu-id="9d78a-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="9d78a-104">下面的示例演示如何创建一个应用程序，用于调用 SQL Server 数据库中的存储过程。</span><span class="sxs-lookup"><span data-stu-id="9d78a-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="9d78a-105">该示例演示如何调用数据库中的两个不同的存储过程。</span><span class="sxs-lookup"><span data-stu-id="9d78a-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="9d78a-106">每个过程都返回查询的结果。</span><span class="sxs-lookup"><span data-stu-id="9d78a-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="9d78a-107">一个过程采用输入参数，而另一个过程不接受参数。</span><span class="sxs-lookup"><span data-stu-id="9d78a-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="9d78a-108">本主题中的示例使用 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="9d78a-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="9d78a-109">如果你的开发计算机上没有此数据库，可以从 Microsoft 下载中心进行下载。</span><span class="sxs-lookup"><span data-stu-id="9d78a-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="9d78a-110">有关说明，请参阅[下载示例数据库](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="9d78a-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="9d78a-111">创建与数据库的连接</span><span class="sxs-lookup"><span data-stu-id="9d78a-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="9d78a-112">在 Visual Studio 中，通过单击 "**视图**"**菜单上的** **服务器资源管理器**/数据库资源管理器来打开**服务器资源管理器**/**数据库资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="9d78a-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="9d78a-113">右键单击**服务器资源管理器**/**数据库资源管理器**中的 "**数据连接**"，然后单击 "**添加连接**"。</span><span class="sxs-lookup"><span data-stu-id="9d78a-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="9d78a-114">指定与 Northwind 示例数据库的有效连接。</span><span class="sxs-lookup"><span data-stu-id="9d78a-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="9d78a-115">添加包含 LINQ to SQL 文件的项目</span><span class="sxs-lookup"><span data-stu-id="9d78a-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="9d78a-116">在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="9d78a-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="9d78a-117">选择 Visual Basic **Windows 窗体应用程序**作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="9d78a-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="9d78a-118">在 **“项目”** 菜单上，单击 **“添加新项”** 。</span><span class="sxs-lookup"><span data-stu-id="9d78a-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="9d78a-119">选择 " **LINQ to SQL 类**" 项模板。</span><span class="sxs-lookup"><span data-stu-id="9d78a-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="9d78a-120">为 `northwind.dbml` 文件命名。</span><span class="sxs-lookup"><span data-stu-id="9d78a-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="9d78a-121">单击 **“添加”** 。</span><span class="sxs-lookup"><span data-stu-id="9d78a-121">Click **Add**.</span></span> <span data-ttu-id="9d78a-122">为 northwind 文件打开对象关系设计器（O/R 设计器）。</span><span class="sxs-lookup"><span data-stu-id="9d78a-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="9d78a-123">将存储过程添加到 O/R 设计器</span><span class="sxs-lookup"><span data-stu-id="9d78a-123">To add stored procedures to the O/R Designer</span></span>  
  
1. <span data-ttu-id="9d78a-124">在**服务器资源管理器**/**数据库资源管理器**中，展开与 Northwind 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="9d78a-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="9d78a-125">展开 "**存储过程**" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="9d78a-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="9d78a-126">如果关闭了 O/R 设计器，则可以通过双击先前添加的 northwind 文件来重新打开它。</span><span class="sxs-lookup"><span data-stu-id="9d78a-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="9d78a-127">单击 "**按年份的销售额**" 存储过程，并将其拖到设计器的右窗格中。</span><span class="sxs-lookup"><span data-stu-id="9d78a-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="9d78a-128">单击**十个最昂贵的产品**存储过程，将其拖到设计器的右窗格中。</span><span class="sxs-lookup"><span data-stu-id="9d78a-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3. <span data-ttu-id="9d78a-129">保存更改并关闭设计器。</span><span class="sxs-lookup"><span data-stu-id="9d78a-129">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="9d78a-130">保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="9d78a-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="9d78a-131">添加代码以显示存储过程的结果</span><span class="sxs-lookup"><span data-stu-id="9d78a-131">To add code to display the results of the stored procedures</span></span>  
  
1. <span data-ttu-id="9d78a-132">从 "**工具箱**" 中，将 "<xref:System.Windows.Forms.DataGridView>" 控件拖动到项目的默认 Windows 窗体 "Form1"。</span><span class="sxs-lookup"><span data-stu-id="9d78a-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="9d78a-133">双击 "Form1"，将代码添加到其 `Load` 事件。</span><span class="sxs-lookup"><span data-stu-id="9d78a-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3. <span data-ttu-id="9d78a-134">将存储过程添加到 O/R 设计器后，设计器将为您的项目添加 <xref:System.Data.Linq.DataContext> 对象。</span><span class="sxs-lookup"><span data-stu-id="9d78a-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="9d78a-135">此对象包含访问这些过程所需的代码。</span><span class="sxs-lookup"><span data-stu-id="9d78a-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="9d78a-136">项目的 <xref:System.Data.Linq.DataContext> 对象根据 .dbml 文件的名称进行命名。</span><span class="sxs-lookup"><span data-stu-id="9d78a-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="9d78a-137">对于此项目，<xref:System.Data.Linq.DataContext> 对象名为 `northwindDataContext`。</span><span class="sxs-lookup"><span data-stu-id="9d78a-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="9d78a-138">您可以在代码中创建 <xref:System.Data.Linq.DataContext> 的实例，并调用由 O/R 设计器指定的存储过程方法。</span><span class="sxs-lookup"><span data-stu-id="9d78a-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="9d78a-139">若要绑定到 <xref:System.Windows.Forms.DataGridView> 对象，可能需要通过对存储过程的结果调用 <xref:System.Linq.Enumerable.ToList%2A> 方法来强制立即执行查询。</span><span class="sxs-lookup"><span data-stu-id="9d78a-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="9d78a-140">将以下代码添加到 `Load` 事件，以便调用公开为数据上下文的方法的存储过程之一。</span><span class="sxs-lookup"><span data-stu-id="9d78a-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4. <span data-ttu-id="9d78a-141">按 F5 运行项目并查看结果。</span><span class="sxs-lookup"><span data-stu-id="9d78a-141">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d78a-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d78a-142">See also</span></span>

- [<span data-ttu-id="9d78a-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="9d78a-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="9d78a-144">查询</span><span class="sxs-lookup"><span data-stu-id="9d78a-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="9d78a-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="9d78a-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="9d78a-146">DataContext 方法（O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="9d78a-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="9d78a-147">如何：分配存储过程以便执行更新、插入和删除操作（O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="9d78a-147">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
