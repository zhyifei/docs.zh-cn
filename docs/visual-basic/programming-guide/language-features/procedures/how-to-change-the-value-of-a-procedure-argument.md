---
title: "如何︰ 更改过程参数 (Visual Basic 中) 的值 |Microsoft 文档"
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
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
caps.latest.revision: 16
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
ms.openlocfilehash: 3f192d738ca2753cd12b6fffca1f4f94a606a42c
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="03e95-102">如何：更改过程自变量的值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03e95-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="03e95-103">当调用过程时，您提供每个参数对应一个过程中定义的参数。</span><span class="sxs-lookup"><span data-stu-id="03e95-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="03e95-104">在某些情况下，过程代码可以更改基础调用代码中的参数的值。</span><span class="sxs-lookup"><span data-stu-id="03e95-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="03e95-105">在其他情况下，该过程可以更改只有一个参数的本地副本。</span><span class="sxs-lookup"><span data-stu-id="03e95-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="03e95-106">当您调用过程中，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]使传递的每个参数的本地副本[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)。</span><span class="sxs-lookup"><span data-stu-id="03e95-106">When you call the procedure, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] makes a local copy of every argument that is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="03e95-107">对于每个参数传递[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]使过程代码中调用代码参数的基础的编程元素直接引用。</span><span class="sxs-lookup"><span data-stu-id="03e95-107">For each argument passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="03e95-108">如果调用代码中的基础元素是一个可修改的元素，则参数进行传递`ByRef`，过程代码可用于直接引用更改调用代码中的元素的值。</span><span class="sxs-lookup"><span data-stu-id="03e95-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="03e95-109">更改基础值</span><span class="sxs-lookup"><span data-stu-id="03e95-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="03e95-110">若要更改过程参数的调用代码中的基础值</span><span class="sxs-lookup"><span data-stu-id="03e95-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1.  <span data-ttu-id="03e95-111">在过程声明中，指定[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)对应于参数的参数。</span><span class="sxs-lookup"><span data-stu-id="03e95-111">In the procedure declaration, specify [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2.  <span data-ttu-id="03e95-112">在调用代码中，将作为参数传递的可修改的编程元素。</span><span class="sxs-lookup"><span data-stu-id="03e95-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3.  <span data-ttu-id="03e95-113">在调用代码中，不要将括在圆括号中的参数列表中的参数。</span><span class="sxs-lookup"><span data-stu-id="03e95-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4.  <span data-ttu-id="03e95-114">在过程代码中，使用参数名称将值分配给调用代码中的基础元素。</span><span class="sxs-lookup"><span data-stu-id="03e95-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="03e95-115">请参阅示例进一步向下的演示。</span><span class="sxs-lookup"><span data-stu-id="03e95-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="03e95-116">不断变化的本地副本</span><span class="sxs-lookup"><span data-stu-id="03e95-116">Changing Local Copies</span></span>  
 <span data-ttu-id="03e95-117">如果调用代码中的基础元素是不可更改的元素，或者如果传递参数`ByVal`，过程将无法更改它调用的代码中的值。</span><span class="sxs-lookup"><span data-stu-id="03e95-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="03e95-118">但是，该过程可以更改此类实际参数的本地副本。</span><span class="sxs-lookup"><span data-stu-id="03e95-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="03e95-119">若要更改过程参数在过程代码中的副本</span><span class="sxs-lookup"><span data-stu-id="03e95-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1.  <span data-ttu-id="03e95-120">在过程声明中，指定[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)对应于参数的参数。</span><span class="sxs-lookup"><span data-stu-id="03e95-120">In the procedure declaration, specify [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="03e95-121">- 或 -</span><span class="sxs-lookup"><span data-stu-id="03e95-121">-or-</span></span>  
  
     <span data-ttu-id="03e95-122">在调用代码中，将括在圆括号中的参数列表中的参数。</span><span class="sxs-lookup"><span data-stu-id="03e95-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="03e95-123">这样做可以强制[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]来按值传递参数，即使相应的参数指定`ByRef`。</span><span class="sxs-lookup"><span data-stu-id="03e95-123">This forces [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2.  <span data-ttu-id="03e95-124">在过程代码中，使用参数名称将值分配给该参数的本地副本。</span><span class="sxs-lookup"><span data-stu-id="03e95-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="03e95-125">不更改基础值调用的代码中。</span><span class="sxs-lookup"><span data-stu-id="03e95-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03e95-126">示例</span><span class="sxs-lookup"><span data-stu-id="03e95-126">Example</span></span>  
 <span data-ttu-id="03e95-127">下面的示例演示两个过程可采用一个数组变量并运行它的元素。</span><span class="sxs-lookup"><span data-stu-id="03e95-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="03e95-128">`increase`过程只需添加一个对每个元素。</span><span class="sxs-lookup"><span data-stu-id="03e95-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="03e95-129">`replace`过程将一个新数组分配给该参数`a()`，然后添加一个对每个元素。</span><span class="sxs-lookup"><span data-stu-id="03e95-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 <span data-ttu-id="03e95-130">[!code-vb[VbVbcnProcedures #&35;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="03e95-130">[!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]</span></span>  
  
 <span data-ttu-id="03e95-131">[!code-vb[VbVbcnProcedures #&36;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="03e95-131">[!code-vb[VbVbcnProcedures#36](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]</span></span>  
  
 <span data-ttu-id="03e95-132">[!code-vb[VbVbcnProcedures #&37;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="03e95-132">[!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]</span></span>  
  
 <span data-ttu-id="03e95-133">第一个`MsgBox`调用显示"后 increase(n): 11、 21、 31、 41"。</span><span class="sxs-lookup"><span data-stu-id="03e95-133">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="03e95-134">因为数组`n`是引用类型，`replace`可以更改其中一个成员，即使传递机制是`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="03e95-134">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="03e95-135">第二个`MsgBox`调用显示"之后 replace(n): 101、 201、 301"。</span><span class="sxs-lookup"><span data-stu-id="03e95-135">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="03e95-136">因为`n`传递`ByRef`，`replace`可以修改变量`n`中调用代码并将赋给它一个新数组。</span><span class="sxs-lookup"><span data-stu-id="03e95-136">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="03e95-137">因为`n`是引用类型，`replace`还可以更改它的成员。</span><span class="sxs-lookup"><span data-stu-id="03e95-137">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="03e95-138">您可以防止该过程修改调用代码中的变量本身。</span><span class="sxs-lookup"><span data-stu-id="03e95-138">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="03e95-139">请参阅[如何︰ 防止过程参数的值被更改](./how-to-protect-a-procedure-argument-against-value-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="03e95-139">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="03e95-140">编译代码</span><span class="sxs-lookup"><span data-stu-id="03e95-140">Compiling the Code</span></span>  
 <span data-ttu-id="03e95-141">当通过引用传递变量时，则必须使用`ByRef`关键字来指定此机制。</span><span class="sxs-lookup"><span data-stu-id="03e95-141">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="03e95-142">中的默认设置[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]是按值传递参数。</span><span class="sxs-lookup"><span data-stu-id="03e95-142">The default in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="03e95-143">但是，很好的编程做法包括[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字用于声明的每个参数。</span><span class="sxs-lookup"><span data-stu-id="03e95-143">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="03e95-144">这使您的代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="03e95-144">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="03e95-145">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="03e95-145">.NET Framework Security</span></span>  
 <span data-ttu-id="03e95-146">在允许一个过程来更改基础调用代码中的参数的值都具有潜在的风险。</span><span class="sxs-lookup"><span data-stu-id="03e95-146">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="03e95-147">请确保您希望此值可更改，并做好准备，然后再使用它的有效性检查它。</span><span class="sxs-lookup"><span data-stu-id="03e95-147">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03e95-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03e95-148">See Also</span></span>  
 <span data-ttu-id="03e95-149">[过程](./index.md) </span><span class="sxs-lookup"><span data-stu-id="03e95-149">[Procedures](./index.md) </span></span>  
<span data-ttu-id="03e95-150"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="03e95-150"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="03e95-151"> [如何︰ 将参数传递给过程](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="03e95-151"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="03e95-152"> [通过值和通过引用传递参数](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="03e95-152"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="03e95-153"> [可修改和不可修改参数之间的差异](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="03e95-153"> [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span></span>  
<span data-ttu-id="03e95-154"> [通过值和通过引用传递参数之间的差异](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="03e95-154"> [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="03e95-155"> [如何︰ 防止过程参数的值更改](./how-to-protect-a-procedure-argument-against-value-changes.md) </span><span class="sxs-lookup"><span data-stu-id="03e95-155"> [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md) </span></span>  
<span data-ttu-id="03e95-156"> [如何︰ 强制通过值传递参数](./how-to-force-an-argument-to-be-passed-by-value.md) </span><span class="sxs-lookup"><span data-stu-id="03e95-156"> [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md) </span></span>  
<span data-ttu-id="03e95-157"> [按位置和按名称传递参数](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="03e95-157"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="03e95-158"> [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="03e95-158"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
