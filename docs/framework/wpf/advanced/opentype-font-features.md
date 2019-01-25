---
title: OpenType 字体功能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], OpenType
- typography [WPF], OpenType font technology
- OpenType font technology [WPF]
ms.assetid: 4061a9d1-fe8b-4921-9e17-18ec7d2e3ea2
ms.openlocfilehash: 5751efe0c6621425b8b54c642d51127118c0b6bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529774"
---
# <a name="opentype-font-features"></a><span data-ttu-id="4587b-102">OpenType 字体功能</span><span class="sxs-lookup"><span data-stu-id="4587b-102">OpenType Font Features</span></span>
<span data-ttu-id="4587b-103">本主题概述 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 字体技术的一些主要功能。</span><span class="sxs-lookup"><span data-stu-id="4587b-103">This topic provides an overview of some of the key features of [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] font technology in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  

  
<a name="overview"></a>   
## <a name="opentype-font-format"></a><span data-ttu-id="4587b-104">OpenType 字体格式</span><span class="sxs-lookup"><span data-stu-id="4587b-104">OpenType Font Format</span></span>  
 <span data-ttu-id="4587b-105">[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 字体格式是 [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] 字体格式的扩展，添加了对 PostScript 字体数据的支持。</span><span class="sxs-lookup"><span data-stu-id="4587b-105">The [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] font format is an extension of the [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] font format, adding support for PostScript font data.</span></span> <span data-ttu-id="4587b-106">[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 字体格式由 [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] 和 Adobe Corporation 联合开发。</span><span class="sxs-lookup"><span data-stu-id="4587b-106">The [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] font format was developed jointly by [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] and Adobe Corporation.</span></span> <span data-ttu-id="4587b-107">无论字体包含 [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] 边框还是 CFF (PostScript) 边框，[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 字体和支持 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 字体的操作系统服务都向用户提供一种简单的字体安装和使用方式。</span><span class="sxs-lookup"><span data-stu-id="4587b-107">[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fonts and the operating system services which support [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fonts provide users with a simple way to install and use fonts, whether the fonts contain [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] outlines or CFF (PostScript) outlines.</span></span>  
  
 <span data-ttu-id="4587b-108">[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 字体格式解决了开发人员面临的以下挑战：</span><span class="sxs-lookup"><span data-stu-id="4587b-108">The [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] font format addresses the following developer challenges:</span></span>  
  
-   <span data-ttu-id="4587b-109">更广泛的多平台支持。</span><span class="sxs-lookup"><span data-stu-id="4587b-109">Broader multi-platform support.</span></span>  
  
-   <span data-ttu-id="4587b-110">更出色的国际字符集支持。</span><span class="sxs-lookup"><span data-stu-id="4587b-110">Better support for international character sets.</span></span>  
  
-   <span data-ttu-id="4587b-111">更优的字体数据保护。</span><span class="sxs-lookup"><span data-stu-id="4587b-111">Better protection for font data.</span></span>  
  
-   <span data-ttu-id="4587b-112">更小的文件大小，让字体发布更加高效。</span><span class="sxs-lookup"><span data-stu-id="4587b-112">Smaller file sizes to make font distribution more efficient.</span></span>  
  
-   <span data-ttu-id="4587b-113">更广泛的高级版式控件支持。</span><span class="sxs-lookup"><span data-stu-id="4587b-113">Broader support for advanced typographic control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4587b-114">Windows SDK 包含了一组可用于 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 应用程序的示例 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 字体。</span><span class="sxs-lookup"><span data-stu-id="4587b-114">The Windows SDK contains a set of sample [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fonts that you can use with [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="4587b-115">这些字体提供本主题余下部分所述的大多数功能。</span><span class="sxs-lookup"><span data-stu-id="4587b-115">These fonts provide most of the features illustrated in the rest of this topic.</span></span> <span data-ttu-id="4587b-116">有关详细信息，请参阅[示例 OpenType 字体包](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md)。</span><span class="sxs-lookup"><span data-stu-id="4587b-116">For more information, see [Sample OpenType Font Pack](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md).</span></span>  
  
 <span data-ttu-id="4587b-117">有关 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 字体格式的详细信息，请参阅 [OpenType 规范](https://go.microsoft.com/fwlink/?LinkId=96731)。</span><span class="sxs-lookup"><span data-stu-id="4587b-117">See the [OpenType Specification](https://go.microsoft.com/fwlink/?LinkId=96731) for details of the [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] font format.</span></span>  
  
### <a name="advanced-typographic-extensions"></a><span data-ttu-id="4587b-118">高级版式扩展</span><span class="sxs-lookup"><span data-stu-id="4587b-118">Advanced Typographic Extensions</span></span>  
 <span data-ttu-id="4587b-119">高级版式表格（[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 布局表格）扩展了具有 [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] 或 CFF 边框的字体的功能。</span><span class="sxs-lookup"><span data-stu-id="4587b-119">The Advanced Typographic tables ([!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Layout tables) extend the functionality of fonts with either [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] or CFF outlines.</span></span> [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] <span data-ttu-id="4587b-120">布局字体包含一些其他信息，可扩展字体功能以支持高质量国际版式。</span><span class="sxs-lookup"><span data-stu-id="4587b-120">Layout fonts contain additional information that extends the capabilities of the fonts to support high-quality international typography.</span></span> <span data-ttu-id="4587b-121">大多数 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 字体仅体现全部可用 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="4587b-121">Most [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fonts expose only a subset of the total [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] features available.</span></span> [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] <span data-ttu-id="4587b-122">字体提供以下功能。</span><span class="sxs-lookup"><span data-stu-id="4587b-122">fonts provide the following features.</span></span>  
  
-   <span data-ttu-id="4587b-123">字符与字形之间的丰富映射，可支持连字、定位格式、备用项以及其他字体替换功能。</span><span class="sxs-lookup"><span data-stu-id="4587b-123">Rich mapping between characters and glyphs that support ligatures, positional forms, alternates, and other font substitutions.</span></span>  
  
-   <span data-ttu-id="4587b-124">支持二维定位和字形附加。</span><span class="sxs-lookup"><span data-stu-id="4587b-124">Support for two-dimensional positioning and glyph attachment.</span></span>  
  
-   <span data-ttu-id="4587b-125">字体中包含的显式脚本和语言信息，使文本处理应用程序可相应调整其行为。</span><span class="sxs-lookup"><span data-stu-id="4587b-125">Explicit script and language information contained in font, so a text-processing application can adjust its behavior accordingly.</span></span>  
  
 <span data-ttu-id="4587b-126">[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 布局表格在 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 规范的[“字体文件表格”](https://www.microsoft.com/typography/otspec/otff.htm)部分中进行了更详细的描述。</span><span class="sxs-lookup"><span data-stu-id="4587b-126">The [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Layout tables are described in more detail in the ["Font File Tables"](https://www.microsoft.com/typography/otspec/otff.htm) section of the [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] specification.</span></span>  
  
 <span data-ttu-id="4587b-127">本概述的其余部分介绍的广度和灵活性的一些直观有趣[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]的属性公开的功能<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-127">The remainder of this overview introduces the breadth and flexibility of some of the visually-interesting [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] features that are exposed by the properties of the <xref:System.Windows.Documents.Typography> object.</span></span> <span data-ttu-id="4587b-128">有关此对象的详细信息，请参阅[版式类](#typography_class)。</span><span class="sxs-lookup"><span data-stu-id="4587b-128">For more information on this object, see [Typography Class](#typography_class).</span></span>  
  
<a name="variants"></a>   
## <a name="variants"></a><span data-ttu-id="4587b-129">变量</span><span class="sxs-lookup"><span data-stu-id="4587b-129">Variants</span></span>  
 <span data-ttu-id="4587b-130">变量用于呈现不同的版式风格，例如上标和下标。</span><span class="sxs-lookup"><span data-stu-id="4587b-130">Variants are used to render different typographic styles, such as superscripts and subscripts.</span></span>  
  
### <a name="superscripts-and-subscripts"></a><span data-ttu-id="4587b-131">上标和下标</span><span class="sxs-lookup"><span data-stu-id="4587b-131">Superscripts and Subscripts</span></span>  
 <span data-ttu-id="4587b-132"><xref:System.Windows.Documents.Typography.Variants%2A>属性可以设置上标和下标值[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]字体。</span><span class="sxs-lookup"><span data-stu-id="4587b-132">The <xref:System.Windows.Documents.Typography.Variants%2A> property allows you to set superscript and subscript values for an [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] font.</span></span>  
  
 <span data-ttu-id="4587b-133">以下文本显示 Palatino Linotype 字体的上标。</span><span class="sxs-lookup"><span data-stu-id="4587b-133">The following text displays superscripts for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="4587b-134">![使用 OpenType 上标的文本](../../../../docs/framework/wpf/advanced/media/opentypefont14.gif "opentypefont14")</span><span class="sxs-lookup"><span data-stu-id="4587b-134">![Text using OpenType superscripts](../../../../docs/framework/wpf/advanced/media/opentypefont14.gif "opentypefont14")</span></span>  
<span data-ttu-id="4587b-135">使用 OpenType 上标的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-135">Text using OpenType superscripts</span></span>  
  
 <span data-ttu-id="4587b-136">以下标记示例演示如何定义使用的属性的 Palatino Linotype 字体的上标<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-136">The following markup example shows how to define superscripts for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#12)]  
  
 <span data-ttu-id="4587b-137">以下文本显示 Palatino Linotype 字体的下标。</span><span class="sxs-lookup"><span data-stu-id="4587b-137">The following text displays subscripts for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="4587b-138">![使用 OpenType 下标的文本](../../../../docs/framework/wpf/advanced/media/opentypefont15.gif "opentypefont15")</span><span class="sxs-lookup"><span data-stu-id="4587b-138">![Text using OpenType subscripts](../../../../docs/framework/wpf/advanced/media/opentypefont15.gif "opentypefont15")</span></span>  
<span data-ttu-id="4587b-139">使用 OpenType 下标的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-139">Text using OpenType subscripts</span></span>  
  
 <span data-ttu-id="4587b-140">以下标记示例演示如何定义 Palatino Linotype 字体的使用的属性的下标<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-140">The following markup example shows how to define subscripts for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#13)]  
  
### <a name="decorative-uses-of-superscripts-and-subscripts"></a><span data-ttu-id="4587b-141">上标和下标的修饰用法</span><span class="sxs-lookup"><span data-stu-id="4587b-141">Decorative Uses of Superscripts and Subscripts</span></span>  
 <span data-ttu-id="4587b-142">也可使用上标和下标来营造混合大小写文本的修饰效果。</span><span class="sxs-lookup"><span data-stu-id="4587b-142">You can also use superscripts and subscripts to create decorative effects of mixed case text.</span></span> <span data-ttu-id="4587b-143">以下文本显示 Palatino Linotype 字体的上标和下标文本。</span><span class="sxs-lookup"><span data-stu-id="4587b-143">The following text displays superscript and subscript text for the Palatino Linotype font.</span></span> <span data-ttu-id="4587b-144">注意，大写字母不受影响。</span><span class="sxs-lookup"><span data-stu-id="4587b-144">Note that the capitals are not affected.</span></span>  
  
 <span data-ttu-id="4587b-145">![使用 OpenType 上标和下标的文本](../../../../docs/framework/wpf/advanced/media/opentypefont16.gif "opentypefont16")</span><span class="sxs-lookup"><span data-stu-id="4587b-145">![Text using OpenType superscripts and subscripts](../../../../docs/framework/wpf/advanced/media/opentypefont16.gif "opentypefont16")</span></span>  
<span data-ttu-id="4587b-146">使用 OpenType 上标和下标的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-146">Text using OpenType superscripts and subscripts</span></span>  
  
 <span data-ttu-id="4587b-147">以下标记示例演示如何定义上标和下标字体使用的属性的<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-147">The following markup example shows how to define superscripts and subscripts for a font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#14)]  
  
<a name="capitals"></a>   
## <a name="capitals"></a><span data-ttu-id="4587b-148">大写字母</span><span class="sxs-lookup"><span data-stu-id="4587b-148">Capitals</span></span>  
 <span data-ttu-id="4587b-149">大写字母是一组以大写样式字形呈现文本的版式形式。</span><span class="sxs-lookup"><span data-stu-id="4587b-149">Capitals are a set of typographical forms that render text in capital-styled glyphs.</span></span> <span data-ttu-id="4587b-150">通常情况下，当以全大写呈现文本时，字母之间的间距可能看起来很小，字母的权重和比例看起来会很大。</span><span class="sxs-lookup"><span data-stu-id="4587b-150">Typically, when text is rendered as all capitals, the spacing between letters can appear too tight, and the weight and proportion of the letters too heavy.</span></span> [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] <span data-ttu-id="4587b-151">支持多种大写字母的样式格式，包括小体大写字母、小号大写字母、标题和大写字母间距。</span><span class="sxs-lookup"><span data-stu-id="4587b-151">supports a number of styling formats for capitals, including small capitals, petite capitals, titling, and capital spacing.</span></span> <span data-ttu-id="4587b-152">通过这些样式格式可控制大写字母的外观。</span><span class="sxs-lookup"><span data-stu-id="4587b-152">These styling formats allow you to control the appearance of capitals.</span></span>  
  
 <span data-ttu-id="4587b-153">以下文本显示 Pescadero 字体的标准大写字母，其后接样式为“SmallCaps”和“AllSmallCaps”的字母。</span><span class="sxs-lookup"><span data-stu-id="4587b-153">The following text displays standard capital letters for the Pescadero font, followed by the letters styled as "SmallCaps" and "AllSmallCaps".</span></span> <span data-ttu-id="4587b-154">本例中，对所有三个单词均使用相同的字体大小。</span><span class="sxs-lookup"><span data-stu-id="4587b-154">In this case, the same font size is used for all three words.</span></span>  
  
 <span data-ttu-id="4587b-155">![使用 OpenType 大写字母的文本](../../../../docs/framework/wpf/advanced/media/opentypefont11.gif "opentypefont11")</span><span class="sxs-lookup"><span data-stu-id="4587b-155">![Text using OpenType capitals](../../../../docs/framework/wpf/advanced/media/opentypefont11.gif "opentypefont11")</span></span>  
<span data-ttu-id="4587b-156">使用 OpenType 大写字母的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-156">Text using OpenType capitals</span></span>  
  
 <span data-ttu-id="4587b-157">以下标记示例演示如何定义使用的属性的 Pescadero 字体的大写字母<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-157">The following markup example shows how to define capitals for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span> <span data-ttu-id="4587b-158">使用“SmallCaps”格式时会忽略任何前导大写字母。</span><span class="sxs-lookup"><span data-stu-id="4587b-158">When the "SmallCaps" format is used, any leading capital letter is ignored.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
### <a name="titling-capitals"></a><span data-ttu-id="4587b-159">标题大写字母</span><span class="sxs-lookup"><span data-stu-id="4587b-159">Titling Capitals</span></span>  
 <span data-ttu-id="4587b-160">标题大写字母权重和比例更小，外观比普通大写字母更加雅致。</span><span class="sxs-lookup"><span data-stu-id="4587b-160">Titling capitals are lighter in weight and proportion and designed to give a more elegant look than normal capitals.</span></span> <span data-ttu-id="4587b-161">标题大写字母通常用于作为标题的大号字体中。</span><span class="sxs-lookup"><span data-stu-id="4587b-161">Titling capitals are typically used in larger font sizes as headings.</span></span> <span data-ttu-id="4587b-162">以下文本显示 Pescadero 字体的普通大写字母和标题大写字母。</span><span class="sxs-lookup"><span data-stu-id="4587b-162">The following text displays normal and titling capitals for the Pescadero font.</span></span> <span data-ttu-id="4587b-163">请注意第二行文本的宽度更窄。</span><span class="sxs-lookup"><span data-stu-id="4587b-163">Notice the narrower stem widths of the text on the second line.</span></span>  
  
 <span data-ttu-id="4587b-164">![使用 OpenType 标题大写字母的文本](../../../../docs/framework/wpf/advanced/media/opentypefont20.gif "OpenTypeFont20")</span><span class="sxs-lookup"><span data-stu-id="4587b-164">![Text using OpenType titling capitals](../../../../docs/framework/wpf/advanced/media/opentypefont20.gif "OpenTypeFont20")</span></span>  
<span data-ttu-id="4587b-165">使用 OpenType 标题大写字母的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-165">Text using OpenType titling capitals</span></span>  
  
 <span data-ttu-id="4587b-166">以下标记示例演示如何定义 Pescadero 字体使用的属性的标题大写字母<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-166">The following markup example shows how to define titling capitals for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet17)]  
  
### <a name="capital-spacing"></a><span data-ttu-id="4587b-167">大写字母间距</span><span class="sxs-lookup"><span data-stu-id="4587b-167">Capital Spacing</span></span>  
 <span data-ttu-id="4587b-168">大写字母间距功能让你可以在使用全大写字母文本时提供更宽的间距。</span><span class="sxs-lookup"><span data-stu-id="4587b-168">Capital spacing is a feature that allows you to provide more spacing when using all capitals in text.</span></span> <span data-ttu-id="4587b-169">大写字母通常设计为与小写字母混合使用。</span><span class="sxs-lookup"><span data-stu-id="4587b-169">Capital letters are typically designed to blend with lowercase letters.</span></span> <span data-ttu-id="4587b-170">大写字母和小写字母之间看起来比较美观的间距在使用全大写字母时可能会显得过紧。</span><span class="sxs-lookup"><span data-stu-id="4587b-170">Spacing that appears attractive between and a capital letter and a lowercase letter may look too tight when all capital letters are used.</span></span> <span data-ttu-id="4587b-171">以下文本显示 Pescadero 字体的普通间距和大写字母间距。</span><span class="sxs-lookup"><span data-stu-id="4587b-171">The following text displays normal and capital spacing for the Pescadero font.</span></span>  
  
 <span data-ttu-id="4587b-172">![使用 OpenType 大写字母间距的文本](../../../../docs/framework/wpf/advanced/media/opentypefont21.gif "OpenTypeFont21")</span><span class="sxs-lookup"><span data-stu-id="4587b-172">![Text using OpenType capital spacing](../../../../docs/framework/wpf/advanced/media/opentypefont21.gif "OpenTypeFont21")</span></span>  
<span data-ttu-id="4587b-173">使用 OpenType 大写字母间距的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-173">Text using OpenType capital spacing</span></span>  
  
 <span data-ttu-id="4587b-174">以下标记示例演示如何定义使用的属性的 Pescadero 字体的大写字母间距<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-174">The following markup example shows how to define capital spacing for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet18)]  
  
<a name="ligatures"></a>   
## <a name="ligatures"></a><span data-ttu-id="4587b-175">连字</span><span class="sxs-lookup"><span data-stu-id="4587b-175">Ligatures</span></span>  
 <span data-ttu-id="4587b-176">连子是为使文本更具可读性或更加美观而由两个或更多字形形成的一个单一字形。</span><span class="sxs-lookup"><span data-stu-id="4587b-176">Ligatures are two or more glyphs that are formed into a single glyph in order to create more readable or attractive text.</span></span> [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] <span data-ttu-id="4587b-177">字体支持四种类型的连字：</span><span class="sxs-lookup"><span data-stu-id="4587b-177">fonts support four types of ligatures:</span></span>  
  
-   <span data-ttu-id="4587b-178">**标准连字**。</span><span class="sxs-lookup"><span data-stu-id="4587b-178">**Standard ligatures**.</span></span> <span data-ttu-id="4587b-179">旨在增强可读性。</span><span class="sxs-lookup"><span data-stu-id="4587b-179">Designed to enhance readability.</span></span> <span data-ttu-id="4587b-180">标准连字包括“fi”、“fl”和“ff”。</span><span class="sxs-lookup"><span data-stu-id="4587b-180">Standard ligatures include "fi", "fl", and "ff".</span></span>  
  
-   <span data-ttu-id="4587b-181">**上下文连字**。</span><span class="sxs-lookup"><span data-stu-id="4587b-181">**Contextual ligatures**.</span></span> <span data-ttu-id="4587b-182">旨在通过在组成连字的字符之间提供更好的联结行为来增强可读性。</span><span class="sxs-lookup"><span data-stu-id="4587b-182">Designed to enhance readability by providing better joining behavior between the characters that make up the ligature.</span></span>  
  
-   <span data-ttu-id="4587b-183">**自由连字**。</span><span class="sxs-lookup"><span data-stu-id="4587b-183">**Discretionary ligatures**.</span></span> <span data-ttu-id="4587b-184">重在修饰性，并非专为可读性而设计。</span><span class="sxs-lookup"><span data-stu-id="4587b-184">Designed to be ornamental, and not specifically designed for readability.</span></span>  
  
-   <span data-ttu-id="4587b-185">**历史连字**。</span><span class="sxs-lookup"><span data-stu-id="4587b-185">**Historical ligatures**.</span></span> <span data-ttu-id="4587b-186">重在历史性，并非专为可读性而设计。</span><span class="sxs-lookup"><span data-stu-id="4587b-186">Designed to be historical, and not specifically designed for readability.</span></span>  
  
 <span data-ttu-id="4587b-187">以下文本显示 Pericles 字体的标准连字字形。</span><span class="sxs-lookup"><span data-stu-id="4587b-187">The following text displays standard ligature glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="4587b-188">![使用 OpenType 标准连字的文本](../../../../docs/framework/wpf/advanced/media/opentypefont04.gif "opentypefont04")</span><span class="sxs-lookup"><span data-stu-id="4587b-188">![Text using OpenType standard ligatures](../../../../docs/framework/wpf/advanced/media/opentypefont04.gif "opentypefont04")</span></span>  
<span data-ttu-id="4587b-189">使用 OpenType 标准连字的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-189">Text using OpenType standard ligatures</span></span>  
  
 <span data-ttu-id="4587b-190">以下标记示例演示如何定义使用的属性的 Pericles 字体的标准连字字形<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-190">The following markup example shows how to define standard ligature glyphs for the Pericles font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#4)]  
  
 <span data-ttu-id="4587b-191">以下文本显示 Pericles 字体的自由连字字形。</span><span class="sxs-lookup"><span data-stu-id="4587b-191">The following text displays discretionary ligature glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="4587b-192">![使用 OpenType 自由连字的文本](../../../../docs/framework/wpf/advanced/media/opentypefont05.gif "opentypefont05")</span><span class="sxs-lookup"><span data-stu-id="4587b-192">![Text using OpenType discretionary ligatures](../../../../docs/framework/wpf/advanced/media/opentypefont05.gif "opentypefont05")</span></span>  
<span data-ttu-id="4587b-193">使用 OpenType 自由连字的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-193">Text using OpenType discretionary ligatures</span></span>  
  
 <span data-ttu-id="4587b-194">以下标记示例演示如何定义使用的属性的 Pericles 字体的自由连字字形<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-194">The following markup example shows how to define discretionary ligature glyphs for the Pericles font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#5)]  
  
 <span data-ttu-id="4587b-195">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中的 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 字体默认启用标准连字。</span><span class="sxs-lookup"><span data-stu-id="4587b-195">By default, [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fonts in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] enable standard ligatures.</span></span> <span data-ttu-id="4587b-196">例如，如果使用 Palatino Linotype 字体，则标准连字“fi”、“ff”和“fl”显示为组合字符字形。</span><span class="sxs-lookup"><span data-stu-id="4587b-196">For example, if you use the Palatino Linotype font, the standard ligatures "fi", "ff", and "fl" appear as a combined character glyph.</span></span> <span data-ttu-id="4587b-197">请注意，每个标准连字的字符对之间彼此相连。</span><span class="sxs-lookup"><span data-stu-id="4587b-197">Notice that the pair of characters for each standard ligature touch each other.</span></span>  
  
 <span data-ttu-id="4587b-198">![使用 OpenType 标准连字的文本](../../../../docs/framework/wpf/advanced/media/opentypefont06.gif "opentypefont06")</span><span class="sxs-lookup"><span data-stu-id="4587b-198">![Text using OpenType standard ligatures](../../../../docs/framework/wpf/advanced/media/opentypefont06.gif "opentypefont06")</span></span>  
<span data-ttu-id="4587b-199">使用 OpenType 标准连字的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-199">Text using OpenType standard ligatures</span></span>  
  
 <span data-ttu-id="4587b-200">但是，可禁用标准连字功能，从而使“ff”等标准连字显示为两个单独的字形，而不显示为一个组合字符字形。</span><span class="sxs-lookup"><span data-stu-id="4587b-200">However, you can disable standard ligature features so that a standard ligature such as "ff" displays as two separate glyphs, rather than as a combined character glyph.</span></span>  
  
 <span data-ttu-id="4587b-201">![文本使用禁用的 OpenType 标准连字](../../../../docs/framework/wpf/advanced/media/opentypefont07.gif "opentypefont07")</span><span class="sxs-lookup"><span data-stu-id="4587b-201">![Text using disabled OpenType standard ligatures](../../../../docs/framework/wpf/advanced/media/opentypefont07.gif "opentypefont07")</span></span>  
<span data-ttu-id="4587b-202">使用禁用的 OpenType 标准连字的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-202">Text using disabled OpenType standard ligatures</span></span>  
  
 <span data-ttu-id="4587b-203">以下标记示例演示如何禁用 Palatino Linotype 字体的使用的属性的标准连字字形<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-203">The following markup example shows how to disable standard ligature glyphs for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#6)]  
  
<a name="swashes"></a>   
## <a name="swashes"></a><span data-ttu-id="4587b-204">花体</span><span class="sxs-lookup"><span data-stu-id="4587b-204">Swashes</span></span>  
 <span data-ttu-id="4587b-205">花体是使用精美修饰的装饰性字形，通常与书法相关。</span><span class="sxs-lookup"><span data-stu-id="4587b-205">Swashes are decorative glyphs that use elaborate ornamentation often associated with calligraphy.</span></span> <span data-ttu-id="4587b-206">以下文本显示 Pescadero 字体的标准和花体字形。</span><span class="sxs-lookup"><span data-stu-id="4587b-206">The following text displays standard and swash glyphs for the Pescadero font.</span></span>  
  
 <span data-ttu-id="4587b-207">![使用 OpenType 标准和花体字形的文本](../../../../docs/framework/wpf/advanced/media/opentypefont08.gif "opentypefont08")</span><span class="sxs-lookup"><span data-stu-id="4587b-207">![Text using OpenType standard and swash glyphs](../../../../docs/framework/wpf/advanced/media/opentypefont08.gif "opentypefont08")</span></span>  
<span data-ttu-id="4587b-208">使用 OpenType 标准和花体连字的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-208">Text using OpenType standard and swash glyphs</span></span>  
  
 <span data-ttu-id="4587b-209">花体通常用作事件公告等简短文章中的修饰元素。</span><span class="sxs-lookup"><span data-stu-id="4587b-209">Swashes are often used as decorative elements in short phrases such as event announcements.</span></span> <span data-ttu-id="4587b-210">以下文本使用花体强调事件名称的大写字母。</span><span class="sxs-lookup"><span data-stu-id="4587b-210">The following text uses swashes to emphasize the capital letters of the name of the event.</span></span>  
  
 <span data-ttu-id="4587b-211">![使用 OpenType 连接形式花体的文本](../../../../docs/framework/wpf/advanced/media/opentypefont09.gif "opentypefont09")</span><span class="sxs-lookup"><span data-stu-id="4587b-211">![Text using OpenType swashes](../../../../docs/framework/wpf/advanced/media/opentypefont09.gif "opentypefont09")</span></span>  
<span data-ttu-id="4587b-212">使用 OpenType 花体的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-212">Text using OpenType swashes</span></span>  
  
 <span data-ttu-id="4587b-213">以下标记示例演示如何定义字体花体，使用的属性<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-213">The following markup example shows how to define swashes for a font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#7)]  
  
### <a name="contextual-swashes"></a><span data-ttu-id="4587b-214">连接形式花体</span><span class="sxs-lookup"><span data-stu-id="4587b-214">Contextual Swashes</span></span>  
 <span data-ttu-id="4587b-215">花体字形的某些组合可能导致文本外观欠佳，例如相邻字母的下行处出现重叠。</span><span class="sxs-lookup"><span data-stu-id="4587b-215">Certain combinations of swash glyphs can cause an unattractive appearance, such as overlapping descenders on adjacent letters.</span></span> <span data-ttu-id="4587b-216">通过连接形式花体，可使用能生成更佳外观的替代花体字形。</span><span class="sxs-lookup"><span data-stu-id="4587b-216">Using a contextual swash allows you to use a substitute swash glyph that produces a better appearance.</span></span> <span data-ttu-id="4587b-217">以下文本显示同一单词应用连接形式花体前后的外观。</span><span class="sxs-lookup"><span data-stu-id="4587b-217">The following text shows the same word before and after a contextual swash is applied.</span></span>  
  
 <span data-ttu-id="4587b-218">![使用 OpenType 花体的文本](../../../../docs/framework/wpf/advanced/media/opentypefont19.gif "OpenTypeFont19")</span><span class="sxs-lookup"><span data-stu-id="4587b-218">![Text using OpenType contextual swashes](../../../../docs/framework/wpf/advanced/media/opentypefont19.gif "OpenTypeFont19")</span></span>  
<span data-ttu-id="4587b-219">使用 OpenType 连接形式花体的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-219">Text using OpenType contextual swashes</span></span>  
  
 <span data-ttu-id="4587b-220">以下标记示例演示如何定义 Pescadero 字体使用的属性的上下文花体<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-220">The following markup example shows how to define a contextual swash for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet16)]  
  
<a name="alternates"></a>   
## <a name="alternates"></a><span data-ttu-id="4587b-221">备用项</span><span class="sxs-lookup"><span data-stu-id="4587b-221">Alternates</span></span>  
 <span data-ttu-id="4587b-222">备用项是可替代标准字形的字形。</span><span class="sxs-lookup"><span data-stu-id="4587b-222">Alternates are glyphs that can be substituted for a standard glyph.</span></span> [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] <span data-ttu-id="4587b-223">字体（例如以下示例中使用的 Pericles 字体）可包含用于塑造不同文本外观的备用字形。</span><span class="sxs-lookup"><span data-stu-id="4587b-223">fonts, such as the Pericles font used in the following examples, can contain alternate glyphs that you can use to create different appearances for text.</span></span> <span data-ttu-id="4587b-224">以下文本显示 Pericles 字体的标准字形。</span><span class="sxs-lookup"><span data-stu-id="4587b-224">The following text displays standard glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="4587b-225">![使用 OpenType 标准字形的文本](../../../../docs/framework/wpf/advanced/media/opentypefont01.gif "opentypefont01")</span><span class="sxs-lookup"><span data-stu-id="4587b-225">![Text using OpenType standard glyphs](../../../../docs/framework/wpf/advanced/media/opentypefont01.gif "opentypefont01")</span></span>  
<span data-ttu-id="4587b-226">使用 OpenType 标准字形的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-226">Text using OpenType standard glyphs</span></span>  
  
 <span data-ttu-id="4587b-227">Pericles [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 字体包含其他字形，可为标准自行集提供样式备用项。</span><span class="sxs-lookup"><span data-stu-id="4587b-227">The Pericles [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] font contains additional glyphs that provide stylistic alternates to the standard set of glyphs.</span></span> <span data-ttu-id="4587b-228">以下文本显示样式备用字形。</span><span class="sxs-lookup"><span data-stu-id="4587b-228">The following text displays stylistic alternate glyphs.</span></span>  
  
 <span data-ttu-id="4587b-229">![使用 OpenType 样式备用字形的文本](../../../../docs/framework/wpf/advanced/media/opentypefont02.gif "opentypefont02")</span><span class="sxs-lookup"><span data-stu-id="4587b-229">![Text using OpenType stylistic alternate glyphs](../../../../docs/framework/wpf/advanced/media/opentypefont02.gif "opentypefont02")</span></span>  
<span data-ttu-id="4587b-230">使用 OpenType 样式备用标志符号的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-230">Text using OpenType stylistic alternate glyphs</span></span>  
  
 <span data-ttu-id="4587b-231">以下标记示例演示如何定义 Pericles 字体的使用的属性的样式备用字形<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-231">The following markup example shows how to define stylistic alternate glyphs for the Pericles font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#2)]  
  
 <span data-ttu-id="4587b-232">以下文本显示 Pericles 字体的几种其他样式备用字形。</span><span class="sxs-lookup"><span data-stu-id="4587b-232">The following text displays several other stylistic alternate glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="4587b-233">![使用 OpenType 样式备用字形的文本](../../../../docs/framework/wpf/advanced/media/opentypefont03.gif "opentypefont03")</span><span class="sxs-lookup"><span data-stu-id="4587b-233">![Text using OpenType stylistic alternate glyphs](../../../../docs/framework/wpf/advanced/media/opentypefont03.gif "opentypefont03")</span></span>  
<span data-ttu-id="4587b-234">使用 OpenType 样式备用标志符号的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-234">Text using OpenType stylistic alternate glyphs</span></span>  
  
 <span data-ttu-id="4587b-235">以下标记示例演示如何定义其他样式备用字形。</span><span class="sxs-lookup"><span data-stu-id="4587b-235">The following markup example shows how to define these other stylistic alternate glyphs.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#3)]  
  
### <a name="random-contextual-alternates"></a><span data-ttu-id="4587b-236">随机备用连接形式</span><span class="sxs-lookup"><span data-stu-id="4587b-236">Random Contextual Alternates</span></span>  
 <span data-ttu-id="4587b-237">随机备用连接形式为单个字符提供多种备用字形。</span><span class="sxs-lookup"><span data-stu-id="4587b-237">Random contextual alternates provide multiple substitute glyphs for a single character.</span></span> <span data-ttu-id="4587b-238">实现脚本类型字体时，此功能可通过使用一组随机选择的外观稍有差异的字形来模拟手写内容。</span><span class="sxs-lookup"><span data-stu-id="4587b-238">When implemented with script-type fonts, this feature can simulate handwriting by using of a set of randomly chosen glyphs with slight differences in appearance.</span></span> <span data-ttu-id="4587b-239">以下文本使用 Lindsey 字体的随机备用连接形式。</span><span class="sxs-lookup"><span data-stu-id="4587b-239">The following text uses random contextual alternates for the Lindsey font.</span></span> <span data-ttu-id="4587b-240">请注意字母“a”外观稍有变化</span><span class="sxs-lookup"><span data-stu-id="4587b-240">Notice that the letter "a" varies slightly in appearance</span></span>  
  
 <span data-ttu-id="4587b-241">![使用 OpenType 随机备用连接形式的文本](../../../../docs/framework/wpf/advanced/media/opentypefont23.gif "OpenTypeFont23")</span><span class="sxs-lookup"><span data-stu-id="4587b-241">![Text using OpenType random contextual alternates](../../../../docs/framework/wpf/advanced/media/opentypefont23.gif "OpenTypeFont23")</span></span>  
<span data-ttu-id="4587b-242">使用 OpenType 随机备用连接形式的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-242">Text using OpenType random contextual alternates</span></span>  
  
 <span data-ttu-id="4587b-243">以下标记示例演示如何定义 Lindsey 字体使用的属性的随机备用<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-243">The following markup example shows how to define random contextual alternates for the Lindsey font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet20)]  
  
### <a name="historical-forms"></a><span data-ttu-id="4587b-244">历史形式</span><span class="sxs-lookup"><span data-stu-id="4587b-244">Historical Forms</span></span>  
 <span data-ttu-id="4587b-245">历史形式指过去常见的版式约定。</span><span class="sxs-lookup"><span data-stu-id="4587b-245">Historical forms are typographic conventions that were common in the past.</span></span> <span data-ttu-id="4587b-246">以下文本使用 Palatino Linotype 字体的一种历史字形形式显示短语“Boston, Massachusetts”。</span><span class="sxs-lookup"><span data-stu-id="4587b-246">The following text displays the phrase, "Boston, Massachusetts", using an historical form of glyphs for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="4587b-247">![使用 OpenType 历史形式的文本](../../../../docs/framework/wpf/advanced/media/opentypefont10.gif "opentypefont10")</span><span class="sxs-lookup"><span data-stu-id="4587b-247">![Text using OpenType historical forms](../../../../docs/framework/wpf/advanced/media/opentypefont10.gif "opentypefont10")</span></span>  
<span data-ttu-id="4587b-248">使用 OpenType 历史形式的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-248">Text using OpenType historical forms</span></span>  
  
 <span data-ttu-id="4587b-249">以下标记示例演示如何定义 Palatino Linotype 字体的使用的属性的历史记录格式<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-249">The following markup example shows how to define historical forms for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#8)]  
  
<a name="numerical_styles"></a>   
## <a name="numerical-styles"></a><span data-ttu-id="4587b-250">数字样式</span><span class="sxs-lookup"><span data-stu-id="4587b-250">Numerical Styles</span></span>  
 <span data-ttu-id="4587b-251">OpenType 字体支持多种可用于文本中数值的功能。</span><span class="sxs-lookup"><span data-stu-id="4587b-251">OpenType fonts support a large number of features that can be used with numerical values in text.</span></span>  
  
### <a name="fractions"></a><span data-ttu-id="4587b-252">分数</span><span class="sxs-lookup"><span data-stu-id="4587b-252">Fractions</span></span>  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] <span data-ttu-id="4587b-253">字体支持多种分数样式，包括横式分数和竖式分数。</span><span class="sxs-lookup"><span data-stu-id="4587b-253">fonts support styles for fractions, including slashed and stacked.</span></span>  
  
 <span data-ttu-id="4587b-254">以下文本显示 Palatino Linotype 字体的分数样式。</span><span class="sxs-lookup"><span data-stu-id="4587b-254">The following text displays fraction styles for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="4587b-255">![文本使用 OpenType 横式分数和竖式](../../../../docs/framework/wpf/advanced/media/opentypefont12.gif "opentypefont12")</span><span class="sxs-lookup"><span data-stu-id="4587b-255">![Text using OpenType slashed and stacked fractions](../../../../docs/framework/wpf/advanced/media/opentypefont12.gif "opentypefont12")</span></span>  
<span data-ttu-id="4587b-256">使用 OpenType 横式分数和竖式分数的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-256">Text using OpenType slashed and stacked fractions</span></span>  
  
 <span data-ttu-id="4587b-257">以下标记示例演示如何定义 Palatino Linotype 字体的使用的属性的分数样式<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-257">The following markup example shows how to define fraction styles for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#10)]  
  
### <a name="old-style-numerals"></a><span data-ttu-id="4587b-258">旧样式数字</span><span class="sxs-lookup"><span data-stu-id="4587b-258">Old Style Numerals</span></span>  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] <span data-ttu-id="4587b-259">字体支持旧样式数字格式。</span><span class="sxs-lookup"><span data-stu-id="4587b-259">fonts support an old style numeral format.</span></span> <span data-ttu-id="4587b-260">此格式对于显示不再是标准样式的数字非常有用。</span><span class="sxs-lookup"><span data-stu-id="4587b-260">This format is useful for displaying numerals in styles that are no longer standard.</span></span> <span data-ttu-id="4587b-261">以下文本以 Palatino Linotype 字体的标准和旧样式数字格式显示 18 世纪日期。</span><span class="sxs-lookup"><span data-stu-id="4587b-261">The following text displays an 18th century date in standard and old style numeral formats for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="4587b-262">![使用 OpenType 旧样式数字的文本](../../../../docs/framework/wpf/advanced/media/opentypefont24.gif "OpenTypeFont24")</span><span class="sxs-lookup"><span data-stu-id="4587b-262">![Text using OpenType old style numerals](../../../../docs/framework/wpf/advanced/media/opentypefont24.gif "OpenTypeFont24")</span></span>  
<span data-ttu-id="4587b-263">使用 OpenType 旧样式数字的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-263">Text using OpenType old style numerals</span></span>  
  
 <span data-ttu-id="4587b-264">以下文本显示 Palatino Linotype 字体的标准数字，后跟旧样式数字。</span><span class="sxs-lookup"><span data-stu-id="4587b-264">The following text displays standard numerals for the Palatino Linotype font, followed by old style numerals.</span></span>  
  
 <span data-ttu-id="4587b-265">![使用 OpenType 旧样式数字集的文本](../../../../docs/framework/wpf/advanced/media/opentypefont13.gif "opentypefont13")</span><span class="sxs-lookup"><span data-stu-id="4587b-265">![Text using OpenType old style numeral sets](../../../../docs/framework/wpf/advanced/media/opentypefont13.gif "opentypefont13")</span></span>  
<span data-ttu-id="4587b-266">使用 OpenType 旧样式数字集的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-266">Text using OpenType old style numeral sets</span></span>  
  
 <span data-ttu-id="4587b-267">以下标记示例演示如何定义 Palatino Linotype 字体的使用的属性的旧样式数字<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-267">The following markup example shows how to define old style numerals for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#11)]  
  
### <a name="proportional-and-tabular-figures"></a><span data-ttu-id="4587b-268">比例数字和表格式数字</span><span class="sxs-lookup"><span data-stu-id="4587b-268">Proportional and Tabular Figures</span></span>  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] <span data-ttu-id="4587b-269">字体支持比例数字和表格式数字功能，可在使用数字时控制宽度对齐。</span><span class="sxs-lookup"><span data-stu-id="4587b-269">fonts support a proportional and tabular figure feature to control the alignment of widths when using numerals.</span></span> <span data-ttu-id="4587b-270">比例数字将每个数字视为具有不同的宽度—“1”窄于“5”。</span><span class="sxs-lookup"><span data-stu-id="4587b-270">Proportional figures treat each numeral as having a different width—"1" is narrower than "5".</span></span> <span data-ttu-id="4587b-271">表格式数字被视为宽度相等的数字，因此它们可垂直对齐，从而增强财务类型信息的可读性。</span><span class="sxs-lookup"><span data-stu-id="4587b-271">Tabular figures are treated as equal-width numerals so that they align vertically, which increases the readability of financial type information.</span></span>  
  
 <span data-ttu-id="4587b-272">以下文本使用 Miramonte 字体显示第一列中的两个表格式数字。</span><span class="sxs-lookup"><span data-stu-id="4587b-272">The following text displays two proportional figures in the first column using the Miramonte font.</span></span> <span data-ttu-id="4587b-273">请注意数字“5”和“1”之间的宽度差异。</span><span class="sxs-lookup"><span data-stu-id="4587b-273">Note the difference in width between the numerals "5" and "1".</span></span> <span data-ttu-id="4587b-274">第二列显示相同的两个数值，并通过使用表格式数字功能调整其宽度。</span><span class="sxs-lookup"><span data-stu-id="4587b-274">The second column shows the same two numeric values with the widths adjusted by using the tabular figure feature.</span></span>  
  
 <span data-ttu-id="4587b-275">![使用 OpenType 比例数字和表格式数字的文本](../../../../docs/framework/wpf/advanced/media/opentypefont22.gif "OpenTypeFont22")</span><span class="sxs-lookup"><span data-stu-id="4587b-275">![Text using OpenType proportional & tabular figures](../../../../docs/framework/wpf/advanced/media/opentypefont22.gif "OpenTypeFont22")</span></span>  
<span data-ttu-id="4587b-276">使用 OpenType 比例数字和表格式数字的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-276">Text using OpenType proportional and tabular figures</span></span>  
  
 <span data-ttu-id="4587b-277">以下标记示例演示如何定义比例数字和表格式数字 Miramonte 字体使用的属性的<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-277">The following markup example shows how to define proportional and tabular figures for the Miramonte font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet19)]  
  
### <a name="slashed-zero"></a><span data-ttu-id="4587b-278">斜线零</span><span class="sxs-lookup"><span data-stu-id="4587b-278">Slashed Zero</span></span>  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] <span data-ttu-id="4587b-279">字体支持斜线零数字格式来强调字母“O”和数字“0”之间的差异。</span><span class="sxs-lookup"><span data-stu-id="4587b-279">fonts support a slashed zero numeral format to emphasize the difference between the letter "O" and the numeral "0".</span></span> <span data-ttu-id="4587b-280">斜线零数字通常用于财务和商务信息中的标识符。</span><span class="sxs-lookup"><span data-stu-id="4587b-280">The slashed zero numeral is often used for identifiers in financial and business information.</span></span>  
  
 <span data-ttu-id="4587b-281">以下文本显示使用 Miramonte 字体的订单标识符。</span><span class="sxs-lookup"><span data-stu-id="4587b-281">The following text displays a sample order identifier using the Miramonte font.</span></span> <span data-ttu-id="4587b-282">第一行使用标准数字。</span><span class="sxs-lookup"><span data-stu-id="4587b-282">The first line uses standard numerals.</span></span> <span data-ttu-id="4587b-283">第二行使用斜线零数字，以便更易于与大写字母“O”进行区分。</span><span class="sxs-lookup"><span data-stu-id="4587b-283">The second line used slashed zero numerals to provide better contrast with the uppercase "O" letter.</span></span>  
  
 <span data-ttu-id="4587b-284">![文本使用 OpenType 斜线零数字](../../../../docs/framework/wpf/advanced/media/opentypefont17.gif "OpenTypeFont17")</span><span class="sxs-lookup"><span data-stu-id="4587b-284">![Text using OpenType slashed zero numerals](../../../../docs/framework/wpf/advanced/media/opentypefont17.gif "OpenTypeFont17")</span></span>  
<span data-ttu-id="4587b-285">使用 OpenType 斜线零数字的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-285">Text using OpenType slashed zero numerals</span></span>  
  
 <span data-ttu-id="4587b-286">以下标记示例演示如何定义使用的属性的 Miramonte 字体的斜线零数字<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-286">The following markup example shows how to define slashed zero numerals for the Miramonte font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet15)]  
  
<a name="typography_class"></a>   
## <a name="typography-class"></a><span data-ttu-id="4587b-287">版式类</span><span class="sxs-lookup"><span data-stu-id="4587b-287">Typography Class</span></span>  
 <span data-ttu-id="4587b-288"><xref:System.Windows.Documents.Typography>对象公开的功能集的[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]字体支持。</span><span class="sxs-lookup"><span data-stu-id="4587b-288">The <xref:System.Windows.Documents.Typography> object exposes the set of features that an [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] font supports.</span></span> <span data-ttu-id="4587b-289">通过设置的属性<xref:System.Windows.Documents.Typography>在标记中，您可以轻松地编写文档，充分利用[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]功能。</span><span class="sxs-lookup"><span data-stu-id="4587b-289">By setting the properties of <xref:System.Windows.Documents.Typography> in markup, you can easily author documents that take advantage of [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] features.</span></span>  
  
 <span data-ttu-id="4587b-290">以下文本显示 Pescadero 字体的标准大写字母，其后接样式为“SmallCaps”和“AllSmallCaps”的字母。</span><span class="sxs-lookup"><span data-stu-id="4587b-290">The following text displays standard capital letters for the Pescadero font, followed by the letters styled as "SmallCaps" and "AllSmallCaps".</span></span> <span data-ttu-id="4587b-291">本例中，对所有三个单词均使用相同的字体大小。</span><span class="sxs-lookup"><span data-stu-id="4587b-291">In this case, the same font size is used for all three words.</span></span>  
  
 <span data-ttu-id="4587b-292">![使用 OpenType 大写字母的文本](../../../../docs/framework/wpf/advanced/media/opentypefont11.gif "opentypefont11")</span><span class="sxs-lookup"><span data-stu-id="4587b-292">![Text using OpenType capitals](../../../../docs/framework/wpf/advanced/media/opentypefont11.gif "opentypefont11")</span></span>  
<span data-ttu-id="4587b-293">使用 OpenType 大写字母的文本</span><span class="sxs-lookup"><span data-stu-id="4587b-293">Text using OpenType capitals</span></span>  
  
 <span data-ttu-id="4587b-294">以下标记示例演示如何定义使用的属性的 Pescadero 字体的大写字母<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-294">The following markup example shows how to define capitals for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span> <span data-ttu-id="4587b-295">使用“SmallCaps”格式时会忽略任何前导大写字母。</span><span class="sxs-lookup"><span data-stu-id="4587b-295">When the "SmallCaps" format is used, any leading capital letter is ignored.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
 <span data-ttu-id="4587b-296">以下代码示例完成与先前的标记事例相同的任务。</span><span class="sxs-lookup"><span data-stu-id="4587b-296">The following code example accomplishes the same task as the previous markup example.</span></span>  
  
 [!code-csharp[TypographyCodeSnippets#TypographyCodeSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TypographyCodeSnippets/CSharp/Page1.xaml.cs#typographycodesnippet1)]
 [!code-vb[TypographyCodeSnippets#TypographyCodeSnippet1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TypographyCodeSnippets/visualbasic/page1.xaml.vb#typographycodesnippet1)]  
  
### <a name="typography-class-properties"></a><span data-ttu-id="4587b-297">版式类属性</span><span class="sxs-lookup"><span data-stu-id="4587b-297">Typography Class Properties</span></span>  
 <span data-ttu-id="4587b-298">下表列出了属性、 值和默认设置<xref:System.Windows.Documents.Typography>对象。</span><span class="sxs-lookup"><span data-stu-id="4587b-298">The following table lists the properties, values, and default settings of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
|<span data-ttu-id="4587b-299">属性</span><span class="sxs-lookup"><span data-stu-id="4587b-299">Property</span></span>|<span data-ttu-id="4587b-300">值</span><span class="sxs-lookup"><span data-stu-id="4587b-300">Value(s)</span></span>|<span data-ttu-id="4587b-301">默认值</span><span class="sxs-lookup"><span data-stu-id="4587b-301">Default Value</span></span>|  
|--------------|----------------|-------------------|  
|<xref:System.Windows.Documents.Typography.AnnotationAlternates%2A>|<span data-ttu-id="4587b-302">数值 - 字节</span><span class="sxs-lookup"><span data-stu-id="4587b-302">Numeric value - byte</span></span>|<span data-ttu-id="4587b-303">0</span><span class="sxs-lookup"><span data-stu-id="4587b-303">0</span></span>|  
|<xref:System.Windows.Documents.Typography.Capitals%2A>|<span data-ttu-id="4587b-304"><xref:System.Windows.FontCapitals.AllPetiteCaps> &#124; <xref:System.Windows.FontCapitals.AllSmallCaps> &#124; <xref:System.Windows.FontCapitals.Normal> &#124; <xref:System.Windows.FontCapitals.PetiteCaps> &#124; <xref:System.Windows.FontCapitals.SmallCaps> &#124; <xref:System.Windows.FontCapitals.Titling> &#124; <xref:System.Windows.FontCapitals.Unicase></span><span class="sxs-lookup"><span data-stu-id="4587b-304"><xref:System.Windows.FontCapitals.AllPetiteCaps> &#124; <xref:System.Windows.FontCapitals.AllSmallCaps> &#124; <xref:System.Windows.FontCapitals.Normal> &#124; <xref:System.Windows.FontCapitals.PetiteCaps> &#124; <xref:System.Windows.FontCapitals.SmallCaps> &#124; <xref:System.Windows.FontCapitals.Titling> &#124; <xref:System.Windows.FontCapitals.Unicase></span></span>|<xref:System.Windows.FontCapitals.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.CapitalSpacing%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.CaseSensitiveForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.ContextualAlternates%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualSwashes%2A>|<span data-ttu-id="4587b-305">数值 - 字节</span><span class="sxs-lookup"><span data-stu-id="4587b-305">Numeric value - byte</span></span>|<span data-ttu-id="4587b-306">0</span><span class="sxs-lookup"><span data-stu-id="4587b-306">0</span></span>|  
|<xref:System.Windows.Documents.Typography.DiscretionaryLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianExpertForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianLanguage%2A>|<span data-ttu-id="4587b-307"><xref:System.Windows.FontEastAsianLanguage.HojoKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis04> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis78> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis83> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis90> &#124; <xref:System.Windows.FontEastAsianLanguage.NlcKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Normal> &#124; <xref:System.Windows.FontEastAsianLanguage.Simplified> &#124; <xref:System.Windows.FontEastAsianLanguage.Traditional> &#124; <xref:System.Windows.FontEastAsianLanguage.TraditionalNames></span><span class="sxs-lookup"><span data-stu-id="4587b-307"><xref:System.Windows.FontEastAsianLanguage.HojoKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis04> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis78> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis83> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis90> &#124; <xref:System.Windows.FontEastAsianLanguage.NlcKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Normal> &#124; <xref:System.Windows.FontEastAsianLanguage.Simplified> &#124; <xref:System.Windows.FontEastAsianLanguage.Traditional> &#124; <xref:System.Windows.FontEastAsianLanguage.TraditionalNames></span></span>|<xref:System.Windows.FontEastAsianLanguage.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.EastAsianWidths%2A>|<span data-ttu-id="4587b-308"><xref:System.Windows.FontEastAsianWidths.Full> &#124; <xref:System.Windows.FontEastAsianWidths.Half> &#124; <xref:System.Windows.FontEastAsianWidths.Normal> &#124; <xref:System.Windows.FontEastAsianWidths.Proportional> &#124; <xref:System.Windows.FontEastAsianWidths.Quarter> &#124; <xref:System.Windows.FontEastAsianWidths.Third></span><span class="sxs-lookup"><span data-stu-id="4587b-308"><xref:System.Windows.FontEastAsianWidths.Full> &#124; <xref:System.Windows.FontEastAsianWidths.Half> &#124; <xref:System.Windows.FontEastAsianWidths.Normal> &#124; <xref:System.Windows.FontEastAsianWidths.Proportional> &#124; <xref:System.Windows.FontEastAsianWidths.Quarter> &#124; <xref:System.Windows.FontEastAsianWidths.Third></span></span>|<xref:System.Windows.FontEastAsianWidths.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.Fraction%2A>|<span data-ttu-id="4587b-309"><xref:System.Windows.FontFraction.Normal> &#124; <xref:System.Windows.FontFraction.Slashed> &#124; <xref:System.Windows.FontFraction.Stacked></span><span class="sxs-lookup"><span data-stu-id="4587b-309"><xref:System.Windows.FontFraction.Normal> &#124; <xref:System.Windows.FontFraction.Slashed> &#124; <xref:System.Windows.FontFraction.Stacked></span></span>|<xref:System.Windows.FontFraction.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.HistoricalForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.HistoricalLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Kerning%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.MathematicalGreek%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.NumeralAlignment%2A>|<span data-ttu-id="4587b-310"><xref:System.Windows.FontNumeralAlignment.Normal> &#124; <xref:System.Windows.FontNumeralAlignment.Proportional> &#124; <xref:System.Windows.FontNumeralAlignment.Tabular></span><span class="sxs-lookup"><span data-stu-id="4587b-310"><xref:System.Windows.FontNumeralAlignment.Normal> &#124; <xref:System.Windows.FontNumeralAlignment.Proportional> &#124; <xref:System.Windows.FontNumeralAlignment.Tabular></span></span>|<xref:System.Windows.FontNumeralAlignment.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.NumeralStyle%2A>|<xref:System.Boolean>|<xref:System.Windows.FontNumeralStyle.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.SlashedZero%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StandardLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.StandardSwashes%2A>|<span data-ttu-id="4587b-311">数值 - 字节</span><span class="sxs-lookup"><span data-stu-id="4587b-311">numeric value – byte</span></span>|<span data-ttu-id="4587b-312">0</span><span class="sxs-lookup"><span data-stu-id="4587b-312">0</span></span>|  
|<xref:System.Windows.Documents.Typography.StylisticAlternates%2A>|<span data-ttu-id="4587b-313">数值 - 字节</span><span class="sxs-lookup"><span data-stu-id="4587b-313">numeric value – byte</span></span>|<span data-ttu-id="4587b-314">0</span><span class="sxs-lookup"><span data-stu-id="4587b-314">0</span></span>|  
|<xref:System.Windows.Documents.Typography.StylisticSet1%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet2%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet3%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet4%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet5%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet6%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet7%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet8%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet9%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet10%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet11%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet12%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet13%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet14%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet15%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet16%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet17%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet18%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet19%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet20%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Variants%2A>|<span data-ttu-id="4587b-315"><xref:System.Windows.FontVariants.Inferior> &#124; <xref:System.Windows.FontVariants.Normal> &#124; <xref:System.Windows.FontVariants.Ordinal> &#124; <xref:System.Windows.FontVariants.Ruby> &#124; <xref:System.Windows.FontVariants.Subscript> &#124; <xref:System.Windows.FontVariants.Superscript></span><span class="sxs-lookup"><span data-stu-id="4587b-315"><xref:System.Windows.FontVariants.Inferior> &#124; <xref:System.Windows.FontVariants.Normal> &#124; <xref:System.Windows.FontVariants.Ordinal> &#124; <xref:System.Windows.FontVariants.Ruby> &#124; <xref:System.Windows.FontVariants.Subscript> &#124; <xref:System.Windows.FontVariants.Superscript></span></span>|<xref:System.Windows.FontVariants.Normal?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="4587b-316">请参阅</span><span class="sxs-lookup"><span data-stu-id="4587b-316">See also</span></span>
- <xref:System.Windows.Documents.Typography>
- [<span data-ttu-id="4587b-317">OpenType 规范</span><span class="sxs-lookup"><span data-stu-id="4587b-317">OpenType Specification</span></span>](https://go.microsoft.com/fwlink/?LinkId=96731)
- [<span data-ttu-id="4587b-318">WPF 中的版式</span><span class="sxs-lookup"><span data-stu-id="4587b-318">Typography in WPF</span></span>](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)
- [<span data-ttu-id="4587b-319">示例 OpenType 字体包</span><span class="sxs-lookup"><span data-stu-id="4587b-319">Sample OpenType Font Pack</span></span>](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md)
- [<span data-ttu-id="4587b-320">将字体与应用程序一起打包</span><span class="sxs-lookup"><span data-stu-id="4587b-320">Packaging Fonts with Applications</span></span>](../../../../docs/framework/wpf/advanced/packaging-fonts-with-applications.md)
