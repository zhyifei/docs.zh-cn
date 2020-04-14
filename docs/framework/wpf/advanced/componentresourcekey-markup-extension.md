---
title: ComponentResourceKey 标记扩展
ms.date: 03/30/2017
f1_keywords:
- ComponentResourceKey
- ComponentResourceKeyExtension
helpviewer_keywords:
- ComponentResourceKey markup extension [WPF]
- XAML [WPF], ComponentResourceKey markup extension
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
ms.openlocfilehash: 4cdba2a61be4e9686cd2120fd90a213534c222c8
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243357"
---
# <a name="componentresourcekey-markup-extension"></a>ComponentResourceKey 标记扩展
定义和引用从外部程序集加载的资源的键。 这使资源查找能够在程序集中指定目标类型，而不是在程序集或类上指定显式资源字典。  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>XAML 属性用法（设置键，紧凑）  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>XAML 属性用法（设置键，详细）  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>XAML 属性使用（请求资源，紧凑）  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>XAML 属性使用（请求资源，详细）  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`targetTypeName`|在资源程序集中定义的公共通用语言运行时 （CLR） 类型的名称。|  
|`targetID`|资源的键。 当资源被抬起来时`targetID`，将类似于资源的[x：Key 指令](../../../desktop-wpf/xaml-services/xkey-directive.md)。|  
  
## <a name="remarks"></a>备注  
 如上文用法所示，在以下两`ComponentResourceKey`个位置可以找到 [ 标记扩展用法：  
  
- 主题资源字典中键的定义，由控件作者提供。  
  
- 从程序集访问主题资源时，当您重新模板化控件，但希望使用来自控件主题提供的资源的属性值时。  
  
 对于引用来自主题的组件资源，通常建议您使用`{DynamicResource}`而不是`{StaticResource}`。 这在用法中显示。 `{DynamicResource}`建议使用，因为用户可以更改主题本身。 如果希望与控件作者支持主题的意图最匹配的组件资源，则应使组件资源引用也是动态的。  
  
 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>标识目标程序集中存在的类型，其中实际定义了资源。 `ComponentResourceKey`可以定义和使用，而确切知道定义 的位置<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>，但最终必须通过引用的程序集解析类型。  
  
 一个常用法<xref:System.Windows.ComponentResourceKey>种是定义密钥，然后作为类的成员公开。 对于此用法，<xref:System.Windows.ComponentResourceKey>请使用类构造函数，而不是标记扩展名。 有关详细信息，请参阅<xref:System.Windows.ComponentResourceKey>主题["控件创作概述](../controls/control-authoring-overview.md)"中的"主题资源定义和引用键"部分。  
  
 对于建立键和引用键控资源，属性语法通常用于`ComponentResourceKey`标记扩展。  
  
 显示的紧凑语法依赖于标记扩展<xref:System.Windows.ComponentResourceKey.%23ctor%2A>的构造函数签名和位置参数用法。 `targetTypeName`给出 的顺序`targetID`很重要。 详细语法依赖于无<xref:System.Windows.ComponentResourceKey.%23ctor%2A>参数构造函数，然后以类似于对象元素上的真实属性<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>语法<xref:System.Windows.ComponentResourceKey.ResourceId%2A>的方式设置 和。 在详细语法中，属性的设置顺序并不重要。 这两种备选方案的关系和机制（紧凑和详细）在主题[标记扩展和WPF XAML](markup-extensions-and-wpf-xaml.md)中进行了更详细的描述。  
  
 从技术上讲，的值`targetID`可以是任何对象，它不必是字符串。 但是，WPF 中最常见的用法是使`targetID`值与字符串的窗体对齐，以及此类字符串在[XamlName 语法](../../../desktop-wpf/xaml-services/xamlname-grammar.md)中有效的位置。  
  
 `ComponentResourceKey`可用于对象元素语法。 在这种情况下，需要指定<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>和<xref:System.Windows.ComponentResourceKey.ResourceId%2A>属性的值才能正确初始化扩展。  
  
 在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]读取器实现中，此标记扩展的处理由<xref:System.Windows.ComponentResourceKey>类定义。  
  
 `ComponentResourceKey` 是标记扩展。 当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。 有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [控件创作概述](../controls/control-authoring-overview.md)
- [XAML 概述 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)
