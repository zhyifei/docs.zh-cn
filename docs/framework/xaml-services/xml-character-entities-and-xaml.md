---
title: "XML 字符实体和 XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- '&'
- '&amp'
- '&gt'
- '&lt'
helpviewer_keywords:
- XAML [XAML Services], special characters
- ampersand (&) [XAML Services]
- special characters [XAML Services]
- apostrophe (') [XAML Services]
- greater-than (>) character [XAML Services]
- XAML [XAML Services], quotation mark (")
- XAML [XAML Services], apostrophe (')
- '& (ampersand) [XAML Services]'
- XAML [XAML Services], & (ampersand)
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- less-than (<) character [XAML Services]
ms.assetid: 6896d0ce-74f7-420a-9ab4-de9bbf390e8d
caps.latest.revision: "23"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 5973c67b26e07bba69383cc625ff34493d825a41
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xml-character-entities-and-xaml"></a><span data-ttu-id="e737b-102">XML 字符实体和 XAML</span><span class="sxs-lookup"><span data-stu-id="e737b-102">XML Character Entities and XAML</span></span>
<span data-ttu-id="e737b-103">XAML 使用在 XML 中为特殊字符定义的字符实体。</span><span class="sxs-lookup"><span data-stu-id="e737b-103">XAML uses character entities defined in XML for special characters.</span></span> <span data-ttu-id="e737b-104">本主题介绍一些特定的字符实体和 XAML 中其他 XML 概念的一般注意事项。</span><span class="sxs-lookup"><span data-stu-id="e737b-104">This topic describes some specific character entities and general considerations for other XML concepts in XAML.</span></span>  
  
<a name="character_entities_and_escaping_issues_that_are_unique_to_xaml"></a>   
## <a name="character-entities-and-escaping-issues-that-are-unique-to-xaml"></a><span data-ttu-id="e737b-105">XAML 独有的字符实体和转义问题</span><span class="sxs-lookup"><span data-stu-id="e737b-105">Character Entities and Escaping Issues That Are Unique to XAML</span></span>  
 <span data-ttu-id="e737b-106">XAML 标记通常使用相同的字符实体和在 XML 中定义的转义序列。</span><span class="sxs-lookup"><span data-stu-id="e737b-106">XAML markup typically uses the same character entities and escape sequences that are defined in XML.</span></span>  
  
 <span data-ttu-id="e737b-107">主要的例外是大括号（{ 和 }）在 XAML 中具有意义，因为这些字符通知 XAML 处理器必须将括在大括号中的字符序列解释为标记扩展。</span><span class="sxs-lookup"><span data-stu-id="e737b-107">The main exception is that braces ({ and }) have significance in XAML because these characters inform a XAML processor that a character sequence enclosed by braces must be interpreted as a markup extension.</span></span> <span data-ttu-id="e737b-108">有关标记扩展的详细信息，请参阅 [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e737b-108">For more information about markup extensions, see [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).</span></span>  
  
 <span data-ttu-id="e737b-109">但是，你仍可通过使用特定于 XAML（而非 XML）的转义序列将大括号显示为原义字符。</span><span class="sxs-lookup"><span data-stu-id="e737b-109">However, you can still display the braces as literal characters by using an escape sequence that is particular to XAML instead of XML.</span></span> <span data-ttu-id="e737b-110">有关详细信息，请参阅[{} 转义序列的标记扩展](escape-sequence-markup-extension.md)。</span><span class="sxs-lookup"><span data-stu-id="e737b-110">For more information, see [{} Escape Sequence - Markup Extension](escape-sequence-markup-extension.md).</span></span>  
  
 <span data-ttu-id="e737b-111">请注意，反斜杠 (\\) 作为字符串对其进行处理时不需要转义序列。</span><span class="sxs-lookup"><span data-stu-id="e737b-111">Note that a backslash (\\) does not require an escape sequence when it is handled as a string.</span></span>  
  
<a name="xml_character_entities"></a>   
## <a name="xml-character-entities"></a><span data-ttu-id="e737b-112">XML 字符实体</span><span class="sxs-lookup"><span data-stu-id="e737b-112">XML Character Entities</span></span>  
 <span data-ttu-id="e737b-113">如前所述，通常用于编写 XAML 标记的大多数字符实体和转义序列都由 XML 定义。</span><span class="sxs-lookup"><span data-stu-id="e737b-113">As mentioned previously, most character entities and escape sequences that are typically used to write XAML markup are defined by XML.</span></span> <span data-ttu-id="e737b-114">本主题不提供这些实体的完整列表；实体的详细参考可在外部文档（如 XML 规范）中找到。</span><span class="sxs-lookup"><span data-stu-id="e737b-114">This topic does not provide the complete list of these entities; a detailed reference for the entities can be found in external documentation, such as in XML specifications.</span></span> <span data-ttu-id="e737b-115">但是，为方便起见，本主题列出了一些常在 XAML 标记中使用的特定 XML 字符实体。</span><span class="sxs-lookup"><span data-stu-id="e737b-115">However, for convenience, this topic lists some of the specific XML character entities that are typically used in XAML markup.</span></span>  
  
|<span data-ttu-id="e737b-116">字符</span><span class="sxs-lookup"><span data-stu-id="e737b-116">Character</span></span>|<span data-ttu-id="e737b-117">实体</span><span class="sxs-lookup"><span data-stu-id="e737b-117">Entity</span></span>|<span data-ttu-id="e737b-118">备注</span><span class="sxs-lookup"><span data-stu-id="e737b-118">Notes</span></span>|  
|---------------|------------|-----------|  
|<span data-ttu-id="e737b-119">&（"and"符）</span><span class="sxs-lookup"><span data-stu-id="e737b-119">& (ampersand)</span></span>|&amp;|<span data-ttu-id="e737b-120">必须用于属性值和元素内容两者。</span><span class="sxs-lookup"><span data-stu-id="e737b-120">Must be used both for attribute values and for content of an element.</span></span>|  
|<span data-ttu-id="e737b-121">>（大于号字符）</span><span class="sxs-lookup"><span data-stu-id="e737b-121">> (greater-than character)</span></span>|&gt;|<span data-ttu-id="e737b-122">必须用于属性值，只要 < 不在 > 之前，> 就可作为元素内容。</span><span class="sxs-lookup"><span data-stu-id="e737b-122">Must be used for an attribute value, but > is acceptable as the content of an element as long as < does not precede it.</span></span>|  
|<span data-ttu-id="e737b-123"><（小于号字符）</span><span class="sxs-lookup"><span data-stu-id="e737b-123">< (less-than character)</span></span>|&lt;|<span data-ttu-id="e737b-124">必须用于属性值，但\<可作为元素内容的前提下尽可能接受 > 不跟随其后。</span><span class="sxs-lookup"><span data-stu-id="e737b-124">Must be used for an attribute value, but \< is acceptable as the content of an element as long as > does not follow it.</span></span>|  
|<span data-ttu-id="e737b-125">"（直双引号）</span><span class="sxs-lookup"><span data-stu-id="e737b-125">" (straight quotation mark)</span></span>|&quot;|<span data-ttu-id="e737b-126">必须用于属性值，但直双引号 (") 可作为元素内容。</span><span class="sxs-lookup"><span data-stu-id="e737b-126">Must be used for an attribute value, but a straight quotation mark (") is acceptable as the content of an element.</span></span> <span data-ttu-id="e737b-127">请注意，属性值可能括在直单引号 (') 或直双引号 (") 内；首先出现的字符定义属性值的引号，另一个引号则可用作值内部的文字。</span><span class="sxs-lookup"><span data-stu-id="e737b-127">Note that attribute values may be enclosed either by a single straight quotation mark (') or by a straight quotation mark ("); whichever character appears first defines the attribute value enclosure, and the alternative quote can then be used as a literal within the value.</span></span>|  
|<span data-ttu-id="e737b-128">'（直单引号）</span><span class="sxs-lookup"><span data-stu-id="e737b-128">' (single straight quotation mark)</span></span>|&apos;|<span data-ttu-id="e737b-129">必须用于属性值，但直单引号 (') 可作为元素内容。</span><span class="sxs-lookup"><span data-stu-id="e737b-129">Must be used for an attribute value, but a single straight quotation mark (') is acceptable as the content of an element.</span></span> <span data-ttu-id="e737b-130">请注意，属性值可能括在直单引号 (') 或直双引号 (") 内；首先出现的字符定义属性值的引号，另一个引号则可用作值内部的文字。</span><span class="sxs-lookup"><span data-stu-id="e737b-130">Note that attribute values may be enclosed either by a single straight quotation mark (') or by a straight quotation mark ("); whichever character appears first defines the attribute value enclosure, and the alternative quote can then be used as a literal within the value.</span></span>|  
|<span data-ttu-id="e737b-131">（数字字符映射）</span><span class="sxs-lookup"><span data-stu-id="e737b-131">(numeric character mappings)</span></span>|<span data-ttu-id="e737b-132">&#*[整数]*; 或 & #x*[十六进制]*;</span><span class="sxs-lookup"><span data-stu-id="e737b-132">&#*[integer]*; or &#x*[hex]*;</span></span>|<span data-ttu-id="e737b-133">XAML 支持向处于活动状态的编码的数字字符映射。</span><span class="sxs-lookup"><span data-stu-id="e737b-133">XAML supports numeric character mappings into the encoding that is active.</span></span>|  
|<span data-ttu-id="e737b-134">（不间断空格）</span><span class="sxs-lookup"><span data-stu-id="e737b-134">(nonbreaking space)</span></span>|<span data-ttu-id="e737b-135">&\#160;（假定 utf-8 编码）</span><span class="sxs-lookup"><span data-stu-id="e737b-135">&\#160; (assuming UTF-8 encoding)</span></span>|<span data-ttu-id="e737b-136">对于流文档元素或采用文本（如 WPF <xref:System.Windows.Controls.TextBox>）的元素，不间断空格没有超出标记范围进行规范化，甚至是对于 `xml:space="default"` 也是如此。</span><span class="sxs-lookup"><span data-stu-id="e737b-136">For flow document elements, or elements that take text such as the WPF <xref:System.Windows.Controls.TextBox>, nonbreaking spaces are not normalized out of the markup, even for `xml:space="default"`.</span></span> <span data-ttu-id="e737b-137">(有关详细信息，请参阅[在 XAML 中的空白处理](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)。)</span><span class="sxs-lookup"><span data-stu-id="e737b-137">(For more information, see [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).)</span></span>|  
  
<a name="xml_comment_format"></a>   
## <a name="xml-comment-format"></a><span data-ttu-id="e737b-138">XML 注释格式</span><span class="sxs-lookup"><span data-stu-id="e737b-138">XML Comment Format</span></span>  
 <span data-ttu-id="e737b-139">XAML 使用 XML 注释格式：注释的开头为 `<!--`，注释的结尾为 `-->,` 且序列 `--` 不能出现在注释中。</span><span class="sxs-lookup"><span data-stu-id="e737b-139">XAML uses the XML comment format: the start of the comment is `<!--`, the end of comment is `-->,` and the sequence `--` must not occur within the comment.</span></span>  
  
<a name="xml_processing_instructions"></a>   
## <a name="xml-processing-instructions"></a><span data-ttu-id="e737b-140">XML 处理指令</span><span class="sxs-lookup"><span data-stu-id="e737b-140">XML Processing Instructions</span></span>  
 <span data-ttu-id="e737b-141">XAML 根据 XML 规范处理 XML 处理指令，该规范说明必须传递指令。</span><span class="sxs-lookup"><span data-stu-id="e737b-141">XAML handles XML processing instructions according to XML specifications, which state that the instructions must be passed through.</span></span> <span data-ttu-id="e737b-142">.NET Framework XAML 服务中的 XAML 处理不使用任何处理指令。</span><span class="sxs-lookup"><span data-stu-id="e737b-142">XAML processing in .NET Framework XAML Services  does not use any processing instructions.</span></span> <span data-ttu-id="e737b-143">使用 XAML 的其他现有框架也不会使用 XAML 中的处理指令。</span><span class="sxs-lookup"><span data-stu-id="e737b-143">Other existing frameworks that use XAML also do not use processing instructions from XAML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e737b-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e737b-144">See Also</span></span>  
 [<span data-ttu-id="e737b-145">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="e737b-145">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="e737b-146">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="e737b-146">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="e737b-147">XamlName 语法</span><span class="sxs-lookup"><span data-stu-id="e737b-147">XamlName Grammar</span></span>](../../../docs/framework/xaml-services/xamlname-grammar.md)  
 [<span data-ttu-id="e737b-148">XAML 中的空白处理</span><span class="sxs-lookup"><span data-stu-id="e737b-148">Whitespace Processing in XAML</span></span>](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)
