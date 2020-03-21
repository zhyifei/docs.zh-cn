---
title: ToolTip 概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], about ToolTip control
- controls [WPF], ToolTip
ms.assetid: f06c1603-e9cb-4809-8a62-234607fc52f7
ms.openlocfilehash: 0fec31b28a21c2e17986210c852b3d630087842d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181953"
---
# <a name="tooltip-overview"></a>ToolTip 概述
工具提示是当用户将鼠标指针悬停在元素（如 在 上）时出现的一个小弹出窗口<xref:System.Windows.Controls.Button>。 本主题介绍工具提示，并讨论如何创建和自定义工具提示内容。  

<a name="what_is_a_tooltip"></a>
## <a name="what-is-a-tooltip"></a>什么是工具提示？  
 当用户将鼠标指针移动到具有工具提示的元素上时，将在一段指定的时间内显示一个包含工具提示内容（例如，介绍控件功能的文本内容）的窗口。 如果用户将鼠标指针从控件上移开，该窗口将消失，因为工具提示内容无法接收焦点。  
  
 工具提示的内容可以包含一行或多行文本、图像、形状或其他可视内容。 通过将以下属性之一设置为工具提示内容来定义控件的工具提示。  
  
- <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType>  
  
 您使用的属性取决于定义工具提示的控件是否从<xref:System.Windows.FrameworkContentElement>或<xref:System.Windows.FrameworkElement>类继承。  
  
<a name="create_tooltip"></a>
## <a name="creating-a-tooltip"></a>创建工具提示  
 下面的示例演示如何通过将<xref:System.Windows.FrameworkElement.ToolTip%2A><xref:System.Windows.Controls.Button>控件的属性设置为文本字符串来创建简单的工具提示。  
  
 [!code-xaml[GroupBoxSnippet#ToolTipString](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 您还可以将工具提示定义为<xref:System.Windows.Controls.ToolTip>对象。 下面的示例用于[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]指定<xref:System.Windows.Controls.ToolTip>对象作为<xref:System.Windows.Controls.TextBox>元素的工具提示。 请注意，该示例<xref:System.Windows.Controls.ToolTip>通过设置 属性指定<xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType>。  
  
 [!code-xaml[ToolTipSimple#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 下面的示例使用代码生成<xref:System.Windows.Controls.ToolTip>对象。 该示例创建<xref:System.Windows.Controls.ToolTip>一`tt`个 （ ，<xref:System.Windows.Controls.Button>并将其与 关联它与 。  
  
 [!code-csharp[ToolTipSimple#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 还可以通过将工具提示内容封闭在布局元素（如<xref:System.Windows.Controls.ToolTip><xref:System.Windows.Controls.DockPanel>中）来创建未定义为对象的工具提示内容。 下面的示例演示如何将<xref:System.Windows.FrameworkElement.ToolTip%2A>中的 属性<xref:System.Windows.Controls.TextBox>设置为包含在<xref:System.Windows.Controls.DockPanel>控件中的内容。  
  
 [!code-xaml[GroupBoxSnippet#ToolTipDockPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>
## <a name="using-the-properties-of-the-tooltip-and-tooltipservice-classes"></a>使用 ToolTipd 和 ToolTipService 类的属性  
 可以通过设置视觉属性和应用样式来自定义工具提示内容。 如果将工具提示内容定义为<xref:System.Windows.Controls.ToolTip>对象，则可以设置<xref:System.Windows.Controls.ToolTip>对象的可视属性。 否则，必须在<xref:System.Windows.Controls.ToolTipService>类上设置等效的附加属性。  
  
 有关如何设置属性以便使用<xref:System.Windows.Controls.ToolTip>和<xref:System.Windows.Controls.ToolTipService>属性指定工具提示内容的位置的示例，请参阅[定位工具提示](how-to-position-a-tooltip.md)。  
  
<a name="StylingToolTip"></a>
## <a name="styling-a-tooltip"></a>设置工具提示样式  
 您可以通过定义自定义<xref:System.Windows.Style><xref:System.Windows.Controls.ToolTip>来设置 样式 。 下面的<xref:System.Windows.Style>示例定义一个调用`Simple`，它演示如何通过设置<xref:System.Windows.Controls.ToolTip><xref:System.Windows.Controls.Control.Background%2A>、<xref:System.Windows.Controls.Control.Foreground%2A>和<xref:System.Windows.Controls.Control.FontSize%2A>来抵消 的位置并更改其外观。 <xref:System.Windows.Controls.Control.FontWeight%2A>  
  
 [!code-xaml[ToolTipSimple#Style](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>
## <a name="using-the-time-interval-properties-of-tooltipservice"></a>使用 ToolTipService 的 Time Interval 属性  
 该<xref:System.Windows.Controls.ToolTipService>类提供以下属性，用于设置工具提示显示时间：<xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>和<xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>。 <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>  
  
 使用<xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>和<xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>属性指定<xref:System.Windows.Controls.ToolTip>出现之前的延迟（通常简短），并指定<xref:System.Windows.Controls.ToolTip>保留的可见时间。 有关详细信息，请参阅[如何：延迟 ToolTip 的显示](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms747264(v=vs.90))。  
  
 该<xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>属性确定在鼠标指针之间快速移动鼠标指针时，不同控件的工具提示是否不会出现初始延迟。 有关该<xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>属性的详细信息，请参阅[使用"ShowDelay 之间"属性](how-to-use-the-betweenshowdelay-property.md)。  
  
 以下示例演示如何为工具提示设置这些属性。  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.ToolTipService>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipEventArgs>
- <xref:System.Windows.Controls.ToolTipEventHandler>
- [如何使用主题](tooltip-how-to-topics.md)
