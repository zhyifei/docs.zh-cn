---
title: Alignment、Margin 和 Padding 概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- margins [WPF]
- padding [WPF]
- aligning [WPF]
ms.assetid: 9c6a2009-9b86-4e40-8605-0a2664dc3973
ms.openlocfilehash: bf351b6df972dc992f214ddfe899bfa808d0cd53
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963639"
---
# <a name="alignment-margins-and-padding-overview"></a>Alignment、Margin 和 Padding 概述
<xref:System.Windows.FrameworkElement>类公开几个用于精确定位子元素的属性。 本主题讨论四个最重要的属性: <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>、 <xref:System.Windows.FrameworkElement.Margin%2A>、 <xref:System.Windows.Controls.Border.Padding%2A>和<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>。 了解这些属性的作用非常重要，因为这些属性是控制元素在 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 应用程序中的位置的基础。  

<a name="wcpsdk_layout_amp_introduction"></a>   
## <a name="introduction-to-element-positioning"></a>元素定位简介  
 可使用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 通过多种方式来定位元素。 但是, 即使只是选择正确<xref:System.Windows.Controls.Panel>的元素, 也不会获得理想的布局。 对定位进行精细控制<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>需要了解<xref:System.Windows.Controls.Border.Padding%2A>、 <xref:System.Windows.FrameworkElement.Margin%2A>、和<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性。  
  
 下图显示了一个采用若干定位属性的布局方案。  
  
 ![WPF 定位属性示例](./media/layout-margins-padding-alignment-graphic1.PNG "layout_margins_padding_alignment_graphic1")  
  
 乍一看, 此<xref:System.Windows.Controls.Button>图中的元素可能显示为随机放置。 但是，其位置实际上是通过使用边距、对齐和填充加以精确控制的。  
  
 下面的示例描述如何创建上图中的布局。 元素封装父<xref:System.Windows.Controls.StackPanel>, 其<xref:System.Windows.Controls.Border.Padding%2A>值为15个与设备无关的像素。 <xref:System.Windows.Controls.Border> 此帐户用于环绕子项<xref:System.Windows.Media.Brushes.LightBlue%2A> <xref:System.Windows.Controls.StackPanel>的窄带区。 的子元素<xref:System.Windows.Controls.StackPanel>用于演示本主题中详细介绍的各个定位属性。 三<xref:System.Windows.Controls.Button>个元素用于演示<xref:System.Windows.FrameworkElement.Margin%2A>和<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性。  
  
 [!code-csharp[MPALayoutSampleIntro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 通过下图可以仔细查看上例中使用的各个定位属性。 本主题的后面各节更详细地介绍了如何使用各个定位属性。  
  
 ![具有屏幕标注的定位属性](./media/layout-margins-padding-alignment-graphic2.PNG "layout_margins_padding_alignment_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>   
## <a name="understanding-alignment-properties"></a>了解 Alignment 属性  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 和<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性描述应如何将子元素定位到父元素的已分配布局空间内。 结合使用这些属性可精确定位子元素。 例如, <xref:System.Windows.Controls.DockPanel>的子元素可以指定四个不同的水平对齐方式: <xref:System.Windows.HorizontalAlignment.Right> <xref:System.Windows.HorizontalAlignment.Left>、、 <xref:System.Windows.HorizontalAlignment.Center>或, 或<xref:System.Windows.HorizontalAlignment.Stretch>以填充可用空间。 类似的值可用于垂直定位。  
  
> [!NOTE]
> 元素的显式<xref:System.Windows.FrameworkElement.Height%2A>设置<xref:System.Windows.FrameworkElement.Width%2A>和属性优先于属性值。<xref:System.Windows.HorizontalAlignment.Stretch> 如果尝试将<xref:System.Windows.FrameworkElement.Height%2A>、 <xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>的值`Stretch`设置为, 则`Stretch`会忽略请求中的结果。  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>   
### <a name="horizontalalignment-property"></a>HorizontalAlignment 属性  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性声明要应用于子元素的水平对齐特征。 下表显示了<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性的每个可能值。  
  
|成员|描述|  
|------------|-----------------|  
|<xref:System.Windows.HorizontalAlignment.Left>|子元素与父元素的已分配布局空间的左端对齐。|  
|<xref:System.Windows.HorizontalAlignment.Center>|子元素与父元素的已分配布局空间的中心对齐。|  
|<xref:System.Windows.HorizontalAlignment.Right>|子元素与父元素的已分配布局空间的右端对齐。|  
|<xref:System.Windows.HorizontalAlignment.Stretch>缺省值|拉伸子元素以填充父元素的已分配布局空间。 显式<xref:System.Windows.FrameworkElement.Width%2A> 和<xref:System.Windows.FrameworkElement.Height%2A>值优先。|  
  
 下面的示例演示如何将<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性应用到<xref:System.Windows.Controls.Button>元素。 显示每个特性值，以便更好地阐释各种呈现行为。  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 以上代码将产生与下图类似的布局。 图中显示每个<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>值的定位效果。  
  
 ![HorizontalAlignment 示例](./media/layout-horizontal-alignment-graphic.PNG "layout_horizontal_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>   
### <a name="verticalalignment-property"></a>VerticalAlignment 属性  
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性描述要应用于子元素的垂直对齐特征。 下表显示了<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性的每个可能值。  
  
|成员|描述|  
|------------|-----------------|  
|<xref:System.Windows.VerticalAlignment.Top>|子元素与父元素的已分配布局空间的顶端对齐。|  
|<xref:System.Windows.VerticalAlignment.Center>|子元素与父元素的已分配布局空间的中心对齐。|  
|<xref:System.Windows.VerticalAlignment.Bottom>|子元素与父元素的已分配布局空间的底端对齐。|  
|<xref:System.Windows.VerticalAlignment.Stretch>缺省值|拉伸子元素以填充父元素的已分配布局空间。 显式<xref:System.Windows.FrameworkElement.Width%2A> 和<xref:System.Windows.FrameworkElement.Height%2A>值优先。|  
  
 下面的示例演示如何将<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性应用到<xref:System.Windows.Controls.Button>元素。 显示每个特性值，以便更好地阐释各种呈现行为。 出于本示例的目的, <xref:System.Windows.Controls.Grid>具有可视网格线的元素用作父级, 以更好地说明每个属性值的布局行为。  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xaml[MPALayoutVerticalAlignment#2](~/samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 以上代码将产生与下图类似的布局。 图中显示每个<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>值的定位效果。  
  
 ![VerticalAlignment 属性示例](./media/layout-vertical-alignment-graphic.PNG "layout_vertical_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>   
## <a name="understanding-margin-properties"></a>了解 Margin 属性  
 <xref:System.Windows.FrameworkElement.Margin%2A>属性描述元素及其子元素和同级之间的距离。 <xref:System.Windows.FrameworkElement.Margin%2A>通过使用类似`Margin="20"`的语法, 值可以是统一的。 使用此语法时, 将<xref:System.Windows.FrameworkElement.Margin%2A>对元素应用20个与设备无关的统一像素。 <xref:System.Windows.FrameworkElement.Margin%2A>值还可以采用四个非重复值的形式, 每个值描述要应用于左侧、顶部、右侧和底部 (按顺序) 的不同边距, 如`Margin="0,10,5,25"`。 正确使用<xref:System.Windows.FrameworkElement.Margin%2A>属性可以非常精确地控制元素的呈现位置以及其邻居元素和子元素的呈现位置。  
  
> [!NOTE]
> 非零边距将应用于元素的<xref:System.Windows.FrameworkElement.ActualWidth%2A>和<xref:System.Windows.FrameworkElement.ActualHeight%2A>之外的空间。  
  
 下面的示例演示如何在一组<xref:System.Windows.Controls.Button>元素周围应用统一的边距。 <xref:System.Windows.Controls.Button>元素在每个方向上均匀地分布在十个像素的边距缓冲区中。  
  
 [!code-cpp[MarginPaddingAlignmentSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#1)]
 [!code-csharp[MarginPaddingAlignmentSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#1)]
 [!code-vb[MarginPaddingAlignmentSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#1)]
 [!code-xaml[MarginPaddingAlignmentSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#1)]  
  
 在许多情况下，不适合使用统一边距。 对于这些情况，可应用非统一间距。 下面的示例演示如何将非统一边距间距应用于子元素。 按此顺序描述边距：左端、顶端、右端和底端。  
  
 [!code-cpp[MarginPaddingAlignmentSample#2](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#2)]
 [!code-csharp[MarginPaddingAlignmentSample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#2)]
 [!code-vb[MarginPaddingAlignmentSample#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#2)]
 [!code-xaml[MarginPaddingAlignmentSample#2](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#2)]  
  
<a name="wcpsdk_layout_amp_padding_properties"></a>   
## <a name="understanding-the-padding-property"></a>了解 Padding 属性  
 填充<xref:System.Windows.FrameworkElement.Margin%2A>在大多数方面类似于。 仅在几个类上公开填充属性, 这主要是为了方便<xref:System.Windows.Documents.Block>:、 <xref:System.Windows.Controls.Border>、 <xref:System.Windows.Controls.Control>和<xref:System.Windows.Controls.TextBlock>是公开空白属性的类的示例。 属性按指定<xref:System.Windows.Thickness>的值增大子元素的有效大小。 <xref:System.Windows.Controls.Border.Padding%2A>  
  
 下面的示例演示如何将应用<xref:System.Windows.Controls.Border.Padding%2A>于父<xref:System.Windows.Controls.Border>元素。  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xaml[MarginPaddingAlignmentSample#3](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>   
## <a name="using-alignment-margins-and-padding-in-an-application"></a>在应用程序中使用 Alignment、Margins 和 Padding  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>、、和提供<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>创建复杂[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]的所需的定位控件。 <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.Border.Padding%2A> 可利用每个属性的作用来更改子元素定位，以便能够灵活地创建动态应用程序和用户体验。  
  
 下面的示例演示本主题中详述的各个概念。 此示例在本主题的第一个示例中的基础结构上构建, 此<xref:System.Windows.Controls.Grid>示例将一个元素添加为<xref:System.Windows.Controls.Border>第一个示例中的的子元素。 <xref:System.Windows.Controls.Border.Padding%2A>应用于父<xref:System.Windows.Controls.Border>元素。 用于在三个子<xref:System.Windows.Controls.StackPanel>元素之间对空间进行分区。 <xref:System.Windows.Controls.Grid> <xref:System.Windows.Controls.Button>再次使用元素显示<xref:System.Windows.FrameworkElement.Margin%2A>和<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>的各种效果。 <xref:System.Windows.Controls.TextBlock>向每个<xref:System.Windows.Controls.ColumnDefinition>元素添加元素可更好地定义应用于每<xref:System.Windows.Controls.Button>个列中的元素的各种属性。  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xaml[MarginPaddingAlignmentSample#4](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 编译后，前面的应用程序生成类似于下图的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 各种属性值的效果在元素间的间距中很明显, 每个列中的元素的重要属性值显示<xref:System.Windows.Controls.TextBlock>在元素中。  
  
 ![一个应用程序中的多个定位属性](./media/layout-margins-padding-aligment-graphic3.PNG "layout_margins_padding_aligment_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>   
## <a name="whats-next"></a>下一步  
 通过定位<xref:System.Windows.FrameworkElement>类定义的属性, 可以在应用程序中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]对元素位置进行精细控制。 至此你已了解多种方法，可使用这些方法更好地通过 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 来定位元素。  
  
 我们还提供了一些附加资源，这些资源更详细地介绍 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 布局。 [面板概述](../controls/panels-overview.md)主题包含有关各种<xref:System.Windows.Controls.Panel>元素的更多详细信息。 主题[演练:我的第一个 WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)桌面应用程序引入了使用布局元素定位组件并将其操作绑定到数据源的高级方法。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- <xref:System.Windows.FrameworkElement.Margin%2A>
- [面板概述](../controls/panels-overview.md)
- [布局](layout.md)
- [WPF 布局库示例](https://go.microsoft.com/fwlink/?LinkID=160054)
