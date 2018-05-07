---
title: OrElse 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- OrElse
- vb.OrElse
helpviewer_keywords:
- short-circuiting
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], disjunction
- short-circuit evaluation
- OrElse operator [Visual Basic]
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
ms.openlocfilehash: 1ee3c1a5b6089f44742281eb40e2a7e9cb3e2812
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="orelse-operator-visual-basic"></a>OrElse 运算符 (Visual Basic)
执行短路对两个表达式的非独占逻辑或运算。  
  
## <a name="syntax"></a>语法  
  
```  
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必须的。 任何 `Boolean` 表达式。  
  
 `expression1`  
 必须的。 任何 `Boolean` 表达式。  
  
 `expression2`  
 必须的。 任何 `Boolean` 表达式。  
  
## <a name="remarks"></a>备注  
 逻辑操作称为*短路*如果编译的代码可以绕过根据另一个表达式的结果的一个表达式的计算。 如果计算的第一个表达式的结果确定该操作的最终结果，则不需要计算第二个表达式，因为它不能更改的最终结果。 如果跳过的表达式是复杂，或如果它涉及过程调用，则短路可以提高性能。  
  
 如果一个或两个表达式的计算结果为`True`，`result`是`True`。 下表说明了如何`result`确定。  
  
|如果`expression1`是|和`expression2`是|值`result`是|  
|-------------------------|--------------------------|------------------------------|  
|`True`|（不会评估）|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a>数据类型  
 `OrElse`运算符仅为定义[布尔数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)。 Visual Basic 将根据需要向每个操作数转换`Boolean`并执行运算全部`Boolean`。 如果你将结果赋给数值类型时，Visual Basic 会将其转换从`Boolean`为该类型。 这可能产生意外的行为。 例如，`5 OrElse 12`导致`–1`时转换为`Integer`。  
  
## <a name="overloading"></a>重载  
 [或运算符](../../../visual-basic/language-reference/operators/or-operator.md)和[IsTrue 运算符](../../../visual-basic/language-reference/operators/istrue-operator.md)可以是*重载*，这意味着，一个类或结构可以重新定义它们的行为时，操作数的该类的类型或结构。 重载`Or`和`IsTrue`运算符会影响的行为`OrElse`运算符。 如果你的代码使用`OrElse`对类或重载的结构`Or`和`IsTrue`，确保你理解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`OrElse`运算符对两个表达式执行逻辑析取。 结果是`Boolean`值，该值表示是否两个表达式之一为 true。 如果第一个表达式为`True`，则不会计算第二个。  
  
 [!code-vb[VbVbalrOperators#37](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_1.vb)]  
  
 前面的示例将生成的结果`True`， `True`，和`False`分别。 在计算中使用的`firstCheck`，因为第一个已不会计算第二个表达式`True`。 但是，第二个表达式计算中的计算`secondCheck`。  
  
## <a name="example"></a>示例  
 下面的示例演示`If`...`Then`语句包含两个过程调用。 如果首次调用返回`True`，则不调用第二个过程。 如果第二个过程执行此部分的代码运行时始终应执行的重要任务，这可能产生意外的结果。  
  
 [!code-vb[VbVbalrOperators#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_2.vb)]  
  
## <a name="see-also"></a>请参阅  
 [逻辑/按位运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Or 运算符](../../../visual-basic/language-reference/operators/or-operator.md)  
 [IsTrue 运算符](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [在 Visual Basic 中的逻辑和按位运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
