---
title: 对 DataGridView 控件中的数据进行排序
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 1fcd5a5f5c6d690c573c4c2c5fa7c32aa0292441
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742947"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a>对 Windows 窗体 DataGridView 控件中的数据进行排序

默认情况下，用户可以通过单击文本框列的标题来对 <xref:System.Windows.Forms.DataGridView> 控件中的数据进行排序（或者通过在文本框单元格集中于 .NET Framework 4.7.2 和更高版本时按 F3）来对数据进行排序。 您可以修改特定列的 <xref:System.Windows.Forms.DataGridViewColumn.SortMode> 属性，以允许用户在执行此操作时按其他列类型进行排序。 还可以通过编程方式按任何列或多个列对数据进行排序。

## <a name="in-this-section"></a>本节内容

[Windows 窗体 DataGridView 控件中的列排序模式](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
描述用于对控件中的数据进行排序的选项。

[如何：设置 Windows 窗体 DataGridView 控件中列的排序模式](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
介绍如何使用户能够按默认情况下不可排序的列排序。

[如何：在 Windows 窗体 DataGridView 控件中自定义排序](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
描述如何以编程方式对数据进行排序，以及如何通过使用 <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> 事件或通过实现 <xref:System.Collections.IComparer> 接口自定义排序。

## <a name="reference"></a>引用

<xref:System.Windows.Forms.DataGridView>  
提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
提供 <xref:System.Windows.Forms.DataGridView.Sort%2A> 方法的参考文档。

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
提供 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 属性的参考文档。

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
提供 <xref:System.Windows.Forms.DataGridViewColumnSortMode> 枚举的参考文档。

## <a name="see-also"></a>另请参阅

- [DataGridView 控件](datagridview-control-windows-forms.md)
- [Windows 窗体 DataGridView 控件中的列类型](column-types-in-the-windows-forms-datagridview-control.md)
