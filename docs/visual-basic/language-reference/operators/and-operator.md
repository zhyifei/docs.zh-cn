---
title: And 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.And
helpviewer_keywords:
- operators [Visual Basic], bitwise
- logical conjunction
- bitwise AND operator [Visual Basic]
- conjunction operator [Visual Basic]
- And operator [Visual Basic]
- bitwise operators [Visual Basic], AND operator
- operators [Visual Basic], conjunction
- bitwise comparison [Visual Basic]
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
ms.openlocfilehash: a1802d3a7018b1b6190ff5601eba055e16e62371
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913161"
---
# <a name="and-operator-visual-basic"></a>And 运算符 (Visual Basic)
对两个`Boolean`表达式执行逻辑与运算, 或对两个数值表达式执行位与运算。  
  
## <a name="syntax"></a>语法  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必需。 Any `Boolean`或数值表达式。 对于布尔值比较`result` , 是两个`Boolean`值的逻辑与。 对于按位运算`result` , 是表示两个数值位模式的按位 "与" 的数值。  
  
 `expression1`  
 必需。 Any `Boolean`或数值表达式。  
  
 `expression2`  
 必需。 Any `Boolean`或数值表达式。  
  
## <a name="remarks"></a>备注  
 对于布尔值比较`result` , `True`如果`expression1` `True`和均为, 则为。 `expression2` 下表说明了如何`result`确定。  
  
|如果`expression1`为|并且`expression2`为|的值`result`为|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> 在布尔比较中, `And`运算符始终计算两个表达式, 这可能包括进行过程调用。 [AndAlso 运算符](../../../visual-basic/language-reference/operators/andalso-operator.md)执行*短路*, 这意味着, 如果`expression1`为`False`, `expression2`则不计算。  
  
 当应用于数值时, `And`运算符将对两个数值表达式中的相同位置执行按位比较, 并根据下表设置中`result`的相应位。  
  
|如果中`expression1`的位是|和中`expression2`的位是|中`result`的位是|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
> 由于逻辑运算符和位运算符的优先级低于其他算术运算符和关系运算符, 因此应将任何按位运算括在括号中, 以确保准确的结果。  
  
## <a name="data-types"></a>数据类型  
 如果操作数由`Boolean`一个表达式和一个数值表达式组成, 则 Visual Basic 会`Boolean`将表达式转换为数值 (–1表示`True` , 0 表示`False`), 并执行按位运算。  
  
 对于布尔值比较, 结果的数据类型为`Boolean`。 对于按位比较, 结果数据类型是适用于`expression1`和`expression2`的数据类型的数值类型。 请参阅[运算符结果的数据类型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)中的 "关系和按位比较" 表。  
  
> [!NOTE]
> 运算符可以重载, 这意味着当操作数具有该类或结构的类型时, 该类或结构可以重新定义其行为。 `And` 如果你的代码在该类或结构上使用此运算符, 请确保了解其重新定义的行为。 有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`And`运算符对两个表达式执行逻辑与运算。 结果是一个`Boolean`表示两个表达式是否都`True`为的值。  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 前面的示例分别生成和`True` `False`的结果。  
  
## <a name="example"></a>示例  
 下面的示例使用`And`运算符对两个数值表达式的单个位执行逻辑与运算。 如果操作数中的相应位均设置为 1, 则结果模式中的位将设置为1。  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 前面的示例分别生成8、2和0的结果。  
  
## <a name="see-also"></a>请参阅

- [逻辑/按位运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [AndAlso 运算符](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [Visual Basic 中的逻辑运算符和位运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
