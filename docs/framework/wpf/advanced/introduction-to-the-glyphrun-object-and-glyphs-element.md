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
ms.openlocfilehash: 9af07d48877fee0e94f8e5fa2556c4361795df6a
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740355"
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a>GlyphRun 对象和 Glyphs 元素简介
本主题介绍 <xref:System.Windows.Media.GlyphRun> 对象和 <xref:System.Windows.Documents.Glyphs> 元素。  

<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a>GlyphRun 简介  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供高级文本支持，包括可直接访问 <xref:System.Windows.Documents.Glyphs> 的字形级标记，适用于想要在设置格式后截获和保存文本的客户。 这些功能为以下每种方案中不同的文本呈现要求提供关键支持。  
  
1. 固定格式文档的屏幕显示。  
  
2. 打印方案。  
  
    - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 作为设备打印机语言。  
  
    - Microsoft XPS 文档编写器。  
  
    - 以前的打印机驱动程序，从 Win32 应用程序输出为固定格式。  
  
    - 打印后台处理格式。  
  
3. 固定格式的文档表示形式，包括以前版本的 Windows 和其他计算设备的客户端。  
  
> [!NOTE]
> <xref:System.Windows.Documents.Glyphs> 和 <xref:System.Windows.Media.GlyphRun> 专为固定格式的文档演示和打印方案而设计。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 为常规布局和 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 方案（如 <xref:System.Windows.Controls.Label> 和 <xref:System.Windows.Controls.TextBlock>）提供了多个元素。 有关布局和 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 方案的详细信息，请参阅 [WPF 中的版式](typography-in-wpf.md)。  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a>GlyphRun 对象  
 <xref:System.Windows.Media.GlyphRun> 对象表示一系列标志符号，该标志符号来自单个字体的单个字体，并且具有一种呈现样式。  
  
 <xref:System.Windows.Media.GlyphRun> 同时包含字体详细信息，例如标志符号 <xref:System.Windows.Documents.Glyphs.Indices%2A> 和单个标志符号位置。 它还包括从生成运行的原始 Unicode 码位、字符到标志符号缓冲区偏移量映射信息以及每个字符和每个标志符号的标志。  
  
 <xref:System.Windows.Media.GlyphRun> 具有相应的高级 <xref:System.Windows.FrameworkElement>，<xref:System.Windows.Documents.Glyphs>。 <xref:System.Windows.Documents.Glyphs> 可以在元素树和 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 标记中用于表示 <xref:System.Windows.Media.GlyphRun> 输出。  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a>Glyphs 元素  
 <xref:System.Windows.Documents.Glyphs> 元素表示 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中 <xref:System.Windows.Media.GlyphRun> 的输出。 以下标记语法用于描述 <xref:System.Windows.Documents.Glyphs> 元素。  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 以下属性定义对应于示例标记中的前四个特性。  
  
|Property|描述|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|指定资源标识符：文件名、Web 统一资源标识符（URI）或 .exe 或容器中的资源引用。|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|以绘图图面单位指定字号（默认值为 .96 英寸）。|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|指定粗体和斜体样式的标志。|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|指定双向布局级别。 偶数和零值表示从左到右布局；奇数值表示从右到左布局。|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a>Indices 属性  
 <xref:System.Windows.Documents.Glyphs.Indices%2A> 属性是字形规范字符串。 在一系列字形形成单个群集的情况下，群集中第一个字形的规范之前会跟有一个规范，说明组合了多少个字形和多少个代码点来形成群集。 <xref:System.Windows.Documents.Glyphs.Indices%2A> 属性在一个字符串中收集以下属性。  
  
- 字形索引  
  
- 字形步进宽度  
  
- 组合字形附加矢量  
  
- 从代码点映射到字形的群集  
  
- 字形标志  
  
 每个字形规范具有以下形式。  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a>字形度量值  
 每个字形定义用于指定它与其他 <xref:System.Windows.Documents.Glyphs>的对齐方式的指标。 以下图形定义两种不同字形字符的各种排版品质。  
  
 ![字形度量的示意图](./media/glyph-example.png "glyph_example")  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a>Glyphs 标记  
 下面的代码示例演示如何使用 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中 <xref:System.Windows.Documents.Glyphs> 元素的各种属性。  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>另请参阅

- [WPF 中的版式](typography-in-wpf.md)
- [WPF 中的文档](documents-in-wpf.md)
- [文本](optimizing-performance-text.md)
