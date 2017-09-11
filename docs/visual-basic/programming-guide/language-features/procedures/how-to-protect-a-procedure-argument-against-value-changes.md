---
title: "如何︰ 防止过程参数的值被更改 (Visual Basic 中) |Microsoft 文档"
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
- procedures, arguments
- procedures, parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures, calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
caps.latest.revision: 14
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
ms.openlocfilehash: db40b3426256e7789a5273ab4d0afc8d5b47c8a7
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a><span data-ttu-id="2d9b0-102">如何：防止过程自变量的值被更改 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d9b0-102">How to: Protect a Procedure Argument Against Value Changes (Visual Basic)</span></span>
<span data-ttu-id="2d9b0-103">如果过程声明将参数作为[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]使过程代码中调用代码参数的基础的编程元素直接引用。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-103">If a procedure declares a parameter as [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="2d9b0-104">这将允许更改基础调用代码中的参数的值的过程。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-104">This permits the procedure to change the value underlying the argument in the calling code.</span></span> <span data-ttu-id="2d9b0-105">在某些情况下调用的代码可能想要防止出现这种更改。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-105">In some cases the calling code might want to protect against such a change.</span></span>  
  
 <span data-ttu-id="2d9b0-106">您可以始终防止参数更改通过声明的相应参数[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)过程中。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-106">You can always protect an argument from change by declaring the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) in the procedure.</span></span> <span data-ttu-id="2d9b0-107">如果您想要将无法更改在某些情况下，而不是其他中给定的参数，可以将它声明`ByRef`，并让调用代码确定每个调用中的传递机制。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-107">If you want to be able to change a given argument in some cases but not others, you can declare it `ByRef` and let the calling code determine the passing mechanism in each call.</span></span> <span data-ttu-id="2d9b0-108">做到这一点通过将相应实参括在圆括号中以将其传递的值，或不将其括在圆括号中以通过引用传递。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-108">It does this by enclosing the corresponding argument in parentheses to pass it by value, or not enclosing it in parentheses to pass it by reference.</span></span> <span data-ttu-id="2d9b0-109">有关详细信息，请参阅[如何︰ 强制通过值传递到参数](./how-to-force-an-argument-to-be-passed-by-value.md)。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-109">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d9b0-110">示例</span><span class="sxs-lookup"><span data-stu-id="2d9b0-110">Example</span></span>  
 <span data-ttu-id="2d9b0-111">下面的示例演示两个过程可采用一个数组变量并运行它的元素。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-111">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="2d9b0-112">`increase`过程只需添加一个对每个元素。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-112">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="2d9b0-113">`replace`过程将一个新数组分配给该参数`a()`，然后添加一个对每个元素。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-113">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="2d9b0-114">但是，重新分配不影响调用代码中的基础数组变量。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-114">However, the reassignment does not affect the underlying array variable in the calling code.</span></span>  
  
 <span data-ttu-id="2d9b0-115">[!code-vb[VbVbcnProcedures #&35;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2d9b0-115">[!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]</span></span>  
  
 <span data-ttu-id="2d9b0-116">[!code-vb[VbVbcnProcedures #&38;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="2d9b0-116">[!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]</span></span>  
  
 <span data-ttu-id="2d9b0-117">[!code-vb[VbVbcnProcedures #&37;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="2d9b0-117">[!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]</span></span>  
  
 <span data-ttu-id="2d9b0-118">第一个`MsgBox`调用显示"之后 increase(n): 11、 21、 31、 41"。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-118">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="2d9b0-119">因为数组`n`是引用类型，`replace`可以更改其中一个成员，即使传递机制是`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-119">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="2d9b0-120">第二个`MsgBox`调用显示"之后 replace(n): 11、 21、 31、 41"。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-120">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="2d9b0-121">因为`n`传递`ByVal`，`replace`不能修改该变量`n`通过向它分配一个新数组，调用代码中。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-121">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` in the calling code by assigning a new array to it.</span></span> <span data-ttu-id="2d9b0-122">当`replace`创建新的数组实例`k`并将其分配给本地变量`a`，它将失去对引用`n`由调用代码传入的。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-122">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="2d9b0-123">当其更改的成员`a`，只有本地数组`k`受到影响。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-123">When it changes the members of `a`, only the local array `k` is affected.</span></span> <span data-ttu-id="2d9b0-124">因此，`replace`不会增加数组的值`n`调用代码中。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-124">Therefore, `replace` does not increment the values of array `n` in the calling code.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2d9b0-125">编译代码</span><span class="sxs-lookup"><span data-stu-id="2d9b0-125">Compiling the Code</span></span>  
 <span data-ttu-id="2d9b0-126">中的默认设置[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]是按值传递参数。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-126">The default in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="2d9b0-127">但是，很好的编程做法包括[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字用于声明的每个参数。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-127">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="2d9b0-128">这使您的代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="2d9b0-128">This makes your code easier to read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d9b0-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d9b0-129">See Also</span></span>  
 <span data-ttu-id="2d9b0-130">[过程](./index.md) </span><span class="sxs-lookup"><span data-stu-id="2d9b0-130">[Procedures](./index.md) </span></span>  
<span data-ttu-id="2d9b0-131"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="2d9b0-131"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="2d9b0-132"> [如何︰ 将参数传递给过程](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="2d9b0-132"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="2d9b0-133"> [通过值和通过引用传递参数](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2d9b0-133"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="2d9b0-134"> [可修改和不可修改参数之间的差异](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="2d9b0-134"> [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span></span>  
<span data-ttu-id="2d9b0-135"> [通过值和通过引用传递参数之间的差异](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2d9b0-135"> [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="2d9b0-136"> [如何︰ 更改过程参数的值](./how-to-change-the-value-of-a-procedure-argument.md) </span><span class="sxs-lookup"><span data-stu-id="2d9b0-136"> [How to: Change the Value of a Procedure Argument](./how-to-change-the-value-of-a-procedure-argument.md) </span></span>  
<span data-ttu-id="2d9b0-137"> [如何︰ 强制通过值传递参数](./how-to-force-an-argument-to-be-passed-by-value.md) </span><span class="sxs-lookup"><span data-stu-id="2d9b0-137"> [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md) </span></span>  
<span data-ttu-id="2d9b0-138"> [按位置和按名称传递参数](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="2d9b0-138"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="2d9b0-139"> [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="2d9b0-139"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
