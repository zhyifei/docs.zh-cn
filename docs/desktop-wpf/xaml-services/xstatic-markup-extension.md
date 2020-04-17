---
title: x:Static 标记扩展
ms.date: 03/30/2017
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
ms.openlocfilehash: fb9ee6807135f17fd9e0c799533bba28b369ebe2
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433264"
---
# <a name="xstatic-markup-extension"></a>x:Static 标记扩展

引用以通用语言规范 （CLS） 兼容方式定义的任何静态按值代码实体。 引用的静态属性可用于在 XAML 中提供属性的值。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<object property="{x:Static prefix:typeName.staticMemberName}" .../>
```

## <a name="xaml-values"></a>XAML 值

| | |
|-|-|
|`prefix`|可选。 指映射的非默认 XAML 命名空间的前缀。 `prefix`在用法中显式显示，因为很少引用来自默认 XAML 命名空间的静态属性。 请参阅“备注”。|
|`typeName`|必需。 定义所需静态成员的类型的名称。|
|`staticMemberName`|必需。 所需静态值成员（常量、静态属性、字段或枚举值）的名称。|

## <a name="remarks"></a>备注

引用的代码实体必须是以下类型之一：

- 常量
- 静态属性
- 字段
- 枚举值

如果编译了 XAML，或者 XAML 加载时间分析异常，则指定任何其他代码实体（如非静态属性）会导致编译时错误。

您可以`x:Static`引用当前 XAML 文档的默认 XAML 命名空间中未包含的静态字段或属性;但是，这需要前缀映射。 XAML 命名空间几乎总是在 XAML 文档的根元素上定义。

静态属性的查找操作可以由 .NET XAML 服务及其 XAML 读取器和 XAML 编写器执行，当它们使用默认的 XAML 架构上下文运行时。 此 XAML 架构上下文可以使用 CLR 反射为对象图形构造提供必要的静态值。 `typeName`您指定的实际上是一个 XAML 类型名称，而不是 CLR 类型名称，尽管在使用默认 XAML 架构上下文或使用所有基于 CLR 的 XAML 实现框架时，这些名称本质上是相同的名称。

当您进行`x:Static`不是属性值类型的引用时，应小心谨慎。 在 XAML 处理序列中，从标记扩展提供的值不会调用附加值转换。 即使引用`x:Static`创建了文本字符串，也是如此，并且通常针对该特定成员或返回类型的任何成员值对基于文本字符串的属性值进行值转换。

特性语法是最常用于该标记扩展的语法。 在 `x:Static` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.Markup.StaticExtension.Member%2A> 扩展类的 <xref:System.Windows.Markup.StaticExtension> 值。

技术上可能还有其他两个 XAML 用法。 但是，这些用法不太常见，因为它们是不必要的冗长：

01. 对象元素语法。

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

02. 具有显式成员属性的属性语法，用于初始化字符串。

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

在 .NET XAML 服务实现中，此标记扩展的处理由<xref:System.Windows.Markup.StaticExtension>类定义。

`x:Static` 是标记扩展。 XAML 中的所有标记扩展在其属性语法中使用`{``}`和 字符，这是 XAML 处理器识别标记扩展必须提供值的约定。 有关标记扩展的详细信息，请参阅 [Markup Extensions for XAML Overview](markup-extensions-overview.md)。

## <a name="wpf-usage-notes"></a>WPF 用法说明

用于 WPF 编程的默认 XAML 命名空间不包含许多有用的静态属性，并且大多数有用的静态属性都支持，例如类型转换器，无需即可`{x:Static}`方便使用。 对于静态属性，如果以下原因之一为 true，则必须映射 XAML 命名空间的前缀：

- 您引用的类型存在于 WPF 中，但不是 WPF （ 的`http://schemas.microsoft.com/winfx/2006/xaml/presentation`默认 XAML 命名空间的一部分）。 这是使用`x:Static`的相当常见的方案。 例如，可以使用具有`x:Static`XAML 命名空间映射到<xref:System>CLR 命名空间和 mscorlib 程序集的引用，以便引用类的<xref:System.Environment>静态属性。

- 您正在引用自定义程序集中的类型。

- 您引用的类型存在于 WPF 程序集中，但该类型位于未映射到 WPF 默认 XAML 命名空间的 CLR 命名空间中。 CLR 命名空间映射到 WPF 的默认 XAML 命名空间由各种 WPF 程序集中的定义执行（有关此概念的详细信息，请参阅[WPF XAML 的 XAML 命名空间和命名空间映射](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)）。 如果 CLR 命名空间主要由通常不用于 XAML 的类定义组成，则存在非映射 CLR 命名空间，例如<xref:System.Windows.Threading>。

有关如何为 WPF 使用前缀和 XAML 命名空间的详细信息，请参阅[WPF XAML 的 XAML 命名空间和命名空间映射](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)。

## <a name="see-also"></a>请参阅

- [x:Type 标记扩展](xtype-markup-extension.md)
- [从 WPF 迁移到 System.Xaml 的类型](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
