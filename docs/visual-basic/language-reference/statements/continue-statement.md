---
title: Continue 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 9ee5fb19db6eafeb7e4bed12935d0b950d6368d6
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005102"
---
# <a name="continue-statement-visual-basic"></a>Continue 语句 (Visual Basic)
将控制立即传输到循环的下一次迭代。  
  
## <a name="syntax"></a>语法  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>备注  
 可以从 `Do`、`For` 或 `While` 循环内传输到循环的下一次迭代。 控制权会立即传递到循环条件测试，这等效于转移到 `For` 或 `While` 语句，或传递到包含 @no__t 或 @no__t 子句的 `Do` 或 @no__t 3 语句。  
  
 可以在允许传输的循环中的任意位置使用 `Continue`。 允许传输控件的规则与[GoTo 语句](../../../visual-basic/language-reference/statements/goto-statement.md)相同。  
  
 例如，如果一个循环完全包含在 @no__t 0 块、@no__t 块或 @no__t 2 块中，则可以使用 `Continue` 来传出循环。 另一方面，如果 `Try` ... `End Try` 结构包含在循环中，则不能使用 `Continue` 来将控制转移出 `Finally` 块，并且仅当完全从 @no__t 传输时，才能使用它从 @no__t 或 @no_ 块中传出_t-6 `End Try` 结构。  
  
 如果有相同类型的嵌套循环（例如，另一个 `Do` 循环内的 @no__t 0 循环），则 `Continue Do` 语句将跳转到包含它的最 @no__t 内层的第3个循环的下一次迭代。 不能使用 `Continue` 跳到相同类型的包含循环的下一次迭代。  
  
 如果具有不同类型的嵌套循环（例如，在 @no__t 1 循环内的 @no__t 0 循环），则可以使用 `Continue Do` 或 `Continue For` 跳到任一循环的下一次迭代。  
  
## <a name="example"></a>示例  
 下面的代码示例使用 `Continue While` 语句跳转到数组的下一列（如果除数为零）。 @No__t-0 在 @no__t 循环中。 它传输到 `While col < lastcol` 语句，该语句是包含 @no__t 2 循环的最内层 `While` 循环的下一次迭代。  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>请参阅

- [Do...Loop 语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next 语句](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [While...End While 语句](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
