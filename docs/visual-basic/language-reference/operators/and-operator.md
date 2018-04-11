---
title: And 运算符 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 83e1f9df11152f88ef0db24a794026d6f5888a2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="and-operator-visual-basic"></a>And 运算符 (Visual Basic)
对两个执行逻辑与`Boolean`表达式或对两个数值表达式位与运算。  
  
## <a name="syntax"></a>语法  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必需。 任何`Boolean`或数值表达式。 有关布尔比较，`result`是逻辑的两个联合`Boolean`值。 对于按位运算，`result`表示两个数值的位模式的位与的数值。  
  
 `expression1`  
 必需。 任何`Boolean`或数值表达式。  
  
 `expression2`  
 必需。 任何`Boolean`或数值表达式。  
  
## <a name="remarks"></a>备注  
 有关布尔比较，`result`是`True`当且仅当`expression1`和`expression2`计算结果为`True`。 下表说明了如何`result`确定。  
  
|如果`expression1`是|和`expression2`是|值`result`是|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  在布尔比较中，`And`运算符始终在两个表达式，它可能包含使过程调用。 [AndAlso 运算符](../../../visual-basic/language-reference/operators/andalso-operator.md)执行*短路*，这意味着，如果`expression1`是`False`，然后`expression2`则不会评估。  
  
 当应用于数值，`And`运算符在两个数值表达式执行位置相同的位的按位比较，并设置相应的中位`result`根据下表。  
  
|如果在位`expression1`是|和中位`expression2`是|中的位`result`是|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
>  因为逻辑和按位运算符的优先级低于其他算术和关系运算符，所以应将任何按位运算括在圆括号中以确保准确的结果。  
  
## <a name="data-types"></a>数据类型  
 如果操作数组成一个`Boolean`Visual Basic 表达式和一个数值表达式，将转换`Boolean`为数字值的表达式 (– 1 表示`True`和 0 `False`)，并执行按位运算。  
  
 对于布尔比较，结果的数据类型是`Boolean`。 有关的按位比较，结果数据类型为数值类型适用于数据类型的`expression1`和`expression2`。 请参阅中的"关系和按位比较"表[运算符结果的数据类型的](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)。  
  
> [!NOTE]
>  `And`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。 如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`And`运算符对两个表达式执行逻辑与。 结果是`Boolean`值，该值表示两个表达式是否`True`。  
  
 [!code-vb[VbVbalrOperators#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_1.vb)]  
  
 前面的示例将生成的结果`True`和`False`分别。  
  
## <a name="example"></a>示例  
 下面的示例使用`And`运算符对单个位进行运算的两个数值表达式执行逻辑与。 如果操作数中的相应位均设置为 1，则结果模式中的位被设置。  
  
 [!code-vb[VbVbalrOperators#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_2.vb)]  
  
 上面的示例分别产生 8，2，0，结果。  
  
## <a name="see-also"></a>另请参阅  
 [逻辑/按位运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [AndAlso 运算符](../../../visual-basic/language-reference/operators/andalso-operator.md)  
 [在 Visual Basic 中的逻辑和按位运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
