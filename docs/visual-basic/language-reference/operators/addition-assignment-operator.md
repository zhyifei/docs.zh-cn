---
title: "+= 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4ac8f5679aa90c50c15c33a957cfc75d9ccecde6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>+= 运算符 (Visual Basic)
将数值表达式的值添加到的数值变量或属性的值并将结果赋给该变量或属性。 此外可以使用要连接`String`表达式`String`变量或属性并将结果赋给变量或属性。  
  
## <a name="syntax"></a>语法  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a>部件  
 `variableorproperty`  
 必需。 任何数值或`String`变量或属性。  
  
 `expression`  
 必需。 任何数值或`String`表达式。  
  
## <a name="remarks"></a>备注  
 在左侧的元素`+=`运算符可以是简单的标量变量、 属性或数组的元素。 变量或属性不能为[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。  
  
 `+=`运算符将值添加到该变量或属性在其左侧，右侧，并将结果赋给该变量或与其左侧的属性。 `+=`运算符还可以用于串联`String`到右侧的表达式`String`变量或在其左侧和将结果赋给变量的属性或与其左侧的属性。  
  
> [!NOTE]
>  当你使用`+=`运算符，你可能不能以确定是否添加或字符串串联将出现。 使用`&=`的串联运算符，以消除多义性，并提供自说明代码。  
  
 此赋值运算符隐式执行扩大转换而不是收缩转换，如果编译环境强制执行严格的语义。 有关这些转换的详细信息，请参阅[扩大和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。 严格和宽松语义的详细信息，请参阅[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。  
  
 如果允许宽松语义，`+=`运算符隐式执行各种字符串和数字转换执行的转换相同`+`运算符。 有关这些转换的详细信息，请参阅[+ 运算符](../../../visual-basic/language-reference/operators/addition-operator.md)。  
  
## <a name="overloading"></a>重载  
 `+`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。 重载`+`运算符会影响的行为`+=`运算符。 如果你的代码使用`+=`对类或重载的结构`+`，确保你理解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`+=`运算符将与另一个变量的值合并。 第一部分使用`+=`带有数值变量添加到另一个值。 第二部分使用`+=`与`String`变量以连接与另一个值。 在这两种情况下，结果被分配给第一个变量。  
  
 [!code-vb[VbVbalrOperators#7](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_1.vb)]  
  
 [!code-vb[VbVbalrOperators#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_2.vb)]  
  
 值`num1`13 和的值现在是`str1`现在是"103"。  
  
## <a name="see-also"></a>另请参阅  
 [+ 运算符](../../../visual-basic/language-reference/operators/addition-operator.md)  
 [赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [串联运算符](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [语句](../../../visual-basic/programming-guide/language-features/statements.md)
