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
ms.openlocfilehash: 332cee57c8d25d7f51737e01e70ba515d50bd6e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604388"
---
# <a name="not-operator-visual-basic"></a>Not 运算符 (Visual Basic)
在执行逻辑求反`Boolean`表达式或对数值表达式的按位求反运算。  
  
## <a name="syntax"></a>语法  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必须的。 任何`Boolean`或数值表达式。  
  
 `expression`  
 必须的。 任何`Boolean`或数值表达式。  
  
## <a name="remarks"></a>备注  
 有关`Boolean`表达式下, 表说明了如何`result`确定。  
  
|如果`expression`是|值`result`是|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 对于数值表达式，`Not`运算符反转任何数值表达式的位值，并设置相应的中位`result`根据下表。  
  
|如果在位`expression`是|中的位`result`是|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
>  因为逻辑和按位运算符的优先级低于其他算术和关系运算符，所以应将任何按位运算括在圆括号中以确保准确的执行。  
  
## <a name="data-types"></a>数据类型  
 对于布尔求反，结果的数据类型是`Boolean`。 对于按位求反，结果数据类型是相同的`expression`。 但是，如果表达式为`Decimal`，结果是`Long`。  
  
## <a name="overloading"></a>重载  
 `Not`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，其操作数的类或结构的类型。 如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`Not`运算符对执行逻辑求反`Boolean`表达式。 结果是`Boolean`值，该值表示表达式的值的相反值。  
  
 [!code-vb[VbVbalrOperators#33](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_1.vb)]  
  
 前面的示例将生成的结果`False`和`True`分别。  
  
## <a name="example"></a>示例  
 下面的示例使用`Not`运算符执行的单个位进行运算的数值表达式的逻辑求反。 结果模式中的位设置为在操作数模式中，包括符号位的相应位的相反值。  
  
 [!code-vb[VbVbalrOperators#34](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_2.vb)]  
  
 上面的示例分别产生结果 – 11、-9 和-7。  
  
## <a name="see-also"></a>请参阅  
 [逻辑/按位运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [在 Visual Basic 中的逻辑和按位运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
