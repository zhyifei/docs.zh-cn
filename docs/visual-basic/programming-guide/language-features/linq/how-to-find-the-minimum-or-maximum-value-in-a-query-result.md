---
title: 如何：使用 LINQ 查找查询结果中的最小值或最大值
ms.date: 07/20/2015
helpviewer_keywords:
- max operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- minimum values [LINQ in Visual Basic]
- min operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], minimum and maximum values
- Max property
- maximum values [LINQ in Visual Basic]
- Aggregate clause [Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 238b763b-7dcd-4b14-8050-b65500a4f71c
ms.openlocfilehash: ef5f218cdcc7275f616486110825ad0b9df11cc3
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112357"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a>如何：使用 LINQ 查找查询结果中的最小值或最大值 (Visual Basic)
语言集成查询 （LINQ） 使访问数据库信息和执行查询变得容易。  
  
 下面的示例演示如何创建执行针对 SQL Server 数据库的查询的新应用程序。 该示例通过使用`Aggregate`和`Group By`子句确定结果的最小值和最大值。 有关详细信息，请参阅[聚合子句](../../../../visual-basic/language-reference/queries/aggregate-clause.md)和[按子句分组](../../../../visual-basic/language-reference/queries/group-by-clause.md)。  
  
 本主题中的示例使用北风示例数据库。 如果你的开发计算机上没有此数据库，可以从 Microsoft 下载中心进行下载。 有关说明，请参阅[下载示例数据库](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="create-a-connection-to-a-database"></a>创建与数据库的连接  
  
1. 在可视化工作室中，通过单击 **"视图"** 菜单上**的服务器资源管理器**/**数据库资源管理器**打开**服务器资源管理器**/**数据库资源管理器**。  
  
2. 右键单击**服务器资源管理器**/**数据库资源管理器**中**的数据连接**，然后单击"**添加连接**"。  
  
3. 指定到北风样本数据库的有效连接。  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>将包含 LINQ 的项目添加到 SQL 文件  
  
1. 在可视化工作室中，在 **"文件"** 菜单上，指向 **"新建"，** 然后单击"**项目**"。 选择可视化基本**窗口窗体应用程序**作为项目类型。  
  
2. 在 **“项目”** 菜单上，单击 **“添加新项”**。 选择**LINQ 到 SQL 类**项模板。  
  
3. 将该文件命名为 `northwind.dbml`。 单击 **“添加”**。 为北风.dbml 文件打开对象关系设计器（O/R 设计器）。  
  
## <a name="add-tables-to-query-to-the-or-designer"></a>将表添加到 O/R 设计器  
  
1. 在**服务器资源管理器**/**数据库资源管理器中**，展开与北风数据库的连接。 展开 **“表”** 文件夹。  
  
     如果已关闭 O/R 设计器，则可以通过双击之前添加的 Northwind.dbml 文件重新打开它。  
  
2. 单击"客户"表并将其拖动到设计器的左侧窗格。 单击"订单"表并将其拖动到设计器的左侧窗格。  
  
     设计器为项目`Customer`创建新`Order`对象和对象。 请注意，设计器会自动检测表之间的关系，并为相关对象创建子属性。 例如，IntelliSense 将显示`Customer`该对象具有与该客户`Orders`相关的所有订单的属性。  
  
3. 保存更改并关闭设计器。  
  
4. 保存你的项目。  
  
## <a name="add-code-to-query-the-database-and-display-the-results"></a>添加代码以查询数据库并显示结果  
  
1. 从**工具箱**中<xref:System.Windows.Forms.DataGridView>，将控件拖动到项目的默认 Windows 窗体窗体 Form1。  
  
2. 双击 Form1 可向窗体`Load`的事件添加代码。  
  
3. 将表添加到 O/R 设计器时，设计器会<xref:System.Data.Linq.DataContext>为项目添加对象。 除了每个表的各个对象和集合之外，此对象还包含访问这些表必须具有的代码。 项目<xref:System.Data.Linq.DataContext>的对象是根据 .dbml 文件的名称命名的。 对于此项目，<xref:System.Data.Linq.DataContext>对象名为`northwindDataContext`。  
  
     您可以在代码中创建 的<xref:System.Data.Linq.DataContext>实例，并查询 O/R 设计器指定的表。  
  
     将以下代码添加到事件`Load`。 此代码查询作为数据上下文的属性公开的表，并确定结果的最小值和最大值。 该示例使用`Aggregate`子句查询单个结果，`Group By`子句显示分组结果的平均值。  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. 按**F5**运行项目并查看结果。  
  
## <a name="see-also"></a>另请参阅

- [Linq](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [查询](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext 方法（O/R 设计器）](/visualstudio/data-tools/datacontext-methods-o-r-designer)
