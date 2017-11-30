---
title: "通过值和通过引用传递自变量 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- passing arguments [Visual Basic], by value or by reference
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing [Visual Basic], by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 752c0c8e90cafe457cbd5d684bc984a1ea4632ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="c54dd-102">通过值和通过引用传递自变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c54dd-102">Passing Arguments by Value and by Reference (Visual Basic)</span></span>
<span data-ttu-id="c54dd-103">在[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]，可以将自变量传递给过程*按值*或*通过引用*。</span><span class="sxs-lookup"><span data-stu-id="c54dd-103">In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], you can pass an argument to a procedure *by value* or *by reference*.</span></span> <span data-ttu-id="c54dd-104">这称为*传递机制*，同时确定过程是否可以修改调用代码中的以该参数基础的编程元素。</span><span class="sxs-lookup"><span data-stu-id="c54dd-104">This is known as the *passing mechanism*, and it determines whether the procedure can modify the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="c54dd-105">过程声明确定每个参数的传递机制，通过指定[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="c54dd-105">The procedure declaration determines the passing mechanism for each parameter by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword.</span></span>  
  
## <a name="distinctions"></a><span data-ttu-id="c54dd-106">区别</span><span class="sxs-lookup"><span data-stu-id="c54dd-106">Distinctions</span></span>  
 <span data-ttu-id="c54dd-107">如果将参数传递给过程中，应注意的彼此交互的几点差异：</span><span class="sxs-lookup"><span data-stu-id="c54dd-107">When passing an argument to a procedure, be aware of several different distinctions that interact with each other:</span></span>  
  
-   <span data-ttu-id="c54dd-108">基础的编程元素是可修改或不可修改</span><span class="sxs-lookup"><span data-stu-id="c54dd-108">Whether the underlying programming element is modifiable or nonmodifiable</span></span>  
  
-   <span data-ttu-id="c54dd-109">自变量本身是可修改或不可修改</span><span class="sxs-lookup"><span data-stu-id="c54dd-109">Whether the argument itself is modifiable or nonmodifiable</span></span>  
  
-   <span data-ttu-id="c54dd-110">自变量通过值还是引用传递</span><span class="sxs-lookup"><span data-stu-id="c54dd-110">Whether the argument is being passed by value or by reference</span></span>  
  
-   <span data-ttu-id="c54dd-111">参数数据类型是否是值类型或引用类型</span><span class="sxs-lookup"><span data-stu-id="c54dd-111">Whether the argument data type is a value type or a reference type</span></span>  
  
 <span data-ttu-id="c54dd-112">有关详细信息，请参阅[差异之间可修改和不可修改自变量](./differences-between-modifiable-and-nonmodifiable-arguments.md)和[差异之间传递自变量传递的值和按引用](./differences-between-passing-an-argument-by-value-and-by-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="c54dd-112">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) and [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="choice-of-passing-mechanism"></a><span data-ttu-id="c54dd-113">选择的传递机制</span><span class="sxs-lookup"><span data-stu-id="c54dd-113">Choice of Passing Mechanism</span></span>  
 <span data-ttu-id="c54dd-114">你应该选择仔细为每个参数的传递机制。</span><span class="sxs-lookup"><span data-stu-id="c54dd-114">You should choose the passing mechanism carefully for each argument.</span></span>  
  
-   <span data-ttu-id="c54dd-115">**保护**。</span><span class="sxs-lookup"><span data-stu-id="c54dd-115">**Protection**.</span></span> <span data-ttu-id="c54dd-116">在两个传递机制之间进行选择，最重要的标准是要更改的调用变量公开。</span><span class="sxs-lookup"><span data-stu-id="c54dd-116">In choosing between the two passing mechanisms, the most important criterion is the exposure of calling variables to change.</span></span> <span data-ttu-id="c54dd-117">传递自变量的优点`ByRef`是过程可以返回到调用代码通过该自变量的值。</span><span class="sxs-lookup"><span data-stu-id="c54dd-117">The advantage of passing an argument `ByRef` is that the procedure can return a value to the calling code through that argument.</span></span> <span data-ttu-id="c54dd-118">传递自变量的优点`ByVal`是它可防止变量被过程正在更改。</span><span class="sxs-lookup"><span data-stu-id="c54dd-118">The advantage of passing an argument `ByVal` is that it protects a variable from being changed by the procedure.</span></span>  
  
-   <span data-ttu-id="c54dd-119">**性能**。</span><span class="sxs-lookup"><span data-stu-id="c54dd-119">**Performance**.</span></span> <span data-ttu-id="c54dd-120">尽管的传递机制可能会影响代码的性能，区别在于通常无意义。</span><span class="sxs-lookup"><span data-stu-id="c54dd-120">Although the passing mechanism can affect the performance of your code, the difference is usually insignificant.</span></span> <span data-ttu-id="c54dd-121">一个例外是值类型传递`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="c54dd-121">One exception to this is a value type passed `ByVal`.</span></span> <span data-ttu-id="c54dd-122">在这种情况下，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]复制自变量的整个数据内容。</span><span class="sxs-lookup"><span data-stu-id="c54dd-122">In this case, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] copies the entire data contents of the argument.</span></span> <span data-ttu-id="c54dd-123">因此，较大的值类型，如一个结构，它可以更高效，以将其传递`ByRef`。</span><span class="sxs-lookup"><span data-stu-id="c54dd-123">Therefore, for a large value type such as a structure, it can be more efficient to pass it `ByRef`.</span></span>  
  
     <span data-ttu-id="c54dd-124">对于引用类型，仅指向的数据为复制 （四个字节在 32 位平台上，在 64 位平台上的 8 个字节）。</span><span class="sxs-lookup"><span data-stu-id="c54dd-124">For reference types, only the pointer to the data is copied (four bytes on 32-bit platforms, eight bytes on 64-bit platforms).</span></span> <span data-ttu-id="c54dd-125">因此，你可以将类型自变量传递`String`或`Object`的值，从而不会降低性能。</span><span class="sxs-lookup"><span data-stu-id="c54dd-125">Therefore, you can pass arguments of type `String` or `Object` by value without harming performance.</span></span>  
  
## <a name="determination-of-the-passing-mechanism"></a><span data-ttu-id="c54dd-126">确定的传递机制</span><span class="sxs-lookup"><span data-stu-id="c54dd-126">Determination of the Passing Mechanism</span></span>  
 <span data-ttu-id="c54dd-127">过程声明指定每个参数的传递机制。</span><span class="sxs-lookup"><span data-stu-id="c54dd-127">The procedure declaration specifies the passing mechanism for each parameter.</span></span> <span data-ttu-id="c54dd-128">调用的代码不能重写`ByVal`机制。</span><span class="sxs-lookup"><span data-stu-id="c54dd-128">The calling code can't override a `ByVal` mechanism.</span></span>  
  
 <span data-ttu-id="c54dd-129">如果参数用声明`ByRef`，调用代码可以强制机制来`ByVal`通过将在调用中的括号中的自变量名称。</span><span class="sxs-lookup"><span data-stu-id="c54dd-129">If a parameter is declared with `ByRef`, the calling code can force the mechanism to `ByVal` by enclosing the argument name in parentheses in the call.</span></span> <span data-ttu-id="c54dd-130">有关详细信息，请参阅[如何： 强制通过值传递到自变量](./how-to-force-an-argument-to-be-passed-by-value.md)。</span><span class="sxs-lookup"><span data-stu-id="c54dd-130">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
 <span data-ttu-id="c54dd-131">中的默认值[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]是按值传递自变量。</span><span class="sxs-lookup"><span data-stu-id="c54dd-131">The default in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] is to pass arguments by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-value"></a><span data-ttu-id="c54dd-132">何时通过值传递自变量</span><span class="sxs-lookup"><span data-stu-id="c54dd-132">When to Pass an Argument by Value</span></span>  
  
-   <span data-ttu-id="c54dd-133">如果基础自变量调用的代码元素是不可修改的元素，声明对应的形参[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)。</span><span class="sxs-lookup"><span data-stu-id="c54dd-133">If the calling code element underlying the argument is a nonmodifiable element, declare the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="c54dd-134">没有代码可以更改不可修改的元素的值。</span><span class="sxs-lookup"><span data-stu-id="c54dd-134">No code can change the value of a nonmodifiable element.</span></span>  
  
-   <span data-ttu-id="c54dd-135">如果基础元素是可修改，但不是希望能够更改其值的过程，将参数声明`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="c54dd-135">If the underlying element is modifiable, but you do not want the procedure to be able to change its value, declare the parameter `ByVal`.</span></span> <span data-ttu-id="c54dd-136">仅调用代码可以更改可修改元素的值传递的值。</span><span class="sxs-lookup"><span data-stu-id="c54dd-136">Only the calling code can change the value of a modifiable element passed by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-reference"></a><span data-ttu-id="c54dd-137">何时通过引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="c54dd-137">When to Pass an Argument by Reference</span></span>  
  
-   <span data-ttu-id="c54dd-138">如果过程有正版需要更改中调用代码的基础元素，声明对应的形参[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)。</span><span class="sxs-lookup"><span data-stu-id="c54dd-138">If the procedure has a genuine need to change the underlying element in the calling code, declare the corresponding parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span>  
  
-   <span data-ttu-id="c54dd-139">如果代码正确执行依赖于更改中调用代码的基础元素的过程，将参数声明`ByRef`。</span><span class="sxs-lookup"><span data-stu-id="c54dd-139">If the correct execution of the code depends on the procedure changing the underlying element in the calling code, declare the parameter `ByRef`.</span></span> <span data-ttu-id="c54dd-140">如果将其传递的值，或者调用代码重写`ByRef`传递机制，通过将实参括在括号内，过程调用可能会产生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="c54dd-140">If you pass it by value, or if the calling code overrides the `ByRef` passing mechanism by enclosing the argument in parentheses, the procedure call might produce unexpected results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c54dd-141">示例</span><span class="sxs-lookup"><span data-stu-id="c54dd-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c54dd-142">描述</span><span class="sxs-lookup"><span data-stu-id="c54dd-142">Description</span></span>  
 <span data-ttu-id="c54dd-143">下面的示例演示了何时通过值传递自变量以及何时将它们通过引用传递。</span><span class="sxs-lookup"><span data-stu-id="c54dd-143">The following example illustrates when to pass arguments by value and when to pass them by reference.</span></span> <span data-ttu-id="c54dd-144">过程`Calculate`同时具有`ByVal`和`ByRef`参数。</span><span class="sxs-lookup"><span data-stu-id="c54dd-144">Procedure `Calculate` has both a `ByVal` and a `ByRef` parameter.</span></span> <span data-ttu-id="c54dd-145">给定利率， `rate`，和的金额，总和`debt`，该过程的任务是计算为的新值`debt`，它是对应用的结果利率的原始值`debt`。</span><span class="sxs-lookup"><span data-stu-id="c54dd-145">Given an interest rate, `rate`, and a sum of money, `debt`, the task of the procedure is to calculate a new value for `debt` that is the result of applying the interest rate to the original value of `debt`.</span></span> <span data-ttu-id="c54dd-146">因为`debt`是`ByRef`参数，对应于调用代码中的自变量的值中反映新的总计`debt`。</span><span class="sxs-lookup"><span data-stu-id="c54dd-146">Because `debt` is a `ByRef` parameter, the new total is reflected in the value of the argument in the calling code that corresponds to `debt`.</span></span> <span data-ttu-id="c54dd-147">参数`rate`是`ByVal`参数因为`Calculate`不应更改其值。</span><span class="sxs-lookup"><span data-stu-id="c54dd-147">Parameter `rate` is a `ByVal` parameter because `Calculate` should not change its value.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c54dd-148">代码</span><span class="sxs-lookup"><span data-stu-id="c54dd-148">Code</span></span>  
 [!code-vb[VbVbcnProcedures#74](./codesnippet/VisualBasic/passing-arguments-by-value-and-by-reference_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c54dd-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c54dd-149">See Also</span></span>  
 [<span data-ttu-id="c54dd-150">过程</span><span class="sxs-lookup"><span data-stu-id="c54dd-150">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="c54dd-151">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="c54dd-151">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="c54dd-152">如何：将自变量传递给过程</span><span class="sxs-lookup"><span data-stu-id="c54dd-152">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="c54dd-153">如何：更改过程自变量的值</span><span class="sxs-lookup"><span data-stu-id="c54dd-153">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)  
 [<span data-ttu-id="c54dd-154">如何：防止过程自变量的值被更改</span><span class="sxs-lookup"><span data-stu-id="c54dd-154">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [<span data-ttu-id="c54dd-155">如何：强制通过值传递自变量</span><span class="sxs-lookup"><span data-stu-id="c54dd-155">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [<span data-ttu-id="c54dd-156">按位置和按名称传递自变量</span><span class="sxs-lookup"><span data-stu-id="c54dd-156">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="c54dd-157">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="c54dd-157">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
