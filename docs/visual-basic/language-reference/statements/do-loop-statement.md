---
title: Do...Loop 语句
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
ms.openlocfilehash: 9384cbb355189be448fa4b8d274721b4a7ca6a20
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351259"
---
# <a name="doloop-statement-visual-basic"></a>Do...Loop 语句 (Visual Basic)
当 `True` `Boolean` 条件或条件变为 `True`之前，重复语句块。  
  
## <a name="syntax"></a>语法  
  
```vb  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
' -or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a>部件  
  
|术语|Definition|  
|---|---|  
|`Do`|必需。 开始 `Do` 循环的定义。|  
|`While`|必选项（除非使用了 `Until`）。 重复循环，直到 `False``condition`。|  
|`Until`|必选项（除非使用了 `While`）。 重复循环，直到 `True``condition`。|  
|`condition`|可选。 `Boolean` 表达式。 如果 `Nothing``condition`，Visual Basic 将其视为 `False`。|  
|`statements`|可选。 一个或多个语句，这些语句在 `condition` 时重复，或直到 `True`。|  
|`Continue Do`|可选。 将控制转移到 `Do` 循环的下一次迭代。|  
|`Exit Do`|可选。 将控制转移 `Do` 循环。|  
|`Loop`|必需。 终止 `Do` 循环的定义。|  
  
## <a name="remarks"></a>备注  
 如果希望在满足条件之前重复一组语句，请使用 `Do...Loop` 结构。 如果要将语句重复一组次数[，则下一条语句](../../../visual-basic/language-reference/statements/for-next-statement.md)通常是更好的选择。  
  
 您可以使用 `While` 或 `Until` 来指定 `condition`，但不能同时指定两者。  
  
 只能在循环的开头或结尾测试一次 `condition`。 如果在循环开始时测试 `condition` （在 `Do` 语句中），则循环可能不会运行一次。 如果在循环结束时（在 `Loop` 语句中）进行测试，则循环始终至少运行一次。  
  
 这种情况通常是由两个值比较导致的，但它可以是计算结果为[布尔数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)值（`True` 或 `False`）的任何表达式。 这包括已转换为 `Boolean`的其他数据类型（如数值类型）的值。  
  
 可以通过在另一个循环中放置一个循环来嵌套 `Do` 循环。 您还可以在彼此之间嵌套不同种类的控制结构。 有关详细信息，请参阅[嵌套控制结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)。  
  
> [!NOTE]
> `Do...Loop` 结构提供的灵活性比[.。。End While 语句](../../../visual-basic/language-reference/statements/while-end-while-statement.md)，因为它可用于决定在 `condition` 停止时 `True` 或第一次变为 `True`时是否终止循环。 它还使你能够在循环的开头或结尾测试 `condition`。  
  
## <a name="exit-do"></a>退出 Do  
 [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md)语句可以提供退出 `Do…Loop`的替代方法。 `Exit Do` 将控制立即传输到 `Loop` 语句后面的语句。  
  
 在计算某些条件（例如在 `If...Then...Else` 结构中）后，通常使用 `Exit Do`。 如果检测到可能导致不必要或无法继续迭代的条件（如错误值或终止请求），则可能需要退出循环。 `Exit Do` 的一种用途是测试可能导致*无限循环*的情况，这是一个可运行很大甚至无限次的循环。 您可以使用 `Exit Do` 来转义循环。  
  
 可以将任意数量的 `Exit Do` 语句包含在 `Do…Loop`中的任意位置。  
  
 在嵌套的 `Do` 循环中使用时，`Exit Do` 将控制转移出最内层的循环，并移到下一个更高的嵌套级别。  
  
## <a name="example"></a>示例  
 在下面的示例中，循环中的语句将继续运行，直至 `index` 变量大于10。 `Until` 子句位于循环的结尾。  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a>示例  
 下面的示例使用 `While` 子句而不是 `Until` 子句，而 `condition` 在循环开始而不是在结束时进行测试。  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a>示例  
 在下面的示例中，当 `index` 变量大于100时，`condition` 停止循环。 但是，循环中的 `If` 语句导致 `Exit Do` 语句在索引变量大于10时停止循环。  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>示例  
 下面的示例读取文本文件中的所有行。 <xref:System.IO.File.OpenText%2A> 方法将打开文件并返回读取字符的 <xref:System.IO.StreamReader>。 在 `Do...Loop` 条件下，`StreamReader` 的 <xref:System.IO.StreamReader.Peek%2A> 方法决定是否有任何其他字符。  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a>另请参阅

- [循环结构](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [For...Next 语句](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Boolean 数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [嵌套的控件结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)
- [While...End While 语句](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
