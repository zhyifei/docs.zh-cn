---
title: '{}转义序列 - 标记扩展'
ms.date: 03/30/2017
f1_keywords:
- '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
ms.openlocfilehash: f84243994557d76fa52d72b060a1ba35460e98b0
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432964"
---
# <a name="-escape-sequence--markup-extension"></a>{}转义序列/标记扩展

为属性值提供 XAML 转义序列。 转义序列允许将属性中的后续值解释为文本。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<object property="{} literalValue" .../>
```

## <a name="xaml-property-element-usage"></a>XAML 属性元素用法

```xaml
<object>
  <object.property>
    {} literalValue
  </object.property>
</object>
```

## <a name="xaml-values"></a>XAML 值

|||
|-|-|
|*字面值*|转义序列后面的文本字符串。 通常，此字符串包含打开或关闭大括号 （* 或 |）。|

## <a name="remarks"></a>备注

转义序列{}（ ） 用于使打开大括号 （*） 可用作 XAML 中的字面字符。

XAML 读取器通常使用开放大括号 （*） 来表示标记扩展的入口点;但是，他们首先检查下一个字符以确定它是否是右大括号 （*）。 只有当两个大括号 （{}） 相邻时， 它们才被视为转义序列.

如果遇到转义序列，XAML 读取器应作为字符串处理字符串的其余部分。 但是，如果转义序列应用于具有类型转换器的成员，则当 XAML 编写器解释该字符串时，该字符串可能会进行类型转换。

转义序列不是标记扩展，并且不由类支持。 但是，XAML 读取器（包括自定义 XAML 读取器）应遵守的约定。

引号 （"） 不能以这种方式用作转义序列。 如果需要将引号设置为非内容属性的属性值，请使用属性元素语法并将引号作为字符串放在属性元素中，或使用 XML 字符实体。 对于内容属性，引号可以是整个内容。

指定必须包含命名{}空间限定符的位置的 XML 类型时，经常需要转义序列 （ ） 。 此位置包括 XAML 属性值的开头，以及等于符号 （*） 之后的标记扩展中。 下面的示例显示出现在 XAML 属性值开头的 XML 命名空间的转义序列。

[!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]

## <a name="see-also"></a>请参阅

- [XAML 的类型转换器和标记扩展](type-converters-and-markup-extensions.md)
- [XML 字符实体和 XAML](xml-character-entities.md)
