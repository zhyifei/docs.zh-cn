---
title: XAML 中的泛型
ms.date: 03/30/2017
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
ms.openlocfilehash: 9354f74b978652c36df28a91a6b9db5cfff4bb1e
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432958"
---
# <a name="generics-in-xaml"></a>XAML 中的泛型

.NET XAML 服务（<xref:System.Xaml?displayProperty=fullName>如实现）支持使用通用 CLR 类型。 此支持包括指定泛型的约束作为类型参数，并通过调用泛型集合案例的适当`Add`方法来强制执行约束。 本主题介绍在 XAML 中使用和引用泛型类型的方面。

## <a name="xtypearguments"></a>x：类型参数

`x:TypeArguments`是由 XAML 语言定义的指令。 当它用作由泛型类型支持的 XAML 类型的成员时，`x:TypeArguments`将泛型的约束类型参数传递给支持构造函数。 有关 与 .NET XAML 服务使用 相关的`x:TypeArguments`引用语法，其中包括语法示例，请参阅[x：TypeArguments 指令](xtypearguments-directive.md)。

由于`x:TypeArguments`采用字符串，并且具有类型转换器支持，因此通常在 XAML 用法中声明为属性。

在 XAML 节点流中，可以从节点`x:TypeArguments`流中`StartObject`的位置获取<xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType>声明的信息。 的返回值<xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType>是值的列表<xref:System.Xaml.XamlType>。 可以通过调用<xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>确定 XAML 类型是否表示泛型类型。

## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a>XAML 中泛型的规则和语法约定

在 XAML 中，泛型类型必须始终表示为受约束的泛型。 无约束泛型永远不会存在于 XAML 类型系统或 XAML 节点流中，并且不能在 XAML 标记中表示。 泛型可以在 XAML 属性语法中引用，用于对于泛型是 被`x:TypeArguments`引用的泛型的嵌套类型约束的情况，或者对于`x:Type`为泛型类型提供 CLR 类型引用的情况。 通过 .NET XAML<xref:System.Xaml.Schema.XamlTypeTypeConverter>服务定义的类支持引用泛型。

XAML 属性语法窗体通过<xref:System.Xaml.Schema.XamlTypeTypeConverter>更改典型的 MSIL/ CLR 语法约定而启用，该约定使用角度括号来表示泛型的类型和约束，而是替换约束容器的括号。 例如，请参阅[x：Type参数指令](xtypearguments-directive.md)。

## <a name="generics-and-xaml-2009-features"></a>泛型和 XAML 2009 功能

如果使用 XAML 2009 而不是映射 CLR 基类型以获取通用语言基元中的 XAML 类型，则可以使用[XAML 2009 内置类型](types-for-primitives.md)作为 中`x:TypeArguments`的信息项。 例如，您可以声明以下内容（未显示前缀映射，但`x`XAML 语言 XAML 2009 的命名空间）：

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

## <a name="generics-support-in-wpf"></a>WPF 中的通用支持

对于专门针对 WPF 的 XAML 2006 用法，x：class 还必须[x:Class](xclass-directive.md)提供`x:TypeArguments`与 的元素，并且该元素必须是 XAML 文档中的根元素。 根元素必须映射到具有至少一个类型参数的泛型类型。 示例为 <xref:System.Windows.Navigation.PageFunction%601>。

支持泛型用法的可能解决方法包括定义可以返回泛型类型的自定义标记扩展，或提供从泛型类型派生但在其自己的类定义中平展泛型约束的换行类定义。

在 WPF 中，您可以将 XAML 2009 功能与 一起使用`x:TypeArguments`，但仅适用于松散的 XAML（未标记编译的 XAML）。 WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。

.NET 框架 3.5 的 Windows 工作流基础中的自定义工作流不支持通用的 XAML 使用。

## <a name="see-also"></a>请参阅

- [x:TypeArguments 指令](xtypearguments-directive.md)
- [x:Class 指令](xclass-directive.md)
- [常见 XAML 语言基元的内置类型](types-for-primitives.md)
