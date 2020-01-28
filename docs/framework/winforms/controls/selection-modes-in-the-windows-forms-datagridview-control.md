---
title: DataGridView 控件中的选择模式
ms.date: 03/30/2017
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
ms.openlocfilehash: e20bf6307d77bf189b698e847c6b855c249dc3c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743037"
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 선택 모드

有时，你希望应用程序根据 <xref:System.Windows.Forms.DataGridView> 控件中的用户选择执行操作。 根据具体的操作，可能需要限制可能的选择类型。 例如，假设您的应用程序可以打印当前所选记录的报表。 在这种情况下，您可能需要配置 <xref:System.Windows.Forms.DataGridView> 控件以便单击行中的任意位置，以始终选择整行，以便每次只能选择一行。

可以通过将 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> 属性设置为以下 <xref:System.Windows.Forms.DataGridViewSelectionMode> 枚举值之一来指定允许的选项。

|DataGridViewSelectionMode 值|설명|
|-------------------------------------|-----------------|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|单击单元格会将其选中。 行标题和列标题不能用于选择。|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|单击单元格会将其选中。 单击列标题会选择整个列。 列标题不能用于排序。|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|单击单元或列标题将选择整个列。 列标题不能用于排序。|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|单击单元格或行标题将选择整行。|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|默认选择模式。 单击单元格会将其选中。 单击行标题会选择整行。|

> [!NOTE]
> 在运行时更改选择模式会自动清除当前选定内容。

默认情况下，用户可以通过使用鼠标拖动、按 CTRL 或 SHIFT 的同时选择以扩展或修改选择，或者单击左上方标题单元格来选择控件中的所有单元格，来选择多个行、列或单元格。 若要防止此行为，请将 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 属性设置为 `false`。

<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> 和 <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> 模式允许用户通过选择行并按 DELETE 键来删除行。 仅当当前单元格未处于编辑模式，<xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> 属性设置为 `true`，并且基础数据源支持用户驱动的行删除时，用户才可以删除行。 请注意，这些设置不会阻止编程行删除。

## <a name="programmatic-selection"></a>编程选择

当前选择模式会限制编程选择和用户选择的行为。 您可以通过设置 <xref:System.Windows.Forms.DataGridView> 控件中的任何单元格、行或列的 `Selected` 属性，以编程方式更改当前选择。 还可以通过 <xref:System.Windows.Forms.DataGridView.SelectAll%2A> 方法选择控件中的所有单元格，具体取决于选择模式。 若要清除所选内容，请使用 <xref:System.Windows.Forms.DataGridView.ClearSelection%2A> 方法。

如果将 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 属性设置为 `true`，则可以通过更改元素的 `Selected` 属性，将 <xref:System.Windows.Forms.DataGridView> 元素添加到选定内容或从中删除这些元素。 否则，将 `Selected` 属性设置为 `true` 一个元素会自动从选定内容中删除其他元素。

请注意，更改 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 属性的值不会更改当前所选内容。

您可以通过 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>、<xref:System.Windows.Forms.DataGridView.SelectedRows%2A>和 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 属性检索当前选定的单元格、行或列的集合。 当控件中的每个单元格都处于选定状态时，访问这些属性是低效的。 为了避免在这种情况下对性能产生负面影响，请首先使用 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> 方法。 此外，访问这些集合来确定所选单元格、行或列的数量可能效率低下。 应改为使用 <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>、<xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>或 <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A> 方法，并传入 <xref:System.Windows.Forms.DataGridViewElementStates.Selected> 值。

> [!TIP]
> 演示如何在 <xref:System.Windows.Forms.DataGridView> 类概述中找到所选单元格的编程使用的示例代码。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤의 선택 모드 설정](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)
