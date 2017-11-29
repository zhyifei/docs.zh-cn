---
title: "Windows 窗体 DataGridView 控件中的大小调整选项"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], row sizing
- data grids [Windows Forms], column sizing
- DataGridView control [Windows Forms], column sizing
- DataGridView control [Windows Forms], sizing options
- data grids [Windows Forms], row sizing
- data grids [Windows Forms], sizing options
ms.assetid: a5620a9c-0d06-41e3-8934-c25ddb16c9e6
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1a4819f0c4596c34312bf689d57cca687641d6a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="sizing-options-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的大小调整选项
<xref:System.Windows.Forms.DataGridView>行、 列和标头可以更改由于许多不同的匹配项的大小。 下表显示了这些情况。  
  
|匹配项|描述|  
|----------------|-----------------|  
|用户大小调整|用户可以通过拖动或双击行、 列或标头的分隔线进行大小调整。|  
|控件调整大小|在列填充模式列宽度控件宽度发生更改时更改;例如，当该控件停靠到其父窗体和用户调整窗体。|  
|单元格值更改|在基于内容的自动调整大小模式下，大小更改以适应新的显示值。|  
|方法调用|以编程方式基于内容的大小调整，能让你将在方法调用时基于单元格的值的机会大小调整。|  
|属性设置|你还可以设置特定的高度和宽度的值。|  
  
 默认情况下，用户调整大小启用、 禁用自动调整大小，则和单元格的宽度大于其列的值将被剪裁。  
  
 下表显示方案，你可以使用若要调整的默认行为，或使用特定的大小调整选项来实现特定的效果。  
  
|方案|实现|  
|--------------|--------------------|  
|使用显示的列填充模式同样大小相对较小占用而不显示水平滚动条控件的整个宽度的列数中的数据。|将 <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> 属性设置为 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>。|  
|使用列填充模式显示不同大小的值。|将 <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> 属性设置为 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>。 通过将列设置初始化相对列宽<xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>属性或通过调用控件<xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>方法之后使用数据填充控件。|  
|使用的不同重要性的值的列填充模式。|将 <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> 属性设置为 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>。 设置大<xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A>必须始终显示一些其数据或使用大小调整选项之外的列填充模式的特定列的值。|  
|使用列填充模式以避免显示控件背景。|设置<xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>到最后一列的属性<xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill>和其他调整大小选项用于其他列。 如果其他列使用过多的可用空间，设置<xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A>的最后一列的属性。|  
|显示固定宽度的列，如图标或 ID 列。|设置<xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>到<xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None>和<xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A>到<xref:System.Windows.Forms.DataGridViewTriState.False>的列。 通过设置初始化其宽度<xref:System.Windows.Forms.DataGridViewColumn.Width%2A>属性或通过调用控件<xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A>方法之后使用数据填充控件。|  
|单元格内容更改来避免剪辑并优化空间使用情况的时，会自动调整大小。|自动调整大小属性设置为一个值，表示基于内容的大小调整模式。 若要避免对性能产生负面影响，在处理大量数据时，使用计算显示的行的大小调整模式。|  
|调整大小以容纳中显示的行，以避免性能损失，使用多行时的值。|使用自动或以编程方式调整大小的相应调整大小模式的枚举值。 若要调整大小以容纳新显示的行中的值，在滚动时，调用调整大小的方法<xref:System.Windows.Forms.DataGridView.Scroll>事件处理程序。 若要自定义用户双击调整大小，以便仅显示的行中的值确定新的大小，调用调整大小的方法<xref:System.Windows.Forms.DataGridView.RowDividerDoubleClick>或<xref:System.Windows.Forms.DataGridView.ColumnDividerDoubleClick>事件处理程序。|  
|调整大小以适应仅在特定时间以避免性能损失或启用用户调整大小的单元格内容。|事件处理程序中调用基于内容的大小调整方法。 例如，使用<xref:System.Windows.Forms.DataGridView.DataBindingComplete>事件来绑定后，初始化大小并处理<xref:System.Windows.Forms.DataGridView.CellValidated>或<xref:System.Windows.Forms.DataGridView.CellValueChanged>要调整大小，以弥补用户编辑或更改事件中绑定的数据源。|  
|调整行高对于多行的单元格内容。|确保列宽适用于显示的文本段落，并使用自动或以编程方式基于内容的行大小调整调整高度。 另外，请确保使用多行内容的单元格的显示使用<xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>单元格的样式值<xref:System.Windows.Forms.DataGridViewTriState.True>。<br /><br /> 通常，将使用自动列大小调整模式来维护列宽，或将它们设置为特定的宽度之前调整行高。|  
  
## <a name="resizing-with-the-mouse"></a>使用鼠标调整大小  
 默认情况下，用户可以调整行、 列和不使用自动调整大小模式，基于单元格的值的标头大小。 若要防止用户与其他模式，如列填充模式中，调整大小将设置一个或多个以下<xref:System.Windows.Forms.DataGridView>属性：  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
 你也可阻止用户调整单个行或列，通过设置其<xref:System.Windows.Forms.DataGridViewBand.Resizable%2A>属性。 默认情况下，<xref:System.Windows.Forms.DataGridViewBand.Resizable%2A>属性值根据<xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>列的属性值和<xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>行的属性值。 如果显式设置<xref:System.Windows.Forms.DataGridViewBand.Resizable%2A>到<xref:System.Windows.Forms.DataGridViewTriState.True>或<xref:System.Windows.Forms.DataGridViewTriState.False>，但是，控制值的行和列的指定的值替代。 设置<xref:System.Windows.Forms.DataGridViewBand.Resizable%2A>到<xref:System.Windows.Forms.DataGridViewTriState.NotSet>还原继承。  
  
 因为<xref:System.Windows.Forms.DataGridViewTriState.NotSet>还原值继承，<xref:System.Windows.Forms.DataGridViewBand.Resizable%2A>属性将永远不会返回<xref:System.Windows.Forms.DataGridViewTriState.NotSet>值，除非行或列尚未添加到<xref:System.Windows.Forms.DataGridView>控件。 如果你需要确定是否<xref:System.Windows.Forms.DataGridViewBand.Resizable%2A>行或列的属性值继承，请查看其<xref:System.Windows.Forms.DataGridViewElement.State%2A>属性。 如果<xref:System.Windows.Forms.DataGridViewElement.State%2A>值包括<xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>标志，<xref:System.Windows.Forms.DataGridViewBand.Resizable%2A>不继承属性值。  
  
## <a name="automatic-sizing"></a>自动调整大小  
 有两种类型中的自动调整大小的<xref:System.Windows.Forms.DataGridView>控件： 列填充模式和基于内容的自动调整大小。  
  
 列填充模式导致要填充的控件的显示区域宽度的控件中可见的列。 有关此模式的详细信息，请参阅[在 Windows 窗体 DataGridView 控件中的列填充模式](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)。  
  
 你还可以配置行、 列和标头，以便自动调整其大小以适应其单元格内容。 在这种情况下，单元格内容更改时发生大小调整。  
  
> [!NOTE]
>  当用户编辑单元格值，但未发生更改外部的缓存的值时维护时使用的虚拟模式的自定义数据缓存中的单元值，如果时发生自动调整大小<xref:System.Windows.Forms.DataGridView.CellValuePushed>事件处理程序。 在这种情况下，调用<xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A>方法，以强制要更新的单元格显示并应用当前的自动调整大小模式的控件。  
  
 如果仅对一个维度启用了基于内容的自动调整大小-的是，对行但没有为列，或列，但不对行-和<xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>还有其他维度发生更改时，也会发生已启用，大小调整。 例如，如果行但没有为列配置为自动调整大小和<xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>是启用，用户可以拖动列分隔符更改列的宽度和以便仍然能够完全显示单元格内容，将自动调整行高。  
  
 如果你配置行和基于内容的自动调整大小的列和<xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>启用，则<xref:System.Windows.Forms.DataGridView>控件将调整大小，无论何时单元格内容更改，并计算新的大小的情况下将使用理想的单元格高度到宽度的比例。  
  
 若要配置有关标头和行和列不会重写控件的值的大小调整模式，设置一个或多个以下<xref:System.Windows.Forms.DataGridView>属性：  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A>  
  
 若要重写控件的单个列的列大小调整模式，设置其<xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>属性的值以外的其他<xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>。 列的大小调整模式实际上由其<xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A>属性。 此属性的值基于列的<xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>属性值，除非该值是<xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>，在这种情况下控件的<xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>继承值。  
  
 使用基于内容的自动调整大小时要格外小心使用大量的数据时。 若要避免性能损失，使用计算大小仅根据所显示的行，而不是分析控件中的每一行自动调整大小模式。 为获得最佳性能，使用以编程方式调整大小相反，以便你可以调整大小在特定时间，如新数据之后立即将加载。  
  
 基于内容的自动调整大小模式行、 列或具有隐藏的行或列设置的标头不会影响<xref:System.Windows.Forms.DataGridViewBand.Visible%2A>属性或控件<xref:System.Windows.Forms.DataGridView.RowHeadersVisible%2A>或<xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A>属性设置为`false`。 例如，如果列处于隐藏状态之后它自动调整大小以适应一个大型的单元格值,，隐藏的列将不更改其大小如果删除包含大型的单元格的值的行。 自动调整大小不会在发生可见性更改，因此无法更改列<xref:System.Windows.Forms.DataGridViewColumn.Visible%2A>属性改回`true`不会强制它重新计算其大小以适应当前的内容。  
  
 编程基于内容调整大小会影响行、 列和标头而不考虑其可见性。  
  
## <a name="programmatic-resizing"></a>以编程方式调整大小  
 禁用自动调整大小后，可以以编程方式设置的确切的宽度或高度的行、 列或标头通过以下属性：  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
  
 以编程方式还可以调整行、 列和标头以适应其内容，使用以下方法：  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A>  
  
 这些方法将调整行、 列或一次标头而不是它们配置为使用连续调整大小。 新的大小会自动计算，以显示会不经剪辑的所有单元格内容。 当您以编程方式调整列大小具有<xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A>属性值的<xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill>，但是，使用计算的基于内容的宽度来按比例调整列<xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>属性值和的实际列宽度然后计算根据这些新的比例，以便所有列都填充可用显示区域的控件。  
  
 以编程方式调整大小将有助于避免连续大小调整的性能损失。 它也是有用以提供初始大小，对于用户可调整大小的行、 列和标头和列填充模式。  
  
 通常将在特定时间调用的以编程方式调整大小的方法。 例如，可能会以编程方式加载数据后立即, 调整所有列或一个特定的单元格值已修改后可能会以编程方式调整都大小特定行。  
  
## <a name="customizing-content-based-sizing-behavior"></a>自定义基于内容调整大小行为  
 使用派生时，你可以自定义大小调整行为<xref:System.Windows.Forms.DataGridView>通过重写的单元格、 行和列类型<xref:System.Windows.Forms.DataGridViewCell.GetPreferredSize%2A?displayProperty=nameWithType>， <xref:System.Windows.Forms.DataGridViewRow.GetPreferredHeight%2A?displayProperty=nameWithType>，或<xref:System.Windows.Forms.DataGridViewColumn.GetPreferredWidth%2A?displayProperty=nameWithType>方法或通过调用受保护的调整大小的方法重载中派生<xref:System.Windows.Forms.DataGridView>控件。 受保护的大小调整方法重载用于处理在对实现理想的单元格高度宽度的比例，避免过度宽或更高的单元格。 例如，如果你调用`AutoResizeRows(DataGridViewAutoSizeRowsMode,Boolean)`重载<xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A>方法并传入的值`false`为<xref:System.Boolean>参数，重载将计算的理想高度和宽度的单元格在行中，但它将调整行高仅。 然后，你必须调用<xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>方法调整到计算得到的理想列宽。  
  
## <a name="content-based-sizing-options"></a>基于内容的大小调整选项  
 使用大小调整属性和方法的枚举具有相似基于内容调整大小的值。 使用这些值，你可以限制哪些单元格用于计算的首选的大小。 对于所有大小调整枚举，其名称引用显示的单元格的值限制其计算中显示的行的单元格。 不包括行可用于在你使用了大量的行时避免对性能产生负面影响。 你也可以限制到单元格标头或非标头单元格中的值的计算。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>  
 <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>  
 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>  
 [调整 Windows 窗体 DataGridView 控件中列和行的大小](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)  
 [Windows 窗体 DataGridView 控件中的列填充模式](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 [如何：设置 Windows 窗体 DataGridView 控件的重设大小模式](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)
