---
title: 高级文本格式设置
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [WPF]
- text [WPF]
- typography [WPF], text formatting
ms.assetid: f0a7986e-f5b2-485c-a27d-f8e922022212
ms.openlocfilehash: 745d20e0bd4f877f9d4559f9fc7829b56689d35c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185938"
---
# <a name="advanced-text-formatting"></a>高级文本格式设置
Windows 演示基础 （WPF） 提供了一组强大的 API，用于在应用程序中包含文本。 布局和[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]API（如<xref:System.Windows.Controls.TextBlock>）为文本表示提供了最常用和最常用的元素。 绘图 API（如<xref:System.Windows.Media.GlyphRunDrawing>和<xref:System.Windows.Media.FormattedText>）提供了一种在图形中包含格式化文本的方法。 在最先进的级别上，WPF 提供了一个可扩展的文本格式引擎来控制文本表示的各个方面，如文本存储管理、文本运行格式管理和嵌入对象管理。  
  
 本主题介绍了 WPF 文本格式。 它侧重于客户端实现和使用 WPF 文本格式引擎。  
  
> [!NOTE]
> 本文档中的所有代码示例都可以在[高级文本格式示例](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI/TextFormatting)中找到。  

<a name="prereq"></a>
## <a name="prerequisites"></a>系统必备  
 本主题假定您熟悉用于文本表示的更高级别 API。 大多数用户方案不需要本主题中讨论的高级文本格式 API。 有关不同文本 API 的介绍，请参阅[WPF 中的文档](documents-in-wpf.md)。  
  
<a name="section1"></a>
## <a name="advanced-text-formatting"></a>高级文本格式设置  
 WPF 中[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]的文本布局和控件提供格式属性，允许您轻松地在应用程序中包含格式化文本。 这些控件会公开许多用于处理文本呈现（包括字样、大小和颜色）的属性。 一般情况下，这些控件可以处理应用程序中的大部分文本呈现。 但是，某些高级方案要求控制文本存储和文本呈现。 为此，WPF 提供了可扩展的文本格式引擎。  
  
 WPF 中的高级文本格式设置功能包括文本格式引擎、文本存储、文本运行和格式设置属性。 文本格式引擎 ，<xref:System.Windows.Media.TextFormatting.TextFormatter>创建要用于表示的文本行。 这是通过启动行格式设置过程并调用文本格式化的 来实现的<xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>。 文本 formatter 通过调用存储<xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>的方法检索文本存储运行的文本。 然后<xref:System.Windows.Media.TextFormatting.TextRun>，对象由文本物质<xref:System.Windows.Media.TextFormatting.TextLine>组成对象，并提供给应用程序进行检查或显示。  
  
<a name="section2"></a>
## <a name="using-the-text-formatter"></a>使用文本格式化程序  
 <xref:System.Windows.Media.TextFormatting.TextFormatter>是 WPF 文本格式设置引擎，并提供格式化和断开文本行的服务。 文本格式化程序可处理各种文本字符格式和段落样式，并提供对国际文本布局的支持。  
  
 与传统文本 API 不同，<xref:System.Windows.Media.TextFormatting.TextFormatter>通过一组回调方法与文本布局客户端进行交互。 它要求客户端在<xref:System.Windows.Media.TextFormatting.TextSource>类的实现中提供这些方法。 下图说明了客户端应用程序和<xref:System.Windows.Media.TextFormatting.TextFormatter>之间的文本布局交互。  
  
 ![文本布局客户端和 TextFormatter 示意图](./media/advanced-text-formatting/text-layout-textformatter-interaction.png)  
  
 文本格式化用于从文本存储检索格式化的文本行，文本存储是 的<xref:System.Windows.Media.TextFormatting.TextSource>实现。 这是首先使用 方法创建文本前物质的实例来实现的<xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A>。 此方法可创建一个文本格式化程序实例，并设置最大行高值和行宽值。 一旦创建了文本前物质的实例，行创建过程就会通过调用<xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>方法启动。 <xref:System.Windows.Media.TextFormatting.TextFormatter>调用回文本源以检索构成行的文本运行的文本和格式参数。  
  
 下例演示文本存储的格式设置过程。 该<xref:System.Windows.Media.TextFormatting.TextFormatter>对象用于从文本存储中检索文本行，然后格式化文本行以绘制到 中<xref:System.Windows.Media.DrawingContext>。  
  
 [!code-csharp[TextFormatterExample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>
## <a name="implementing-the-client-text-store"></a>实现客户端文本存储  
 扩展文本格式引擎时，需要实现和管理文本存储的各个方面。 该任务不是无关紧要的。 文本存储负责跟踪文本运行属性、段落属性、嵌入对象和其他类似内容。 它还为文本前物质用于创建<xref:System.Windows.Media.TextFormatting.TextRun><xref:System.Windows.Media.TextFormatting.TextLine>对象的单个对象提供文本前身。  
  
 要处理文本存储的虚拟化，文本存储必须派生自<xref:System.Windows.Media.TextFormatting.TextSource>。 <xref:System.Windows.Media.TextFormatting.TextSource>定义文本前物质用于检索文本存储中运行的文本的方法。 <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>是文本格式化用于检索行格式中使用的文本运行的方法。 调用<xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>由文本事件重复进行，直到出现以下情况之一：  
  
- 返回<xref:System.Windows.Media.TextFormatting.TextEndOfLine>a 或子类。  
  
- 文本运行的累积宽度超过调用中指定的最大行宽，以创建文本 formatter 或对文本 formatter 方法的<xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>调用。  
  
- 返回 Unicode newline 序列，如"CF"、"LF"或"CRLF"。  
  
<a name="section4"></a>
## <a name="providing-text-runs"></a>提供文本运行  
 文本格式设置过程的核心是文本格式化程序和文本存储之间的交互。 的<xref:System.Windows.Media.TextFormatting.TextSource>实现为文本格式化提供了<xref:System.Windows.Media.TextFormatting.TextRun>对象和用于设置文本运行格式的属性。 此交互由<xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>方法处理，该方法由文本前物质调用。  
  
 下表显示了一些预定义<xref:System.Windows.Media.TextFormatting.TextRun>对象。  
  
|TextRun 类型|使用情况|  
|------------------|-----------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|专用文本运行，用于将字符标志符号的表示形式传回给文本格式化程序。|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|专用文本运行，用于提供其中的度量、命中测试和绘制将作为整体执行的内容，例如文本中的按钮或图像。|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|专用文本运行，用于对行尾进行标记。|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|专用文本运行，用于对段落结尾进行标记。|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|用于标记段末尾的专用文本运行，例如结束受上一次<xref:System.Windows.Media.TextFormatting.TextModifier>运行影响的范围。|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|专用文本运行，用于对一系列隐藏字符进行标记。|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|专用文本运行，用于在其范围内修改文本运行属性。 范围扩展到下一个匹配<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>的文本运行或下一个<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>。|  
  
 可以对任何预定义<xref:System.Windows.Media.TextFormatting.TextRun>的对象进行子分类。 这样，文本源便可为文本格式化程序提供包含自定义数据的文本运行。  
  
 下面的示例演示了一<xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>种方法。 此文本存储将<xref:System.Windows.Media.TextFormatting.TextRun>对象返回到文本事件进行处理。  
  
 [!code-csharp[TextFormatterExample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
> 在此示例中，文本存储为所有文本提供了相同的文本属性。 高级文本存储需要实现各自的范围管理，以便单个字符具有不同的属性。  
  
<a name="section5"></a>
## <a name="specifying-formatting-properties"></a>指定格式设置属性  
 <xref:System.Windows.Media.TextFormatting.TextRun>对象使用文本存储提供的属性进行格式化。 这些属性有两种类型，<xref:System.Windows.Media.TextFormatting.TextParagraphProperties>和<xref:System.Windows.Media.TextFormatting.TextRunProperties>。 <xref:System.Windows.Media.TextFormatting.TextParagraphProperties>处理段落包含属性，如<xref:System.Windows.TextAlignment><xref:System.Windows.FlowDirection>和 。 <xref:System.Windows.Media.TextFormatting.TextRunProperties>对于在段落中运行的每个文本（如前景画笔和<xref:System.Windows.Media.Typeface>字体大小）可以不同的属性。 要实现自定义段落和自定义文本运行属性类型，应用程序必须创建派生自<xref:System.Windows.Media.TextFormatting.TextParagraphProperties>和<xref:System.Windows.Media.TextFormatting.TextRunProperties>派生的类。  
  
## <a name="see-also"></a>另请参阅

- [WPF 中的版式](typography-in-wpf.md)
- [WPF 中的文档](documents-in-wpf.md)
