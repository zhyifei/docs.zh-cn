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
ms.openlocfilehash: bf94f1d61ee3080c9d3582e55e0695b269801c80
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733358"
---
# <a name="xstatic-markup-extension"></a>x:Static 标记扩展
引用以符合公共语言规范（CLS）的方式定义的任何静态按值的代码实体。 引用的静态属性可用于在 XAML 中提供属性的值。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
| | |  
|-|-|  
|`prefix`|可选。 引用映射的非默认 XAML 命名空间的前缀。 由于很少引用来自默认 XAML 命名空间的静态属性，因此在用法中显式显示了 `prefix`。 请参阅“备注”。|  
|`typeName`|必须的。 定义所需静态成员的类型的名称。|  
|`staticMemberName`|必须的。 所需的静态值成员的名称（常量、静态属性、字段或枚举值）。|  
  
## <a name="remarks"></a>备注  

引用的代码实体必须是以下项之一：  
  
- 常量  
- 静态属性  
- 一个字段  
- 枚举值

如果指定任何其他代码实体（如非静态属性），则会导致编译时错误，如果已编译了 XAML 或 XAML 加载时分析异常，则会引发编译时错误。  

您可以对当前 XAML 文档的默认 XAML 命名空间中不是的静态字段或属性进行 `x:Static` 引用;但是，这需要前缀映射。 XAML 命名空间几乎始终在 XAML 文档的根元素上定义。  

当 XAML 服务及其 XAML 读取器和 XAML 编写器运行时，可 .NET Framework 通过默认的 XAML 架构上下文来执行静态属性的查找操作。 此 XAML 架构上下文可以使用 CLR 反射为对象图构造提供必要的静态值。 指定的 `typeName` 实际上是 XAML 类型名称，而不是 CLR 类型名称，不过，在使用默认 XAML 架构上下文或使用所有基于 CLR 的现有 XAML 实现框架时，这些名称本质上是相同的名称。  

当你 `x:Static` 不直接是属性值的类型的引用时，请小心。 在 XAML 处理序列中，从标记扩展提供的值不会调用其他值转换。 即使 `x:Static` 引用创建了文本字符串，并且基于文本字符串的属性值的值转换通常出现在该特定成员或返回类型的任何成员值中时，也是如此。  

特性语法是最常用于该标记扩展的语法。 在 `x:Static` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.Markup.StaticExtension.Member%2A> 扩展类的 <xref:System.Windows.Markup.StaticExtension> 值。  

还有其他两个在技术上可能的 XAML 用法。 不过，这些用法不太常见，因为它们不太必要：  

1. 对象元素语法。

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

2. 带有用于初始化字符串的显式成员属性的特性语法。

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

在 .NET Framework XAML 服务实现中，对此标记扩展的处理由 <xref:System.Windows.Markup.StaticExtension> 类定义。  

`x:Static` 是标记扩展。 XAML 中的所有标记扩展在其特性语法中使用 `{` 和 `}` 字符，这是 XAML 处理器识别标记扩展必须提供值的约定。 有关标记扩展的详细信息，请参阅 [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md)。  
  
## <a name="wpf-usage-notes"></a>WPF 使用说明  
 用于 WPF 编程的默认 XAML 命名空间不包含很多有用的静态属性，并且大多数有用的静态属性都具有支持，如可在不需要 `{x:Static}` 的情况下使用的类型转换器。 对于静态属性，如果满足以下条件之一，则必须映射 XAML 命名空间的前缀：  
  
- 引用的类型存在于 WPF 中，但它不是 WPF 的默认 XAML 命名空间的一部分（`http://schemas.microsoft.com/winfx/2006/xaml/presentation`）。 这是使用 `x:Static`的一种非常常见的方案。 例如，你可以使用 `x:Static` 引用，其中包含到 <xref:System> CLR 命名空间和 mscorlib 程序集的 XAML 命名空间映射，以便引用 <xref:System.Environment> 类的静态属性。  
  
- 正在从自定义程序集引用类型。  
  
- 正在引用 WPF 程序集中存在的类型，但该类型位于未映射到 WPF 默认 XAML 命名空间的一部分的 CLR 命名空间中。 CLR 命名空间到 WPF 的默认 XAML 命名空间的映射由各种 WPF 程序集中的定义执行（有关此概念的详细信息，请参阅[WPF xaml 的 Xaml 命名空间和命名空间映射](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)）。 如果 CLR 命名空间主要由通常不适用于 XAML 的类定义组成，如 <xref:System.Windows.Threading>，则可能存在非映射 CLR 命名空间。  
  
 有关如何对 WPF 使用前缀和 XAML 命名空间的详细信息，请参阅[WPF xaml 的 XAML 命名空间和命名空间映射](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)。  
  
## <a name="see-also"></a>请参阅

- [x:Type 标记扩展](x-type-markup-extension.md)
- [从 WPF 迁移到 System.Xaml 的类型](types-migrated-from-wpf-to-system-xaml.md)
