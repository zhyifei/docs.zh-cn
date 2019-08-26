---
title: Return 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: af49ea95d7f9d01072190ac3ccf6ba2f1041347e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957678"
---
# <a name="return-statement-visual-basic"></a>Return 语句 (Visual Basic)
将控件返回到调用`Function`、 `Sub`、 `Get`、 `Set`或`Operator`过程的代码。  
  
## <a name="syntax"></a>语法  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a>部件  
 `expression`  
 在、 `Function` `Get`或过程中是必需的。`Operator` 表示要返回到调用代码的值的表达式。  
  
## <a name="remarks"></a>备注  
 `Return` `Exit Sub` `Exit Property` `expression`在或过程`Set`中, 语句等效于或语句, 不能提供。 `Sub`  
  
 `expression` `expression`在、或过程`Operator`中,`Return`语句必须包含, 并且必须计算为可转换为过程返回类型的数据类型。 `Get` `Function` `Exit Function` `Exit Property`在或过程`Get`中, 您还可以选择将表达式分配给过程名称以用作返回值, 然后执行或语句。 `Function` 在过程中, 必须使用`Return expression`。 `Operator`  
  
 可以在同一个过程`Return`中包含任意多个语句。  
  
> [!NOTE]
> `Finally`块中的代码在遇到`Try`或`Catch`块`Return`中的语句之后、但在执行该`Return`语句之前运行。 语句不能包含`Finally`在块中。 `Return`  
  
## <a name="example"></a>示例  
 下面的示例多次使用`Return`语句, 以便在过程不需要执行任何其他操作时返回到调用代码。  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a>请参阅

- [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Get 语句](../../../visual-basic/language-reference/statements/get-statement.md)
- [Set 语句](../../../visual-basic/language-reference/statements/set-statement.md)
- [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)
- [Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
