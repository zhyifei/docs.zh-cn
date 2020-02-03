---
title: 运算符重载
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
ms.openlocfilehash: 0999e94c8d77396b237522e89c51206ce1226718
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743683"
---
# <a name="operator-overloads"></a>运算符重载
运算符重载允许框架类型的外观类似内置语言基元。

 虽然在某些情况下允许使用运算符重载并且有用，但应谨慎使用。 在许多情况下，运算符重载受到滥用，例如框架设计者开始使用运算符进行本应是简单方法的操作。 以下准则可帮助你确定何时以及如何使用运算符重载。

 ❌ 避免定义运算符重载，但在应像基元（内置）类型的类型中除外。

 ✔️考虑在应感觉为基元类型的类型中定义运算符重载。

 例如，<xref:System.String?displayProperty=nameWithType> 已定义 `operator==` 并 `operator!=`。

 ✔️在表示数字的结构（如 <xref:System.Decimal?displayProperty=nameWithType>）中定义运算符重载。

 定义运算符重载时，❌ 不太刻意。

 如果操作结果直观而明显，则运算符重载非常有用。 例如，能够从另一个 `DateTime` 中减去一个 <xref:System.DateTime> 并获得一个 <xref:System.TimeSpan>是有意义的。 但是，使用逻辑 union 运算符来合并两个数据库查询或使用 shift 运算符写入流则是不合适的。

 除非至少一个操作数为定义重载的类型，否则 ❌ 不提供运算符重载。

 ✔️以对称方式重载运算符。

 例如，如果重载 `operator==`，还应重载 `operator!=`。 同样，如果你重载 `operator<`，还应重载 `operator>`，依此类推。

 ✔️考虑为具有对应于每个重载运算符的友好名称提供方法。

 许多语言不支持运算符重载。 因此，建议重载运算符的类型包括具有适当的特定于域的名称的辅助方法，该方法提供等效功能。

 下表包含一个运算符列表和相应的友好方法名称。

|C#运算符符号|元数据名称|友好名称|
|-------------------------|-------------------|-------------------|
|`N/A`|`op_Implicit`|`To<TypeName>/From<TypeName>`|
|`N/A`|`op_Explicit`|`To<TypeName>/From<TypeName>`|
|`+ (binary)`|`op_Addition`|`Add`|
|`- (binary)`|`op_Subtraction`|`Subtract`|
|`* (binary)`|`op_Multiply`|`Multiply`|
|`/`|`op_Division`|`Divide`|
|`%`|`op_Modulus`|`Mod or Remainder`|
|`^`|`op_ExclusiveOr`|`Xor`|
|`& (binary)`|`op_BitwiseAnd`|`BitwiseAnd`|
|<code>&#124;</code>|`op_BitwiseOr`|`BitwiseOr`|
|`&&`|`op_LogicalAnd`|`And`|
|<code>&#124;&#124;</code>|`op_LogicalOr`|`Or`|
|`=`|`op_Assign`|`Assign`|
|`<<`|`op_LeftShift`|`LeftShift`|
|`>>`|`op_RightShift`|`RightShift`|
|`N/A`|`op_SignedRightShift`|`SignedRightShift`|
|`N/A`|`op_UnsignedRightShift`|`UnsignedRightShift`|
|`==`|`op_Equality`|`Equals`|
|`!=`|`op_Inequality`|`Equals`|
|`>`|`op_GreaterThan`|`CompareTo`|
|`<`|`op_LessThan`|`CompareTo`|
|`>=`|`op_GreaterThanOrEqual`|`CompareTo`|
|`<=`|`op_LessThanOrEqual`|`CompareTo`|
|`*=`|`op_MultiplicationAssignment`|`Multiply`|
|`-=`|`op_SubtractionAssignment`|`Subtract`|
|`^=`|`op_ExclusiveOrAssignment`|`Xor`|
|`<<=`|`op_LeftShiftAssignment`|`LeftShift`|
|`%=`|`op_ModulusAssignment`|`Mod`|
|`+=`|`op_AdditionAssignment`|`Add`|
|`&=`|`op_BitwiseAndAssignment`|`BitwiseAnd`|
|<code>&#124;=</code>|`op_BitwiseOrAssignment`|`BitwiseOr`|
|`,`|`op_Comma`|`Comma`|
|`/=`|`op_DivisionAssignment`|`Divide`|
|`--`|`op_Decrement`|`Decrement`|
|`++`|`op_Increment`|`Increment`|
|`- (unary)`|`op_UnaryNegation`|`Negate`|
|`+ (unary)`|`op_UnaryPlus`|`Plus`|
|`~`|`op_OnesComplement`|`OnesComplement`|

### <a name="overloading-operator-"></a>重载运算符 ==
 重载 `operator ==` 非常复杂。 运算符的语义需要与其他一些成员（如 <xref:System.Object.Equals%2A?displayProperty=nameWithType>）兼容。

### <a name="conversion-operators"></a>转换运算符
 转换运算符是一元运算符，允许从一种类型转换为另一种类型。 必须在操作数或返回类型上将运算符定义为静态成员。 有两种类型的转换运算符：隐式和显式。

 如果最终用户不清楚此类转换，❌ 不提供转换运算符。

 ❌ 不会在类型的域外部定义转换运算符。

 例如，<xref:System.Int32>、<xref:System.Double>和 <xref:System.Decimal> 均为数值类型，而 <xref:System.DateTime> 则不是。 因此，不应使用转换运算符将 `Double(long)` 转换为 `DateTime`。 在这种情况中，应该首选构造函数。

 如果转换可能有损，❌ 不提供隐式转换运算符。

 例如，不应有从 `Double` 到 `Int32` 的隐式转换，因为 `Double` 的范围超出了 `Int32`。 可以提供显式转换运算符，即使转换可能产生损耗。

 ❌ 不会从隐式转换中引发异常。

 最终用户将难以理解当前出现的情况，因为他们可能不知道转换正在进行。

 如果调用强制转换运算符导致了有损转换，并且该运算符的协定不允许有损转换，✔️将引发 <xref:System.InvalidCastException?displayProperty=nameWithType>。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。

## <a name="see-also"></a>另请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
