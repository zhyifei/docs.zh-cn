---
title: "Windows 窗体 DataGridView 控件中的选择模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f0d605b7ee7e48ad0ed2e693f0e71e5f1c25e022
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的选择模式
有时你希望应用程序以根据用户中的选定内容执行操作<xref:System.Windows.Forms.DataGridView>控件。 根据操作，你可能想要限制可能会出现的各种选择。 例如，假设你的应用程序可以打印当前所选记录的报表。 在这种情况下，你可能想要配置<xref:System.Windows.Forms.DataGridView>控件，以便单击任意位置行中始终选择整行，并且可以选择一次只有一个该行。  
  
 你可以指定允许的设置的所选<xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>属性设置为以下项之一<xref:System.Windows.Forms.DataGridViewSelectionMode>枚举值。  
  
|DataGridViewSelectionMode 值|描述|  
|-------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|单击单元格选择它。 标题行和列标题不能用于所选内容。|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|单击单元格选择它。 单击列标题可以选择整个列。 列标题不能用于排序。|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|单击单元格或列标题可以选择整个列。 列标题不能用于排序。|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|单击单元格或行标题选择整个行。|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|默认选择模式。 单击单元格选择它。 单击行标题选择整行。|  
  
> [!NOTE]
>  更改选择模式，在运行时自动清除当前的选择。  
  
 默认情况下，用户可以选择多个行、 列或单元格通过拖动鼠标，按 CTRL 或 SHIFT 的同时选择以扩展或修改所选内容，或单击要在控件中选择所有单元格的左上角的标题单元格。 若要防止此行为，设置<xref:System.Windows.Forms.DataGridView.MultiSelect%2A>属性`false`。  
  
 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>和<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>模式允许用户通过选择它们并按 DELETE 键删除行。 仅当当前单元格不处于编辑模式时，用户可以删除行<xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A>属性设置为`true`，和基础数据源支持用户驱动行删除。 请注意这些设置不会阻止通过编程删除行。  
  
## <a name="programmatic-selection"></a>以编程方式选择  
 当前的选择模式限制以编程方式选择，以及用户所选内容的行为。 你可以通过设置以编程方式更改当前所选内容`Selected`属性的任何单元格、 行或列中存在<xref:System.Windows.Forms.DataGridView>控件。 你还可以通过控件中选择所有单元格<xref:System.Windows.Forms.DataGridView.SelectAll%2A>方法，具体取决于选择模式。 若要清除所选内容，使用<xref:System.Windows.Forms.DataGridView.ClearSelection%2A>方法。  
  
 如果<xref:System.Windows.Forms.DataGridView.MultiSelect%2A>属性设置为`true`，你可以添加<xref:System.Windows.Forms.DataGridView>到元素或删除它们从所选内容更改`Selected`元素的属性。 否则，设置`Selected`属性`true`的一个元素自动移除所选内容中的其他元素。  
  
 请注意该更改的值<xref:System.Windows.Forms.DataGridView.CurrentCell%2A>属性不会更改当前所选内容。  
  
 你可以检索的当前选定的单元格、 行或列到列集合<xref:System.Windows.Forms.DataGridView.SelectedCells%2A>， <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>，和<xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>属性<xref:System.Windows.Forms.DataGridView>控件。 选择控件中的每个单元格时，访问这些属性的效率低。 若要在此情况下避免对性能产生负面影响，请使用<xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>方法第一个。 此外，访问这些集合来确定所选单元格的数目，行或列可能效率很低。 相反，应使用<xref:System.Windows.Forms.DataGridView.GetCellCount%2A>， <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>，或<xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A>方法，同时传入<xref:System.Windows.Forms.DataGridViewElementStates.Selected>值。  
  
> [!TIP]
>  演示如何以编程方式使用选定的单元格的示例代码可在<xref:System.Windows.Forms.DataGridView>类概述。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>  
 <xref:System.Windows.Forms.DataGridViewSelectionMode>  
 [将选择模式和剪贴板与 Windows 窗体 DataGridView 控件结合使用](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)  
 [如何：设置 Windows 窗体 DataGridView 控件的选择模式](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)
