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
ms.openlocfilehash: 2c120c6d71cb22bc38909f980b2f6faf2b5c3663
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395215"
---
# <a name="advanced-text-formatting"></a>高级文本格式设置
Windows Presentation Foundation （WPF）提供了一组可靠的 Api，用于在应用程序中包含文本。 布局和 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]Api，如 <xref:System.Windows.Controls.TextBlock>，为文本演示提供最常见和最常用的元素。 绘图 Api （如 <xref:System.Windows.Media.GlyphRunDrawing> 和 <xref:System.Windows.Media.FormattedText>）提供了一种在绘图中包含格式化文本的方法。 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 提供了一个可扩展的文本格式引擎来控制文本显示的每个方面，如文本存储管理、文本运行格式管理和嵌入对象管理，在最高级级别。  
  
 本主题提供 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 文本格式设置的简介。 它侧重于客户端实现和 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 文本格式引擎的使用。  
  
> [!NOTE]
> 此文档中的所有代码示例都可以在[高级文本格式设置示例](https://go.microsoft.com/fwlink/?LinkID=159965)中找到。  

<a name="prereq"></a>   
## <a name="prerequisites"></a>先决条件  
 本主题假定您熟悉用于文本呈现的更高级 Api。 大多数用户方案都不需要本主题中讨论的高级文本格式设置 Api。 有关不同文本 Api 的介绍，请参阅[WPF 中的文档](documents-in-wpf.md)。  
  
<a name="section1"></a>   
## <a name="advanced-text-formatting"></a>高级文本格式设置  
 中的文本布局和 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 控件 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 提供格式设置属性，使你可以轻松地在应用程序中包含格式化文本。 这些控件会公开许多用于处理文本呈现（包括字样、大小和颜色）的属性。 一般情况下，这些控件可以处理应用程序中的大部分文本呈现。 但是，某些高级方案要求控制文本存储和文本呈现。 为此，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 提供了一个可扩展的文本格式引擎。  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中找到的高级文本格式设置功能包括文本格式引擎、文本存储、文本运行和格式设置属性。 文本格式引擎 <xref:System.Windows.Media.TextFormatting.TextFormatter>会创建要用于显示的文本行。 这是通过初始化行格式设置进程并调用文本格式化程序的 <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>来实现的。 文本格式化程序通过调用商店的 <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> 方法从文本存储中检索文本运行。 然后，文本格式化程序将 <xref:System.Windows.Media.TextFormatting.TextRun> 对象组成 <xref:System.Windows.Media.TextFormatting.TextLine> 对象中，并将其提供给应用程序进行检查或显示。  
  
<a name="section2"></a>   
## <a name="using-the-text-formatter"></a>使用文本格式化程序  
 <xref:System.Windows.Media.TextFormatting.TextFormatter> 是 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 文本格式引擎，并提供用于设置格式和断开文本线条的服务。 文本格式化程序可处理各种文本字符格式和段落样式，并提供对国际文本布局的支持。  
  
 与传统的文本 API 不同，<xref:System.Windows.Media.TextFormatting.TextFormatter> 通过一组回调方法与文本布局客户端进行交互。 它要求客户端在 <xref:System.Windows.Media.TextFormatting.TextSource> 类的实现中提供这些方法。 下图说明了客户端应用程序和 <xref:System.Windows.Media.TextFormatting.TextFormatter>之间的文本布局交互。  
  
 ![文本布局客户端和 TextFormatter 示意图](./media/advanced-text-formatting/text-layout-textformatter-interaction.png)  
  
 文本格式化程序用于从文本存储中检索格式化文本行，这是 <xref:System.Windows.Media.TextFormatting.TextSource>的实现。 这是通过使用 <xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A> 方法首先创建文本格式化程序的实例来完成的。 此方法可创建一个文本格式化程序实例，并设置最大行高值和行宽值。 一旦创建了文本格式化程序实例，就会通过调用 <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> 方法来启动行创建进程。 <xref:System.Windows.Media.TextFormatting.TextFormatter> 回调到文本源，以便为形成线条的文本的运行检索文本和格式参数。  
  
 下例演示文本存储的格式设置过程。 <xref:System.Windows.Media.TextFormatting.TextFormatter> 对象用于从文本存储中检索文本行，然后对绘制到 <xref:System.Windows.Media.DrawingContext>中的文本行进行格式设置。  
  
 [!code-csharp[TextFormatterExample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>   
## <a name="implementing-the-client-text-store"></a>实现客户端文本存储  
 扩展文本格式引擎时，需要实现和管理文本存储的各个方面。 该任务不是无关紧要的。 文本存储负责跟踪文本运行属性、段落属性、嵌入对象和其他类似内容。 它还使用文本格式化程序用于创建 <xref:System.Windows.Media.TextFormatting.TextLine> 对象的单个 <xref:System.Windows.Media.TextFormatting.TextRun> 对象提供文本格式化程序。  
  
 若要处理文本存储的虚拟化，文本存储必须派生自 <xref:System.Windows.Media.TextFormatting.TextSource>。 <xref:System.Windows.Media.TextFormatting.TextSource> 定义文本格式化程序用来从文本存储中检索文本运行的方法。 <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> 是文本格式化程序用来检索在行格式设置中使用的文本运行的方法。 在发生以下情况之一之前，文本格式化程序重复对 <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> 的调用：  
  
- 返回 <xref:System.Windows.Media.TextFormatting.TextEndOfLine> 或子类。  
  
- 文本运行的累积宽度超出了创建文本格式化程序的调用或对文本格式化程序的 <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> 方法的调用中指定的最大线条宽度。  
  
- 返回 Unicode 换行符，如 "CF"、"LF" 或 "CRLF"。  
  
<a name="section4"></a>   
## <a name="providing-text-runs"></a>提供文本运行  
 文本格式设置过程的核心是文本格式化程序和文本存储之间的交互。 的实现 <xref:System.Windows.Media.TextFormatting.TextSource> 提供文本格式化程序，其中包含 <xref:System.Windows.Media.TextFormatting.TextRun> 对象和用于设置文本格式的属性。 此交互由文本格式化程序调用的 <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> 方法进行处理。  
  
 下表显示了一些预定义的 <xref:System.Windows.Media.TextFormatting.TextRun> 对象。  
  
|TextRun 类型|用法|  
|------------------|-----------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|专用文本运行，用于将字符标志符号的表示形式传回给文本格式化程序。|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|专用文本运行，用于提供其中的度量、命中测试和绘制将作为整体执行的内容，例如文本中的按钮或图像。|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|专用文本运行，用于对行尾进行标记。|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|专用文本运行，用于对段落结尾进行标记。|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|专用文本运行，用于标记段的末尾，如结束受上一 <xref:System.Windows.Media.TextFormatting.TextModifier> 运行影响的范围。|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|专用文本运行，用于对一系列隐藏字符进行标记。|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|专用文本运行，用于在其范围内修改文本运行属性。 范围将扩展到下一个匹配的 <xref:System.Windows.Media.TextFormatting.TextEndOfSegment> 文本运行，或下一个 <xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>。|  
  
 任何预定义的 <xref:System.Windows.Media.TextFormatting.TextRun> 对象都可以为子类。 这样，文本源便可为文本格式化程序提供包含自定义数据的文本运行。  
  
 下面的示例演示 <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> 方法。 此文本存储将 <xref:System.Windows.Media.TextFormatting.TextRun> 对象返回到文本格式化程序以进行处理。  
  
 [!code-csharp[TextFormatterExample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
> 在此示例中，文本存储为所有文本提供了相同的文本属性。 高级文本存储需要实现各自的范围管理，以便单个字符具有不同的属性。  
  
<a name="section5"></a>   
## <a name="specifying-formatting-properties"></a>指定格式设置属性  
 使用文本存储提供的属性设置 <xref:System.Windows.Media.TextFormatting.TextRun> 对象的格式。 这些属性分为两种类型，<xref:System.Windows.Media.TextFormatting.TextParagraphProperties> 和 <xref:System.Windows.Media.TextFormatting.TextRunProperties>。 <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> 处理段落包含性属性，如 <xref:System.Windows.TextAlignment> 和 <xref:System.Windows.FlowDirection>。 <xref:System.Windows.Media.TextFormatting.TextRunProperties> 是在段落中运行的每个文本可能不同的属性，例如前景画笔、<xref:System.Windows.Media.Typeface>和字体大小。 若要实现自定义段落和自定义文本运行属性类型，你的应用程序必须分别创建从 <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> 和 <xref:System.Windows.Media.TextFormatting.TextRunProperties> 派生的类。  
  
## <a name="see-also"></a>另请参阅

- [WPF 中的版式](typography-in-wpf.md)
- [WPF 中的文档](documents-in-wpf.md)
