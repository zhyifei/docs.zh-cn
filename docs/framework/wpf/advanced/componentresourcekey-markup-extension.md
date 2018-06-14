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
ms.openlocfilehash: d11c26add084165eaa9fd0b319a375c4b98c7fb9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540405"
---
# <a name="componentresourcekey-markup-extension"></a>ComponentResourceKey 标记扩展
定义和引用从外部程序集加载的资源键。 这使得资源查找功能可以在一个程序集，而不是在程序集或在类上的显式资源字典中指定的目标类型。  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>XAML 属性用法 （设置键，compact）  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>（设置键、 详细） 的 XAML 属性用法  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>XAML 属性用法 （请求资源，compact）  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>XAML 属性用法 （请求资源，详细）  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`targetTypeName`|公共名称[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]中的资源程序集定义的类型。|  
|`targetID`|资源键。 当资源查找时，`targetID`将类似于[X:key 指令](../../../../docs/framework/xaml-services/x-key-directive.md)的资源。|  
  
## <a name="remarks"></a>备注  
 如上面的用法中所示 {`ComponentResourceKey`} 标记扩展用法在两个位置中找到：  
  
-   内主题资源字典，由控件作者提供的键的定义。  
  
-   从程序集访问主题资源，当你是重新模板化控件，但想要使用来自控件的主题提供资源的属性值。  
  
 用于引用来自主题的组件资源，通常建议您使用`{DynamicResource}`而非`{StaticResource}`。 这是与用法中所示。 `{DynamicResource}` 建议，因为用户可以更改主题本身。 如果你想存储组件资源与支持该主题的控件作者意向最相匹配，则应启用组件资源参考，用于也会动态。  
  
 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>标识存在于实际定义资源所在的目标程序集的类型。 A`ComponentResourceKey`可以定义和使用独立于完全了解其中<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>已定义，但最终必须解决通过引用的程序集的类型。  
  
 常见用法<xref:System.Windows.ComponentResourceKey>是定义为类的成员的然后公开的密钥。 对于此用法中，你使用<xref:System.Windows.ComponentResourceKey>类构造函数，不是标记扩展。 有关详细信息，请参阅<xref:System.Windows.ComponentResourceKey>，或主题的"定义和引用主题资源的键"部分[控件创作概述](../../../../docs/framework/wpf/controls/control-authoring-overview.md)。  
  
 有关建立键和引用键控资源，特性语法通常用于`ComponentResourceKey`标记扩展。  
  
 所示的紧凑语法依赖于<xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType>构造函数签名和标记扩展的位置参数用法。 顺序`targetTypeName`和`targetID`提供非常重要。 详细语法依赖于<xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType>默认构造函数，然后设置<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>和<xref:System.Windows.ComponentResourceKey.ResourceId%2A>类似于的对象元素上的实际特性语法的方式。 在详细的语法中，将设置其属性的顺序并不重要。 主题中的更多详细信息中所述的关系和以下两个替代方法 （compact 和详细） 机制[标记扩展和 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)。  
  
 从技术上讲，值`targetID`可以是任何对象，它没有为一个字串符。 但是，在 WPF 中的最常见用法是对齐`targetID`窗体，是字符串，且此类字符串是在中有效的值[XamlName 语法](../../../../docs/framework/xaml-services/xamlname-grammar.md)。  
  
 `ComponentResourceKey` 可在对象元素语法。 在这种情况下，指定的值都<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>和<xref:System.Windows.ComponentResourceKey.ResourceId%2A>正确初始化扩展所需的属性。  
  
 在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]读取器实现，对此标记扩展的处理定义的<xref:System.Windows.ComponentResourceKey>类。  
  
 `ComponentResourceKey` 是标记扩展。 当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。 有关详细信息，请参阅[标记扩展和 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.ComponentResourceKey>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [控件创作概述](../../../../docs/framework/wpf/controls/control-authoring-overview.md)  
 [XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [标记扩展和 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
