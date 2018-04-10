---
title: '&lt;&lt;= 运算符 (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5c5c36e4f91155c09d01b448777483941d018d9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltlt-operator-visual-basic"></a>&lt;&lt;= 运算符 (Visual Basic)
对变量或属性的值执行算术左的移位运算，并将结果赋回给该变量或属性。  
  
## <a name="syntax"></a>语法  
  
```  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a>部件  
 `variableorproperty`  
 必需。 变量或属性的整数类型 (`SByte`， `Byte`， `Short`， `UShort`， `Integer`， `UInteger`， `Long`，或`ULong`)。  
  
 `amount`  
 必需。 数值表达式的数据类型扩大到`Integer`。  
  
## <a name="remarks"></a>备注  
 在左侧的元素`<<=`运算符可以是简单的标量变量、 属性或数组的元素。 变量或属性不能为[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。  
  
 `<<=`运算符先执行算术左的移位运算的变量或属性的值。 然后，运算符将该操作的结果赋回给该变量或属性。  
  
 算术移位不是循环，这意味着移出结果的一个 end 的数位另一端不重新移入。 在算术左移位运算移出的结果数据类型范围的位将被丢弃，并在右侧空出的位设置为零。  
  
## <a name="overloading"></a>重载  
 [<< 运算符](../../../visual-basic/language-reference/operators/left-shift-operator.md)可以是*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。 重载`<<`运算符会影响的行为`<<=`运算符。 如果你的代码使用`<<=`对类或重载的结构`<<`，确保你理解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`<<=`运算符以将移动的位模式`Integer`变量留下指定的量并将结果赋给变量。  
  
 [!code-vb[VbVbalrOperators#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [<< 运算符](../../../visual-basic/language-reference/operators/left-shift-operator.md)  
 [赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [移位运算符](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [语句](../../../visual-basic/programming-guide/language-features/statements.md)
