---
title: Not 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
ms.openlocfilehash: 5ebc5f9dbf674a9a6560bd96b3e8c9edcae08a81
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701081"
---
# <a name="not-operator-visual-basic"></a>Not 运算符 (Visual Basic)
对 @no__t 0 表达式执行逻辑非运算，或对数值表达式执行位求反运算。  
  
## <a name="syntax"></a>语法  
  
```vb  
result = Not expression  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必需。 Any `Boolean`或数值表达式。  
  
 `expression`  
 必需。 Any `Boolean`或数值表达式。  
  
## <a name="remarks"></a>备注  
 对于 @no__t 0 表达式，下表说明了如何确定 @no__t。  
  
|如果`expression`为|@No__t 值为|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 对于数值表达式，@no__t 0 运算符会反转任何数值表达式的位值，并根据下表设置 `result` 中的相应位。  
  
|如果 @no__t 中的位为|@No__t-0 中的位是|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
> 由于逻辑 and 位运算符的优先级低于其他算术运算符和关系运算符，因此应将任何按位运算括在括号中，以确保准确执行。  
  
## <a name="data-types"></a>数据类型  
 对于布尔求反，结果的数据类型为 `Boolean`。 对于按位求反，结果数据类型与 `expression` 的数据类型相同。 但是，如果 expression `Decimal`，则结果为 `Long`。  
  
## <a name="overloading"></a>重载  
 @No__t-0 运算符可*重载*，这意味着当类或结构的操作数具有该类或结构的类型时，该类或结构可以重新定义它的行为。 如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。 有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用 `Not` 运算符对 @no__t 1 表达式执行逻辑求反运算。 结果为 `Boolean` 值，该值表示表达式的值的反转。  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 前面的示例分别产生 @no__t 0 和 @no__t 的结果。  
  
## <a name="example"></a>示例  
 下面的示例使用 @no__t 0 运算符对数值表达式的各个位执行逻辑求反运算。 结果模式中的位设置为操作数模式中相应位的反向，其中包括符号位。  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 前面的示例分别产生–11、–9和–7的结果。  
  
## <a name="see-also"></a>请参阅

- [逻辑/按位运算符（Visual Basic）](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Visual Basic 中的逻辑运算符和位运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
