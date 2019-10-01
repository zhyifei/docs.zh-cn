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
ms.openlocfilehash: d82018a3018e2cf4362b9904ed127c20f56f6f0c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701273"
---
# <a name="xor-operator-visual-basic"></a>异或运算符 (Visual Basic)
对两个 @no__t 0 个表达式执行逻辑异运算，或对两个数值表达式执行位异运算。  
  
## <a name="syntax"></a>语法  
  
```vb  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必需。 任何 @no__t 0 或数值变量。 对于布尔值比较，`result` 是两个 @no__t 值的逻辑异运算（互斥逻辑析取）。 对于按位运算，@no__t 为数值，表示两个数值位模式的按位异运算（互斥按位析取）。  
  
 `expression1`  
 必需。 Any `Boolean`或数值表达式。  
  
 `expression2`  
 必需。 Any `Boolean`或数值表达式。  
  
## <a name="remarks"></a>备注  
 对于布尔值比较，当且仅当 `expression1` 和 @no__t 为 @no__t 时，`result` @no__t 为-1。 也就是说，当且仅当 `expression1` 和 `expression2` 的计算结果为相反 `Boolean` 值时。 下表说明了如何确定 `result`。  
  
|如果`expression1`为|并且`expression2`为|@No__t 值为|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> 在布尔比较中，@no__t 0 运算符始终计算两个表达式，这可能包括执行过程调用。 与 `Xor` 之间没有短路对应项，因为结果总是依赖于这两个操作数。 对于*短路*逻辑运算符，请参阅[AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse 运算符](../../../visual-basic/language-reference/operators/orelse-operator.md)。  
  
 对于按位运算，@no__t 0 运算符执行两个数值表达式中的相同位置位的按位比较，并根据下表设置 `result` 中的相应位。  
  
|如果 @no__t 中的位为|@No__t 中的位是|@No__t-0 中的位是|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|0|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
> 由于逻辑 and 位运算符的优先级低于其他算术运算符和关系运算符，因此应将任何按位运算括在括号中，以确保准确执行。  
  
 例如，5 `Xor` 3 为6。 若要查看此操作的原因，请将5和3转换为其二进制表示形式101和011。 然后，使用上表来确定 101 Xor 011 为110，这是十进制数字6的二进制表示形式。  
  
## <a name="data-types"></a>数据类型  
 如果操作数由一个 @no__t 0 表达式和一个数值表达式组成，则 Visual Basic 会将 `Boolean` 表达式转换为数值（-1 表示 `True`，0表示 `False`）并执行按位运算。  
  
 对于 0 @no__t 比较，结果的数据类型为 `Boolean`。 对于按位比较，结果数据类型是一种适合 `expression1` 和 `expression2` 的数据类型的数值类型。 请参阅[运算符结果的数据类型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)中的 "关系和按位比较" 表。  
  
## <a name="overloading"></a>重载  
 @No__t-0 运算符可*重载*，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。 如果代码对这样的类或结构使用此运算符，请确保了解其重新定义的行为。 有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用 @no__t 0 运算符对两个表达式执行逻辑异运算（互斥逻辑析取）。 结果为 `Boolean` 值，该值表示是否只有一个表达式 @no__t 为-1。  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 前面的示例分别产生 `False`、`True` 和 `False` 的结果。  
  
## <a name="example"></a>示例  
 下面的示例使用 @no__t 0 运算符对两个数值表达式的各个位执行逻辑异运算（互斥逻辑析取）。 如果操作数中的相应位中正好有一个设置为1，则结果模式中的位将设置为1。  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 前面的示例分别产生2、12和14的结果。  
  
## <a name="see-also"></a>请参阅

- [逻辑/按位运算符（Visual Basic）](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Visual Basic 中的逻辑运算符和位运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
