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
ms.openlocfilehash: df0b3fe53cb8f284fc6e2d79a9b2cea86318d701
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459916"
---
# <a name="xtype-markup-extension"></a>x:Type 标记扩展
为指定的 XAML 类型的基础类型 <xref:System.Type> 提供 CLR。  
  
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
|`typeNameValue`|必须的。 可解析为当前默认 XAML 命名空间的类型名称;如果提供 `prefix`，则为指定的映射前缀。|  
  
## <a name="remarks"></a>备注  
 `x:Type` 标记扩展在C# `typeof()` 运算符与 Microsoft Visual Basic 中的 `GetType` 运算符具有类似的函数。  
  
 `x:Type` 标记扩展为采用类型 <xref:System.Type>的属性提供 from 字符串转换行为。 输入为 XAML 类型。 输入 XAML 类型和输出 CLR <xref:System.Type> 之间的关系是，输出 <xref:System.Type> 是输入 <xref:System.Xaml.XamlType>的 <xref:System.Xaml.XamlType.UnderlyingType%2A>，在基于 XAML 架构上下文和上下文提供的 <xref:System.Xaml.XamlType> 服务查找必需的 <xref:System.Windows.Markup.IXamlTypeResolver> 之后。  
  
 在 .NET Framework XAML 服务中，此标记扩展的处理由 <xref:System.Windows.Markup.TypeExtension> 类定义。  
  
 在特定的框架实现中，某些采用作为值 <xref:System.Type> 的属性可以直接接受类型的名称（`Name`的字符串值）。 但是，实现此行为是一种复杂的方案。 有关示例，请参阅后面的 "WPF 用法说明" 部分。  
  
 特性语法是最常用于该标记扩展的语法。 在 `x:Type` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 扩展类的 <xref:System.Windows.Markup.TypeExtension> 值。 在基于 CLR 类型 .NET Framework XAML 服务的默认 XAML 架构上下文下，此属性的值是所需类型的 <xref:System.Reflection.MemberInfo.Name%2A>，或包含 <xref:System.Reflection.MemberInfo.Name%2A> 前面带有非默认 XAML 命名空间映射的前缀。  
  
 可以在对象元素语法中使用 `x:Type` 标记扩展。 在这种情况下，必须指定 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 属性的值才能正确地初始化扩展。  
  
 `x:Type` 标记扩展还可用作详细特性;但这种用法并不典型： `<object property="{x:Type TypeName=typeNameValue}" .../>`  
  
## <a name="wpf-usage-notes"></a>WPF 使用说明  
  
### <a name="default-xaml-namespace-and-type-mapping"></a>默认 XAML 命名空间和类型映射  
 WPF 编程的默认 XAML 命名空间包含典型 XAML 方案所需的大多数 XAML 类型;因此，在引用 XAML 类型值时，通常可以避免前缀。 如果引用的是自定义程序集的类型或存在于 WPF 程序集中的类型，但却来自未映射到默认 XAML 命名空间的 CLR 命名空间，则可能需要映射前缀。 有关前缀、XAML 命名空间和映射 CLR 命名空间的详细信息，请参阅[WPF xaml 的 XAML 命名空间和命名空间映射](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)。  
  
### <a name="type-properties-that-support-typename-as-string"></a>支持类型为字符串的类型属性  
 WPF 支持用于指定 <xref:System.Type> 类型的某些属性的值，而无需 `x:Type` 标记扩展用法的技术。 相反，你可以将值指定为命名类型的字符串。 <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>示例。 不通过类型转换器或标记扩展提供对此行为的支持。 相反，这是通过 <xref:System.Windows.FrameworkElementFactory>实现的延迟行为。  
  
 Silverlight 支持类似的约定。 事实上，Silverlight 目前不支持其 XAML 语言支持 `{x:Type}`，并且在用于支持 WPF Silverlight XAML 迁移的少数情况下，不接受 `{x:Type}` 使用。 因此，类型名称字符串行为内置于所有 Silverlight 本机属性评估中，其中 <xref:System.Type> 是值。  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 提供对泛型类型的其他支持，并修改 `x:TypeArguments` 和 `x:Type` 的功能行为以提供此支持。  
  
- 泛型对象实例化的 `x:TypeArguments` 和关联的对象元素可以位于根以外的元素上。 有关详细信息，请参阅[X:TypeArguments 指令](x-typearguments-directive.md)的 "XAML 2009" 一节。  
  
- XAML 2009 支持用于在标记中指定泛型类型的约束的语法。 这可由 `x:TypeArguments`、`x:Type`或组合的两个功能使用。  
  
- 当处理 XAML 2009 for load 时，WPF XAML 实现还会将此功能添加到使用类型 <xref:System.Type>的某些框架属性的隐式类型转换行为。  
  
 在 WPF 中，可以使用 XAML 2009 功能，但仅适用于松散 XAML （未进行标记编译的 XAML）。 WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Style>
- [样式设置和模板化](../wpf/controls/styling-and-templating.md)
- [XAML 概述 (WPF)](../../desktop-wpf/fundamentals/xaml.md)
- [标记扩展和 WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
