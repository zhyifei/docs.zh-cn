---
title: x:XData 内部 XAML 类型
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: b7f0954158988db107feb4a6c51ba81d5db11dcb
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432790"
---
# <a name="xxdata-intrinsic-xaml-type"></a>x:XData 内部 XAML 类型
支持在 XAML 生产中放置 XML 数据孤岛。 XAML`x:XData`处理器不应将其中的 XML 元素视为代理默认 XAML 命名空间或任何其他 XAML 命名空间的一部分。 `x:XData`可以包含任意格式良好的 XML。

## <a name="xaml-object-element-usage"></a>XAML 对象元素用法

```xaml
<x:XData>
  <elementDataRoot>
    [elementData]
  </elementDataRoot>
</x:XData>
```

## <a name="xaml-values"></a>XAML 值

|||
|-|-|
|`elementDataRoot`|封闭数据岛的单根元素。 对于大多数最终使用者，没有单个根的 XML 被视为无效。 特别是，如果`x:XData`用作 WPF 的 XML 数据源或使用 XML 源进行数据绑定的许多其他技术，则需要单个根。|
|`[elementData]`|可选。 表示 XML 数据的 XML。 任意数量的元素可以包含在元素数据中，嵌套元素可以包含在其他元素中;但是，XML 的一般规则适用。|

## <a name="remarks"></a>备注

`x:XData`对象中的 XML 元素可以重新声明数据中包含 XMLDOM 的所有可能的命名空间和前缀。

在 .NET XAML 服务中可以通过`x:XData`<xref:System.Windows.Markup.XData>类对 XML 数据和内在 XAML 类型进行编程访问。

## <a name="wpf-usage-notes"></a>WPF 用法说明

该`x:XData`对象主要用作<xref:System.Windows.Data.XmlDataProvider>的子对象，或者用作属性的<xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType>子对象（在 XAML 中，这通常用属性元素语法表示）。

数据通常应重新定义数据孤岛中的基本 XML 命名空间，作为新的默认 XML 命名空间（设置为空字符串）。 对于简单的数据孤岛来说，这很容易，<xref:System.Windows.Data.Binding.XPath%2A>因为用于引用和绑定到数据的表达式可以避免包含前缀。 更复杂的数据孤岛可能为数据定义多个前缀，并使用根目录的 XML 命名空间的特定前缀。 在这种情况下，所有<xref:System.Windows.Data.Binding.XPath%2A>表达式引用都应包含适当的命名空间映射前缀。 有关详细信息，请参阅 [数据绑定概述](../data/data-binding-overview.md)。

从技术上讲，`x:XData`可用作任何类型<xref:System.Xml.Serialization.IXmlSerializable>属性的内容。 然而，<xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType>是唯一突出的实现。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Data.XmlDataProvider>
- [数据绑定概述](../data/data-binding-overview.md)
- [绑定标记扩展](../../framework/wpf/advanced/binding-markup-extension.md)
