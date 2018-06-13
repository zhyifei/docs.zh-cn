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
ms.openlocfilehash: 518a85c158c9a4472689d3c236b84278114cf3ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547194"
---
# <a name="staticresource-markup-extension"></a>StaticResource 标记扩展
任何提供的值[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]通过查找对已定义的资源的引用的属性特性。 该资源的查找行为是类似于将查找以前已从标记当前加载的资源的加载时间查找[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]页面以及其他应用程序源，并将生成此资源值在运行时对象中的属性值。  
  
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
|`key`|所请求资源的密钥。 此密钥最初分配[X:key 指令](../../../../docs/framework/xaml-services/x-key-directive.md)如果资源已在标记中，创建数据库或用作`key`参数调用时<xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>如果资源在代码中创建的。|  
  
## <a name="remarks"></a>备注  
  
> [!IMPORTANT]
>  A`StaticResource`必须尝试进行的资源的定义的前向引用中按词法进一步[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文件。 不支持尝试执行此操作，并且即使在这种引用不会失败，尝试前向引用将会产生对负载时间性能产生负面影响时表示的内部哈希表<xref:System.Windows.ResourceDictionary>搜索。 为获得最佳结果，调整组合的资源字典中，以便可以避免前向引用。 如果无法避免的前向引用，使用[DynamicResource 标记扩展](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)相反。  
  
 指定<xref:System.Windows.StaticResourceExtension.ResourceKey%2A>应对应于现有资源，使用标识[X:key 指令](../../../../docs/framework/xaml-services/x-key-directive.md)在某种程度在你的页面、 应用程序，可用控件主题和外部资源或系统资源。 该顺序进行资源查找。 有关静态和动态资源的资源查找行为的详细信息，请参阅[XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)。  
  
 资源键可以是定义的任何字符串[XamlName 语法](../../../../docs/framework/xaml-services/xamlname-grammar.md)。 资源键也可以是其他对象类型，如<xref:System.Type>。 A<xref:System.Type>该键样式的基础如何控件可以按主题，通过隐式样式键。 有关详细信息，请参阅[控件创作概述](../../../../docs/framework/wpf/controls/control-authoring-overview.md)。  
  
 引用资源的替代的声明性方式是作为[DynamicResource 标记扩展](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)。  
  
 特性语法是最常用于该标记扩展的语法。 在 `StaticResource` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 扩展类的 <xref:System.Windows.StaticResourceExtension> 值。  
  
 `StaticResource` 可在对象元素语法。 在这种情况下，指定的值<xref:System.Windows.StaticResourceExtension.ResourceKey%2A>属性是必需的。  
  
 `StaticResource` 还可以在详细特性用法中使用，以便将 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 属性指定为一个 property=value 对：  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 如果扩展具有一个以上的可设置属性，或者某些属性是可选的，则详细用法通常会很有用。 由于 `StaticResource` 仅有一个可设置的属性，并且此属性是必需的，因此该详细用法不具有典型性。  
  
 在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器实现，对此标记扩展的处理定义的<xref:System.Windows.StaticResourceExtension>类。  
  
 `StaticResource` 是标记扩展。 当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。 有关详细信息，请参阅[标记扩展和 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)。  
  
## <a name="see-also"></a>请参阅  
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [标记扩展和 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [资源和代码](../../../../docs/framework/wpf/advanced/resources-and-code.md)
