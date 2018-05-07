---
title: x:Uid 指令
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: 667b722097d091902cb65f2e6f0485a039f8a2ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="xuid-directive"></a>x:Uid 指令
为标记元素提供的唯一标识符。 在许多情况下，由 XAML 本地化过程和工具使用此唯一标识符。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<object x:Uid="identifier"... />  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`identifier`|手动创建或自动生成的字符串，它们应是唯一的文件中时它由解释`x:Uid`使用者。|  
  
## <a name="remarks"></a>备注  
 在 [MS-XAML]，`x:Uid`为指令定义。 有关详细信息，请参阅[ \[MS-XAML\]部分 5.3.6](http://go.microsoft.com/fwlink/?LinkId=114525)。  
  
 `x:Uid` 是从离散`x:Name`同时由于规定的 XAML 本地化方案和以便用于本地化的标识符没有任何依赖关系的编程模型含义`x:Name`。 此外，`x:Name`受 XAML 名称范围; 但是，`x:Uid`不受强制唯一性的任何 XAML 语言定义概念。 广义上讲 （不是在本地化过程的一部分的处理器） 的 XAML 处理器不会强制实现唯一性的`x:Uid`值。 该责任从概念上讲是发起方的值上。 唯一性的假定条件下`x:Uid`单一 XAML 源中的值是合理的值，如专门的全球化过程或工具的使用者。 典型的唯一性模型是：`x:Uid`值都是唯一 XML 编码文件，它表示 XAML 中。  
  
 具有重要知识的特定 XAML 架构的工具可以选择将应用`x:Uid`仅为 true 可本地化的字符串，而不是所有情况下，在标记中遇到一个文本字符串值。  
  
 框架可以在其对象模型，以便为的别名中指定的特定属性`x:Uid`通过在应用特性<xref:System.Windows.Markup.UidPropertyAttribute>到定义的类型。 如果一个框架，指定的特定属性，所以不能同时指定`x:Uid`和对同一对象的别名成员。 如果这两个`x:Uid`和指定的别名成员，.NET Framework XAML 服务 API 通常会引发<xref:System.Xaml.XamlDuplicateMemberException>这种情况下。  
  
## <a name="wpf-usage-notes"></a>WPF 用法说明  
 有关详细信息的角色有关的`x:Uid`WPF 本地化过程中和 XAML 的 BAML 形式中，请参阅[WPF 的全球化](../../../docs/framework/wpf/advanced/globalization-for-wpf.md)或 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
 <xref:Microsoft.Build.Tasks.Windows.UidManager>  
 [WPF 全球化](../../../docs/framework/wpf/advanced/globalization-for-wpf.md)
