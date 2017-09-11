---
title: "如何︰ 使用 LINQ (Visual Basic 中) 调用存储的过程 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 40e72ece8399b1ffbe8c5457c63113d563c9f7f8
ms.contentlocale: zh-cn
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="a0442-102">如何：使用 LINQ 调用存储过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0442-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="a0442-103">语言集成查询 (LINQ) 就可以轻松地访问数据库的信息，包括数据库对象，如存储过程。</span><span class="sxs-lookup"><span data-stu-id="a0442-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="a0442-104">下面的示例演示如何创建 SQL Server 数据库中调用存储的过程的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a0442-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="a0442-105">此示例演示如何在数据库中调用两个不同的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="a0442-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="a0442-106">每个过程返回查询的结果。</span><span class="sxs-lookup"><span data-stu-id="a0442-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="a0442-107">一个过程采用输入的参数，以及另一个过程不带参数。</span><span class="sxs-lookup"><span data-stu-id="a0442-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="a0442-108">本主题中的示例使用罗斯文示例数据库。</span><span class="sxs-lookup"><span data-stu-id="a0442-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="a0442-109">如果您的开发计算机上没有 Northwind 示例数据库，您可以下载它从[Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web 站点。</span><span class="sxs-lookup"><span data-stu-id="a0442-109">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="a0442-110">有关说明，请参阅[下载示例数据库](https://msdn.microsoft.com/library/bb399411)。</span><span class="sxs-lookup"><span data-stu-id="a0442-110">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="a0442-111">若要创建与数据库的连接</span><span class="sxs-lookup"><span data-stu-id="a0442-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="a0442-112">在 Visual Studio 中，打开**服务器资源管理器**/**数据库资源管理器**通过单击**服务器资源管理器**/**数据库资源管理器**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="a0442-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="a0442-113">用鼠标右键单击**数据连接**中**服务器资源管理器**/**数据库资源管理器**，然后单击**添加连接**。</span><span class="sxs-lookup"><span data-stu-id="a0442-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="a0442-114">指定到 Northwind 示例数据库的有效连接。</span><span class="sxs-lookup"><span data-stu-id="a0442-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="a0442-115">若要添加的项目中包含一个 LINQ to SQL 文件</span><span class="sxs-lookup"><span data-stu-id="a0442-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="a0442-116">在 Visual Studio 中，在**文件**菜单上，指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="a0442-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="a0442-117">选择 Visual Basic **Windows 窗体应用程序**作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="a0442-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="a0442-118">在 **“项目”** 菜单上，单击 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="a0442-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="a0442-119">选择**LINQ to SQL 类**项模板。</span><span class="sxs-lookup"><span data-stu-id="a0442-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="a0442-120">命名该文件`northwind.dbml`。</span><span class="sxs-lookup"><span data-stu-id="a0442-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="a0442-121">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="a0442-121">Click **Add**.</span></span> <span data-ttu-id="a0442-122">此时，northwind.dbml 文件打开对象关系设计器 （O/R 设计器）。</span><span class="sxs-lookup"><span data-stu-id="a0442-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="a0442-123">若要将存储的过程添加到 O/R 设计器</span><span class="sxs-lookup"><span data-stu-id="a0442-123">To add stored procedures to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="a0442-124">在**服务器资源管理器**/**数据库资源管理器**，展开 Northwind 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="a0442-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="a0442-125">展开**存储过程**文件夹。</span><span class="sxs-lookup"><span data-stu-id="a0442-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="a0442-126">如果已经关闭 O/R 设计器，您可以通过双击前面添加此时，northwind.dbml 文件将其重新打开。</span><span class="sxs-lookup"><span data-stu-id="a0442-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="a0442-127">单击**年份的销售额**存储过程并将其拖到设计器的右窗格中。</span><span class="sxs-lookup"><span data-stu-id="a0442-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="a0442-128">单击**Ten Most Expensive Products**存储的过程将将其拖到设计器的右窗格中。</span><span class="sxs-lookup"><span data-stu-id="a0442-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3.  <span data-ttu-id="a0442-129">保存所做的更改并关闭设计器。</span><span class="sxs-lookup"><span data-stu-id="a0442-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="a0442-130">保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="a0442-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="a0442-131">添加代码以显示存储过程的结果</span><span class="sxs-lookup"><span data-stu-id="a0442-131">To add code to display the results of the stored procedures</span></span>  
  
1.  <span data-ttu-id="a0442-132">从**工具箱**，拖动<xref:System.Windows.Forms.DataGridView>控件拖放到您的项目，form1 的默认设置 Windows 窗体。</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="a0442-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="a0442-133">双击 form1 若要将代码添加到其`Load`事件。</span><span class="sxs-lookup"><span data-stu-id="a0442-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3.  <span data-ttu-id="a0442-134">当存储的过程添加到 O/R 设计器时，设计器添加<xref:System.Data.Linq.DataContext>为你的项目的对象。</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="a0442-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="a0442-135">此对象包含必须具有访问这些过程的代码。</span><span class="sxs-lookup"><span data-stu-id="a0442-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="a0442-136"><xref:System.Data.Linq.DataContext>对象项目命名为根据.dbml 文件的名称。</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="a0442-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="a0442-137">对于此项目，<xref:System.Data.Linq.DataContext>对象被命名为`northwindDataContext`。</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="a0442-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="a0442-138">您可以创建的实例<xref:System.Data.Linq.DataContext>在您的代码和调用存储的过程方法由指定的 O/R 设计器。</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="a0442-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="a0442-139">若要将绑定到<xref:System.Windows.Forms.DataGridView>对象时，你可能需要强制执行查询立即执行，通过调用<xref:System.Linq.Enumerable.ToList%2A>方法存储过程的结果。</xref:System.Linq.Enumerable.ToList%2A> </xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="a0442-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="a0442-140">添加以下代码到`Load`事件，以调用存储过程公开为数据上下文的方法之一。</span><span class="sxs-lookup"><span data-stu-id="a0442-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     <span data-ttu-id="a0442-141">[!code-vb[VbLINQtoSQLHowTos #&1;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a0442-141">[!code-vb[VbLINQtoSQLHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]</span></span>  
    <span data-ttu-id="a0442-142">[!code-vb[VbLINQtoSQLHowTos #&2;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a0442-142">[!code-vb[VbLINQtoSQLHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]</span></span>  
  
4.  <span data-ttu-id="a0442-143">按 F5 以运行您的项目并查看结果。</span><span class="sxs-lookup"><span data-stu-id="a0442-143">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0442-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0442-144">See Also</span></span>  
 <span data-ttu-id="a0442-145">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="a0442-145">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="a0442-146"> [查询](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="a0442-146"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="a0442-147"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="a0442-147"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="a0442-148"> [DataContext 方法 （O/R 设计器）](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer) </span><span class="sxs-lookup"><span data-stu-id="a0442-148"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer) </span></span>  
<span data-ttu-id="a0442-149"> [如何︰ 分配存储的过程以便执行更新、 插入和删除操作 （O/R 设计器）](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)</span><span class="sxs-lookup"><span data-stu-id="a0442-149"> [How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)</span></span>

