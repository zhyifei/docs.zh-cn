---
title: 如何：使用 LINQ 修改数据库中的数据
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
ms.openlocfilehash: 9a10efef5ae92dd21888594ae80a3fc07869a8c0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344949"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a>如何：使用 LINQ 修改数据库中的数据 (Visual Basic)

使用语言集成查询（LINQ）查询可以轻松地访问数据库信息和修改数据库中的值。

下面的示例演示如何创建一个新的应用程序，用于检索和更新 SQL Server 数据库中的信息。

本主题中的示例使用 Northwind 示例数据库。 如果你的开发计算机上没有此数据库，可以从 Microsoft 下载中心进行下载。 有关说明，请参阅[下载示例数据库](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)。

### <a name="to-create-a-connection-to-a-database"></a>创建与数据库的连接

1. 在 Visual Studio 中，通过单击 "**查看**" 菜单打开**服务器资源管理器**/**数据库资源管理器**，然后选择 "**服务器资源管理器**/**数据库资源管理器**"。

2. 右键单击**服务器资源管理器**/**数据库资源管理器**中的 "**数据连接**"，然后单击 "**添加连接**"。

3. 指定与 Northwind 示例数据库的有效连接。

### <a name="to-add-a-project-with-a-linq-to-sql-file"></a>使用 LINQ to SQL 文件添加项目

1. 在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。 选择 Visual Basic **Windows 窗体应用程序**作为项目类型。

2. 在 **“项目”** 菜单上，单击 **“添加新项”** 。 选择 " **LINQ to SQL 类**" 项模板。

3. 为 `northwind.dbml` 文件命名。 单击 **“添加”** 。 为 `northwind.dbml` 文件打开对象关系设计器（O/R 设计器）。

### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a>添加要查询和修改设计器的表

1. 在**服务器资源管理器**/**数据库资源管理器**中，展开与 Northwind 数据库的连接。 展开 "**表**" 文件夹。

     如果关闭了 O/R 设计器，则可以通过双击先前添加的 `northwind.dbml` 文件重新打开它。

2. 单击 "Customers" 表，并将其拖到设计器的左窗格中。

     设计器将为您的项目创建一个新的客户对象。

3. 保存更改并关闭设计器。

4. 保存你的项目。

### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a>添加代码以修改数据库并显示结果

1. 从 "**工具箱**" 中，将 "<xref:System.Windows.Forms.DataGridView>" 控件拖动到项目的默认 Windows 窗体 "Form1"。

2. 将表添加到 O/R 设计器后，设计器会将 <xref:System.Data.Linq.DataContext> 对象添加到项目。 此对象包含可用于访问 Customers 表的代码。 它还包含用于定义表的本地 Customer 对象和 Customer 集合的代码。 项目的 <xref:System.Data.Linq.DataContext> 对象根据 .dbml 文件的名称进行命名。 对于此项目，<xref:System.Data.Linq.DataContext> 对象名为 `northwindDataContext`。

     您可以在代码中创建 <xref:System.Data.Linq.DataContext> 对象的实例，并查询和修改 O/R 设计器指定的 Customers 集合。 在通过调用 <xref:System.Data.Linq.DataContext> 对象的 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 方法提交之前，对 "客户" 集合所做的更改不会反映到数据库中。

     双击 Windows 窗体 "Form1"，将代码添加到 <xref:System.Windows.Forms.Form.Load> 事件，以查询作为 <xref:System.Data.Linq.DataContext>的属性公开的 Customers 表。 添加以下代码：

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

3. 从 "**工具箱**" 中，将三个 <xref:System.Windows.Forms.Button> 控件拖动到窗体上。 选择第一个 `Button` 控件。 在 "**属性**" 窗口中，将 `Button` 控件的 `Name` 设置为 `AddButton`，并将 `Text` 设置为 `Add`。 选择第二个按钮，并将 `Name` 属性设置为 `UpdateButton`，将 `Text` 属性设置为 "`Update`"。 选择第三个按钮，并将 `Name` 属性设置为 `DeleteButton`，将 `Text` 属性设置为 "`Delete`"。

4. 双击 "**添加**" 按钮，将代码添加到其 `Click` 事件。 添加以下代码：

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

5. 双击 "**更新**" 按钮，将代码添加到其 `Click` 事件。 添加以下代码：

    ```vb
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _
                                   ByVal e As System.EventArgs
                                  ) Handles UpdateButton.Click
      Dim updateCust = (From cust In db.Customers
                        Where cust.CustomerID = "JILLF").ToList()(0)

      updateCust.ContactName = "Jill Shrader"
      updateCust.Country = "Wales"
      updateCust.CompanyName = "Red Yonder Airlines"
      updateCust.City = "Cardiff"

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

6. 双击 "**删除**" 按钮，将代码添加到其 `Click` 事件。 添加以下代码：

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

7. 按 F5 运行项目。 单击 "**添加**" 以添加新记录。 单击 "**更新**" 以修改新记录。 单击 "**删除**" 以删除新记录。

## <a name="see-also"></a>另请参阅

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [查询](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext 方法（O/R 设计器）](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [如何：分配存储过程以便执行更新、插入和删除操作（O/R 设计器）](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
