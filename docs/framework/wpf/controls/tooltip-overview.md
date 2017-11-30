---
title: "ToolTip 概述"
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
- ToolTip control [WPF], about ToolTip control
- controls [WPF], ToolTip
ms.assetid: f06c1603-e9cb-4809-8a62-234607fc52f7
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31bd56323e90368f850ae54854e6f50b63d5f7fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="tooltip-overview"></a>ToolTip 概述
工具提示是当用户将鼠标指针暂停元素，如过度时显示一个小型弹出窗口<xref:System.Windows.Controls.Button>。 本主题介绍工具提示，并讨论如何创建和自定义工具提示内容。  
  
 
  
<a name="what_is_a_tooltip"></a>   
## <a name="what-is-a-tooltip"></a>什么是工具提示？  
 当用户将鼠标指针移动到具有工具提示的元素上时，将在一段指定的时间内显示一个包含工具提示内容（例如，介绍控件功能的文本内容）的窗口。 如果用户将鼠标指针从控件上移开，该窗口将消失，因为工具提示内容无法接收焦点。  
  
 工具提示的内容可以包含一行或多行文本、图像、形状或其他可视内容。 通过将以下属性之一设置为工具提示内容来定义控件的工具提示。  
  
-   <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType>  
  
 所使用的属性取决于是否定义工具提示的控件继承自<xref:System.Windows.FrameworkContentElement>或<xref:System.Windows.FrameworkElement>类。  
  
<a name="create_tooltip"></a>   
## <a name="creating-a-tooltip"></a>创建工具提示  
 下面的示例演示如何通过设置创建简单的工具提示<xref:System.Windows.FrameworkElement.ToolTip%2A>属性<xref:System.Windows.Controls.Button>为文本字符串的控件。  
  
 [!code-xaml[GroupBoxSnippet#ToolTipString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 你还可以定义为工具提示<xref:System.Windows.Controls.ToolTip>对象。 下面的示例使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]指定<xref:System.Windows.Controls.ToolTip>对象作为的工具提示<xref:System.Windows.Controls.TextBox>元素。 请注意，该示例指定<xref:System.Windows.Controls.ToolTip>通过设置<xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType>属性。  
  
 [!code-xaml[ToolTipSimple#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 下面的示例使用代码生成<xref:System.Windows.Controls.ToolTip>对象。 该示例创建<xref:System.Windows.Controls.ToolTip>(`tt`) 并将其与关联<xref:System.Windows.Controls.Button>。  
  
 [!code-csharp[ToolTipSimple#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 你还可以创建未定义为工具提示内容<xref:System.Windows.Controls.ToolTip>括工具提示的内容在布局元素中，如对象<xref:System.Windows.Controls.DockPanel>。 下面的示例演示如何设置<xref:System.Windows.FrameworkElement.ToolTip%2A>属性<xref:System.Windows.Controls.TextBox>内容用括起来<xref:System.Windows.Controls.DockPanel>控件。  
  
 [!code-xaml[GroupBoxSnippet#ToolTipDockPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>   
## <a name="using-the-properties-of-the-tooltip-and-tooltipservice-classes"></a>使用 ToolTipd 和 ToolTipService 类的属性  
 可以通过设置视觉属性和应用样式来自定义工具提示内容。 如果定义作为内容的工具提示<xref:System.Windows.Controls.ToolTip>对象，你可以设置的视觉属性<xref:System.Windows.Controls.ToolTip>对象。 否则，必须设置等效的附加的属性上<xref:System.Windows.Controls.ToolTipService>类。  
  
 有关如何才能通过使用指定的工具提示的内容位置设置属性的示例<xref:System.Windows.Controls.ToolTip>和<xref:System.Windows.Controls.ToolTipService>属性，请参阅[放置工具提示](../../../../docs/framework/wpf/controls/how-to-position-a-tooltip.md)。  
  
<a name="StylingToolTip"></a>   
## <a name="styling-a-tooltip"></a>设置工具提示样式  
 你可以设置样式<xref:System.Windows.Controls.ToolTip>通过定义一个自定义<xref:System.Windows.Style>。 下面的示例定义<xref:System.Windows.Style>调用`Simple`，演示如何偏移量的位置<xref:System.Windows.Controls.ToolTip>和更改其外观，通过设置<xref:System.Windows.Controls.Control.Background%2A>， <xref:System.Windows.Controls.Control.Foreground%2A>， <xref:System.Windows.Controls.Control.FontSize%2A>，和<xref:System.Windows.Controls.Control.FontWeight%2A>。  
  
 [!code-xaml[ToolTipSimple#Style](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>   
## <a name="using-the-time-interval-properties-of-tooltipservice"></a>使用 ToolTipService 的 Time Interval 属性  
 <xref:System.Windows.Controls.ToolTipService>类提供了以下属性，你才能设置工具提示显示时间： <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>， <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>，和<xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>。  
  
 使用<xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>和<xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>属性指定的延迟通常很短，之前<xref:System.Windows.Controls.ToolTip>显示并且还可指定多长时间<xref:System.Windows.Controls.ToolTip>保持可见。 有关详细信息，请参阅[如何：延迟 ToolTip 的显示](http://msdn.microsoft.com/en-us/618e05ef-f2bf-4a53-a0f4-aacb49918bd7)。  
  
 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>属性确定是否为不同的控件的工具提示不经历初始延迟时显示你将鼠标指针移动快速它们之间。 有关详细信息<xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>属性，请参阅[使用 BetweenShowDelay 属性](../../../../docs/framework/wpf/controls/how-to-use-the-betweenshowdelay-property.md)。  
  
 以下示例演示如何为工具提示设置这些属性。  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Controls.ToolTipService>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipEventArgs>  
 <xref:System.Windows.Controls.ToolTipEventHandler>  
 [操作说明主题](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
