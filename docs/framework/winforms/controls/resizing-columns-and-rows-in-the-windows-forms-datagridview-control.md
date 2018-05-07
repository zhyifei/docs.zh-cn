---
title: 调整 Windows 窗体 DataGridView 控件中列和行的大小
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
ms.openlocfilehash: 1e501d124ccec749537d319b992c5caf00b025f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a>调整 Windows 窗体 DataGridView 控件中列和行的大小
`DataGridView`控件提供许多选项用于自定义其列和行的大小调整行为。 通常情况下，`DataGridView`单元格，不要调整大小基于其内容。 相反，它们剪切任何大于单元格的显示值。 如果内容可以显示为一个字符串，该单元格在工具提示中显示它。  
  
 默认情况下，用户可以拖动行、 列和标头使用鼠标以显示详细信息的分隔线。 用户还可以双击分隔符以自动调整大小以适应内容的关联的行、 列或标头带区。  
  
 `DataGridView`控件提供属性、 方法和事件，您可以自定义或禁用所有这些用户重定向的行为。 此外，可以以编程方式调整大小的行、 列和标头以适应其内容，或你可以将它们配置为自动调整自身大小，其内容更改时。 你还可以配置将自动在你指定的比例控件的可用宽度的列。  
  
## <a name="in-this-section"></a>本节内容  
 [Windows 窗体 DataGridView 控件中的重设大小选项](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)  
 介绍有关大小调整行、 列和标头的选项。 此外提供大小调整相关属性和方法，有关详细信息，并描述了常见使用方案。  
  
 [Windows 窗体 DataGridView 控件中的列填充模式](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 描述列填充模式中的详细信息，并提供可用于体验列填充模式和其他模式的演示代码。  
  
 [如何：设置 Windows 窗体 DataGridView 控件的重设大小模式](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 描述如何为常见用途配置的大小调整模式。  
  
 [如何：以编程方式重设单元格大小以适应 Windows 窗体 DataGridView 控件中的内容](../../../../docs/framework/winforms/controls/programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 提供可用于试验以编程方式调整大小的演示代码。  
  
 [如何：在 Windows 窗体 DataGridView 控件中的内容发生变化时自动重设单元格大小](../../../../docs/framework/winforms/controls/automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 提供可用于试验自动调整大小模式的演示代码。  
  
## <a name="reference"></a>参考  
 <xref:System.Windows.Forms.DataGridView>  
 提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。  
  
## <a name="see-also"></a>请参阅  
 [DataGridView 控件](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
