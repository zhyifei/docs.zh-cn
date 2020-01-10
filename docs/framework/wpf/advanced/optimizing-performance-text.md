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
ms.openlocfilehash: 3e729458538353499f27f95ea2ca37fea1335238
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740352"
---
# <a name="optimizing-performance-text"></a>优化性能：文本

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 支持通过使用功能丰富的 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 控件实现的文本内容演示。 通常可以将文本呈现分为三层：

1. 直接使用 <xref:System.Windows.Documents.Glyphs> 和 <xref:System.Windows.Media.GlyphRun> 对象。

2. 使用 <xref:System.Windows.Media.FormattedText> 对象。

3. 使用高级控件，如 <xref:System.Windows.Controls.TextBlock> 和 <xref:System.Windows.Documents.FlowDocument> 对象。

本主题提供文本呈现性能方面的建议。

<a name="Glyph_Level"></a>

## <a name="rendering-text-at-the-glyph-level"></a>字形级别的呈现文本

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供高级文本支持，包括可直接访问 <xref:System.Windows.Documents.Glyphs> 的字形级标记，适用于想要在设置格式后截获和保存文本的客户。 这些功能为以下每种方案中不同的文本呈现要求提供关键支持。

- 固定格式文档的屏幕显示。

- 打印方案。

  - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 作为设备打印机语言。

  - Microsoft XPS 文档编写器。

  - 以前的打印机驱动程序，从 Win32 应用程序输出为固定格式。

  - 打印后台处理格式。

- 固定格式的文档表示形式，包括以前版本的 Windows 和其他计算设备的客户端。

> [!NOTE]
> <xref:System.Windows.Documents.Glyphs> 和 <xref:System.Windows.Media.GlyphRun> 专为固定格式的文档演示和打印方案而设计。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 为常规布局和 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 方案（如 <xref:System.Windows.Controls.Label> 和 <xref:System.Windows.Controls.TextBlock>）提供了多个元素。 有关布局和 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 方案的详细信息，请参阅 [WPF 中的版式](typography-in-wpf.md)。

下面的示例演示如何为 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中的 <xref:System.Windows.Documents.Glyphs> 对象定义属性。 <xref:System.Windows.Documents.Glyphs> 对象表示 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中 <xref:System.Windows.Media.GlyphRun> 的输出。 示例假定本地计算机上的 **C:\WINDOWS\Fonts** 文件夹中安装了 Arial、Courier New 和 Times New Roman 字体。

[!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]

### <a name="using-drawglyphrun"></a>使用 DrawGlyphRun

如果你具有自定义控件并且要呈现标志符号，请使用 <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A> 方法。

通过使用 <xref:System.Windows.Media.FormattedText> 对象，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 还为自定义文本格式提供了较低级别的服务。 在 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中呈现文本的最有效方法是在字形级别使用 <xref:System.Windows.Documents.Glyphs> 和 <xref:System.Windows.Media.GlyphRun>生成文本内容。 但是，这种效率的代价是，使用丰富文本格式却会丢失，这是 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 控件的内置功能，例如 <xref:System.Windows.Controls.TextBlock> 和 <xref:System.Windows.Documents.FlowDocument>。

<a name="FormattedText_Object"></a>

## <a name="formattedtext-object"></a>FormattedText 对象

<xref:System.Windows.Media.FormattedText> 对象允许您绘制多行文本，在这种情况下，文本中的每个字符都可以单独设置格式。 有关详细信息，请参阅[绘制格式化文本](drawing-formatted-text.md)。

若要创建格式化文本，请调用 <xref:System.Windows.Media.FormattedText.%23ctor%2A> 构造函数以创建 <xref:System.Windows.Media.FormattedText> 对象。 创建初始格式化文本字符串后，便可应用某一范围的格式样式。 如果你的应用程序想要实现其自己的布局，则 <xref:System.Windows.Media.FormattedText> 对象比使用控件（如 <xref:System.Windows.Controls.TextBlock>）更好。 有关 <xref:System.Windows.Media.FormattedText> 对象的详细信息，请参阅[绘制格式化文本](drawing-formatted-text.md)。

<xref:System.Windows.Media.FormattedText> 对象提供低级别文本格式设置功能。 可向一个或多个字符应用多种格式样式。 例如，可以调用 <xref:System.Windows.Media.FormattedText.SetFontSize%2A> 和 <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> 方法来更改文本中前五个字符的格式设置。

下面的代码示例创建一个 <xref:System.Windows.Media.FormattedText> 对象并呈现该对象。

[!code-csharp[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
[!code-vb[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]

<a name="FlowDocument_TextBlock_Label"></a>

## <a name="flowdocument-textblock-and-label-controls"></a>FlowDocument、TextBlock 和 Label 控件

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 包括多个用于在屏幕中绘制文本的控件。 每个控件都面向不同的方案，并具有自己的功能和限制列表。

### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>FlowDocument 对性能的影响比 TextBlock 或 Label 大

通常情况下，当需要有限的文本支持时，应使用 <xref:System.Windows.Controls.TextBlock> 元素，例如 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]中的 brief 句子。 需要最少文本支持时，可以使用 <xref:System.Windows.Controls.Label>。 <xref:System.Windows.Documents.FlowDocument> 元素是一个容器，用于 flowable 支持丰富的内容呈现的文档，因此，与使用 <xref:System.Windows.Controls.TextBlock> 或 <xref:System.Windows.Controls.Label> 控件相比，性能影响更大。

有关 <xref:System.Windows.Documents.FlowDocument>的详细信息，请参阅[流文档概述](flow-document-overview.md)。

### <a name="avoid-using-textblock-in-flowdocument"></a>避免在 FlowDocument 中使用 TextBlock

<xref:System.Windows.Controls.TextBlock> 元素是从 <xref:System.Windows.UIElement>派生的。 <xref:System.Windows.Documents.Run> 元素派生自 <xref:System.Windows.Documents.TextElement>，它比 <xref:System.Windows.UIElement>派生的对象使用的成本更低。 如果可能，请使用 <xref:System.Windows.Documents.Run> 而不是 <xref:System.Windows.Controls.TextBlock> 在 <xref:System.Windows.Documents.FlowDocument>中显示文本内容。

以下标记示例演示了在 <xref:System.Windows.Documents.FlowDocument>中设置文本内容的两种方式：

[!code-xaml[Performance#PerformanceSnippet13](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]

### <a name="avoid-using-run-to-set-text-properties"></a>避免使用 Run 来设置文本属性

通常，在 <xref:System.Windows.Controls.TextBlock> 中使用 <xref:System.Windows.Documents.Run> 比根本不使用显式 <xref:System.Windows.Documents.Run> 对象的性能更高。 如果使用 <xref:System.Windows.Documents.Run> 来设置文本属性，请改为直接在 <xref:System.Windows.Controls.TextBlock> 上设置这些属性。

以下标记示例演示了这两种设置文本属性的方法，在本例中为 <xref:System.Windows.Controls.TextBlock.FontWeight%2A> 属性：

[!code-xaml[Performance#PerformanceSnippet12](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]

下表显示了使用和不使用显式 <xref:System.Windows.Documents.Run>显示 1000 <xref:System.Windows.Controls.TextBlock> 对象的费用。

|**TextBlock 类型**|**创建时间 (ms)**|**呈现时间 (ms)**|
|------------------------|------------------------------|----------------------------|
|运行设置文本属性|146|540|
|TextBlock 设置文本属性|43|453|

### <a name="avoid-databinding-to-the-labelcontent-property"></a>避免对 Label.Content 属性进行数据绑定

假设有一个方案，其中有一个从 <xref:System.String> 源中频繁更新的 <xref:System.Windows.Controls.Label> 对象。 数据将 <xref:System.Windows.Controls.Label> 元素的 <xref:System.Windows.Controls.ContentControl.Content%2A> 属性绑定到 <xref:System.String> 源对象时，可能会遇到性能不佳的情况。 每当更新源 <xref:System.String> 时，旧的 <xref:System.String> 对象将被丢弃，并重新创建新的 <xref:System.String>，因为 <xref:System.String> 对象是不可变的，因此不能对其进行修改。 这进而导致 <xref:System.Windows.Controls.Label> 对象的 <xref:System.Windows.Controls.ContentPresenter> 放弃其旧内容并重新生成新内容以显示新的 <xref:System.String>。

此问题的解决方法很简单。 如果 <xref:System.Windows.Controls.Label> 未设置为自定义 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 值，则将 <xref:System.Windows.Controls.Label> 替换为 <xref:System.Windows.Controls.TextBlock>，并将其 <xref:System.Windows.Controls.TextBlock.Text%2A> 属性绑定到源字符串。

|**数据绑定属性**|**更新时间 (ms)**|
|-----------------------------|----------------------------|
|Label.Content|835|
|TextBlock.Text|242|

<a name="Hyperlink"></a>

## <a name="hyperlink"></a>超链接

<xref:System.Windows.Documents.Hyperlink> 对象是一个内联级别的流内容元素，它允许在流内容中承载超链接。

### <a name="combine-hyperlinks-in-one-textblock-object"></a>在一个 TextBlock 对象中合并超链接

可以通过在同一 <xref:System.Windows.Controls.TextBlock>中将多个 <xref:System.Windows.Documents.Hyperlink> 元素组合在一起来优化其使用。 这有助于最小化在应用程序中创建的对象的数量。 例如，可显示多个超链接，如下所示：

MSN 主页 &#124; 我的 MSN

以下标记示例演示了用于显示超链接的多个 <xref:System.Windows.Controls.TextBlock> 元素：

[!code-xaml[Performance#PerformanceSnippet9](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]

以下标记示例演示了一种使用单个 <xref:System.Windows.Controls.TextBlock>显示超链接的更有效方法：

[!code-xaml[Performance#PerformanceSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]

### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>仅在 MouseEnter 事件的超链接中显示下划线

<xref:System.Windows.TextDecoration> 对象是可以添加到文本的视觉对象装饰;但是，若要进行实例化，性能可能会很高。 如果对 <xref:System.Windows.Documents.Hyperlink> 元素进行大量使用，请考虑仅在触发事件时显示下划线，如 <xref:System.Windows.ContentElement.MouseEnter> 事件。 有关详细信息，请参阅[指定是否为超链接添加下划线](how-to-specify-whether-a-hyperlink-is-underlined.md)。

下图显示了 MouseEnter 事件如何触发带下划线的超链接：

![显示 TextDecoration 的超链接](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)

以下标记示例显示了使用和不带下划线定义的 <xref:System.Windows.Documents.Hyperlink>：

[!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]

下表显示了使用和不带下划线显示 1000 <xref:System.Windows.Documents.Hyperlink> 元素的性能成本。

|**超链接**|**创建时间 (ms)**|**呈现时间 (ms)**|
|-------------------|------------------------------|----------------------------|
|使用下划线|289|1130|
|不使用下划线|299|776|

<a name="Text_Formatting_Features"></a>

## <a name="text-formatting-features"></a>文本格式设置功能

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供丰富的文本格式设置服务，如自动断字。 这些服务可能会影响应用程序性能，应仅在需要时使用。

### <a name="avoid-unnecessary-use-of-hyphenation"></a>避免不必要地使用断字

自动断字查找文本行的连字符断点，并允许 <xref:System.Windows.Controls.TextBlock> 和 <xref:System.Windows.Documents.FlowDocument> 对象中的直线的额外断点位置。 默认禁用这些对象中的自动断字功能。 通过将该对象的 IsHyphenationEnabled 属性设置为 `true`，可以启用此功能。 但是，启用此功能会导致 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 启动组件对象模型（COM）互操作性，这会影响应用程序性能。 除非需要，否则不建议使用自动断字功能。

### <a name="use-figures-carefully"></a>谨慎使用图形

<xref:System.Windows.Documents.Figure> 元素表示可以在内容页中完全定位的流内容的一部分。 在某些情况下，<xref:System.Windows.Documents.Figure> 可能会导致整个页面在其位置与已布局的内容冲突时自动重新设置格式。您可以通过将 <xref:System.Windows.Documents.Figure> 元素相互组合在一起来最大程度地减少不必要的重新格式化，或在固定页面大小的情况下将其声明到内容顶部附近。

### <a name="optimal-paragraph"></a>最佳段落

<xref:System.Windows.Documents.FlowDocument> 对象的最佳段落功能会将段落布局，以便尽可能均匀地分布空白。 默认禁用最佳段落功能。 可以通过将对象的 <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> 属性设置为 `true`来启用此功能。 但是，启用此功能会影响应用程序的性能。 除非需要，否则不建议使用最佳段落功能。

## <a name="see-also"></a>另请参阅

- [优化 WPF 应用程序性能](optimizing-wpf-application-performance.md)
- [规划应用程序性能](planning-for-application-performance.md)
- [利用硬件](optimizing-performance-taking-advantage-of-hardware.md)
- [布局和示例](optimizing-performance-layout-and-design.md)
- [2D 图形和图像处理](optimizing-performance-2d-graphics-and-imaging.md)
- [对象行为](optimizing-performance-object-behavior.md)
- [应用程序资源](optimizing-performance-application-resources.md)
- [数据绑定](optimizing-performance-data-binding.md)
- [其他性能建议](optimizing-performance-other-recommendations.md)
