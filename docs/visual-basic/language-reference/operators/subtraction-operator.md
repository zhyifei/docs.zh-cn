---
title: '- 运算符 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
ms.openlocfilehash: 4df8eb3844ed20fd24ca375f77cea46b9c6cee37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604310"
---
# <a name="--operator-visual-basic"></a>- 运算符 (Visual Basic)
返回两个数值表达式或数值表达式的负值之间的差异。  
  
## <a name="syntax"></a>语法  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a>部件  
 `expression1`  
 必须的。 任何数值表达式。  
  
 `expression2`  
 必填，除非`–`运算符正在计算值为负。 任何数值表达式。  
  
## <a name="result"></a>结果  
 结果之间的区别是`expression1`和`expression2`，或的相反的值`expression1`。  
  
 结果数据类型为数值类型适用于数据类型的`expression1`和`expression2`。 请参阅中的"整数算法"表[运算符结果的数据类型的](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)。  
  
## <a name="supported-types"></a>支持的类型  
 所有数值类型。 这包括的无符号和浮点类型和`Decimal`。  
  
## <a name="remarks"></a>备注  
 在以前，所示的语法中所示的第一个应用`–`运算符是*二进制*算术减法运算符，用于两个数值表达式之间的差异。  
  
 在中以前，所示的语法中所示的第二个应用`–`运算符是*一元*求反运算符的表达式的负值。 在这个意义上来说，该向量组成反转的符号`expression1`以便则结果为正如果`expression1`为负。  
  
 如果其中任何一个表达式的计算结果为[执行任何操作](../../../visual-basic/language-reference/nothing.md)、`–`运算符会将其视为零。  
  
> [!NOTE]
>  `–`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。 如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`–`运算符计算并返回两个数字之间的差异，然后进行求反运算的一个数字。  
  
 [!code-vb[VbVbalrOperators#10](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]  
  
 这些语句执行后`binaryResult`包含 124.45 和`unaryResult`包含 –334.90。  
  
## <a name="see-also"></a>请参阅  
 [-= 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [在 Visual Basic 中的算术运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
