---
title: 在 DataGridView 控件中设置数据格式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in DataGridView control
- data grids [Windows Forms], enabling wordwrap
- currency values [Windows Forms], formatting in data grids
- data grids [Windows Forms], currency values
- data grids [Windows Forms], formatting data
- data grids [Windows Forms], text alignment
- data grids [Windows Forms], date values
- cells [Windows Forms], text alignment
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
ms.openlocfilehash: 9ee2869cf4085b5acfdf1f8c440151be506dbe3e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736789"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a>如何：设置 Windows 窗体 DataGridView 控件中的数据格式
下面的过程演示如何使用 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> 属性和控件中特定列的单元格值的基本格式设置。 有关高级数据格式设置的信息，请参阅[如何：自定义 Windows 窗体 DataGridView 控件中的数据格式](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)。  
  
### <a name="to-format-currency-and-date-values"></a>设置货币和日期值的格式  
  
- 设置 <xref:System.Windows.Forms.DataGridViewCellStyle> 的 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 属性。 下面的代码示例使用列的 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> 属性设置特定列的格式。 "`UnitPrice`" 列中的值以当前特定于区域性的货币格式显示，其中负值括在括号中。 "`ShipDate`" 列中的值以当前特定于区域性的短日期格式显示。 有关 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 值的详细信息，请参阅[格式设置类型](../../../standard/base-types/formatting-types.md)。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a>自定义 null 数据库值的显示  
  
- 设置 <xref:System.Windows.Forms.DataGridViewCellStyle> 的 <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> 属性。 下面的代码示例使用 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> 属性在包含等于 <xref:System.DBNull.Value?displayProperty=nameWithType>的值的所有单元格中显示 "no entry"。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a>在基于文本的单元中启用换行  
  
- 将 <xref:System.Windows.Forms.DataGridViewCellStyle> 的 <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> 属性设置为 <xref:System.Windows.Forms.DataGridViewTriState> 枚举值之一。 下面的代码示例使用 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> 属性为整个控件设置环绕模式。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a>指定 DataGridView 单元格的文本对齐方式  
  
- 将 <xref:System.Windows.Forms.DataGridViewCellStyle> 的 <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> 属性设置为 <xref:System.Windows.Forms.DataGridViewContentAlignment> 枚举值之一。 下面的代码示例使用列的 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> 属性设置特定列的对齐方式。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a>编译代码  
 这些示例需要：  
  
- 名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件，其中包含一个名为 `UnitPrice`的列、一个名为 `ShipDate`的列和一个名为 `CustomerName`的列。  
  
- 对 <xref:System?displayProperty=nameWithType><xref:System.Drawing?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="robust-programming"></a>可靠的编程  
 为了获得最大的可伸缩性，你应跨多个使用相同样式的行、列或单元格共享 <xref:System.Windows.Forms.DataGridViewCellStyle> 对象，而不是单独设置每个元素的样式属性。 有关详细信息，请参阅[缩放 Windows 窗体 DataGridView 控件的最佳做法](best-practices-for-scaling-the-windows-forms-datagridview-control.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Windows 窗体 DataGridView 控件中的基本格式和样式设置](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的数据格式设置](data-formatting-in-the-windows-forms-datagridview-control.md)
- [如何：在 Windows 窗体 DataGridView 控件中自定义数据格式设置](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [格式设置类型](../../../standard/base-types/formatting-types.md)
