---
title: 如何：更改过程自变量 (Visual Basic 中) 的值
ms.date: 07/20/2015
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
ms.openlocfilehash: a56bdf888163c9559b87e857abb33522c547ed45
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316617"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="2b35b-102">如何：更改过程自变量 (Visual Basic 中) 的值</span><span class="sxs-lookup"><span data-stu-id="2b35b-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="2b35b-103">在调用过程时，您提供每个自变量对应于一个过程中定义的参数。</span><span class="sxs-lookup"><span data-stu-id="2b35b-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="2b35b-104">在某些情况下，过程代码可以更改基础调用代码中的自变量的值。</span><span class="sxs-lookup"><span data-stu-id="2b35b-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="2b35b-105">在其他情况下，该过程可以更改仅其自变量的本地副本。</span><span class="sxs-lookup"><span data-stu-id="2b35b-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="2b35b-106">Visual Basic 时调用该过程，创建本地副本的每个参数传递[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)。</span><span class="sxs-lookup"><span data-stu-id="2b35b-106">When you call the procedure, Visual Basic makes a local copy of every argument that is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="2b35b-107">对于每个自变量传递[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，Visual Basic 使过程代码中调用代码参数的基础的编程元素直接引用。</span><span class="sxs-lookup"><span data-stu-id="2b35b-107">For each argument passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="2b35b-108">如果调用代码中的基础元素是一个可修改的元素，将参数传递`ByRef`，过程代码可用于直接引用更改调用代码中的元素的值。</span><span class="sxs-lookup"><span data-stu-id="2b35b-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="2b35b-109">更改基础值</span><span class="sxs-lookup"><span data-stu-id="2b35b-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="2b35b-110">若要更改过程自变量调用的代码中的基础值</span><span class="sxs-lookup"><span data-stu-id="2b35b-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1. <span data-ttu-id="2b35b-111">在过程声明中，指定[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)对应于参数的参数。</span><span class="sxs-lookup"><span data-stu-id="2b35b-111">In the procedure declaration, specify [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2. <span data-ttu-id="2b35b-112">在调用代码中，将作为参数传递的可修改的编程元素。</span><span class="sxs-lookup"><span data-stu-id="2b35b-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3. <span data-ttu-id="2b35b-113">在调用代码中，不能将放在括号中的参数列表中的参数。</span><span class="sxs-lookup"><span data-stu-id="2b35b-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4. <span data-ttu-id="2b35b-114">在过程代码中，使用参数名称将值分配给调用代码中的基础元素。</span><span class="sxs-lookup"><span data-stu-id="2b35b-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="2b35b-115">请参阅示例进一步演示。</span><span class="sxs-lookup"><span data-stu-id="2b35b-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="2b35b-116">更改本地副本</span><span class="sxs-lookup"><span data-stu-id="2b35b-116">Changing Local Copies</span></span>  
 <span data-ttu-id="2b35b-117">如果调用代码中的基础元素是不可修改的元素，或将参数传递`ByVal`，该过程不能更改调用代码中的其值。</span><span class="sxs-lookup"><span data-stu-id="2b35b-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="2b35b-118">但是，该过程可以更改其这类参数的本地副本。</span><span class="sxs-lookup"><span data-stu-id="2b35b-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="2b35b-119">若要更改过程自变量的过程代码中的副本</span><span class="sxs-lookup"><span data-stu-id="2b35b-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1. <span data-ttu-id="2b35b-120">在过程声明中，指定[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)对应于参数的参数。</span><span class="sxs-lookup"><span data-stu-id="2b35b-120">In the procedure declaration, specify [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="2b35b-121">或</span><span class="sxs-lookup"><span data-stu-id="2b35b-121">-or-</span></span>  
  
     <span data-ttu-id="2b35b-122">在调用代码中，将括在括号中的参数列表中的参数。</span><span class="sxs-lookup"><span data-stu-id="2b35b-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="2b35b-123">这会强制 Visual Basic，将按值传递自变量，即使相应的参数指定`ByRef`。</span><span class="sxs-lookup"><span data-stu-id="2b35b-123">This forces Visual Basic to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2. <span data-ttu-id="2b35b-124">在过程代码中，使用参数名称的参数的本地副本分配一个值。</span><span class="sxs-lookup"><span data-stu-id="2b35b-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="2b35b-125">调用代码中的基础值不会更改。</span><span class="sxs-lookup"><span data-stu-id="2b35b-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b35b-126">示例</span><span class="sxs-lookup"><span data-stu-id="2b35b-126">Example</span></span>  
 <span data-ttu-id="2b35b-127">下面的示例演示两个过程采用一个数组变量并运行它的元素。</span><span class="sxs-lookup"><span data-stu-id="2b35b-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="2b35b-128">`increase`过程只需添加一个到每个元素。</span><span class="sxs-lookup"><span data-stu-id="2b35b-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="2b35b-129">`replace`过程将一个新数组分配给该参数`a()`，然后添加一个到每个元素。</span><span class="sxs-lookup"><span data-stu-id="2b35b-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 <span data-ttu-id="2b35b-130">第一个`MsgBox`调用显示"increase(n) 后：11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="2b35b-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="2b35b-131">因为数组`n`是引用类型，`replace`可以更改其中一个成员，即使传递机制是`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="2b35b-131">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="2b35b-132">第二个`MsgBox`调用显示"replace(n) 后：101, 201, 301".</span><span class="sxs-lookup"><span data-stu-id="2b35b-132">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="2b35b-133">因为`n`传递`ByRef`，`replace`可以修改变量`n`调用代码和分配给它一个新数组中。</span><span class="sxs-lookup"><span data-stu-id="2b35b-133">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="2b35b-134">因为`n`是引用类型，`replace`还可以更改其成员。</span><span class="sxs-lookup"><span data-stu-id="2b35b-134">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="2b35b-135">可以修改变量本身调用代码中的阻止该过程。</span><span class="sxs-lookup"><span data-stu-id="2b35b-135">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="2b35b-136">请参阅[如何：防止过程自变量的值更改](./how-to-protect-a-procedure-argument-against-value-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="2b35b-136">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2b35b-137">编译代码</span><span class="sxs-lookup"><span data-stu-id="2b35b-137">Compiling the Code</span></span>  
 <span data-ttu-id="2b35b-138">当通过引用传递变量时，必须使用`ByRef`关键字来指定此机制。</span><span class="sxs-lookup"><span data-stu-id="2b35b-138">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="2b35b-139">Visual Basic 中的默认值是按值传递参数。</span><span class="sxs-lookup"><span data-stu-id="2b35b-139">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="2b35b-140">但是，它是一个良好的编程做法包括[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字与每个声明的参数。</span><span class="sxs-lookup"><span data-stu-id="2b35b-140">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="2b35b-141">这使您的代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="2b35b-141">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="2b35b-142">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="2b35b-142">.NET Framework Security</span></span>  
 <span data-ttu-id="2b35b-143">允许更改基础调用代码中的自变量的值的过程中始终没有带来潜在的风险。</span><span class="sxs-lookup"><span data-stu-id="2b35b-143">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="2b35b-144">请确保您希望此值可更改，并且准备好使用它之前检查其有效性。</span><span class="sxs-lookup"><span data-stu-id="2b35b-144">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b35b-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b35b-145">See also</span></span>

- [<span data-ttu-id="2b35b-146">过程</span><span class="sxs-lookup"><span data-stu-id="2b35b-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="2b35b-147">过程形参和实参</span><span class="sxs-lookup"><span data-stu-id="2b35b-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="2b35b-148">如何：将参数传递给过程</span><span class="sxs-lookup"><span data-stu-id="2b35b-148">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="2b35b-149">按值和按引用传递参数</span><span class="sxs-lookup"><span data-stu-id="2b35b-149">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="2b35b-150">可修改和不可修改参数之间的差异</span><span class="sxs-lookup"><span data-stu-id="2b35b-150">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="2b35b-151">通过值传递参数和通过引用传递参数之间的差异</span><span class="sxs-lookup"><span data-stu-id="2b35b-151">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="2b35b-152">如何：防止过程参数的值被更改</span><span class="sxs-lookup"><span data-stu-id="2b35b-152">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="2b35b-153">如何：强制通过值传递参数</span><span class="sxs-lookup"><span data-stu-id="2b35b-153">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="2b35b-154">按位置和按名称传递参数</span><span class="sxs-lookup"><span data-stu-id="2b35b-154">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="2b35b-155">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="2b35b-155">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
