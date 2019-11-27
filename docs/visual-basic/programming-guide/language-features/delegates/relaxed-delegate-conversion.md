---
title: 宽松委托转换
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: ffb242842553382ba26121333c38fc65eaa168a9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345222"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a>宽松委托转换 (Visual Basic)
通过宽松委托转换，您可以将 sub 和函数分配给委托或处理程序，即使它们的签名不相同。 因此，绑定到委托将与已允许方法调用的绑定一致。  
  
## <a name="parameters-and-return-type"></a>参数和返回类型  
 宽松转换要求在将 `Option Strict` 设置为 `On`时满足以下条件：  
  
- 必须将每个委托参数的数据类型的扩大转换为分配的函数或 `Sub`的相应参数的数据类型。 在下面的示例中，委托 `Del1` 具有一个参数，即一个 `Integer`。 已分配 lambda 表达式中的参数 `m` 必须具有一个数据类型，该数据类型的数据类型为，其中存在从 `Integer`的扩大转换，如 `Long` 或 `Double`。  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     仅当 `Option Strict` 设置为 `Off`时，才允许收缩转换。  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- 扩大转换必须与指定函数的返回类型或 `Sub` 为委托的返回类型的方向相反。 在下面的示例中，每个已分配 lambda 表达式的主体的计算结果都必须是扩大到 `Integer` 的数据类型，因为 `del1` 的返回类型是 `Integer`的。  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 如果 `Option Strict` 设置为 `Off`，则将在这两个方向上删除扩大限制。  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a>省略参数规范  
 宽松委托还允许您完全省略分配的方法中的参数规范：  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 请注意，不能指定某些参数并忽略其他参数。  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 在某些情况下，忽略参数的功能非常有用，例如定义一个事件处理程序，其中涉及多个复杂参数。 不使用某些事件处理程序的参数。 相反，处理程序将直接访问在其上注册事件的控件的状态，并忽略参数。 宽松的委托允许在没有歧义结果时省略此类声明中的参数。 在下面的示例中，`OnClick` 的完全指定方法可以重写为 `RelaxedOnClick`。  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>AddressOf 示例  
 前面的示例中使用了 Lambda 表达式，使类型关系易于查看。 但是，允许使用 `AddressOf`、`Handles`或 `AddHandler`的委托分配使用相同的松弛法。  
  
 在下面的示例中，函数 `f1`、`f2`、`f3`和 `f4` 都可以分配给 `Del1`。  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 仅当 `Option Strict` 设置为 `Off`时，下面的示例才有效。  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a>删除函数返回  
 通过宽松委托转换，您可以将函数分配给 `Sub` 委托，从而有效地忽略函数的返回值。 但是，不能向函数委托分配 `Sub`。 在下面的示例中，函数 `doubler` 的地址分配给 `Sub` 委托 `Del3`。  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a>另请参阅

- [Lambda 表达式](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [扩大转换和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [委托](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [如何：在 Visual Basic 中将过程传递给另一过程](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
