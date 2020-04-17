---
title: XML 字符实体和 XAML
ms.date: 03/30/2017
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
ms.openlocfilehash: aff96c5d0ee6bbf2bbe2f9e3b3ae091caa781f7a
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432718"
---
# <a name="xml-character-entities-and-xaml"></a>XML 字符实体和 XAML

XAML 使用在 XML 中为特殊字符定义的字符实体。 本主题介绍一些特定的字符实体和 XAML 中其他 XML 概念的一般注意事项。

## <a name="character-entities-and-escaping-issues-that-are-unique-to-xaml"></a>XAML 独有的字符实体和转义问题

XAML 标记通常使用相同的字符实体和在 XML 中定义的转义序列。

主要的例外是大括号（{ 和 }）在 XAML 中具有意义，因为这些字符通知 XAML 处理器必须将括在大括号中的字符序列解释为标记扩展。 有关标记扩展的详细信息，请参阅 [Markup Extensions for XAML Overview](markup-extensions-overview.md)。

但是，你仍可通过使用特定于 XAML（而非 XML）的转义序列将大括号显示为原义字符。 有关详细信息，请参阅[{}转义序列 - 标记扩展](escape-sequence-markup-extension.md)。

请注意，反斜杠\\（ ） 在作为字符串处理时不需要转义序列。

## <a name="xml-character-entities"></a>XML 字符实体

如前所述，通常用于编写 XAML 标记的大多数字符实体和转义序列都由 XML 定义。 本主题不提供这些实体的完整列表；实体的详细参考可在外部文档（如 XML 规范）中找到。 但是，为方便起见，本主题列出了一些常在 XAML 标记中使用的特定 XML 字符实体。

|字符|实体|说明|
|---------------|------------|-----------|
|&（与号）|\&amp;|必须用于属性值和元素内容两者。|
|>（大于字符）|\&gt;|必须用于属性值，但>是可以接受的，因为元素的内容，只要<不位于它前面。|
|<（字符小于字符）|\&lt;|必须用于属性值，但\<只要>不遵循元素，作为元素的内容是可以接受的。|
|"（直双引号）|\&quot;|必须用于属性值，但直双引号 (") 可作为元素内容。 请注意，属性值可能括在直单引号 (') 或直双引号 (") 内；首先出现的字符定义属性值的引号，另一个引号则可用作值内部的文字。|
|'（直单引号）|\&apos;|必须用于属性值，但直单引号 (') 可作为元素内容。 请注意，属性值可能括在直单引号 (') 或直双引号 (") 内；首先出现的字符定义属性值的引号，另一个引号则可用作值内部的文字。|
|（数字字符映射）|&#*[整数]*;或&x *[十六进制];*|XAML 支持向处于活动状态的编码的数字字符映射。|
|（不间断空格）|&\#160;（假设 UTF-8 编码）|对于流文档元素或采用文本（如 WPF <xref:System.Windows.Controls.TextBox>）的元素，不间断空格没有超出标记范围进行规范化，甚至是对于 `xml:space="default"` 也是如此。 （有关详细信息，请参阅[XAML 中的空白处理](white-space-processing.md)。|

## <a name="xml-comment-format"></a>XML 注释格式

XAML 使用 XML 注释格式：注释的开头为 `<!--`，注释的结尾为 `-->,` 且序列 `--` 不能出现在注释中。

## <a name="xml-processing-instructions"></a>XML 处理指令

XAML 根据 XML 规范处理 XML 处理指令，该规范说明必须传递指令。 .NET XAML 服务中的 XAML 处理不使用任何处理说明。 使用 XAML 的其他现有框架也不会使用 XAML 中的处理指令。

## <a name="see-also"></a>请参阅

- [XAML 概述 (WPF)](../fundamentals/xaml.md)
- [标记扩展和 WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [XamlName 语法](xamlname-grammar.md)
- [XAML 中的空白处理](white-space-processing.md)
