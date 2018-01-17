---
title: "Alignment、Margin 和 Padding 概述"
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
- cpp
helpviewer_keywords:
- margins [WPF]
- padding [WPF]
- aligning [WPF]
ms.assetid: 9c6a2009-9b86-4e40-8605-0a2664dc3973
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9d53ec57bdd6126aa1b82e3fa34d01b8907ca169
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="alignment-margins-and-padding-overview"></a>Alignment、Margin 和 Padding 概述
<xref:System.Windows.FrameworkElement>类公开多个用于精确定位子元素的属性。 本主题讨论四个最重要的属性： <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>， <xref:System.Windows.FrameworkElement.Margin%2A>， <xref:System.Windows.Controls.Border.Padding%2A>，和<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>。 了解这些属性的作用非常重要，因为这些属性是控制元素在 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 应用程序中的位置的基础。  
  
  
<a name="wcpsdk_layout_amp_introduction"></a>   
## <a name="introduction-to-element-positioning"></a>元素定位简介  
 可使用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 通过多种方式来定位元素。 但是，获得理想的布局体现在只需选择合适<xref:System.Windows.Controls.Panel>元素。 对定位进行精细控制需要了解<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>， <xref:System.Windows.FrameworkElement.Margin%2A>， <xref:System.Windows.Controls.Border.Padding%2A>，和<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性。  
  
 下图显示了一个采用若干定位属性的布局方案。  
  
 ![WPF 定位属性示例](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-alignment-graphic1.PNG "layout_margins_padding_alignment_graphic1")  
  
 从表面看，<xref:System.Windows.Controls.Button>在此图中的元素可能看起来随意放置。 但是，其位置实际上是通过使用边距、对齐和填充加以精确控制的。  
  
 下面的示例描述如何创建上图中的布局。 A<xref:System.Windows.Controls.Border>元素封装了父<xref:System.Windows.Controls.StackPanel>，与<xref:System.Windows.Controls.Border.Padding%2A>15 与设备无关的像素的值。 此操作占窄的<xref:System.Windows.Media.Brushes.LightBlue%2A>带环绕子<xref:System.Windows.Controls.StackPanel>。 子元素的<xref:System.Windows.Controls.StackPanel>用于阐释每本主题中详述的各种定位属性。 三个<xref:System.Windows.Controls.Button>元素用于演示同时<xref:System.Windows.FrameworkElement.Margin%2A>和<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性。  
  
 [!code-csharp[MPALayoutSampleIntro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 通过下图可以仔细查看上例中使用的各个定位属性。 本主题的后面各节更详细地介绍了如何使用各个定位属性。  
  
 ![具有屏幕标注的定位属性](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-alignment-graphic2.PNG "layout_margins_padding_alignment_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>   
## <a name="understanding-alignment-properties"></a>了解 Alignment 属性  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>和<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性描述了如何子元素应放置在父元素的已分配的布局空间内。 结合使用这些属性可精确定位子元素。 例如，子元素的<xref:System.Windows.Controls.DockPanel>可以指定四个不同的水平对齐方式： <xref:System.Windows.HorizontalAlignment.Left>， <xref:System.Windows.HorizontalAlignment.Right>，或<xref:System.Windows.HorizontalAlignment.Center>，或<xref:System.Windows.HorizontalAlignment.Stretch>以填充可用空间。 类似的值可用于垂直定位。  
  
> [!NOTE]
>  显式设置<xref:System.Windows.FrameworkElement.Height%2A>和<xref:System.Windows.FrameworkElement.Width%2A>上一个元素的属性优先于<xref:System.Windows.HorizontalAlignment.Stretch>属性值。 正在尝试设置<xref:System.Windows.FrameworkElement.Height%2A>， <xref:System.Windows.FrameworkElement.Width%2A>，和一个<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>值`Stretch`导致`Stretch`请求被忽略。  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>   
### <a name="horizontalalignment-property"></a>HorizontalAlignment 属性  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性声明要应用于子元素的水平对齐特征。 下表显示了每个可能的值的<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性。  
  
|成员|描述|  
|------------|-----------------|  
|<xref:System.Windows.HorizontalAlignment.Left>|子元素与父元素的已分配布局空间的左端对齐。|  
|<xref:System.Windows.HorizontalAlignment.Center>|子元素与父元素的已分配布局空间的中心对齐。|  
|<xref:System.Windows.HorizontalAlignment.Right>|子元素与父元素的已分配布局空间的右端对齐。|  
|<xref:System.Windows.HorizontalAlignment.Stretch>（默认值）|拉伸子元素以填充父元素的已分配布局空间。 显式<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>值优先。|  
  
 下面的示例演示如何将应用<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性<xref:System.Windows.Controls.Button>元素。 显示每个特性值，以便更好地阐释各种呈现行为。  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 以上代码将产生与下图类似的布局。 每个定位效果<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>值是在图中可见。  
  
 ![HorizontalAlignment 示例](../../../../docs/framework/wpf/advanced/media/layout-horizontal-alignment-graphic.PNG "layout_horizontal_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>   
### <a name="verticalalignment-property"></a>VerticalAlignment 属性  
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性描述要应用于子元素的垂直对齐特征。 下表显示了每个的可能值<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性。  
  
|成员|描述|  
|------------|-----------------|  
|<xref:System.Windows.VerticalAlignment.Top>|子元素与父元素的已分配布局空间的顶端对齐。|  
|<xref:System.Windows.VerticalAlignment.Center>|子元素与父元素的已分配布局空间的中心对齐。|  
|<xref:System.Windows.VerticalAlignment.Bottom>|子元素与父元素的已分配布局空间的底端对齐。|  
|<xref:System.Windows.VerticalAlignment.Stretch>（默认值）|拉伸子元素以填充父元素的已分配布局空间。 显式<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>值优先。|  
  
 下面的示例演示如何将应用<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性<xref:System.Windows.Controls.Button>元素。 显示每个特性值，以便更好地阐释各种呈现行为。 此示例的目的<xref:System.Windows.Controls.Grid>可见的网格线具有元素使用作为父项，以更好地说明每个属性值的布局行为。  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xaml[MPALayoutVerticalAlignment#2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 以上代码将产生与下图类似的布局。 每个定位效果<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>值是在图中可见。  
  
 ![VerticalAlignment 属性示例](../../../../docs/framework/wpf/advanced/media/layout-vertical-alignment-graphic.PNG "layout_vertical_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>   
## <a name="understanding-margin-properties"></a>了解 Margin 属性  
 <xref:System.Windows.FrameworkElement.Margin%2A>属性描述元素及其子或对等方之间的距离。 <xref:System.Windows.FrameworkElement.Margin%2A>值可以通过使用类似的语法统一， `Margin="20"`。 使用以下语法，一个统一的<xref:System.Windows.FrameworkElement.Margin%2A>的 20 设备无关的像素将应用于的元素。 <xref:System.Windows.FrameworkElement.Margin%2A>值可以也采用以下形式的四个非重复值，每个值，描述要应用于左侧、 顶部、 右侧和 （按此顺序） 的底部的不同边距如`Margin="0,10,5,25"`。 正确使用<xref:System.Windows.FrameworkElement.Margin%2A>属性使非常精确地控制元素的呈现位置，以及其邻居元素及其子级的呈现位置。  
  
> [!NOTE]
>  非零边距适用的元素之外的空间<xref:System.Windows.FrameworkElement.ActualWidth%2A>和<xref:System.Windows.FrameworkElement.ActualHeight%2A>。  
  
 下面的示例演示如何将应用的一组周围的统一边距<xref:System.Windows.Controls.Button>元素。 <xref:System.Windows.Controls.Button>元素上使用每个方向一个 10 像素的边距的缓冲区均匀。  
  
 [!code-cpp[MarginPaddingAlignmentSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#1)]
 [!code-csharp[MarginPaddingAlignmentSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#1)]
 [!code-vb[MarginPaddingAlignmentSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#1)]
 [!code-xaml[MarginPaddingAlignmentSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#1)]  
  
 在许多情况下，不适合使用统一边距。 对于这些情况，可应用非统一间距。 下面的示例演示如何将非统一边距间距应用于子元素。 按此顺序描述边距：左端、顶端、右端和底端。  
  
 [!code-cpp[MarginPaddingAlignmentSample#2](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#2)]
 [!code-csharp[MarginPaddingAlignmentSample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#2)]
 [!code-vb[MarginPaddingAlignmentSample#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#2)]
 [!code-xaml[MarginPaddingAlignmentSample#2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#2)]  
  
<a name="wcpsdk_layout_amp_padding_properties"></a>   
## <a name="understanding-the-padding-property"></a>了解 Padding 属性  
 填充状态是类似于<xref:System.Windows.FrameworkElement.Margin%2A>在大多数方面。 Padding 属性上仅上公开了一些类，主要是作为一种便于使用： <xref:System.Windows.Documents.Block>， <xref:System.Windows.Controls.Border>， <xref:System.Windows.Controls.Control>，和<xref:System.Windows.Controls.TextBlock>是公开一个填充的属性的类的示例。 <xref:System.Windows.Controls.Border.Padding%2A>属性放大由指定的子元素的有效大小<xref:System.Windows.Thickness>值。  
  
 下面的示例演示如何将应用<xref:System.Windows.Controls.Border.Padding%2A>给父<xref:System.Windows.Controls.Border>元素。  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xaml[MarginPaddingAlignmentSample#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>   
## <a name="using-alignment-margins-and-padding-in-an-application"></a>在应用程序中使用 Alignment、Margins 和 Padding  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A><xref:System.Windows.FrameworkElement.Margin%2A>， <xref:System.Windows.Controls.Border.Padding%2A>，和<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>提供创建复杂的所需的定位控制[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]。 可利用每个属性的作用来更改子元素定位，以便能够灵活地创建动态应用程序和用户体验。  
  
 下面的示例演示本主题中详述的各个概念。 在本主题中的第一个示例中找到的基础结构上生成，此示例将添加<xref:System.Windows.Controls.Grid>元素的子级作为<xref:System.Windows.Controls.Border>中第一个示例。 <xref:System.Windows.Controls.Border.Padding%2A>应用于父<xref:System.Windows.Controls.Border>元素。 <xref:System.Windows.Controls.Grid>用于分区三个子之间的空间<xref:System.Windows.Controls.StackPanel>元素。 <xref:System.Windows.Controls.Button>再次使用元素显示的各种效果<xref:System.Windows.FrameworkElement.Margin%2A>和<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>。 <xref:System.Windows.Controls.TextBlock>元素添加到每个<xref:System.Windows.Controls.ColumnDefinition>更好地定义应用于的各种属性<xref:System.Windows.Controls.Button>每列中的元素。  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xaml[MarginPaddingAlignmentSample#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 编译后，前面的应用程序生成类似于下图的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 不同的属性值的效果元素之间的间距中并且每个列中的元素的重要属性值内显示<xref:System.Windows.Controls.TextBlock>元素。  
  
 ![一个应用程序中的多个定位属性](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-aligment-graphic3.PNG "layout_margins_padding_aligment_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>   
## <a name="whats-next"></a>下一步  
 定义的定位属性<xref:System.Windows.FrameworkElement>类可以精确地控制中的元素放置[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序。 至此你已了解多种方法，可使用这些方法更好地通过 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 来定位元素。  
  
 我们还提供了一些附加资源，这些资源更详细地介绍 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 布局。 [面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)主题包含更详细地介绍各种<xref:System.Windows.Controls.Panel>元素。 主题[演练： 我第一个 WPF 桌面应用程序](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)引入了使用布局元素来定位组件并将其操作绑定到数据源的高级的技术。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>  
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>  
 <xref:System.Windows.FrameworkElement.Margin%2A>  
 [面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [布局](../../../../docs/framework/wpf/advanced/layout.md)  
 [WPF 布局库示例](http://go.microsoft.com/fwlink/?LinkID=160054)
