---
title: x:Type 标记扩展
ms.date: 03/30/2017
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
ms.openlocfilehash: f75d4e30dc41bbce995e466466c96c1a2830949b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432634"
---
# <a name="xtype-markup-extension"></a>x:Type 标记扩展

提供 CLR<xref:System.Type>对象，该对象是指定 XAML 类型的基础类型。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<object property="{x:Type prefix:typeNameValue}" .../>
```

## <a name="xaml-object-element-usage"></a>XAML 对象元素用法

```xaml
<x:Type TypeName="prefix:typeNameValue"/>
```

## <a name="xaml-values"></a>XAML 值

|||
|-|-|
|`prefix`|可选。 映射非默认 XAML 命名空间的前缀。 通常不需要指定前缀。 请参阅“备注”。|
|`typeNameValue`|必需。 可解析为当前默认 XAML 命名空间的类型名称;或指定的映射前缀（如果`prefix`提供）。|

## <a name="remarks"></a>备注

标记`x:Type`扩展具有与 C# 中的`typeof()`运算符或 Microsoft Visual `GetType` Basic 中的运算符类似的功能。

标记`x:Type`扩展为采用 类型<xref:System.Type>的属性提供从字符串转换行为。 输入是 XAML 类型。 输入 XAML<xref:System.Type>类型和输出 CLR 之间的关系是输出<xref:System.Type>是输入<xref:System.Xaml.XamlType.UnderlyingType%2A><xref:System.Xaml.XamlType>的输出，在根据 XAML 架构<xref:System.Xaml.XamlType>上下文和<xref:System.Windows.Markup.IXamlTypeResolver>上下文提供的服务查找必要的结果后。

在 .NET XAML 服务中，此标记扩展的处理由<xref:System.Windows.Markup.TypeExtension>类定义。

在特定框架实现中，某些作为<xref:System.Type>值的属性可以直接接受类型的名称（类型的`Name`字符串值）。 但是，实现此行为是一个复杂的方案。 有关示例，请参阅后面的"WPF 使用说明"部分。

特性语法是最常用于该标记扩展的语法。 在 `x:Type` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 扩展类的 <xref:System.Windows.Markup.TypeExtension> 值。 在基于 CLR 类型的 .NET XAML 服务的默认 XAML 架构上下文中，此属性的值是<xref:System.Reflection.MemberInfo.Name%2A>所需类型的，或者包含<xref:System.Reflection.MemberInfo.Name%2A>非默认 XAML 命名空间映射的前缀。

标记`x:Type`扩展可用于对象元素语法。 在这种情况下，需要指定<xref:System.Windows.Markup.TypeExtension.TypeName%2A>属性的值才能正确初始化扩展。

标记`x:Type`扩展也可以用作详细属性;但是，此用途并不常见：`<object property="{x:Type TypeName=typeNameValue}" .../>`

## <a name="wpf-usage-notes"></a>WPF 用法说明

### <a name="default-xaml-namespace-and-type-mapping"></a>默认 XAML 命名空间和类型映射

WPF 编程的默认 XAML 命名空间包含典型 XAML 方案所需的大多数 XAML 类型;因此，在引用 XAML 类型值时，通常可以避免前缀。 如果要从自定义程序集引用类型或 WPF 程序集中存在但来自未映射到默认 XAML 命名空间的 CLR 命名空间的类型，则可能需要映射前缀。 有关前缀、XAML 命名空间和映射 CLR 命名空间的详细信息，请参阅[WPF XAML 的 XAML 命名空间和命名空间映射](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)。

### <a name="type-properties-that-support-typename-as-string"></a>类型属性支持类型名称作为字符串

WPF 支持启用指定某些类型<xref:System.Type>属性的值而无需`x:Type`标记扩展用的技术。 相反，您可以将该值指定为命名类型的字符串。 这方面的示例是<xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType>和<xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>。 不支持此行为不会通过类型转换器或标记扩展提供。 相反，这是通过<xref:System.Windows.FrameworkElementFactory>实现的延迟行为。

银光支持类似的约定。 事实上，Silverlight 目前不支持`{x:Type}`其 XAML 语言支持，并且不接受`{x:Type}`用于支持 WPF-Silverlight XAML 迁移的少数情况以外的用法。 因此，类型名称即字符串行为内置于所有 Silverlight 本机属性计算中， <xref:System.Type>

## <a name="xaml-2009"></a>XAML 2009

XAML 2009 为泛型类型提供了其他支持，并修改了`x:TypeArguments`和`x:Type`的功能行为，并提供此支持。

- `x:TypeArguments`泛型对象实例化的关联对象元素可以位于根以外的元素上。 有关详细信息，请参阅[x：Type参数指令](xtypearguments-directive.md)的"XAML 2009"部分。

- XAML 2009 支持用于在标记中指定泛型类型约束的语法。 这可以通过`x:TypeArguments`、由`x:Type`或两个要素组合使用。

- 处理 XAML 2009 负载时实现的 WPF XAML 也会将此功能添加到使用 类型 的某些<xref:System.Type>框架属性的隐式类型转换行为中。

在 WPF 中，可以使用 XAML 2009 功能，但仅适用于松散的 XAML（未标记编译的 XAML）。 WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Style>
- [样式设置和模板化](../fundamentals/styles-templates-overview.md)
- [XAML 概述 (WPF)](../fundamentals/xaml.md)
- [标记扩展和 WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
