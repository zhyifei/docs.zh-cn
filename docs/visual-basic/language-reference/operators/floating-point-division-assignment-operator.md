---
title: /= 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: 642307bc531e7d9ce21a932b112795b35e7b3182
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-visual-basic"></a>/= 运算符 (Visual Basic)
除以表达式值的变量或属性的值并将浮点结果赋给该变量或属性。  
  
## <a name="syntax"></a>语法  
  
```  
variableorproperty /= expression  
```  
  
## <a name="parts"></a>部件  
 `variableorproperty`  
 必须的。 任何数值变量或属性。  
  
 `expression`  
 必须的。 任何数值表达式。  
  
## <a name="remarks"></a>备注  
 在左侧的元素`/=`运算符可以是简单的标量变量、 属性或数组的元素。 变量或属性不能为[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。  
  
 `/=`运算符将该变量或属性 （该运算符左侧） 的值第一次除以 （运算符右侧） 表达式的值。 然后，运算符将该操作的浮点结果分配给该变量或属性。  
  
 此语句将赋`Double`给该变量或在左侧的属性的值。 如果`Option Strict`是`On`，`variableorproperty`必须`Double`。 如果`Option Strict`是`Off`，Visual Basic 执行隐式转换，并将该生成值赋给`variableorproperty`，并可能在运行时错误。 有关详细信息，请参阅[扩大和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)和[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。  
  
## <a name="overloading"></a>重载  
 [/ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)可以是*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。 重载`/`运算符会影响的行为`/=`运算符。 如果你的代码使用`/=`对类或重载的结构`/`，确保你理解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`/=`运算符将一个`Integer`变量中的第二个和分配给第一个变量的商。  
  
 [!code-vb[VbVbalrOperators#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [/ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)  
 [\\= 运算符](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [语句](../../../visual-basic/programming-guide/language-features/statements.md)
