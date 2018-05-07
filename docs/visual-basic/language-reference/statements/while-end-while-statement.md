---
title: While...End While 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 9f46a6ec65faef4448bdd25e30a6cc0c605cd0f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="whileend-while-statement-visual-basic"></a>While...End While 语句 (Visual Basic)
只要给定的条件运行一系列语句`True`。  
  
## <a name="syntax"></a>语法  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`condition`|必须的。 `Boolean` 表达式。 如果`condition`是`Nothing`，Visual Basic 会将其视为`False`。|  
|`statements`|可选。 一个或多个语句以下`While`，每次运行该`condition`是`True`。|  
|`Continue While`|可选。 将控制转移到的下一个迭代`While`块。|  
|`Exit While`|可选。 将扩展的控制转移`While`块。|  
|`End While`|必须的。 终止 `While` 块的定义。|  
  
## <a name="remarks"></a>备注  
 使用`While...End While`结构时，只要条件仍然要重复语句无限次，一组`True`。 如果想要更灵活地选择你在其中测试条件以及针对什么结果进行测试，你可能希望[执行...循环语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)。 如果你想要重复执行语句，一定的时间，[为...下一条语句](../../../visual-basic/language-reference/statements/for-next-statement.md)通常是更好的选择。  
  
> [!NOTE]
>  `While`关键字还用于[执行...循环语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)、 [Skip While 子句](../../../visual-basic/language-reference/queries/skip-while-clause.md)和[Take While 子句](../../../visual-basic/language-reference/queries/take-while-clause.md)。  
  
 如果`condition`是`True`，所有的`statements`运行，直至`End While`遇到语句。 随后控制返回到`While`语句，和`condition`再次检查。 如果`condition`仍`True`，请重复该过程。 如果它具有`False`，控制将传递到后面的语句`End While`语句。  
  
 `While`语句始终检查条件，然后会启动循环。 循环条件保持时将会继续下去`True`。 如果`condition`是`False`当您首次进入循环，它不甚至一次运行。  
  
 `condition`通常于比较的两个值，但它的结果可以是任何表达式计算结果为[布尔数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)值 (`True`或`False`)。 此表达式可包含的另一个数据类型，如的数值类型，已转换为值`Boolean`。  
  
 可以嵌套`While`通过将另一个循环内的循环。 此外可以嵌套在另一个控制结构的不同类型。 有关详细信息，请参阅[嵌套控制结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)。  
  
## <a name="exit-while"></a>退出时  
 [退出时](../../../visual-basic/language-reference/statements/exit-statement.md)语句可以提供另一种方式退出`While`循环。 `Exit While` 立即将控制权转交给后面的语句`End While`语句。  
  
 通常使用`Exit While`对某些条件进行评估后 (例如，在`If...Then...Else`结构)。 你可能想要退出循环，如果检测到的条件，使它不必要或不可能继续循环，如错误的值或终止请求。 你可以使用`Exit While`当你测试的条件，可能会导致*无限循环*，即无法运行次数极大甚至无限循环。 然后，可以使用`Exit While`来退出循环。  
  
 你可以放置任意数量的`Exit While`中的任意位置语句`While`循环。  
  
 当使用内嵌套`While`循环，`Exit While`传输最内层的循环出来放入下一个较高级别的嵌套的控件。  
  
 `Continue While`语句立即将控制权转交给循环的下一个迭代。 有关详细信息，请参阅[继续语句](../../../visual-basic/language-reference/statements/continue-statement.md)。  
  
## <a name="example"></a>示例  
 在下面的示例中，在循环中的语句继续运行，直到`index`变量是否大于 10。  
  
 [!code-vb[VbVbalrStatements#171](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_1.vb)]  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用`Continue While`和`Exit While`语句。  
  
 [!code-vb[VbVbalrStatements#172](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_2.vb)]  
  
## <a name="example"></a>示例  
 下面的示例读取在文本文件中的所有行。 <xref:System.IO.File.OpenText%2A>方法打开该文件，并返回<xref:System.IO.StreamReader>读取字符。 在`While`条件，<xref:System.IO.StreamReader.Peek%2A>方法`StreamReader`确定文件是否包含其他字符。  
  
 [!code-vb[VbVbalrStatements#173](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_3.vb)]  
  
## <a name="see-also"></a>请参阅  
 [循环结构](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Do...Loop 语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [For...Next 语句](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Boolean 数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [嵌套的控件结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Continue 语句](../../../visual-basic/language-reference/statements/continue-statement.md)
