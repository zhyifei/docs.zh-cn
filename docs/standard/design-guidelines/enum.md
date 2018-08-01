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
ms.openlocfilehash: 544f617ca3a352814504125d7a61d70db5a81566
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33579244"
---
# <a name="enum-design"></a>枚举设计
枚举是特殊类型的值类型。 有两种枚举： 简单枚举和标志枚举。  
  
 简单枚举表示小闭的集的选择。 简单枚举的一个常见示例是一组的颜色。  
  
 标志枚举旨在支持的枚举值的按位运算。 标志枚举的一个常见示例是选项的列表。  
  
 **✓ DO** 枚举用于强类型参数、 属性，并返回表示的值的集的值。  
  
 **✓ DO** 倾向于使用而不静态常量的枚举。  
  
 **X DO NOT** 枚举用于打开集 （如操作系统版本、 名称的友元，等等。）。  
  
 **X DO NOT** 提供应保留的枚举值供将来使用。  
  
 你在以后的阶段始终只需向现有的枚举添加值。 请参阅[将值添加到枚举](#add_value)有关将值添加到枚举的详细信息。 只需保留的值会污染的实际值集，并往往会导致用户错误。  
  
 **X AVOID** 公开使用只有一个值的枚举。  
  
 确保将来扩展的 C Api 的常见做法是将保留的参数添加到方法签名。 此类保留的参数可以表示为具有一个默认值的枚举。 这不应该在托管 Api 来完成。 方法重载允许添加参数以后的版本。  
  
 **X DO NOT** 在枚举中包括 sentinel 值。  
  
 尽管它们有时 framework 开发人员很有帮助，sentinel 值是给的 framework 的用户造成混淆。 它们用于从枚举所表示的集中跟踪枚举而不是正在值之一的状态。  
  
 **✓ DO** 提供简单枚举零的值。  
  
 请考虑调用值类似于"None。 如果这样的值不适合于此特定枚举，则应基础值零的分配的最常见的默认值为枚举。  
  
 **✓ CONSIDER** 使用<xref:System.Int32>（默认值在大多数编程语言） 作为枚举的基础类型除非以下任一条件成立：  
  
-   枚举是标志枚举，您有 32 个以上的标志，或者希望有在将来的详细信息。  
  
-   基础类型必须是不同于<xref:System.Int32>更容易与预期不同大小的枚举的非托管代码的互操作性。  
  
-   小的基础类型将导致节省大量空间。 如果您希望主要用作有关控制流的参数将枚举，大小就不太重要。 节省的大小可能会很明显如果：  
  
    -   你预计将枚举用作非常频繁地实例化的结构或类中的字段。  
  
    -   指望用户能创建大型数组或集合的枚举实例。  
  
    -   你预计大量枚举要序列化的实例。  
  
 对于内存中的用法，请注意的托管的对象始终是`DWORD`-对齐，因此你有效地需要多个枚举中的或其他小结构一个实例，以便因为总实例大小始终会起作用，以便包较小枚举将会向上舍入到`DWORD`。  
  
 **✓ DO** 命名为复数名词或名词短语的标志枚举和简单枚举用单数形式的名词或名词短语。  
  
 **X DO NOT** 扩展<xref:System.Enum?displayProperty=nameWithType>直接。  
  
 <xref:System.Enum?displayProperty=nameWithType> 是一种特殊类型使用由 CLR 创建用户定义的枚举。 大多数编程语言提供与此功能使你可以访问的编程元素。 例如，在 C#`enum`关键字用于定义枚举。  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a>设计标志枚举  
 **✓ DO** 应用<xref:System.FlagsAttribute?displayProperty=nameWithType>到标志枚举。 不将此特性应用于简单枚举。  
  
 **✓ DO** 使用幂的两个用于标志枚举值，因此它们可以自由地组合使用按位或运算。  
  
 **✓ CONSIDER** 通常提供特殊的枚举值使用标志的组合。  
  
 按位运算是一个高级的概念，应该不需要用于简单任务。 <xref:System.IO.FileAccess.ReadWrite> 是一个示例这样的特殊值。  
  
 **X AVOID** 创建标志枚举值的某些组合将无效。  
  
 **X AVOID** 使用标志为零的枚举值，除非值表示"清除所有标志"，并且相应地下, 一项准则中规定名为。  
  
 **✓ DO** 命名的零值的标志枚举`None`。 对于标志枚举，该值必须并始终表示"清除所有标志。"  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a>将值添加到枚举  
 它是很常见，来发现你需要将值添加到枚举中，已发送了它后。 时出现的潜在应用程序兼容性问题新添加的值返回从现有的 API，因为编写不佳的应用程序可能不会正确处理的新值。  
  
 **✓ CONSIDER** 将值添加到枚举，尽管小兼容性风险。  
  
 如果你具有有关应用程序不兼容问题引起向枚举添加内容的真实数据，请考虑将添加一个新 API，返回新值和旧值，并且否决旧 API，这应继续返回只是这些旧值。 这将确保你现有的应用程序仍保持兼容。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [类型设计准则](../../../docs/standard/design-guidelines/type.md)  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)
