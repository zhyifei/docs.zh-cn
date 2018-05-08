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
ms.openlocfilehash: 980bf6a1bdb19afd5c8d3c798d31037ab8cd7086
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="xstatic-markup-extension"></a>x:Static 标记扩展
引用任何静态的按值代码实体中定义[!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]– 遵守法规的方法。 引用的静态属性可用来提供 XAML 中的属性的值。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`prefix`|可选。 指映射、 非默认 XAML 命名空间前缀。 `prefix` 所示显式使用由于很少引用来自默认 XAML 命名空间的静态属性。 请参阅“备注”。|  
|`typeName`|必须的。 定义的所需的静态成员的类型的名称。|  
|`staticMemberName`|必须的。 所需的静态值成员 （常量、 静态属性、 字段或枚举值） 的名称。|  
  
## <a name="remarks"></a>备注  
 引用的代码实体必须是以下项之一：  
  
-   常量  
  
-   静态属性  
  
-   字段  
  
-   一个枚举值  
  
 如果 XAML 是标记编译或 XAML 的加载时间分析异常，指定任何其他代码实体，例如非静态属性，会导致编译时错误。  
  
 你可以`x:Static`对静态字段或属性不在当前的 XAML 文档中; 默认 XAML 命名空间的引用但是，这需要的前缀映射。 几乎总是 XAML 文档的根元素上定义的 XAML 命名空间。  
  
 可以由.NET Framework XAML 服务和其 XAML 读取器和 XAML 编写器执行对于静态属性的查找操作，它们是在运行时与默认 XAML 架构上下文。 此 XAML 架构上下文可用于 CLR 反射提供所需的静态值为对象图构造。 `typeName`你指定实际是 XAML 类型名称，不是 CLR 类型名称，虽然这些是实质上是相同的名称，当使用默认 XAML 架构上下文或当使用所有现有的基于 CLR 的 XAML 实现框架。  
  
 当你进行时要格外小心`x:Static`它们不直接是属性的值的类型的引用。 在 XAML 处理序列中，从标记扩展提供的值不调用其他值的转换。 这是 true 即使你`x:Static`引用创建文本字符串，且通常基于文本字符串的属性值的值转换发生时针对特定成员或为返回类型的所有成员值。  
  
 特性语法是最常用于该标记扩展的语法。 在 `x:Static` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.Markup.StaticExtension.Member%2A> 扩展类的 <xref:System.Windows.Markup.StaticExtension> 值。  
  
 有两个还从技术上讲可能有其他 XAML 用法。 但是，这些用法并不常见，因为它们是冗长:  
  
 **对象元素语法：** `<x:Static Member="` `prefix` `:` `typeName` `.` `staticMemberName` `" .../>`  
  
 **与初始化字符串的显式成员属性的特性语法：** `<` `object` `` `property` `="{x:Static Member=` `prefix` `:` `typeName` `.` `staticMemberName` `}" .../>`  
  
 在.NET Framework XAML 服务实现中，对此标记扩展的处理由定义<xref:System.Windows.Markup.StaticExtension>类。  
  
 `x:Static` 是标记扩展。 XAML 使用中的所有标记扩展`{`和`}`其属性的语法，这是 XAML 处理器识别标记扩展，必须提供一个值所依据的约定中的字符。 有关标记扩展的详细信息，请参阅 [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md)。  
  
## <a name="wpf-usage-notes"></a>WPF 用法说明  
 将用于 WPF 编程的默认 XAML 命名空间不包含许多有用的静态属性，并且有用的静态属性大多具有支持，例如促进而无需使用的类型转换器`{x:Static}`。 对于静态属性，必须映射 XAML 命名空间的前缀，如果下列其中一项为 true:  
  
-   所引用的类型，存在于 WPF，但不是 WPF 的默认 XAML 命名空间的一部分 ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)])。 这是一个非常常见方案用于使用`x:Static`。 例如，你可能使用`x:Static`XAML 命名空间映射到引用<xref:System>CLR 命名空间和 mscorlib 程序集以引用的静态属性<xref:System.Environment>类。  
  
-   从自定义程序集，所引用的类型。  
  
-   所引用存在于 WPF 程序集的类型，但该类型位于未映射的 WPF 默认 XAML 命名空间一部分的 CLR 命名空间。 WPF 默认 XAML 命名空间到 CLR 命名空间的映射由各种 WPF 程序集中定义 (有关这一概念的详细信息，请参阅[XAML 命名空间和 WPF XAML Namespace 映射](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md))。 如果该 CLR 命名空间主要组成一般不应为 XAML，如的类定义非映射 CLR 命名空间可以存在<xref:System.Windows.Threading>。  
  
 有关如何为 WPF 使用前缀和 XAML 命名空间的详细信息，请参阅[XAML 命名空间和 Namespace 映射为 WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)。  
  
## <a name="see-also"></a>请参阅  
 [x:Type 标记扩展](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [从 WPF 迁移到 System.Xaml 的类型](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
