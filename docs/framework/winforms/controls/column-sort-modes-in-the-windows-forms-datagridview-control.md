---
title: Windows 窗体 DataGridView 控件中的列排序模式
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], sort modes
- DataGridView control [Windows Forms], sort mode
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
ms.openlocfilehash: d0d743ccae38d101eda5bb9780b33ae18dfb608a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918451"
---
# <a name="column-sort-modes-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的列排序模式
<xref:System.Windows.Forms.DataGridView>列具有三种排序模式。 每个列的排序模式是通过<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>列的属性指定的, 该列可设置为以下<xref:System.Windows.Forms.DataGridViewColumnSortMode>枚举值之一。  
  
|`DataGridViewColumnSortMode` 值|描述|  
|----------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>|文本框列的默认值。 除非列标题用于选择, 否则, 单击列标题会自动<xref:System.Windows.Forms.DataGridView>按此列对进行排序, 并显示指示排序顺序的标志符号。|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>|非文本框列的默认值。 您可以通过编程方式对此列进行排序;但是, 它不用于排序, 因此不会为排序标志符号保留任何空间。|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>|您可以通过编程方式对此列进行排序, 并为排序标志符号保留空间。|  
  
 如果列中包含可有意义排序的值, 则您可能<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>需要更改默认为的列的排序模式。 例如, 如果您有一个包含表示项状态的数字的数据库列, 则可以通过将 image 列绑定到数据库列来将这些数值显示为相应的图标。 然后, 可以将数字单元值更改为<xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>事件处理程序中的图像显示值。 在这种情况下, <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>将属性<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>设置为将使用户能够对列进行排序。 自动排序将使用户能够对具有相同状态的项进行分组, 即使与数字相对应的状态没有自然顺序也是如此。 复选框列是另一个示例, 在此示例中, 自动排序适用于对处于相同状态的项进行分组。  
  
 <xref:System.Windows.Forms.DataGridView> 无论<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>设置如何, 都可以通过任何列或多列中的值以编程方式对其进行排序。 如果希望提供自己的用户界面 (UI) 进行排序或要实现自定义排序, 则编程排序非常有用。 提供自己的排序 UI 非常有用, 例如, 当您将选择模式<xref:System.Windows.Forms.DataGridView>设置为 "启用列标题" 选项时。 在这种情况下, 尽管列标题不能用于排序, 但您仍希望标题显示适当的排序符号, 因此您可以将<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>属性设置为。 <xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>  
  
 设置为编程排序模式的列不会自动显示排序标志符号。 对于这些列, 必须通过设置<xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>属性来自行显示标志符号。 如果要灵活地进行自定义排序, 则这是必需的。 例如, 如果<xref:System.Windows.Forms.DataGridView>按多个列排序, 则可能希望显示多个排序标志符号或无排序标志符号。  
  
 尽管可以<xref:System.Windows.Forms.DataGridView>通过编程方式按任何列进行排序, 但某些列 (如按钮列) 可能不包含可有意义排序的值。 对于这些列, <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>的属性<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>设置指示它永远不会用于排序, 因此不需要在标头中为排序标志符号保留空间。  
  
 排序后, 可以通过检查<xref:System.Windows.Forms.DataGridView.SortedColumn%2A>和<xref:System.Windows.Forms.DataGridView.SortOrder%2A>属性的值来确定 sort 列和排序顺序。 <xref:System.Windows.Forms.DataGridView> 自定义排序操作后, 这些值不是有意义的。 有关自定义排序的详细信息, 请参阅本主题后面的自定义排序部分。  
  
 如果对<xref:System.Windows.Forms.DataGridView>同时包含绑定列和未绑定列的控件进行排序, 则未绑定列中的值将无法自动维护。 若要维护这些值<xref:System.Windows.Forms.DataGridView.VirtualMode%2A> , 必须通过将属性设置为`true`并处理<xref:System.Windows.Forms.DataGridView.CellValueNeeded>和<xref:System.Windows.Forms.DataGridView.CellValuePushed>事件来实现虚拟模式。 有关详细信息，请参阅[如何：在 Windows 窗体 DataGridView 控件](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)中实现虚拟模式。 不支持在绑定模式下按未绑定列进行排序。  
  
## <a name="programmatic-sorting"></a>编程排序  
 可以通过调用其<xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridView.Sort%2A>方法, 以编程方式对进行排序。  
  
 方法的`Sort(DataGridViewColumn,ListSortDirection)` 重载<xref:System.Windows.Forms.DataGridViewColumn>采用和枚举值作为参数。<xref:System.ComponentModel.ListSortDirection> <xref:System.Windows.Forms.DataGridView.Sort%2A> 此重载在按具有可有意义的值的列进行排序时非常有用, 但不希望将其配置为自动排序。 当你调用此重载并<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>传入属性值为的<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic?displayProperty=nameWithType>列时, <xref:System.Windows.Forms.DataGridView.SortedColumn%2A>和<xref:System.Windows.Forms.DataGridView.SortOrder%2A>属性将自动设置, 并且相应的排序标志符号将出现在列标题中。  
  
> [!NOTE]
> 如果通过`Sort(DataGridViewColumn,ListSortDirection)`设置属性将控件绑定到外部数据源, 则方法重载对未绑定的列不起作用。 <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridView.DataSource%2A> 此外, 当<xref:System.Windows.Forms.DataGridView.VirtualMode%2A>属性为`true`时, 只能为绑定列调用此重载。 若要确定列是否是数据绑定列, 请检查<xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A>属性值。 不支持对绑定模式下的未绑定列进行排序。  
  
## <a name="custom-sorting"></a>自定义排序  
 您可以通过<xref:System.Windows.Forms.DataGridView> `Sort(IComparer)`使用<xref:System.Windows.Forms.DataGridView.Sort%2A>方法的重载或通过处理<xref:System.Windows.Forms.DataGridView.SortCompare>事件来自定义。  
  
 方法重载使用<xref:System.Collections.IComparer>实现接口的类的实例作为参数。 `Sort(IComparer)` 如果要提供自定义排序, 此重载非常有用;例如, 当列中的值不具有自然排序顺序或自然排序顺序不合适时。 在这种情况下, 您不能使用自动排序, 但您可能仍希望用户通过单击列标题进行排序。 如果不使用列标题进行选择, 则可以<xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick>在事件的处理程序中调用此重载。  
  
> [!NOTE]
> 方法重载仅<xref:System.Windows.Forms.DataGridView>在控件未绑定到<xref:System.Windows.Forms.DataGridView.VirtualMode%2A>外部数据源并且属性值为`false`时才有效。 `Sort(IComparer)` 若要为绑定到外部数据源的列自定义排序, 必须使用数据源提供的排序操作。 在虚拟模式下, 必须为未绑定列提供自己的排序操作。  
  
 若要使用`Sort(IComparer)`方法重载, 必须创建自己的类来<xref:System.Collections.IComparer>实现接口。 此接口需要你的<xref:System.Collections.IComparer.Compare%2A?displayProperty=nameWithType>类实现方法, 当调用`Sort(IComparer)`方法重载<xref:System.Windows.Forms.DataGridView>时<xref:System.Windows.Forms.DataGridViewRow> , 该方法会将对象作为输入传递给。 这样, 就可以根据任何列中的值来计算正确的行顺序。  
  
 方法重载不<xref:System.Windows.Forms.DataGridView.SortedColumn%2A>设置<xref:System.Windows.Forms.DataGridView.SortOrder%2A> 和<xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>属性, 因此您必须始终将属性设置为显示排序标志符号。 `Sort(IComparer)`  
  
 作为`Sort(IComparer)`方法重载的替代方法, 可以通过实现<xref:System.Windows.Forms.DataGridView.SortCompare>事件的处理程序来提供自定义排序。 当用户单击配置为自动排序的列标题或调用`Sort(DataGridViewColumn,ListSortDirection)` <xref:System.Windows.Forms.DataGridView.Sort%2A>方法的重载时, 将发生此事件。 此事件在控件中的每对行中发生, 使您能够计算它们的正确顺序。  
  
> [!NOTE]
> 如果设置了<xref:System.Windows.Forms.DataGridView.SortCompare> <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>属性或属性值为`true`, 则不会发生该事件。 <xref:System.Windows.Forms.DataGridView.DataSource%2A>  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>
- [在 Windows 窗体 DataGridView 控件中进行数据排序](sorting-data-in-the-windows-forms-datagridview-control.md)
- [如何：在 Windows 窗体 DataGridView 控件中设置列的排序模式](set-the-sort-modes-for-columns-wf-datagridview-control.md)
- [如何：自定义 Windows 窗体 DataGridView 控件中的排序](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
