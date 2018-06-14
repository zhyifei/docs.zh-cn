---
title: Continue 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: eb8596c43bf6232eec4bcb844e6202c5de373404
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602718"
---
# <a name="continue-statement-visual-basic"></a>Continue 语句 (Visual Basic)
传输控制立即传递给循环的下一个迭代。  
  
## <a name="syntax"></a>语法  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>备注  
 你可以将从传输内`Do`， `For`，或`While`到该循环的下一个迭代的循环。 控制将传递给循环条件测试，这等效于将传输到立即`For`或`While`语句，或`Do`或`Loop`包含语句`Until`或`While`子句。  
  
 你可以使用`Continue`允许传输该循环中的任何位置。 允许控制的转移的规则是与相同[GoTo 语句](../../../visual-basic/language-reference/statements/goto-statement.md)。  
  
 例如，如果循环是完全包含在`Try`块，`Catch`块，或`Finally`块中，你可以使用`Continue`传输出循环。 另一方面，如果`Try`...`End Try`结构是否包含在循环内，不能使用`Continue`来将控制转移出`Finally`块中，你可以使用它来转移出`Try`或`Catch`阻止仅在完全外传输`Try`...`End Try`结构。  
  
 如果你有嵌套的循环相同的类型，例如`Do`另循环内的`Do`循环，`Continue Do`语句将跳到下一个迭代的最内层`Do`包含它的循环。 不能使用`Continue`跳到包含相同类型的循环的下一个迭代。  
  
 如果你有嵌套的循环的不同的类型，例如`Do`循环内`For`循环，则可以跳到任一循环的下一个迭代使用`Continue Do`或`Continue For`。  
  
## <a name="example"></a>示例  
 下面的代码示例使用`Continue While`语句跳到下一列的数组，如果除数为零。 `Continue While`位于`For`循环。 它传输到`While col < lastcol`语句，这是最内层的下一个迭代`While`循环包含`For`循环。  
  
 [!code-vb[VbVbalrStatements#14](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/continue-statement_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [Do...Loop 语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [For...Next 语句](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [While...End While 语句](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
