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
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="0150b-102">嵌套的控件结构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0150b-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="0150b-103">您可以将控制语句放置在其他控制语句中，例如`If...Then...Else``For...Next`循环中的块。</span><span class="sxs-lookup"><span data-stu-id="0150b-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="0150b-104">放置在另一个控制语句中的控制语句*表示嵌套。*</span><span class="sxs-lookup"><span data-stu-id="0150b-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="0150b-105">嵌套级别</span><span class="sxs-lookup"><span data-stu-id="0150b-105">Nesting Levels</span></span>  
 <span data-ttu-id="0150b-106">Visual Basic 中的控件结构可以嵌套到所需的尽可能多的级别。</span><span class="sxs-lookup"><span data-stu-id="0150b-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="0150b-107">通常的做法是通过缩进每个结构的主体来使嵌套结构更具可读性。</span><span class="sxs-lookup"><span data-stu-id="0150b-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="0150b-108">集成开发环境 （IDE） 编辑器会自动这样做。</span><span class="sxs-lookup"><span data-stu-id="0150b-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="0150b-109">在下面的示例中，该过程`sumRows`将矩阵每行的正元素相加。</span><span class="sxs-lookup"><span data-stu-id="0150b-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="0150b-110">在前面的示例中，第一个`Next`语句关闭内部`For`循环，最后一`Next`个语句关闭外部`For`循环。</span><span class="sxs-lookup"><span data-stu-id="0150b-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="0150b-111">同样，在嵌套`If`语句中，`End If`语句会自动应用于最近的先前`If`语句。</span><span class="sxs-lookup"><span data-stu-id="0150b-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="0150b-112">嵌套`Do`循环的工作方式类似，其中最`Loop`里面的语句与最`Do`里面的语句匹配。</span><span class="sxs-lookup"><span data-stu-id="0150b-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0150b-113">对于许多控件结构，当您单击关键字时，结构中的所有关键字都会突出显示。</span><span class="sxs-lookup"><span data-stu-id="0150b-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="0150b-114">例如`If`，当您在`If...Then...Else`构造中单击时，构造`If``Then``ElseIf``Else``End If`中的所有实例将突出显示。</span><span class="sxs-lookup"><span data-stu-id="0150b-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="0150b-115">要移动到下一个或上一个突出显示的关键字，请按 CTRL_SHIFT_向下箭头或 CTRL_SHIFT_UP 箭头。</span><span class="sxs-lookup"><span data-stu-id="0150b-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="0150b-116">嵌套不同类型的控制结构</span><span class="sxs-lookup"><span data-stu-id="0150b-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="0150b-117">可以将一种控制结构嵌套在另一种类型中。</span><span class="sxs-lookup"><span data-stu-id="0150b-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="0150b-118">下面的`With`示例使用`For Each`循环中的块和块内的`If``With`嵌套块。</span><span class="sxs-lookup"><span data-stu-id="0150b-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="0150b-119">重叠的控制结构</span><span class="sxs-lookup"><span data-stu-id="0150b-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="0150b-120">不能重叠控制结构。</span><span class="sxs-lookup"><span data-stu-id="0150b-120">You cannot overlap control structures.</span></span> <span data-ttu-id="0150b-121">这意味着任何嵌套结构都必须完全包含在下一个最内部结构中。</span><span class="sxs-lookup"><span data-stu-id="0150b-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="0150b-122">例如，以下排列无效，`For`因为循环在内部`With`块终止之前终止。</span><span class="sxs-lookup"><span data-stu-id="0150b-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![显示无效嵌套示例的图表。](./media/nested-control-structures/example-invalid-nesting.gif)
  
 <span data-ttu-id="0150b-124">Visual Basic 编译器检测此类重叠的控制结构，并发出编译时错误信号。</span><span class="sxs-lookup"><span data-stu-id="0150b-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0150b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0150b-125">See also</span></span>

- [<span data-ttu-id="0150b-126">控制流</span><span class="sxs-lookup"><span data-stu-id="0150b-126">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="0150b-127">决策结构</span><span class="sxs-lookup"><span data-stu-id="0150b-127">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="0150b-128">循环结构</span><span class="sxs-lookup"><span data-stu-id="0150b-128">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="0150b-129">其他控件结构</span><span class="sxs-lookup"><span data-stu-id="0150b-129">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
