---
title: WPF 的全球化
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], international user interface
- XAML [WPF], globalization
- international user interface [WPF], XAML
- globalization [WPF]
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
ms.openlocfilehash: 9a08fdeaa3517b1483af3f9958ad2db1c64648b8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62031327"
---
# <a name="globalization-for-wpf"></a><span data-ttu-id="d6b1b-102">WPF 的全球化</span><span class="sxs-lookup"><span data-stu-id="d6b1b-102">Globalization for WPF</span></span>
<span data-ttu-id="d6b1b-103">本主题介绍你应注意的编写时的问题[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]全球市场的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-103">This topic introduces issues that you should be aware of when writing [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applications for the global market.</span></span> <span data-ttu-id="d6b1b-104">全球化编程元素中定义[!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)]在`System.Globalization`。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-104">The globalization programming elements are defined in [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] in `System.Globalization`.</span></span>

<a name="xaml_globalization"></a>
## <a name="xaml-globalization"></a><span data-ttu-id="d6b1b-105">XAML 全球化</span><span class="sxs-lookup"><span data-stu-id="d6b1b-105">XAML Globalization</span></span>
 [!INCLUDE[TLA#tla_xaml#initcap](../../../../includes/tlasharptla-xamlsharpinitcap-md.md)] <span data-ttu-id="d6b1b-106">基于[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]并充分利用中定义的全球化支持[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]规范。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-106">is based on [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] and takes advantage of the globalization support defined in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] specification.</span></span> <span data-ttu-id="d6b1b-107">以下部分介绍一些[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]应注意的功能。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-107">The following sections describe some [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] features that you should be aware of.</span></span>

<a name="char_reference"></a>
### <a name="character-references"></a><span data-ttu-id="d6b1b-108">字符引用</span><span class="sxs-lookup"><span data-stu-id="d6b1b-108">Character References</span></span>
<span data-ttu-id="d6b1b-109">字符引用提供了特定的 UTF16 代码单元[!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]字符其表示时，以十进制或十六进制。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-109">A character reference gives the UTF16 code unit of the particular [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] character it represents, in either decimal or hexadecimal.</span></span> <span data-ttu-id="d6b1b-110">下面的示例演示十进制字符引用科普特语大写字母 HORI 或 Ϩ:</span><span class="sxs-lookup"><span data-stu-id="d6b1b-110">The following example shows a decimal character reference for the COPTIC CAPITAL LETTER HORI, or 'Ϩ':</span></span>

```
&#1000;
```

<span data-ttu-id="d6b1b-111">下面的示例演示十六进制字符引用。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-111">The following example shows a hexadecimal character reference.</span></span> <span data-ttu-id="d6b1b-112">请注意，它具有**x**十六进制数字的前面。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-112">Notice that it has an **x** in front of the hexadecimal number.</span></span>

```
&#x3E8;
```

<a name="encoding"></a>
### <a name="encoding"></a><span data-ttu-id="d6b1b-113">编码</span><span class="sxs-lookup"><span data-stu-id="d6b1b-113">Encoding</span></span>
 <span data-ttu-id="d6b1b-114">支持的编码[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]都[!INCLUDE[TLA#tla_ascii](../../../../includes/tlasharptla-ascii-md.md)]， [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] UTF-16 和 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-114">The encoding supported by [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] are [!INCLUDE[TLA#tla_ascii](../../../../includes/tlasharptla-ascii-md.md)], [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] UTF-16, and UTF-8.</span></span> <span data-ttu-id="d6b1b-115">编码语句位于开头[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文档。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-115">The encoding statement is at the beginning of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] document.</span></span> <span data-ttu-id="d6b1b-116">如果不存在编码特性，并且没有任何字节顺序，则分析器默认为 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-116">If no encoding attribute exists and there is no byte-order, the parser defaults to UTF-8.</span></span> <span data-ttu-id="d6b1b-117">UTF-8 和 UTF-16 都是首选编码。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-117">UTF-8 and UTF-16 are the preferred encodings.</span></span> <span data-ttu-id="d6b1b-118">不支持 UTF-7。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-118">UTF-7 is not supported.</span></span> <span data-ttu-id="d6b1b-119">下面的示例演示如何指定 utf-8 编码中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文件。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-119">The following example demonstrates how to specify a UTF-8 encoding in a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.</span></span>

```
?xml encoding="UTF-8"?
```

<a name="lang_attrib"></a>
### <a name="language-attribute"></a><span data-ttu-id="d6b1b-120">语言特性</span><span class="sxs-lookup"><span data-stu-id="d6b1b-120">Language Attribute</span></span>
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="d6b1b-121">使用[xml: lang](../../xaml-services/xml-lang-handling-in-xaml.md)来表示一个元素的 language 特性。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-121">uses [xml:lang](../../xaml-services/xml-lang-handling-in-xaml.md) to represent the language attribute of an element.</span></span>  <span data-ttu-id="d6b1b-122">若要充分利用<xref:System.Globalization.CultureInfo>类，语言特性值需要是一个预定义的区域性名称的<xref:System.Globalization.CultureInfo>。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-122">To take advantage of the <xref:System.Globalization.CultureInfo> class, the language attribute value needs to be one of the culture names predefined by <xref:System.Globalization.CultureInfo>.</span></span> <span data-ttu-id="d6b1b-123">[xml:lang](../../xaml-services/xml-lang-handling-in-xaml.md) 在元素树中可继承（可按 XML 规则继承，但并不一定这样继承，因为存在依赖属性继承）；在未明确赋值的情况下，其默认值为空字符串。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-123">[xml:lang](../../xaml-services/xml-lang-handling-in-xaml.md) is inheritable in the element tree (by XML rules, not necessarily because of dependency property inheritance) and its default value is an empty string if it is not assigned explicitly.</span></span>

 <span data-ttu-id="d6b1b-124">语言特性对指定方言非常有用。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-124">The language attribute is very useful for specifying dialects.</span></span> <span data-ttu-id="d6b1b-125">例如，法语在法国、魁北克、比利时和瑞士的拼写、词汇和发音各不相同。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-125">For example, French has different spelling, vocabulary, and pronunciation in France, Quebec, Belgium, and Switzerland.</span></span> <span data-ttu-id="d6b1b-126">中文、 日语和朝鲜语还共享中的代码点[!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)]，但表意文字字形不同，并且它们使用完全不同的字体。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-126">Also Chinese, Japanese, and Korean share code points in [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], but the ideographic shapes are different and they use totally different fonts.</span></span>

 <span data-ttu-id="d6b1b-127">以下[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]的示例使用`fr-CA`语言特性指定加拿大法语。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-127">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example uses the `fr-CA` language attribute to specify Canadian French.</span></span>

```xml
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>
```

<a name="unicode"></a>
### <a name="unicode"></a><span data-ttu-id="d6b1b-128">Unicode</span><span class="sxs-lookup"><span data-stu-id="d6b1b-128">Unicode</span></span>
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="d6b1b-129">支持所有[!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)]功能，包括代理项。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-129">supports all [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] features including surrogates.</span></span> <span data-ttu-id="d6b1b-130">只要将字符集可以映射到[!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)]，它受支持。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-130">As long as the character set can be mapped to [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], it is supported.</span></span> <span data-ttu-id="d6b1b-131">例如，GB18030 中引入了某些可映射到中文、日语和朝鲜语 (CFK) 扩展 A 和 B 以及代理项对的字符，因此完全受支持。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-131">For example, GB18030 introduces some characters that are mapped to the Chinese, Japanese, and Korean (CFK) extension A and B and surrogate pairs, therefore it is fully supported.</span></span> <span data-ttu-id="d6b1b-132">一个[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序可以使用<xref:System.Globalization.StringInfo>操作而无需知道其是否具有代理项对或组合字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-132">A [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application can use <xref:System.Globalization.StringInfo> to manipulate strings without understanding whether they have surrogate pairs or combining characters.</span></span>

<a name="design_intl_ui_with_xaml"></a>
## <a name="designing-an-international-user-interface-with-xaml"></a><span data-ttu-id="d6b1b-133">使用 XAML 设计国际用户界面</span><span class="sxs-lookup"><span data-stu-id="d6b1b-133">Designing an International User Interface with XAML</span></span>
 <span data-ttu-id="d6b1b-134">本部分介绍[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]编写的应用程序时应考虑的功能。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-134">This section describes [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] features that you should consider when writing an application.</span></span>

<a name="intl_text"></a>
### <a name="international-text"></a><span data-ttu-id="d6b1b-135">国际化文本</span><span class="sxs-lookup"><span data-stu-id="d6b1b-135">International Text</span></span>
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="d6b1b-136">提供了有关所有受支持的 Microsoft.NET Framework 书写系统的内置处理。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-136">includes built-in processing for all Microsoft .NET Framework supported writing systems.</span></span>

 <span data-ttu-id="d6b1b-137">目前支持以下脚本：</span><span class="sxs-lookup"><span data-stu-id="d6b1b-137">The following scripts are currently supported:</span></span>

- <span data-ttu-id="d6b1b-138">阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-138">Arabic</span></span>

- <span data-ttu-id="d6b1b-139">孟加拉语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-139">Bengali</span></span>

- <span data-ttu-id="d6b1b-140">梵文</span><span class="sxs-lookup"><span data-stu-id="d6b1b-140">Devanagari</span></span>

- <span data-ttu-id="d6b1b-141">西里尔文</span><span class="sxs-lookup"><span data-stu-id="d6b1b-141">Cyrillic</span></span>

- <span data-ttu-id="d6b1b-142">希腊语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-142">Greek</span></span>

- <span data-ttu-id="d6b1b-143">古吉拉特语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-143">Gujarati</span></span>

- <span data-ttu-id="d6b1b-144">果鲁穆奇语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-144">Gurmukhi</span></span>

- <span data-ttu-id="d6b1b-145">希伯来语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-145">Hebrew</span></span>

- <span data-ttu-id="d6b1b-146">表意文字脚本</span><span class="sxs-lookup"><span data-stu-id="d6b1b-146">Ideographic scripts</span></span>

- <span data-ttu-id="d6b1b-147">卡纳达语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-147">Kannada</span></span>

- <span data-ttu-id="d6b1b-148">老挝语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-148">Lao</span></span>

- <span data-ttu-id="d6b1b-149">拉丁语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-149">Latin</span></span>

- <span data-ttu-id="d6b1b-150">马拉雅拉姆语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-150">Malayalam</span></span>

- <span data-ttu-id="d6b1b-151">蒙古语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-151">Mongolian</span></span>

- <span data-ttu-id="d6b1b-152">奥里亚语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-152">Odia</span></span>

- <span data-ttu-id="d6b1b-153">叙利亚语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-153">Syriac</span></span>

- <span data-ttu-id="d6b1b-154">泰米尔语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-154">Tamil</span></span>

- <span data-ttu-id="d6b1b-155">泰卢固语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-155">Telugu</span></span>

- <span data-ttu-id="d6b1b-156">塔安那文</span><span class="sxs-lookup"><span data-stu-id="d6b1b-156">Thaana</span></span>

- <span data-ttu-id="d6b1b-157">泰语\*</span><span class="sxs-lookup"><span data-stu-id="d6b1b-157">Thai\*</span></span>

- <span data-ttu-id="d6b1b-158">藏语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-158">Tibetan</span></span>

 <span data-ttu-id="d6b1b-159">\*此版本支持显示和编辑泰语文本，但不支持断词。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-159">\*In this release the display and editing of Thai text is supported; word breaking is not.</span></span>

 <span data-ttu-id="d6b1b-160">目前不支持以下脚本：</span><span class="sxs-lookup"><span data-stu-id="d6b1b-160">The following scripts are not currently supported:</span></span>

- <span data-ttu-id="d6b1b-161">高棉语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-161">Khmer</span></span>

- <span data-ttu-id="d6b1b-162">古朝鲜语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-162">Korean Old Hangul</span></span>

- <span data-ttu-id="d6b1b-163">缅甸语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-163">Myanmar</span></span>

- <span data-ttu-id="d6b1b-164">僧伽罗语</span><span class="sxs-lookup"><span data-stu-id="d6b1b-164">Sinhala</span></span>

 <span data-ttu-id="d6b1b-165">所有书写系统都引擎都支持[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]字体。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-165">All the writing system engines support [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fonts.</span></span> [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] <span data-ttu-id="d6b1b-166">字体可包括[!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]布局表格，字体创建者来设计更好地国际化的高端版式字体。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-166">fonts can include the [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] layout tables that enable font creators to design better international and high-end typographic fonts.</span></span> <span data-ttu-id="d6b1b-167">[!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]字体布局表格包含有关字形替换、 字形位置、 对齐和定位基线，信息使文本处理应用程序改进文本布局。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-167">The [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] font layout tables contain information about glyph substitutions, glyph positioning, justification, and baseline positioning, enabling text-processing applications to improve text layout.</span></span>

 [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] <span data-ttu-id="d6b1b-168">字体，可使用处理大型字形集[!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)]编码。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-168">fonts allow the handling of large glyph sets using [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] encoding.</span></span> <span data-ttu-id="d6b1b-169">这种编码享有广泛的国际支持，并支持版式字形变体。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-169">Such encoding enables broad international support as well as for typographic glyph variants.</span></span>

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="d6b1b-170">文本呈现[!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)]子像素技术，它支持分辨率独立性。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-170">text rendering is powered by [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] sub-pixel technology that supports resolution independence.</span></span> <span data-ttu-id="d6b1b-171">这极大地提高了可读性，并为所有脚本提供了支持高质量杂志样式文档的功能。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-171">This significantly improves legibility and provides the ability to support high quality magazine style documents for all scripts.</span></span>

<a name="intl_layout"></a>
### <a name="international-layout"></a><span data-ttu-id="d6b1b-172">国际化布局</span><span class="sxs-lookup"><span data-stu-id="d6b1b-172">International Layout</span></span>
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="d6b1b-173">提供一种支持水平、双向和垂直布局的简便方式。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-173">provides a very convenient way to support horizontal, bidirectional, and vertical layouts.</span></span> <span data-ttu-id="d6b1b-174">在演示框架<xref:System.Windows.FrameworkElement.FlowDirection%2A>属性可以用于定义布局。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-174">In presentation framework the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property can be used to define layout.</span></span> <span data-ttu-id="d6b1b-175">流方向模式包括：</span><span class="sxs-lookup"><span data-stu-id="d6b1b-175">The flow direction patterns are:</span></span>

- <span data-ttu-id="d6b1b-176">*LeftToRight* - 适用于拉丁语和东亚语等语言的水平布局。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-176">*LeftToRight* - horizontal layout for Latin, East Asian and so forth.</span></span>

- <span data-ttu-id="d6b1b-177">*RightToLeft* - 适用于阿拉伯语和希伯来语等语言的双向布局。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-177">*RightToLeft* - bidirectional for Arabic, Hebrew and so forth.</span></span>

<a name="developing_localizable_apps"></a>
## <a name="developing-localizable-applications"></a><span data-ttu-id="d6b1b-178">开发可本地化的应用程序</span><span class="sxs-lookup"><span data-stu-id="d6b1b-178">Developing Localizable Applications</span></span>
 <span data-ttu-id="d6b1b-179">编写供全球使用的应用程序时，应牢记应用程序必须可本地化。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-179">When you write an application for global consumption you should keep in mind that the application must be localizable.</span></span> <span data-ttu-id="d6b1b-180">以下主题指出了若干注意事项。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-180">The following topics point out things to consider.</span></span>

<a name="mui"></a>
### <a name="multilingual-user-interface"></a><span data-ttu-id="d6b1b-181">多语言用户界面</span><span class="sxs-lookup"><span data-stu-id="d6b1b-181">Multilingual User Interface</span></span>
 <span data-ttu-id="d6b1b-182">多语言用户界面 (MUI) 是[!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)]支持用于切换[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]从到另一种语言。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-182">Multilingual User Interfaces (MUI) is a [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] support for switching [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] from one language to another.</span></span> <span data-ttu-id="d6b1b-183">一个[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序使用程序集的模型来支持 MUI。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-183">A [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application uses the assembly model to support MUI.</span></span> <span data-ttu-id="d6b1b-184">一个应用程序包含非特定语言程序集和与语言相关的附属资源程序集。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-184">One application contains language-neutral assemblies as well as language-dependent satellite resource assemblies.</span></span> <span data-ttu-id="d6b1b-185">入口点是主程序集中的托管 .EXE。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-185">The entry point is a managed .EXE in the main assembly.</span></span>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="d6b1b-186">资源加载程序利用[!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)]的资源管理器以支持资源查找和回退。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-186">resource loader takes advantage of the [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)]'s resource manager to support resource lookup and fallback.</span></span> <span data-ttu-id="d6b1b-187">多个语言附属程序集使用同一个主程序集。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-187">Multiple language satellite assemblies work with the same main assembly.</span></span> <span data-ttu-id="d6b1b-188">加载资源程序集依赖于<xref:System.Globalization.CultureInfo.CurrentUICulture%2A>当前线程。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-188">The resource assembly that is loaded depends on the <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> of the current thread.</span></span>

<a name="localizable_ui"></a>
### <a name="localizable-user-interface"></a><span data-ttu-id="d6b1b-189">可本地化的用户界面</span><span class="sxs-lookup"><span data-stu-id="d6b1b-189">Localizable User Interface</span></span>
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="d6b1b-190">应用程序使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]来定义其[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-190">applications use [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] to define their [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> <span data-ttu-id="d6b1b-191">通过 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，开发人员可使用一组属性和逻辑指定对象的层次结构。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-191">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] allows developers to specify a hierarchy of objects with a set of properties and logic.</span></span> <span data-ttu-id="d6b1b-192">主要用途[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]是开发[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序，但它可用于指定层次结构的任何[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]对象。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-192">The primary use of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is to develop [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications but it can be used to specify a hierarchy of any [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objects.</span></span> <span data-ttu-id="d6b1b-193">大多数开发人员使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]以指定其应用程序的[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]和使用 C# 等编程语言，以响应用户交互。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-193">Most developers use [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] to specify their application's [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] and use a programming language such as C# to react to user interaction.</span></span>

 <span data-ttu-id="d6b1b-194">从资源角度来看，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文件以描述依赖于语言的[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]属于资源元素，因此其最终分发格式必须可本地化，以支持国际语言。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-194">From a resource point of view, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file designed to describe a language-dependent [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is a resource element and therefore its final distribution format must be localizable to support international languages.</span></span> <span data-ttu-id="d6b1b-195">因为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]无法处理事件许多[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]应用程序包含要执行此操作的代码块。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-195">Because [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] cannot handle events many [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] applications contain blocks of code to do this.</span></span> <span data-ttu-id="d6b1b-196">有关详细信息，请参阅[XAML 概述 (WPF)](xaml-overview-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-196">For more information, see [XAML Overview (WPF)](xaml-overview-wpf.md).</span></span> <span data-ttu-id="d6b1b-197">剥除代码并将其编译到不同的二进制文件时[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文件标记为 XAML 的 BAML 形式。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-197">Code is stripped out and compiled into different binaries when a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is tokenized into the BAML form of XAML.</span></span> <span data-ttu-id="d6b1b-198">BAML 形式的 XAML 文件、图像以及其他类型的托管资源对象将嵌入附属资源程序集中，该程序集可本地化为其他语言，如果不需要进行本地化，以上各项就会嵌入主程序集中。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-198">The BAML form of XAML files, images, and other types of managed resource objects are embedded in the satellite resource assembly, which can be localized into other languages, or the main assembly when localization is not required.</span></span>

> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="d6b1b-199">应用程序支持所有[!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)][!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]资源包括字符串表、 图像和等。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-199">applications support all the [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)][!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] resources including string tables, images, and so forth.</span></span>

<a name="building_localizable_apps"></a>
### <a name="building-localizable-applications"></a><span data-ttu-id="d6b1b-200">生成可本地化的应用程序</span><span class="sxs-lookup"><span data-stu-id="d6b1b-200">Building Localizable Applications</span></span>
 <span data-ttu-id="d6b1b-201">本地化是指以适应[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]不同的区域性。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-201">Localization means to adapt a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to different cultures.</span></span> <span data-ttu-id="d6b1b-202">若要使[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序可本地化，开发人员需要生成一个资源程序集的所有可本地化的资源。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-202">To make a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="d6b1b-203">资源程序集本地化为不同语言和代码隐藏功能使用资源管理[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]加载。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-203">The resource assembly is localized into different languages, and the code-behind uses resource management [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] to load.</span></span> <span data-ttu-id="d6b1b-204">所需的文件之一[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序是项目文件 (.proj)。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-204">One of the files required for a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application is a project file (.proj).</span></span> <span data-ttu-id="d6b1b-205">应用程序中使用的所有资源都应包括在项目文件中。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-205">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="d6b1b-206">以下 .csproj 文件示例演示如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-206">The following example from a .csproj file shows how to do this.</span></span>

```xml
<Resource Include="data\picture1.jpg"/>
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

 <span data-ttu-id="d6b1b-207">若要使用你的应用程序中的资源实例化<xref:System.Resources.ResourceManager>并加载你想要使用的资源。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-207">To use a resource in your application instantiate a <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="d6b1b-208">下面的示例演示如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-208">The following example demonstrates how to do this.</span></span>

 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

<a name="using_clickonce"></a>
## <a name="using-clickonce-with-localized-applications"></a><span data-ttu-id="d6b1b-209">在本地化的应用程序中使用 ClickOnce</span><span class="sxs-lookup"><span data-stu-id="d6b1b-209">Using ClickOnce with Localized Applications</span></span>
 <span data-ttu-id="d6b1b-210">ClickOnce 是将随 Visual Studio 2005 的新 Windows 窗体部署技术。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-210">ClickOnce is a new Windows Forms deployment technology that will ship with Visual Studio 2005.</span></span> <span data-ttu-id="d6b1b-211">通过该技术可安装应用程序和升级 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-211">It enables application installation and upgrading of Web applications.</span></span> <span data-ttu-id="d6b1b-212">对使用 ClickOnce 部署的应用程序进行本地化后，只能在本地化的区域性中查看该应用程序。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-212">When an application that was deployed with ClickOnce is localized it can only be viewed on the localized culture.</span></span> <span data-ttu-id="d6b1b-213">例如，如果部署的应用程序本地化为日语它只能查看在日语[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]不在英文 Windows 上。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-213">For example, if a deployed application is localized to Japanese it can only be viewed on Japanese [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] not on English Windows.</span></span> <span data-ttu-id="d6b1b-214">这带来问题，因为它是日语用户经常运行英语版本的 Windows 的常见方案。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-214">This presents a problem because it is a common scenario for Japanese users to run an English version of Windows.</span></span>

 <span data-ttu-id="d6b1b-215">此问题的解决方案是设置非特定语言回退特性。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-215">The solution to this problem is setting the neutral language fallback attribute.</span></span> <span data-ttu-id="d6b1b-216">应用程序开发人员可选择从主程序集中删除资源，并指定可在特定区域性对应的附属程序集中找到该资源。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-216">An application developer can optionally remove resources from the main assembly and specify that the resources can be found in a satellite assembly corresponding to a specific culture.</span></span> <span data-ttu-id="d6b1b-217">若要控制此过程，请使用<xref:System.Resources.NeutralResourcesLanguageAttribute>。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-217">To control this process use the <xref:System.Resources.NeutralResourcesLanguageAttribute>.</span></span> <span data-ttu-id="d6b1b-218">构造函数<xref:System.Resources.NeutralResourcesLanguageAttribute>类具有两个签名，另一个采用<xref:System.Resources.UltimateResourceFallbackLocation>参数指定的位置，<xref:System.Resources.ResourceManager>应提取回退资源： 主程序集或附属程序集。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-218">The constructor of the <xref:System.Resources.NeutralResourcesLanguageAttribute> class has two signatures, one that takes an <xref:System.Resources.UltimateResourceFallbackLocation> parameter to specify the location where the <xref:System.Resources.ResourceManager> should extract the fallback resources: main assembly or satellite assembly.</span></span> <span data-ttu-id="d6b1b-219">下面的示例演示如何使用此特性。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-219">The following example shows how to use the attribute.</span></span> <span data-ttu-id="d6b1b-220">对于最终回退位置，代码会导致<xref:System.Resources.ResourceManager>查找当前正在执行的程序集的目录的"de"子目录中的资源。</span><span class="sxs-lookup"><span data-stu-id="d6b1b-220">For the ultimate fallback location, the code causes the <xref:System.Resources.ResourceManager> to look for the resources in the "de" subdirectory of the directory of the currently executing assembly.</span></span>

```
[assembly: NeutralResourcesLanguageAttribute(
    "de" , UltimateResourceFallbackLocation.Satellite)]
```

## <a name="see-also"></a><span data-ttu-id="d6b1b-221">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6b1b-221">See also</span></span>

- [<span data-ttu-id="d6b1b-222">WPF 全球化和本地化概述</span><span class="sxs-lookup"><span data-stu-id="d6b1b-222">WPF Globalization and Localization Overview</span></span>](wpf-globalization-and-localization-overview.md)
