---
title: 如何：使用 Windows 窗体 BindingSource 组件对 ADO.NET 数据进行排序和筛选
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
ms.openlocfilehash: ae331ca9e3fd2aed654659e11434454874eff8fa
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960427"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>如何：使用 Windows 窗体 BindingSource 组件对 ADO.NET 数据进行排序和筛选
可以<xref:System.Windows.Forms.BindingSource> 通过和<xref:System.Windows.Forms.BindingSource.Filter%2A>属性公开控件的排序和筛选功能。 <xref:System.Windows.Forms.BindingSource.Sort%2A> 如果基础数据源是<xref:System.ComponentModel.IBindingList>, 则可以应用简单排序, 如果数据源<xref:System.ComponentModel.IBindingListView>是, 则可以应用筛选和高级排序。 属性需要标准 ADO.NET 语法: 一个字符串, 表示数据源中的数据列的名称, `ASC`后跟或`DESC`以指示列表应按升序排序还是按降序排序。 <xref:System.Windows.Forms.BindingSource.Sort%2A> 您可以通过用逗号分隔符分隔每一列来设置高级排序或多列排序。 <xref:System.Windows.Forms.BindingSource.Filter%2A>属性采用字符串表达式。  
  
> [!NOTE]
> 将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。 若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。 有关详细信息，请参阅[保护连接信息](../../data/adonet/protecting-connection-information.md)。  
  
### <a name="to-filter-data-with-the-bindingsource"></a>用 BindingSource 筛选数据  
  
- <xref:System.Windows.Forms.BindingSource.Filter%2A>将属性设置为所需的 expression。  
  
     在下面的代码示例中, 表达式是列名, 后跟要用于该列的值。  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>用 BindingSource 对数据进行排序  
  
1. 将属性设置为所需的列名, `ASC`并将其设置`DESC`为或以指示升序或降序。 <xref:System.Windows.Forms.BindingSource.Sort%2A>  
  
2. 用逗号分隔多个列。  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>示例  
 下面的代码示例将 Northwind 示例数据库的 Customers 表中的数据加载到<xref:System.Windows.Forms.DataGridView>控件中, 并对显示的数据进行筛选和排序。  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 若要运行此示例, 请将代码<xref:System.Windows.Forms.BindingSource>粘贴到包含名为`BindingSource1`的和名<xref:System.Windows.Forms.DataGridView> `dataGridView1`为的的窗体中。 处理窗<xref:System.Windows.Forms.Form.Load>体的事件, 并在`InitializeSortedFilteredBindingSource` load 事件处理程序方法中调用。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- [如何：安装示例数据库](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))
- [BindingSource 组件](bindingsource-component.md)
