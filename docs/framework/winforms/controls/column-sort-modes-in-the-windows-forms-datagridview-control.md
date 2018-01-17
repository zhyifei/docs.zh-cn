---
title: "Windows 窗体 DataGridView 控件中的列排序模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], sort modes
- DataGridView control [Windows Forms], sort mode
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 088d9f1f76e88d8be838cbf7050601835eff216a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="column-sort-modes-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的列排序模式
<xref:System.Windows.Forms.DataGridView>列具有三种排序模式。 通过指定每个列的排序模式<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>属性的列，可以将设置为以下项之一<xref:System.Windows.Forms.DataGridViewColumnSortMode>枚举值。  
  
|`DataGridViewColumnSortMode` 值|描述|  
|----------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>|默认值为文本框列。 除非使用列标题来进行选择，自动单击列标题排序<xref:System.Windows.Forms.DataGridView>按此列，并显示的标志符号，它指示排序顺序。|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>|非 – 文本框中列的默认值。 可以对此列排序以编程方式;但是，它是不适用于进行排序，因此排序标志符号不保留任何空间。|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>|可以对此列排序以编程方式，而且的排序标志符号保留空间。|  
  
 你可能想要更改默认为列的排序模式<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>如果它包含可有意义的方式排序的值。 例如，如果你有一个数据库列包含表示项状态的数字，你可以通过将 image 列绑定到的数据库列将这些数字显示为对应的图标中。 然后可以为处理程序中的图像显示值来更改数值单元格值<xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>事件。 在这种情况下，设置<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>属性<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>将使用户可以对列进行排序。 自动排序将使你的用户对具有相同的状态，即使对应于数字的状态并具备自然序列的项进行分组。 复选框列是另一个示例，其中自动排序是用于分组的相同状态的项。  
  
 您可以进行排序<xref:System.Windows.Forms.DataGridView>以编程方式通过中的任何列或多个列，而不考虑中的值<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>设置。 当你想要提供自己的用户界面 (UI) 进行排序或当你想要实现自定义排序，则编程排序非常有用。 提供你自己排序的用户界面非常有用，例如，当你设置<xref:System.Windows.Forms.DataGridView>选择模式以启用列标头选择。 在这种情况下，虽然不能用于列标题排序，但是你仍然想要的标头显示相应的排序标志符号，因此，你将设置<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>属性<xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>。  
  
 设为以编程方式排序模式的列未自动显示排序标志符号。 对于这些列中，你必须自己显示标志符号通过设置<xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>属性。 这是必需的如果您要在自定义排序中的灵活性。 例如，如果在进行排序<xref:System.Windows.Forms.DataGridView>通过多个列，你可能想要显示多个排序标志符号或无排序标志符号。  
  
 尽管您可以以编程方式进行排序<xref:System.Windows.Forms.DataGridView>按任意列中，某些列，如按钮列可能不包含可有意义的方式排序的值。 对于这些列，<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>属性设置的<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>指示它将永远不会要用于进行排序，因此无需保留排序标志符号的标头中的空间。  
  
 当<xref:System.Windows.Forms.DataGridView>是排序，你检查可确定该排序列和排序顺序的值<xref:System.Windows.Forms.DataGridView.SortedColumn%2A>和<xref:System.Windows.Forms.DataGridView.SortOrder%2A>属性。 自定义排序操作之后，这些值没有意义。 有关自定义排序的详细信息，请参阅本主题后面的自定义排序一节。  
  
 当<xref:System.Windows.Forms.DataGridView>控件，它包含绑定和未绑定列进行排序，但不能自动仍未绑定列中的值。 若要保留这些值，必须实现虚拟模式通过设置<xref:System.Windows.Forms.DataGridView.VirtualMode%2A>属性`true`和处理<xref:System.Windows.Forms.DataGridView.CellValueNeeded>和<xref:System.Windows.Forms.DataGridView.CellValuePushed>事件。 有关详细信息，请参阅[如何： 在 Windows 窗体 DataGridView 控件中实现虚拟模式](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)。 不支持按在绑定模式下的未绑定列进行排序。  
  
## <a name="programmatic-sorting"></a>编程排序  
 您可以进行排序<xref:System.Windows.Forms.DataGridView>以编程方式通过调用其<xref:System.Windows.Forms.DataGridView.Sort%2A>方法。  
  
 `Sort(DataGridViewColumn,ListSortDirection)`重载<xref:System.Windows.Forms.DataGridView.Sort%2A>方法采用<xref:System.Windows.Forms.DataGridViewColumn>和<xref:System.ComponentModel.ListSortDirection>作为参数的枚举值。 按使用的可进行有意义的方式排序，但又不想进行自动排序配置的值的列进行排序时，此重载非常有用。 当调用此重载并传递与列中<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>属性值<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic?displayProperty=nameWithType>、<xref:System.Windows.Forms.DataGridView.SortedColumn%2A>和<xref:System.Windows.Forms.DataGridView.SortOrder%2A>将自动设置属性和列标题中显示相应的排序标志符号。  
  
> [!NOTE]
>  当<xref:System.Windows.Forms.DataGridView>控件绑定到外部数据源的设置<xref:System.Windows.Forms.DataGridView.DataSource%2A>属性，`Sort(DataGridViewColumn,ListSortDirection)`方法重载并不适用于未绑定的列。 此外，当<xref:System.Windows.Forms.DataGridView.VirtualMode%2A>属性是`true`，你可以调用此重载仅为绑定列。 若要确定列是否为数据绑定，请检查<xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A>属性值。 不支持对在绑定模式下的未绑定的列进行排序。  
  
## <a name="custom-sorting"></a>自定义排序  
 你可以自定义<xref:System.Windows.Forms.DataGridView>使用`Sort(IComparer)`重载<xref:System.Windows.Forms.DataGridView.Sort%2A>方法或通过处理<xref:System.Windows.Forms.DataGridView.SortCompare>事件。  
  
 `Sort(IComparer)`方法重载采用一个类以实现的实例<xref:System.Collections.IComparer>作为参数的接口。 此重载十分有用，如果你想要提供自定义排序;例如，当列中的值没有自然排序顺序或当自然排序顺序是不适当。 在这种情况下，你无法使用自动排序，但您可能仍希望用户通过单击列标题进行排序。 你可以在处理程序中调用此重载<xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick>事件，如果选择不使用列标题。  
  
> [!NOTE]
>  `Sort(IComparer)`方法重载时才起作用<xref:System.Windows.Forms.DataGridView>控件未绑定到外部数据源和<xref:System.Windows.Forms.DataGridView.VirtualMode%2A>属性值是`false`。 若要自定义对绑定到外部数据源的列进行排序，必须使用提供的数据源的排序操作。 虚拟模式下，你必须提供自己的未绑定的列的排序操作。  
  
 若要使用`Sort(IComparer)`方法重载中，你必须创建您自己的类实现<xref:System.Collections.IComparer>接口。 此接口需要你的类以实现<xref:System.Collections.IComparer.Compare%2A?displayProperty=nameWithType>方法，向其<xref:System.Windows.Forms.DataGridView>传递<xref:System.Windows.Forms.DataGridViewRow>对象作为输入时`Sort(IComparer)`调用方法重载。 与此，可以计算的正确的行排序基于任何列中的值。  
  
 `Sort(IComparer)`方法重载不会设置<xref:System.Windows.Forms.DataGridView.SortedColumn%2A>和<xref:System.Windows.Forms.DataGridView.SortOrder%2A>属性，因此你必须始终设置<xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>属性显示的排序标志符号。  
  
 作为替代方法`Sort(IComparer)`方法重载中，你可以提供通过实现的处理程序的自定义排序<xref:System.Windows.Forms.DataGridView.SortCompare>事件。 当用户单击的列配置为自动排序，或当调用的标头时，将发生此事件`Sort(DataGridViewColumn,ListSortDirection)`重载<xref:System.Windows.Forms.DataGridView.Sort%2A>方法。 每个对的行在控件中，使您能够计算其正确的顺序发生事件。  
  
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView.SortCompare>事件不会发生时<xref:System.Windows.Forms.DataGridView.DataSource%2A>设置属性时，或者当<xref:System.Windows.Forms.DataGridView.VirtualMode%2A>属性值是`true`。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>  
 [在 Windows 窗体 DataGridView 控件中进行数据排序](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 [如何：设置 Windows 窗体 DataGridView 控件中列的排序模式](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)  
 [如何：在 Windows 窗体 DataGridView 控件中自定义排序](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
