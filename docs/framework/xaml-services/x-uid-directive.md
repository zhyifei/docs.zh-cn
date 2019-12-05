---
title: x:Uid 指令
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: 32cfd9ab0cf6037c731b619e81a7504ac92d5fb9
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837176"
---
# <a name="xuid-directive"></a>x:Uid 指令
为标记元素提供一个唯一标识符。 在许多情况下，XAML 本地化流程和工具使用此唯一标识符。  
  
## <a name="xaml-attribute-usage"></a>XAML 特性用法  
  
```xaml  
<object x:Uid="identifier"... />  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`identifier`|手动创建或自动生成的字符串，当 `x:Uid` 使用者对其进行解释时，它应在文件中是唯一的。|  
  
## <a name="remarks"></a>备注  
 在 [MS-CHAP] 中，`x:Uid` 定义为指令。 有关详细信息，请参阅[\[MS-XAML\] 部分 5.3.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))。  
  
 由于所述的 XAML 本地化方案，`x:Uid` 与 `x:Name` 是离散的，因此用于本地化的标识符不依赖于 `x:Name`的编程模型含义。 此外，`x:Name` 由 XAML 名称范围控制;但 `x:Uid` 不受任何 XAML 语言定义的唯一性强制概念的约束。 一般意义上的 XAML 处理器（不是本地化过程的一部分的处理器）不应强制实施 `x:Uid` 值的唯一性。 从概念上讲，这种责任在值的发起方。 单个 XAML 源中 `x:Uid` 值的唯一性假定对于值的使用者（如专用的全球化过程或工具）是合理的。 典型的唯一性模型是，`x:Uid` 值在表示 XAML 的 XML 编码文件中是唯一的。  
  
 对于特定 XAML 架构具有重要了解的工具，可以选择仅将 `x:Uid` 应用于真正可本地化的字符串，而不是用于标记中出现文本字符串值的所有情况。  
  
 框架可以通过将特性 <xref:System.Windows.Markup.UidPropertyAttribute> 应用于定义类型，将其对象模型中的特定属性指定为 `x:Uid` 的别名。 如果框架指定了特定属性，则在同一对象上同时指定 `x:Uid` 和化名成员是无效的。 如果同时指定 `x:Uid` 和化名成员，则 .NET Framework XAML 服务 API 通常会在这种情况下引发 <xref:System.Xaml.XamlDuplicateMemberException>。  
  
## <a name="wpf-usage-notes"></a>WPF 使用说明  
 有关 WPF 本地化过程中的 `x:Uid` 角色以及 XAML 的 BAML 形式的详细信息，请参阅[wpf 的全球化](../wpf/advanced/globalization-for-wpf.md)或 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [WPF 全球化](../wpf/advanced/globalization-for-wpf.md)
