---
title: "如何：定位 ToolTip"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62e86f2adfbe8f8aac000d653e955555c7def750
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-position-a-tooltip"></a>如何：定位 ToolTip
此示例演示如何在屏幕上指定的工具提示的位置。  
  
## <a name="example"></a>示例  
 您可以使用一组中都定义的五个属性来定位工具提示<xref:System.Windows.Controls.ToolTip>和<xref:System.Windows.Controls.ToolTipService>类。 下表显示五个属性这两个集，并提供指向其根据类的参考文档。  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a>类根据相应的工具提示属性  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType>类属性|<xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType>类属性|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 如果您通过使用定义的工具提示的内容<xref:System.Windows.Controls.ToolTip>对象时，你可以使用其中一个类的属性; 但是，<xref:System.Windows.Controls.ToolTipService>属性优先。 使用<xref:System.Windows.Controls.ToolTipService>属性未定义为的工具提示<xref:System.Windows.Controls.ToolTip>对象。  
  
 下图显示如何使用这些属性来定位工具提示。 尽管、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]在这些说明中的示例演示如何设置的属性定义的<xref:System.Windows.Controls.ToolTip>类的对应属性<xref:System.Windows.Controls.ToolTipService>类遵循相同的布局规则。 有关放置属性的可能值的详细信息，请参阅[弹出项放置行为](../../../../docs/framework/wpf/controls/popup-placement-behavior.md)。  
  
 ![ToolTip 定位](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")  
ToolTip 定位使用放置属性  
  
 ![通过使用定位矩形 tooltip](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")  
通过使用放置和 PlacementRectangle 属性的 ToolTip 定位  
  
 ![ToolTip 定位示意图](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")  
通过使用放置、 PlacementRectangle 和偏移量属性的 ToolTip 定位  
  
 下面的示例演示如何使用<xref:System.Windows.Controls.ToolTip>属性以指定其内容的工具提示的位置<xref:System.Windows.Controls.ToolTip>对象。  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 下面的示例演示如何使用<xref:System.Windows.Controls.ToolTipService>属性以指定其内容不属于的工具提示的位置<xref:System.Windows.Controls.ToolTip>对象。  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [帮助主题](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [ToolTip 概述](../../../../docs/framework/wpf/controls/tooltip-overview.md)  
 [使用 ContextMenuService 和 ToolTipService](http://msdn.microsoft.com/en-us/809b0e9c-d612-4cda-b8af-1a698c68f4d1)
