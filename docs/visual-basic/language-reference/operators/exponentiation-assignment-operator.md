---
title: ^= 运算符 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fa9d87d2f090a8c18aaab742e73878c7b80f55c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>^= 运算符 (Visual Basic)
引发的变量或表达式的次幂的属性的值，并将结果赋回给该变量或属性。  
  
## <a name="syntax"></a>语法  
  
```  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a>部件  
 `variableorproperty`  
 必需。 任何数值变量或属性。  
  
 `expression`  
 必需。 任何数值表达式。  
  
## <a name="remarks"></a>备注  
 在左侧的元素`^=`运算符可以是简单的标量变量、 属性或数组的元素。 变量或属性不能为[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。  
  
 `^=`运算符首先引发 （运算符右侧） 表达式的值的幂的值的变量或属性 （该运算符左侧）。 然后，运算符将该操作的结果赋回给该变量或属性。  
  
 Visual Basic 始终执行求幂中的[Double 数据类型](../../../visual-basic/language-reference/data-types/double-data-type.md)。 任何其他类型的操作数将转换为`Double`，并且结果始终为`Double`。  
  
 值`expression`可以是小数，负的、 和/或文件名。  
  
## <a name="overloading"></a>重载  
 [^ 运算符](../../../visual-basic/language-reference/operators/exponentiation-operator.md)可以是*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。 重载`^`运算符会影响的行为`^=`运算符。 如果你的代码使用`^=`对类或重载的结构`^`，确保你理解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`^=`运算符来引发的一个值`Integer`变量的第二个变量中，并将结果赋给第一个变量次幂。  
  
 [!code-vb[VbVbalrOperators#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [^ 运算符](../../../visual-basic/language-reference/operators/exponentiation-operator.md)  
 [赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [语句](../../../visual-basic/programming-guide/language-features/statements.md)
