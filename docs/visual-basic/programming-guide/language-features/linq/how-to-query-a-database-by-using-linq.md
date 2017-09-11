---
title: "如何︰ 使用 LINQ (Visual Basic 中) 来查询数据库 |Microsoft 文档"
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
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
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
ms.openlocfilehash: a645a71dd0489d6bf2cc0cd4fe5898eb7293f13c
ms.contentlocale: zh-cn
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="e4001-102">如何：使用 LINQ 查询数据库 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4001-102">How to: Query a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="e4001-103">语言集成查询 (LINQ) 更加方便地访问数据库信息和执行查询。</span><span class="sxs-lookup"><span data-stu-id="e4001-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="e4001-104">下面的示例演示如何创建新的应用程序对 SQL Server 数据库执行查询。</span><span class="sxs-lookup"><span data-stu-id="e4001-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="e4001-105">本主题中的示例使用罗斯文示例数据库。</span><span class="sxs-lookup"><span data-stu-id="e4001-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="e4001-106">如果您的开发计算机上没有 Northwind 示例数据库，您可以下载它从[Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web 站点。</span><span class="sxs-lookup"><span data-stu-id="e4001-106">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="e4001-107">有关说明，请参阅[下载示例数据库](https://msdn.microsoft.com/library/bb399411)。</span><span class="sxs-lookup"><span data-stu-id="e4001-107">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="e4001-108">若要创建与数据库的连接</span><span class="sxs-lookup"><span data-stu-id="e4001-108">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="e4001-109">在 Visual Studio 中，打开**服务器资源管理器**/**数据库资源管理器**通过单击**服务器资源管理器**/**数据库资源管理器**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="e4001-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="e4001-110">用鼠标右键单击**数据连接**中**服务器资源管理器**/**数据库资源管理器**，然后单击**添加连接**。</span><span class="sxs-lookup"><span data-stu-id="e4001-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="e4001-111">指定到 Northwind 示例数据库的有效连接。</span><span class="sxs-lookup"><span data-stu-id="e4001-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="e4001-112">若要添加的项目中包含一个 LINQ to SQL 文件</span><span class="sxs-lookup"><span data-stu-id="e4001-112">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="e4001-113">在 Visual Studio 中，在**文件**菜单上，指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="e4001-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="e4001-114">选择 Visual Basic **Windows 窗体应用程序**作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="e4001-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="e4001-115">在 **“项目”** 菜单上，单击 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="e4001-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="e4001-116">选择**LINQ to SQL 类**项模板。</span><span class="sxs-lookup"><span data-stu-id="e4001-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="e4001-117">命名该文件`northwind.dbml`。</span><span class="sxs-lookup"><span data-stu-id="e4001-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="e4001-118">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="e4001-118">Click **Add**.</span></span> <span data-ttu-id="e4001-119">此时，northwind.dbml 文件打开对象关系设计器 （O/R 设计器）。</span><span class="sxs-lookup"><span data-stu-id="e4001-119">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="e4001-120">若要添加到 O/R 设计器查询的表</span><span class="sxs-lookup"><span data-stu-id="e4001-120">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="e4001-121">在**服务器资源管理器**/**数据库资源管理器**，展开 Northwind 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="e4001-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="e4001-122">展开**表**文件夹。</span><span class="sxs-lookup"><span data-stu-id="e4001-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="e4001-123">如果已经关闭 O/R 设计器，您可以通过双击前面添加此时，northwind.dbml 文件将其重新打开。</span><span class="sxs-lookup"><span data-stu-id="e4001-123">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="e4001-124">单击客户表，将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="e4001-124">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="e4001-125">单击订单表，将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="e4001-125">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="e4001-126">设计器创建新`Customer`和`Order`为你的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="e4001-126">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="e4001-127">请注意，设计器会自动检测表之间的关系并创建子相关对象的属性。</span><span class="sxs-lookup"><span data-stu-id="e4001-127">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="e4001-128">例如，IntelliSense 将显示该`Customer`对象具有`Orders`与该客户相关的所有订单的属性。</span><span class="sxs-lookup"><span data-stu-id="e4001-128">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="e4001-129">保存所做的更改并关闭设计器。</span><span class="sxs-lookup"><span data-stu-id="e4001-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="e4001-130">保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="e4001-130">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="e4001-131">添加代码以查询数据库并显示结果</span><span class="sxs-lookup"><span data-stu-id="e4001-131">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="e4001-132">从**工具箱**，拖动<xref:System.Windows.Forms.DataGridView>控件拖放到您的项目，form1 的默认设置 Windows 窗体。</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="e4001-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="e4001-133">双击 form1 若要将代码添加到`Load`形式的事件。</span><span class="sxs-lookup"><span data-stu-id="e4001-133">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="e4001-134">当表添加到 O/R 设计器时，设计器添加<xref:System.Data.Linq.DataContext>为你的项目的对象。</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e4001-134">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="e4001-135">此对象包含必须具有访问这些表，以及各个对象和集合的每个表的代码。</span><span class="sxs-lookup"><span data-stu-id="e4001-135">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="e4001-136"><xref:System.Data.Linq.DataContext>对象名为您的项目根据.dbml 文件的名称。</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e4001-136">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="e4001-137">对于此项目，<xref:System.Data.Linq.DataContext>对象被命名为`northwindDataContext`。</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e4001-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="e4001-138">您可以创建的实例<xref:System.Data.Linq.DataContext>代码和查询中指定由 O/R 设计器的表。</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e4001-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="e4001-139">添加以下代码到`Load`事件以查询公开为数据上下文的属性的表。</span><span class="sxs-lookup"><span data-stu-id="e4001-139">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     <span data-ttu-id="e4001-140">[!code-vb[VbLINQToSQLHowTos #&3;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e4001-140">[!code-vb[VbLINQToSQLHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_1.vb)]</span></span>  
  
4.  <span data-ttu-id="e4001-141">按 F5 以运行您的项目并查看结果。</span><span class="sxs-lookup"><span data-stu-id="e4001-141">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="e4001-142">以下是您可以尝试的其他一些查询︰</span><span class="sxs-lookup"><span data-stu-id="e4001-142">Following are some additional queries that you can try:</span></span>  
  
     <span data-ttu-id="e4001-143">[!code-vb[VbLINQToSQLHowTos #&4;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e4001-143">[!code-vb[VbLINQToSQLHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_2.vb)]</span></span>  
    <span data-ttu-id="e4001-144">[!code-vb[VbLINQToSQLHowTos #&5;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="e4001-144">[!code-vb[VbLINQToSQLHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_3.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4001-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4001-145">See Also</span></span>  
 <span data-ttu-id="e4001-146">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="e4001-146">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="e4001-147"> [查询](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="e4001-147"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="e4001-148"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="e4001-148"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="e4001-149"> [DataContext 方法 （O/R 设计器）](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="e4001-149"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span></span>

