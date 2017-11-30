---
title: "Return 语句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b66d16a249164b8989f05f10c785b97055bfde9e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="return-statement-visual-basic"></a>Return 语句 (Visual Basic)
将控制权返回给调用的代码`Function`， `Sub`， `Get`， `Set`，或`Operator`过程。  
  
## <a name="syntax"></a>语法  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a>部件  
 `expression`  
 中所需`Function`， `Get`，或`Operator`过程。 表示要返回到调用代码的值的表达式。  
  
## <a name="remarks"></a>备注  
 在`Sub`或`Set`过程中，`Return`语句是等效于`Exit Sub`或`Exit Property`语句，和`expression`必须未提供。  
  
 在`Function`， `Get`，或`Operator`过程中，`Return`语句必须包含`expression`，和`expression`计算结果必须为可以转换为的过程的返回类型的数据类型。 在`Function`或`Get`过程中，你还可以选择表达式分配到过程名称以作为返回值，然后执行`Exit Function`或`Exit Property`语句。 在`Operator`过程中，你必须使用`Return``expression`。  
  
 可以包括任意多个`Return`应在相同的过程中适当的语句。  
  
> [!NOTE]
>  中的代码`Finally`块之后运行`Return`中的语句`Try`或`Catch`块是遇到，但在此之前`Return`执行语句。 A`Return`语句不能包含在`Finally`块。  
  
## <a name="example"></a>示例  
 下面的示例使用`Return`语句数次以返回到调用代码时不需要执行任何其他操作过程。  
  
 [!code-vb[VbVbalrStatements#53](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/return-statement_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Get 语句](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Set 语句](../../../visual-basic/language-reference/statements/set-statement.md)  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
