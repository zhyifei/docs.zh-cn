---
title: 在 Windows 窗体 DataGridView 控件中使用新记录行
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], adding rows for new records
- rows [Windows Forms], new records
- DataGridView control [Windows Forms], data entry
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
ms.openlocfilehash: abf62cc9165d74f6bf183e3df30d9a768c0c537f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="using-the-row-for-new-records-in-the-windows-forms-datagridview-control"></a>在 Windows 窗体 DataGridView 控件中使用新记录行
当你使用<xref:System.Windows.Forms.DataGridView>进行编辑你的应用程序中的数据，通常要使用户能够将新的数据行添加到数据存储。 <xref:System.Windows.Forms.DataGridView>控件通过始终作为最后一行显示为新记录，提供行来支持此功能。 它将标有其行标题中的星号 （*） 符号。 以下各节讨论的一些操作应考虑启用程序与用于新纪录的行。  
  
## <a name="displaying-the-row-for-new-records"></a>显示用于新纪录的行  
 使用<xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A>属性以指示是否显示用于新纪录的行。 此属性的默认值为 `true`。  
  
 数据绑定情况下，将显示新记录所在行如果<xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A>的控件的属性和<xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=nameWithType>的数据源的属性均`true`。 如果存在任何一种`false`则不会显示行。  
  
## <a name="populating-the-row-for-new-records-with-default-data"></a>为新记录的默认数据填充行  
 当用户选择用于新纪录的行的当前行中，作为<xref:System.Windows.Forms.DataGridView>控件都将引发<xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>事件。  
  
 此事件提供对新的访问<xref:System.Windows.Forms.DataGridViewRow>并使你能够填充新的默认数据行。 有关详细信息，请参阅[如何： 在 Windows 窗体 DataGridView 控件中的新行的指定默认值](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)  
  
## <a name="the-rows-collection"></a>行集合  
 用于新纪录的行包含在<xref:System.Windows.Forms.DataGridView>控件的<xref:System.Windows.Forms.DataGridView.Rows%2A>集合但其行为以不同方式在两个方面：  
  
-   用于新纪录的行不能从删除<xref:System.Windows.Forms.DataGridView.Rows%2A>集合以编程方式。 <xref:System.InvalidOperationException>如果尝试执行此操作，将引发。 用户也不能删除用于新纪录的行。 <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=nameWithType>方法不会删除从此行<xref:System.Windows.Forms.DataGridView.Rows%2A>集合。  
  
-   可以为新记录的行之后不添加任何行。 <xref:System.InvalidOperationException>如果尝试执行此操作，则引发。 因此，用于新纪录的行始终是中的最后一行<xref:System.Windows.Forms.DataGridView>控件。 上的方法<xref:System.Windows.Forms.DataGridViewRowCollection>中添加行-<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>， <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>，和<xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>-所有调用插入方法内部存在用于新纪录的行时。  
  
## <a name="visual-customization-of-the-row-for-new-records"></a>为新记录可视的行的自定义  
 创建用于新纪录的行时，它基于指定的行的<xref:System.Windows.Forms.DataGridView.RowTemplate%2A>属性。 任何未指定此行的单元格样式均继承于其他属性。 有关单元格样式继承的详细信息，请参阅[在 Windows 窗体 DataGridView 控件中的单元格样式](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)。  
  
 为新的记录检索从每个单元格的行中的单元显示的初始值<xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A>属性。 有关类型的单元格<xref:System.Windows.Forms.DataGridViewImageCell>，此属性返回占位符图像。 否则，此属性返回`null`。 你可以重写此属性以返回自定义值。 但是，这些初始值可以替换为<xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>事件处理程序时焦点输入新记录的行。  
  
 是一个箭头或星号，用于此行的标头的标准图标不被公开。 如果你想要自定义图标，你将需要创建自定义<xref:System.Windows.Forms.DataGridViewRowHeaderCell>类。  
  
 使用的标准图标<xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>属性<xref:System.Windows.Forms.DataGridViewCellStyle>使用行标题单元格。 如果没有足够的空间来显示它们完全不会呈现的标准图标。  
  
 如果行标题单元格具有一个字符串值，设置，并且没有为文本和图标足够的空间，先删除图标。  
  
## <a name="sorting"></a>排序  
 在未绑定模式下，将总是被新记录添加到的末尾<xref:System.Windows.Forms.DataGridView>即使用户已排序的内容<xref:System.Windows.Forms.DataGridView>。 用户将需要再次应用排序，以便将该行排列到正确的位置;此行为是类似于<xref:System.Windows.Forms.ListView>控件。  
  
 在数据绑定和虚拟模式，插入行为应用排序时将依赖于数据模型的实现。 有关[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]，行立即排列到正确的位置。  
  
## <a name="other-notes-on-the-row-for-new-records"></a>用于新纪录的行上的其他说明  
 无法设置<xref:System.Windows.Forms.DataGridViewRow.Visible%2A>该行与属性`false`。 <xref:System.InvalidOperationException>如果尝试执行此操作，则引发。  
  
 始终在未选中状态中创建用于新纪录的行。  
  
## <a name="virtual-mode"></a>虚拟模式  
 如果你要实现虚拟模式，你将需要跟踪用于新记录行需要在数据模型，何时回滚添加行时。 此功能的正确实现取决于实现数据模型和其事务的语义，例如，在单元或行级别上是否是提交作用域。 有关详细信息，请参阅[Windows 窗体 DataGridView 控件中的虚拟模式](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 [Windows 窗体 DataGridView 控件中的数据输入](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [如何：指定 Windows 窗体 DataGridView 控件中新行的默认值](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)
