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
ms.openlocfilehash: a52f598c8a7c7a79b0f2436f1add7b3eb5d5261b
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835232"
---
# <a name="andalso-operator-visual-basic"></a>AndAlso 运算符 (Visual Basic)
对两个表达式执行短路逻辑与运算。  
  
## <a name="syntax"></a>语法  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a>部件  
  
|术语|Definition|  
|---|---|  
|`result`|必需。 任何 `Boolean` 表达式。 结果是对两个表达式进行比较 `Boolean` 结果。|  
|`expression1`|必需。 任何 `Boolean` 表达式。|  
|`expression2`|必需。 任何 `Boolean` 表达式。|  
  
## <a name="remarks"></a>备注  
 如果编译后的代码可以根据另一个表达式的结果跳过对一个表达式的计算，则将逻辑运算称为*短路*。 如果第一个表达式的计算结果确定了运算的最终结果，则不需要计算第二个表达式，因为它不能更改最终结果。 如果绕过的表达式较复杂，或者它涉及过程调用，则短路可以提高性能。  
  
 如果两个表达式的计算结果都为 `True`，`result` `True`。 下表说明了如何确定 `result`。  
  
|如果 `expression1` 为|并且 `expression2` 为|`result` 的值是|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|（未计算）|`False`|  
  
## <a name="data-types"></a>数据类型  
 仅为[布尔数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)定义 `AndAlso` 运算符。 Visual Basic 在计算表达式之前，根据需要将每个操作数转换为 `Boolean`。 如果将结果赋给数值类型，Visual Basic 会将其从 `Boolean` 转换为该类型，以便 `False` 成为 `0`，`True` 变为 `-1`。
有关详细信息，请参阅[布尔类型转换](../data-types/boolean-data-type.md#type-conversions)。
  
## <a name="overloading"></a>重载  
 [And 运算符](../../../visual-basic/language-reference/operators/and-operator.md)和[IsFalse 运算符](../../../visual-basic/language-reference/operators/isfalse-operator.md)可以*重载*，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义它们的行为。 重载 `And` 和 `IsFalse` 运算符会影响 `AndAlso` 运算符的行为。 如果你的代码对 `And` 和 `IsFalse`重载的类或结构使用 `AndAlso`，请确保了解其重新定义的行为。 有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用 `AndAlso` 运算符对两个表达式执行逻辑与运算。 结果是一个 `Boolean` 值，该值表示整个联合表达式是否为 true。 如果 `False`第一个表达式，则不计算第二个表达式。  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 前面的示例分别产生 `True`、`False`和 `False`的结果。 在 `secondCheck`的计算中，不计算第二个表达式，因为第一个表达式已 `False`。 但是，在 `thirdCheck`的计算中计算第二个表达式。  
  
## <a name="example"></a>示例  
 下面的示例演示了一个 `Function` 过程，该过程在数组的元素中搜索给定的值。 如果数组为空，或超出了数组长度，则 `While` 语句不会对照搜索值测试数组元素。  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a>另请参阅

- [逻辑/按位运算符（Visual Basic）](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [And 运算符](../../../visual-basic/language-reference/operators/and-operator.md)
- [IsFalse 运算符](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Visual Basic 中的逻辑运算符和位运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
