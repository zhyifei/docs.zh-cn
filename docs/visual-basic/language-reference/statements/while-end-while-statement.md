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
ms.openlocfilehash: 7ea0814c587f65ddc1f114d2314ac7147143d40d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965814"
---
# <a name="whileend-while-statement-visual-basic"></a>While...End While 语句 (Visual Basic)
只要给定条件为, `True`则运行一系列语句。  
  
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
|`condition`|必需。 `Boolean`表达式. 如果`condition`为`Nothing` ,则VisualBasic`False`将其视为。|  
|`statements`|可选。 后面`While`的一个或多个语句, 每次`condition`运行`True`都是。|  
|`Continue While`|可选。 将控制转移到`While`块的下一次迭代。|  
|`Exit While`|可选。 将控制转移到`While`块。|  
|`End While`|必需。 终止 `While` 块的定义。|  
  
## <a name="remarks"></a>备注  
 如果您想要重复一组不确定次数的语句, 只要存在`True`条件, 就可以使用结构。`While...End While` 如果你想要更灵活地对条件进行测试或测试的结果, 你可能更倾向于 ... [循环语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)。 如果要将语句重复一组次数, 则[下一条语句](../../../visual-basic/language-reference/statements/for-next-statement.md)通常是更好的选择。  
  
> [!NOTE]
> `While`关键字还用于[Do .。。Loop 语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)、 [Skip while 子句](../../../visual-basic/language-reference/queries/skip-while-clause.md)和[Take while 子句](../../../visual-basic/language-reference/queries/take-while-clause.md)。  
  
 如果`condition` `statements` `End While`为`True`, 则在遇到语句之前, 所有运行。 控件会返回到`While`语句, 并`condition`再次选中。 如果`condition` 仍`True`为, 则将重复该过程。 如果是`False`, 控制将传递到`End While`语句后面的语句。  
  
 `While`语句在开始循环之前始终检查条件。 当条件保留`True`时, 循环将继续。 如果`condition` 是`False`第一次进入循环, 则它不会运行一次。  
  
 通常, 比较两个值, 但它可以是计算结果为[布尔数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)值 (`True`或`False`) 的任何表达式。 `condition` 此表达式可以包含已转换为`Boolean`的另一种数据类型的值, 例如, 数值类型。  
  
 可以通过在`While`另一个循环中放置循环来嵌套循环。 您还可以将不同种类的控制结构相互嵌套。 有关详细信息, 请参阅[嵌套控制结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)。  
  
## <a name="exit-while"></a>退出时间  
 [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md)语句可以提供另一种退出循环的`While`方法。 `Exit While`立即将控制转移到`End While`语句后面的语句。  
  
 通常在计算`Exit While`某些条件后 (例如, `If...Then...Else`在结构中) 使用。 如果检测到可能导致不必要或无法继续迭代的条件 (如错误值或终止请求), 则可能需要退出循环。 当您测试`Exit While`可能导致*无限循环*的情况时, 可以使用, 这是一个循环, 该循环可以运行极大规模甚至无限次。 然后, 可以使用`Exit While`来转义循环。  
  
 可以将任意数量的`Exit While`语句置于`While`循环中的任意位置。  
  
 在嵌套`While`循环内使用时`Exit While` , 将控制转移出最内层循环, 并将其转移到下一个更高的嵌套级别。  
  
 `Continue While`语句会立即将控制转移到循环的下一次迭代。 有关详细信息, 请参阅[Continue 语句](../../../visual-basic/language-reference/statements/continue-statement.md)。  
  
## <a name="example"></a>示例  
 在下面的示例中, 循环中的语句将继续运行, 直到`index`变量大于10。  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用`Continue While`和`Exit While`语句。  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a>示例  
 下面的示例读取文本文件中的所有行。 方法打开文件并<xref:System.IO.StreamReader>返回读取字符的。 <xref:System.IO.File.OpenText%2A> 在条件中<xref:System.IO.StreamReader.Peek%2A> , 的方法`StreamReader`确定文件是否包含其他字符。 `While`  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a>请参阅

- [循环结构](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Do...Loop 语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next 语句](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Boolean 数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [嵌套的控件结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Continue 语句](../../../visual-basic/language-reference/statements/continue-statement.md)
