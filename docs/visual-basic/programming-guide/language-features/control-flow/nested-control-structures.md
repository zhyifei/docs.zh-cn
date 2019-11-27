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
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="921b4-102">嵌套的控件结构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="921b4-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="921b4-103">可以在其他控制语句中放置 control 语句，例如 `For...Next` 循环内的 `If...Then...Else` 块。</span><span class="sxs-lookup"><span data-stu-id="921b4-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="921b4-104">放置在另一控制语句内部的控制语句称为 "*嵌套*"。</span><span class="sxs-lookup"><span data-stu-id="921b4-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="921b4-105">嵌套级别</span><span class="sxs-lookup"><span data-stu-id="921b4-105">Nesting Levels</span></span>  
 <span data-ttu-id="921b4-106">Visual Basic 中的控制结构可以嵌套给所需的多个级别。</span><span class="sxs-lookup"><span data-stu-id="921b4-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="921b4-107">常见的做法是通过缩进每个结构的主体，使嵌套结构更具可读性。</span><span class="sxs-lookup"><span data-stu-id="921b4-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="921b4-108">集成开发环境（IDE）编辑器会自动执行此功能。</span><span class="sxs-lookup"><span data-stu-id="921b4-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="921b4-109">在下面的示例中，过程 `sumRows` 将矩阵的每一行的正面元素相加。</span><span class="sxs-lookup"><span data-stu-id="921b4-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="921b4-110">在前面的示例中，第一个 `Next` 语句关闭了内部 `For` 循环，最后一个 `Next` 语句关闭外部 `For` 循环。</span><span class="sxs-lookup"><span data-stu-id="921b4-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="921b4-111">同样，在嵌套的 `If` 语句中，`End If` 语句会自动应用到最近的 `If` 语句。</span><span class="sxs-lookup"><span data-stu-id="921b4-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="921b4-112">嵌套 `Do` 循环的工作方式类似，最内层的 `Loop` 语句与最内层的 `Do` 语句匹配。</span><span class="sxs-lookup"><span data-stu-id="921b4-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="921b4-113">对于许多控制结构，当您单击某个关键字时，将突出显示该结构中的所有关键字。</span><span class="sxs-lookup"><span data-stu-id="921b4-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="921b4-114">例如，单击 `If...Then...Else` 构造中的 `If` 时，将突出显示构造中 `If`、`Then`、`ElseIf`、`Else`和 `End If` 的所有实例。</span><span class="sxs-lookup"><span data-stu-id="921b4-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="921b4-115">若要移动到下一个或上一个突出显示的关键字，请按 CTRL + SHIFT + 向下键或 CTRL + SHIFT + 向上键。</span><span class="sxs-lookup"><span data-stu-id="921b4-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="921b4-116">嵌套不同种类的控制结构</span><span class="sxs-lookup"><span data-stu-id="921b4-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="921b4-117">您可以在另一种类型中嵌套一种控件结构。</span><span class="sxs-lookup"><span data-stu-id="921b4-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="921b4-118">下面的示例在 `For Each` 循环内使用 `With` 块，并在 `With` 块内使用嵌套 `If` 块。</span><span class="sxs-lookup"><span data-stu-id="921b4-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="921b4-119">重叠控制结构</span><span class="sxs-lookup"><span data-stu-id="921b4-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="921b4-120">不能重叠控制结构。</span><span class="sxs-lookup"><span data-stu-id="921b4-120">You cannot overlap control structures.</span></span> <span data-ttu-id="921b4-121">这意味着，任何嵌套结构都必须完全包含在下一个最内层的结构中。</span><span class="sxs-lookup"><span data-stu-id="921b4-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="921b4-122">例如，下面的排列无效，因为 `For` 循环在内部 `With` 块终止之前终止。</span><span class="sxs-lookup"><span data-stu-id="921b4-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![显示无效嵌套示例的关系图。](./media/nested-control-structures/example-invalid-nesting.gif) 
  
 <span data-ttu-id="921b4-124">Visual Basic 编译器检测到这样的重叠控制结构并发出编译时错误。</span><span class="sxs-lookup"><span data-stu-id="921b4-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="921b4-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="921b4-125">See also</span></span>

- [<span data-ttu-id="921b4-126">控制流</span><span class="sxs-lookup"><span data-stu-id="921b4-126">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="921b4-127">决策结构</span><span class="sxs-lookup"><span data-stu-id="921b4-127">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="921b4-128">循环结构</span><span class="sxs-lookup"><span data-stu-id="921b4-128">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="921b4-129">其他控件结构</span><span class="sxs-lookup"><span data-stu-id="921b4-129">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
