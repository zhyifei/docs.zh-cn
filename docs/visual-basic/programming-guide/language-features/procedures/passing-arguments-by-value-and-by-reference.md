---
title: "传递参数通过值和通过引用 (Visual Basic 中) |Microsoft 文档"
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
- ByRef keyword, passing arguments by reference
- Visual Basic code, procedures
- passing arguments, by value or by reference
- ByVal keyword, passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing, by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
caps.latest.revision: 23
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
ms.openlocfilehash: 44107171d6f24e22614788470c65cf7ad8d28640
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="9d75c-102">通过值和通过引用传递自变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d75c-102">Passing Arguments by Value and by Reference (Visual Basic)</span></span>
<span data-ttu-id="9d75c-103">在[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]，可以将参数传递给过程*按值*或*通过引用*。</span><span class="sxs-lookup"><span data-stu-id="9d75c-103">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], you can pass an argument to a procedure *by value* or *by reference*.</span></span> <span data-ttu-id="9d75c-104">这称为*传递机制*，并确定该过程是否可以修改调用代码中的实参的编程元素。</span><span class="sxs-lookup"><span data-stu-id="9d75c-104">This is known as the *passing mechanism*, and it determines whether the procedure can modify the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="9d75c-105">过程声明确定每个参数的传递机制，通过指定[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="9d75c-105">The procedure declaration determines the passing mechanism for each parameter by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword.</span></span>  
  
## <a name="distinctions"></a><span data-ttu-id="9d75c-106">区别</span><span class="sxs-lookup"><span data-stu-id="9d75c-106">Distinctions</span></span>  
 <span data-ttu-id="9d75c-107">如果将参数传递给过程，应注意的几点彼此交互的差异︰</span><span class="sxs-lookup"><span data-stu-id="9d75c-107">When passing an argument to a procedure, be aware of several different distinctions that interact with each other:</span></span>  
  
-   <span data-ttu-id="9d75c-108">基础的编程元素是可修改还是不可更改</span><span class="sxs-lookup"><span data-stu-id="9d75c-108">Whether the underlying programming element is modifiable or nonmodifiable</span></span>  
  
-   <span data-ttu-id="9d75c-109">参数本身是可修改或不可更改</span><span class="sxs-lookup"><span data-stu-id="9d75c-109">Whether the argument itself is modifiable or nonmodifiable</span></span>  
  
-   <span data-ttu-id="9d75c-110">参数按值或按引用传递</span><span class="sxs-lookup"><span data-stu-id="9d75c-110">Whether the argument is being passed by value or by reference</span></span>  
  
-   <span data-ttu-id="9d75c-111">参数数据类型是否是值类型或引用类型</span><span class="sxs-lookup"><span data-stu-id="9d75c-111">Whether the argument data type is a value type or a reference type</span></span>  
  
 <span data-ttu-id="9d75c-112">有关详细信息，请参阅[差异之间可修改和不可修改参数](./differences-between-modifiable-and-nonmodifiable-arguments.md)和[差异之间传递的参数值和通过引用来](./differences-between-passing-an-argument-by-value-and-by-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="9d75c-112">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) and [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="choice-of-passing-mechanism"></a><span data-ttu-id="9d75c-113">选择传递机制</span><span class="sxs-lookup"><span data-stu-id="9d75c-113">Choice of Passing Mechanism</span></span>  
 <span data-ttu-id="9d75c-114">您应选择小心地为每个参数传递机制。</span><span class="sxs-lookup"><span data-stu-id="9d75c-114">You should choose the passing mechanism carefully for each argument.</span></span>  
  
-   <span data-ttu-id="9d75c-115">**保护**。</span><span class="sxs-lookup"><span data-stu-id="9d75c-115">**Protection**.</span></span> <span data-ttu-id="9d75c-116">在两个传递机制之间进行选择，最重要的条件是公开的调用要更改的变量。</span><span class="sxs-lookup"><span data-stu-id="9d75c-116">In choosing between the two passing mechanisms, the most important criterion is the exposure of calling variables to change.</span></span> <span data-ttu-id="9d75c-117">传递参数的优点`ByRef`是该过程可以返回给调用代码通过该参数的值。</span><span class="sxs-lookup"><span data-stu-id="9d75c-117">The advantage of passing an argument `ByRef` is that the procedure can return a value to the calling code through that argument.</span></span> <span data-ttu-id="9d75c-118">传递参数的优点`ByVal`是它可防止一个变量的过程更改。</span><span class="sxs-lookup"><span data-stu-id="9d75c-118">The advantage of passing an argument `ByVal` is that it protects a variable from being changed by the procedure.</span></span>  
  
-   <span data-ttu-id="9d75c-119">**性能**。</span><span class="sxs-lookup"><span data-stu-id="9d75c-119">**Performance**.</span></span> <span data-ttu-id="9d75c-120">尽管传递机制可能会影响您的性能，不同之处是代码的通常并不显著。</span><span class="sxs-lookup"><span data-stu-id="9d75c-120">Although the passing mechanism can affect the performance of your code, the difference is usually insignificant.</span></span> <span data-ttu-id="9d75c-121">一个例外是值类型传递`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="9d75c-121">One exception to this is a value type passed `ByVal`.</span></span> <span data-ttu-id="9d75c-122">在这种情况下，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]复制参数的整个数据内容。</span><span class="sxs-lookup"><span data-stu-id="9d75c-122">In this case, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] copies the entire data contents of the argument.</span></span> <span data-ttu-id="9d75c-123">因此，较大的值类型，如一个结构，它可以更高效，以将其传递`ByRef`。</span><span class="sxs-lookup"><span data-stu-id="9d75c-123">Therefore, for a large value type such as a structure, it can be more efficient to pass it `ByRef`.</span></span>  
  
     <span data-ttu-id="9d75c-124">对于引用类型，只对数据的指针是复制 （4 个字节在 32 位平台上，在 64 位平台上的 8 个字节）。</span><span class="sxs-lookup"><span data-stu-id="9d75c-124">For reference types, only the pointer to the data is copied (four bytes on 32-bit platforms, eight bytes on 64-bit platforms).</span></span> <span data-ttu-id="9d75c-125">因此，可以将类型的参数传递`String`或`Object`的值，而不损害性能的前提下。</span><span class="sxs-lookup"><span data-stu-id="9d75c-125">Therefore, you can pass arguments of type `String` or `Object` by value without harming performance.</span></span>  
  
## <a name="determination-of-the-passing-mechanism"></a><span data-ttu-id="9d75c-126">确定的传递机制</span><span class="sxs-lookup"><span data-stu-id="9d75c-126">Determination of the Passing Mechanism</span></span>  
 <span data-ttu-id="9d75c-127">过程声明中指定的每个参数的传递机制。</span><span class="sxs-lookup"><span data-stu-id="9d75c-127">The procedure declaration specifies the passing mechanism for each parameter.</span></span> <span data-ttu-id="9d75c-128">调用代码不能重写`ByVal`机制。</span><span class="sxs-lookup"><span data-stu-id="9d75c-128">The calling code can't override a `ByVal` mechanism.</span></span>  
  
 <span data-ttu-id="9d75c-129">如果参数用声明`ByRef`，调用代码可以强制机制来`ByVal`通过括在圆括号来调用的参数名称。</span><span class="sxs-lookup"><span data-stu-id="9d75c-129">If a parameter is declared with `ByRef`, the calling code can force the mechanism to `ByVal` by enclosing the argument name in parentheses in the call.</span></span> <span data-ttu-id="9d75c-130">有关详细信息，请参阅[如何︰ 强制通过值传递到参数](./how-to-force-an-argument-to-be-passed-by-value.md)。</span><span class="sxs-lookup"><span data-stu-id="9d75c-130">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
 <span data-ttu-id="9d75c-131">中的默认设置[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]是按值传递参数。</span><span class="sxs-lookup"><span data-stu-id="9d75c-131">The default in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is to pass arguments by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-value"></a><span data-ttu-id="9d75c-132">何时通过值传递参数</span><span class="sxs-lookup"><span data-stu-id="9d75c-132">When to Pass an Argument by Value</span></span>  
  
-   <span data-ttu-id="9d75c-133">如果调用参数的基础的代码元素是不可修改的元素，声明对应的形参[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)。</span><span class="sxs-lookup"><span data-stu-id="9d75c-133">If the calling code element underlying the argument is a nonmodifiable element, declare the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="9d75c-134">无代码可以更改不可更改元素的值。</span><span class="sxs-lookup"><span data-stu-id="9d75c-134">No code can change the value of a nonmodifiable element.</span></span>  
  
-   <span data-ttu-id="9d75c-135">如果基础元素是可修改的但不是希望将无法更改其值的过程，将参数声明`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="9d75c-135">If the underlying element is modifiable, but you do not want the procedure to be able to change its value, declare the parameter `ByVal`.</span></span> <span data-ttu-id="9d75c-136">只有调用代码可以更改通过值传递的可修改元素的值。</span><span class="sxs-lookup"><span data-stu-id="9d75c-136">Only the calling code can change the value of a modifiable element passed by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-reference"></a><span data-ttu-id="9d75c-137">当通过引用传递参数</span><span class="sxs-lookup"><span data-stu-id="9d75c-137">When to Pass an Argument by Reference</span></span>  
  
-   <span data-ttu-id="9d75c-138">如果该过程具有确实需要更改的基础元素调用的代码中，声明对应的形参[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)。</span><span class="sxs-lookup"><span data-stu-id="9d75c-138">If the procedure has a genuine need to change the underlying element in the calling code, declare the corresponding parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span>  
  
-   <span data-ttu-id="9d75c-139">如果代码正确执行依赖于更改中调用代码的基础元素的过程，将参数声明`ByRef`。</span><span class="sxs-lookup"><span data-stu-id="9d75c-139">If the correct execution of the code depends on the procedure changing the underlying element in the calling code, declare the parameter `ByRef`.</span></span> <span data-ttu-id="9d75c-140">如果将其传递的数值，或者调用代码重写`ByRef`传递机制，通过将实参括在括号内，则过程调用可能会产生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="9d75c-140">If you pass it by value, or if the calling code overrides the `ByRef` passing mechanism by enclosing the argument in parentheses, the procedure call might produce unexpected results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d75c-141">示例</span><span class="sxs-lookup"><span data-stu-id="9d75c-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9d75c-142">描述</span><span class="sxs-lookup"><span data-stu-id="9d75c-142">Description</span></span>  
 <span data-ttu-id="9d75c-143">以下示例说明何时通过值传递参数以及何时通过引用传递。</span><span class="sxs-lookup"><span data-stu-id="9d75c-143">The following example illustrates when to pass arguments by value and when to pass them by reference.</span></span> <span data-ttu-id="9d75c-144">过程`Calculate`同时具有`ByVal`和`ByRef`参数。</span><span class="sxs-lookup"><span data-stu-id="9d75c-144">Procedure `Calculate` has both a `ByVal` and a `ByRef` parameter.</span></span> <span data-ttu-id="9d75c-145">给定利率， `rate`，和资金，总和`debt`，该过程的任务是来计算新值的`debt`，它是对应用的结果利率的原始值`debt`。</span><span class="sxs-lookup"><span data-stu-id="9d75c-145">Given an interest rate, `rate`, and a sum of money, `debt`, the task of the procedure is to calculate a new value for `debt` that is the result of applying the interest rate to the original value of `debt`.</span></span> <span data-ttu-id="9d75c-146">因为`debt`是`ByRef`参数，对应于调用代码中的参数的值中反映新的总`debt`。</span><span class="sxs-lookup"><span data-stu-id="9d75c-146">Because `debt` is a `ByRef` parameter, the new total is reflected in the value of the argument in the calling code that corresponds to `debt`.</span></span> <span data-ttu-id="9d75c-147">参数`rate`是`ByVal`参数因为`Calculate`不应更改其值。</span><span class="sxs-lookup"><span data-stu-id="9d75c-147">Parameter `rate` is a `ByVal` parameter because `Calculate` should not change its value.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9d75c-148">代码</span><span class="sxs-lookup"><span data-stu-id="9d75c-148">Code</span></span>  
 <span data-ttu-id="9d75c-149">[!code-vb[VbVbcnProcedures #&74;](./codesnippet/VisualBasic/passing-arguments-by-value-and-by-reference_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="9d75c-149">[!code-vb[VbVbcnProcedures#74](./codesnippet/VisualBasic/passing-arguments-by-value-and-by-reference_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d75c-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d75c-150">See Also</span></span>  
 <span data-ttu-id="9d75c-151">[过程](./index.md) </span><span class="sxs-lookup"><span data-stu-id="9d75c-151">[Procedures](./index.md) </span></span>  
<span data-ttu-id="9d75c-152"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="9d75c-152"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="9d75c-153"> [如何︰ 将参数传递给过程](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="9d75c-153"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="9d75c-154"> [如何︰ 更改过程参数的值](./how-to-change-the-value-of-a-procedure-argument.md) </span><span class="sxs-lookup"><span data-stu-id="9d75c-154"> [How to: Change the Value of a Procedure Argument](./how-to-change-the-value-of-a-procedure-argument.md) </span></span>  
<span data-ttu-id="9d75c-155"> [如何︰ 防止过程参数的值更改](./how-to-protect-a-procedure-argument-against-value-changes.md) </span><span class="sxs-lookup"><span data-stu-id="9d75c-155"> [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md) </span></span>  
<span data-ttu-id="9d75c-156"> [如何︰ 强制通过值传递参数](./how-to-force-an-argument-to-be-passed-by-value.md) </span><span class="sxs-lookup"><span data-stu-id="9d75c-156"> [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md) </span></span>  
<span data-ttu-id="9d75c-157"> [按位置和按名称传递参数](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="9d75c-157"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="9d75c-158"> [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="9d75c-158"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
