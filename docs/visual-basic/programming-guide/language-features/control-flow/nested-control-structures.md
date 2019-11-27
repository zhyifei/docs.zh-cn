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
ms.openlocfilehash: 5818b13661fb4415c6f531b741b8a963a80bd2b8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348140"
---
# <a name="nested-control-structures-visual-basic"></a>嵌套的控件结构 (Visual Basic)
可以在其他控制语句中放置 control 语句，例如 `For...Next` 循环内的 `If...Then...Else` 块。 放置在另一控制语句内部的控制语句称为 "*嵌套*"。  
  
## <a name="nesting-levels"></a>嵌套级别  
 Visual Basic 中的控制结构可以嵌套给所需的多个级别。 常见的做法是通过缩进每个结构的主体，使嵌套结构更具可读性。 集成开发环境（IDE）编辑器会自动执行此功能。  
  
 在下面的示例中，过程 `sumRows` 将矩阵的每一行的正面元素相加。  
  
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
  
 在前面的示例中，第一个 `Next` 语句关闭了内部 `For` 循环，最后一个 `Next` 语句关闭外部 `For` 循环。  
  
 同样，在嵌套的 `If` 语句中，`End If` 语句会自动应用到最近的 `If` 语句。 嵌套 `Do` 循环的工作方式类似，最内层的 `Loop` 语句与最内层的 `Do` 语句匹配。  
  
> [!NOTE]
> 对于许多控制结构，当您单击某个关键字时，将突出显示该结构中的所有关键字。 例如，单击 `If...Then...Else` 构造中的 `If` 时，将突出显示构造中 `If`、`Then`、`ElseIf`、`Else`和 `End If` 的所有实例。 若要移动到下一个或上一个突出显示的关键字，请按 CTRL + SHIFT + 向下键或 CTRL + SHIFT + 向上键。  
  
## <a name="nesting-different-kinds-of-control-structures"></a>嵌套不同种类的控制结构  
 您可以在另一种类型中嵌套一种控件结构。 下面的示例在 `For Each` 循环内使用 `With` 块，并在 `With` 块内使用嵌套 `If` 块。  
  
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
  
## <a name="overlapping-control-structures"></a>重叠控制结构  
 不能重叠控制结构。 这意味着，任何嵌套结构都必须完全包含在下一个最内层的结构中。 例如，下面的排列无效，因为 `For` 循环在内部 `With` 块终止之前终止。  
  
 ![显示无效嵌套示例的关系图。](./media/nested-control-structures/example-invalid-nesting.gif) 
  
 Visual Basic 编译器检测到这样的重叠控制结构并发出编译时错误。  
  
## <a name="see-also"></a>另请参阅

- [控制流](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [决策结构](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [循环结构](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [其他控件结构](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
