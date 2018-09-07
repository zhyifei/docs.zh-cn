---
title: 参数设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea5311de8cef266af23b259d943568bfa95eaf72
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44071409"
---
# <a name="parameter-design"></a>参数设计
本部分提供全面的指南参数的设计方案，包括用于检查参数的指导原则的部分。 此外，应参考中所述的准则[命名参数](../../../docs/standard/design-guidelines/naming-parameters.md)。  
  
 **✓ DO** 使用至少派生的参数提供的类型的成员所需的功能。  
  
 例如，假设你想要设计枚举集合，并输出到控制台的每个项的方法。 此类方法应采取<xref:System.Collections.IEnumerable>作为参数，不<xref:System.Collections.ArrayList>或<xref:System.Collections.IList>，例如。  
  
 **X DO NOT** 使用保留的参数。  
  
 如果某些未来版本中需要更多输入到成员，则可以添加新的重载。  
  
 **X DO NOT** 具有公共公开指针、 数组的指针或作为参数的多维数组的方法。  
  
 指针和多维数组是相对较难正确使用。 在几乎所有情况下，可以重新设计的 Api 来避免这些类型作为参数。  
  
 **✓ DO** 放置所有`out`后所有按值的参数和`ref`参数 （不包括参数数组），即使它会导致重载之间进行排序的参数中的不一致 (请参阅[成员重载](../../../docs/standard/design-guidelines/member-overloading.md))。  
  
 `out`参数可将其视为额外返回的值，并将它们组合在一起使方法签名易于理解。  
  
 **✓ DO** 时重写成员命名参数或实现接口成员中保持一致。  
  
 这更好地进行通信的方法之间的关系。  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a>枚举和布尔参数之间进行选择  
 **✓ DO** 如果成员本来两个或多个布尔参数，请使用枚举。  
  
 **X DO NOT** 如果你不完全确定永远不会将两个以上值需要使用布尔值。  
  
 枚举为您提供一些空间以便将来添加值，但您应注意将值添加到枚举器中所述的所有隐患[枚举设计](../../../docs/standard/design-guidelines/enum.md)。  
  
 **✓ CONSIDER** 布尔值用于构造函数参数是真正的两个状态的值，只需用来初始化布尔属性。  
  
### <a name="validating-arguments"></a>验证自变量  
 **✓ DO** 验证自变量传递到公共、 受保护，或显式实现的成员。 引发<xref:System.ArgumentException?displayProperty=nameWithType>，或一个子类，如果验证失败。  
  
 请注意，实际的验证不一定发生这种情况中的公共或受保护成员本身。 它可能在某些私有或内部的例程中较低级别。 要点是，向最终用户公开的整个图面区域会检查自变量。  
  
 **✓ DO** 引发<xref:System.ArgumentNullException>如果传递 null 自变量，并将该成员不支持 null 参数。  
  
 **✓ DO** 验证 enum 参数。  
  
 不要假定枚举自变量将在枚举定义的范围内。 CLR 允许任何整数值转换为枚举值，即使在枚举中未定义值。  
  
 **X DO NOT** 使用<xref:System.Enum.IsDefined%2A?displayProperty=nameWithType>枚举范围检查。  
  
 **✓ DO** 请注意，在经过验证后，可能已更改可变自变量。  
  
 如果该成员是敏感的安全，建议您的生成副本和验证并处理自变量。  
  
### <a name="parameter-passing"></a>参数传递  
 从框架设计器的角度来看，有三个主要组的参数： 按值参数，`ref`参数，和`out`参数。  
  
 当自变量传递通过按值参数时，成员都会中传递的实际自变量的副本。 如果参数为值类型，自变量的副本放在堆栈上。 如果参数为引用类型，引用的副本放在堆栈上。 最常用的 CLR 语言，如 C#、 VB.NET 和 c + +，默认为按值传递参数。  
  
 当自变量传递通过`ref`参数，该成员接收到传入的实际参数的引用。 如果参数为值类型，对自变量的引用放在堆栈上。 如果参数为引用类型，对引用的引用放在堆栈上。 `Ref` 可以使用参数，以便成员可以修改由调用方传递的参数。  
  
 `Out` 参数是类似于`ref`参数，但存在一些小差异。 参数最初被认为是未分配，分配一些值之前无法在成员正文中读取。 此外，该参数具有值分配给某些成员返回之前。  
  
 **X AVOID** 使用`out`或`ref`参数。  
  
 使用`out`或`ref`参数需要体验提供了指导，了解值类型和引用类型的不同之处，以及能处理具有多个返回值的方法。 此外，之间的差异`out`和`ref`参数没有得到广泛了解。 为一般用户设计的框架架构师不应指望用户掌握了`out`或`ref`参数。  
  
 **X DO NOT** 通过引用传递引用类型。  
  
 有一些有限的例外规则，例如可用于交换的引用的方法。  
  
### <a name="members-with-variable-number-of-parameters"></a>具有可变数量的参数的成员  
 通过提供的数组参数表示可以采用可变数量的参数的成员。 例如，<xref:System.String>提供了以下方法：  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 然后，用户可以调用<xref:System.String.Format%2A?displayProperty=nameWithType>方法，按如下所示：  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 将 C# params 关键字添加到的数组参数更改为所谓的 params 数组参数的参数，并提供了创建临时数组的快捷方式。  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 执行此操作允许用户通过将数组元素传递自变量列表中直接调用的方法。  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 请注意 params 关键字，可以添加仅对在参数列表中的最后一个参数。  
  
 **✓ CONSIDER** 将 params 关键字添加到数组参数中，如果希望最终用户能够将较少的元素的数组传递。 如果希望，大量元素将传递在常见方案，用户可能不会传递这些元素内联不管怎样，并因此 params 关键字不必要。  
  
 **X AVOID** 使用 params 数组，如果调用方将几乎始终输入已具有数组中。  
  
 例如，几乎不会将单个字节表示通过调用通过字节数组参数的成员。 出于此原因，.NET Framework 中的字节数组参数不使用 params 关键字。  
  
 **X DO NOT** 使用 params 数组，如果采用 params 数组参数的成员来修改数组。  
  
 原因在于，许多编译器将对成员实参转换到调用站点上的临时数组，该数组可能为临时对象，并因此对数组进行任何修改都将丢失。  
  
 **✓ CONSIDER** 使用在简单的重载中，params 关键字，即使更复杂的重载不能使用它。  
  
 问问自己，是否用户将具有参数数组中某一重载，即使它不是在所有重载值。  
  
 **✓ DO** 尝试顺序参数，以使其可以使用 params 关键字。  
  
 **✓ CONSIDER** 使用少量的极性能敏感的 Api 中的自变量调用提供特殊的重载和代码路径。  
  
 这样可以避免使用少量的参数调用 API 时创建的数组对象。 通过采用数组参数的单数形式，并添加数字后缀构成的参数的名称。  
  
 只有如果您将特殊处理的完整的代码路径，而不仅仅是创建一个数组，并调用更多常规方法的保护时，才应该这样做。  
  
 **✓ DO** 请注意该 null 可以作为参数数组自变量传递。  
  
 您应验证数组不处理前为 null。  
  
 **X DO NOT** 使用`varargs`方法，也称为旁边的省略号。  
  
 某些 CLR 语言，例如，c + +，支持替代约定，以便传递变量参数列表调用`varargs`方法。 约定不应在框架中，因为它不符合 CLS。  
  
### <a name="pointer-parameters"></a>指针参数  
 一般情况下，指针不应出现在一个设计良好的托管的代码框架的公共图面区域。 大多数情况下，应封装的指针。 但是，在某些情况下指针所需的互操作性方面的考虑，并且在这种情况下使用指针适合。  
  
 **✓ DO** 为采用指针自变量，任何成员提供一种替代方法，因为不符合 cls 的指针。  
  
 **X AVOID** 执行检查的指针自变量的高开销的参数。  
  
 **✓ DO** 设计具有使用指针的成员时遵循指针相关的常见约定。  
  
 例如，没有必要将传递的起始索引，因为简单指针算法可用于实现相同的结果。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
