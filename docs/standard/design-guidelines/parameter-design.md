---
title: 参数设计
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
ms.openlocfilehash: 78eb07503810e75d14bcd73740fe429e2f73475e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743679"
---
# <a name="parameter-design"></a>参数设计

本部分提供了有关参数设计的广泛准则，包括用于检查参数的准则。 此外，还应参阅[命名参数](../../../docs/standard/design-guidelines/naming-parameters.md)中所述的准则。

 ✔️使用最不提供成员所需功能的派生参数类型。

 例如，假设想要设计一个枚举集合并将每个项输出到控制台的的方法。 例如，此类方法应将 <xref:System.Collections.IEnumerable> 用作参数，而不是 <xref:System.Collections.ArrayList> 或 <xref:System.Collections.IList>。

 ❌ 不使用保留的参数。

 如果在将来的某个版本中需要对成员有更多输入，则可以添加新的重载。

 ❌ 没有公开的方法，这些方法采用指针、指针数组或多维数组作为参数。

 指针和多维数组相对难以正确使用。 几乎在所有情况下，都可以重新设计 API 以避免将这些类型作为参数。

 ✔️将所有 `out` 参数置于所有按值和 `ref` 参数之后（不包括参数数组），即使在重载之间导致参数排序不一致（请参阅[成员重载](../../../docs/standard/design-guidelines/member-overloading.md)）。

 `out` 参数可以视为额外的返回值，并将它们组合在一起，使方法签名更易于理解。

 重写成员或实现接口成员时，✔️在命名参数中保持一致。

 这更好地传达了方法之间的关系。

### <a name="choose-between-enum-and-boolean-parameters"></a>选择枚举参数和布尔参数
 如果成员将使用两个或多个布尔参数，✔️确实使用枚举。

 ❌ 不要使用布尔值，除非你完全确定不需要两个以上的值。

 枚举为您提供了一些空间供将来添加值，但您应了解将值添加到枚举的所有含义，如[枚举设计](../../../docs/standard/design-guidelines/enum.md)中所述。

 ✔️考虑为构造函数参数使用布尔值，这些参数是真正的双状态值，只用于初始化布尔属性。

### <a name="validate-arguments"></a>验证参数
 ✔️验证传递到公共、受保护或显式实现的成员的参数。 如果验证失败，则引发 <xref:System.ArgumentException?displayProperty=nameWithType>或其中一个子类。

 请注意，实际验证不一定必须在公共成员或受保护成员本身中进行。 它可能发生在某些私有或内部例程的较低级别。 重点是暴露给最终用户的整个上层区域会检查参数。

 如果传递了 null 参数并且成员不支持 null 参数，✔️将引发 <xref:System.ArgumentNullException>。

 ✔️验证枚举参数。

 不要假设枚举实参将在枚举定义的范围内。 CLR 允许将任何整数值转换为枚举值，即使该值未在枚举中定义。

 ❌ 不使用 <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> 进行枚举范围检查。

 ✔️请注意，可变参数在验证后可能已更改。

 如果该成员对安全性敏感，则建议生成一个副本，然后验证并处理该实参。

### <a name="pass-parameters"></a>传递参数
 从框架设计器的角度来看，有三个主要参数组：按值参数、`ref` 参数和 `out` 参数。

 当实参通过传值形参传递时，该成员将接收传入的实际实参的副本。 如果实参是值类型，则将实参的副本放在栈上。 如果实参是引用类型，则将引用的副本放在栈上。 最常用的 CLR 语言（例如C#Visual Basic 和C++）默认为通过值传递参数。

 当通过 `ref` 参数传递参数时，该成员将接收对传入的实际参数的引用。 如果实参是值类型，则将实参的引用放在栈上。 如果实参是引用类型，则将引用的引用放在栈上。 `Ref` 参数可用于允许成员修改调用方传递的参数。

 `Out` 参数与 `ref` 参数类似，但差别略有不同。 该形参最初被视为未分配，并且在为其分配某个值之前无法在成员体内中读取。 此外，必须在成员返回之前为形参指定一些值。

 ❌ 避免使用 `out` 或 `ref` 参数。

 使用 `out` 或 `ref` 参数需要使用指针的经验，了解值类型和引用类型的不同之处，以及处理具有多个返回值的方法。 此外，不会广泛理解 `out` 和 `ref` 参数之间的差异。 一般受众设计框架架构师不应指望用户使用 `out` 或 `ref` 参数。

 ❌ 不通过引用传递引用类型。

 该规则有一些有限的例外情况，例如可用于交换引用的方法。

### <a name="members-with-variable-number-of-parameters"></a>参数数目可变的成员
 可以通过提供数组形参来表示使用可变数量实参的成员。 例如，<xref:System.String> 提供以下方法：

```csharp
public class String {
    public static string Format(string format, object[] parameters);
}
```

 然后，用户可以调用 <xref:System.String.Format%2A?displayProperty=nameWithType> 方法，如下所示：

 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`

 将 C# params 关键字添加到数组形参会将形参更改为所谓的 params 数组形参，并提供了创建临时数组的快捷方式。

```csharp
public class String {
    public static string Format(string format, params object[] parameters);
}
```

 执行此操作允许用户通过直接在实参列表中传递数组元素来调用方法。

 `String.Format("File {0} not found in {1}",filename,directory);`

 请注意，params 关键字只能添加到形参列表中的最后一个形参。

 如果预计最终用户要传递具有少量元素的数组，✔️考虑将 params 关键字添加到数组参数。 如果期望在常见场景中传递大量元素，则用户可能无论如何也不会以内联方式传递这些元素，因此 params 关键字不是必需的。

 如果调用方几乎总是在数组中具有输入，则 ❌ 避免使用 params 数组。

 例如，具有字节数组形参的成员几乎不会通过传递单个字节来调用。 因此，.NET Framework 中的字节数组形参不使用 params 关键字。

 如果使用 params 数组参数的成员修改了数组，则 ❌ 不要使用 params 数组。

 由于许多编译器将成员的实参转换为调用站点的临时数组，因此该数组可能是临时对象，所以对数组的任何修改都将丢失。

 ✔️考虑在简单重载中使用 params 关键字，即使比较复杂的重载无法使用它也是如此。

 问问自己用户是否会重视在一个重载中使用 params 数组，即使它不在所有重载中。

 ✔️尝试对参数进行排序，以便可以使用 params 关键字。

 ✔️考虑为在极高性能的 Api 中使用少量参数的调用提供特殊重载和代码路径。

 这样在使用少量实参调用 API 时可以避免创建数组对象。 通过采用数组形参的单数形式，并添加数字后缀来形成形参的名称。

 应该只在对整个代码路径执行特例时才这样做，而不仅仅是创建一个数组并调用更通用的方法。

 ✔️请注意，null 可作为参数数组参数进行传递。

 应该在处理之前验证数组是否为 null。

 ❌ 不使用 `varargs` 方法，也称为省略号。

 某些 CLR 语言（如C++）支持用于传递变量参数列表（称为 `varargs` 方法）的替代约定。 该约定不应在框架中使用，因为它不符合CLS。

### <a name="pointer-parameters"></a>指针参数
 通常，指针不应出现在设计良好的托管代码框架的公共上层区域中。 大多数情况下，指针应该被封装。 但是，在某些情况下，出于互操作性原因需要指针，在这种情况下适合使用指针。

 ✔️确实为采用指针参数的任何成员提供了一种替代方法，因为指针不符合 CLS。

 ❌ 避免对指针参数执行昂贵的参数检查。

 ✔️在用指针设计成员时遵循常见的指针相关约定。

 例如，不需要传递起始索引，因为可以使用简单的指针算法来完成相同的结果。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。

## <a name="see-also"></a>另请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
