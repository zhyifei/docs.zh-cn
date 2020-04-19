---
title: x:Null 标记扩展
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: b83e893f951c15eca69fbb6b002369dd723ca469
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432694"
---
# <a name="xnull-markup-extension"></a>x:Null 标记扩展

指定`null`为 XAML 成员的值。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a>备注

C# 和 C++ 中空引用的关键字为 null。 对于 null 引用的 Microsoft Visual `Nothing`Basic 关键字是`{x:Null}`，但无论与 XAML 关联的代码后面语言如何，您始终用作 XAML 用法。

标记`x:Null`扩展没有可设置属性。

空用法通常与 CLR<xref:System.Nullable%601>值的 XAML 成员暴露相关联。

标记`x:Null`扩展与所有 XAML 标记扩展一样，使用大括号 （`{,}`） 来转义属性值的处理，以非文本或事件处理程序引用。 属性语法是最常用于此标记扩展的语法。 对象元素语法`<x:Null />`在技术上是可能的，但很少使用，`x:Null`因为标记扩展没有位置参数或构造参数。

有关标记扩展的信息，请参阅[标记扩展和 WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)。

在 .NET XAML 服务中，此标记扩展的处理由<xref:System.Windows.Markup.NullExtension>类定义。

## <a name="wpf-usage-notes"></a>WPF 用法说明

请注意，`null`不一定是引用类型依赖项属性的初始未设置值。 初始默认值可能因依赖项属性而异，并且可以基于特定于属性的元数据。 许多依赖项属性不接受`null`作为值，无论是通过标记还是代码，因为它们的验证回调实现。 有关依赖项属性的详细信息，请参阅[依赖项属性概述](../../framework/wpf/advanced/dependency-properties-overview.md)。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [XAML 概述 (WPF)](../fundamentals/xaml.md)
- [标记扩展和 WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
