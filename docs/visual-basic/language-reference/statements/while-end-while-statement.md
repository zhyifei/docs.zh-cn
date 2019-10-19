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
ms.openlocfilehash: 5da05835998b2e9ef9aeefe5b00faf9e1ecb9ce2
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582260"
---
# <a name="whileend-while-statement-visual-basic"></a>While...End While 语句 (Visual Basic)
只要 `True` 给定条件，就运行一系列语句。  
  
## <a name="syntax"></a>语法  
  
```vb  
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
|`condition`|必须的。 `Boolean` 表达式。 如果 `Nothing` `condition`，Visual Basic 将其视为 `False`。|  
|`statements`|可选。 @No__t_0 后面的一个或多个语句，在每次 `True` `condition` 时运行。|  
|`Continue While`|可选。 将控制转移到 `While` 块的下一次迭代。|  
|`Exit While`|可选。 将控制转移到 `While` 块。|  
|`End While`|必须的。 终止 `While` 块的定义。|  
  
## <a name="remarks"></a>备注  
 如果要重复一组不确定次数的语句，请使用 `While...End While` 结构，前提是条件保持 `True`。 如果你想要更灵活地对条件进行测试或测试的结果，你可能更倾向[于 .。。循环语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)。 如果要将语句重复一组次数[，则下一条语句](../../../visual-basic/language-reference/statements/for-next-statement.md)通常是更好的选择。  
  
> [!NOTE]
> "Do ..." 中也使用了 `While` 关键字[Loop 语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)、 [Skip while 子句](../../../visual-basic/language-reference/queries/skip-while-clause.md)和[Take while 子句](../../../visual-basic/language-reference/queries/take-while-clause.md)。  
  
 如果 `True` `condition`，则所有 `statements` 都将运行，直到遇到 `End While` 语句为止。 然后，控件返回到 `While` 语句，并再次检查 `condition`。 如果仍 `True` `condition`，则将重复该过程。 如果 `False`，控制将传递到 `End While` 语句后面的语句。  
  
 在开始循环之前，`While` 语句始终检查条件。 当条件仍 `True` 时，循环将继续。 如果第一次进入循环时 `False` `condition`，则它不会运行一次。  
  
 @No__t_0 通常是对两个值进行比较导致的，但它可以是计算结果为[布尔数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)值（`True` 或 `False`）的任何表达式。 此表达式可以包含已转换为 `Boolean` 的另一种数据类型的值，如数值类型。  
  
 可以通过在另一个循环中放置一个循环来嵌套 `While` 循环。 您还可以将不同种类的控制结构相互嵌套。 有关详细信息，请参阅[嵌套控制结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)。  
  
## <a name="exit-while"></a>退出时间  
 [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md)语句可以提供另一种退出 `While` 循环的方法。 `Exit While` 立即将控制转移到 `End While` 语句后面的语句。  
  
 在计算某些条件（例如，在 `If...Then...Else` 结构中）后，通常使用 `Exit While`。 如果检测到可能导致不必要或无法继续迭代的条件（如错误值或终止请求），则可能需要退出循环。 当测试可能导致*无限循环*的情况时，可以使用 `Exit While`，这是一个循环，该循环可以运行极大规模甚至无限次。 然后，可以使用 `Exit While` 来转义循环。  
  
 可以将任意数量的 `Exit While` 语句置于 `While` 循环的任意位置。  
  
 在嵌套的 `While` 循环中使用时，`Exit While` 将控制转移出最内层的循环，并移到下一个更高的嵌套级别。  
  
 @No__t_0 语句会立即将控制转移到循环的下一次迭代。 有关详细信息，请参阅[Continue 语句](../../../visual-basic/language-reference/statements/continue-statement.md)。  
  
## <a name="example"></a>示例  
 在下面的示例中，循环中的语句将继续运行，直至 `index` 变量大于10。  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a>示例  
 下面的示例阐释了 `Continue While` 和 `Exit While` 语句的用法。  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a>示例  
 下面的示例读取文本文件中的所有行。 @No__t_0 方法将打开文件并返回读取字符的 <xref:System.IO.StreamReader>。 在 `While` 条件下，`StreamReader` 的 <xref:System.IO.StreamReader.Peek%2A> 方法决定文件是否包含其他字符。  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a>请参阅

- [循环结构](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Do...Loop 语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next 语句](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Boolean 数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [嵌套的控件结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Continue 语句](../../../visual-basic/language-reference/statements/continue-statement.md)
