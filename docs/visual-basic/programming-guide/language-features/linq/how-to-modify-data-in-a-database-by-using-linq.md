---
title: "如何︰ 通过使用 LINQ (Visual Basic 中) 来修改数据库中的数据 |Microsoft 文档"
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
- inserting rows [LINQ to SQL]
- deleting rows [LINQ to SQL]
- updating rows [LINQ to SQL]
- inserting data [Visual Basic]
- deleting data
- data [Visual Basic], updating
- updating data [LINQ]
- queries [LINQ in Visual Basic], data changes in database
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: cf52635f-0c1b-46c3-aff1-bdf181cf19b1
caps.latest.revision: 15
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2d230594345cff26a83907714e5e8e11b10dde60
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="5a3ac-102">如何：使用 LINQ 修改数据库中的数据 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a3ac-102">How to: Modify Data in a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="5a3ac-103">语言集成查询 (LINQ) 查询更加易于访问数据库信息和修改数据库中的值。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-103">Language-Integrated Query (LINQ) queries make it easy to access database information and modify values in the database.</span></span>  
  
 <span data-ttu-id="5a3ac-104">下面的示例演示如何创建新的应用程序，以检索和更新信息在 SQL Server 数据库中。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-104">The following example shows how to create a new application that retrieves and updates information in a SQL Server database.</span></span>  
  
 <span data-ttu-id="5a3ac-105">本主题中的示例使用罗斯文示例数据库。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="5a3ac-106">如果您的开发计算机上没有 Northwind 示例数据库，您可以下载它从[Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web 站点。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-106">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="5a3ac-107">有关说明，请参阅[下载示例数据库](https://msdn.microsoft.com/library/bb399411)。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-107">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="5a3ac-108">若要创建与数据库的连接</span><span class="sxs-lookup"><span data-stu-id="5a3ac-108">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="5a3ac-109">在 Visual Studio 中，打开**服务器资源管理器**/**数据库资源管理器**通过单击**视图**菜单，然后再选择**服务器资源管理器**/**数据库资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking the **View** menu, and then select **Server Explorer**/**Database Explorer**.</span></span>  
  
2.  <span data-ttu-id="5a3ac-110">用鼠标右键单击**数据连接**中**服务器资源管理器**/**数据库资源管理器**，然后单击**添加连接**。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer**, and click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="5a3ac-111">指定到 Northwind 示例数据库的有效连接。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a><span data-ttu-id="5a3ac-112">若要将使用 LINQ 项目添加到 SQL 文件</span><span class="sxs-lookup"><span data-stu-id="5a3ac-112">To add a Project with a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="5a3ac-113">在 Visual Studio 中，在**文件**菜单上，指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="5a3ac-114">选择 Visual Basic **Windows 窗体应用程序**作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="5a3ac-115">在 **“项目”** 菜单上，单击 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="5a3ac-116">选择**LINQ to SQL 类**项模板。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="5a3ac-117">命名该文件`northwind.dbml`。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="5a3ac-118">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-118">Click **Add**.</span></span> <span data-ttu-id="5a3ac-119">对象关系设计器 （O/R 设计器） 打开以进行`northwind.dbml`文件。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-119">The Object Relational Designer (O/R Designer) is opened for the `northwind.dbml` file.</span></span>  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a><span data-ttu-id="5a3ac-120">若要添加表以查询和修改到设计器</span><span class="sxs-lookup"><span data-stu-id="5a3ac-120">To add tables to query and modify to the designer</span></span>  
  
1.  <span data-ttu-id="5a3ac-121">在**服务器资源管理器**/**数据库资源管理器**，展开 Northwind 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="5a3ac-122">展开**表**文件夹。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="5a3ac-123">如果已经关闭 O/R 设计器，您可以重新打开它通过双击`northwind.dbml`前面添加的文件。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-123">If you have closed the O/R Designer, you can reopen it by double-clicking the `northwind.dbml` file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="5a3ac-124">单击客户表，将其拖到设计器的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-124">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="5a3ac-125">设计器创建新的 Customer 对象为你的项目。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-125">The designer creates a new Customer object for your project.</span></span>  
  
3.  <span data-ttu-id="5a3ac-126">保存所做的更改并关闭设计器。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-126">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="5a3ac-127">保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-127">Save your project.</span></span>  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a><span data-ttu-id="5a3ac-128">添加代码以修改数据库并显示结果</span><span class="sxs-lookup"><span data-stu-id="5a3ac-128">To add code to modify the database and display the results</span></span>  
  
1.  <span data-ttu-id="5a3ac-129">从**工具箱**，拖动<xref:System.Windows.Forms.DataGridView>控件拖放到您的项目，form1 的默认设置 Windows 窗体。</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="5a3ac-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="5a3ac-130">当表添加到 O/R 设计器时，设计器添加<xref:System.Data.Linq.DataContext>对象传递给您的项目。</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="5a3ac-130">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="5a3ac-131">此对象包含可用于访问客户表的代码。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-131">This object contains code that you can use to access the Customers table.</span></span> <span data-ttu-id="5a3ac-132">它还包含用于定义本地的客户对象和一个客户集合，以便对表的代码。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-132">It also contains code that defines  a local Customer object and a Customers collection for the table.</span></span> <span data-ttu-id="5a3ac-133"><xref:System.Data.Linq.DataContext>对象名为您的项目根据.dbml 文件的名称。</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="5a3ac-133">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="5a3ac-134">对于此项目，<xref:System.Data.Linq.DataContext>对象被命名为`northwindDataContext`。</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="5a3ac-134">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="5a3ac-135">您可以创建的实例<xref:System.Data.Linq.DataContext>对象在您的代码和查询和修改由 O/R 设计器指定的客户集合。</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="5a3ac-135">You can create an instance of the <xref:System.Data.Linq.DataContext> object in your code and query and modify the Customers collection specified by the O/R Designer.</span></span> <span data-ttu-id="5a3ac-136">之前通过调用将提交对 Customers 集合所做的更改不会反映在数据库中<xref:System.Data.Linq.DataContext.SubmitChanges%2A>方法<xref:System.Data.Linq.DataContext>对象。</xref:System.Data.Linq.DataContext> </xref:System.Data.Linq.DataContext.SubmitChanges%2A></span><span class="sxs-lookup"><span data-stu-id="5a3ac-136">Changes that you make to the Customers collection are not reflected in the database until you submit them by calling the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> method of the <xref:System.Data.Linq.DataContext> object.</span></span>  
  
     <span data-ttu-id="5a3ac-137">双击 Windows 窗体，form1，以将代码添加到<xref:System.Windows.Forms.Form.Load>事件，以查询作为您<xref:System.Data.Linq.DataContext>。</xref:System.Data.Linq.DataContext>属性公开的客户表</xref:System.Windows.Forms.Form.Load></span><span class="sxs-lookup"><span data-stu-id="5a3ac-137">Double-click the Windows Form, Form1, to add code to the <xref:System.Windows.Forms.Form.Load> event to query the Customers table that is exposed as a property of your <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="5a3ac-138">添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="5a3ac-138">Add the following code:</span></span>  
  
    ```vb  
    Private db As northwindDataContext  
  
    Private Sub Form1_Load(ByVal sender As System.Object,   
                           ByVal e As System.EventArgs  
                          ) Handles MyBase.Load  
      db = New northwindDataContext()  
  
      RefreshData()  
    End Sub  
  
    Private Sub RefreshData()  
      Dim customers = From cust In db.Customers   
                      Where cust.City(0) = "W"   
                      Select cust  
  
      DataGridView1.DataSource = customers  
    End Sub  
    ```  
  
3.  <span data-ttu-id="5a3ac-139">从**工具箱**，将三个<xref:System.Windows.Forms.Button>拖到窗体的控件。</xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="5a3ac-139">From the **Toolbox**, drag three <xref:System.Windows.Forms.Button> controls onto the form.</span></span> <span data-ttu-id="5a3ac-140">选择第一个`Button`控件。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-140">Select the first `Button` control.</span></span> <span data-ttu-id="5a3ac-141">在**属性**窗口中，设置`Name`的`Button`控制转移到`AddButton`和`Text`到`Add`。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-141">In the **Properties** window, set the `Name` of the `Button` control to `AddButton` and the `Text` to `Add`.</span></span> <span data-ttu-id="5a3ac-142">选择第二个按钮并设置`Name`属性设置为`UpdateButton`和`Text`属性设置为`Update`。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-142">Select the second button and set the `Name` property to `UpdateButton` and the `Text` property to `Update`.</span></span> <span data-ttu-id="5a3ac-143">选择第三个按钮并设置`Name`属性设置为`DeleteButton`和`Text`属性设置为`Delete`。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-143">Select the third button and set the `Name` property to `DeleteButton` and the `Text` property to `Delete`.</span></span>  
  
4.  <span data-ttu-id="5a3ac-144">双击**添加**按钮以将代码添加到其`Click`事件。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-144">Double-click the **Add** button to add code to its `Click` event.</span></span> <span data-ttu-id="5a3ac-145">添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="5a3ac-145">Add the following code:</span></span>  
  
    ```vb  
    Private Sub AddButton_Click(ByVal sender As System.Object,   
                                ByVal e As System.EventArgs  
                               ) Handles AddButton.Click  
      Dim cust As New Customer With {   
        .City = "Wellington",   
        .CompanyName = "Blue Yonder Airlines",   
        .ContactName = "Jill Frank",   
        .Country = "New Zealand",   
        .CustomerID = "JILLF"}  
  
      db.Customers.InsertOnSubmit(cust)  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
5.  <span data-ttu-id="5a3ac-146">双击**更新**按钮以将代码添加到其`Click`事件。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-146">Double-click the **Update** button to add code to its `Click` event.</span></span> <span data-ttu-id="5a3ac-147">添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="5a3ac-147">Add the following code:</span></span>  
  
    ```vb  
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles UpdateButton.Click  
      Dim updateCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      updateCust.ContactName = "Jill Shrader"  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
6.  <span data-ttu-id="5a3ac-148">双击**删除**按钮以将代码添加到其`Click`事件。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-148">Double-click the **Delete** button to add code to its `Click` event.</span></span> <span data-ttu-id="5a3ac-149">添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="5a3ac-149">Add the following code:</span></span>  
  
    ```vb  
    Private Sub DeleteButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles DeleteButton.Click  
      Dim deleteCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      db.Customers.DeleteOnSubmit(deleteCust)  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
7.  <span data-ttu-id="5a3ac-150">按 F5 运行项目。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-150">Press F5 to run your project.</span></span> <span data-ttu-id="5a3ac-151">单击**添加**添加一条新记录。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-151">Click **Add** to add a new record.</span></span> <span data-ttu-id="5a3ac-152">单击**更新**修改新记录。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-152">Click **Update** to modify the new record.</span></span> <span data-ttu-id="5a3ac-153">单击**删除**来删除新的记录。</span><span class="sxs-lookup"><span data-stu-id="5a3ac-153">Click **Delete** to delete the new record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a3ac-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a3ac-154">See Also</span></span>  
 <span data-ttu-id="5a3ac-155">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="5a3ac-155">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="5a3ac-156"> [查询](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="5a3ac-156"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="5a3ac-157"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="5a3ac-157"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="5a3ac-158"> [DataContext 方法 （O/R 设计器）](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer) </span><span class="sxs-lookup"><span data-stu-id="5a3ac-158"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer) </span></span>  
<span data-ttu-id="5a3ac-159"> [如何︰ 分配存储的过程以便执行更新、 插入和删除操作 （O/R 设计器）](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)</span><span class="sxs-lookup"><span data-stu-id="5a3ac-159"> [How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)</span></span>
