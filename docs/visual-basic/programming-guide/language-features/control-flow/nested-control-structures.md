---
title: 嵌套的控件结构
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, control flow
- control structures [Visual Basic], nested
- conditional statements [Visual Basic], nested
- statements [Visual Basic], control flow
- control flow [Visual Basic], nested control statements
- structures [Visual Basic], nested control
- nested control statements [Visual Basic]
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
ms.openlocfilehash: b696c79cd3cada4416b3f4b6cdf96f00b89a5a0a
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266919"
---
# <a name="nested-control-structures-visual-basic"></a>嵌套的控件结构 (Visual Basic)
您可以将控制语句放置在其他控制语句中，例如`If...Then...Else``For...Next`循环中的块。 放置在另一个控制语句中的控制语句*表示嵌套。*  
  
## <a name="nesting-levels"></a>嵌套级别  
 Visual Basic 中的控件结构可以嵌套到所需的尽可能多的级别。 通常的做法是通过缩进每个结构的主体来使嵌套结构更具可读性。 集成开发环境 （IDE） 编辑器会自动这样做。  
  
 在下面的示例中，该过程`sumRows`将矩阵每行的正元素相加。  
  
```vb
Public Sub sumRows(ByVal a(,) As Double, ByRef r() As Double)  
    Dim i, j As Integer  
    For i = 0 To UBound(a, 1)  
        r(i) = 0  
        For j = 0 To UBound(a, 2)  
            If a(i, j) > 0 Then  
                r(i) = r(i) + a(i, j)  
            End If  
        Next j  
    Next i  
End Sub  
```  
  
 在前面的示例中，第一个`Next`语句关闭内部`For`循环，最后一`Next`个语句关闭外部`For`循环。  
  
 同样，在嵌套`If`语句中，`End If`语句会自动应用于最近的先前`If`语句。 嵌套`Do`循环的工作方式类似，其中最`Loop`里面的语句与最`Do`里面的语句匹配。  
  
> [!NOTE]
> 对于许多控件结构，当您单击关键字时，结构中的所有关键字都会突出显示。 例如`If`，当您在`If...Then...Else`构造中单击时，构造`If``Then``ElseIf``Else``End If`中的所有实例将突出显示。 要移动到下一个或上一个突出显示的关键字，请按 CTRL_SHIFT_向下箭头或 CTRL_SHIFT_UP 箭头。  
  
## <a name="nesting-different-kinds-of-control-structures"></a>嵌套不同类型的控制结构  
 可以将一种控制结构嵌套在另一种类型中。 下面的`With`示例使用`For Each`循环中的块和块内的`If``With`嵌套块。  
  
```vb
For Each ctl As System.Windows.Forms.Control In Me.Controls  
    With ctl  
        .BackColor = System.Drawing.Color.Yellow  
        .ForeColor = System.Drawing.Color.Black  
        If .CanFocus Then  
            .Text = "Colors changed"  
            If Not .Focus() Then  
                ' Insert code to process failed focus.  
            End If  
        End If  
    End With  
Next ctl  
```  
  
## <a name="overlapping-control-structures"></a>重叠的控制结构  
 不能重叠控制结构。 这意味着任何嵌套结构都必须完全包含在下一个最内部结构中。 例如，以下排列无效，`For`因为循环在内部`With`块终止之前终止。  
  
 ![显示无效嵌套示例的图表。](./media/nested-control-structures/example-invalid-nesting.gif)
  
 Visual Basic 编译器检测此类重叠的控制结构，并发出编译时错误信号。  
  
## <a name="see-also"></a>另请参阅

- [控制流](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [决策结构](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [循环结构](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [其他控件结构](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
