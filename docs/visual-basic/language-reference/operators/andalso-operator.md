---
title: AndAlso 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
ms.openlocfilehash: 549d14cc35d285ac2e4a02a37dd201cc669c5627
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="andalso-operator-visual-basic"></a>AndAlso 运算符 (Visual Basic)
执行短路逻辑与对两个表达式。  
  
## <a name="syntax"></a>语法  
  
```  
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`result`|必须的。 任何 `Boolean` 表达式。 结果是`Boolean`比较的两个表达式的结果。|  
|`expression1`|必须的。 任何 `Boolean` 表达式。|  
|`expression2`|必须的。 任何 `Boolean` 表达式。|  
  
## <a name="remarks"></a>备注  
 逻辑操作称为*短路*如果编译的代码可以绕过根据另一个表达式的结果的一个表达式的计算。 如果计算的第一个表达式的结果确定该操作的最终结果，则不需要计算第二个表达式，因为它不能更改的最终结果。 如果跳过的表达式是复杂，或如果它涉及过程调用，则短路可以提高性能。  
  
 如果两个表达式的计算结果为`True`，`result`是`True`。 下表说明了如何`result`确定。  
  
|如果`expression1`是|和`expression2`是|值`result`是|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|（不会评估）|`False`|  
  
## <a name="data-types"></a>数据类型  
 `AndAlso`运算符仅为定义[布尔数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)。 Visual Basic 将根据需要向每个操作数转换`Boolean`并执行运算全部`Boolean`。 如果你将结果赋给数值类型时，Visual Basic 会将其转换从`Boolean`为该类型。 这可能产生意外的行为。 例如，`5 AndAlso 12`导致`–1`时转换为`Integer`。  
  
## <a name="overloading"></a>重载  
 [And 运算符](../../../visual-basic/language-reference/operators/and-operator.md)和[IsFalse 运算符](../../../visual-basic/language-reference/operators/isfalse-operator.md)可以是*重载*，这意味着，一个类或结构可以重新定义它们的行为时，操作数的类型，类或结构。 重载`And`和`IsFalse`运算符会影响的行为`AndAlso`运算符。 如果你的代码使用`AndAlso`对类或重载的结构`And`和`IsFalse`，确保你理解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`AndAlso`运算符对两个表达式执行逻辑与。 结果是`Boolean`值，该值表示是否整个联合表达式为 true。 如果第一个表达式为`False`，则不会计算第二个。  
  
 [!code-vb[VbVbalrOperators#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_1.vb)]  
  
 前面的示例将生成的结果`True`， `False`，和`False`分别。 在计算中使用的`secondCheck`，因为第一个已不会计算第二个表达式`False`。 但是，第二个表达式计算中的计算`thirdCheck`。  
  
## <a name="example"></a>示例  
 下面的示例演示`Function`搜索数组的元素之间的给定值的过程。 如果数组为空，或已超过数组长度，`While`语句不会测试根据搜索值的数组元素。  
  
 [!code-vb[VbVbalrOperators#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_2.vb)]  
  
## <a name="see-also"></a>请参阅  
 [逻辑/按位运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [And 运算符](../../../visual-basic/language-reference/operators/and-operator.md)  
 [IsFalse 运算符](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [在 Visual Basic 中的逻辑和按位运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
