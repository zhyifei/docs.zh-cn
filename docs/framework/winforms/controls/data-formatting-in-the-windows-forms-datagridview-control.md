---
title: DataGridView 控件中的数据格式设置
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
ms.openlocfilehash: a041bcc5e1b65afb3123f1f42e0f1b5a479b5764
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743981"
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的数据格式设置
<xref:System.Windows.Forms.DataGridView> 控件提供了单元值与父列显示的数据类型之间的自动转换。 例如，文本框列显示日期、时间、数字和枚举值的字符串表示形式，并将用户输入的字符串值转换为数据存储所需的类型。  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a>用 DataGridViewCellStyle 类设置格式  
 <xref:System.Windows.Forms.DataGridView> 控件通过 <xref:System.Windows.Forms.DataGridViewCellStyle> 类提供单元格值的基本数据格式设置。 您可以使用 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 属性，使用格式[设置类型](../../../standard/base-types/formatting-types.md)中描述的格式说明符来设置当前默认区域性的日期、时间、数字和枚举值的格式。 你还可以使用 <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A> 属性为特定区域性设置这些值的格式。 指定的格式用于显示数据，并用于分析用户输入的指定格式的数据。  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle> 类提供了换行、文本对齐和 null 数据库值的自定义显示的其他格式设置属性。 有关详细信息，请参阅[如何：设置 Windows 窗体 DataGridView 控件中的数据格式](how-to-format-data-in-the-windows-forms-datagridview-control.md)。  
  
## <a name="formatting-with-the-cellformatting-event"></a>用 CellFormatting 事件设置格式  
 如果基本格式设置不能满足您的需要，您可以在 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> 事件的处理程序中提供自定义数据格式设置。 传递到处理程序的 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> 具有一个最初包含单元格值的 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 属性。 通常，此值将自动转换为显示类型。 若要自行转换该值，请将 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 属性设置为显示类型的值。  
  
> [!NOTE]
> 如果该单元格的格式字符串有效，则它将覆盖 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 属性值的更改，除非将 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> 属性设置为 `true`。  
  
 如果要基于单个单元格的值设置 <xref:System.Windows.Forms.DataGridViewCellStyle> 属性，则 <xref:System.Windows.Forms.DataGridView.CellFormatting> 事件也很有用。 有关详细信息，请参阅[如何：自定义 Windows 窗体 DataGridView 控件中的数据格式](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)。  
  
 如果用户指定值的默认分析无法满足您的需要，您可以处理 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.CellParsing> 事件以提供自定义分析。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [在 Windows 窗体 DataGridView 控件中显示数据](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)
- [如何：在 Windows 窗体 DataGridView 控件中设置数据格式](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [如何：在 Windows 窗体 DataGridView 控件中自定义数据格式设置](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
