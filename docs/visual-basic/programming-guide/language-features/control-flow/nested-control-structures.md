---
title: 嵌套的控件结构 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, control flow
- control structures [Visual Basic], nested
- conditional statements [Visual Basic], nested
- statements [Visual Basic], control flow
- control flow [Visual Basic], nested control statements
- structures [Visual Basic], nested control
- nested control statements [Visual Basic]
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f2c91bcdd741ef75417fe50b0c08bd0f9bd5ff80
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="nested-control-structures-visual-basic"></a>嵌套的控件结构 (Visual Basic)
你可以控制将语句放在其他控制语句，例如`If...Then...Else`中块`For...Next`循环。 控制语句放在另一个控制语句称为*嵌套*。  
  
## <a name="nesting-levels"></a>嵌套级别  
 在 Visual Basic 中的控件结构就可以嵌入到尽可能多的级别。 它是常见做法使嵌套的结构的缩进的每个正文更具可读性。 集成的开发环境 (IDE) 编辑器自动执行此操作。  
  
 在下面的示例中，该过程`sumRows`将相加矩阵中每一行的正元素。  
  
```  
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
  
 在前面的示例中，第一个`Next`语句关闭内部`For`循环和最后一个`Next`语句关闭外部`For`循环。  
  
 同样，在嵌套`If`语句，`End If`语句自动应用到最近的前`If`语句。 嵌套`Do`循环工作以类似的方式，使用最内层`Loop`语句匹配最里面`Do`语句。  
  
> [!NOTE]
>  许多控件结构，当您单击某个关键字，所有结构中的关键字将突出显示。 例如，当单击`If`中`If...Then...Else`构造、 的所有实例`If`， `Then`， `ElseIf`， `Else`，和`End If`在构造将突出显示。 若要将移到下一步或上一个突出显示关键字，按 CTRL + SHIFT + 向下键或 CTRL + SHIFT + 向上键。  
  
## <a name="nesting-different-kinds-of-control-structures"></a>嵌套不同类型的控件结构  
 你可以嵌套在另一种类的控件结构的一种类型。 下面的示例使用`With`内阻止`For Each`循环和嵌套`If`块内`With`块。  
  
```  
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
  
## <a name="overlapping-control-structures"></a>重叠控件结构  
 不能重叠控制结构。 这意味着，任何嵌套的结构必须完全包含在下一步的内部结构。 例如，下面的排列是无效因为`For`循环将终止之前内部`With`块终止。  
  
 ![无效嵌套示意图](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")  
无效嵌套的并使用结构  
  
 Visual Basic 编译器检测到这种重叠的控制结构，并发出信号编译时错误。  
  
## <a name="see-also"></a>请参阅  
 [控制流](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [决策结构](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [循环结构](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [其他控件结构](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
