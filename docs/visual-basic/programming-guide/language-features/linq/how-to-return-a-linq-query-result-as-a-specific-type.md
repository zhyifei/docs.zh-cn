---
title: 如何：以特定类型返回 LINQ 查询结果 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: e0b7e402fba4fb51afb60ad0ae7698bd4947b2f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a>如何：以特定类型返回 LINQ 查询结果 (Visual Basic)
语言集成查询 (LINQ)，可以轻松地访问数据库信息和执行查询。 默认情况下，LINQ 查询以匿名类型返回的对象的列表。 你还可以指定查询返回特定类型的列表，通过使用`Select`子句。  
  
 下面的示例演示如何创建的新应用程序对 SQL Server 数据库执行查询并将结果投影为特定的命名类型。 有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)和[Select 子句](../../../../visual-basic/language-reference/queries/select-clause.md)。  
  
 本主题中的示例使用 Northwind 示例数据库。 如果你的开发计算机上没有 Northwind 示例数据库，您可以下载它从[Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web 站点。 有关说明，请参阅[下载示例数据库](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>若要创建与数据库的连接  
  
1.  在 Visual Studio 中，打开**服务器资源管理器**/**数据库资源管理器**通过单击**服务器资源管理器**/**数据库资源管理器**上**视图**菜单。  
  
2.  右键单击**数据连接**中**服务器资源管理器**/**数据库资源管理器**，然后单击**添加连接**。  
  
3.  指定到 Northwind 示例数据库的有效连接。  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>若要添加包含 LINQ to SQL 文件的项目  
  
1.  在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。 选择 Visual Basic **Windows 窗体应用程序**作为项目类型。  
  
2.  在 **“项目”** 菜单上，单击 **“添加新项”**。 选择**LINQ to SQL 类**项模板。  
  
3.  为 `northwind.dbml` 文件命名。 单击 **添加**。 此时，northwind.dbml 文件打开的对象关系设计器 （O/R 设计器）。  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>若要添加到 O/R 设计器查询的表  
  
1.  在**服务器资源管理器**/**数据库资源管理器**，展开包含到 Northwind 数据库的连接。 展开**表**文件夹。  
  
     如果你已经关闭 O/R 设计器，你可以通过双击前面添加的 northwind.dbml 文件重新打开它。  
  
2.  单击客户表并将其拖到设计器的左窗格中。  
  
     设计器创建一个新`Customer`为你的项目的对象。 可以投影查询结果映射为`Customer`类型或为你创建的类型。 此示例将在后面的过程中创建新的类型，并将查询结果映射为该类型。  
  
3.  保存所做的更改并关闭设计器。  
  
4.  保存你的项目。  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>若要添加代码以查询数据库并显示结果  
  
1.  从**工具箱**，拖动<xref:System.Windows.Forms.DataGridView>控件拖到你的项目，form1 的默认设置 Windows 窗体。  
  
2.  双击 Form1 以修改 Form1 类。  
  
3.  后`End Class`Form1 类的语句添加以下代码以创建`CustomerInfo`类型以保存此示例的查询结果。  
  
     [!code-vb[VbLINQToSQLHowTos#16](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_1.vb)]  
  
4.  当表添加到 O/R 设计器时，设计器添加<xref:System.Data.Linq.DataContext>到你的项目的对象。 此对象包含必须具有访问这些表，并访问单个对象和集合的每个表的代码。 <xref:System.Data.Linq.DataContext>对象命名为你的项目基于.dbml 文件的名称。 对于此项目，<xref:System.Data.Linq.DataContext>对象命名为`northwindDataContext`。  
  
     你可以创建的实例<xref:System.Data.Linq.DataContext>在你的代码和查询表指定由 O/R 设计器。  
  
     在`Load`Form1 类的事件添加以下代码以查询公开为属性的数据上下文的表。 `Select`查询子句将创建一个新`CustomerInfo`而不是匿名类型的每个项的查询结果的类型。  
  
     [!code-vb[VbLINQToSQLHowTos#15](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_2.vb)]  
  
5.  按 F5 运行项目，并查看结果。  
  
## <a name="see-also"></a>请参阅  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [查询](../../../../visual-basic/language-reference/queries/queries.md)  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
 [DataContext 方法 （O/R 设计器）](/visualstudio/data-tools/datacontext-methods-o-r-designer)
