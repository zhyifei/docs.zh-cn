---
title: GoTo 语句
ms.date: 07/20/2015
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
ms.openlocfilehash: d5cdcd214c9679e245645505fe11cb5d521ce085
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351090"
---
# <a name="goto-statement"></a>GoTo 语句
无条件地分支到过程中的指定行。  
  
## <a name="syntax"></a>语法  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a>部件  
 `line`  
 必需。 任何行标签。  
  
## <a name="remarks"></a>备注  
 `GoTo` 语句只能分支到它所显示的过程中的行。 该行必须有 `GoTo` 可以引用的行标签。 有关详细信息，请参阅[如何：标签语句](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)。  
  
> [!NOTE]
> `GoTo` 语句可以使代码难以阅读和维护。 请尽可能使用控制结构。 有关详细信息，请参阅[控制流](../../../visual-basic/programming-guide/language-features/control-flow/index.md)。  
  
 不能使用 `GoTo` 语句从 `For`...`Next`、`For Each`...`Next`、`SyncLock`...`End SyncLock``Try`、`Catch`...`Finally`或 `With`构造添加到内部的标签，从而将其从 ...、...`End With`、`Using`。`End Using`  
  
## <a name="branching-and-try-constructions"></a>分支和尝试构造  
 在 `Try``Catch`...`Finally` 构造中，以下规则适用于使用 `GoTo` 语句进行分支。  
  
|块或区域|从外部分支|从内部分支出|  
|---------------------|-------------------------------|-------------------------------|  
|`Try` 块|仅从同一构造<sup>1</sup>的 `Catch` 块|仅限于整个构造之外|  
|`Catch` 块|不允许|仅对整个构造以外的或同一构造<sup>1</sup>的 `Try` 块|  
|`Finally` 块|不允许|不允许|  
  
 <sup>1</sup>如果将一个 `Try``Catch`...`Finally` 构造嵌套在另一个中，则 `Catch` 块可以在其自身的嵌套级别（而不是任何其他 `Try` 块）分支到 `Try` 块。 嵌套的 `Try``Catch`...`Finally` 构造必须完全包含在它所嵌套到的构造的 `Try` 或 `Catch` 块中。  
  
 下图显示了嵌套在另一个 `Try` 构造。 这两个构造的块中的各种分支都指示为有效或无效。  
  
 ![Try 结构分支示意图](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a>示例  
 下面的示例使用 `GoTo` 语句分支到过程中的行标签。  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>另请参阅

- [Do...Loop 语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next 语句](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [For Each...Next 语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [If...Then...Else 语句](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Select...Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [While...End While 语句](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [With...End With 语句](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
