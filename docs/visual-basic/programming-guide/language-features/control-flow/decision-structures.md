---
title: 决策结构
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: d0d4039ff2edc61ee8b4b732c6adcb6e420d73ea
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353966"
---
# <a name="decision-structures-visual-basic"></a>决策结构 (Visual Basic)
Visual Basic 允许您测试条件并根据该测试的结果执行不同的操作。 对于表达式的各个值，或者在执行一系列语句时生成的各种异常，可以测试条件是 true 还是 false。  
  
 下图显示了一个决策结构，该结构用于测试条件是否为 true，并执行不同的操作，具体取决于它是 true 还是 false。  
  
 ![If...Then...Else 构造。](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a>If...Then...Else 构造  
 `If...Then...Else` 构造，你可以测试一个或多个条件并根据每个条件运行一个或多个语句。 可以通过以下方式测试条件并采取措施：  
  
- 如果条件为，则运行一个或多个语句 `True`  
  
- 如果条件为，则运行一个或多个语句 `False`  
  
- 如果条件 `True`，则运行某些语句，如果 `False`，则运行其他语句  
  
- 如果 `False` 上一个条件，则测试其他条件  
  
 提供所有这些可能的控制结构是[If .。。Then .。。Else 语句](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)。 如果仅有一个测试和一个语句要运行，则可以使用单行版本。 如果有更复杂的条件和操作集，则可以使用多行版本。  
  
## <a name="selectcase-construction"></a>Select...Case 构造  
 `Select...Case` 构造使你可以一次计算一个表达式，并基于不同的可能值运行不同的语句集。 有关详细信息，请参阅[Select .。。Case 语句](../../../../visual-basic/language-reference/statements/select-case-statement.md)。  
  
## <a name="trycatchfinally-construction"></a>Try...Catch...Finally 构造  
 `Try...Catch...Finally` 构造，可让你在某个环境下运行一组语句，如果你的任何一条语句导致异常，该环境将保留控制权。 对于不同的异常，可以执行不同的操作。 无论发生何种情况，您都可以根据需要指定在退出整个 `Try...Catch...Finally` 构造之前运行的代码块。 有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。  
  
> [!NOTE]
> 对于许多控制结构，当您单击某个关键字时，将突出显示该结构中的所有关键字。 例如，单击 `If...Then...Else` 构造中的 `If` 时，将突出显示构造中 `If`、`Then`、`ElseIf`、`Else`和 `End If` 的所有实例。 若要移动到下一个或上一个突出显示的关键字，请按 CTRL + SHIFT + 向下键或 CTRL + SHIFT + 向上键。  
  
## <a name="see-also"></a>另请参阅

- [控制流](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [循环结构](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [其他控件结构](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [嵌套的控件结构](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [If 运算符](../../../../visual-basic/language-reference/operators/if-operator.md)
