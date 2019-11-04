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
ms.openlocfilehash: b15e2c0bac5610c6f1b10a640254236987c0bcf5
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458735"
---
# <a name="staticresource-markup-extension"></a>StaticResource 标记扩展
通过查找对已定义资源的引用来为任何 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 属性属性提供一个值。 该资源的查找行为与加载时查找类似，它将查找以前从当前 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页的标记加载的资源以及其他应用程序源，并将该资源值生成为属性运行时对象中的值。  
  
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
|`key`|所请求资源的密钥。 如果在标记中创建了资源，则此密钥最初由[X：Key 指令](../../xaml-services/x-key-directive.md)分配，或在调用 <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> 时作为 `key` 参数提供（如果资源是在代码中创建的）。|  
  
## <a name="remarks"></a>备注  
  
> [!IMPORTANT]
> `StaticResource` 不得尝试对在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件中对其进行词法上进一步定义的资源进行前向引用。 如果不支持这样做，则不支持此操作，即使此类引用不会失败，在搜索代表 <xref:System.Windows.ResourceDictionary> 的内部哈希表时，尝试转发引用会导致加载时性能下降。 为了获得最佳结果，请调整资源字典的组合，以便可以避免转发引用。 如果无法避免正向引用，请改用[DynamicResource 标记扩展](dynamicresource-markup-extension.md)。  
  
 指定的 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 应对应于现有的资源，该资源在页面、应用程序、可用控件主题和外部资源或系统资源的某一级别以[X：Key 指令](../../xaml-services/x-key-directive.md)标识。 资源查找按顺序进行。 有关静态和动态资源的资源查找行为的详细信息，请参阅[XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。  
  
 资源键可以是[XamlName 语法](../../xaml-services/xamlname-grammar.md)中定义的任意字符串。 资源键还可以是其他对象类型，如 <xref:System.Type>。 <xref:System.Type> 的关键是通过隐式样式键对控件进行样式控制的基础。 有关详细信息，请参阅[控件创作概述](../controls/control-authoring-overview.md)。  
  
 引用资源的替代声明方法是作为[DynamicResource 标记扩展](dynamicresource-markup-extension.md)。  
  
 特性语法是最常用于该标记扩展的语法。 在 `StaticResource` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 扩展类的 <xref:System.Windows.StaticResourceExtension> 值。  
  
 `StaticResource` 可以在对象元素语法中使用。 在这种情况下，需要指定 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 属性的值。  
  
 `StaticResource` 还可以在详细特性用法中使用，以便将 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 属性指定为一个 property=value 对：  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 如果扩展具有一个以上的可设置属性，或者某些属性是可选的，则详细用法通常会很有用。 由于 `StaticResource` 仅有一个可设置的属性，并且此属性是必需的，因此该详细用法不具有典型性。  
  
 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器实现中，对此标记扩展的处理由 <xref:System.Windows.StaticResourceExtension> 类定义。  
  
 `StaticResource` 是标记扩展。 当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。 有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。  
  
## <a name="see-also"></a>请参阅

- [样式设置和模板化](../controls/styling-and-templating.md)
- [XAML 概述 (WPF)](xaml-overview-wpf.md)
- [标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)
- [XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [资源和代码](resources-and-code.md)
