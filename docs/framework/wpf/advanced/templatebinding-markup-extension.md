---
title: "TemplateBinding 标记扩展"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TemplateBinding
- TemplateBindingExtension
helpviewer_keywords:
- XAML [WPF], TemplateBinding markup extension
- TemplateBinding markup extensions [WPF]
ms.assetid: 1d25bbfc-dbc2-499d-9f12-419d23d4ac6a
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 959cad0d53b12c3093b95b19ff56ed55eec7eb4f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="templatebinding-markup-extension"></a>TemplateBinding 标记扩展
连接某一控件模板中的属性值，使之成为模板化控件上另一个属性的值。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xml  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-attribute-usage-for-setter-property-in-template-or-style"></a>XAML 特性用法（适用于模板或样式的 Setter 属性）  
  
```xml  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`propertyName`|在资源库语法中设置的属性的 <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>。|  
|`sourceProperty`|另一个在要模板化的类型上存在的依赖项属性，由其 <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> 来指定。<br /><br /> - 或 -<br /><br /> 由要模板化的目标类型之外的类型所定义的“dotted-down”属性名称。 这实际上是 <xref:System.Windows.PropertyPath>。 请参阅[PropertyPath XAML 语法](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md)。|  
  
## <a name="remarks"></a>备注  
 A`TemplateBinding`是优化窗体的[绑定](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)对于模板方案，类似于`Binding`使用构造`{Binding RelativeSource={RelativeSource TemplatedParent}}`。 `TemplateBinding` 始终为单向绑定，即使所涉及的属性默认为双向绑定。 所涉及的两个属性都必须是依赖项属性。  
  
 [RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md)是有时在或而不是一起使用的另一个标记扩展`TemplateBinding`以便执行在模板中的相对属性绑定。  
  
 描述为一个概念的控件模板未涵盖;有关详细信息，请参阅[控件样式和模板](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)。  
  
 特性语法是最常用于该标记扩展的语法。 在 `TemplateBinding` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.TemplateBindingExtension.Property%2A> 扩展类的 <xref:System.Windows.TemplateBindingExtension> 值。  
  
 对象元素语法也可行，但因为没有实际的应用，所以未进行演示。 `TemplateBinding` 用于使用计算的表达式来填充资源库内的值，因此使用 `TemplateBinding` 的对象元素语法来填充 `<Setter.Property>` 属性元素语法就会变得繁冗而多余。  
  
 `TemplateBinding` 还可以在详细特性用法中使用，以便将 <xref:System.Windows.TemplateBindingExtension.Property%2A> 属性指定为一个 property=value 对：  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 如果扩展具有一个以上的可设置属性，或者某些属性是可选的，则详细用法通常会很有用。 由于 `TemplateBinding` 仅有一个可设置的属性，并且此属性是必需的，因此该详细用法不具有典型性。  
  
 在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]XAML 处理器实现，对此标记扩展的处理定义的<xref:System.Windows.TemplateBindingExtension>类。  
  
 `TemplateBinding` 是标记扩展。 当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。 XAML 使用中的所有标记扩展`{`和`}`其属性的语法，这是 XAML 处理器识别标记扩展必须处理该特性所依据的约定中的字符。 有关详细信息，请参阅[标记扩展和 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Style>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [标记扩展和 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [RelativeSource 标记扩展](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md)  
 [绑定标记扩展](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)
