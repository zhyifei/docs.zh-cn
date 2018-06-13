---
title: 优化性能：文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rendering text [WPF]
- hyperlinks [WPF]
- formatted text [WPF]
- text [WPF], performance
- glyphs [WPF]
ms.assetid: 66b1b9a7-8618-48db-b616-c57ea4327b98
ms.openlocfilehash: 177f42dfa1c1be2b12d7e9e5283cf57f14c0880c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548865"
---
# <a name="optimizing-performance-text"></a>优化性能：文本
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 支持通过使用功能丰富的 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 控件实现的文本内容演示。 通常可以将文本呈现分为三层：  
  
1.  使用<xref:System.Windows.Documents.Glyphs>和<xref:System.Windows.Media.GlyphRun>直接对象。  
  
2.  使用<xref:System.Windows.Media.FormattedText>对象。  
  
3.  使用高级控件，如<xref:System.Windows.Controls.TextBlock>和<xref:System.Windows.Documents.FlowDocument>对象。  
  
 本主题提供文本呈现性能方面的建议。  
  
  
<a name="Glyph_Level"></a>   
## <a name="rendering-text-at-the-glyph-level"></a>字形级别的呈现文本  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供高级的文本支持包括直接访问的标志符号级标记<xref:System.Windows.Documents.Glyphs>的用户想要截获并保存在格式化后的文本。 这些功能为以下每种方案中不同的文本呈现要求提供关键支持。  
  
-   固定格式文档的屏幕显示。  
  
-   打印方案。  
  
    -   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 作为设备打印机语言。  
  
    -   [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)]。  
  
    -   以前的打印机驱动程序，从 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 应用程序输出为固定格式。  
  
    -   打印后台处理格式。  
  
-   固定格式的文档演示，包括以前版本的 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 客户端和其他计算设备。  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Glyphs> 和<xref:System.Windows.Media.GlyphRun>旨在固定格式的文档演示文稿和打印方案。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 为常规布局提供了多个元素和[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]如方案<xref:System.Windows.Controls.Label>和<xref:System.Windows.Controls.TextBlock>。 有关布局和 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 方案的详细信息，请参阅 [WPF 中的版式](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)。  
  
 下面的示例演示如何定义属性<xref:System.Windows.Documents.Glyphs>对象在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。 <xref:System.Windows.Documents.Glyphs>对象表示的输出<xref:System.Windows.Media.GlyphRun>中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。 示例假定本地计算机上的 **C:\WINDOWS\Fonts** 文件夹中安装了 Arial、Courier New 和 Times New Roman 字体。  
  
 [!code-xaml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
### <a name="using-drawglyphrun"></a>使用 DrawGlyphRun  
 如果你必须自定义控件，你想要呈现标志符号，请使用<xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A>方法。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 此外提供了使用格式设置的自定义文本的较低级别服务<xref:System.Windows.Media.FormattedText>对象。 中的呈现文本的最高效方式[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]是通过生成标志符号级别使用的文本内容<xref:System.Windows.Documents.Glyphs>和<xref:System.Windows.Media.GlyphRun>。 但是，此效率的成本是易于使用丰富文本格式，这是内置的功能的损失的[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]控件，如<xref:System.Windows.Controls.TextBlock>和<xref:System.Windows.Documents.FlowDocument>。  
  
<a name="FormattedText_Object"></a>   
## <a name="formattedtext-object"></a>FormattedText 对象  
 <xref:System.Windows.Media.FormattedText>对象允许你绘制多行文本，在其中每个字符文本中的可以单独设置格式。 有关详细信息，请参阅[绘制格式化文本](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)。  
  
 若要创建带格式的文本，请调用<xref:System.Windows.Media.FormattedText.%23ctor%2A>构造函数来创建<xref:System.Windows.Media.FormattedText>对象。 创建初始格式化文本字符串后，便可应用某一范围的格式样式。 如果你的应用程序想要实现其自己的布局，则<xref:System.Windows.Media.FormattedText>对象是更好的选择比使用一个控件，如<xref:System.Windows.Controls.TextBlock>。 有关详细信息<xref:System.Windows.Media.FormattedText>对象，请参阅[绘制格式的文本](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)。  
  
 <xref:System.Windows.Media.FormattedText>对象提供低级别的文本格式设置功能。 可向一个或多个字符应用多种格式样式。 例如，您可以调用<xref:System.Windows.Media.FormattedText.SetFontSize%2A>和<xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A>方法来更改格式设置的文本中的前五个字符。  
  
 下面的代码示例创建<xref:System.Windows.Media.FormattedText>对象并将其呈现。  
  
 [!code-csharp[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
<a name="FlowDocument_TextBlock_Label"></a>   
## <a name="flowdocument-textblock-and-label-controls"></a>FlowDocument、TextBlock 和 Label 控件  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 包括多个用于在屏幕中绘制文本的控件。 每个控件都面向不同的方案，并具有自己的功能和限制列表。  
  
### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>FlowDocument 对性能的影响比 TextBlock 或 Label 大  
 一般情况下，<xref:System.Windows.Controls.TextBlock>有限的文本支持是必需的如中的简短句子时应使用元素[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]。 <xref:System.Windows.Controls.Label> 可在时极少的文字支持是必需的。 <xref:System.Windows.Documents.FlowDocument>元素是支持的内容，丰富演示文稿的可重流动文档的容器，因此，包括性能影响最大比使用<xref:System.Windows.Controls.TextBlock>或<xref:System.Windows.Controls.Label>控件。  
  
 有关详细信息<xref:System.Windows.Documents.FlowDocument>，请参阅[流文档概述](../../../../docs/framework/wpf/advanced/flow-document-overview.md)。  
  
### <a name="avoid-using-textblock-in-flowdocument"></a>避免在 FlowDocument 中使用 TextBlock  
 <xref:System.Windows.Controls.TextBlock>元素派生自<xref:System.Windows.UIElement>。 <xref:System.Windows.Documents.Run>元素派生自<xref:System.Windows.Documents.TextElement>，这是比使用成本较低<xref:System.Windows.UIElement>-派生对象。 如果可能，请使用<xref:System.Windows.Documents.Run>而非<xref:System.Windows.Controls.TextBlock>用于显示文本中的内容<xref:System.Windows.Documents.FlowDocument>。  
  
 以下的标记示例阐释了两种方法中设置文本内容<xref:System.Windows.Documents.FlowDocument>:  
  
 [!code-xaml[Performance#PerformanceSnippet13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]  
  
### <a name="avoid-using-run-to-set-text-properties"></a>避免使用 Run 来设置文本属性  
 一般情况下，使用<xref:System.Windows.Documents.Run>内<xref:System.Windows.Controls.TextBlock>是更好的性能比不使用显式密集型<xref:System.Windows.Documents.Run>根本对象。 如果你使用<xref:System.Windows.Documents.Run>才能设置文本属性，直接在上设置这些属性<xref:System.Windows.Controls.TextBlock>相反。  
  
 以下的标记示例阐释了这两种方式的 text 属性，在这种情况下，设置<xref:System.Windows.Controls.TextBlock.FontWeight%2A>属性：  
  
 [!code-xaml[Performance#PerformanceSnippet12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]  
  
 下表显示显示 1000 个的成本<xref:System.Windows.Controls.TextBlock>对象具有和没有显式<xref:System.Windows.Documents.Run>。  
  
|**TextBlock 类型**|**创建时间 (ms)**|**呈现时间 (ms)**|  
|------------------------|------------------------------|----------------------------|  
|运行设置文本属性|146|540|  
|TextBlock 设置文本属性|43|453|  
  
### <a name="avoid-databinding-to-the-labelcontent-property"></a>避免对 Label.Content 属性进行数据绑定  
 假设你有<xref:System.Windows.Controls.Label>从经常更新的对象<xref:System.String>源。 当数据绑定<xref:System.Windows.Controls.Label>元素的<xref:System.Windows.Controls.ContentControl.Content%2A>属性<xref:System.String>源对象，你可能会遇到性能不佳。 每次源<xref:System.String>更新时，旧<xref:System.String>对象是放弃，并且新<xref:System.String>重新创建-因为<xref:System.String>对象是不可变的不能修改它。 这反过来会导致<xref:System.Windows.Controls.ContentPresenter>的<xref:System.Windows.Controls.Label>对象以放弃其旧内容，并重新生成新的内容，以显示新<xref:System.String>。  
  
 此问题的解决方法很简单。 如果<xref:System.Windows.Controls.Label>未设置为自定义<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>值时，请替换<xref:System.Windows.Controls.Label>与<xref:System.Windows.Controls.TextBlock>和数据绑定其<xref:System.Windows.Controls.TextBlock.Text%2A>的源字符串的属性。  
  
|**数据绑定属性**|**更新时间 (ms)**|  
|-----------------------------|----------------------------|  
|Label.Content|835|  
|TextBlock.Text|242|  
  
<a name="Hyperlink"></a>   
## <a name="hyperlink"></a>超链接  
 <xref:System.Windows.Documents.Hyperlink>对象是允许你在流内容中承载超链接的内联级别流内容元素。  
  
### <a name="combine-hyperlinks-in-one-textblock-object"></a>在一个 TextBlock 对象中合并超链接  
 你可以优化使用多个<xref:System.Windows.Documents.Hyperlink>通过将它们组合在一起在同一元素<xref:System.Windows.Controls.TextBlock>。 这有助于最小化在应用程序中创建的对象的数量。 例如，可显示多个超链接，如下所示：  
  
 MSN 主页 &#124; 我的 MSN  
  
 下面的标记示例演示多个<xref:System.Windows.Controls.TextBlock>元素用于显示这些超链接：  
  
 [!code-xaml[Performance#PerformanceSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]  
  
 下面的标记示例演示更有效的方式显示的超链接，此时，使用单个<xref:System.Windows.Controls.TextBlock>:  
  
 [!code-xaml[Performance#PerformanceSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]  
  
### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>仅在 MouseEnter 事件的超链接中显示下划线  
 A<xref:System.Windows.TextDecoration>对象是你可以将其添加到文本的视觉装饰; 但是，可将其实例化大幅降低性能。 如果你进行大量使用<xref:System.Windows.Documents.Hyperlink>元素，请考虑仅当如触发事件时，才显示下划线<xref:System.Windows.ContentElement.MouseEnter>事件。 有关详细信息，请参阅[指定是否为超链接添加下划线](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)。  
  
 ![显示 Textdecoration 的超](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
MouseEnter 上显示的超链接  
  
 下面的标记示例演示<xref:System.Windows.Documents.Hyperlink>使用和未使用下划线定义：  
  
 [!code-xaml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 下表显示显示 1000 个的性能成本<xref:System.Windows.Documents.Hyperlink>元素与和未使用下划线。  
  
|**超链接**|**创建时间 (ms)**|**呈现时间 (ms)**|  
|-------------------|------------------------------|----------------------------|  
|使用下划线|289|1130|  
|不使用下划线|299|776|  
  
<a name="Text_Formatting_Features"></a>   
## <a name="text-formatting-features"></a>文本格式设置功能  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供丰富的文本格式设置服务，如自动断字。 这些服务可能会影响应用程序性能，应仅在需要时使用。  
  
### <a name="avoid-unnecessary-use-of-hyphenation"></a>避免不必要地使用断字  
 自动断字功能发现连字符断点行文本，并允许其他中断位置中的行<xref:System.Windows.Controls.TextBlock>和<xref:System.Windows.Documents.FlowDocument>对象。 默认禁用这些对象中的自动断字功能。 通过将该对象的 IsHyphenationEnabled 属性设置为 `true`，可以启用此功能。 但是，启用此功能会导致 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 启动 [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)] 互操作性，这可能会影响应用程序的性能。 除非需要，否则不建议使用自动断字功能。  
  
### <a name="use-figures-carefully"></a>谨慎使用图形  
 A<xref:System.Windows.Documents.Figure>元素表示可以是绝对定位的内容页中的流内容的一部分。 在某些情况下，<xref:System.Windows.Documents.Figure>可能会导致整个页面自动重新设置格式的如果其位置与内容已经过布局的冲突。可以通过组合在一起的不必要重新格式化的可能性降至<xref:System.Windows.Documents.Figure>旁边，或者将它们声明在固定的页大小方案中的内容的顶部附近的元素。  
  
### <a name="optimal-paragraph"></a>最佳段落  
 最佳段落功能<xref:System.Windows.Documents.FlowDocument>对象布局在段落，以便尽可能均匀地分发的空白区域。 默认禁用最佳段落功能。 你可以启用此功能，通过设置对象的<xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A>属性`true`。 但是，启用此功能会影响应用程序的性能。 除非需要，否则不建议使用最佳段落功能。  
  
## <a name="see-also"></a>请参阅  
 [优化 WPF 应用程序性能](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [规划应用程序性能](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [利用硬件](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [布局和示例](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [2D 图形和图像处理](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [对象行为](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [应用程序资源](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [数据绑定](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [其他性能建议](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
