---
title: 如何：定位 ToolTip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
ms.openlocfilehash: 0f52703e4fe127daa40f220280f084b2026580cc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186939"
---
# <a name="how-to-position-a-tooltip"></a>如何：定位 ToolTip
此示例演示如何在屏幕上指定工具提示的位置。  
  
## <a name="example"></a>示例  
 可以使用 在 和<xref:System.Windows.Controls.ToolTip><xref:System.Windows.Controls.ToolTipService>类 中定义的一组五个属性来定位工具提示。 下表显示了这两组五个属性，并根据类提供指向其参考文档的链接。  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a>根据类对应的工具提示属性  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType>类属性|<xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType>类属性|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 如果使用对象定义工具提示的内容，则可以使用任一类的属性<xref:System.Windows.Controls.ToolTip>;如果使用对象定义工具提示的内容，则可以使用任一类的属性。但是，<xref:System.Windows.Controls.ToolTipService>属性优先。 对未<xref:System.Windows.Controls.ToolTipService>定义为<xref:System.Windows.Controls.ToolTip>对象的工具提示使用属性。  
  
 下图显示了如何使用这些属性定位工具提示。 尽管这些插图[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中的示例演示如何设置由<xref:System.Windows.Controls.ToolTip>类定义的属性，但类的<xref:System.Windows.Controls.ToolTipService>相应属性遵循相同的布局规则。 有关放置属性的可能值的详细信息，请参阅[弹出放置行为](popup-placement-behavior.md)。  

 下图显示了使用"放置"属性的工具提示放置：  
  
 ![使用放置属性显示工具提示放置的图表。](./media/how-to-position-a-tooltip/tooltip-placement-property.png)

 下图使用"放置"和"放置矩形"属性显示工具提示放置：

 ![使用放置矩形属性显示工具提示放置位置的图表。](./media/how-to-position-a-tooltip/tooltip-placement-rectangle-property.png)  

 下图使用"放置"、放置矩形和偏移属性显示工具提示放置：
  
 ![使用"偏移"属性显示工具提示放置位置的图表。](./media/how-to-position-a-tooltip/tooltip-placement-offset-property.png)

 下面的示例演示如何使用<xref:System.Windows.Controls.ToolTip>属性来指定其内容为<xref:System.Windows.Controls.ToolTip>对象的工具提示的位置。  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 下面的示例演示如何使用<xref:System.Windows.Controls.ToolTipService>属性来指定其内容不是<xref:System.Windows.Controls.ToolTip>对象的工具提示的位置。  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [如何使用主题](tooltip-how-to-topics.md)
- [ToolTip 概述](tooltip-overview.md)
