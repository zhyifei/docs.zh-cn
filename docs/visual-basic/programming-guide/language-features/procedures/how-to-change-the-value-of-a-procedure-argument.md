---
title: "如何：更改过程自变量的值 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ba23c8f0b4b0b6e751546019af902a6305b9ef53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="9633a-102">如何：更改过程自变量的值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9633a-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="9633a-103">当调用过程时，你提供每个自变量对应于在过程中定义的参数之一。</span><span class="sxs-lookup"><span data-stu-id="9633a-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="9633a-104">在某些情况下，该过程代码可以更改基础中调用代码的自变量的值。</span><span class="sxs-lookup"><span data-stu-id="9633a-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="9633a-105">在其他情况下，该过程只可以更改其本地副本的自变量。</span><span class="sxs-lookup"><span data-stu-id="9633a-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="9633a-106">在调用过程中，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]使每个自变量传递的本地副本[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)。</span><span class="sxs-lookup"><span data-stu-id="9633a-106">When you call the procedure, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] makes a local copy of every argument that is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="9633a-107">对于每个自变量传递[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]使该过程代码中调用代码的实参的编程元素直接引用。</span><span class="sxs-lookup"><span data-stu-id="9633a-107">For each argument passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="9633a-108">如果调用代码中的基础元素是可修改的元素，并传递自变量`ByRef`，过程代码可以使用的直接引用来更改调用代码中的元素的值。</span><span class="sxs-lookup"><span data-stu-id="9633a-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="9633a-109">更改基础值</span><span class="sxs-lookup"><span data-stu-id="9633a-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="9633a-110">若要更改过程自变量调用的代码中的基础值</span><span class="sxs-lookup"><span data-stu-id="9633a-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1.  <span data-ttu-id="9633a-111">在过程声明中，指定[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)对应于参数的参数。</span><span class="sxs-lookup"><span data-stu-id="9633a-111">In the procedure declaration, specify [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2.  <span data-ttu-id="9633a-112">在调用代码中，将作为参数传递的可修改的编程元素。</span><span class="sxs-lookup"><span data-stu-id="9633a-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3.  <span data-ttu-id="9633a-113">在调用代码中，不要将括在参数列表中的括号中的自变量。</span><span class="sxs-lookup"><span data-stu-id="9633a-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4.  <span data-ttu-id="9633a-114">在过程代码中，使用参数名称分配给调用代码中的基础元素的值。</span><span class="sxs-lookup"><span data-stu-id="9633a-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="9633a-115">请参阅示例进一步向下的演示。</span><span class="sxs-lookup"><span data-stu-id="9633a-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="9633a-116">更改本地副本</span><span class="sxs-lookup"><span data-stu-id="9633a-116">Changing Local Copies</span></span>  
 <span data-ttu-id="9633a-117">如果调用代码中的基础元素是不可修改的元素，或者如果传递参数`ByVal`，过程将无法更改其调用的代码中的值。</span><span class="sxs-lookup"><span data-stu-id="9633a-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="9633a-118">但是，该过程可以更改其本地副本的这类参数。</span><span class="sxs-lookup"><span data-stu-id="9633a-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="9633a-119">若要更改在过程代码中的过程自变量的副本</span><span class="sxs-lookup"><span data-stu-id="9633a-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1.  <span data-ttu-id="9633a-120">在过程声明中，指定[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)对应于参数的参数。</span><span class="sxs-lookup"><span data-stu-id="9633a-120">In the procedure declaration, specify [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="9633a-121">- 或 -</span><span class="sxs-lookup"><span data-stu-id="9633a-121">-or-</span></span>  
  
     <span data-ttu-id="9633a-122">在调用代码中，将括在参数列表中的括号中的自变量。</span><span class="sxs-lookup"><span data-stu-id="9633a-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="9633a-123">这将强制[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]以按值传递自变量，即使相应的参数指定`ByRef`。</span><span class="sxs-lookup"><span data-stu-id="9633a-123">This forces [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2.  <span data-ttu-id="9633a-124">在过程代码中，使用参数名称的自变量的本地副本分配一个值。</span><span class="sxs-lookup"><span data-stu-id="9633a-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="9633a-125">调用代码中的基础值不会更改。</span><span class="sxs-lookup"><span data-stu-id="9633a-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9633a-126">示例</span><span class="sxs-lookup"><span data-stu-id="9633a-126">Example</span></span>  
 <span data-ttu-id="9633a-127">下面的示例演示对其元素的两个过程可采用一个数组变量并运行。</span><span class="sxs-lookup"><span data-stu-id="9633a-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="9633a-128">`increase`过程只需添加一个对每个元素。</span><span class="sxs-lookup"><span data-stu-id="9633a-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="9633a-129">`replace`过程将一个新数组分配给参数`a()`，然后添加一个用于每个元素。</span><span class="sxs-lookup"><span data-stu-id="9633a-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#36](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]  
  
 <span data-ttu-id="9633a-130">第一个`MsgBox`调用显示"后 increase(n): 11、 21、 31、 41"。</span><span class="sxs-lookup"><span data-stu-id="9633a-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="9633a-131">因为数组`n`是引用类型，`replace`可以更改的成员，即使的传递机制`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="9633a-131">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="9633a-132">第二个`MsgBox`调用显示"后 replace(n): 101、 201、 301"。</span><span class="sxs-lookup"><span data-stu-id="9633a-132">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="9633a-133">因为`n`传递`ByRef`，`replace`可以修改变量`n`中调用代码并将赋给它的新数组。</span><span class="sxs-lookup"><span data-stu-id="9633a-133">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="9633a-134">因为`n`是引用类型，`replace`还可以更改其成员。</span><span class="sxs-lookup"><span data-stu-id="9633a-134">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="9633a-135">你可以修改调用代码中的变量本身阻止过程。</span><span class="sxs-lookup"><span data-stu-id="9633a-135">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="9633a-136">请参阅[如何： 防止过程自变量的值更改](./how-to-protect-a-procedure-argument-against-value-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="9633a-136">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9633a-137">编译代码</span><span class="sxs-lookup"><span data-stu-id="9633a-137">Compiling the Code</span></span>  
 <span data-ttu-id="9633a-138">当通过引用传递的变量时，你必须使用`ByRef`关键字来指定此机制。</span><span class="sxs-lookup"><span data-stu-id="9633a-138">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="9633a-139">中的默认值[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]是按值传递自变量。</span><span class="sxs-lookup"><span data-stu-id="9633a-139">The default in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="9633a-140">但是，很好的编程做法包括[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字后跟每个声明的参数。</span><span class="sxs-lookup"><span data-stu-id="9633a-140">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="9633a-141">这使得你的代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="9633a-141">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="9633a-142">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="9633a-142">.NET Framework Security</span></span>  
 <span data-ttu-id="9633a-143">允许一个过程来更改基础中调用代码的自变量的值始终没有潜在风险。</span><span class="sxs-lookup"><span data-stu-id="9633a-143">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="9633a-144">请确保您希望此值可更改，并做好准备，然后再使用它的有效性检查它。</span><span class="sxs-lookup"><span data-stu-id="9633a-144">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9633a-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9633a-145">See Also</span></span>  
 [<span data-ttu-id="9633a-146">过程</span><span class="sxs-lookup"><span data-stu-id="9633a-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="9633a-147">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="9633a-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="9633a-148">如何：将自变量传递给过程</span><span class="sxs-lookup"><span data-stu-id="9633a-148">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="9633a-149">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="9633a-149">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="9633a-150">可修改和不可修改自变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="9633a-150">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="9633a-151">通过值传递自变量和通过引用传递自变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="9633a-151">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="9633a-152">如何：防止过程自变量的值被更改</span><span class="sxs-lookup"><span data-stu-id="9633a-152">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [<span data-ttu-id="9633a-153">如何：强制通过值传递自变量</span><span class="sxs-lookup"><span data-stu-id="9633a-153">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [<span data-ttu-id="9633a-154">按位置和按名称传递自变量</span><span class="sxs-lookup"><span data-stu-id="9633a-154">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="9633a-155">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="9633a-155">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
