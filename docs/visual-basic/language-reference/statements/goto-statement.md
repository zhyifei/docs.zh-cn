---
title: GoTo 语句（Visual Basic）
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
ms.openlocfilehash: 4b7a5cce56dfdd2bdc7e068aadbc18b92bba269d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581820"
---
# <a name="goto-statement"></a>GoTo 语句
无条件地分支到过程中的指定行。  
  
## <a name="syntax"></a>语法  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a>部件  
 `line`  
 必须的。 任何行标签。  
  
## <a name="remarks"></a>备注  
 @No__t_0 语句只能分支到它所显示的过程中的行。 该行必须有 `GoTo` 可以引用的行标签。 有关详细信息，请参阅[如何：标签语句](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)。  
  
> [!NOTE]
> `GoTo` 语句可以使代码难以阅读和维护。 请尽可能使用控制结构。 有关详细信息，请参阅[控制流](../../../visual-basic/programming-guide/language-features/control-flow/index.md)。  
  
 不能使用`GoTo`语句从`For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, 或`Using`...`End Using`构造到中的标签。  
  
## <a name="branching-and-try-constructions"></a>分支和尝试构造  
 `Try`在 ...`Catch`...构造, 以下规则适用于`GoTo`使用语句的分支。 `Finally`  
  
|块或区域|从外部分支|从内部分支出|  
|---------------------|-------------------------------|-------------------------------|  
|`Try` 块|仅从同一构造<sup>1</sup>的 `Catch` 块|仅限于整个构造之外|  
|`Catch` 块|不允许|仅对整个构造以外的或同一构造<sup>1</sup>的 `Try` 块|  
|`Finally` 块|不允许|不允许|  
  
 <sup>1</sup> (如果`Try`有) ...`Catch`...构造嵌套在另一个块中`Catch` , `Try`块可以在其自身的嵌套级别 (而不是其他`Try`块) 分支到块。 `Finally` 嵌套`Try`...`Catch`...构造必须完全包含在它所`Try`嵌套`Catch`到的构造内或块中。 `Finally`  
  
 下图显示了嵌套在另一个 `Try` 构造。 这两个构造的块中的各种分支都指示为有效或无效。  
  
 ![Try 结构分支示意图](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a>示例  
 下面的示例使用 `GoTo` 语句分支到过程中的行标签。  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>请参阅

- [Do...Loop 语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next 语句](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [For Each...Next 语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [If...Then...Else 语句](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Select...Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [While...End While 语句](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [With...End With 语句](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
