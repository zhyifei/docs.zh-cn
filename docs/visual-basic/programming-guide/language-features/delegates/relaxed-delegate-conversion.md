---
title: 宽松委托转换 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: c4a41bf74716a6ea7d3c1139651834acccf27657
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="relaxed-delegate-conversion-visual-basic"></a>宽松委托转换 (Visual Basic)
宽松的委托转换，可将订阅和函数分配给委托或处理程序，即使在它们的签名不相同。 因此，绑定到委托将与已允许的方法调用绑定保持一致。  
  
## <a name="parameters-and-return-type"></a>参数和返回类型  
 替代签名完全匹配宽松的转换需要满足以下条件时`Option Strict`设置为`On`:  
  
-   扩大转换为所分配函数的相应参数的数据类型必须存在从每个委托参数的数据类型或`Sub`。 在下面的示例中，委托`Del1`具有一个参数、 `Integer`。 参数`m`中分配的 lambda 表达式必须具有的扩大转换数据类型`Integer`，如`Long`或`Double`。  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]  
  
     收缩转换允许仅当`Option Strict`设置为`Off`。  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]  
  
-   扩大转换必须存在分配的函数的返回类型从相反的方向或`Sub`到委托的返回类型。 在以下示例中，每个分配的 lambda 表达式的主体计算结果必须为数据类型扩大到`Integer`因为返回类型的`del1`是`Integer`。  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]  
  
 如果`Option Strict`设置为`Off`，扩大限制已从两个方向中删除。  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]  
  
## <a name="omitting-parameter-specifications"></a>省略参数规范  
 宽松的委托还允许您将能够完全省略分配的方法中的参数规范：  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]  
  
 请注意，你不能指定某些参数并且省略其他人。  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]  
  
 若要省略参数的能力是如定义事件处理程序，其中包含多个复杂参数的情况下有用。 不使用某些事件处理程序的自变量。 相反，该处理程序直接访问的控件的事件在其注册，并忽略这些参数的状态。 宽松的委托允许你忽略不产生多义性时此类声明中的参数。 在下面的示例中，完全指定的方法`OnClick`可以重写为`RelaxedOnClick`。  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>AddressOf 示例  
 在前面的示例使用 lambda 表达式以便可以方便地查看类型关系。 但是，相同松弛法允许使用的委托分配`AddressOf`， `Handles`，或`AddHandler`。  
  
 在下面的示例中，函数`f1`， `f2`， `f3`，和`f4`都可以分配到`Del1`。  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]  
  
 下面的示例是仅当`Option Strict`设置为`Off`。  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]  
  
## <a name="dropping-function-returns"></a>删除函数返回值  
 宽松的委托转换使您能够分配到函数`Sub`委托，有效地忽略该函数的返回值。 但是，不能将分配`Sub`到函数委托。 在下面的示例中，函数的地址`doubler`分配给`Sub`委托`Del3`。  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]  
  
## <a name="see-also"></a>请参阅  
 [Lambda 表达式](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [扩大转换和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [委托](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [如何：在 Visual Basic 中将过程传递给另一过程](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)  
 [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
