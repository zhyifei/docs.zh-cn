---
title: "嵌套的控件结构 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
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
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 22adf4086cd494202a540b2ec16310072329b6ca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="3acc5-102">嵌套的控件结构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3acc5-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="3acc5-103">你可以控制将语句放在其他控制语句，例如`If...Then...Else`中块`For...Next`循环。</span><span class="sxs-lookup"><span data-stu-id="3acc5-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="3acc5-104">控制语句放在另一个控制语句称为*嵌套*。</span><span class="sxs-lookup"><span data-stu-id="3acc5-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="3acc5-105">嵌套级别</span><span class="sxs-lookup"><span data-stu-id="3acc5-105">Nesting Levels</span></span>  
 <span data-ttu-id="3acc5-106">中的控制结构[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]可以嵌套到尽可能多的级别。</span><span class="sxs-lookup"><span data-stu-id="3acc5-106">Control structures in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] can be nested to as many levels as you want.</span></span> <span data-ttu-id="3acc5-107">它是常见做法使嵌套的结构的缩进的每个正文更具可读性。</span><span class="sxs-lookup"><span data-stu-id="3acc5-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="3acc5-108">集成的开发环境 (IDE) 编辑器自动执行此操作。</span><span class="sxs-lookup"><span data-stu-id="3acc5-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="3acc5-109">在下面的示例中，该过程`sumRows`将相加矩阵中每一行的正元素。</span><span class="sxs-lookup"><span data-stu-id="3acc5-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="3acc5-110">在前面的示例中，第一个`Next`语句关闭内部`For`循环和最后一个`Next`语句关闭外部`For`循环。</span><span class="sxs-lookup"><span data-stu-id="3acc5-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="3acc5-111">同样，在嵌套`If`语句，`End If`语句自动应用到最近的前`If`语句。</span><span class="sxs-lookup"><span data-stu-id="3acc5-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="3acc5-112">嵌套`Do`循环工作以类似的方式，使用最内层`Loop`语句匹配最里面`Do`语句。</span><span class="sxs-lookup"><span data-stu-id="3acc5-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3acc5-113">许多控件结构，当您单击某个关键字，所有结构中的关键字将突出显示。</span><span class="sxs-lookup"><span data-stu-id="3acc5-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="3acc5-114">例如，当单击`If`中`If...Then...Else`构造、 的所有实例`If`， `Then`， `ElseIf`， `Else`，和`End If`在构造将突出显示。</span><span class="sxs-lookup"><span data-stu-id="3acc5-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="3acc5-115">若要将移到下一步或上一个突出显示关键字，按 CTRL + SHIFT + 向下键或 CTRL + SHIFT + 向上键。</span><span class="sxs-lookup"><span data-stu-id="3acc5-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="3acc5-116">嵌套不同类型的控件结构</span><span class="sxs-lookup"><span data-stu-id="3acc5-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="3acc5-117">你可以嵌套在另一种类的控件结构的一种类型。</span><span class="sxs-lookup"><span data-stu-id="3acc5-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="3acc5-118">下面的示例使用`With`内阻止`For Each`循环和嵌套`If`块内`With`块。</span><span class="sxs-lookup"><span data-stu-id="3acc5-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="3acc5-119">重叠控件结构</span><span class="sxs-lookup"><span data-stu-id="3acc5-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="3acc5-120">不能重叠控制结构。</span><span class="sxs-lookup"><span data-stu-id="3acc5-120">You cannot overlap control structures.</span></span> <span data-ttu-id="3acc5-121">这意味着，任何嵌套的结构必须完全包含在下一步的内部结构。</span><span class="sxs-lookup"><span data-stu-id="3acc5-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="3acc5-122">例如，下面的排列是无效因为`For`循环将终止之前内部`With`块终止。</span><span class="sxs-lookup"><span data-stu-id="3acc5-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 <span data-ttu-id="3acc5-123">![无效嵌套示意图](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")</span><span class="sxs-lookup"><span data-stu-id="3acc5-123">![Graphic diagram of invalid nesting](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")</span></span>  
<span data-ttu-id="3acc5-124">无效嵌套的并使用结构</span><span class="sxs-lookup"><span data-stu-id="3acc5-124">Invalid nesting of For and With structures</span></span>  
  
 <span data-ttu-id="3acc5-125">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器检测到这种重叠的控制结构和发出信号，编译时错误。</span><span class="sxs-lookup"><span data-stu-id="3acc5-125">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3acc5-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3acc5-126">See Also</span></span>  
 [<span data-ttu-id="3acc5-127">控制流</span><span class="sxs-lookup"><span data-stu-id="3acc5-127">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="3acc5-128">决策结构</span><span class="sxs-lookup"><span data-stu-id="3acc5-128">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="3acc5-129">循环结构</span><span class="sxs-lookup"><span data-stu-id="3acc5-129">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="3acc5-130">其他控件结构</span><span class="sxs-lookup"><span data-stu-id="3acc5-130">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
