---
title: DataGridView 控件中的列排序模式
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], sort modes
- DataGridView control [Windows Forms], sort mode
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
ms.openlocfilehash: d1e2f582c9759332e0ed963cb7f88ee052616c45
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744192"
---
# <a name="column-sort-modes-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 열 정렬 모드
<xref:System.Windows.Forms.DataGridView> 列具有三种排序模式。 每个列的排序模式是通过列的 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 属性指定的，该属性可设置为以下 <xref:System.Windows.Forms.DataGridViewColumnSortMode> 枚举值之一。  
  
|`DataGridViewColumnSortMode` 값|설명|  
|----------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>|文本框列的默认值。 除非列标题用于选择，否则，单击列标题会自动对此列 <xref:System.Windows.Forms.DataGridView> 排序，并显示指示排序顺序的标志符号。|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>|非文本框列的默认值。 您可以通过编程方式对此列进行排序;但是，它不用于排序，因此不会为排序标志符号保留任何空间。|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>|您可以通过编程方式对此列进行排序，并为排序标志符号保留空间。|  
  
 如果列中包含可有意义的值，则可能需要更改默认为 <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> 的列的排序模式。 例如，如果您有一个包含表示项状态的数字的数据库列，则可以通过将 image 列绑定到数据库列来将这些数值显示为相应的图标。 然后，可以将数字单元值更改为 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> 事件的处理程序中的图像显示值。 在这种情况下，将 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 属性设置为 "<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic> 将使用户能够对列进行排序。 自动排序将使用户能够对具有相同状态的项进行分组，即使与数字相对应的状态没有自然顺序也是如此。 复选框列是另一个示例，在此示例中，自动排序适用于对处于相同状态的项进行分组。  
  
 无论 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 设置如何，都可以通过任何列或多列中的值以编程方式对 <xref:System.Windows.Forms.DataGridView> 进行排序。 如果希望提供自己的用户界面（UI）进行排序或要实现自定义排序，则编程排序非常有用。 提供自己的排序 UI 非常有用，例如，当您将 <xref:System.Windows.Forms.DataGridView> 选择模式设置为启用列标题选择时。 在这种情况下，尽管列标题不能用于排序，但您仍希望标题显示适当的排序符号，因此，您可以将 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 属性设置为 <xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>。  
  
 设置为编程排序模式的列不会自动显示排序标志符号。 对于这些列，必须通过设置 <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> 属性来自行显示标志符号。 如果要灵活地进行自定义排序，则这是必需的。 例如，如果您按多个列对 <xref:System.Windows.Forms.DataGridView> 进行排序，则您可能希望显示多个排序标志符号或无排序标志符号。  
  
 尽管可以通过编程方式对任何列进行 <xref:System.Windows.Forms.DataGridView> 排序，但某些列（如按钮列）可能不包含可有意义排序的值。 对于这些列，<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> 的 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 属性设置指示它永远不会用于排序，因此不需要在标头中为排序标志符号保留空间。  
  
 对 <xref:System.Windows.Forms.DataGridView> 进行排序时，可以通过检查 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> 和 <xref:System.Windows.Forms.DataGridView.SortOrder%2A> 属性的值来确定 sort 列和排序顺序。 自定义排序操作后，这些值不是有意义的。 有关自定义排序的详细信息，请参阅本主题后面的自定义排序部分。  
  
 当包含绑定列和未绑定列的 <xref:System.Windows.Forms.DataGridView> 控件进行排序时，无法自动维护未绑定列中的值。 若要维护这些值，必须通过将 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 属性设置为 `true` 并处理 <xref:System.Windows.Forms.DataGridView.CellValueNeeded> 和 <xref:System.Windows.Forms.DataGridView.CellValuePushed> 事件来实现虚拟模式。 有关详细信息，请参阅[如何：在 Windows 窗体 DataGridView 控件中实现虚拟模式](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)。 不支持在绑定模式下按未绑定列进行排序。  
  
## <a name="programmatic-sorting"></a>프로그래밍 방식 정렬  
 可以通过调用其 <xref:System.Windows.Forms.DataGridView.Sort%2A> 方法以编程方式对 <xref:System.Windows.Forms.DataGridView> 进行排序。  
  
 <xref:System.Windows.Forms.DataGridView.Sort%2A> 方法的 `Sort(DataGridViewColumn,ListSortDirection)` 重载采用 <xref:System.Windows.Forms.DataGridViewColumn>，并将 <xref:System.ComponentModel.ListSortDirection> 枚举值作为参数。 此重载在按具有可有意义的值的列进行排序时非常有用，但不希望将其配置为自动排序。 当你调用此重载并传入 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 属性值为 <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic?displayProperty=nameWithType>的列时，将自动设置 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> 和 <xref:System.Windows.Forms.DataGridView.SortOrder%2A> 属性，并且相应的排序标志符号将出现在列标题中。  
  
> [!NOTE]
> 如果通过设置 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 属性将 <xref:System.Windows.Forms.DataGridView> 控件绑定到外部数据源，则 `Sort(DataGridViewColumn,ListSortDirection)` 方法重载对未绑定的列不起作用。 此外，当 `true`<xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 属性时，只能为绑定列调用此重载。 若要确定某列是否是数据绑定列，请检查 <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A> 属性值。 不支持对绑定模式下的未绑定列进行排序。  
  
## <a name="custom-sorting"></a>自定义排序  
 您可以使用 <xref:System.Windows.Forms.DataGridView.Sort%2A> 方法的 `Sort(IComparer)` 重载或通过处理 <xref:System.Windows.Forms.DataGridView.SortCompare> 事件来自定义 <xref:System.Windows.Forms.DataGridView>。  
  
 `Sort(IComparer)` 方法重载采用类的实例，将 <xref:System.Collections.IComparer> 接口实现为参数。 如果要提供自定义排序，此重载非常有用;例如，当列中的值不具有自然排序顺序或自然排序顺序不合适时。 在这种情况下，您不能使用自动排序，但您可能仍希望用户通过单击列标题进行排序。 如果不使用列标题进行选择，则可以在 <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick> 事件的处理程序中调用此重载。  
  
> [!NOTE]
> 仅当 <xref:System.Windows.Forms.DataGridView> 控件未绑定到外部数据源并且 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 属性值为 `false`时，`Sort(IComparer)` 方法重载才有效。 若要为绑定到外部数据源的列自定义排序，必须使用数据源提供的排序操作。 在虚拟模式下，必须为未绑定列提供自己的排序操作。  
  
 若要使用 `Sort(IComparer)` 方法重载，必须创建自己的类来实现 <xref:System.Collections.IComparer> 接口。 此接口需要类实现 <xref:System.Collections.IComparer.Compare%2A?displayProperty=nameWithType> 方法，在调用 `Sort(IComparer)` 方法重载时，<xref:System.Windows.Forms.DataGridView> 将 <xref:System.Windows.Forms.DataGridViewRow> 对象作为输入传递给。 这样，就可以根据任何列中的值来计算正确的行顺序。  
  
 `Sort(IComparer)` 方法重载不设置 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> 和 <xref:System.Windows.Forms.DataGridView.SortOrder%2A> 属性，因此您必须始终将 <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> 属性设置为显示排序标志符号。  
  
 作为 `Sort(IComparer)` 方法重载的替代方法，你可以通过为 <xref:System.Windows.Forms.DataGridView.SortCompare> 事件实现处理程序来提供自定义排序。 当用户单击配置为自动排序的列标题或调用 <xref:System.Windows.Forms.DataGridView.Sort%2A> 方法的 `Sort(DataGridViewColumn,ListSortDirection)` 重载时，将发生此事件。 此事件在控件中的每对行中发生，使您能够计算它们的正确顺序。  
  
> [!NOTE]
> 如果设置了 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 属性或 `true`<xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 属性值，则不会发生 <xref:System.Windows.Forms.DataGridView.SortCompare> 事件。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>
- [Windows Forms DataGridView 컨트롤의 데이터 정렬](sorting-data-in-the-windows-forms-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤의 열 정렬 모드 설정](set-the-sort-modes-for-columns-wf-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤에서 정렬 사용자 지정](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
