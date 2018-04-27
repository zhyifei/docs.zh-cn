---
title: 参数设计
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0d89ed81c06558a6bc101864a7fef3173f019fd0
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="parameter-design"></a>参数设计
本部分参数的设计方案，包括有关检查的自变量的指南的各节提供全面的指南。 此外，你应参考中所述的指导原则[命名参数](../../../docs/standard/design-guidelines/naming-parameters.md)。  
  
 **✓ 执行**使用至少派生的参数提供的类型的成员所需的功能。  
  
 例如，假设你想要设计枚举集合，并输出到控制台的每个项的方法。 此类方法应接受<xref:System.Collections.IEnumerable>作为参数，不<xref:System.Collections.ArrayList>或<xref:System.Collections.IList>，例如。  
  
 **X 不**使用保留的参数。  
  
 如果在将来某个版本中需要更多输入到成员，则可以添加的新重载。  
  
 **X 不**具有公共公开指针、 数组的指针或作为参数的多维数组的方法。  
  
 指针和多维数组是相对较难正确使用。 在几乎所有情况下，可以避免这些类型作为参数而重新设计 Api。  
  
 **✓ 执行**放置所有`out`后所有按值的参数和`ref`参数 （不包括参数数组），即使它会导致重载之间进行排序的参数中的不一致 (请参阅[成员重载](../../../docs/standard/design-guidelines/member-overloading.md))。  
  
 `out`参数可以被视为额外返回值，并对其进行分组在一起使方法签名易于理解。  
  
 **✓ 执行**时重写成员命名参数或实现接口成员中保持一致。  
  
 这更好地进行通信的方法之间的关系。  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a>枚举和布尔参数之间进行选择  
 **✓ 执行**如果成员本来两个或多个布尔参数，请使用枚举。  
  
 **X 不**如果你不完全确定永远不会将两个以上值需要使用布尔值。  
  
 枚举为你提供了一些空间来将来添加的值，但你应注意到的将值添加到枚举中所述的所有影响[枚举设计](../../../docs/standard/design-guidelines/enum.md)。  
  
 **请考虑 ✓**布尔值用于构造函数参数是真正的两个状态的值，只需用来初始化布尔属性。  
  
### <a name="validating-arguments"></a>验证自变量  
 **✓ 执行**验证自变量传递到公共、 受保护，或显式实现的成员。 引发<xref:System.ArgumentException?displayProperty=nameWithType>，或它的某个子类，如果验证失败。  
  
 请注意，实际验证不一定有发生在公共或受保护成员本身中。 也有可能发生在某些私有或内部的例程中较低级别。 主要目的是向最终用户公开的整个图面区域检查自变量。  
  
 **✓ 执行**引发<xref:System.ArgumentNullException>如果传递 null 自变量，并将该成员不支持 null 参数。  
  
 **✓ 执行**验证 enum 参数。  
  
 不要假定枚举自变量将通过枚举定义的范围内。 CLR 允许任何整数值转换为枚举值，即使值未定义的枚举中。  
  
 **X 不**使用<xref:System.Enum.IsDefined%2A?displayProperty=nameWithType>枚举范围检查。  
  
 **✓ 执行**请注意，在经过验证后，可能已更改可变自变量。  
  
 如果该成员是敏感的安全，建议您的制作的副本然后验证并处理自变量。  
  
### <a name="parameter-passing"></a>参数传递  
 从框架设计器的角度来看，有三个主要组的参数： 按值参数，`ref`参数，和`out`参数。  
  
 当通过按值参数传递的参数，则成员会收到一份中传递的实际自变量。 如果参数为值类型，自变量的副本将放在堆栈上。 如果参数为引用类型，引用的副本将放在堆栈上。 最常用的 CLR 语言，例如 C#、 VB.NET 和 c + +，默认为按值传递参数。  
  
 当自变量传递通过`ref`参数，该成员会接收对中传递的实际自变量的引用。 如果参数为值类型，对自变量的引用将存储在堆栈上。 如果参数为引用类型，对引用的引用将存储在堆栈上。 `Ref` 参数可以用于允许要修改由调用方传递自变量的成员。  
  
 `Out` 参数是类似于`ref`参数，其中有一些小的差异。 参数最初被认为是未分配的它还未分配的一些值无法读取成员正文中。 此外，该参数必须之前的成员返回分配的一些值。  
  
 **请避免 x**使用`out`或`ref`参数。  
  
 使用`out`或`ref`参数要求具有使用指针，了解值类型和引用类型的不同之处，以及能处理具有多个返回值的方法的经验。 此外，之间的差异`out`和`ref`参数没有得到广泛了解。 Framework 架构师设计为一般不应指望用户能熟练运用`out`或`ref`参数。  
  
 **X 不**通过引用传递引用类型。  
  
 有一些有限的例外规则，如用于交换引用的方法。  
  
### <a name="members-with-variable-number-of-parameters"></a>具有可变数量的参数的成员  
 可以采用数量可变的自变量的成员所用提供的数组参数。 例如，<xref:System.String>提供以下方法：  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 然后，用户可以调用<xref:System.String.Format%2A?displayProperty=nameWithType>方法，如下所示：  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 将 C# params 关键字添加到的数组参数更改为所谓的参数数组参数的参数，并提供创建临时数组的快捷方式。  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 执行此操作允许用户通过将数组元素传递自变量列表中的直接调用该方法。  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 请注意，可以仅对在参数列表中的最后一个参数添加 params 关键字。  
  
 **请考虑 ✓**将 params 关键字添加到数组参数中，如果希望最终用户能够将较少的元素的数组传递。 如果预期，大量元素将传递在常见方案，用户可能不会传递这些元素内联，并因此 params 关键字是不必要。  
  
 **请避免 x**使用 params 数组，如果调用方将几乎始终输入已具有数组中。  
  
 例如，将几乎从未调用具有字节数组参数的成员，通过传递单个字节。 出于此原因，.NET Framework 中的字节数组参数不使用 params 关键字。  
  
 **X 不**使用 params 数组，如果采用 params 数组参数的成员来修改数组。  
  
 原因在于，许多编译器将该成员的自变量转换为调用站点的临时数组，数组可能是临时对象，并因此对数组进行任何修改都将丢失。  
  
 **请考虑 ✓**使用在简单的重载中，params 关键字，即使更复杂的重载不能使用它。  
  
 问问自己，是否用户将采用一个重载的参数数组，即使它不是所有重载中的值。  
  
 **✓ 执行**尝试顺序参数，以使其可以使用 params 关键字。  
  
 **请考虑 ✓**使用少量的极性能敏感的 Api 中的自变量调用提供特殊的重载和代码路径。  
  
 这使得可能以避免使用少量的自变量调用 API 时创建数组对象。 通过采用数组参数的单数形式，并添加数字后缀而形成的参数的名称。  
  
 只有如果你要到特殊的用例的整个代码路径，而不仅仅是创建一个数组，然后调用更多常规方法的保护时，才应这样做。  
  
 **✓ 执行**请注意该 null 可以作为参数数组自变量传递。  
  
 你应验证数组不在处理之前为 null。  
  
 **X 不**使用`varargs`方法，也称为旁边的省略号。  
  
 某些 CLR 语言，如 c + +，支持备用约定传递变量参数列表调用`varargs`方法。 应在框架，使用约定，因为它不符合 CLS。  
  
### <a name="pointer-parameters"></a>指针参数  
 一般情况下，指针不应出现在设计良好的托管的代码 framework 的公共外围应用。 大多数情况下，应封装指针。 但是，在某些情况下指针所需的互操作性原因，并且在这种情况下使用指针适合。  
  
 **✓ 执行**为采用指针自变量，任何成员提供一种替代方法，因为不符合 cls 的指针。  
  
 **请避免 x**执行检查的指针自变量的高开销的参数。  
  
 **✓ 执行**设计具有使用指针的成员时遵循指针相关的常见约定。  
  
 例如，没有无需传递的起始索引，因为可以使用简单指针算法来达到相同的结果。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [成员设计准则](../../../docs/standard/design-guidelines/member.md)  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)
