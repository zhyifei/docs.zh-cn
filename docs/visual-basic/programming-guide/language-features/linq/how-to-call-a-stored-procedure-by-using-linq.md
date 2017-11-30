---
title: "如何：使用 LINQ 调用存储过程 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7fb2d119d56cb643ebc1b43894952a6323e5e06e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="cd492-102">如何：使用 LINQ 调用存储过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd492-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="cd492-103">语言集成查询 (LINQ)，可以轻松地访问数据库信息，包括数据库对象，如存储过程。</span><span class="sxs-lookup"><span data-stu-id="cd492-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="cd492-104">下面的示例演示如何创建的应用程序在 SQL Server 数据库中调用的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="cd492-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="cd492-105">此示例演示如何调用数据库中的两个不同的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="cd492-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="cd492-106">每个过程会返回查询的结果。</span><span class="sxs-lookup"><span data-stu-id="cd492-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="cd492-107">一个过程采用输入的参数或其他过程不采用参数。</span><span class="sxs-lookup"><span data-stu-id="cd492-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="cd492-108">本主题中的示例使用 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="cd492-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="cd492-109">如果你的开发计算机上没有 Northwind 示例数据库，您可以下载它从[Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web 站点。</span><span class="sxs-lookup"><span data-stu-id="cd492-109">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="cd492-110">有关说明，请参阅[下载示例数据库](https://msdn.microsoft.com/library/bb399411)。</span><span class="sxs-lookup"><span data-stu-id="cd492-110">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="cd492-111">若要创建与数据库的连接</span><span class="sxs-lookup"><span data-stu-id="cd492-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="cd492-112">在 Visual Studio 中，打开**服务器资源管理器**/**数据库资源管理器**通过单击**服务器资源管理器**/**数据库资源管理器**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="cd492-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="cd492-113">右键单击**数据连接**中**服务器资源管理器**/**数据库资源管理器**，然后单击**添加连接**。</span><span class="sxs-lookup"><span data-stu-id="cd492-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="cd492-114">指定到 Northwind 示例数据库的有效连接。</span><span class="sxs-lookup"><span data-stu-id="cd492-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="cd492-115">若要添加包含 LINQ to SQL 文件的项目</span><span class="sxs-lookup"><span data-stu-id="cd492-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="cd492-116">在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="cd492-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="cd492-117">选择 Visual Basic **Windows 窗体应用程序**作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="cd492-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="cd492-118">在 **“项目”** 菜单上，单击 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="cd492-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="cd492-119">选择**LINQ to SQL 类**项模板。</span><span class="sxs-lookup"><span data-stu-id="cd492-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="cd492-120">为 `northwind.dbml` 文件命名。</span><span class="sxs-lookup"><span data-stu-id="cd492-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="cd492-121">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="cd492-121">Click **Add**.</span></span> <span data-ttu-id="cd492-122">此时，northwind.dbml 文件打开的对象关系设计器 （O/R 设计器）。</span><span class="sxs-lookup"><span data-stu-id="cd492-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="cd492-123">若要将存储的过程添加到 O/R 设计器</span><span class="sxs-lookup"><span data-stu-id="cd492-123">To add stored procedures to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="cd492-124">在**服务器资源管理器**/**数据库资源管理器**，展开包含到 Northwind 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="cd492-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="cd492-125">展开**存储过程**文件夹。</span><span class="sxs-lookup"><span data-stu-id="cd492-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="cd492-126">如果你已经关闭 O/R 设计器，你可以通过双击前面添加的 northwind.dbml 文件重新打开它。</span><span class="sxs-lookup"><span data-stu-id="cd492-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="cd492-127">单击**按年销售**存储过程并将其拖到设计器的右窗格中。</span><span class="sxs-lookup"><span data-stu-id="cd492-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="cd492-128">单击**十种最贵的产品**存储的过程将将其拖到设计器的右窗格中。</span><span class="sxs-lookup"><span data-stu-id="cd492-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3.  <span data-ttu-id="cd492-129">保存所做的更改并关闭设计器。</span><span class="sxs-lookup"><span data-stu-id="cd492-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="cd492-130">保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="cd492-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="cd492-131">若要添加代码以显示存储过程的结果</span><span class="sxs-lookup"><span data-stu-id="cd492-131">To add code to display the results of the stored procedures</span></span>  
  
1.  <span data-ttu-id="cd492-132">从**工具箱**，拖动<xref:System.Windows.Forms.DataGridView>控件拖到你的项目，form1 的默认设置 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="cd492-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="cd492-133">双击 Form1 以将代码添加到其`Load`事件。</span><span class="sxs-lookup"><span data-stu-id="cd492-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3.  <span data-ttu-id="cd492-134">当存储的过程添加到 O/R 设计器中时，设计器添加<xref:System.Data.Linq.DataContext>为你的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="cd492-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="cd492-135">此对象包含必须具有访问这些过程的代码。</span><span class="sxs-lookup"><span data-stu-id="cd492-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="cd492-136"><xref:System.Data.Linq.DataContext>对象为项目命名为基于.dbml 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="cd492-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="cd492-137">对于此项目，<xref:System.Data.Linq.DataContext>对象命名为`northwindDataContext`。</span><span class="sxs-lookup"><span data-stu-id="cd492-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="cd492-138">你可以创建的实例<xref:System.Data.Linq.DataContext>在你的代码和调用存储的过程方法指定由 O/R 设计器。</span><span class="sxs-lookup"><span data-stu-id="cd492-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="cd492-139">若要将绑定到<xref:System.Windows.Forms.DataGridView>对象，你可能需要将查询强制执行立即通过调用<xref:System.Linq.Enumerable.ToList%2A>方法存储过程的结果。</span><span class="sxs-lookup"><span data-stu-id="cd492-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="cd492-140">以下代码添加到`Load`任一作为数据上下文的方法公开的存储过程调用的事件。</span><span class="sxs-lookup"><span data-stu-id="cd492-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     [!code-vb[VbLINQtoSQLHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]  
    [!code-vb[VbLINQtoSQLHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]  
  
4.  <span data-ttu-id="cd492-141">按 F5 运行项目，并查看结果。</span><span class="sxs-lookup"><span data-stu-id="cd492-141">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd492-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd492-142">See Also</span></span>  
 [<span data-ttu-id="cd492-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="cd492-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="cd492-144">查询</span><span class="sxs-lookup"><span data-stu-id="cd492-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="cd492-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="cd492-145">LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb386976)  
 [<span data-ttu-id="cd492-146">DataContext 方法 （O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="cd492-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [<span data-ttu-id="cd492-147">如何： 分配存储的过程以便执行更新、 插入和删除操作 （O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="cd492-147">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
