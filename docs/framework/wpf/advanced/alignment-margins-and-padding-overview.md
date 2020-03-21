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
ms.openlocfilehash: bec2d9cd224febb650e2de67bb7406365d075963
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145470"
---
# <a name="alignment-margins-and-padding-overview"></a>Alignment、Margin 和 Padding 概述
类<xref:System.Windows.FrameworkElement>公开几个用于精确定位子元素的属性。 本主题<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>讨论四个最重要的属性： 、<xref:System.Windows.FrameworkElement.Margin%2A><xref:System.Windows.Controls.Border.Padding%2A>和<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>。 了解这些属性的作用非常重要，因为这些属性是控制元素在 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 应用程序中的位置的基础。  

<a name="wcpsdk_layout_amp_introduction"></a>
## <a name="introduction-to-element-positioning"></a>元素定位简介  
 可使用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 通过多种方式来定位元素。 但是，实现理想的布局不仅仅是简单地选择正确的<xref:System.Windows.Controls.Panel>元素。 精细地控制定位需要了解<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>、<xref:System.Windows.FrameworkElement.Margin%2A><xref:System.Windows.Controls.Border.Padding%2A>和<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性。  
  
 下图显示了一个采用若干定位属性的布局方案。  
  
 ![WPF 定位属性示例](./media/layout-margins-padding-alignment-graphic1.PNG "layout_margins_padding_alignment_graphic1")  
  
 乍一看，<xref:System.Windows.Controls.Button>此图中的元素可能看起来是随机放置的。 但是，其位置实际上是通过使用边距、对齐和填充加以精确控制的。  
  
 下面的示例描述如何创建上图中的布局。 元素<xref:System.Windows.Controls.Border>封装父<xref:System.Windows.Controls.StackPanel>级 ，<xref:System.Windows.Controls.Border.Padding%2A>值为 15 个与设备无关的像素。 这说明了围绕孩子<xref:System.Windows.Media.Brushes.LightBlue%2A><xref:System.Windows.Controls.StackPanel>周围的狭窄带。 子<xref:System.Windows.Controls.StackPanel>元素用于说明本主题中详述的每个定位属性。 三<xref:System.Windows.Controls.Button>个元素用于演示 和<xref:System.Windows.FrameworkElement.Margin%2A><xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性。  
  
 [!code-csharp[MPALayoutSampleIntro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 通过下图可以仔细查看上例中使用的各个定位属性。 本主题的后面各节更详细地介绍了如何使用各个定位属性。  
  
 ![使用屏幕呼叫&#45;外定位属性](./media/layout-margins-padding-alignment-graphic2.PNG "layout_margins_padding_alignment_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>
## <a name="understanding-alignment-properties"></a>了解 Alignment 属性  
 和<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A><xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性描述子元素应如何定位到父元素分配的布局空间中。 结合使用这些属性可精确定位子元素。 例如，<xref:System.Windows.Controls.DockPanel>子元素可以指定四种不同的水平对齐：、<xref:System.Windows.HorizontalAlignment.Left><xref:System.Windows.HorizontalAlignment.Right>或<xref:System.Windows.HorizontalAlignment.Center>，或以<xref:System.Windows.HorizontalAlignment.Stretch>填充可用空间。 类似的值可用于垂直定位。  
  
> [!NOTE]
> 元素上的显式设置<xref:System.Windows.FrameworkElement.Height%2A>和<xref:System.Windows.FrameworkElement.Width%2A>属性优先于<xref:System.Windows.HorizontalAlignment.Stretch>属性值。 <xref:System.Windows.FrameworkElement.Height%2A>尝试设置<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>的值`Stretch`会导致`Stretch`请求被忽略。  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>
### <a name="horizontalalignment-property"></a>HorizontalAlignment 属性  
 属性<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>声明要应用于子元素的水平对齐特征。 下表显示了<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>该属性的每个可能值。  
  
|成员|说明|  
|------------|-----------------|  
|<xref:System.Windows.HorizontalAlignment.Left>|子元素与父元素的已分配布局空间的左端对齐。|  
|<xref:System.Windows.HorizontalAlignment.Center>|子元素与父元素的已分配布局空间的中心对齐。|  
|<xref:System.Windows.HorizontalAlignment.Right>|子元素与父元素的已分配布局空间的右端对齐。|  
|<xref:System.Windows.HorizontalAlignment.Stretch>（默认值）|拉伸子元素以填充父元素的已分配布局空间。 显式<xref:System.Windows.FrameworkElement.Width%2A>值<xref:System.Windows.FrameworkElement.Height%2A>和值优先。|  
  
 下面的示例演示如何将<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性应用于<xref:System.Windows.Controls.Button>元素。 显示每个特性值，以便更好地阐释各种呈现行为。  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 以上代码将产生与下图类似的布局。 每个<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>值的定位效果在图中可见。  
  
 ![HorizontalAlignment 示例](./media/layout-horizontal-alignment-graphic.PNG "layout_horizontal_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>
### <a name="verticalalignment-property"></a>VerticalAlignment 属性  
 该<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性描述要应用于子元素的垂直对齐特征。 下表显示了<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>该属性的每个可能值。  
  
|成员|说明|  
|------------|-----------------|  
|<xref:System.Windows.VerticalAlignment.Top>|子元素与父元素的已分配布局空间的顶端对齐。|  
|<xref:System.Windows.VerticalAlignment.Center>|子元素与父元素的已分配布局空间的中心对齐。|  
|<xref:System.Windows.VerticalAlignment.Bottom>|子元素与父元素的已分配布局空间的底端对齐。|  
|<xref:System.Windows.VerticalAlignment.Stretch>（默认值）|拉伸子元素以填充父元素的已分配布局空间。 显式<xref:System.Windows.FrameworkElement.Width%2A>值<xref:System.Windows.FrameworkElement.Height%2A>和值优先。|  
  
 下面的示例演示如何将<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性应用于<xref:System.Windows.Controls.Button>元素。 显示每个特性值，以便更好地阐释各种呈现行为。 出于此示例的目的，<xref:System.Windows.Controls.Grid>使用具有可见网格线的元素作为父元素，以便更好地说明每个属性值的布局行为。  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xaml[MPALayoutVerticalAlignment#2](~/samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 以上代码将产生与下图类似的布局。 每个<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>值的定位效果在图中可见。  
  
 ![VerticalAlignment 属性示例](./media/layout-vertical-alignment-graphic.PNG "layout_vertical_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>
## <a name="understanding-margin-properties"></a>了解 Margin 属性  
 属性<xref:System.Windows.FrameworkElement.Margin%2A>描述元素与其子项或对等体之间的距离。 <xref:System.Windows.FrameworkElement.Margin%2A>通过使用 语法（如`Margin="20"`） 可以统一值。 使用此语法，将应用于元素<xref:System.Windows.FrameworkElement.Margin%2A>的 20 个独立于设备的像素的统一。 <xref:System.Windows.FrameworkElement.Margin%2A>值还可以采用四个不同的值的形式，每个值描述一个不同的边距以应用于左侧、顶部、右侧和底部（按该顺序），如`Margin="0,10,5,25"`。 正确使用 该<xref:System.Windows.FrameworkElement.Margin%2A>属性可以非常精细地控制元素的呈现位置及其相邻元素和子元素的渲染位置。  
  
> [!NOTE]
> 非零边距应用元素<xref:System.Windows.FrameworkElement.ActualWidth%2A>和<xref:System.Windows.FrameworkElement.ActualHeight%2A>以外的空间。  
  
 下面的示例演示如何在一组<xref:System.Windows.Controls.Button>元素周围应用统一边距。 元素<xref:System.Windows.Controls.Button>以每个方向上的 10 像素边距缓冲区均匀间隔。  
  
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
 填充在大多数方面都类似<xref:System.Windows.FrameworkElement.Margin%2A>。 Padding<xref:System.Windows.Documents.Block>属性仅在几个类上公开，这主要为方便： 、<xref:System.Windows.Controls.Border><xref:System.Windows.Controls.Control>和<xref:System.Windows.Controls.TextBlock>是公开填充属性的类的示例。 属性<xref:System.Windows.Controls.Border.Padding%2A>按指定<xref:System.Windows.Thickness>值放大子元素的有效大小。  
  
 下面的示例演示如何应用于<xref:System.Windows.Controls.Border.Padding%2A>父<xref:System.Windows.Controls.Border>元素。  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xaml[MarginPaddingAlignmentSample#3](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>
## <a name="using-alignment-margins-and-padding-in-an-application"></a>在应用程序中使用 Alignment、Margins 和 Padding  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>，<xref:System.Windows.FrameworkElement.Margin%2A><xref:System.Windows.Controls.Border.Padding%2A>并提供<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>创建复杂[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]复杂所需的定位控制。 可利用每个属性的作用来更改子元素定位，以便能够灵活地创建动态应用程序和用户体验。  
  
 下面的示例演示本主题中详述的各个概念。 在本主题中的第一个示例中找到的基础结构的基础上，本示例将元素添加<xref:System.Windows.Controls.Grid>为第一个示例中的<xref:System.Windows.Controls.Border>子元素。 <xref:System.Windows.Controls.Border.Padding%2A>应用于父<xref:System.Windows.Controls.Border>元素。 <xref:System.Windows.Controls.Grid>用于在三个子<xref:System.Windows.Controls.StackPanel>元素之间划分空间。 <xref:System.Windows.Controls.Button>元素再次用于显示<xref:System.Windows.FrameworkElement.Margin%2A>和<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>的各种效果。 <xref:System.Windows.Controls.TextBlock>元素将添加到每个<xref:System.Windows.Controls.ColumnDefinition>元素中，以便更好地定义应用于每列中<xref:System.Windows.Controls.Button>元素的各种属性。  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xaml[MarginPaddingAlignmentSample#4](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 编译后，前面的应用程序生成类似于下图的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 各种属性值的效果在元素之间的间距中很明显，并且每个列中元素的重要属性值显示在元素中<xref:System.Windows.Controls.TextBlock>。  
  
 ![一个应用程序中的几个定位属性](./media/layout-margins-padding-aligment-graphic3.PNG "layout_margins_padding_aligment_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>
## <a name="whats-next"></a>后续步骤  
 <xref:System.Windows.FrameworkElement>类定义的定位属性可精细控制[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序中的元素放置。 至此你已了解多种方法，可使用这些方法更好地通过 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 来定位元素。  
  
 我们还提供了一些附加资源，这些资源更详细地介绍 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 布局。 "[面板概述](../controls/panels-overview.md)"主题包含有关各种<xref:System.Windows.Controls.Panel>元素的更多详细信息。 主题[演练：我的第一个 WPF 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)引入了使用布局元素定位组件并将其操作绑定到数据源的高级技术。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- <xref:System.Windows.FrameworkElement.Margin%2A>
- [面板概述](../controls/panels-overview.md)
- [布局](layout.md)
- [WPF 布局库示例](https://go.microsoft.com/fwlink/?LinkID=160054)
