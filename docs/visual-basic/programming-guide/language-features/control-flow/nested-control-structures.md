---
title: "嵌套的控件结构 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, control flow
- control structures, nested
- conditional statements, nested
- statements [Visual Basic], control flow
- control flow, nested control statements
- structures, nested control
- nested control statements
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8275a0628c8593d9e6c55ef27adcde2acec31547
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="89f3d-102">嵌套的控件结构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89f3d-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="89f3d-103">您可以控制将语句放在其他控制语句中，例如`If...Then...Else`中块`For...Next`循环。</span><span class="sxs-lookup"><span data-stu-id="89f3d-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="89f3d-104">说是一个控制语句放在另一个控制语句可*嵌套*。</span><span class="sxs-lookup"><span data-stu-id="89f3d-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="89f3d-105">嵌套级别</span><span class="sxs-lookup"><span data-stu-id="89f3d-105">Nesting Levels</span></span>  
 <span data-ttu-id="89f3d-106">中的控制结构[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]可以嵌套到任意数量的级别。</span><span class="sxs-lookup"><span data-stu-id="89f3d-106">Control structures in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] can be nested to as many levels as you want.</span></span> <span data-ttu-id="89f3d-107">它是常见的做法使嵌套的结构通过缩进每个正文更具可读性。</span><span class="sxs-lookup"><span data-stu-id="89f3d-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="89f3d-108">集成的开发环境 (IDE) 编辑器自动执行此操作。</span><span class="sxs-lookup"><span data-stu-id="89f3d-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="89f3d-109">在下面的示例中，该过程`sumRows`相加矩阵的每个行的正元素。</span><span class="sxs-lookup"><span data-stu-id="89f3d-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="89f3d-110">在前面的示例中，第一个`Next`语句关闭内部`For`循环和最后一个`Next`语句关闭外部`For`循环。</span><span class="sxs-lookup"><span data-stu-id="89f3d-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="89f3d-111">同样，在嵌套`If`语句，`End If`语句自动应用到最近的前`If`语句。</span><span class="sxs-lookup"><span data-stu-id="89f3d-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="89f3d-112">嵌套`Do`循环的工作方式类似，最里层`Loop`语句匹配里面`Do`语句。</span><span class="sxs-lookup"><span data-stu-id="89f3d-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89f3d-113">对于许多控制结构，当您单击某个关键字在结构中的关键字的所有都会突出显示。</span><span class="sxs-lookup"><span data-stu-id="89f3d-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="89f3d-114">例如，当您单击`If`中`If...Then...Else`构造、 的所有实例`If`， `Then`， `ElseIf`， `Else`，和`End If`在构造过程中会突出显示。</span><span class="sxs-lookup"><span data-stu-id="89f3d-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="89f3d-115">若要将移动到下一步或上一个突出显示关键字，按 CTRL + SHIFT + 向下键或 CTRL + SHIFT + 向上键。</span><span class="sxs-lookup"><span data-stu-id="89f3d-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="89f3d-116">嵌套不同类型的控件结构</span><span class="sxs-lookup"><span data-stu-id="89f3d-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="89f3d-117">您可以嵌套在另一种控制结构的一种。</span><span class="sxs-lookup"><span data-stu-id="89f3d-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="89f3d-118">下面的示例使用`With`在此块内`For Each`循环，而且嵌套`If`块内`With`块。</span><span class="sxs-lookup"><span data-stu-id="89f3d-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="89f3d-119">重叠的控件结构</span><span class="sxs-lookup"><span data-stu-id="89f3d-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="89f3d-120">不能重叠控制结构。</span><span class="sxs-lookup"><span data-stu-id="89f3d-120">You cannot overlap control structures.</span></span> <span data-ttu-id="89f3d-121">这意味着，任何嵌套的结构都必须完全包含在下一步最里面的结构。</span><span class="sxs-lookup"><span data-stu-id="89f3d-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="89f3d-122">例如，下面的排列是无效因为`For`循环将终止之前内部`With`块终止。</span><span class="sxs-lookup"><span data-stu-id="89f3d-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 <span data-ttu-id="89f3d-123">![无效嵌套示意图](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")</span><span class="sxs-lookup"><span data-stu-id="89f3d-123">![Graphic diagram of invalid nesting](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")</span></span>  
<span data-ttu-id="89f3d-124">无效嵌套的并且具有结构</span><span class="sxs-lookup"><span data-stu-id="89f3d-124">Invalid nesting of For and With structures</span></span>  
  
 <span data-ttu-id="89f3d-125">[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器检测到这种重叠的控制结构和标志编译时错误。</span><span class="sxs-lookup"><span data-stu-id="89f3d-125">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89f3d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89f3d-126">See Also</span></span>  
 <span data-ttu-id="89f3d-127">[控制流](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span><span class="sxs-lookup"><span data-stu-id="89f3d-127">[Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span></span>  
<span data-ttu-id="89f3d-128"> [决策结构](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span><span class="sxs-lookup"><span data-stu-id="89f3d-128"> [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span></span>  
<span data-ttu-id="89f3d-129"> [循环结构](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span><span class="sxs-lookup"><span data-stu-id="89f3d-129"> [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span></span>  
<span data-ttu-id="89f3d-130"> [其他控件结构](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)</span><span class="sxs-lookup"><span data-stu-id="89f3d-130"> [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)</span></span>
