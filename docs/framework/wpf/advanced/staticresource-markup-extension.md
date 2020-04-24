---
title: StaticResource 标记扩展
ms.date: 03/30/2017
f1_keywords:
- StaticResource
- StaticResourceExtension
helpviewer_keywords:
- XAML [WPF], StaticResource markup extension
- StaticResource markup extensions [WPF]
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
ms.openlocfilehash: 5c0bb247bae525658d89d53f1672e57b87aba7bc
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646211"
---
# <a name="staticresource-markup-extension"></a>StaticResource 标记扩展
通过查找对已定义的[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]资源的引用，为任何属性属性提供值。 该资源的查找行为类似于加载时间查找，它将查找以前从当前[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]页面标记和其他应用程序源加载的资源，并将该资源值生成为运行时对象中的属性值。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xml  
<object property="{StaticResource key}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>XAML 对象元素用法  
  
```xml  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`key`|所请求资源的密钥。 如果在标记中创建了资源，则[x：Key 指令](../../../desktop-wpf/xaml-services/xkey-directive.md)最初分配此密钥，或者在调用`key`<xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>资源时作为参数提供， 则调用资源是在代码中创建的。|  
  
## <a name="remarks"></a>备注  
  
> [!IMPORTANT]
> 不得`StaticResource`尝试对[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文件中进一步定义的资源进行转发引用。 不支持尝试执行此操作，即使此类引用未失败，在搜索表示 a<xref:System.Windows.ResourceDictionary>的内部哈希表时，尝试正向引用也会造成加载时间性能损失。 为获得最佳效果，请调整资源字典的组成，以避免转发引用。 如果无法避免正向引用，请改用[动态资源标记扩展](dynamicresource-markup-extension.md)。  
  
 指定的<xref:System.Windows.StaticResourceExtension.ResourceKey%2A>资源应对应于现有资源，该资源在页面、应用程序、可用控制主题和外部资源或系统资源的某个级别使用[x：Key 指令](../../../desktop-wpf/xaml-services/xkey-directive.md)标识。 资源查找按该顺序进行。 有关静态和动态资源的资源查找行为的详细信息，请参阅[XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。  
  
 资源键可以是[XamlName 语法](../../../desktop-wpf/xaml-services/xamlname-grammar.md)中定义的任何字符串。 资源密钥也可以是其他对象类型，如 。 <xref:System.Type> 键<xref:System.Type>是如何通过隐式样式键按主题设置控件样式的基础。 有关详细信息，请参阅[控件创作概述](../controls/control-authoring-overview.md)。  
  
 引用资源的替代方法声明性方法是作为[动态资源标记扩展](dynamicresource-markup-extension.md)。  
  
 特性语法是最常用于该标记扩展的语法。 在 `StaticResource` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 扩展类的 <xref:System.Windows.StaticResourceExtension> 值。  
  
 `StaticResource`可用于对象元素语法。 在这种情况下，需要指定<xref:System.Windows.StaticResourceExtension.ResourceKey%2A>属性的值。  
  
 `StaticResource` 还可以在详细特性用法中使用，以便将 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 属性指定为一个 property=value 对：  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 如果扩展具有一个以上的可设置属性，或者某些属性是可选的，则详细用法通常会很有用。 由于 `StaticResource` 仅有一个可设置的属性，并且此属性是必需的，因此该详细用法不具有典型性。  
  
 在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器实现中，此标记扩展的处理由<xref:System.Windows.StaticResourceExtension>类定义。  
  
 `StaticResource` 是标记扩展。 当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。 有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。  
  
## <a name="see-also"></a>另请参阅

- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [XAML 概述 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)
- [XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [资源和代码](resources-and-code.md)
