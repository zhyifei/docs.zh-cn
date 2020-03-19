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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401219"
---
# <a name="operator-overloads"></a>运算符重载
运算符重载允许框架类型显示为内置语言基元。

 尽管在某些情况下允许并且很有用，但应谨慎使用操作员过载。 在许多情况下，运算符过载被滥用，例如框架设计器开始使用运算符执行应该简单的操作。 以下指南将帮助您决定何时以及如何使用运算符重载。

 ❌AVOID 定义运算符重载，但应感觉像基元（内置）类型的类型除外。

 ✔️考虑在应感觉像基元类型的类型中定义运算符重载。

 例如，<xref:System.String?displayProperty=nameWithType>已`operator==`和`operator!=`已定义。

 ✔️DO在表示数字（如<xref:System.Decimal?displayProperty=nameWithType>）的结构中定义运算符重载。

 ❌定义运算符过载时不要可爱。

 在操作结果立即明显的情况下，操作员重载非常有用。 例如，能够从另<xref:System.DateTime>`DateTime`一个中减去一个并获取 一个<xref:System.TimeSpan>是有意义的。 但是，使用逻辑联合运算符联合两个数据库查询或使用移位运算符写入流是不适当的。

 ❌除非至少有一个操作数是定义重载的类型，否则不要提供运算符重载。

 ✔️以对称方式执行重载运算符。

 例如，如果重载`operator==`， 还应重载 。 `operator!=` 同样，如果重载`operator<`，也应重载`operator>`等。

 ✔️考虑提供与每个重载运算符对应的友好名称的方法。

 许多语言不支持运算符重载。 因此，建议重载运算符的类型包括具有提供等效功能的适当特定于域的名称的辅助方法。

 下表包含运算符列表和相应的友好方法名称。

|C# 运算符符号|元数据名称|友好名称|
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

### <a name="overloading-operator-"></a>重载运算符 |
 过载`operator ==`相当复杂。 运算符的语义需要与其他几个成员（如<xref:System.Object.Equals%2A?displayProperty=nameWithType>） 兼容。

### <a name="conversion-operators"></a>转换运算符
 转换运算符是允许从一种类型转换为另一种类型的单位运算符。 运算符必须定义为操作数或返回类型的静态成员。 转换运算符有两种类型：隐式运算符和显式运算符。

 ❌如果最终用户没有明确预期此类转换，则不要提供转换运算符。

 ❌不要在类型域之外定义转换运算符。

 <xref:System.Int32>例如，<xref:System.Double>和<xref:System.Decimal>都是数字类型， 而不是。 <xref:System.DateTime> 因此，不应有转换运算符将`Double(long)`转换为 。 `DateTime` 在这种情况下，构造函数是首选。

 ❌如果转换可能丢失，请不要提供隐式转换运算符。

 例如，`Double`不应有从 到`Int32`的隐式转换，`Double`因为 范围比`Int32`宽。 即使转换可能丢失，也可以提供显式转换运算符。

 ❌不要从隐式强制转换中引发异常。

 最终用户很难理解发生了什么，因为他们可能不知道正在进行转换。

 如果调用强制<xref:System.InvalidCastException?displayProperty=nameWithType>转换运算符导致亏损转换，并且操作员的合同不允许亏损转换，则✔️强制进行丢弃。

 *部分© 2005， 2009 微软公司.保留所有权利。*

 *经 Pearson 教育公司许可，从[框架设计指南：可重用的约定、习语和模式 .NET 库重新打印，第二版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)由 Krzysztof Cwalina 和 Brad Abrams 出版，由艾迪森-韦斯利专业公司作为微软 Windows 开发系列的一部分于 2008 年 10 月 22 日出版。*

## <a name="see-also"></a>另请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)
- [框架设计准则](../../../docs/standard/design-guidelines/index.md)
