---
title: Return 语句
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: efc85a3a844898345aa2d16926ba0e35d7346d1b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333017"
---
# <a name="return-statement-visual-basic"></a>Return 语句 (Visual Basic)
将控件返回到调用 `Function`、`Sub`、`Get`、`Set`或 `Operator` 过程的代码。  
  
## <a name="syntax"></a>语法  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a>部件  
 `expression`  
 在 `Function`、`Get`或 `Operator` 过程中是必需的。 表示要返回到调用代码的值的表达式。  
  
## <a name="remarks"></a>备注  
 在 `Sub` 或 `Set` 过程中，`Return` 语句等效于 `Exit Sub` 或 `Exit Property` 语句，不能提供 `expression`。  
  
 在 `Function`、`Get`或 `Operator` 过程中，`Return` 语句必须包含 `expression`，并且 `expression` 的计算结果必须为可转换为过程返回类型的数据类型。 在 `Function` 或 `Get` 过程中，您还可以选择将表达式分配给过程名称以用作返回值，然后执行 `Exit Function` 或 `Exit Property` 语句。 在 `Operator` 过程中，必须使用 `Return expression`。  
  
 可以在同一过程中包含任意数量的 `Return` 语句。  
  
> [!NOTE]
> `Finally` 块中的代码将在遇到 `Try` 或 `Catch` 块中的 `Return` 语句之后、但在执行该 `Return` 语句之前运行。 `Finally` 块中不能包含 `Return` 语句。  
  
## <a name="example"></a>示例  
 下面的示例多次使用 `Return` 语句，以便在过程无需执行任何其他操作时返回到调用代码。  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a>另请参阅

- [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Get 语句](../../../visual-basic/language-reference/statements/get-statement.md)
- [Set 语句](../../../visual-basic/language-reference/statements/set-statement.md)
- [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)
- [Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
