---
title: "DynamicResource 标记扩展"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DynamicResource
- DynamicResourceExtension
helpviewer_keywords:
- XAML [WPF], DynamicResource markup extension
- DynamicResource markup extensions [WPF]
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c80d975e756fab449c254b9e1d8d1bc99a25652e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="dynamicresource-markup-extension"></a>DynamicResource 标记扩展
任何提供的值[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]通过延迟将对定义资源的引用值的属性特性。 该资源的查找行为是类似于运行时查找。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xml  
<object property="{DynamicResource key}" .../>  
```  
  
## <a name="xaml-property-element-usage"></a>XAML 属性元素用法  
  
```xml  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`key`|请求的资源键。 此密钥最初分配[X:key 指令](../../../../docs/framework/xaml-services/x-key-directive.md)如果资源已在标记中，创建数据库或用作`key`参数调用时<xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>如果资源在代码中创建的。|  
  
## <a name="remarks"></a>备注  
 A`DynamicResource`将创建一个临时在初始编译表达式，因此遵从资源的查找，直到实际需要来构造对象请求的资源值为止。 这可能会后[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]加载页。 资源值将根据针对从当前页范围，开始的所有活动的资源字典的键搜索找到并替换为从编译的占位符表达式。  
  
> [!IMPORTANT]
>  依赖项属性在优先级方面，`DynamicResource`表达式等效于应用动态资源引用的位置的位置。 如果你设置一个属性，以前的本地值`DynamicResource`表达式作为本地值，`DynamicResource`完全删除。 有关详细信息，请参阅[依赖属性值优先级](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)。  
  
 某些资源访问控制方案是特别适合于`DynamicResource`相对于[否则标记扩展](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)。 请参阅[XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)有关的相对优势和性能产生的影响的讨论`DynamicResource`和`StaticResource`。  
  
 指定<xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>应对应于现有资源由[X:key 指令](../../../../docs/framework/xaml-services/x-key-directive.md)在你的页面、 应用程序、 可用控件主题和外部资源或系统资源，在某种程度和资源查找将按该顺序。 有关静态和动态资源的资源查找的详细信息，请参阅[XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)。  
  
 资源键可以是定义的任何字符串[XamlName 语法](../../../../docs/framework/xaml-services/xamlname-grammar.md)。 资源键也可能是其他对象类型，如<xref:System.Type>。 A<xref:System.Type>该键可以如何通过主题样式控件的基础。 有关详细信息，请参阅[控件创作概述](../../../../docs/framework/wpf/controls/control-authoring-overview.md)。  
  
 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]有关查找资源值，如<xref:System.Windows.FrameworkElement.FindResource%2A>，按照所使用的相同的资源查找逻辑`DynamicResource`。  
  
 引用资源的替代的声明性方式是作为[否则标记扩展](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)。  
  
 特性语法是最常用于该标记扩展的语法。 在 `DynamicResource` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 扩展类的 <xref:System.Windows.DynamicResourceExtension> 值。  
  
 `DynamicResource`可在对象元素语法。 在这种情况下，指定的值<xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>属性是必需的。  
  
 `DynamicResource` 还可以在详细特性用法中使用，以便将 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 属性指定为一个 property=value 对：  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 如果扩展具有一个以上的可设置属性，或者某些属性是可选的，则详细用法通常会很有用。 由于 `DynamicResource` 仅有一个可设置的属性，并且此属性是必需的，因此该详细用法不具有典型性。  
  
 在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器实现，对此标记扩展的处理定义的<xref:System.Windows.DynamicResourceExtension>类。  
  
 `DynamicResource` 是标记扩展。 当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。 有关详细信息，请参阅[标记扩展和 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)。  
  
## <a name="see-also"></a>另请参阅  
 [XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [资源和代码](../../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [x:Key 指令](../../../../docs/framework/xaml-services/x-key-directive.md)  
 [XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [标记扩展和 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [StaticResource 标记扩展](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)  
 [标记扩展和 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
