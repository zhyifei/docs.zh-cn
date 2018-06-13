---
title: GlyphRun 对象和 Glyphs 元素简介
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], Glyphs element
- Glyphs elements [WPF]
- GlyphRun object [WPF]
- text [WPF], glyphs
- glyphs [WPF]
- typography [WPF], GlyphRun object
ms.assetid: 746ca769-a331-4435-9b95-f72a883b67c1
ms.openlocfilehash: 5750177c03cf859ebb884c5774b7ded03fa60628
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547376"
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a>GlyphRun 对象和 Glyphs 元素简介
本主题介绍<xref:System.Windows.Media.GlyphRun>对象和<xref:System.Windows.Documents.Glyphs>元素。  
  
  
<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a>GlyphRun 简介  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供高级的文本支持包括直接访问的标志符号级标记<xref:System.Windows.Documents.Glyphs>的用户想要截获并保存在格式化后的文本。 这些功能为以下每种方案中不同的文本呈现要求提供关键支持。  
  
1.  固定格式文档的屏幕显示。  
  
2.  打印方案。  
  
    -   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 作为设备打印机语言。  
  
    -   [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)]。  
  
    -   以前的打印机驱动程序，从 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 应用程序输出为固定格式。  
  
    -   打印后台处理格式。  
  
3.  固定格式的文档演示，包括以前版本的 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 客户端和其他计算设备。  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Glyphs> 和<xref:System.Windows.Media.GlyphRun>旨在固定格式的文档演示文稿和打印方案。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 为常规布局提供了多个元素和[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]如方案<xref:System.Windows.Controls.Label>和<xref:System.Windows.Controls.TextBlock>。 有关布局和 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 方案的详细信息，请参阅 [WPF 中的版式](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)。  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a>GlyphRun 对象  
 <xref:System.Windows.Media.GlyphRun>对象表示的标志符号的序列中的一种字体在单个大小，并且一种呈现样式的单个字形。  
  
 <xref:System.Windows.Media.GlyphRun> 包括这两种字体详细信息，例如标志符号<xref:System.Windows.Documents.Glyphs.Indices%2A>和单个标志符号位置。 它还包括原始[!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]点从字符标志符号缓冲区偏移量的映射信息，以及每个字符和每个标志符号的标志生成运行的代码。  
  
 <xref:System.Windows.Media.GlyphRun> 有一个相应的高级<xref:System.Windows.FrameworkElement>， <xref:System.Windows.Documents.Glyphs>。 <xref:System.Windows.Documents.Glyphs> 元素树中并在可以使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]标记来表示<xref:System.Windows.Media.GlyphRun>输出。  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a>Glyphs 元素  
 <xref:System.Windows.Documents.Glyphs>元素表示的输出<xref:System.Windows.Media.GlyphRun>中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。 以下的标记语法用于描述<xref:System.Windows.Documents.Glyphs>元素。  
  
 [!code-xaml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 以下属性定义对应于示例标记中的前四个特性。  
  
|属性|描述|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|指定资源标识符： 文件名、 Web [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]，或在应用程序.exe 或容器资源引用。|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|以绘图图面单位指定字号（默认值为 .96 英寸）。|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|指定粗体和斜体样式的标志。|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|指定双向布局级别。 偶数和零值表示从左到右布局；奇数值表示从右到左布局。|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a>Indices 属性  
 <xref:System.Windows.Documents.Glyphs.Indices%2A>属性是一个字符串的标志符号规范。 在一系列字形形成单个群集的情况下，群集中第一个字形的规范之前会跟有一个规范，说明组合了多少个字形和多少个代码点来形成群集。 <xref:System.Windows.Documents.Glyphs.Indices%2A>属性收集在一个字符串中的以下属性。  
  
-   字形索引  
  
-   字形步进宽度  
  
-   组合字形附加矢量  
  
-   从代码点映射到字形的群集  
  
-   字形标志  
  
 每个字形规范具有以下形式。  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a>字形度量值  
 每个字形定义度量值，指定与其他的对齐方式<xref:System.Windows.Documents.Glyphs>。 以下图形定义两种不同字形字符的各种排版品质。  
  
 ![字形度量示意图](../../../../docs/framework/wpf/advanced/media/glyph-example.png "glyph_example")  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a>Glyphs 标记  
 下面的代码示例演示如何使用各种属性<xref:System.Windows.Documents.Glyphs>中的元素[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。  
  
 [!code-xaml[GlyphsOvwSamp2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>请参阅  
 [WPF 中的版式](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [WPF 中的文档](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [文本](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)
