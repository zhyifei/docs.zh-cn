---
title: 具有内置所有者描述支持的控件
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], owner
- drawing [Windows Forms], custom
- controls [Windows Forms], changing appearance
- custom drawing
- owner drawing
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
ms.openlocfilehash: f0d4b99f9ee0134fc7334a941dd5ef4fd7ba3df3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930197"
---
# <a name="controls-with-built-in-owner-drawing-support"></a>具有内置所有者描述支持的控件
Windows 窗体中的所有者描述（也称为自定义绘图）是一种更改特定控件的可视外观的技术。  
  
> [!NOTE]
> 本主题中的 "控件" 一词用于表示从<xref:System.Windows.Forms.Control>或<xref:System.ComponentModel.Component>派生的类。  
  
 通常, Windows 通过使用属性设置 (例如<xref:System.Windows.Forms.Control.BackColor%2A> ) 来自动处理绘制, 以确定控件的外观。 使用所有者描述，可接管绘制进程，更改无法使用属性更改的外观元素。 例如，许多控件都允许设置文本的显示颜色，但仅限于一种颜色。 通过所有者描述，可执行诸如用黑色和红色分别显示部分文本等操作。  
  
 实际上，所有者描述类似于在窗体上绘制图形。 例如, 您可以在窗体<xref:System.Windows.Forms.Control.Paint>事件的处理程序中使用图形方法来`ListBox`模拟控件, 但您必须编写自己的代码来处理所有用户交互。 借助所有者描述，该控件可使用代码来绘制其内容，但仍保留其所有固有功能。 可使用图形方法绘制控件中的每一项，或在每一项的其他方面使用默认外观时自定义每一项的某些方面。  
  
## <a name="owner-drawing-in-windows-forms-controls"></a>Windows 窗体控件中的所有者描述  
 若要在支持所有者描述的控件中执行此功能，通常需设置一个属性并处理一个或多个事件。  
  
 支持所有者描述的大多数控件都具有 `OwnerDraw` 或 `DrawMode` 属性，用于指示控件对自身进行绘制时是否引发其绘制相关事件。  
  
 不具有 `OwnerDraw` 或 `DrawMode` 属性的控件包括 `DataGridView` 控件（提供自动发生的绘制事件）和 `ToolStrip` 事件（使用具有其自身绘制相关事件的外部呈现类绘制而成）。  
  
 有许多不同类型的绘制事件，但通常发生的典型绘制事件是在控件中绘制单个项。 事件处理程序接收一个 `EventArgs` 对象，其中包含与要绘制的项以及可用于绘制该项的工具有关的信息。 例如, 此对象通常包含其父集合中的项的索引号, <xref:System.Drawing.Rectangle>即指示该项的显示边界的, <xref:System.Drawing.Graphics>以及用于调用 paint 方法的对象。 对于某些事件，`EventArgs` 对象提供有关项和方法的附加信息，默认情况下可调用这些方法来绘制该项的某些方面，例如背景和聚焦框。  
  
 若要创建包含所有者描述的自定义项的可重用控件，请创建一个派生自控件类（支持所有者描述）的新类。 不需要对绘制事件进行处理，只需在新类中包含所有者描述代码，并替代相应的 `On`*EventName* 方法。 在这种情况下，务必调用基类 `On`*EventName* 方法，以便使用该控件的用户能够处理所有者描述事件并提供其他自定义内容。  
  
 以下 Windows 窗体控件在所有版本的 .NET Framework 中都支持所有者描述：  
  
- <xref:System.Windows.Forms.ListBox>  
  
- <xref:System.Windows.Forms.ComboBox>  
  
- <xref:System.Windows.Forms.MenuItem>(由<xref:System.Windows.Forms.MainMenu>和<xref:System.Windows.Forms.ContextMenu>使用)  
  
- <xref:System.Windows.Forms.TabControl>  
  
 以下控件仅支持 .NET Framework 2.0 中的所有者描述:  
  
- <xref:System.Windows.Forms.ToolTip>  
  
- <xref:System.Windows.Forms.ListView>  
  
- <xref:System.Windows.Forms.TreeView>  
  
 以下控件支持所有者描述, 并且是 .NET Framework 2.0 中的新增内容:  
  
- <xref:System.Windows.Forms.DataGridView>  
  
- <xref:System.Windows.Forms.ToolStrip>  
  
 以下各节进一步详述了以上每个控件。  
  
### <a name="listbox-and-combobox-controls"></a>ListBox 和 ComboBox 控件  
 利用<xref:System.Windows.Forms.ListBox> 和<xref:System.Windows.Forms.ComboBox>控件, 您可以在控件中绘制所有项, 无论是在同一大小还是在不同大小。  
  
> [!NOTE]
> 尽管控件是<xref:System.Windows.Forms.ListBox>从控件派生的, 但它不支持所有者描述。 <xref:System.Windows.Forms.CheckedListBox>  
  
 若要以相同大小绘制每个项, `DrawMode`请将<xref:System.Windows.Forms.DrawMode.OwnerDrawFixed>属性设置为`DrawItem`并处理事件。  
  
 若要使用不同的大小绘制每个项, `DrawMode`请将<xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>属性设置为, `MeasureItem`并`DrawItem`处理和事件。 使用 `MeasureItem` 事件可在项发生 `DrawItem` 事件之前指示该项的大小。  
  
 有关详细信息（包括代码示例），请参阅以下主题：  
  
- <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=nameWithType>  
  
- [如何：在 ComboBox 控件中创建大小可变的文本](how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a>MenuItem 组件  
 组件表示<xref:System.Windows.Forms.MainMenu> 或<xref:System.Windows.Forms.ContextMenu>组件中的单个菜单项。 <xref:System.Windows.Forms.MenuItem>  
  
 若要绘制<xref:System.Windows.Forms.MenuItem>, 请将`OwnerDraw`其属性`true`设置为, `DrawItem`并处理其事件。 若要在发生 `DrawItem` 事件之前自定义菜单项的大小，请处理该项的 `MeasureItem` 事件。  
  
 有关详细信息（包括代码示例），请参阅以下参考主题：  
  
- <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=nameWithType>  
  
### <a name="tabcontrol-control"></a>TabControl 控件  
 <xref:System.Windows.Forms.TabControl>控件使您可以在控件中绘制各个选项卡。 所有者描述只影响选项卡;<xref:System.Windows.Forms.TabPage>内容不受影响。  
  
 若要在中<xref:System.Windows.Forms.TabControl>绘制每个选项卡, 请<xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> `DrawMode`将`DrawItem`属性设置为并处理事件。 如果选项卡在控件中可见，则对于每个选项卡，此事件只发生一次。  
  
 有关详细信息（包括代码示例），请参阅以下参考主题：  
  
- <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=nameWithType>  
  
### <a name="tooltip-component"></a>ToolTip 组件  
 <xref:System.Windows.Forms.ToolTip>组件使您可以在显示时绘制整个工具提示。  
  
 若要绘制<xref:System.Windows.Forms.ToolTip>, 请将`OwnerDraw`其属性`true`设置为, `Draw`并处理其事件。 若<xref:System.Windows.Forms.ToolTip>要在`Draw` 事件发生<xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A>之前自定义的大小, 请处理事件,并在事件处理程序中设置属性。`Popup`  
  
 有关详细信息（包括代码示例），请参阅以下参考主题：  
  
- <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=nameWithType>  
  
### <a name="listview-control"></a>ListView 控件  
 <xref:System.Windows.Forms.ListView>控件使您可以在控件中绘制各个项、子项和列标题。  
  
 若要在控件中启用所有者描述，请将 `OwnerDraw` 属性设置为 `true`。  
  
 若要绘制控件中的每个项，请处理 `DrawItem` 事件。  
  
 若要在<xref:System.Windows.Forms.ListView.View%2A>属性设置为<xref:System.Windows.Forms.View.Details>时绘制控件中的每个子项或列标题, 请`DrawSubItem`处理`DrawColumnHeader`和事件。  
  
 有关详细信息（包括代码示例），请参阅以下参考主题：  
  
- <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=nameWithType>  
  
### <a name="treeview-control"></a>TreeView 控件  
 <xref:System.Windows.Forms.TreeView>控件使您可以在控件中绘制各个节点。  
  
 若要仅绘制每个节点中显示的文本, `DrawMode`请将<xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText>属性设置为`DrawNode` , 并处理事件以绘制文本。  
  
 若要绘制每个节点的所有元素, `DrawMode`请将<xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll>属性设置为`DrawNode` , 并处理事件以绘制您需要的任何元素, 例如文本、图标、复选框、加号和减号以及连接节点的线条。  
  
 有关详细信息（包括代码示例），请参阅以下参考主题：  
  
- <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=nameWithType>  
  
### <a name="datagridview-control"></a>DataGridView 控件  
 <xref:System.Windows.Forms.DataGridView>控件使您可以在控件中绘制单个单元和行。  
  
 若要绘制各个单元格，请处理 `CellPainting` 事件。  
  
 若要绘制各个行或行的元素，请择一/同时处理 `RowPrePaint` 和 `RowPostPaint` 事件。 `RowPrePaint` 事件发生在绘制行中的单元格之前，`RowPostPaint` 事件发生在绘制单元格之后。 可同时处理这两个事件和 `CellPainting` 事件以分别绘制行背景、各个单元格和行前景，或者可在需要的位置提供特定自定义内容并对行中的其他元素使用默认显示。  
  
 有关详细信息（包括代码示例），请参阅以下主题：  
  
- <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
- <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
- <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
- [如何：自定义 Windows 窗体 DataGridView 控件中的单元格的外观](customize-the-appearance-of-cells-in-the-datagrid.md)  
  
- [如何：自定义 Windows 窗体 DataGridView 控件中行的外观](customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a>ToolStrip 控件  
 <xref:System.Windows.Forms.ToolStrip>使用派生控件可自定义其外观的任何方面。  
  
 若<xref:System.Windows.Forms.ToolStrip>要为控件提供自定义呈现, `Renderer`请将<xref:System.Windows.Forms.ToolStrip>、 <xref:System.Windows.Forms.ToolStripManager>、 <xref:System.Windows.Forms.ToolStripPanel>或<xref:System.Windows.Forms.ToolStripContentPanel>的属性设置为`ToolStripRenderer`对象, 并处理由`ToolStripRenderer`类。 `Renderer`或者, 将属性设置为从`ToolStripRenderer`、 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>或<xref:System.Windows.Forms.ToolStripSystemRenderer>派生的类的实例, 该实例实现或重写特定`On`的*事件名称*方法。  
  
 有关详细信息（包括代码示例），请参阅以下主题：  
  
- <xref:System.Windows.Forms.ToolStripRenderer>  
  
- [如何：在 Windows 窗体中为 ToolStrip 控件创建和设置自定义呈现器](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
- [如何：自定义绘制 ToolStrip 控件](how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a>请参阅

- [在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)
