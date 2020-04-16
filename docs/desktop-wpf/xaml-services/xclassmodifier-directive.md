---
title: x:ClassModifier 指令
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 436204774c2d59b43a77865c666aed702f7681db
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433270"
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier 指令
在提供时`x:Class`修改 XAML 编译行为。 具体而言，提供的不是创建具有`class``Public`访问级别的部分（默认值），而是使用`x:Class``NotPublic`访问级别创建所提供的部分。 此行为会影响生成的程序集中类的访问级别。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a>XAML 值

|||
|-|-|
|*不公开*|要指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>的确切字符串与不同<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>，具体取决于您使用的代码背后的编程语言。 请参阅“备注”。|

## <a name="dependencies"></a>依赖项

[x：类](xclass-directive.md)也必须在同一元素上提供，并且该元素必须是页面中的根元素。 有关详细信息，请参阅[\[MS-XAML\]部分 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))。

## <a name="remarks"></a>备注

.NET `x:ClassModifier` XAML 服务使用中的值因编程语言而异。 要使用的字符串取决于每种语言如何实现其<xref:System.CodeDom.Compiler.CodeDomProvider>和返回的类型转换器来定义<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>和<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>的含义，以及该语言是否区分大小写。

- 对于 C#，要传递到指定的<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>字符串为`internal`。

- 对于 Microsoft Visual Basic .NET，要传递<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>要`Friend`指定的字符串为 。

- 对于C++/CLI，不存在支持编译 XAML 的目标;因此，未指定要传递的值。

您还可以指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>（`public`在 C# 中`Public`，在视觉基础中）;但是，指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>不常执行，因为<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>已是默认行为。

具有等效用户代码访问级别限制的其他值（如`private`C#中）与 XAML`x:ClassModifier`中不支持嵌套类引用无关，因此<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>，修改器具有相同的效果。

## <a name="security-notes"></a>安全说明

中`x:ClassModifier`宣布的访问级别仍受特定框架及其能力的解释。 WPF 包括加载和实例化类型的功能，如果`x:ClassModifier``internal`通过包 URI 引用 WPF 资源引用该类。 由于这种情况，以及可能由其他框架实现的可能其他框架，不完全依赖`x:ClassModifier`来阻止所有可能的实例化尝试。

## <a name="see-also"></a>请参阅

- [x:Class 指令](xclass-directive.md)
- [WPF 中的代码隐藏和 XAML](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:FieldModifier 指令](xfieldmodifier-directive.md)
- [安全性 (WPF)](../../framework/wpf/security-wpf.md)
- [从 WPF 迁移到 System.Xaml 的类型](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
