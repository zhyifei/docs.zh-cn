---
title: x:Array 标记扩展
ms.date: 03/30/2017
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
ms.openlocfilehash: b332c43d7f9ffe2117c9afe1ed625c3e3c869813
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433282"
---
# <a name="xarray-markup-extension"></a>x:Array 标记扩展

通过标记扩展为 XAML 中的对象数组提供常规支持。 这对应于 [MS-XAML] 中的`x:ArrayExtension`XAML 类型。

## <a name="xaml-object-element-usage"></a>XAML 对象元素用法

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a>XAML 值

|||
|-|-|
|`typeName`|将`x:Array`包含的类型的名称。 `typeName`对于包含 XAML 类型定义的 XAML 命名空间，可能（而且通常是）预固定。|
|`arrayContents`|分配给内部`ArrayExtension.Items`属性的项内容。 通常，这些项目被指定为`x:Array`打开和关闭标记中包含的一个或多个对象元素。 此处指定的对象应可分配给 中`typeName`指定的 XAML 类型。|

## <a name="remarks"></a>备注

`Type`是所有`x:Array`对象元素的必需属性。 参数`Type`值不需要使用`x:Type`标记扩展，因此参数值不需要使用标记扩展。类型的短名称是 XAML 类型，可以指定为字符串。

在 .NET XAML 服务实现中，输入 XAML 类型和创建数组<xref:System.Type>的输出 CLR 之间的关系受标记扩展的服务上下文的影响。 输出<xref:System.Type>是<xref:System.Xaml.XamlType.UnderlyingType%2A>输入 XAML 类型的输出，在根据 XAML<xref:System.Xaml.XamlType>架构上下文和<xref:System.Windows.Markup.IXamlTypeResolver>上下文提供的服务查找所需的结果后。

处理时，数组内容将分配给`ArrayExtension.Items`内部属性。 在实现中<xref:System.Windows.Markup.ArrayExtension>，这由 表示<xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>。

在 .NET XAML 服务实现中，此标记扩展的处理由<xref:System.Windows.Markup.ArrayExtension>类定义。 <xref:System.Windows.Markup.ArrayExtension>不密封，可用作自定义数组类型的标记扩展实现的基础。

`x:Array`更适用于 XAML 中的一般语言扩展性。 但是`x:Array`，对于指定某些属性的 XAML 值也很有用，这些属性将 XAML 支持的集合作为其结构化属性内容。 例如，可以指定具有<xref:System.Collections.IEnumerable>`x:Array`用法的属性的内容。

`x:Array` 是标记扩展。 当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。 `x:Array`部分是该规则的一个例外，因为不提供替代属性值处理，`x:Array`而是提供对其内部文本内容的替代处理。 此行为允许将现有内容模型可能不支持的类型分组到数组中，并在稍后通过访问命名数组在代码后面引用;您可以调用<xref:System.Array>方法来获取单个数组项。

XAML 中的所有标记扩展都使用大括号（{,}`)`在其属性语法中，这是 XAML 处理器识别标记扩展必须处理属性值的约定）。 有关标记扩展的详细信息，请参阅[XAML 的类型转换器和标记扩展](type-converters-and-markup-extensions.md)。

在 XAML 2009 中，`x:Array`定义为语言基元而不是标记扩展。 有关详细信息，请参阅常见[XAML 语言基元的内置类型](types-for-primitives.md)。

## <a name="wpf-usage-notes"></a>WPF 用法说明

通常，填充 的对象元素`x:Array`不是[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]XAML 命名空间中存在的元素，需要前缀映射到非默认 XAML 命名空间。

例如，下面是两个字符串的简单数组，`sys`前缀 （和 也`x`） 在数组的级别上定义。

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

对于用作数组元素的自定义类型，类还必须支持在 XAML 中实例化为对象元素的要求。 有关详细信息，请参阅[WPF 的 XAML 和自定义类](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)。

## <a name="see-also"></a>请参阅

- [标记扩展和 WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [从 WPF 迁移到 System.Xaml 的类型](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
