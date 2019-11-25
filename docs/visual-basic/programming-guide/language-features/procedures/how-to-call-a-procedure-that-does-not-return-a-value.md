---
title: 如何：调用不返回值的过程
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 3a5de98c6edf795a11bd9f0465aa6919f09eebfa
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340963"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>如何：调用不返回值的过程 (Visual Basic)
A `Sub` procedure does not return a value to the calling code. You call it explicitly with a stand-alone calling statement. You cannot call it by simply using its name within an expression.  
  
### <a name="to-call-a-sub-procedure"></a>To call a Sub procedure  
  
1. Specify the name of the `Sub` procedure.  
  
2. Follow the procedure name with parentheses to enclose the argument list. If there are no arguments, you can optionally omit the parentheses. However, using the parentheses makes your code easier to read.  
  
3. Place the arguments in the argument list within the parentheses, separated by commas. Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.  
  
     The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window. <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument. It does not return a value to the calling code. If a Notepad process is not running, the example throws an <xref:System.ArgumentException>. The `Shell` procedure assumes the applications are in the paths specified.  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [过程](./index.md)
- [Sub 过程](./sub-procedures.md)
- [过程参数和自变量](./procedure-parameters-and-arguments.md)
- [Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [如何：创建过程](./how-to-create-a-procedure.md)
- [如何：调用返回值的过程](./how-to-call-a-procedure-that-returns-a-value.md)
- [How to: Call an Event Handler in Visual Basic](./how-to-call-an-event-handler.md)
