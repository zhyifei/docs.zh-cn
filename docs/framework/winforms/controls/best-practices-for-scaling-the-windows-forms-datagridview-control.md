---
title: "缩放 Windows 窗体 DataGridView 控件的最佳做法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], row sharing
- data grids [Windows Forms], best practices
- DataGridView control [Windows Forms], shared rows
- DataGridView control [Windows Forms], best practices
- best practices [Windows Forms], dataGridView control
- DataGridView control [Windows Forms], scaling
ms.assetid: 8321a8a6-6340-4fd1-b475-fa090b905aaf
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ecd629bd38e08c8d6909ee4ad771f17b1554fc80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="best-practices-for-scaling-the-windows-forms-datagridview-control"></a>缩放 Windows 窗体 DataGridView 控件的最佳做法
<xref:System.Windows.Forms.DataGridView>控件旨在提供最大可伸缩性。 如果想要显示的数据量大，则应遵循避免使用大量的内存或降低用户界面 (UI) 的响应能力本主题中所述准则。 本主题讨论了以下问题：  
  
-   有效使用单元格样式  
  
-   有效使用快捷菜单  
  
-   使用自动调整大小有效地  
  
-   有效使用所选的单元格、 行和列集合  
  
-   使用共享的行  
  
-   阻止行成为非共享行  
  
 如果你有特殊的性能需求，可以实现虚拟模式，并提供你自己的数据管理操作。 有关详细信息，请参阅[在 Windows 窗体 DataGridView 控件中的数据显示模式](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)。  
  
## <a name="using-cell-styles-efficiently"></a>有效使用单元格样式  
 每个单元格、 行和列可以具有其自己的样式信息。 样式信息存储在<xref:System.Windows.Forms.DataGridViewCellStyle>对象。 创建多个独立单元格样式对象<xref:System.Windows.Forms.DataGridView>元素可以是效率低下，尤其是在使用大量的数据。 若要避免对性能有影响，请使用以下准则：  
  
-   避免将设置为各个单元格样式属性<xref:System.Windows.Forms.DataGridViewCell>或<xref:System.Windows.Forms.DataGridViewRow>对象。 这包括指定的行对象<xref:System.Windows.Forms.DataGridView.RowTemplate%2A>属性。 每个克隆从行模板的新行将收到其自己的模板的单元格样式对象副本。 对于最大可伸缩性，设置在单元格样式属性<xref:System.Windows.Forms.DataGridView>级别。 例如，设置<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>属性而不是<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>属性。  
  
-   如果某些单元格需要比默认格式设置的其他格式，使用相同<xref:System.Windows.Forms.DataGridViewCellStyle>跨的单元格、 行或列组的实例。 避免直接设置类型的属性<xref:System.Windows.Forms.DataGridViewCellStyle>上各个单元格、 行和列。 单元格样式共享的示例，请参阅[如何： 设置 Windows 窗体 DataGridView 控件的默认单元格样式](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)。 通过处理单独设置单元格样式时，也可以避免对性能产生负面影响<xref:System.Windows.Forms.DataGridView.CellFormatting>事件处理程序。 有关示例，请参阅[如何： 在 Windows 窗体 DataGridView 控件中自定义数据格式](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)。  
  
-   在确定单元格的样式时，使用<xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType>属性而不是<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>属性。 访问<xref:System.Windows.Forms.DataGridViewCell.Style%2A>属性创建的新实例<xref:System.Windows.Forms.DataGridViewCellStyle>类如果尚未使用属性。 此外，此对象可能不包含该单元格的完整的样式信息，如果某些样式继承自行、 列或控件。 有关单元格样式继承的详细信息，请参阅[在 Windows 窗体 DataGridView 控件中的单元格样式](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)。  
  
## <a name="using-shortcut-menus-efficiently"></a>有效使用快捷菜单  
 每个单元格、 行和列可以具有其自己的快捷菜单。 中的快捷菜单<xref:System.Windows.Forms.DataGridView>控件由<xref:System.Windows.Forms.ContextMenuStrip>控件。 就像使用单元格样式对象创建的多个独立的快捷菜单<xref:System.Windows.Forms.DataGridView>元素将会对性能产生负面影响。 若要避免这种下降，请使用以下准则：  
  
-   避免创建各个单元格和行的快捷菜单。 这包括行模板，新行添加到控件时，会克隆以及其快捷菜单。 要获得最大可伸缩性，使用仅控制的<xref:System.Windows.Forms.Control.ContextMenuStrip%2A>属性指定整个控件的单个快捷菜单。  
  
-   如果你需要多个行或单元格多个快捷菜单，处理<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded>或<xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>事件。 这些事件能够让你管理的快捷菜单对象你自己，允许您优化性能。  
  
## <a name="using-automatic-resizing-efficiently"></a>使用自动调整大小有效地  
 行、 列和标头可以自动调整单元格内容发生变化，以便单元格的整个内容显示会不经剪辑。 更改大小调整模式还可以调整行、 列和标头。 若要确定正确的大小，<xref:System.Windows.Forms.DataGridView>控件必须检查必须适应每个单元格的值。 在使用大型数据集，这种分析可以性能带来负面影响的控件自动调整大小发生时。 若要避免性能损失，使用以下准则：  
  
-   避免在使用自动调整大小<xref:System.Windows.Forms.DataGridView>与大量的行集的控件。 如果你使用自动调整大小，调整大小，基于所显示的行。 在虚拟模式下以及使用显示的行。  
  
    -   对于行和列，使用`DisplayedCells`或`DisplayedCellsExceptHeaders`字段<xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>， <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>，和<xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>枚举。  
  
    -   有关行标头，使用<xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToDisplayedHeaders>或<xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToFirstHeader>字段<xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>枚举。  
  
-   对于最大可伸缩性，关闭自动调整大小并使用以编程方式调整大小。  
  
 有关详细信息，请参阅[在 Windows 窗体 DataGridView 控件中调整选项](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)。  
  
## <a name="using-the-selected-cells-rows-and-columns-collections-efficiently"></a>有效使用选定的单元格、 行和列集合  
 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>集合不对于大型选择有效地执行。 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>和<xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>集合还可能效率很低，尽管到较小度因为有许多更少的行，比在典型的单元格<xref:System.Windows.Forms.DataGridView>控制和许多较少的列比行。 若要避免性能损失，使用这些集合时，使用以下准则：  
  
-   若要确定是否中的所有单元格<xref:System.Windows.Forms.DataGridView>之前访问的内容已选择<xref:System.Windows.Forms.DataGridView.SelectedCells%2A>集合，检查返回值的<xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>方法。 但是，请注意，此方法可导致行变为非共享。 有关更多信息，请参见下一节。  
  
-   避免使用<xref:System.Collections.ICollection.Count%2A>属性<xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=nameWithType>确定选定的单元格的数目。 请改用<xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=nameWithType>方法并传入<xref:System.Windows.Forms.DataGridViewElementStates.Selected?displayProperty=nameWithType>值。 同样，使用<xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=nameWithType>和<xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=nameWithType>方法，以确定所选的元素，而不是访问所选的行和列集合的数目。  
  
-   避免基于单元格的选择模式。 与此相反，设置<xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>属性<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>或<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>。  
  
## <a name="using-shared-rows"></a>使用共享行  
 在实现高效的内存使用<xref:System.Windows.Forms.DataGridView>控制通过共享行。 行将通过共享的实例共享尽可能多的信息有关其外观和行为可能<xref:System.Windows.Forms.DataGridViewRow>类。  
  
 虽然共享行实例节省内存，行可以轻松地成为非共享行。 例如，每当用户交互直接与单元格时，其行成为非共享行。 由于不能避免这种情况，本主题中的准则十分有用，仅当使用的数据量非常大并只在用户将交互具有相对较小部分数据的每次运行程序时。  
  
 不能共享行中未绑定<xref:System.Windows.Forms.DataGridView>控制如果任何其单元格包含值。 当<xref:System.Windows.Forms.DataGridView>控件绑定到外部数据源，或当您实现虚拟模式，并且提供您自己的数据源，这些单元格值存储到控件而不是单元格对象，允许要共享的行。  
  
 如果可以从行的状态和包含的单元格的列的状态确定其所有单元格的状态，则仅可以共享行对象。 如果你更改单元格的状态，以便它不再可以推导从其行和列的状态，则不能共享行。  
  
 例如，在任何以下情况下不能共享行：  
  
-   该行中包含一个不在所选列中的所选的单元。  
  
-   行包含包含的单元格其<xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A>或<xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A>属性集。  
  
-   行包含<xref:System.Windows.Forms.DataGridViewComboBoxCell>与其<xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A>属性集。  
  
 在绑定的模式或虚拟模式中，你可以提供工具提示和快捷菜单为单个单元格通过处理<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>和<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded>事件。  
  
 <xref:System.Windows.Forms.DataGridView>控件将自动尝试使用共享的行，每当行添加到<xref:System.Windows.Forms.DataGridViewRowCollection>。 使用以下准则以确保共享行：  
  
-   避免调用`Add(Object[])`重载<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>方法和`Insert(Object[])`重载<xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A>方法<xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>集合。 这些重载自动创建非共享的行。  
  
-   请确保在指定的行<xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>可以在以下情况下共享属性：  
  
    -   在调用时`Add()`或`Add(Int32)`的重载<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>方法或`Insert(Int32,Int32)`重载<xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A>方法<xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>集合。  
  
    -   增加的值时<xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=nameWithType>属性。  
  
    -   设置时<xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>属性。  
  
-   请确保指定的行`indexSource`调用时，可以共享参数<xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>， <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>， <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A>，和<xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A>方法<xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>集合。  
  
-   请确保在调用时，可以共享的指定的行`Add(DataGridViewRow)`重载<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>方法，<xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A>方法，`Insert(Int32,DataGridViewRow)`重载<xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A>方法，与<xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A>方法<xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>集合。  
  
 若要确定是否共享行，使用<xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType>方法来检索行对象，然后检查对象的<xref:System.Windows.Forms.DataGridViewBand.Index%2A>属性。 共享的行始终具有<xref:System.Windows.Forms.DataGridViewBand.Index%2A>– 1 的属性值。  
  
## <a name="preventing-rows-from-becoming-unshared"></a>阻止行成为非共享行  
 共享的行可以成为非共享行代码或用户操作的结果。 若要避免对性能有影响，应避免使行成为非共享行。 应用程序在开发期间，你可以处理<xref:System.Windows.Forms.DataGridView.RowUnshared>事件，以确定何时成为非共享行。 在调试行共享问题时，这很有用。  
  
 若要防止行成为非共享行，使用以下准则：  
  
-   避免索引<xref:System.Windows.Forms.DataGridView.Rows%2A>集合或循环访问其与`foreach`循环。 您将通常不必直接访问的行。 <xref:System.Windows.Forms.DataGridView>对行进行操作的方法采用行索引自变量，而不是行实例。 此外，行相关的事件的处理程序接收具有可用于操作而不会导致它们成为非共享行的行的行属性的事件参数对象。  
  
-   如果你需要访问行对象，请使用<xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType>方法并传入行的实际的索引。 但是，请注意，修改通过此方法检索到一个共享的行对象将修改共享此对象的所有行。 用于新纪录的行不与共享其他行，但是，因此它不会受到影响时修改任何其他行。 另请注意，不同的行表示一个共享行可能有不同的快捷菜单。 若要从共享的行实例检索正确的快捷菜单，使用<xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A>方法并传入行的实际的索引。 如果访问共享的行<xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A>属性相反，它将使用共享的行的索引为-1 并将检索正确的快捷菜单。  
  
-   避免索引<xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=nameWithType>集合。 直接访问单元格将导致其成为非共享行，实例化一个新的父行<xref:System.Windows.Forms.DataGridViewRow>。 单元格相关事件的处理程序接收具有可用于对行执行操作而不会导致要成为非共享行的行的单元属性的事件参数对象。 你还可以使用<xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A>属性来检索当前的单元格的行和列索引，而无需直接访问该单元格。  
  
-   避免基于单元格的选择模式。 这些模式将使行成为非共享行。 与此相反，设置<xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>属性<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>或<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>。  
  
-   不处理<xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=nameWithType>或<xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=nameWithType>事件。 这些事件将使行成为非共享行。 此外，请勿调用<xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=nameWithType>或<xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=nameWithType>引发这些事件的方法。  
  
-   不能访问<xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=nameWithType>集合时<xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>属性值是<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>， <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>， <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>，或<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>。 这将导致所有所选的行变为非共享。  
  
-   不要调用<xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=nameWithType>方法。 此方法可以使行成为非共享行。  
  
-   不要调用<xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=nameWithType>方法时<xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>属性值是<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>。 这将导致所有行变为非共享。  
  
-   未设置<xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A>或<xref:System.Windows.Forms.DataGridViewCell.Selected%2A>到单元格的属性`false`时在其列中的相应属性设置为`true`。 这将导致所有行变为非共享。  
  
-   不能访问<xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=nameWithType>属性。 这将导致所有行变为非共享。  
  
-   不要调用`Sort(IComparer)`重载<xref:System.Windows.Forms.DataGridView.Sort%2A>方法。 使用自定义比较器进行排序，则会导致所有行成为非共享行。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 [Windows 窗体 DataGridView 控件中的性能调整](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Windows 窗体 DataGridView 控件中的虚拟模式](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 [Windows 窗体 DataGridView 控件中的数据显示模式](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)  
 [Windows 窗体 DataGridView 控件中的单元格样式](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [如何：设置 Windows 窗体 DataGridView 控件的默认单元格样式](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 [Windows 窗体 DataGridView 控件中的重设大小选项](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)
