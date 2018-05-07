---
title: If 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.IfOperator
- IfOperator
helpviewer_keywords:
- ternary operators [Visual Basic]
- conditional execution
- If expressions [Visual Basic]
- conditional operator [Visual Basic]
- If Operator [Visual Basic]
ms.assetid: dd56c9df-7cd4-442c-9ba6-20c70ee44c8f
ms.openlocfilehash: 192309a7ca728feb300e867bf2340e669e9da16c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="if-operator-visual-basic"></a>If 运算符 (Visual Basic)
使用短路计算有条件地返回两个值之一。 `If`使用三个自变量或两个自变量，可以调用运算符。  
  
## <a name="syntax"></a>语法  
  
```  
If( [argument1,] argument2, argument3 )  
```  
  
## <a name="if-operator-called-with-three-arguments"></a>如果使用三个自变量调用的运算符  
 当`If`调用通过使用三个自变量，第一个参数必须计算为一个值，可以强制转换为`Boolean`。 `Boolean`值将确定的其他两个自变量的计算并返回。 下面的列表适用时，才`If`调用通过使用三个自变量的运算符。  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`argument1`|必须的。 `Boolean`。 确定哪个要计算并返回的其他参数。|  
|`argument2`|必须的。 `Object`。 计算并返回如果`argument1`计算结果为`True`。|  
|`argument3`|必须的。 `Object`。 计算并返回如果`argument1`计算结果为`False`或如果`argument1`是[可以为 Null](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean`变量计算结果为[执行任何操作](../../../visual-basic/language-reference/nothing.md)。|  
  
 `If`使用三个自变量调用的运算符的工作原理类似`IIf`函数，只不过前者使用短路计算。 `IIf`函数始终在所有三个参数，而`If`具有三个自变量的运算符都要都计算其中只有两个。 第一个`If`自变量的计算，并将结果转换为`Boolean`值，`True`或`False`。 如果值为`True`，`argument2`是计算并返回其值，但`argument3`则不会评估。 如果值`Boolean`表达式是`False`，`argument3`是计算并返回其值，但`argument2`则不会评估。 下面的示例演示如何使用`If`使用三个自变量时：  
  
 [!code-vb[VbVbalrOperators#100](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_1.vb)]  
  
 下面的示例说明了的价值短路计算。 该示例演示两次尝试将变量`number`变量`divisor`时除外`divisor`为零。 在这种情况下，应返回 0，并且不应尝试执行除法运算，否则会导致运行时错误。 因为`If`使用表达式短路计算，其计算结果的第二个或第三个参数，具体取决于第一个自变量的值。 如果第一个参数为 true，除数不为零，则可以安全地评估第二个参数并执行该除法运算。 如果第一个参数为 false，仅第三个自变量的计算，并返回 0。 因此，除数为 0 时，不会执行除法并不会产生错误。 但是，因为`IIf`不使用短路计算，甚至当第一个参数为 false 时，才计算第二个参数。 这将导致运行时被零除错误。  
  
 [!code-vb[VbVbalrOperators#101](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_2.vb)]  
  
## <a name="if-operator-called-with-two-arguments"></a>如果使用两个自变量调用的运算符  
 第一个参数`If`可以省略。 这使操作员能够使用仅有两个自变量进行调用。 下面的列表适用时，才`If`运算符调用带有两个参数。  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`argument2`|必须的。 `Object`。 必须是引用或可以为 null 的类型。 其计算结果为任何内容以外时计算并返回`Nothing`。|  
|`argument3`|必须的。 `Object`。 计算并返回如果`argument2`计算结果为`Nothing`。|  
  
 当`Boolean`忽略自变量，第一个参数必须是引用或可以为 null 的类型。 如果第一个自变量的计算结果为`Nothing`，返回第二个参数的值。 在所有其他情况下，返回第一个自变量的值。 下面的示例阐释了这种计算的工作原理。  
  
 [!code-vb[VbVbalrOperators#102](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_3.vb)]  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.Interaction.IIf%2A>  
 [可以为 null 的值类型](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [Nothing](../../../visual-basic/language-reference/nothing.md)
