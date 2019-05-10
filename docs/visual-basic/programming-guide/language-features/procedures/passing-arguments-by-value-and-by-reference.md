---
title: 通过值和通过引用传递参数 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- passing arguments [Visual Basic], by value or by reference
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing [Visual Basic], by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
ms.openlocfilehash: eb2260c6547d4f1cd7d9c23445ac38ac600e3535
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64638869"
---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="7ebf6-102">通过值和通过引用传递参数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ebf6-102">Passing Arguments by Value and by Reference (Visual Basic)</span></span>
<span data-ttu-id="7ebf6-103">在 Visual Basic 中，您可以传递参数给过程*按值*或*按引用*。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-103">In Visual Basic, you can pass an argument to a procedure *by value* or *by reference*.</span></span> <span data-ttu-id="7ebf6-104">这称为*传递机制*，并确定该过程是否可以修改调用代码中的参数的基础的编程元素。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-104">This is known as the *passing mechanism*, and it determines whether the procedure can modify the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="7ebf6-105">过程声明确定通过指定每个参数的传递机制[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-105">The procedure declaration determines the passing mechanism for each parameter by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword.</span></span>  
  
## <a name="distinctions"></a><span data-ttu-id="7ebf6-106">区别</span><span class="sxs-lookup"><span data-stu-id="7ebf6-106">Distinctions</span></span>  
 <span data-ttu-id="7ebf6-107">向过程传递参数，应注意的几点彼此交互的差异：</span><span class="sxs-lookup"><span data-stu-id="7ebf6-107">When passing an argument to a procedure, be aware of several different distinctions that interact with each other:</span></span>  
  
- <span data-ttu-id="7ebf6-108">基础的编程元素是否可修改或不可修改</span><span class="sxs-lookup"><span data-stu-id="7ebf6-108">Whether the underlying programming element is modifiable or nonmodifiable</span></span>  
  
- <span data-ttu-id="7ebf6-109">参数本身是可修改或不可修改</span><span class="sxs-lookup"><span data-stu-id="7ebf6-109">Whether the argument itself is modifiable or nonmodifiable</span></span>  
  
- <span data-ttu-id="7ebf6-110">自变量通过值或按引用传递</span><span class="sxs-lookup"><span data-stu-id="7ebf6-110">Whether the argument is being passed by value or by reference</span></span>  
  
- <span data-ttu-id="7ebf6-111">参数数据类型是值类型或引用类型</span><span class="sxs-lookup"><span data-stu-id="7ebf6-111">Whether the argument data type is a value type or a reference type</span></span>  
  
 <span data-ttu-id="7ebf6-112">有关详细信息，请参阅[差异之间可修改和不可修改自变量](./differences-between-modifiable-and-nonmodifiable-arguments.md)并[差异之间传递参数值和按引用来](./differences-between-passing-an-argument-by-value-and-by-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-112">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) and [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="choice-of-passing-mechanism"></a><span data-ttu-id="7ebf6-113">选择的传递机制</span><span class="sxs-lookup"><span data-stu-id="7ebf6-113">Choice of Passing Mechanism</span></span>  
 <span data-ttu-id="7ebf6-114">应选择仔细的每个自变量的传递机制。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-114">You should choose the passing mechanism carefully for each argument.</span></span>  
  
- <span data-ttu-id="7ebf6-115">**保护**。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-115">**Protection**.</span></span> <span data-ttu-id="7ebf6-116">在两个传递机制之间进行选择，最重要的条件是要更改的调用变量公开。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-116">In choosing between the two passing mechanisms, the most important criterion is the exposure of calling variables to change.</span></span> <span data-ttu-id="7ebf6-117">传递自变量的优点`ByRef`是该过程可以返回给调用代码通过该参数的值。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-117">The advantage of passing an argument `ByRef` is that the procedure can return a value to the calling code through that argument.</span></span> <span data-ttu-id="7ebf6-118">传递自变量的优点`ByVal`是它可防止变量正在更改的过程。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-118">The advantage of passing an argument `ByVal` is that it protects a variable from being changed by the procedure.</span></span>  
  
- <span data-ttu-id="7ebf6-119">**性能**。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-119">**Performance**.</span></span> <span data-ttu-id="7ebf6-120">虽然的传递机制可能会影响代码的性能，不同之处是通常并不显著。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-120">Although the passing mechanism can affect the performance of your code, the difference is usually insignificant.</span></span> <span data-ttu-id="7ebf6-121">一个例外是值类型传递`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-121">One exception to this is a value type passed `ByVal`.</span></span> <span data-ttu-id="7ebf6-122">在这种情况下，Visual Basic 将复制整个数据内容的自变量。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-122">In this case, Visual Basic copies the entire data contents of the argument.</span></span> <span data-ttu-id="7ebf6-123">因此，较大的值类型，如一个结构，它可以更有效，将其传递`ByRef`。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-123">Therefore, for a large value type such as a structure, it can be more efficient to pass it `ByRef`.</span></span>  
  
     <span data-ttu-id="7ebf6-124">对于引用类型，仅对数据的指针是复制 （四个字节在 32 位平台上，在 64 位平台上的 8 个字节）。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-124">For reference types, only the pointer to the data is copied (four bytes on 32-bit platforms, eight bytes on 64-bit platforms).</span></span> <span data-ttu-id="7ebf6-125">因此，可以将类型的参数传递`String`或`Object`通过值而不损害性能。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-125">Therefore, you can pass arguments of type `String` or `Object` by value without harming performance.</span></span>  
  
## <a name="determination-of-the-passing-mechanism"></a><span data-ttu-id="7ebf6-126">确定的传递机制</span><span class="sxs-lookup"><span data-stu-id="7ebf6-126">Determination of the Passing Mechanism</span></span>  
 <span data-ttu-id="7ebf6-127">过程声明指定每个参数的传递机制。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-127">The procedure declaration specifies the passing mechanism for each parameter.</span></span> <span data-ttu-id="7ebf6-128">调用代码不能重写`ByVal`机制。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-128">The calling code can't override a `ByVal` mechanism.</span></span>  
  
 <span data-ttu-id="7ebf6-129">如果与声明的参数`ByRef`，调用代码可以强制机制来`ByVal`将参数名称括在括号内的调用中。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-129">If a parameter is declared with `ByRef`, the calling code can force the mechanism to `ByVal` by enclosing the argument name in parentheses in the call.</span></span> <span data-ttu-id="7ebf6-130">有关详细信息，请参阅[如何：强制通过值传递自变量](./how-to-force-an-argument-to-be-passed-by-value.md)。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-130">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
 <span data-ttu-id="7ebf6-131">Visual Basic 中的默认值是按值传递参数。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-131">The default in Visual Basic is to pass arguments by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-value"></a><span data-ttu-id="7ebf6-132">何时按值传递参数</span><span class="sxs-lookup"><span data-stu-id="7ebf6-132">When to Pass an Argument by Value</span></span>  
  
- <span data-ttu-id="7ebf6-133">如果基础自变量调用的代码元素是不可修改的元素，声明对应的形参[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-133">If the calling code element underlying the argument is a nonmodifiable element, declare the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="7ebf6-134">没有代码可以更改不可修改的元素的值。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-134">No code can change the value of a nonmodifiable element.</span></span>  
  
- <span data-ttu-id="7ebf6-135">如果基础元素是可修改，但不是希望将无法更改其值的过程，将参数声明`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-135">If the underlying element is modifiable, but you do not want the procedure to be able to change its value, declare the parameter `ByVal`.</span></span> <span data-ttu-id="7ebf6-136">仅调用代码可以更改按值传递的可修改元素的值。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-136">Only the calling code can change the value of a modifiable element passed by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-reference"></a><span data-ttu-id="7ebf6-137">何时按引用传递参数</span><span class="sxs-lookup"><span data-stu-id="7ebf6-137">When to Pass an Argument by Reference</span></span>  
  
- <span data-ttu-id="7ebf6-138">如果该过程有确实需要更改调用代码中的基础元素，声明对应的形参[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-138">If the procedure has a genuine need to change the underlying element in the calling code, declare the corresponding parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span>  
  
- <span data-ttu-id="7ebf6-139">如果正确执行代码取决于更改调用代码中的基础元素的过程，将参数声明`ByRef`。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-139">If the correct execution of the code depends on the procedure changing the underlying element in the calling code, declare the parameter `ByRef`.</span></span> <span data-ttu-id="7ebf6-140">如果将其传递的值，或者调用代码重写`ByRef`括在括号中，自变量传递机制在过程调用可能会产生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-140">If you pass it by value, or if the calling code overrides the `ByRef` passing mechanism by enclosing the argument in parentheses, the procedure call might produce unexpected results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ebf6-141">示例</span><span class="sxs-lookup"><span data-stu-id="7ebf6-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7ebf6-142">描述</span><span class="sxs-lookup"><span data-stu-id="7ebf6-142">Description</span></span>  
 <span data-ttu-id="7ebf6-143">下面的示例说明了何时按值传递参数，以及何时将它们按引用传递。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-143">The following example illustrates when to pass arguments by value and when to pass them by reference.</span></span> <span data-ttu-id="7ebf6-144">过程`Calculate`同时具有`ByVal`和一个`ByRef`参数。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-144">Procedure `Calculate` has both a `ByVal` and a `ByRef` parameter.</span></span> <span data-ttu-id="7ebf6-145">给定利率`rate`，和的总金额的`debt`，该过程的任务是计算新值的`debt`，它是应用到的原始值的利率的结果`debt`。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-145">Given an interest rate, `rate`, and a sum of money, `debt`, the task of the procedure is to calculate a new value for `debt` that is the result of applying the interest rate to the original value of `debt`.</span></span> <span data-ttu-id="7ebf6-146">因为`debt`是`ByRef`参数，对应于在调用代码中的参数的值中反映新的总`debt`。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-146">Because `debt` is a `ByRef` parameter, the new total is reflected in the value of the argument in the calling code that corresponds to `debt`.</span></span> <span data-ttu-id="7ebf6-147">参数`rate`是`ByVal`参数因为`Calculate`不应更改其值。</span><span class="sxs-lookup"><span data-stu-id="7ebf6-147">Parameter `rate` is a `ByVal` parameter because `Calculate` should not change its value.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7ebf6-148">代码</span><span class="sxs-lookup"><span data-stu-id="7ebf6-148">Code</span></span>  
 [!code-vb[VbVbcnProcedures#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class2.vb#74)]  
  
## <a name="see-also"></a><span data-ttu-id="7ebf6-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ebf6-149">See also</span></span>

- [<span data-ttu-id="7ebf6-150">过程</span><span class="sxs-lookup"><span data-stu-id="7ebf6-150">Procedures</span></span>](./index.md)
- [<span data-ttu-id="7ebf6-151">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="7ebf6-151">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="7ebf6-152">如何：将参数传递给过程</span><span class="sxs-lookup"><span data-stu-id="7ebf6-152">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="7ebf6-153">如何：更改过程自变量的值</span><span class="sxs-lookup"><span data-stu-id="7ebf6-153">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="7ebf6-154">如何：防止过程自变量的值更改</span><span class="sxs-lookup"><span data-stu-id="7ebf6-154">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="7ebf6-155">如何：强制通过值传递自变量</span><span class="sxs-lookup"><span data-stu-id="7ebf6-155">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="7ebf6-156">按位置和按名称传递自变量</span><span class="sxs-lookup"><span data-stu-id="7ebf6-156">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="7ebf6-157">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="7ebf6-157">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
