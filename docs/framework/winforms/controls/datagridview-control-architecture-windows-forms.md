---
title: DataGridView 控件体系结构
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: 2e1884383cca87f8d4ff84f486e2b29761a0c55d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742526"
---
# <a name="datagridview-control-architecture-windows-forms"></a>DataGridView 控件体系结构（Windows 窗体）
<xref:System.Windows.Forms.DataGridView> 控件及其相关类被设计为用于显示和编辑表格数据的灵活、可扩展的系统。 这些类都包含在 <xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间中，它们都是用 "DataGridView" 前缀命名的。  
  
## <a name="architecture-elements"></a>体系结构元素  
 主 <xref:System.Windows.Forms.DataGridView> 伴生类派生自 <xref:System.Windows.Forms.DataGridViewElement>。 以下对象模型说明了 <xref:System.Windows.Forms.DataGridViewElement> 继承层次结构。  
  
 ![显示 DataGridViewElement 对象模型层次结构的关系图。](./media/datagridview-control-architecture-windows-forms/datagridviewelement-object-model.gif)  
  
 <xref:System.Windows.Forms.DataGridViewElement> 类提供对父 <xref:System.Windows.Forms.DataGridView> 控件的引用，并且具有 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 属性，该属性包含一个值，该值表示 <xref:System.Windows.Forms.DataGridViewElementStates> 枚举中的值的组合。  
  
 以下部分更详细地介绍了 <xref:System.Windows.Forms.DataGridView> 伴生类。  
  
### <a name="datagridviewelementstates"></a>DataGridViewElementStates  
 <xref:System.Windows.Forms.DataGridViewElementStates> 枚举包含以下值：  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 此枚举的值可以与按位逻辑运算符组合在一起，因此 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 属性可以同时表示多个状态。 例如，可以同时 <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>、<xref:System.Windows.Forms.DataGridViewElementStates.Selected>和 <xref:System.Windows.Forms.DataGridViewElementStates.Visible><xref:System.Windows.Forms.DataGridViewElement>。  
  
### <a name="cells-and-bands"></a>单元和带区  
 <xref:System.Windows.Forms.DataGridView> 控件包含两种基本类型的对象：单元格和带区。 所有单元均派生自 <xref:System.Windows.Forms.DataGridViewCell> 的基类。 两种类型的带区（<xref:System.Windows.Forms.DataGridViewColumn> 和 <xref:System.Windows.Forms.DataGridViewRow>）均派生自 <xref:System.Windows.Forms.DataGridViewBand> 基类。  
  
 <xref:System.Windows.Forms.DataGridView> 控件与多个类进行互操作，但最常见的是 <xref:System.Windows.Forms.DataGridViewCell>、<xref:System.Windows.Forms.DataGridViewColumn>和 <xref:System.Windows.Forms.DataGridViewRow>。  
  
### <a name="datagridviewcell"></a>DataGridViewCell  
 单元是 <xref:System.Windows.Forms.DataGridView>的基本交互单位。 显示在单元格中居中，数据输入通常通过单元格执行。 您可以通过使用 <xref:System.Windows.Forms.DataGridViewRow> 类的 <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> 集合来访问单元，您可以通过使用 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 集合来访问所选单元。 以下对象模型说明了这种用法，并显示 <xref:System.Windows.Forms.DataGridViewCell> 继承层次结构。  
  
 ![显示 DataGridViewCell 对象模型层次结构的关系图。](./media/datagridview-control-architecture-windows-forms/datagridviewcell-object-model.gif)  
  
 <xref:System.Windows.Forms.DataGridViewCell> 类型是一个抽象基类，所有单元类型都派生自该基类。 <xref:System.Windows.Forms.DataGridViewCell> 及其派生类型不是 Windows 窗体控件，而是某些宿主 Windows 窗体控件。 单元支持的所有编辑功能通常由寄宿控件处理。  
  
 <xref:System.Windows.Forms.DataGridViewCell> 对象不以与 Windows 窗体控件相同的方式来控制其自身外观和绘制功能。 相反，<xref:System.Windows.Forms.DataGridView> 负责其 <xref:System.Windows.Forms.DataGridViewCell> 对象的外观。 通过与 <xref:System.Windows.Forms.DataGridView> 控件的属性和事件交互，可以显著影响单元格的外观和行为。 如果对超出 <xref:System.Windows.Forms.DataGridView> 控件功能的自定义项有特殊要求，则可以实现自己的类，该类派生自 <xref:System.Windows.Forms.DataGridViewCell> 或该类的一个子类。  
  
 以下列表显示了从 <xref:System.Windows.Forms.DataGridViewCell>派生的类：  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
- <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewImageCell>  
  
- <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
- 自定义单元类型  
  
### <a name="datagridviewcolumn"></a>DataGridViewColumn  
 <xref:System.Windows.Forms.DataGridView> 控件的附加数据存储的架构以 <xref:System.Windows.Forms.DataGridView> 控件的列表示。 您可以通过使用 <xref:System.Windows.Forms.DataGridView.Columns%2A> 集合访问 <xref:System.Windows.Forms.DataGridView> 控件的列。 您可以通过使用 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 集合来访问所选列。 以下对象模型说明了这种用法，并显示 <xref:System.Windows.Forms.DataGridViewColumn> 继承层次结构。  
  
 ![显示 DataGridViewColumn 对象模型层次结构的关系图。](./media/datagridview-control-architecture-windows-forms/datagridviewcolumn-object-model.gif)  
  
 某些键单元类型具有相应的列类型。 这些类派生自 <xref:System.Windows.Forms.DataGridViewColumn> 的基类。  
  
 以下列表显示了从 <xref:System.Windows.Forms.DataGridViewColumn>派生的类：  
  
- <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
- 自定义列类型  
  
### <a name="datagridview-editing-controls"></a>DataGridView 编辑控件  
 支持高级编辑功能的单元通常使用派生自 Windows 窗体控件的托管控件。 这些控件还实现 <xref:System.Windows.Forms.IDataGridViewEditingControl> 接口。 以下对象模型说明了这些控件的用法。  
  
 ![显示 DataGridView 编辑控件对象模型层次结构的关系图。](./media/datagridview-control-architecture-windows-forms/datagridviewediting-object-model.gif)  
  
 以下编辑控件随 <xref:System.Windows.Forms.DataGridView> 控件一起提供：  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 有关创建自己的编辑控件的信息，请参阅[如何：在 Windows 窗体 DataGridView 单元格中承载控件](how-to-host-controls-in-windows-forms-datagridview-cells.md)。  
  
 下表说明了单元类型、列类型和编辑控件之间的关系。  
  
|单元类型|托管控件|列类型|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|无|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|无|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|无|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|无|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a>DataGridViewRow  
 <xref:System.Windows.Forms.DataGridViewRow> 类显示 <xref:System.Windows.Forms.DataGridView> 控件附加到的数据存储中的记录的数据字段。 您可以通过使用 <xref:System.Windows.Forms.DataGridView.Rows%2A> 集合来访问 <xref:System.Windows.Forms.DataGridView> 控件的行。 您可以通过使用 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 集合来访问所选行。 以下对象模型说明了这种用法，并显示 <xref:System.Windows.Forms.DataGridViewRow> 继承层次结构。  
  
 ![显示 DataGridViewRow 对象模型层次结构的关系图。](./media/datagridview-control-architecture-windows-forms/datagridviewrow-object-model.gif)
  
 你可以从 <xref:System.Windows.Forms.DataGridViewRow> 类派生你自己的类型，但通常不需要这样做。 <xref:System.Windows.Forms.DataGridView> 控件具有几个与行相关的事件和属性，用于自定义其 <xref:System.Windows.Forms.DataGridViewRow> 对象的行为。  
  
 如果启用 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 属性，则添加新行的特殊行将显示为最后一行。 此行是 <xref:System.Windows.Forms.DataGridView.Rows%2A> 集合的一部分，但它具有可能需要注意的特殊功能。 有关详细信息，请参阅在[Windows 窗体 DataGridView 控件中使用新记录行](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)。  
  
## <a name="see-also"></a>另请参阅

- [DataGridView 控件概述](datagridview-control-overview-windows-forms.md)
- [自定义 Windows 窗体 DataGridView 控件](customizing-the-windows-forms-datagridview-control.md)
- [在 Windows 窗体 DataGridView 控件中对新记录使用行](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
