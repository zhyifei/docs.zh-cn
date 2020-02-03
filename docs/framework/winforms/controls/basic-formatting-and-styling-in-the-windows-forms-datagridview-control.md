---
title: DataGridView 控件中的基本格式设置和样式设置
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
ms.openlocfilehash: d295718b7bd4f3bc4c5f63b6e6cb911f733525fe
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731995"
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的基本格式设置和样式设置
利用 `DataGridView` 控件，可以轻松定义单元格的基本外观和单元格值的显示格式。 可以通过设置通过各种 `DataGridView` 控件属性访问的 `DataGridViewCellStyle` 对象的属性，为单独的单元格、特定的列和行中的单元格或控件中的所有单元定义外观和格式设置样式。 此外，您还可以通过处理 `CellFormatting` 事件，根据单元值等因素动态修改这些样式。  
  
## <a name="in-this-section"></a>本节内容  
 [如何：在 Windows 窗体 DataGridView 控件中更改边框和网格线的样式](change-the-border-and-gridline-styles-in-the-datagrid.md)  
 描述如何设置 `DataGridView` 属性，这些属性定义控件边框的外观和单元格间的边界线条。  
  
 [Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)  
 介绍 `DataGridViewCellStyle` 类以及该类型的属性如何交互以定义单元格在控件中的显示方式。  
  
 [如何：设置 Windows 窗体 DataGridView 控件的默认单元格样式](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 介绍如何使用 `DataGridViewCellStyle` 属性来定义特定行和列以及整个控件中的单元格的默认外观。  
  
 [如何：在 Windows 窗体 DataGridView 控件中设置数据格式](how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 介绍如何使用 `DataGridViewCellStyle` 属性设置单元格显示值的格式。  
  
 [如何：在 Windows 窗体 DataGridView 控件中设置字体和颜色样式](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 介绍如何使用 `DefaultCellStyle` 属性为控件中的所有单元格设置基本显示特性。  
  
 [如何：设置 Windows 窗体 DataGridView 控件的交替行样式](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 介绍如何使用以不同方式显示的交替行在控件中创建类似帐目型的效果。  
  
 [如何：使用行模板在 Windows 窗体 DataGridView 控件中自定义行](use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 描述如何使用 `RowTemplate` 属性设置将用于控件中所有行的行属性。  
  
## <a name="reference"></a>参考  
 <xref:System.Windows.Forms.DataGridView>  
 提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 提供 <xref:System.Windows.Forms.DataGridViewCellStyle> 类的参考文档。  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 提供 <xref:System.Windows.Forms.DataGridView.CellFormatting> 事件的参考文档。  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 提供 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> 属性的参考文档。  
  
## <a name="related-sections"></a>相关章节  
 [自定义 Windows 窗体 DataGridView 控件](customizing-the-windows-forms-datagridview-control.md)  
 提供一些主题，介绍自定义绘制 <xref:System.Windows.Forms.DataGridView> 单元格和行，以及创建派生的单元、列和行类型。  
  
 [Windows 窗体 DataGridView 控件中的列、行和单元格基本功能](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 提供一些主题，这些主题描述常用的单元格、行和列属性。  
  
## <a name="see-also"></a>另请参阅

- [DataGridView 控件](datagridview-control-windows-forms.md)
