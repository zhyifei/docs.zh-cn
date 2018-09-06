---
title: 枚举设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dea187b5f3911114e551d640e0bb0aa6fac1143
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891228"
---
# <a name="enum-design"></a>枚举设计
枚举都是一种特殊的值类型。 有两种类型的枚举： 简单枚举和标志枚举。  
  
 简单枚举表示小闭的集的选择。 简单枚举的一个常见示例是一组颜色。  
  
 标志枚举可以支持的枚举值的按位运算。 标志枚举的一个常见示例是一系列选项。  
  
 **✓ DO** 枚举用于强类型参数、 属性，并返回表示的值的集的值。  
  
 **✓ DO** 倾向于使用而不静态常量的枚举。  
  
 **X DO NOT** 枚举用于打开集 （如操作系统版本、 名称的友元，等等。）。  
  
 **X DO NOT** 提供应保留的枚举值供将来使用。  
  
 在后面的阶段始终只需向现有的枚举添加值。 请参阅[添加到枚举的值](#add_value)有关的详细信息添加到枚举的值。 只需保留的值污染的实际值集，并往往会导致用户错误。  
  
 **X AVOID** 公开使用只有一个值的枚举。  
  
 确保将来扩展的 C Api 的常见做法是将保留的参数添加到方法签名。 此类保留的参数可以表示为具有一个默认值的枚举。 这不应托管的 Api 中完成。 方法重载允许添加参数在将来的版本。  
  
 **X DO NOT** 在枚举中包括 sentinel 值。  
  
 尽管它们是有时对 framework 开发人员有帮助，sentinel 值是给 framework 的用户造成混淆。 它们用于从表示枚举集跟踪枚举而不是一个值的状态。  
  
 **✓ DO** 提供简单枚举零的值。  
  
 请考虑调用值类似于"None。 如果此类值不适合于此特定枚举，则应基础值零分配的最常见的默认值为枚举。  
  
 **✓ CONSIDER** 使用<xref:System.Int32>（默认值在大多数编程语言） 作为枚举的基础类型除非以下任一条件成立：  
  
-   枚举是标志枚举，包含 32 个以上的标志，或希望在将来的详细信息。  
  
-   基础类型必须是不同于<xref:System.Int32>更轻松互操作性与非托管代码应为不同大小的枚举。  
  
-   小的基础类型将导致节省大量空间。 如果希望将枚举主要用作有关控制流的参数，则大小就不太重要。 节省的大小可能会很明显如果：  
  
    -   您将发现要用作非常频繁地实例化的结构或类中的字段的枚举。  
  
    -   你希望用户用户创建大型数组或集合的枚举实例。  
  
    -   您将发现大量枚举要序列化的实例。  
  
 对于内存中使用情况，请注意的托管的对象始终是`DWORD`-对齐，因此您有效地需要多个枚举或实例因为实例总计大小始终是为了使差异，打包具有较小枚举中的其他小结构要四舍五入为`DWORD`。  
  
 **✓ DO** 命名为复数名词或名词短语的标志枚举和简单枚举用单数形式的名词或名词短语。  
  
 **X DO NOT** 扩展<xref:System.Enum?displayProperty=nameWithType>直接。  
  
 <xref:System.Enum?displayProperty=nameWithType> 是一种特殊类型用于由 CLR 创建用户定义的枚举。 大多数编程语言提供此功能可让你访问的编程元素。 例如，在 C#`enum`关键字用于定义的枚举。  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a>设计标志枚举  
 **✓ DO** 应用<xref:System.FlagsAttribute?displayProperty=nameWithType>到标志枚举。 不将此特性应用于简单枚举。  
  
 **✓ DO** 使用幂的两个用于标志枚举值，因此它们可以自由地组合使用按位或运算。  
  
 **✓ CONSIDER** 通常提供特殊的枚举值使用标志的组合。  
  
 按位操作是一种高级的概念，并且不应要求对简单的任务。 <xref:System.IO.FileAccess.ReadWrite> 是这样的特殊值的示例。  
  
 **X AVOID** 创建标志枚举值的某些组合将无效。  
  
 **X AVOID** 使用标志为零的枚举值，除非值表示"清除所有标志"，并且相应地下, 一项准则中规定名为。  
  
 **✓ DO** 命名的零值的标志枚举`None`。 对于标志枚举值必须并始终意味着"清除所有标志。"  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a>将值添加到枚举  
 它是很常见，来发现您需要将值添加到枚举后对已发布它。 没有潜在的应用程序兼容性问题时新添加的值返回从现有的 API，因为编写不佳的应用程序可能不会正确处理的新值。  
  
 **✓ CONSIDER** 将值添加到枚举，尽管小兼容性风险。  
  
 如果已将有关应用程序不兼容问题引起的新增功能的枚举的实际数据，请考虑添加一个新 API，则返回新的和旧值，并弃用旧的 API，应继续返回旧的值。 这将确保现有的应用程序保持兼容。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [类型设计准则](../../../docs/standard/design-guidelines/type.md)  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
