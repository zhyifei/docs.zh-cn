---
title: Exit 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
ms.openlocfilehash: 9c25653809c51662ea5b606ab97be6a9b50d5986
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2019
ms.locfileid: "71956933"
---
# <a name="exit-statement-visual-basic"></a>Exit 语句 (Visual Basic)

退出过程或块并将控制立即传输到过程调用或块定义后面的语句。

## <a name="syntax"></a>语法

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a>语句

 `Exit Do`  
 立即退出出现 @no__t 的0循环。 继续执行 `Loop` 语句后面的语句。 `Exit Do` 只能在 @no__t 循环内使用。 在嵌套 `Do` 循环内使用时，`Exit Do` 退出最内层的循环，并将控制转移到下一个更高的嵌套级别。

 `Exit For`  
 立即退出出现 @no__t 的0循环。 继续执行 `Next` 语句后面的语句。 `Exit For` 只能在 @no__t `Next` 或 `For Each` ... `Next` 循环内使用。 在嵌套 `For` 循环内使用时，`Exit For` 退出最内层的循环，并将控制转移到下一个更高的嵌套级别。

 `Exit Function`  
 会立即退出显示它的 @no__t 0 过程。 执行将继续，语句后跟调用 `Function` 过程的语句后面的语句。 `Exit Function` 只能在 @no__t 一过程中使用。

 若要指定返回值，可以在 `Exit Function` 语句之前，将值分配给函数名称。 若要分配返回值并在一个语句中退出函数，可以改为使用[Return 语句](return-statement.md)。

 `Exit Property`  
 会立即退出显示它的 @no__t 0 过程。 执行将继续，语句称为 @no__t 的过程，即，语句请求或设置属性的值。 `Exit Property` 只能在属性的 @no__t 或 @no__t 步骤中使用。

 若要在 @no__t 的过程中指定返回值，可以在 @no__t 1 语句之前，将值分配给函数名称。 若要在一个语句中分配返回值并退出 `Get` 过程，可以改为使用 @no__t 语句。

 在 @no__t 的过程中，@no__t 语句等效于第 2 @no__t 语句。

 `Exit Select`  
 立即退出出现 @no__t 的块。 继续执行 `End Select` 语句后面的语句。 `Exit Select` 只能在 @no__t 语句中使用。

 `Exit Sub`  
 会立即退出显示它的 @no__t 0 过程。 执行将继续，语句后跟调用 `Sub` 过程的语句后面的语句。 `Exit Sub` 只能在 @no__t 一过程中使用。

 在 @no__t 的过程中，@no__t 语句等效于第 2 @no__t 语句。

 `Exit Try`  
 立即退出出现 @no__t 0 或 `Catch` 块。 如果有 `Finally` 块，则继续执行; 否则，将继续执行 `End Try` 语句后面的语句。 `Exit Try` 只能在 @no__t 或 `Catch` 块内使用，而不能在 @no__t 块内使用。

 `Exit While`  
 立即退出出现 @no__t 的0循环。 继续执行 `End While` 语句后面的语句。 `Exit While` 只能在 @no__t 循环内使用。 在嵌套 `While` 循环内使用时，`Exit While` 会将控制转移到循环，该循环是在发生 `Exit While` 的循环之上的一个嵌套级别。

## <a name="remarks"></a>备注

不要将 `Exit` 语句与 @no__t 语句混淆。 `Exit` 不定义语句的末尾。

## <a name="example"></a>示例

在下面的示例中，当 `index` 变量大于100时，loop 条件将停止循环。 但是，循环中的 `If` 语句导致当索引变量大于10时，`Exit Do` 语句停止循环。

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a>示例

下面的示例将返回值分配给函数名称 `myFunction`，然后使用 `Exit Function` 从函数返回：

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a>示例

下面的示例使用[Return 语句](return-statement.md)来分配返回值并退出函数：

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a>请参阅

- [Continue 语句](continue-statement.md)
- [Do...Loop 语句](do-loop-statement.md)
- [End 语句](end-statement.md)
- [For Each...Next 语句](for-each-next-statement.md)
- [For...Next 语句](for-next-statement.md)
- [Function 语句](function-statement.md)
- [Return 语句](return-statement.md)
- [Stop 语句](stop-statement.md)
- [Sub 语句](sub-statement.md)
- [Try...Catch...Finally 语句](try-catch-finally-statement.md)
