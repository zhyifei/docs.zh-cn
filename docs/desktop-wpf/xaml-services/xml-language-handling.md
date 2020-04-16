---
title: XAML 中 xml:lang 的处理
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:lang attribute
- xml:lang attribute [XAML Services]
- RFC 3066 standard [XAML Services]
- standards [XAML Services], RFC 3066
ms.assetid: 7aac0078-a1c5-41f8-b8b0-975510d9dca0
ms.openlocfilehash: b5a06adbb7cb874bc09899118f13b91fbec7a85e
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432706"
---
# <a name="xmllang-handling-in-xaml"></a>XAML 中 xml:lang 的处理

该`xml:lang`属性是一个 XML 定义的属性，用于声明 XML 中元素的语言和文化信息。 此属性的相同含义在 XAML 中持续存在；但有一些其他注意事项。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<object xml:lang="rfc3066lang" />
```

## <a name="xaml-values"></a>XAML 值

|||
|-|-|
|*rfc3066lang*|派生自 [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) 标准的字符串，并标识一种语言或语言-地区。 当为后者时，将由一个连字符分隔语言和区域。 请参阅 <xref:System.Windows.Markup.XmlLanguage> ，以了解有关值和格式的更多信息。|

## <a name="remarks"></a>备注

中`xml:lang`[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]的属性的定义派生自`xml:lang`万维网联盟 （W3C） 对 XML 的定义。 语言和区域性信息可能由元素根据其实现以不同方式进行处理；但是， [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 属性没有默认的 `xml:lang` 处理方式。

`xml:lang` 属性的默认值是属性级空字符串。

当由作用于 `xml:lang` 值的系统进行解释时， `xml:lang` 属性效果和属性值通常永久保留到子元素中。

当由 .NET XAML 服务的 XAML`xml:lang`编写器解释<xref:System.Windows.Markup.XmlLanguage>时<xref:System.Globalization.CultureInfo>，值可以在基础对象表示形式中创建或对象;但是，该行为取决于为其`xml:lang`指定的值是否为这些类的有效构造。

通过将 `xml:lang` 应用到属性，框架可以在 XML 中创建框架定义属性和 <xref:System.Windows.Markup.XmlLangPropertyAttribute> 含义之间的关联。

## <a name="wpf-usage-nodes"></a>WPF 使用情况节点

对于身为 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.FrameworkContentElement>派生类的元素，可以使用等效 <xref:System.Windows.FrameworkElement.Language%2A> 依赖项属性取代 `xml:lang` 属性。 默认情况下，如果未通过属性或通过处理 <xref:System.Windows.FrameworkElement.Language%2A> 属性来另外设置 `xml:lang` 属性，则它使用“en-US”。

## <a name="see-also"></a>请参阅

- [WPF 的全球化](../../framework/wpf/advanced/globalization-for-wpf.md)
