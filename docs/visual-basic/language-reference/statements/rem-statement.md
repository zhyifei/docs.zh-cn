---
title: REM 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
ms.openlocfilehash: 3bd526b08e1ba3be856e1e823cf8ef49ea9b6c97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="rem-statement-visual-basic"></a>REM 语句 (Visual Basic)
用于将解释性备注包含在程序的源代码。  
  
## <a name="syntax"></a>语法  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a>部件  
 `comment`  
 可选。 想要包括的任何注释的文本。 则之间需要空间`REM`关键字和`comment`。  
  
## <a name="remarks"></a>备注  
 您可以放入`REM`上一行，或你单独的语句可以将其置于另一个语句后的行。 `REM`语句必须是行的最后一个语句。 如果另一个语句，之后它`REM`必须从该语句由空格分隔。  
  
 你可以使用单引号 (`'`) 而不是`REM`。 你的评论相同行中的以下另一个语句还是单独位于行上，也是如此。  
  
> [!NOTE]
>  无法继续`REM`语句通过使用行继续序列 (`_`)。 注释开始之后，编译器将不检查具有特殊含义的字符。 对于多行注释，使用另一`REM`语句或者使用注释符号 (`'`) 在每一行上。  
  
## <a name="example"></a>示例  
 下面的示例演示`REM`语句，用于将解释性备注包含在程序中。 它还演示的替代方案，即使用一个单引号字符 (`'`) 而不是`REM`。  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [代码中的注释](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 [如何：在代码中拆分和合并语句](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
