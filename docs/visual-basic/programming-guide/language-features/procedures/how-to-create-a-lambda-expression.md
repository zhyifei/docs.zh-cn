---
title: 如何：创建 Lambda 表达式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: f437166bc5206b4145d6508aa2131ec94d6eca95
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653541"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a>如何：创建 Lambda 表达式 (Visual Basic)
A *lambda 表达式*是函数或子例程的不具有名称。 一个委托类型有效的任何地方，可以使用 lambda 表达式。  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a>若要创建的单行 lambda 表达式函数  
  
1.  在委托类型可以使用其中任何情况下，键入关键字`Function`，下面的示例所示：  
  
     `Dim add1 =`   `Function`  
  
2.  在括号内后直接, `Function`，键入函数的参数。 请注意，未指定的名称后`Function`。  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3.  以下参数列表中，作为函数的正文中键入一个表达式。 表达式计算结果为的值是由该函数返回的值。 不使用`As`子句指定返回类型。  
  
     [!code-vb[VbVbalrLambdas#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]  
  
     调用 lambda 表达式传入一个整数自变量。  
  
     [!code-vb[VbVbalrLambdas#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]  
  
4.  或者，按下面的示例被实现的相同的结果：  
  
     [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a>若要创建的单行 lambda 表达式子例程  
  
1.  在委托类型可以使用其中任何情况下，键入关键字`Sub`，下面的示例中所示。  
  
     `Dim add1 =`   `Sub`  
  
2.  在括号内后直接, `Sub`，键入子例程的参数。 请注意，未指定的名称后`Sub`。  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3.  以下参数列表中，键入作为子例程的正文的单个语句。  
  
     [!code-vb[VbVbalrLambdas#17](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]  
  
     Lambda 表达式通过调用传递一个字符串自变量中。  
  
     [!code-vb[VbVbalrLambdas#18](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a>若要创建一个多行 lambda 表达式函数  
  
1.  在委托类型可以使用其中任何情况下，键入关键字`Function`，下面的示例中所示。  
  
     `Dim add1 =`   `Function`  
  
2.  在括号内后直接, `Function`，键入函数的参数。 请注意，未指定的名称后`Function`。  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3.  按 Enter。 `End Function`自动添加语句。  
  
4.  该函数体内，添加以下代码以创建一个表达式并返回值。 不使用`As`子句指定返回类型。  
  
     [!code-vb[VbVbalrLambdas#19](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]  
  
     调用 lambda 表达式传入一个整数自变量。  
  
     [!code-vb[VbVbalrLambdas#20](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a>若要创建多行 lambda 表达式子例程  
  
1.  在委托类型可以使用其中任何情况下，键入关键字`Sub`，下面的示例中所示：  
  
     `Dim add1 =`   `Sub`  
  
2.  在括号内后直接, `Sub`，键入子例程的参数。 请注意，未指定的名称后`Sub`。  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3.  按 Enter。 `End Sub`自动添加语句。  
  
4.  该函数体内，添加以下代码以调用子例程时应执行。  
  
     [!code-vb[VbVbalrLambdas#21](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]  
  
     Lambda 表达式通过调用传递一个字符串自变量中。  
  
     [!code-vb[VbVbalrLambdas#22](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]  
  
## <a name="example"></a>示例  
 Lambda 表达式的一个常见用途是定义的函数，可以在作为其类型参数的自变量传递`Delegate`。 在下面的示例中，<xref:System.Diagnostics.Process.GetProcesses%2A>方法返回在本地计算机上运行的进程的数组。 <xref:System.Linq.Enumerable.Where%2A>方法从<xref:System.Linq.Enumerable>类要求`Boolean`委托作为其自变量。 示例中的 lambda 表达式用于此目的。 它将返回`True`每个进程，只有一个线程，并且初始屏幕中选择`filteredList`。  
  
 [!code-vb[VbVbalrLambdas#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]  
  
 前面的示例是等效于下面的代码，以编写[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]语法：  
  
 [!code-vb[VbVbalrLambdas#11](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Linq.Enumerable>  
 [Lambda 表达式](./lambda-expressions.md)  
 [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [委托](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [如何：在 Visual Basic 中将过程传递给另一过程](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)  
 [Delegate 语句](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
