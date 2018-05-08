---
title: 如何：调用不返回值的过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: cf136f1486645d6e8e4b5856c0b1baf9e99f6c50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>如何：调用不返回值的过程 (Visual Basic)
A`Sub`过程不会返回到调用代码的值。 显式调用该过程与独立的调用语句。 不能只需通过其名称在表达式中调用它。  
  
### <a name="to-call-a-sub-procedure"></a>调用 Sub 过程  
  
1.  指定的名称`Sub`过程。  
  
2.  过程名后面加上括号将自变量列表括起来。 如果不有任何自变量，你可以选择省略括号。 但是，使用括号使得你的代码易于阅读。  
  
3.  将自变量放在括号里，用逗号分隔参数列表中。 请确保你提供的相同顺序的自变量，`Sub`过程所定义的相应参数。  
  
     下面的示例调用 Visual Basic<xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>函数来激活应用程序窗口。 <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> 将窗口标题作为其唯一的自变量。 它不会调用的代码返回一个值。 如果未运行 Notepad 进程，本示例将引发<xref:System.ArgumentException>。 `Shell`过程假定应用程序都位于指定的路径。  
  
     [!code-vb[VbVbalrCatRef#11](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>  
 <xref:System.ArgumentException>  
 [过程](./index.md)  
 [Sub 过程](./sub-procedures.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [如何：创建过程](./how-to-create-a-procedure.md)  
 [如何：调用返回值的过程](./how-to-call-a-procedure-that-returns-a-value.md)  
 [如何： 在 Visual Basic 中调用事件处理程序](./how-to-call-an-event-handler.md)
