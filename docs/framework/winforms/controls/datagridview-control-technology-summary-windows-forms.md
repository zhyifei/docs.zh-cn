---
title: DataGridView 控件技术摘要（Windows 窗体）
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- data grids [Windows Forms], about data grids
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
ms.openlocfilehash: cafd832e7105540ae684dd1feb4b33ab74f72836
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528868"
---
# <a name="datagridview-control-technology-summary-windows-forms"></a>DataGridView 控件技术摘要（Windows 窗体）
本主题概述了 `DataGridView` 控件及支持其使用的类的相关信息。  
  
 以表格格式显示数据是一项任务，则可能需要频繁执行。 `DataGridView`控件可用于在网格中显示数据的完整解决方案。  
  
## <a name="keywords"></a>关键字  
 DataGridView、 BindingSource、 表、 单元格、 数据绑定、 虚拟模式  
  
## <a name="namespaces"></a>命名空间  
 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
 <xref:System.Data?displayProperty=nameWithType>  
  
## <a name="related-technologies"></a>相关技术  
 `BindingSource`  
  
## <a name="background"></a>背景  
 用户界面 (UI) 设计器经常发现需要向用户显示表格数据。 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]提供多种方式来在表或网格中显示数据。 `DataGridView`控件表示此项技术的 Windows 窗体应用程序的最新的变化情况。  
  
 `DataGridView`控件可以显示的数据存储区中的数据行。 支持许多类型的数据存储区。 数据存储区可以容纳简单、 非类型化数据，如一维数组，或它可以存放类型化的数据，如<xref:System.Data.DataSet>。 有关详细信息，请参阅[如何： 将数据绑定到 Windows 窗体 DataGridView 控件](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)。  
  
 `DataGridView` 控件提供一种以表格格式显示数据的功能强大且灵活的方法。 你可以使用控件显示的小型到大型数据集的只读或可编辑视图。  
  
 你可以扩展`DataGridView`通过多种方式在你的应用程序中构建自定义行为的控件。 例如，可以以编程方式指定自己的排序算法，并且可以创建自己的单元格类型。 可以通过在多个属性之间进行选择来轻松地自定义 `DataGridView` 控件的外观。 许多类型的数据存储区可以用作数据源，或`DataGridView`控件可以操作不使用绑定到该数据源。  
  
## <a name="implementing-datagridview-classes"></a>实现 DataGridView 类  
 有几种方法供你充分利用`DataGridView`控件的可扩展性功能。 你可以自定义通过事件和属性，该控件的许多方面，但某些自定义要求你创建新的类派生自现有`DataGridView`类。  
  
 最常用的基类`DataGridViewCell`和`DataGridViewColumn`。 可以派生您自己的单元格类从`DataGridViewCell`或任何其子类别。 尽管可以将任何单元格类型添加到任何列中，你将通常还派生从伴生列类`DataGridViewColumn`默认情况下承载自定义单元格类型的单元格。  
  
 你可以实现`IDataGridViewEditingCell`接口派生的单元格类创建具有编辑功能，但未承载在编辑模式的控件的单元格类型中。 若要创建可以在单元格处于编辑模式中承载的控件，则可以实现`IDataGridViewEditingControl`类中的接口派生自<xref:System.Windows.Forms.Control>。  
  
 有关详细信息，请参阅[如何： 自定义单元格和扩展他们行为和外观由 Windows 窗体 DataGridView 控件中的列](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)和[如何： 在 Windows 窗体 DataGridView 单元格中承载控件](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="datagridview-classes-at-a-glance"></a>DataGridView 类简介  
 <xref:System.Windows.Forms>  
  
|技术范围|类/接口/配置元素|  
|---------------------|-------------------------------------------------|  
|数据绑定|<xref:System.Windows.Forms.BindingSource>|  
|数据表示|<xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DataGridViewCell> 和派生的类<br /><br /> <xref:System.Windows.Forms.DataGridViewRow> 和派生的类<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> 和派生的类<br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|<xref:System.Windows.Forms.DataGridView> 扩展性|<xref:System.Windows.Forms.DataGridViewCell> 和派生的类<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> 和派生的类<br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## <a name="whats-new"></a>新增功能  
 <xref:System.Windows.Forms.DataGridView>控件旨在作为有关显示 Windows 窗体的表格数据的完整解决方案。 你应考虑使用<xref:System.Windows.Forms.DataGridView>控件之前其他解决方案中，如<xref:System.Windows.Forms.DataGrid>、 创作新的应用程序时。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 <xref:System.Windows.Forms.DataGridView>控件可在关闭结合工作<xref:System.Windows.Forms.BindingSource>组件。 此组件设计为窗体的主数据源。 它可以管理之间的交互<xref:System.Windows.Forms.DataGridView>控件和其数据源，而不考虑数据源类型。  
  
## <a name="see-also"></a>请参阅  
 [DataGridView 控件概述](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)  
 [DataGridView 控件体系结构](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 [保护连接信息](../../../../docs/framework/data/adonet/protecting-connection-information.md)
