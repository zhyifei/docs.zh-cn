---
title: "GlyphRun 对象和 Glyphs 元素简介"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- typography [WPF], Glyphs element
- Glyphs elements [WPF]
- GlyphRun object [WPF]
- text [WPF], glyphs
- glyphs [WPF]
- typography [WPF], GlyphRun object
ms.assetid: 746ca769-a331-4435-9b95-f72a883b67c1
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fa868b520224b27b3cd2b3dc99431728ad8ea527
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a><span data-ttu-id="0b4cf-102">GlyphRun 对象和 Glyphs 元素简介</span><span class="sxs-lookup"><span data-stu-id="0b4cf-102">Introduction to the GlyphRun Object and Glyphs Element</span></span>
<span data-ttu-id="0b4cf-103">本主题介绍<xref:System.Windows.Media.GlyphRun>对象和<xref:System.Windows.Documents.Glyphs>元素。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-103">This topic describes the <xref:System.Windows.Media.GlyphRun> object and the <xref:System.Windows.Documents.Glyphs> element.</span></span>  
  
  
<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a><span data-ttu-id="0b4cf-104">GlyphRun 简介</span><span class="sxs-lookup"><span data-stu-id="0b4cf-104">Introduction to GlyphRun</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="0b4cf-105">提供高级的文本支持包括直接访问的标志符号级标记<xref:System.Windows.Documents.Glyphs>的用户想要截获并保存在格式化后的文本。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-105"> provides advanced text support including glyph-level markup with direct access to <xref:System.Windows.Documents.Glyphs> for customers who want to intercept and persist text after formatting.</span></span> <span data-ttu-id="0b4cf-106">这些功能为以下每种方案中不同的文本呈现要求提供关键支持。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-106">These features provide critical support for the different text rendering requirements in each of the following scenarios.</span></span>  
  
1.  <span data-ttu-id="0b4cf-107">固定格式文档的屏幕显示。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-107">Screen display of fixed-format documents.</span></span>  
  
2.  <span data-ttu-id="0b4cf-108">打印方案。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-108">Print scenarios.</span></span>  
  
    -   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]<span data-ttu-id="0b4cf-109"> 作为设备打印机语言。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-109"> as a device printer language.</span></span>  
  
    -   [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)]<span data-ttu-id="0b4cf-110">。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-110">.</span></span>  
  
    -   <span data-ttu-id="0b4cf-111">以前的打印机驱动程序，从 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 应用程序输出为固定格式。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-111">Previous printer drivers, output from [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications to the fixed format.</span></span>  
  
    -   <span data-ttu-id="0b4cf-112">打印后台处理格式。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-112">Print spool format.</span></span>  
  
3.  <span data-ttu-id="0b4cf-113">固定格式的文档演示，包括以前版本的 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 客户端和其他计算设备。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-113">Fixed-format document representation, including clients for previous versions of [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] and other computing devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b4cf-114"><xref:System.Windows.Documents.Glyphs>和<xref:System.Windows.Media.GlyphRun>旨在固定格式的文档演示文稿和打印方案。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-114"><xref:System.Windows.Documents.Glyphs> and <xref:System.Windows.Media.GlyphRun> are designed for fixed-format document presentation and print scenarios.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="0b4cf-115">为常规布局提供了多个元素和[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]如方案<xref:System.Windows.Controls.Label>和<xref:System.Windows.Controls.TextBlock>。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-115"> provides several elements for general layout and [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] scenarios such as <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="0b4cf-116">有关布局和 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 方案的详细信息，请参阅 [WPF 中的版式](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-116">For more information on layout and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenarios, see the [Typography in WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md).</span></span>  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a><span data-ttu-id="0b4cf-117">GlyphRun 对象</span><span class="sxs-lookup"><span data-stu-id="0b4cf-117">The GlyphRun Object</span></span>  
 <span data-ttu-id="0b4cf-118"><xref:System.Windows.Media.GlyphRun>对象表示的标志符号的序列中的一种字体在单个大小，并且一种呈现样式的单个字形。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-118">The <xref:System.Windows.Media.GlyphRun> object represents a sequence of glyphs from a single face of a single font at a single size, and with a single rendering style.</span></span>  
  
 <span data-ttu-id="0b4cf-119"><xref:System.Windows.Media.GlyphRun>包括这两种字体详细信息，例如标志符号<xref:System.Windows.Documents.Glyphs.Indices%2A>和单个标志符号位置。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-119"><xref:System.Windows.Media.GlyphRun> includes both font details such as glyph <xref:System.Windows.Documents.Glyphs.Indices%2A> and individual glyph positions.</span></span> <span data-ttu-id="0b4cf-120">它还包括原始[!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]点从字符标志符号缓冲区偏移量的映射信息，以及每个字符和每个标志符号的标志生成运行的代码。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-120">It also includes the original [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] code points the run was generated from, character-to-glyph buffer offset mapping information, and per-character and per-glyph flags.</span></span>  
  
 <span data-ttu-id="0b4cf-121"><xref:System.Windows.Media.GlyphRun>有一个相应的高级<xref:System.Windows.FrameworkElement>， <xref:System.Windows.Documents.Glyphs>。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-121"><xref:System.Windows.Media.GlyphRun> has a corresponding high-level <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="0b4cf-122"><xref:System.Windows.Documents.Glyphs>元素树中并在可以使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]标记来表示<xref:System.Windows.Media.GlyphRun>输出。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-122"><xref:System.Windows.Documents.Glyphs> can be used in the element tree and in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup to represent <xref:System.Windows.Media.GlyphRun> output.</span></span>  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a><span data-ttu-id="0b4cf-123">Glyphs 元素</span><span class="sxs-lookup"><span data-stu-id="0b4cf-123">The Glyphs Element</span></span>  
 <span data-ttu-id="0b4cf-124"><xref:System.Windows.Documents.Glyphs>元素表示的输出<xref:System.Windows.Media.GlyphRun>中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-124">The <xref:System.Windows.Documents.Glyphs> element represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="0b4cf-125">以下的标记语法用于描述<xref:System.Windows.Documents.Glyphs>元素。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-125">The following markup syntax is used to describe the <xref:System.Windows.Documents.Glyphs> element.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="0b4cf-126">以下属性定义对应于示例标记中的前四个特性。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-126">The following property definitions correspond to the first four attributes in the sample markup.</span></span>  
  
|<span data-ttu-id="0b4cf-127">属性</span><span class="sxs-lookup"><span data-stu-id="0b4cf-127">Property</span></span>|<span data-ttu-id="0b4cf-128">描述</span><span class="sxs-lookup"><span data-stu-id="0b4cf-128">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|<span data-ttu-id="0b4cf-129">指定资源标识符： 文件名、 Web [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]，或在应用程序.exe 或容器资源引用。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-129">Specifies a resource identifier: file name, Web [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], or resource reference in the application .exe or container.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|<span data-ttu-id="0b4cf-130">以绘图图面单位指定字号（默认值为 .96 英寸）。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-130">Specifies the font size in drawing surface units (default is .96 inches).</span></span>|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|<span data-ttu-id="0b4cf-131">指定粗体和斜体样式的标志。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-131">Specifies flags for bold and Italic styles.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|<span data-ttu-id="0b4cf-132">指定双向布局级别。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-132">Specifies the bidirectional layout level.</span></span> <span data-ttu-id="0b4cf-133">偶数和零值表示从左到右布局；奇数值表示从右到左布局。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-133">Even-numbered and zero values imply left-to-right layout; odd-numbered values imply right-to-left layout.</span></span>|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a><span data-ttu-id="0b4cf-134">Indices 属性</span><span class="sxs-lookup"><span data-stu-id="0b4cf-134">Indices property</span></span>  
 <span data-ttu-id="0b4cf-135"><xref:System.Windows.Documents.Glyphs.Indices%2A>属性是一个字符串的标志符号规范。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-135">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property is a string of glyph specifications.</span></span> <span data-ttu-id="0b4cf-136">在一系列字形形成单个群集的情况下，群集中第一个字形的规范之前会跟有一个规范，说明组合了多少个字形和多少个代码点来形成群集。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-136">Where a sequence of glyphs forms a single cluster, the specification of the first glyph in the cluster is preceded by a specification of how many glyphs and how many code points combine to form the cluster.</span></span> <span data-ttu-id="0b4cf-137"><xref:System.Windows.Documents.Glyphs.Indices%2A>属性收集在一个字符串中的以下属性。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-137">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property collects in one string the following properties.</span></span>  
  
-   <span data-ttu-id="0b4cf-138">字形索引</span><span class="sxs-lookup"><span data-stu-id="0b4cf-138">Glyph indices</span></span>  
  
-   <span data-ttu-id="0b4cf-139">字形步进宽度</span><span class="sxs-lookup"><span data-stu-id="0b4cf-139">Glyph advance widths</span></span>  
  
-   <span data-ttu-id="0b4cf-140">组合字形附加矢量</span><span class="sxs-lookup"><span data-stu-id="0b4cf-140">Combining glyph attachment vectors</span></span>  
  
-   <span data-ttu-id="0b4cf-141">从代码点映射到字形的群集</span><span class="sxs-lookup"><span data-stu-id="0b4cf-141">Cluster mapping from code points to glyphs</span></span>  
  
-   <span data-ttu-id="0b4cf-142">字形标志</span><span class="sxs-lookup"><span data-stu-id="0b4cf-142">Glyph flags</span></span>  
  
 <span data-ttu-id="0b4cf-143">每个字形规范具有以下形式。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-143">Each glyph specification has the following form.</span></span>  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a><span data-ttu-id="0b4cf-144">字形度量值</span><span class="sxs-lookup"><span data-stu-id="0b4cf-144">Glyph Metrics</span></span>  
 <span data-ttu-id="0b4cf-145">每个字形定义度量值，指定与其他的对齐方式<xref:System.Windows.Documents.Glyphs>。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-145">Each glyph defines metrics that specify how it aligns with other <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="0b4cf-146">以下图形定义两种不同字形字符的各种排版品质。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-146">The following graphic defines the various typographic qualities of two different glyph characters.</span></span>  
  
 <span data-ttu-id="0b4cf-147">![字形度量示意图](../../../../docs/framework/wpf/advanced/media/glyph-example.png "glyph_example")</span><span class="sxs-lookup"><span data-stu-id="0b4cf-147">![Diagraph of glyph measurements](../../../../docs/framework/wpf/advanced/media/glyph-example.png "glyph_example")</span></span>  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a><span data-ttu-id="0b4cf-148">Glyphs 标记</span><span class="sxs-lookup"><span data-stu-id="0b4cf-148">Glyphs Markup</span></span>  
 <span data-ttu-id="0b4cf-149">下面的代码示例演示如何使用各种属性<xref:System.Windows.Documents.Glyphs>中的元素[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0b4cf-149">The following code example shows how to use various properties of the <xref:System.Windows.Documents.Glyphs> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0b4cf-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b4cf-150">See Also</span></span>  
 [<span data-ttu-id="0b4cf-151">WPF 中的版式</span><span class="sxs-lookup"><span data-stu-id="0b4cf-151">Typography in WPF</span></span>](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [<span data-ttu-id="0b4cf-152">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="0b4cf-152">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="0b4cf-153">文本</span><span class="sxs-lookup"><span data-stu-id="0b4cf-153">Text</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)
