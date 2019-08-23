---
title: 异或运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Xor
helpviewer_keywords:
- exclusive OR operator [Visual Basic]
- logical exclusion
- operators [Visual Basic], exclusive or
- exclusion operator [Visual Basic]
- operators [Visual Basic], bitwise
- bitwise operators [Visual Basic], XOR operator
- Xor operator [Visual Basic]
- Xor keyword [Visual Basic]
- bitwise comparison [Visual Basic]
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
ms.openlocfilehash: 59f27b92996e1506be5967de88c22fb88e06f5b7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965848"
---
# <a name="xor-operator-visual-basic"></a>异或运算符 (Visual Basic)
对两个`Boolean`表达式执行逻辑异运算, 或对两个数值表达式执行位异运算。  
  
## <a name="syntax"></a>语法  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必需。 Any `Boolean`或 numeric 变量。 对于布尔值比较`result` , 是两个`Boolean`值的逻辑异运算 (互斥逻辑析取)。 对于按位运算`result` , 表示两个数值位模式的按位异运算 (互斥按位析取)。  
  
 `expression1`  
 必需。 Any `Boolean`或数值表达式。  
  
 `expression2`  
 必需。 Any `Boolean`或数值表达式。  
  
## <a name="remarks"></a>备注  
 对于布尔值比较`result` , `True`当且仅`expression2`当和的`expression1`计算结果都为`True`时, 才为。 即, 当且仅当`expression1` `expression2`和的计算结果为`Boolean`相反值时。 下表说明了如何`result`确定。  
  
|如果`expression1`为|并且`expression2`为|的值`result`为|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> 在布尔比较中, `Xor`运算符始终计算两个表达式, 这可能包括进行过程调用。 没有与`Xor`对应的短路, 因为结果总是依赖于这两个操作数。 对于*短路*逻辑运算符, 请参阅[AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse 运算符](../../../visual-basic/language-reference/operators/orelse-operator.md)。  
  
 对于按位运算, `Xor`运算符对两个数值表达式中的相同位置执行按位比较, 并根据下表`result`设置中的相应位。  
  
|如果中`expression1`的位是|和中`expression2`的位是|中`result`的位是|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|0|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
> 由于逻辑 and 位运算符的优先级低于其他算术运算符和关系运算符, 因此应将任何按位运算括在括号中, 以确保准确执行。  
  
 例如, 5 `Xor` 3 为6。 若要查看此操作的原因, 请将5和3转换为其二进制表示形式101和011。 然后, 使用上表来确定 101 Xor 011 为 110, 这是十进制数字6的二进制表示形式。  
  
## <a name="data-types"></a>数据类型  
 如果操作数由`Boolean`一个表达式和一个数值表达式组成, 则 Visual Basic 会`Boolean`将表达式转换为数值 (–1表示`True` , 0 表示`False`), 并执行按位运算。  
  
 对于比较, 结果的数据类型为`Boolean`。 `Boolean` 对于按位比较, 结果数据类型是适用于`expression1`和`expression2`的数据类型的数值类型。 请参阅[运算符结果的数据类型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)中的 "关系和按位比较" 表。  
  
## <a name="overloading"></a>重载  
 运算符可以重载, 这意味着当操作数具有该类或结构的类型时, 该类或结构可以重新定义其行为。 `Xor` 如果代码对这样的类或结构使用此运算符, 请确保了解其重新定义的行为。 有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的`Xor`示例使用运算符对两个表达式执行逻辑异运算 (互斥逻辑析取)。 结果是一个`Boolean`值, 该值表示是否只有一个表达式是`True`。  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 前面的示例分别生成、 `False` `True`和`False`的结果。  
  
## <a name="example"></a>示例  
 下面的示例使用`Xor`运算符对两个数值表达式的各个位执行逻辑异运算 (互斥逻辑析取)。 如果操作数中的相应位中正好有一个设置为 1, 则结果模式中的位将设置为1。  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 前面的示例分别产生2、12和14的结果。  
  
## <a name="see-also"></a>请参阅

- [逻辑/按位运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Visual Basic 中的逻辑运算符和位运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
