---
title: DataGridView 控件体系结构（Windows 窗体）
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: a9fc1707b1691266d1844c411a08e7e8f35514ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="datagridview-control-architecture-windows-forms"></a>DataGridView 控件体系结构（Windows 窗体）
<xref:System.Windows.Forms.DataGridView>控制和及其相关的类旨在作为用于显示和编辑表格数据的灵活、 可扩展系统。 这些类都包含在<xref:System.Windows.Forms?displayProperty=nameWithType>命名空间，和它们的命名为与"DataGridView"前缀。  
  
## <a name="architecture-elements"></a>体系结构元素  
 主<xref:System.Windows.Forms.DataGridView>伴生类派生自<xref:System.Windows.Forms.DataGridViewElement>。 下面的对象模型阐释了<xref:System.Windows.Forms.DataGridViewElement>继承层次结构。  
  
 ![DataGridViewElement 对象模型](../../../../docs/framework/winforms/controls/media/datagridviewelement.gif "DataGridViewElement")  
DataGridViewElement 对象模型  
  
 <xref:System.Windows.Forms.DataGridViewElement>类提供对父级的引用<xref:System.Windows.Forms.DataGridView>控件，并具有<xref:System.Windows.Forms.DataGridViewElement.State%2A>属性，用于保存一个值，表示从值的组合<xref:System.Windows.Forms.DataGridViewElementStates>枚举。  
  
 以下各节描述了<xref:System.Windows.Forms.DataGridView>伴生类中更多详细信息。  
  
### <a name="datagridviewelementstates"></a>DataGridViewElementStates  
 <xref:System.Windows.Forms.DataGridViewElementStates>枚举包含以下值：  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 此枚举的值可以结合的按位逻辑运算符，因此<xref:System.Windows.Forms.DataGridViewElement.State%2A>属性可以同时 express 不止一个状态。 例如，<xref:System.Windows.Forms.DataGridViewElement>可以同时处于<xref:System.Windows.Forms.DataGridViewElementStates.Frozen>， <xref:System.Windows.Forms.DataGridViewElementStates.Selected>，和<xref:System.Windows.Forms.DataGridViewElementStates.Visible>。  
  
### <a name="cells-and-bands"></a>单元格和带区  
 <xref:System.Windows.Forms.DataGridView>控件包含两种基本类型的对象： 单元格和带区。 所有单元格派生自<xref:System.Windows.Forms.DataGridViewCell>基类。 带区，这两种<xref:System.Windows.Forms.DataGridViewColumn>和<xref:System.Windows.Forms.DataGridViewRow>，都派生自<xref:System.Windows.Forms.DataGridViewBand>基类。  
  
 <xref:System.Windows.Forms.DataGridView>控件互操作具有几个类，但最常用的类为<xref:System.Windows.Forms.DataGridViewCell>， <xref:System.Windows.Forms.DataGridViewColumn>，和<xref:System.Windows.Forms.DataGridViewRow>。  
  
### <a name="datagridviewcell"></a>该单元格  
 该单元格是否为交互的基本单元<xref:System.Windows.Forms.DataGridView>。 在单元格上, 居中显示，并通过单元格通常执行数据输入。 你可以通过使用访问单元格<xref:System.Windows.Forms.DataGridViewRow.Cells%2A>集合<xref:System.Windows.Forms.DataGridViewRow>类，并且你可以通过访问选定的单元格<xref:System.Windows.Forms.DataGridView.SelectedCells%2A>集合<xref:System.Windows.Forms.DataGridView>控件。 下面的对象模型说明了这种用法，并显示<xref:System.Windows.Forms.DataGridViewCell>继承层次结构。  
  
 ![DataGridViewCell 对象模型](../../../../docs/framework/winforms/controls/media/datagridviewcell.gif "DataGridViewCell")  
DataGridViewCell 对象模型  
  
 <xref:System.Windows.Forms.DataGridViewCell>类型是一个抽象基类，从中派生所有单元格类型。 <xref:System.Windows.Forms.DataGridViewCell> 其派生的类型不是 Windows 窗体控件，但某些主机 Windows 窗体控件。 任何支持的单元格的编辑功能通常由托管控件进行处理。  
  
 <xref:System.Windows.Forms.DataGridViewCell> 对象不控制它们自己的外观和绘制功能一样作为 Windows 窗体控件。 相反，<xref:System.Windows.Forms.DataGridView>负责的外观及其<xref:System.Windows.Forms.DataGridViewCell>对象。 你可以有明显的影响的外观和行为的单元格通过与进行交互<xref:System.Windows.Forms.DataGridView>控件的属性和事件。 如果有特殊要求的自定义项的功能超出<xref:System.Windows.Forms.DataGridView>控件，可以实现您自己的类派生自<xref:System.Windows.Forms.DataGridViewCell>或其被子类之一。  
  
 以下列表显示派生自的类<xref:System.Windows.Forms.DataGridViewCell>:  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewImageCell>  
  
-   <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
-   自定义单元格类型  
  
### <a name="datagridviewcolumn"></a>DataGridViewColumn  
 架构<xref:System.Windows.Forms.DataGridView>以表示控件的附加的数据存储区<xref:System.Windows.Forms.DataGridView>控件的列。 你可以访问<xref:System.Windows.Forms.DataGridView>控件的列使用<xref:System.Windows.Forms.DataGridView.Columns%2A>集合。 你可以通过使用访问所选的列<xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>集合。 下面的对象模型说明了这种用法，并显示<xref:System.Windows.Forms.DataGridViewColumn>继承层次结构。  
  
 ![DataGridViewColumn 对象模型](../../../../docs/framework/winforms/controls/media/datagridviewcolumn.gif "DataGridViewColumn")  
DataGridViewColumn 对象模型  
  
 某些关键字单元格类型具有相应的列类型。 这些都派生自<xref:System.Windows.Forms.DataGridViewColumn>基类。  
  
 以下列表显示派生自的类<xref:System.Windows.Forms.DataGridViewColumn>:  
  
-   <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
-   自定义列类型  
  
### <a name="datagridview-editing-controls"></a>DataGridView 编辑控件  
 通常支持高级编辑功能的单元格使用托管的控件派生自 Windows 窗体控件。 这些控件还实现<xref:System.Windows.Forms.IDataGridViewEditingControl>接口。 下面的对象模型演示了这些控件的用法。  
  
 ![DataGridView 编辑控件对象模型](../../../../docs/framework/winforms/controls/media/datagridviewediting.gif "DataGridViewEditing")  
DataGridView 编辑控件对象模型  
  
 提供了下列编辑控件<xref:System.Windows.Forms.DataGridView>控件：  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 有关创建自己的编辑控件的信息，请参阅[如何： 在 Windows 窗体 DataGridView 单元格的主机控件](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)。  
  
 下表阐释了单元格类型、 列类型和编辑控件之间的关系。  
  
|单元格类型|托管的控件|列类型|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|n/a|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|不可用|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|不可用|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|n/a|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a>DataGridViewRow  
 <xref:System.Windows.Forms.DataGridViewRow>类显示记录的数据字段从数据存储到<xref:System.Windows.Forms.DataGridView>附加控件。 你可以访问<xref:System.Windows.Forms.DataGridView>使用的控件的行<xref:System.Windows.Forms.DataGridView.Rows%2A>集合。 你可以通过访问所选的行<xref:System.Windows.Forms.DataGridView.SelectedRows%2A>集合。 下面的对象模型说明了这种用法，并显示<xref:System.Windows.Forms.DataGridViewRow>继承层次结构。  
  
 ![DataGridViewRow 对象模型](../../../../docs/framework/winforms/controls/media/datagridviewrow.gif "DataGridViewRow")  
DataGridViewRow 对象模型  
  
 可以派生您自己的类型从<xref:System.Windows.Forms.DataGridViewRow>类，虽然这通常不会有必要。 <xref:System.Windows.Forms.DataGridView>控件具有多个行相关的事件和自定义的行为的属性及其<xref:System.Windows.Forms.DataGridViewRow>对象。  
  
 如果你启用<xref:System.Windows.Forms.DataGridView>控件的<xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A>属性，用于添加新行的特殊行显示为最后一行。 此行属于<xref:System.Windows.Forms.DataGridView.Rows%2A>集合，但它具有特殊可能需要你关注的功能。 有关详细信息，请参阅[使用 Windows 窗体 DataGridView 控件中的新记录行](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)。  
  
## <a name="see-also"></a>请参阅  
 [DataGridView 控件概述](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)  
 [自定义 Windows 窗体 DataGridView 控件](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [在 Windows 窗体 DataGridView 控件中对新记录使用行](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
