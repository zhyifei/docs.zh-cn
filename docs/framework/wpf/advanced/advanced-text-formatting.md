---
title: "高级文本格式设置"
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
- formatting [WPF]
- text [WPF]
- typography [WPF], text formatting
ms.assetid: f0a7986e-f5b2-485c-a27d-f8e922022212
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9bb2664b267301fdf1e3a67e385595a5d28212bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="advanced-text-formatting"></a>高级文本格式设置
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]提供一组可靠的[!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)]在你的应用程序中包含文本。 布局和[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]，如<xref:System.Windows.Controls.TextBlock>、 提供最常见和常规使用元素的文本表示形式。 绘制[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]，如<xref:System.Windows.Media.GlyphRunDrawing>和<xref:System.Windows.Media.FormattedText>，提供一种在绘图中包括格式化的文本。 在最高级别，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]提供一个可扩展的文本格式引擎，用于控制文本呈现，例如文本存储管理、 运行的文本格式设置管理和嵌入的对象管理的各个方面。  
  
 本主题提供的简介[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]文本格式设置。 它注重客户端实现和利用[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]文本格式引擎。  
  
> [!NOTE]
>  本文档内的所有代码示例都可在[高级文本格式设置示例](http://go.microsoft.com/fwlink/?LinkID=159965)。  
  

  
<a name="prereq"></a>   
## <a name="prerequisites"></a>系统必备  
 本主题假定你熟悉更高级别的[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]用于呈现文本。 大多数用户方案都不需要进行高级的文本格式[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]本主题中讨论。 有关不同的文本的简介[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]，请参阅[WPF 中的文档](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)。  
  
<a name="section1"></a>   
## <a name="advanced-text-formatting"></a>高级文本格式设置  
 文本布局和[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]中控制[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]提供允许你轻松地将格式化的文本包含在你的应用程序的格式设置属性。 这些控件会公开许多用于处理文本呈现（包括字样、大小和颜色）的属性。 一般情况下，这些控件可以处理应用程序中的大部分文本呈现。 但是，某些高级方案要求控制文本存储和文本呈现。 为此，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 提供了一个可扩展的文本格式引擎。  
  
 在中找到高级的文本格式设置功能[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]包括文本格式引擎、 文本存储、 文本运行和格式设置属性。 文本格式引擎， <xref:System.Windows.Media.TextFormatting.TextFormatter>，创建要用于显示的文本行。 这通过启动行格式设置过程和调用文本格式化程序的实现<xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>。 通过调用的存储从文本存储文本格式化程序检索文本运行<xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>方法。 <xref:System.Windows.Media.TextFormatting.TextRun>对象然后形成<xref:System.Windows.Media.TextFormatting.TextLine>文本格式化程序对象和提供给你的应用程序进行检查或显示。  
  
<a name="section2"></a>   
## <a name="using-the-text-formatter"></a>使用文本格式化程序  
 <xref:System.Windows.Media.TextFormatting.TextFormatter>是[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]文本格式引擎，并提供有关格式设置和换行的服务。 文本格式化程序可处理各种文本字符格式和段落样式，并提供对国际文本布局的支持。  
  
 与传统的文本不同[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]、<xref:System.Windows.Media.TextFormatting.TextFormatter>与通过回调方法的一组文本布局客户端交互。 它要求客户端提供这些方法的实现中<xref:System.Windows.Media.TextFormatting.TextSource>类。 下图说明了客户端应用程序之间的文本布局交互和<xref:System.Windows.Media.TextFormatting.TextFormatter>。  
  
 ![文本布局客户端和 TextFormatter 示意图](../../../../docs/framework/wpf/advanced/media/textformatter01.png "TextFormatter01")  
应用程序和 TextFormatter 之间的交互  
  
 文本格式化程序用于从文本存储中，检索格式化的文本行即的实现<xref:System.Windows.Media.TextFormatting.TextSource>。 这可通过第一个创建的实例的文本格式化程序使用<xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A>方法。 此方法可创建一个文本格式化程序实例，并设置最大行高值和行宽值。 一旦创建文本格式化程序的实例，通过调用启动行创建过程<xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>方法。 <xref:System.Windows.Media.TextFormatting.TextFormatter>回拨到文本源以便检索的文本和格式设置参数的文本运行该窗体的行。  
  
 下例演示文本存储的格式设置过程。 <xref:System.Windows.Media.TextFormatting.TextFormatter>对象用于从文本存储中检索文本行，然后设置格式到绘制的文本行<xref:System.Windows.Media.DrawingContext>。  
  
 [!code-csharp[TextFormatterExample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>   
## <a name="implementing-the-client-text-store"></a>实现客户端文本存储  
 扩展文本格式引擎时，需要实现和管理文本存储的各个方面。 该任务不是无关紧要的。 文本存储负责跟踪文本运行属性、段落属性、嵌入对象和其他类似内容。 它还提供与单个文本格式化程序<xref:System.Windows.Media.TextFormatting.TextRun>对象文本格式化程序使用来创建<xref:System.Windows.Media.TextFormatting.TextLine>对象。  
  
 若要处理文本存储的虚拟化，文本存储必须派生自<xref:System.Windows.Media.TextFormatting.TextSource>。 <xref:System.Windows.Media.TextFormatting.TextSource>定义文本格式化程序使用从文本存储中检索文本运行的方法。 <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>是文本格式化程序用于检索文本的方法运行行格式设置中使用。 调用<xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>重复进行文本格式化程序直到出现以下情况之一：  
  
-   A<xref:System.Windows.Media.TextFormatting.TextEndOfLine>或返回子类。  
  
-   文本运行的累计的宽度超过在调用创建文本格式设置或文本格式化程序的调用中指定的最大线条宽度<xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>方法。  
  
-   A[!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]返回换行序列，如"CF"、"LF"或"CRLF"。  
  
<a name="section4"></a>   
## <a name="providing-text-runs"></a>提供文本运行  
 文本格式设置过程的核心是文本格式化程序和文本存储之间的交互。 实现<xref:System.Windows.Media.TextFormatting.TextSource>提供的文本格式化程序<xref:System.Windows.Media.TextFormatting.TextRun>对象和用于格式化文本运行的属性。 由处理这种交互<xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>方法，它由文本格式化程序调用。  
  
 下表显示了一些预定义的<xref:System.Windows.Media.TextFormatting.TextRun>对象。  
  
|TextRun 类型|用法|  
|------------------|-----------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|专用文本运行，用于将字符标志符号的表示形式传回给文本格式化程序。|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|专用文本运行，用于提供其中的度量、命中测试和绘制将作为整体执行的内容，例如文本中的按钮或图像。|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|专用文本运行，用于对行尾进行标记。|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|专用文本运行，用于对段落结尾进行标记。|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|使用标记的末尾一个段，例如，若要结束先前受影响的作用域运行专用的文本<xref:System.Windows.Media.TextFormatting.TextModifier>运行。|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|专用文本运行，用于对一系列隐藏字符进行标记。|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|专用文本运行，用于在其范围内修改文本运行属性。 范围扩展到下一个匹配<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>文本运行或下一步<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>。|  
  
 任意预定义<xref:System.Windows.Media.TextFormatting.TextRun>对象都可以子类化。 这样，文本源便可为文本格式化程序提供包含自定义数据的文本运行。  
  
 下面的示例演示<xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>方法。 此文本存储返回<xref:System.Windows.Media.TextFormatting.TextRun>处理的文本格式化程序的对象。  
  
 [!code-csharp[TextFormatterExample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
>  在此示例中，文本存储为所有文本提供了相同的文本属性。 高级文本存储需要实现各自的范围管理，以便单个字符具有不同的属性。  
  
<a name="section5"></a>   
## <a name="specifying-formatting-properties"></a>指定格式设置属性  
 <xref:System.Windows.Media.TextFormatting.TextRun>对象设置格式的使用提供的文本存储属性。 这些属性包括分为两种类型，<xref:System.Windows.Media.TextFormatting.TextParagraphProperties>和<xref:System.Windows.Media.TextFormatting.TextRunProperties>。 <xref:System.Windows.Media.TextFormatting.TextParagraphProperties>处理涉及段落的属性，如<xref:System.Windows.TextAlignment>和<xref:System.Windows.FlowDirection>。 <xref:System.Windows.Media.TextFormatting.TextRunProperties>是可以为每个文本域中的段落，如前景画笔，不同的属性<xref:System.Windows.Media.Typeface>，和字体大小。 若要实现自定义的段落，然后运行属性类型的自定义文本，你的应用程序必须创建派生自的类<xref:System.Windows.Media.TextFormatting.TextParagraphProperties>和<xref:System.Windows.Media.TextFormatting.TextRunProperties>分别。  
  
## <a name="see-also"></a>请参阅  
 [WPF 中的版式](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [WPF 中的文档](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
