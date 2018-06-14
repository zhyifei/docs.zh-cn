---
title: '\= 运算符'
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: 4ebbf2eca7fb3cd208d979d7f3c77aa106569119
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603556"
---
# <a name="-operator"></a>\\= 运算符
除以表达式值的变量或属性的值并将整数结果赋给该变量或属性。  
  
## <a name="syntax"></a>语法  
  
```  
variableorproperty \= expression  
```  
  
## <a name="parts"></a>部件  
 `variableorproperty`  
 必须的。 任何数值变量或属性。  
  
 `expression`  
 必须的。 任何数值表达式。  
  
## <a name="remarks"></a>备注  
 在左侧的元素`\=`运算符可以是简单的标量变量、 属性或数组的元素。 变量或属性不能为[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。  
  
 `\=`运算符除以右侧，值的变量或与其左侧的属性的值，并将整数结果赋给该变量或与其左侧的属性  
  
 整除的进一步信息，请参阅[\ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)。  
  
## <a name="overloading"></a>重载  
 `\`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。 重载`\`运算符会影响的行为`\=`运算符。 如果你的代码使用`\=`对类或重载的结构`\`，确保你理解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`\=`运算符将一个`Integer`变量中的第二个和分配给第一个变量的整数结果。  
  
 [!code-vb[VbVbalrOperators#19](codesnippet/VisualBasic/integer-division-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [\ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
 [/ = 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [语句](../../../visual-basic/programming-guide/language-features/statements.md)
