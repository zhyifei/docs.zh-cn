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
author: KrzysztofCwalina
ms.openlocfilehash: d1b9d8bc1f5f6f83a50dbd798894f94937320d2b
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152131"
---
# <a name="operator-overloads"></a>运算符重载
运算符重载允许显示如同内置语言基元的框架类型。  
  
 虽然允许，并且在某些情况下很有用，应谨慎使用运算符重载。 有很多情况下在哪些运算符重载具有已被滥用，如框架设计器启动时若要使用的操作，应为简单的方法的运算符。 以下指导原则可帮助您决定何时以及如何使用运算符重载。  
  
 **X AVOID** 定义运算符重载，除了应感觉基元 （内置） 类型的类型中。  
  
 **✓ CONSIDER** 应感觉类似于基元类型的类型中定义运算符重载。  
  
 例如，<xref:System.String?displayProperty=nameWithType>已`operator==`和`operator!=`定义。  
  
 **✓ DO** 中表示的数字的结构定义运算符重载 (如<xref:System.Decimal?displayProperty=nameWithType>)。  
  
 **X DO NOT** 过于刻意定义运算符重载时。  
  
 运算符重载是会立即明显操作的结果将是的非常有用。 例如，最好能够减去<xref:System.DateTime>从另一个`DateTime`，并获取<xref:System.TimeSpan>。 但是，不适合使用逻辑 union 运算符来联合两个数据库查询，或使用移位运算符要写入到流。  
  
 **X DO NOT** 提供运算符重载，除非至少其中一个操作数是定义重载的类型。  
  
 **✓ DO** 对称方式重载运算符。  
  
 例如，如果重载`operator==`，还应该重载`operator!=`。 同样，如果重载`operator<`，还应该重载`operator>`，依次类推。  
  
 **✓ CONSIDER** 提供的友好名称的对应到每个重载运算符的方法。  
  
 许多语言不支持运算符重载。 出于此原因，建议重载运算符的类型包括具有适当的特定于域的名称提供等效功能的辅助方法。  
  
 下表包含一系列运算符和相应的友好方法名称。  
  
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
  
### <a name="overloading-operator-"></a>重载运算符 ==  
 重载`operator ==`非常复杂。 运算符的语义需要符合几个其他成员，如<xref:System.Object.Equals%2A?displayProperty=nameWithType>。  
  
### <a name="conversion-operators"></a>转换运算符  
 转换运算符是一元运算符，从而允许从一种类型转换到另一个。 必须将运算符定义为操作数或返回类型上的静态成员。 有两种类型的转换运算符： 隐式和显式。  
  
 **X DO NOT** 提供转换运算符，如果最终用户未明确要求这种转换。  
  
 **X DO NOT** 定义转换运算符之外的类型的域。  
  
 例如， <xref:System.Int32>， <xref:System.Double>，并<xref:System.Decimal>都是数值类型，而<xref:System.DateTime>不是。 因此，应该有没有要转换的转换运算符`Double(long)`到`DateTime`。 在这种情况中为首选构造函数。  
  
 **X DO NOT** 提供隐式转换运算符，如果转换，则可能丢失信息。  
  
 例如，应该不会有隐式转换`Double`到`Int32`因为`Double`具有更大范围比`Int32`。 可以提供显式转换运算符，即使转换，则可能会丢失数据。  
  
 **X DO NOT** 从隐式强制转换引发异常。  
  
 它是很难了解发生什么情况，因为它们可能不知道转换正在进行的最终用户。  
  
 **✓ DO** 引发<xref:System.InvalidCastException?displayProperty=nameWithType>如果对强制转换运算符的调用导致有损转换和运算符的协定不允许丢失数据的转换。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*  
  
## <a name="see-also"></a>请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
