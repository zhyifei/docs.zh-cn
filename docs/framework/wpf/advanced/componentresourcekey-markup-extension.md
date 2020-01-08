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
ms.openlocfilehash: 2ccc4f3154996a4e442a4092833f5c9ed9c8938a
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559456"
---
# <a name="componentresourcekey-markup-extension"></a>ComponentResourceKey 标记扩展
定义和引用从外部程序集加载的资源的键。 这使得资源查找可以在程序集中指定目标类型，而不是在程序集或类中指定显式资源字典。  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>XAML 特性用法（设置键，compact）  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>XAML 特性用法（设置键，详细）  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>XAML 特性用法（请求资源，compact）  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>XAML 特性用法（请求资源，详细）  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`targetTypeName`|在资源程序集中定义的公共公共语言运行时（CLR）类型的名称。|  
|`targetID`|资源的键。 查找资源时，`targetID` 将类似于资源的 " [x：Key" 指令](../../../desktop-wpf/xaml-services/xkey-directive.md)。|  
  
## <a name="remarks"></a>备注  
 如以上用法中所示，在以下两个位置找到了 {`ComponentResourceKey`} 标记扩展用法：  
  
- 主题资源字典中的键的定义，由控件作者提供。  
  
- 在重新模板化控件时访问程序集中的主题资源，但需要使用由控件主题提供的资源提供的属性值。  
  
 对于引用主题中的组件资源，通常建议使用 `{DynamicResource}` 而不是 `{StaticResource}`。 用法中显示了这种情况。 建议 `{DynamicResource}`，因为用户可以更改主题本身。 如果希望组件资源与控件作者为支持主题最匹配，则应使组件资源引用也是动态的。  
  
 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 标识在实际定义资源的目标程序集中存在的类型。 可以独立地定义和使用 `ComponentResourceKey`，只需知道 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 的定义位置，但最终必须通过引用的程序集解析类型。  
  
 <xref:System.Windows.ComponentResourceKey> 的常见用法是定义随后公开为类成员的键。 为此，请使用 <xref:System.Windows.ComponentResourceKey> 类构造函数，而不是标记扩展。 有关详细信息，请参阅主题[控件创作概述](../controls/control-authoring-overview.md)的 <xref:System.Windows.ComponentResourceKey>或 "定义和引用主题资源的键" 一节。  
  
 对于建立密钥和引用键控资源，特性语法通常用于 `ComponentResourceKey` 标记扩展。  
  
 所示的压缩语法依赖于标记扩展的 <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> 构造函数签名和位置参数用法。 `targetTypeName` 和 `targetID` 的给定顺序非常重要。 详细语法依赖于 <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> 无参数的构造函数，然后以与 object 元素上的 true 特性语法类似的方式设置 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 和 <xref:System.Windows.ComponentResourceKey.ResourceId%2A>。 在详细语法中，设置属性的顺序并不重要。 主题[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)中更详细地介绍了这两种备选方法（简洁和详细）的关系和机制。  
  
 从技术上说，`targetID` 的值可以是任何对象，不一定是字符串。 不过，WPF 最常见的用法是将 `targetID` 值与字符串形式的窗体进行对齐，并在[XamlName 语法](../../../desktop-wpf/xaml-services/xamlname-grammar.md)中使用此类字符串。  
  
 `ComponentResourceKey` 可以在对象元素语法中使用。 在这种情况下，需要指定 "<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>" 和 "<xref:System.Windows.ComponentResourceKey.ResourceId%2A>" 属性的值才能正确地初始化扩展。  
  
 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 读取器实现中，对此标记扩展的处理由 <xref:System.Windows.ComponentResourceKey> 类定义。  
  
 `ComponentResourceKey` 是标记扩展。 当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。 有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [控件创作概述](../controls/control-authoring-overview.md)
- [XAML 概述 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)
