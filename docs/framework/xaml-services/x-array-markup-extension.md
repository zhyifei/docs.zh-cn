---
title: "x:Array 标记扩展"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
caps.latest.revision: "20"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 2cefdee5ca2d1b0a6c79325365aa101d767b6926
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xarray-markup-extension"></a>x:Array 标记扩展
提供对 XAML 中通过标记扩展的对象数组的常规支持。 这对应于`x:ArrayExtension`[MS-XAML] 中的 XAML 类型。  
  
## <a name="xaml-object-element-usage"></a>XAML 对象元素用法  
  
```  
<x:Array Type="typeName">  
  arrayContents  
</x:Array>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`typeName`|类型的名称，你`x:Array`将包含。 `typeName`可能会 （并且通常为） 前缀的 XAML 命名空间包含的 XAML 类型定义。|  
|`arrayContents`|分配给内部函数的项内容`ArrayExtension.Items`属性。 通常情况下，这些项被指定为中包含的一个或多个对象元素`x:Array`开始和结束标记。 此处需要可赋给中指定的 XAML 类型的指定对象`typeName`。|  
  
## <a name="remarks"></a>备注  
 `Type`是所有的必需的属性`x:Array`对象元素。 A`Type`参数值不需要使用`x:Type`标记扩展; 短暂的类型名称都是 XAML 类型，这可以指定为一个字符串。  
  
 在.NET Framework XAML 服务实现中，输入的 XAML 类型和输出 CLR 之间的关系<xref:System.Type>的创建的数组会影响的标记扩展的服务上下文。 输出<xref:System.Type>是<xref:System.Xaml.XamlType.UnderlyingType%2A>后查找所需的输入的 XAML 类型<xref:System.Xaml.XamlType>基于 XAML 架构上下文和<xref:System.Windows.Markup.IXamlTypeResolver>的上下文提供的服务。  
  
 处理时，将数组内容分配给`ArrayExtension.Items`内部属性。 在<xref:System.Windows.Markup.ArrayExtension>实现，它通过表示<xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>。  
  
 在.NET Framework XAML 服务实现中，对此标记扩展的处理由定义<xref:System.Windows.Markup.ArrayExtension>类。 <xref:System.Windows.Markup.ArrayExtension>未密封，并且无法用作自定义数组类型的标记扩展实现的基础。  
  
 `x:Array`是的详细信息适用于常规 XAML 语言的可扩展性。 但`x:Array`也可以是适用于指定的某些属性是作为其结构化的属性内容中使支持 XAML 的集合的 XAML 值。 例如，可以指定的内容<xref:System.Collections.IEnumerable>具有属性`x:Array`使用情况。  
  
 `x:Array` 是标记扩展。 当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此要求更具有全局性。 `x:Array`部分是该规则的例外，因为而不是提供替代属性值处理`x:Array`提供其内部文本内容的其他处理。 此行为使现有的内容模型，来分组到一个数组和更高版本的代码隐藏文件中引用的访问已命名的数组; 可能不支持的类型你可以调用<xref:System.Array>方法来获取各个数组项。  
  
 在 XAML 中的所有标记扩展都使用大括号 ({，}`)`在其属性语法中，该命令是 XAML 处理器识别标记扩展必须处理的属性值所依据的约定。 有关常规中的标记扩展的详细信息，请参阅[类型转换器和 XAML 的标记扩展](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)。  
  
 在 XAML 2009`x:Array`定义为一种语言基元而不是标记扩展。 有关详细信息，请参阅[常见 XAML 语言基元的内置类型](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)。  
  
## <a name="wpf-usage-notes"></a>WPF 用法说明  
 通常情况下，填充的对象元素`x:Array`不中存在的元素[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]XAML 命名空间，并且需要到非默认 XAML 命名空间的前缀映射。  
  
 例如，下面是两个字符串的简单数组与`sys`前缀 (以及`x`) 数组级别定义。  
  
 [xaml]  
  
 `<x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 `xmlns:sys="clr-namespace:System;assembly=mscorlib">`  
  
 `<sys:String>Hello</sys:String>`  
  
 `<sys:String>World</sys:String>`  
  
 `</x:Array>`  
  
 对于用作数组元素的自定义类型，此类还必须支持在 XAML 中作为对象元素实例化的要求。 有关详细信息，请参阅[XAML 和 wpf 自定义类](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)。  
  
## <a name="see-also"></a>另请参阅  
 [标记扩展和 WPF XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [从 WPF 迁移到 System.Xaml 的类型](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
