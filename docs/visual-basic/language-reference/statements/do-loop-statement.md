---
title: Do...Loop 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- conditional statements [Visual Basic], Do�Loop
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- loop structures [Visual Basic], Do�Loop statements
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
ms.openlocfilehash: e12cdc1ae405b877d4d27d1947c98dcb51938ba7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="doloop-statement-visual-basic"></a>Do...Loop 语句 (Visual Basic)
重复时的语句块`Boolean`条件是`True`或直到条件变为`True`。  
  
## <a name="syntax"></a>语法  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`Do`|必须的。 启动的定义`Do`循环。|  
|`While`|必选项（除非使用了 `Until`）。 重复循环，直到`condition`是`False`。|  
|`Until`|必选项（除非使用了 `While`）。 重复循环，直到`condition`是`True`。|  
|`condition`|可选。 `Boolean` 表达式。 如果`condition`是`Nothing`，Visual Basic 会将其视为`False`。|  
|`statements`|可选。 一个或多个语句，它时，或直到，重复`condition`是`True`。|  
|`Continue Do`|可选。 将控制转移到的下一个迭代`Do`循环。|  
|`Exit Do`|可选。 将扩展的控制转移`Do`循环。|  
|`Loop`|必须的。 终止的定义`Do`循环。|  
  
## <a name="remarks"></a>备注  
 使用`Do...Loop`结构，当你想要重复语句无限的次数，直到满足条件集。 如果你想要重复执行语句，一定的时间，[为...下一条语句](../../../visual-basic/language-reference/statements/for-next-statement.md)通常是更好的选择。  
  
 你可以使用`While`或`Until`指定`condition`，但不是两者。  
  
 你可以测试`condition`仅一次的开头或末尾循环。 如果你测试`condition`循环的开头 (在`Do`语句)，循环可能无法运行它甚至一次。 如果测试循环末尾 (在`Loop`语句)，循环始终运行至少一次。  
  
 条件通常导致的比较两个值，但它可以是任何表达式计算结果为[布尔数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)值 (`True`或`False`)。 这包括的其他数据类型，如数值类型的已转换为值`Boolean`。  
  
 可以嵌套`Do`置于另一个循环内的循环。 此外可以嵌套不同类型的每个其他控件结构。 有关详细信息，请参阅[嵌套控制结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)。  
  
> [!NOTE]
>  `Do...Loop`结构提供更大的灵活性比[时...结束 While 语句](../../../visual-basic/language-reference/statements/while-end-while-statement.md)因为它允许用户决定是否要结束循环时`condition`停止`True`或当它首先变为`True`。 它还可用于测试`condition`的开头或末尾循环。  
  
## <a name="exit-do"></a>退出执行  
 [退出执行](../../../visual-basic/language-reference/statements/exit-statement.md)语句可以提供一种替代方式退出`Do…Loop`。 `Exit Do` 立即将控制权转交给后面的语句`Loop`语句。  
  
 `Exit Do` 通常用于计算某个条件，例如，在之后`If...Then...Else`结构。 你可能想要退出循环，如果检测到的条件，使它不必要或不可能继续循环，如错误的值或终止请求。 一种用途`Exit Do`是测试的条件，可能会导致*无限循环*，即无法运行大型或甚至无限数量的次数的循环。 你可以使用`Exit Do`来退出循环。  
  
 可以包含任意数量的`Exit Do`中的任意位置语句`Do…Loop`。  
  
 当使用内嵌套`Do`循环，`Exit Do`传输最内层的循环出来放入下一个较高级别的嵌套的控件。  
  
## <a name="example"></a>示例  
 在下面的示例中，在循环中的语句继续运行，直到`index`变量是否大于 10。 `Until`子句是在循环末尾。  
  
 [!code-vb[VbVbalrStatements#131](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_1.vb)]  
  
## <a name="example"></a>示例  
 下面的示例使用`While`子句，而不是`Until`子句，和`condition`测试末尾而不是循环的开头。  
  
 [!code-vb[VbVbalrStatements#132](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_2.vb)]  
  
## <a name="example"></a>示例  
 在下面的示例中，`condition`停止循环时`index`变量大于 100。 `If`语句在循环中，不过，会导致`Exit Do`语句来索引变量大于 10 时停止循环。  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_3.vb)]  
  
## <a name="example"></a>示例  
 下面的示例读取在文本文件中的所有行。 <xref:System.IO.File.OpenText%2A>方法打开该文件，并返回<xref:System.IO.StreamReader>读取字符。 在`Do...Loop`条件，<xref:System.IO.StreamReader.Peek%2A>方法`StreamReader`确定是否有任何其他字符。  
  
 [!code-vb[VbVbalrStatements#134](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_4.vb)]  
  
## <a name="see-also"></a>请参阅  
 [循环结构](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [For...Next 语句](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Boolean 数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [嵌套的控件结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [While...End While 语句](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
