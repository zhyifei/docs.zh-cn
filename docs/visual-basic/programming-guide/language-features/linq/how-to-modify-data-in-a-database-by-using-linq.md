---
title: 如何：使用 LINQ 修改数据库中的数据 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 617bb62f9009c507658b5d1262657cb4dfa860e9
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2018
ms.locfileid: "34827106"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a>如何：使用 LINQ 修改数据库中的数据 (Visual Basic)
语言集成查询 (LINQ) 查询，可以方便地访问数据库信息和修改数据库中的值。  
  
 下面的示例演示如何创建新的应用程序检索和更新信息的 SQL Server 数据库中。  
  
 本主题中的示例使用 Northwind 示例数据库。 如果你的开发计算机上没有此数据库，您可以从 Microsoft 下载中心下载它。 有关说明，请参阅[下载示例数据库](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)。  
  
### <a name="to-create-a-connection-to-a-database"></a>若要创建与数据库的连接  
  
1.  在 Visual Studio 中，打开**服务器资源管理器**/**数据库资源管理器**通过单击**视图**菜单，然后再选择**服务器资源管理器**/**数据库资源管理器**。  
  
2.  右键单击**数据连接**中**服务器资源管理器**/**数据库资源管理器**，然后单击**添加连接**。  
  
3.  指定到 Northwind 示例数据库的有效连接。  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a>要添加到 SQL 文件具有 LINQ 的项目  
  
1.  在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。 选择 Visual Basic **Windows 窗体应用程序**作为项目类型。  
  
2.  在 **“项目”** 菜单上，单击 **“添加新项”**。 选择**LINQ to SQL 类**项模板。  
  
3.  为 `northwind.dbml` 文件命名。 单击 **添加**。 对象关系设计器 （O/R 设计器） 打开以进行`northwind.dbml`文件。  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a>若要添加表查询和修改到设计器  
  
1.  在**服务器资源管理器**/**数据库资源管理器**，展开包含到 Northwind 数据库的连接。 展开**表**文件夹。  
  
     如果你已经关闭 O/R 设计器，你可以重新打开它通过双击`northwind.dbml`前面添加的文件。  
  
2.  单击客户表并将其拖到设计器的左窗格中。  
  
     设计器创建一个新的客户对象，为你的项目。  
  
3.  保存所做的更改并关闭设计器。  
  
4.  保存你的项目。  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a>若要添加代码以修改数据库并显示结果  
  
1.  从**工具箱**，拖动<xref:System.Windows.Forms.DataGridView>控件拖到你的项目，form1 的默认设置 Windows 窗体。  
  
2.  当表添加到 O/R 设计器时，设计器添加<xref:System.Data.Linq.DataContext>到你的项目的对象。 此对象包含可用于访问客户表的代码。 它还包含代码，用于定义本地的客户对象和表的客户集合。 <xref:System.Data.Linq.DataContext>对象命名为你的项目基于.dbml 文件的名称。 对于此项目，<xref:System.Data.Linq.DataContext>对象命名为`northwindDataContext`。  
  
     你可以创建的实例<xref:System.Data.Linq.DataContext>对象中的代码和查询和修改由 O/R 设计器指定的客户集合。 将它们提交通过调用之前对客户集合所做的更改不会反映在数据库中<xref:System.Data.Linq.DataContext.SubmitChanges%2A>方法<xref:System.Data.Linq.DataContext>对象。  
  
     双击 Windows 窗体，form1，将代码添加到<xref:System.Windows.Forms.Form.Load>的 Customers 表的查询的事件公开的属性为你<xref:System.Data.Linq.DataContext>。 添加以下代码：  
  
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
  
3.  从**工具箱**，将三个<xref:System.Windows.Forms.Button>拖到窗体控件。 选择第一个`Button`控件。 在**属性**窗口中，设置`Name`的`Button`控制转移到`AddButton`和`Text`到`Add`。 选择第二个按钮并设置`Name`属性`UpdateButton`和`Text`属性`Update`。 选择第三个按钮并设置`Name`属性`DeleteButton`和`Text`属性`Delete`。  
  
4.  双击**添加**按钮以将代码添加到其`Click`事件。 添加以下代码：  
  
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
  
5.  双击**更新**按钮以将代码添加到其`Click`事件。 添加以下代码：  
  
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
  
6.  双击**删除**按钮以将代码添加到其`Click`事件。 添加以下代码：  
  
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
  
7.  按 F5 运行项目。 单击**添加**添加一条新记录。 单击**更新**修改新的记录。 单击**删除**删除新的记录。  
  
## <a name="see-also"></a>请参阅  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [查询](../../../../visual-basic/language-reference/queries/queries.md)  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
 [DataContext 方法 （O/R 设计器）](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [如何： 分配存储的过程以便执行更新、 插入和删除操作 （O/R 设计器）](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
