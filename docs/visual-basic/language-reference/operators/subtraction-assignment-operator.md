---
title: -= 运算符 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.-=
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements [Visual Basic]
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 753e3efca311da9e09c67131969626ff59c130f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="--operator-visual-basic"></a>-= 运算符 (Visual Basic)
减去表达式的值的变量或属性的值并将结果赋给该变量或属性。  
  
## <a name="syntax"></a>语法  
  
```  
variableorproperty -= expression  
```  
  
## <a name="parts"></a>部件  
 `variableorproperty`  
 必需。 任何数值变量或属性。  
  
 `expression`  
 必需。 任何数值表达式。  
  
## <a name="remarks"></a>备注  
 在左侧的元素`-=`运算符可以是简单的标量变量、 属性或数组的元素。 变量或属性不能为[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。  
  
 `-=`运算符首先从变量或属性 （该运算符左侧） 的值减去 （运算符右侧） 表达式的值。 然后，运算符将该操作的结果分配给该变量或属性。  
  
## <a name="overloading"></a>重载  
 [-运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md)可以是*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。 重载`-`运算符会影响的行为`-=`运算符。 如果你的代码使用`-=`对类或重载的结构`-`，确保你理解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`-=`运算符相减一个`Integer`从另一个变量并将结果赋给前一个变量。  
  
 [!code-vb[VbVbalrOperators#11](codesnippet/VisualBasic/subtraction-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [-运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md)  
 [赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [语句](../../../visual-basic/programming-guide/language-features/statements.md)
