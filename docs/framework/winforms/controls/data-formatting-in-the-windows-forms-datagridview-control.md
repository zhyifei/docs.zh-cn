---
title: "Windows 窗体 DataGridView 控件中的数据格式设置"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6ff3452a60d9cb80a71dacd5841b120b5efbf82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的数据格式设置
<xref:System.Windows.Forms.DataGridView>控件提供单元格的值的父列显示的数据类型之间的自动转换。 文本框列，例如，显示的日期、 时间、 号和枚举值的字符串表示形式，并将用户输入的字符串值转换为数据存储所需的类型。  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a>使用 DataGridViewCellStyle 类进行格式设置  
 <xref:System.Windows.Forms.DataGridView>控件提供的单元格的值，通过基本数据格式设置<xref:System.Windows.Forms.DataGridViewCellStyle>类。 你可以使用<xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>为当前使用中所述的格式说明符的默认区域性的格式日期、 时间、 编号和枚举值的属性[格式化类型](../../../../docs/standard/base-types/formatting-types.md)。 你还可以设置特定区域性使用这些值进行格式<xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>属性。 使用指定的格式显示数据和分析用户在指定的格式中输入的数据。  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>类提供了附加的格式设置属性，自动换行、 文本对齐方式，以及数据库空值的自定义显示。 有关详细信息，请参阅[如何：设置 Windows 窗体 DataGridView 控件中的数据格式](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)。  
  
## <a name="formatting-with-the-cellformatting-event"></a>与 CellFormatting 事件格式设置  
 如果基本格式设置不符合你的需求，你可以提供自定义数据的处理程序中的格式设置<xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>事件。 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs>传递给处理程序具有<xref:System.Windows.Forms.ConvertEventArgs.Value%2A>最初包含单元格的值的属性。 通常情况下，此值会自动转换为显示类型。 若要自行转换该值，将设置<xref:System.Windows.Forms.ConvertEventArgs.Value%2A>属性显示类型的值。  
  
> [!NOTE]
>  如果单元格实际上是一个格式字符串，它将覆盖您对修改<xref:System.Windows.Forms.ConvertEventArgs.Value%2A>属性值，除非你设置<xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A>属性`true`。  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>事件非常有用，当你想要设置<xref:System.Windows.Forms.DataGridViewCellStyle>各个单元格的属性基于其值。 有关详细信息，请参阅[如何： 在 Windows 窗体 DataGridView 控件中自定义数据格式](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)。  
  
 如果用户指定值的默认分析不满足你的需求，你可以处理<xref:System.Windows.Forms.DataGridView.CellParsing>事件<xref:System.Windows.Forms.DataGridView>控件提供自定义分析。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 [在 Windows 窗体 DataGridView 控件中显示数据](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Windows 窗体 DataGridView 控件中的单元格样式](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [如何：在 Windows 窗体 DataGridView 控件中设置数据格式](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 [如何：在 Windows 窗体 DataGridView 控件中自定义数据格式设置](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
