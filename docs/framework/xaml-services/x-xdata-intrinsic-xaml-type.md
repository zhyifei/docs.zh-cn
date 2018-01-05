---
title: "x:XData 内部 XAML 类型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
caps.latest.revision: "17"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ec46d0363e5b10d3bd3bd3f9c8f4d3694abc1c8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="xxdata-intrinsic-xaml-type"></a>x:XData 内部 XAML 类型
可实现的 XAML 生产中的 XML 数据岛的放置。 中的 XML 元素`x:XData`好像它们是充当默认 XAML 命名空间的一部分或任何其他 XAML 命名空间不应由 XAML 处理器处理。 `x:XData`可以包含任意格式正确的 XML。  
  
## <a name="xaml-object-element-usage"></a>XAML 对象元素用法  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`elementDataRoot`|包含的数据岛的单个根元素。 对于大多数的最终用户来说，有一个根的 XML 将被视为无效。 具体而言，单个根是必需的如果`x:XData`XML 数据源作为适用于 WPF 或 XML 源用于数据绑定的许多其他技术。|  
|`[elementData]`|可选。 表示 XML 数据的 XML。 可以包含任意数目的元素作为元素数据和嵌套的元素可包含其他元素，则在但是，XML 的一般规则适用。|  
  
## <a name="remarks"></a>备注  
 中的 XML 元素`x:XData`对象可以重新声明所有可能的命名空间和包含的 XMLDOM 数据中的前缀。  
  
 以编程方式访问 XML 数据与`x:XData`内部 XAML 类型是在.NET Framework XAML 服务中通过可能<xref:System.Windows.Markup.XData>类。  
  
## <a name="wpf-usage-notes"></a>WPF 用法说明  
 `x:XData`对象主要用作的子对象<xref:System.Windows.Data.XmlDataProvider>，或子对象的形式或者<xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType>属性 （在 XAML 中，这通常表示在属性元素语法）。  
  
 数据通常应重新定义为新的默认 XML 命名空间 （设置为空字符串） 将数据岛内的基 XML 命名空间。 这是最简单的，简单数据岛因为<xref:System.Windows.Data.Binding.XPath%2A>用于引用，并绑定到数据的表达式可以避免包含的前缀。 更复杂的数据岛可能定义的数据的多个前缀，并使用特定前缀的 XML 命名空间根处。 在这种情况下，所有<xref:System.Windows.Data.Binding.XPath%2A>表达式引用应包括相应的命名空间映射前缀。 有关详细信息，请参阅 [数据绑定概述](../../../docs/framework/wpf/data/data-binding-overview.md)。  
  
 从技术上讲，`x:XData`可以用作类型的任何属性的内容<xref:System.Xml.Serialization.IXmlSerializable>。 但是，<xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType>是唯一突出的实现。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Data.XmlDataProvider>  
 [数据绑定概述](../../../docs/framework/wpf/data/data-binding-overview.md)  
 [绑定标记扩展](../../../docs/framework/wpf/advanced/binding-markup-extension.md)
