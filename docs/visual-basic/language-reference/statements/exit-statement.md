---
title: "Exit 语句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2df63ecbf0605d07296e1692f18b1b015e27cd03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="exit-statement-visual-basic"></a>Exit 语句 (Visual Basic)
退出的过程或块，并立即将控制权转交给过程调用或块定义后面的语句。  
  
## <a name="syntax"></a>语法  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## <a name="statements"></a>语句  
 `Exit Do`  
 立即退出`Do`循环中它将出现。 继续后面的语句执行`Loop`语句。 `Exit Do`可以使用仅在内`Do`循环。 当使用内嵌套`Do`循环，`Exit Do`退出最内层的循环，并将控制转移到下一步较高级别的嵌套。  
  
 `Exit For`  
 立即退出`For`循环中它将出现。 继续后面的语句执行`Next`语句。 `Exit For`可以使用仅在内`For`...`Next`或`For Each`...`Next`循环。 当使用内嵌套`For`循环，`Exit For`退出最内层的循环，并将控制转移到下一步较高级别的嵌套。  
  
 `Exit Function`  
 立即退出`Function`它在其中出现的过程。 继续执行的语句之后调用的语句执行`Function`过程。 `Exit Function`可以使用仅在内`Function`过程。  
  
 若要指定一个返回值，可以将该值赋给前一行上的函数名称`Exit Function`语句。 若要分配返回值和退出在一个语句中的函数，则可以使用[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。  
  
 `Exit Property`  
 立即退出`Property`它在其中出现的过程。 继续执行调用语句`Property`过程，即，与请求或设置该属性的值的语句。 `Exit Property`可以使用仅在属性内`Get`或`Set`过程。  
  
 若要指定在返回值`Get`过程中，可以将值分配到前一行上的函数名称`Exit Property`语句。 分配的返回值和退出`Get`在一个语句中的过程，则可以使用`Return`语句。  
  
 在`Set`过程中，`Exit Property`语句是等效于`Return`语句。  
  
 `Exit Select`  
 立即退出`Select Case`块中，在它显示。 继续后面的语句执行`End Select`语句。 `Exit Select`可以使用仅在内`Select Case`语句。  
  
 `Exit Sub`  
 立即退出`Sub`它在其中出现的过程。 继续执行的语句之后调用的语句执行`Sub`过程。 `Exit Sub`可以使用仅在内`Sub`过程。  
  
 在`Sub`过程中，`Exit Sub`语句是等效于`Return`语句。  
  
 `Exit Try`  
 立即退出`Try`或`Catch`块中，在它显示。 继续执行`Finally`阻止如果有一个，或之后的语句`End Try`否则为的语句。 `Exit Try`可以使用仅在内`Try`或`Catch`块中，不能在`Finally`块。  
  
 `Exit While`  
 立即退出`While`循环中它将出现。 继续后面的语句执行`End While`语句。 `Exit While`可以使用仅在内`While`循环。 当使用内嵌套`While`循环，`Exit While`将控制转移到一个嵌套级别上面循环的循环其中`Exit While`时发生。  
  
## <a name="remarks"></a>备注  
 不要混淆`Exit`具有语句`End`语句。 `Exit`未定义语句的末尾。  
  
## <a name="example"></a>示例  
 以下示例中，在循环条件将停止循环时`index`变量大于 100。 `If`语句在循环中，不过，会导致`Exit Do`语句来索引变量大于 10 时停止循环。  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_1.vb)]  
  
## <a name="example"></a>示例  
 下面的示例将返回值分配给函数名称`myFunction`，然后使用`Exit Function`以从函数返回。  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_2.vb)]  
  
## <a name="example"></a>示例  
 下面的示例使用[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)分配返回值并退出该函数。  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_3.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [Continue 语句](../../../visual-basic/language-reference/statements/continue-statement.md)  
 [Do...Loop 语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [End 语句](../../../visual-basic/language-reference/statements/end-statement.md)  
 [For Each...Next 语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [For...Next 语句](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)  
 [Stop 语句](../../../visual-basic/language-reference/statements/stop-statement.md)  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
