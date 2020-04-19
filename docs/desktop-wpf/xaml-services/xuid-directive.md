---
title: x:Uid 指令
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: b5b480016d2183268422dea861510c6a169ac27b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432616"
---
# <a name="xuid-directive"></a>x:Uid 指令

为标记元素提供一个唯一标识符。 在许多情况下，XAML 本地化过程和工具都使用此唯一标识符。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<object x:Uid="identifier"... />
```

## <a name="xaml-values"></a>XAML 值

|||
|-|-|
|`identifier`|手动创建或自动生成的字符串，当使用者解释该文件时，该字符串在文件中应是唯一的`x:Uid`。|

## <a name="remarks"></a>备注

在 [MS-XAML]`x:Uid`中，定义为指令。 有关详细信息，请参阅[\[MS-XAML\]部分 5.3.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))。

`x:Uid`由于所述的`x:Name`XAML 本地化方案，并且用于本地化的标识符对 的编程模型含义没有依赖关系，因此与 这两种情况是离散`x:Name`的。 此外，`x:Name`受 XAML 名称范围控制;但是，`x:Uid`不受任何 XAML 语言定义的唯一性实施概念的约束。 广义的 XAML 处理器（不属于本地化过程的处理器）不应强制实施`x:Uid`值的唯一性。 这种责任在概念上取决于价值观的发起者。 对于值（如专用的`x:Uid`全球化过程或工具）的消费者来说，对单个 XAML 源中值的唯一性的期望是合理的。 典型的唯一性模型是值`x:Uid`在表示 XAML 的 XML 编码文件中是唯一的。

对特定 XAML 架构有重大了解的工具可以选择仅应用于`x:Uid`真正的可本地化字符串，而不是应用于标记中遇到文本字符串值的所有情况。

框架可以通过将属性`x:Uid`<xref:System.Windows.Markup.UidPropertyAttribute>应用于定义类型来指定其对象模型中的特定属性为别名。 如果框架指定特定属性，则在同一对象上指定和`x:Uid`别名成员无效。 如果同时`x:Uid`指定了两个成员和别名成员，则 .NET XAML<xref:System.Xaml.XamlDuplicateMemberException>服务 API 通常会为此情况引发。

## <a name="wpf-usage-notes"></a>WPF 用法说明

有关 WPF 本地化过程`x:Uid`和 XAML BAML 形式中的角色的详细信息，请参阅[WPF 的全球化](../../framework/wpf/advanced/globalization-for-wpf.md)或<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [WPF 的全球化](../../framework/wpf/advanced/globalization-for-wpf.md)
