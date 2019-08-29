---
title: ThemeDictionary 标记扩展
ms.date: 03/30/2017
f1_keywords:
- ThemeDictionaryExtension
- ThemeDictionary
helpviewer_keywords:
- ThemeDictionary markup extension [WPF]
- XAML [WPF], ThemeDictionary markup extension
ms.assetid: aa75e10b-13dd-4989-972d-51bab63a05e2
ms.openlocfilehash: 7fa729d600f25b73028bae0dd6d9248b5839dd4c
ms.sourcegitcommit: 77e33b682db39955e331b8e8eda4ef1925a24e78
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2019
ms.locfileid: "70133864"
---
# <a name="themedictionary-markup-extension"></a>ThemeDictionary 标记扩展
为集成第三方控件的自定义控件创作者或应用程序提供一种方法，用于加载要在设置控件样式时使用的特定于主题的资源字典。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xml  
<object property="{ThemeDictionary assemblyUri}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>XAML 对象元素用法  
  
```xml  
<object>  
  <object.property>  
    <ThemeDictionary AssemblyName="assemblyUri"/>  
  <object.property>  
<object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`assemblyUri`|程序集的 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]，其中包含主题信息。 通常，这是一个引用较大包中程序集的 Pack URI。 程序集资源和 Pack URI 可以简化部署问题。 有关详细信息，请参阅 [WPF 中的 Pack URI](../app-development/pack-uris-in-wpf.md)。|  
  
## <a name="remarks"></a>备注  
 此扩展仅用于填充一个特定的<xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>属性值: 值。  
  
 通过使用此扩展, 你可以指定仅限单个资源的程序集, 该程序集包含的某些样式仅在将 Windows Aero 主题应用于用户系统时使用, 其他样式仅在 Luna 主题处于活动状态时如此。 通过使用此扩展，可以自动让特定于控件的资源字典的内容失效，并在需要时重新将其加载为特定于其他主题的内容。  
  
 `assemblyUri`字符串(<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A>属性值) 形成命名约定的基础, 该约定标识哪个字典适用于特定主题。 的<xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> 逻辑通过[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]生成指向特定主题字典变体 (包含在预编译的资源程序集中) 的来完成约定。`ThemeDictionary` 本文并未将该约定（即主题与一般控件样式设置和页/应用程序级样式设置之间的交互）作为一个概念进行详细介绍。 使用`ThemeDictionary`的基本方案是<xref:System.Windows.ResourceDictionary.Source%2A>指定在应用程序级别`ResourceDictionary`声明的的属性。 将 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 通过 `ThemeDictionary` 扩展而不是作为一个直接的 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 提供给程序集时，扩展逻辑将提供系统主题更改时适用的失效逻辑。  
  
 特性语法是最常用于该标记扩展的语法。 在 `ThemeDictionary` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> 扩展类的 <xref:System.Windows.ThemeDictionaryExtension> 值。  
  
 `ThemeDictionary` 还可以在对象元素语法中使用。 在这种情况下, 需要指定<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A>属性的值。  
  
 `ThemeDictionary` 还可以在详细特性用法中使用，以便将 <xref:System.Windows.Markup.StaticExtension.Member%2A> 属性指定为一个 property=value 对：  
  
```xml  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" .../>  
```  
  
 如果扩展具有一个以上的可设置属性，或者某些属性是可选的，则详细用法通常会很有用。 由于 `ThemeDictionary` 仅有一个可设置的属性，并且此属性是必需的，因此该详细用法不具有典型性。  
  
 在处理器实现中, 对此标记<xref:System.Windows.ThemeDictionaryExtension>扩展的处理由类定义。 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]  
  
 `ThemeDictionary` 是标记扩展。 当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。 有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。  
  
## <a name="see-also"></a>请参阅

- [样式设置和模板化](../controls/styling-and-templating.md)
- [XAML 概述 (WPF)](xaml-overview-wpf.md)
- [标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)
- [WPF 应用程序资源、内容和数据文件](../app-development/wpf-application-resource-content-and-data-files.md)
