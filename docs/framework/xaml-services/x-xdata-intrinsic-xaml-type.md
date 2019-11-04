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
ms.openlocfilehash: 8496e7c87cf7e6eea996ca7af4f288b7495c7661
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459901"
---
# <a name="xxdata-intrinsic-xaml-type"></a>x:XData 内部 XAML 类型
启用 XML 数据岛在 XAML 生产中的放置。 XAML 处理器不应处理 `x:XData` 中的 XML 元素，就好像它们是正在操作的默认 XAML 命名空间或任何其他 XAML 命名空间的一部分。 `x:XData` 可以包含格式正确的 XML。  
  
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
|`elementDataRoot`|括起来的数据岛的单个根元素。 对于最终使用者而言，没有单个根的 XML 被视为无效。 具体而言，如果 `x:XData` 旨在用作 WPF 的 XML 数据源，或使用 XML 源进行数据绑定的其他技术，则需要单个根。|  
|`[elementData]`|可选。 表示 XML 数据的 XML。 可以将任意数量的元素包含为元素数据，嵌套元素可以包含在其他元素中;但是，XML 的一般规则是适用的。|  
  
## <a name="remarks"></a>备注  
 `x:XData` 对象中的 XML 元素可以在数据中重新声明包含 XMLDOM 的所有可能的命名空间和前缀。  
  
 通过 <xref:System.Windows.Markup.XData> 类，可以通过编程方式访问 XML 数据和 `x:XData` 内部 XAML 类型 .NET Framework XAML 服务。  
  
## <a name="wpf-usage-notes"></a>WPF 使用说明  
 `x:XData` 对象主要用作 <xref:System.Windows.Data.XmlDataProvider>的子对象，或者作为 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> 属性的子对象（在 XAML 中，这通常用属性元素语法表示）。  
  
 数据通常应将数据岛内的基本 XML 命名空间重新定义为新的默认 XML 命名空间（设置为空字符串）。 对于简单的数据岛，这是最简单的，因为用于引用和绑定到数据的 <xref:System.Windows.Data.Binding.XPath%2A> 表达式可避免包含前缀。 更复杂的数据岛可能会为数据定义多个前缀，并在根处为 XML 命名空间使用特定的前缀。 在这种情况下，所有 <xref:System.Windows.Data.Binding.XPath%2A> 表达式引用应包括相应的命名空间映射前缀。 有关详细信息，请参阅 [数据绑定概述](../../desktop-wpf/data/data-binding-overview.md)。  
  
 从技术上说，`x:XData` 可以用作 <xref:System.Xml.Serialization.IXmlSerializable>类型的任何属性的内容。 但 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> 是唯一明显的实现。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Data.XmlDataProvider>
- [数据绑定概述](../../desktop-wpf/data/data-binding-overview.md)
- [绑定标记扩展](../wpf/advanced/binding-markup-extension.md)
