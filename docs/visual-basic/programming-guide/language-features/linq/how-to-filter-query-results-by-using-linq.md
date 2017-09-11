---
title: "如何︰ 使用 LINQ (Visual Basic 中) 来筛选查询结果 |Microsoft 文档"
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
- filtering [Visual Basic]
- filtering data [LINQ in Visual Basic]
- filtering [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], filtering results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- filtering data [Visual Basic]
ms.assetid: ef103092-9bed-4134-97f4-2db696e83c12
caps.latest.revision: 6
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
ms.openlocfilehash: d6197e39ffef5b09b87b1b47cab04d4339bcaf3f
ms.contentlocale: zh-cn
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="84115-102">如何：使用 LINQ 筛选查询结果 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84115-102">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="84115-103">语言集成查询 (LINQ) 更加方便地访问数据库信息和执行查询。</span><span class="sxs-lookup"><span data-stu-id="84115-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="84115-104">下面的示例演示如何创建的新应用程序对 SQL Server 数据库执行查询并使用按特定值筛选结果`Where`子句。</span><span class="sxs-lookup"><span data-stu-id="84115-104">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="84115-105">有关详细信息，请参阅[Where 子句](../../../../visual-basic/language-reference/queries/where-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="84115-105">For more information, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
 <span data-ttu-id="84115-106">本主题中的示例使用罗斯文示例数据库。</span><span class="sxs-lookup"><span data-stu-id="84115-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="84115-107">如果您的开发计算机上没有 Northwind 示例数据库，您可以下载它从[Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web 站点。</span><span class="sxs-lookup"><span data-stu-id="84115-107">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="84115-108">有关说明，请参阅[下载示例数据库](https://msdn.microsoft.com/library/bb399411)。</span><span class="sxs-lookup"><span data-stu-id="84115-108">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="84115-109">若要创建与数据库的连接</span><span class="sxs-lookup"><span data-stu-id="84115-109">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="84115-110">在 Visual Studio 中，打开**服务器资源管理器**/**数据库资源管理器**通过单击**服务器资源管理器**/**数据库资源管理器**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="84115-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="84115-111">用鼠标右键单击**数据连接**中**服务器资源管理器**/**数据库资源管理器**，然后单击**添加连接**。</span><span class="sxs-lookup"><span data-stu-id="84115-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="84115-112">指定到 Northwind 示例数据库的有效连接。</span><span class="sxs-lookup"><span data-stu-id="84115-112">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="84115-113">若要添加的项目中包含一个 LINQ to SQL 文件</span><span class="sxs-lookup"><span data-stu-id="84115-113">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="84115-114">在 Visual Studio 中，在**文件**菜单上，指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="84115-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="84115-115">选择 Visual Basic **Windows 窗体应用程序**作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="84115-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="84115-116">在 **“项目”** 菜单上，单击 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="84115-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="84115-117">选择**LINQ to SQL 类**项模板。</span><span class="sxs-lookup"><span data-stu-id="84115-117">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="84115-118">命名该文件`northwind.dbml`。</span><span class="sxs-lookup"><span data-stu-id="84115-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="84115-119">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="84115-119">Click **Add**.</span></span> <span data-ttu-id="84115-120">此时，northwind.dbml 文件将打开对象关系设计器 （O/R 设计器）。</span><span class="sxs-lookup"><span data-stu-id="84115-120">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="84115-121">若要添加到 O/R 设计器查询的表</span><span class="sxs-lookup"><span data-stu-id="84115-121">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="84115-122">在**服务器资源管理器**/**数据库资源管理器**，展开 Northwind 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="84115-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="84115-123">展开**表**文件夹。</span><span class="sxs-lookup"><span data-stu-id="84115-123">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="84115-124">如果已经关闭 O/R 设计器，您可以通过双击前面添加此时，northwind.dbml 文件将其重新打开。</span><span class="sxs-lookup"><span data-stu-id="84115-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="84115-125">单击客户表，将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="84115-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="84115-126">单击订单表，将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="84115-126">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="84115-127">设计器创建新`Customer`和`Order`为你的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="84115-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="84115-128">请注意，设计器会自动检测表之间的关系并创建子相关对象的属性。</span><span class="sxs-lookup"><span data-stu-id="84115-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="84115-129">例如，IntelliSense 将显示该`Customer`对象具有`Orders`与该客户相关的所有订单的属性。</span><span class="sxs-lookup"><span data-stu-id="84115-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="84115-130">保存所做的更改并关闭设计器。</span><span class="sxs-lookup"><span data-stu-id="84115-130">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="84115-131">保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="84115-131">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="84115-132">添加代码以查询数据库并显示结果</span><span class="sxs-lookup"><span data-stu-id="84115-132">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="84115-133">从**工具箱**，拖动<xref:System.Windows.Forms.DataGridView>控件拖放到您的项目，form1 的默认设置 Windows 窗体。</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="84115-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="84115-134">双击 form1 若要将代码添加到`Load`形式的事件。</span><span class="sxs-lookup"><span data-stu-id="84115-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="84115-135">当表添加到 O/R 设计器时，设计器添加<xref:System.Data.Linq.DataContext>为你的项目的对象。</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="84115-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="84115-136">此对象包含必须具有访问这些表，以及各个对象和集合的每个表的代码。</span><span class="sxs-lookup"><span data-stu-id="84115-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="84115-137"><xref:System.Data.Linq.DataContext>对象名为您的项目根据.dbml 文件的名称。</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="84115-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="84115-138">对于此项目，<xref:System.Data.Linq.DataContext>对象被命名为`northwindDataContext`。</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="84115-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="84115-139">您可以创建的实例<xref:System.Data.Linq.DataContext>代码和查询中指定由 O/R 设计器的表。</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="84115-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="84115-140">添加以下代码到`Load`事件以查询公开为数据上下文的属性的表。</span><span class="sxs-lookup"><span data-stu-id="84115-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="84115-141">查询筛选结果，并且仅返回客户位于`London`。</span><span class="sxs-lookup"><span data-stu-id="84115-141">The query filters the results and returns only customers that are located in `London`.</span></span>  
  
     <span data-ttu-id="84115-142">[!code-vb[VbLINQToSQLHowTos #&11;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="84115-142">[!code-vb[VbLINQToSQLHowTos#11](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_1.vb)]</span></span>  
  
4.  <span data-ttu-id="84115-143">按 F5 以运行您的项目并查看结果。</span><span class="sxs-lookup"><span data-stu-id="84115-143">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="84115-144">以下是您可以尝试的一些其他筛选器。</span><span class="sxs-lookup"><span data-stu-id="84115-144">Following are some other filters that you can try.</span></span>  
  
     <span data-ttu-id="84115-145">[!code-vb[VbLINQToSQLHowTos #&12;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="84115-145">[!code-vb[VbLINQToSQLHowTos#12](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84115-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84115-146">See Also</span></span>  
 <span data-ttu-id="84115-147">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="84115-147">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="84115-148"> [查询](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="84115-148"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="84115-149"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="84115-149"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="84115-150"> [DataContext 方法 （O/R 设计器）](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="84115-150"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span></span>

