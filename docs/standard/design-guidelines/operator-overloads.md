---
title: "运算符重载"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 1d17aa00ce551d951b0e178304632572abf592b6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="operator-overloads"></a>运算符重载
运算符重载允许起来就像它们是内置的语言基元的 framework 类型。  
  
 虽然允许，并且在某些情况下有用，应慎重使用运算符重载。 有很多情况下在哪些运算符重载具有已被滥用，如 framework 设计器启动时若要使用的操作，应是简单的方法的运算符。 以下准则可帮助您决定何时以及如何使用运算符重载。  
  
 **请避免 x**定义运算符重载，除了应感觉基元 （内置） 类型的类型中。  
  
 **请考虑 ✓**应感觉类似于基元类型的类型中定义运算符重载。  
  
 例如，<xref:System.String?displayProperty=nameWithType>具有`operator==`和`operator!=`定义。  
  
 **✓ 执行**中表示的数字的结构定义运算符重载 (如<xref:System.Decimal?displayProperty=nameWithType>)。  
  
 **X 不**过于刻意定义运算符重载时。  
  
 运算符重载可种情况下在其中显而易见将哪些操作的结果。 例如，它有意义能够减去<xref:System.DateTime>从另一个`DateTime`并获取<xref:System.TimeSpan>。 但是，不适合使用逻辑 union 运算符到联合的两个数据库查询，或使用移位运算符将写入到流。  
  
 **X 不**提供运算符重载，除非至少其中一个操作数是定义重载的类型。  
  
 **✓ 执行**对称方式重载运算符。  
  
 例如，如果重载`operator==`，还应该重载`operator!=`。 同样，如果重载`operator<`，还应该重载`operator>`，依次类推。  
  
 **请考虑 ✓**提供的友好名称的对应到每个重载运算符的方法。  
  
 许多语言不支持运算符重载。 出于此原因，建议重载运算符的类型包括具有正确的特定于域的名称，它提供等效功能的辅助方法。  
  
 下表包含运算符和相应的友好的方法名称的列表。  
  
|C# 运算符|元数据名称|友好名称|  
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
  
### <a name="overloading-operator-"></a>重载运算符 = =  
 重载`operator ==`非常复杂。 运算符的语义需要是符合几个其他成员，如<xref:System.Object.Equals%2A?displayProperty=nameWithType>。  
  
### <a name="conversion-operators"></a>转换运算符  
 转换运算符是一元运算符，从而允许从一种类型到另一个转换。 必须将运算符定义为操作数或返回类型上的静态成员。 有两种类型的转换运算符： 隐式和显式。  
  
 **X 不**提供转换运算符，如果最终用户未明确要求这种转换。  
  
 **X 不**定义转换运算符之外的类型的域。  
  
 例如， <xref:System.Int32>， <xref:System.Double>，和<xref:System.Decimal>是所有数值类型，而<xref:System.DateTime>不是。 因此，应该有任何转换运算符以转换`Double(long)`到`DateTime`。 在这种情况下被首选构造函数。  
  
 **X 不**提供隐式转换运算符，如果转换，则可能丢失信息。  
  
 例如，存在不应为隐式转换`Double`到`Int32`因为`Double`更广范围比`Int32`。 可以提供显式转换运算符，即使该转换是可能丢失信息。  
  
 **X 不**从隐式强制转换引发异常。  
  
 它是最终用户了解发生了什么情况，因为它们可能不知道正在进行转换很难。  
  
 **✓ 执行**引发<xref:System.InvalidCastException?displayProperty=nameWithType>如果对强制转换运算符的调用导致有损转换和运算符的协定不允许丢失数据的转换。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [成员设计准则](../../../docs/standard/design-guidelines/member.md)  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)
