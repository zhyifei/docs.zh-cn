---
title: 决策结构 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3b89d6f9b27e086b657c29f3353b63cdd855ae19
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="decision-structures-visual-basic"></a>决策结构 (Visual Basic)
Visual Basic，可以测试条件，然后执行不同的操作，具体取决于该测试的结果。 你可以测试条件是 true 或 false 的各种值的表达式，或生成时执行一系列语句的各种异常。  
  
 下图显示一个决策结构，它将针对均为 true 的条件测试并采取不同的操作，具体取决于它是 true 还是 false。  
  
 ![If 的流程图...然后...其他构造](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")  
在条件为 true，当为 false 时执行不同操作  
  
## <a name="ifthenelse-construction"></a>如果...然后...其他构造  
 `If...Then...Else` 构造，可以测试的一个或多个条件，然后运行一个或多个语句，具体取决于每个条件。 你可以测试条件，然后通过以下方式执行的操作：  
  
-   如果条件为，运行一个或多个语句 `True`  
  
-   如果条件为，运行一个或多个语句 `False`  
  
-   如果条件为运行某些语句`True`和其他若是 `False`  
  
-   如果以前条件为，测试的其他条件 `False`  
  
 提供所有这些可能性的控件结构[如果...然后...Else 语句](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)。 如果必须只有一个测试和要运行的一个语句，你可以使用的单行版本。 如果你有一组更复杂的条件和操作，你可以使用多个行版本。  
  
## <a name="selectcase-construction"></a>选择...Case 构造  
 `Select...Case`构造允许您评估一次表达式和运行一组不同的基于不同的可能值的语句。 有关详细信息，请参阅[选择...Case 语句](../../../../visual-basic/language-reference/statements/select-case-statement.md)。  
  
## <a name="trycatchfinally-construction"></a>重试...Catch...最后构造  
 `Try...Catch...Finally` 构造，可以运行一组保留控制，如果您的语句的任何一个导致异常的环境下的语句。 你可以执行不同操作针对不同的异常。 你可以选择指定的退出整个之前运行的代码块`Try...Catch...Finally`构造，而不考虑所发生的情况。 有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。  
  
> [!NOTE]
>  许多控件结构，当您单击某个关键字，所有结构中的关键字将突出显示。 例如，当单击`If`中`If...Then...Else`构造、 的所有实例`If`， `Then`， `ElseIf`， `Else`，和`End If`在构造将突出显示。 若要将移到下一步或上一个突出显示关键字，按 CTRL + SHIFT + 向下键或 CTRL + SHIFT + 向上键。  
  
## <a name="see-also"></a>请参阅  
 [控制流](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [循环结构](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [其他控件结构](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [嵌套的控件结构](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [If 运算符](../../../../visual-basic/language-reference/operators/if-operator.md)
