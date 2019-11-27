---
title: Or 运算符
ms.date: 07/20/2015
f1_keywords:
- vb.Or
helpviewer_keywords:
- Or operator [Visual Basic]
- operators [Visual Basic], bitwise
- inclusive Or operator [Visual Basic]
- bitwise operators [Visual Basic], OR operator
- Or keyword [Visual Basic]
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison [Visual Basic]
- logical disjunction
- disjunction operator [Visual Basic]
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
ms.openlocfilehash: 8f28026b526c29a6122725b2689e53b7f6ee7327
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348251"
---
# <a name="or-operator-visual-basic"></a>Or 运算符 (Visual Basic)
对两个 `Boolean` 表达式执行逻辑或运算，或对两个数值表达式执行按位析取。  
  
## <a name="syntax"></a>语法  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必需。 任何 `Boolean` 或数值表达式。 对于 `Boolean` 比较，`result` 是两个 `Boolean` 值的包含逻辑析取。 对于按位运算，`result` 是表示两个数值位模式的包含按位析取的数值。  
  
 `expression1`  
 必需。 任何 `Boolean` 或数值表达式。  
  
 `expression2`  
 必需。 任何 `Boolean` 或数值表达式。  
  
## <a name="remarks"></a>备注  
 对于 `Boolean` 比较，当且仅当 `expression1` 和 `expression2` 的计算结果都为 `False`时，`result` 为 `False`。 下表说明了如何确定 `result`。  
  
|如果 `expression1` 为|并且 `expression2` 为|`result` 的值是|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> 在 `Boolean` 比较中，`Or` 运算符始终计算两个表达式，这可能包括进行过程调用。 [OrElse 运算符](../../../visual-basic/language-reference/operators/orelse-operator.md)执行*短路*，这意味着如果 `True``expression1`，则不会计算 `expression2`。  
  
 对于按位运算，`Or` 运算符对两个数值表达式中的相同位置执行按位比较，并根据下表设置 `result` 中的相应位。  
  
|如果 `expression1` 中有位|`expression2` 中的位是|`result` 中的位是|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
> 由于逻辑 and 位运算符的优先级低于其他算术运算符和关系运算符，因此应将任何按位运算括在括号中，以确保准确执行。  
  
## <a name="data-types"></a>数据类型  
 如果操作数由一个 `Boolean` 表达式和一个数值表达式组成，则 Visual Basic 会将 `Boolean` 表达式转换为数值（对于 `True` 为–1，对于 `False`为0）并执行按位运算。  
  
 对于 `Boolean` 比较，将 `Boolean`结果的数据类型。 对于按位比较，结果数据类型是一种适合 `expression1` 和 `expression2`的数据类型的数值类型。 请参阅[运算符结果的数据类型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)中的 "关系和按位比较" 表。  
  
## <a name="overloading"></a>重载  
 可以*重载*`Or` 运算符，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。 如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。 有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用 `Or` 运算符对两个表达式执行包含逻辑析取。 结果是一个 `Boolean` 值，该值表示两个表达式之一是否 `True`。  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 前面的示例分别产生 `True`、`True`和 `False`的结果。  
  
## <a name="example"></a>示例  
 下面的示例使用 `Or` 运算符对两个数值表达式的各个位执行包含逻辑析取。 如果操作数中的相应位均设置为1，则结果模式中的位将设置为1。  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 前面的示例分别生成10、14和14的结果。  
  
## <a name="see-also"></a>另请参阅

- [逻辑/按位运算符（Visual Basic）](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [OrElse 运算符](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [Visual Basic 中的逻辑运算符和位运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
