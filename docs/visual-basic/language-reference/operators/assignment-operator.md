---
title: = 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 55b3a8201940a6fec351327aaa88e4ac1ee9246a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-visual-basic"></a>= 运算符 (Visual Basic)
将值分配给变量或属性。  
  
## <a name="syntax"></a>语法  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a>部件  
 `variableorproperty`  
 任何可写的变量或任何属性。  
  
 `value`  
 任何文本、 常量或表达式。  
  
## <a name="remarks"></a>备注  
 等号左侧的元素 (`=`) 可以是简单的标量变量、 属性或数组的元素。 变量或属性不能为[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。 `=`运算符将值赋给变量右侧的值或与其左侧的属性。  
  
> [!NOTE]
>  `=`运算符也用作比较运算符。 有关详细信息，请参阅[比较运算符](../../../visual-basic/language-reference/operators/comparison-operators.md)。  
  
## <a name="overloading"></a>重载  
 `=`仅为关系的比较运算符，而不是赋值运算符可以重载运算符。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示赋值运算符。 在右侧的值分配给左侧的变量。  
  
 [!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [&= 运算符](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [*= 运算符](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)  
 [+= 运算符](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [-= 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)  
 [/ = 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [\\= 运算符](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [^= 运算符](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [语句](../../../visual-basic/programming-guide/language-features/statements.md)  
 [比较运算符](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
