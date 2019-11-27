---
title: 通过值和通过引用传递自变量
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- passing arguments [Visual Basic], by value or by reference
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing [Visual Basic], by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
ms.openlocfilehash: 28e59753a35ab67b15fbc549df5bb8a3489aba5a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352608"
---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="697d1-102">通过值和通过引用传递参数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="697d1-102">Passing Arguments by Value and by Reference (Visual Basic)</span></span>
<span data-ttu-id="697d1-103">在 Visual Basic 中，可以*通过值*或*引用*将参数传递给过程。</span><span class="sxs-lookup"><span data-stu-id="697d1-103">In Visual Basic, you can pass an argument to a procedure *by value* or *by reference*.</span></span> <span data-ttu-id="697d1-104">这称为*传递机制*，它确定过程是否可以修改调用代码中参数的基础编程元素。</span><span class="sxs-lookup"><span data-stu-id="697d1-104">This is known as the *passing mechanism*, and it determines whether the procedure can modify the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="697d1-105">过程声明通过指定[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字来确定每个参数的传递机制。</span><span class="sxs-lookup"><span data-stu-id="697d1-105">The procedure declaration determines the passing mechanism for each parameter by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword.</span></span>  
  
## <a name="distinctions"></a><span data-ttu-id="697d1-106">区别</span><span class="sxs-lookup"><span data-stu-id="697d1-106">Distinctions</span></span>  
 <span data-ttu-id="697d1-107">将参数传递给过程时，请注意彼此交互的几个不同的区别：</span><span class="sxs-lookup"><span data-stu-id="697d1-107">When passing an argument to a procedure, be aware of several different distinctions that interact with each other:</span></span>  
  
- <span data-ttu-id="697d1-108">基础编程元素是否可修改或不可更改</span><span class="sxs-lookup"><span data-stu-id="697d1-108">Whether the underlying programming element is modifiable or nonmodifiable</span></span>  
  
- <span data-ttu-id="697d1-109">参数本身是否可修改或不可更改</span><span class="sxs-lookup"><span data-stu-id="697d1-109">Whether the argument itself is modifiable or nonmodifiable</span></span>  
  
- <span data-ttu-id="697d1-110">参数是通过值还是通过引用传递</span><span class="sxs-lookup"><span data-stu-id="697d1-110">Whether the argument is being passed by value or by reference</span></span>  
  
- <span data-ttu-id="697d1-111">参数数据类型是值类型还是引用类型</span><span class="sxs-lookup"><span data-stu-id="697d1-111">Whether the argument data type is a value type or a reference type</span></span>  
  
 <span data-ttu-id="697d1-112">有关详细信息，请参阅可[修改和不可修改参数](./differences-between-modifiable-and-nonmodifiable-arguments.md)与通过[值传递参数和通过引用传递参数](./differences-between-passing-an-argument-by-value-and-by-reference.md)之间的差异。</span><span class="sxs-lookup"><span data-stu-id="697d1-112">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) and [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="choice-of-passing-mechanism"></a><span data-ttu-id="697d1-113">选择传递机制</span><span class="sxs-lookup"><span data-stu-id="697d1-113">Choice of Passing Mechanism</span></span>  
 <span data-ttu-id="697d1-114">应为每个参数仔细选择传递机制。</span><span class="sxs-lookup"><span data-stu-id="697d1-114">You should choose the passing mechanism carefully for each argument.</span></span>  
  
- <span data-ttu-id="697d1-115">**保护**。</span><span class="sxs-lookup"><span data-stu-id="697d1-115">**Protection**.</span></span> <span data-ttu-id="697d1-116">在两个传递机制之间进行选择时，最重要的条件是公开调用变量以进行更改。</span><span class="sxs-lookup"><span data-stu-id="697d1-116">In choosing between the two passing mechanisms, the most important criterion is the exposure of calling variables to change.</span></span> <span data-ttu-id="697d1-117">传递参数 `ByRef` 的优点是过程可以通过该参数向调用代码返回值。</span><span class="sxs-lookup"><span data-stu-id="697d1-117">The advantage of passing an argument `ByRef` is that the procedure can return a value to the calling code through that argument.</span></span> <span data-ttu-id="697d1-118">`ByVal` 传递参数的优点在于，它可以防止变量被过程更改。</span><span class="sxs-lookup"><span data-stu-id="697d1-118">The advantage of passing an argument `ByVal` is that it protects a variable from being changed by the procedure.</span></span>  
  
- <span data-ttu-id="697d1-119">**性能**。</span><span class="sxs-lookup"><span data-stu-id="697d1-119">**Performance**.</span></span> <span data-ttu-id="697d1-120">尽管传递机制可能会影响你的代码的性能，但差别通常是不重要的。</span><span class="sxs-lookup"><span data-stu-id="697d1-120">Although the passing mechanism can affect the performance of your code, the difference is usually insignificant.</span></span> <span data-ttu-id="697d1-121">这种情况的一个例外是 `ByVal`传递的值类型。</span><span class="sxs-lookup"><span data-stu-id="697d1-121">One exception to this is a value type passed `ByVal`.</span></span> <span data-ttu-id="697d1-122">在这种情况下，Visual Basic 会复制参数的所有数据内容。</span><span class="sxs-lookup"><span data-stu-id="697d1-122">In this case, Visual Basic copies the entire data contents of the argument.</span></span> <span data-ttu-id="697d1-123">因此，对于大值类型（如结构），将其传递到 `ByRef`会更有效。</span><span class="sxs-lookup"><span data-stu-id="697d1-123">Therefore, for a large value type such as a structure, it can be more efficient to pass it `ByRef`.</span></span>  
  
     <span data-ttu-id="697d1-124">对于引用类型，只会复制指向数据的指针（32位平台上的四个字节，64位平台上的8个字节）。</span><span class="sxs-lookup"><span data-stu-id="697d1-124">For reference types, only the pointer to the data is copied (four bytes on 32-bit platforms, eight bytes on 64-bit platforms).</span></span> <span data-ttu-id="697d1-125">因此，可以传递类型为 `String` 或 `Object` 的参数，而不会对性能有任何损害。</span><span class="sxs-lookup"><span data-stu-id="697d1-125">Therefore, you can pass arguments of type `String` or `Object` by value without harming performance.</span></span>  
  
## <a name="determination-of-the-passing-mechanism"></a><span data-ttu-id="697d1-126">确定传递机制</span><span class="sxs-lookup"><span data-stu-id="697d1-126">Determination of the Passing Mechanism</span></span>  
 <span data-ttu-id="697d1-127">过程声明指定每个参数的传递机制。</span><span class="sxs-lookup"><span data-stu-id="697d1-127">The procedure declaration specifies the passing mechanism for each parameter.</span></span> <span data-ttu-id="697d1-128">调用代码无法重写 `ByVal` 机制。</span><span class="sxs-lookup"><span data-stu-id="697d1-128">The calling code can't override a `ByVal` mechanism.</span></span>  
  
 <span data-ttu-id="697d1-129">如果使用 `ByRef`声明参数，则调用代码可以通过在调用中将参数名称括在括号中来强制 `ByVal` 机制。</span><span class="sxs-lookup"><span data-stu-id="697d1-129">If a parameter is declared with `ByRef`, the calling code can force the mechanism to `ByVal` by enclosing the argument name in parentheses in the call.</span></span> <span data-ttu-id="697d1-130">有关详细信息，请参阅[如何：强制通过值传递参数](./how-to-force-an-argument-to-be-passed-by-value.md)。</span><span class="sxs-lookup"><span data-stu-id="697d1-130">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
 <span data-ttu-id="697d1-131">Visual Basic 中的默认值是按值传递参数。</span><span class="sxs-lookup"><span data-stu-id="697d1-131">The default in Visual Basic is to pass arguments by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-value"></a><span data-ttu-id="697d1-132">何时按值传递参数</span><span class="sxs-lookup"><span data-stu-id="697d1-132">When to Pass an Argument by Value</span></span>  
  
- <span data-ttu-id="697d1-133">如果作为参数的基础的调用代码元素是不可更改的元素，则声明相应的参数[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)。</span><span class="sxs-lookup"><span data-stu-id="697d1-133">If the calling code element underlying the argument is a nonmodifiable element, declare the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="697d1-134">任何代码都不能更改不可更改元素的值。</span><span class="sxs-lookup"><span data-stu-id="697d1-134">No code can change the value of a nonmodifiable element.</span></span>  
  
- <span data-ttu-id="697d1-135">如果基础元素可修改，但您不希望该过程能够更改其值，请将参数声明 `ByVal`。</span><span class="sxs-lookup"><span data-stu-id="697d1-135">If the underlying element is modifiable, but you do not want the procedure to be able to change its value, declare the parameter `ByVal`.</span></span> <span data-ttu-id="697d1-136">只有调用代码可以更改通过值传递的可修改元素的值。</span><span class="sxs-lookup"><span data-stu-id="697d1-136">Only the calling code can change the value of a modifiable element passed by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-reference"></a><span data-ttu-id="697d1-137">何时通过引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="697d1-137">When to Pass an Argument by Reference</span></span>  
  
- <span data-ttu-id="697d1-138">如果过程确实需要更改调用代码中的基础元素，请声明相应的参数[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)。</span><span class="sxs-lookup"><span data-stu-id="697d1-138">If the procedure has a genuine need to change the underlying element in the calling code, declare the corresponding parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span>  
  
- <span data-ttu-id="697d1-139">如果正确执行代码取决于更改调用代码中基础元素的过程，请将参数 `ByRef`声明。</span><span class="sxs-lookup"><span data-stu-id="697d1-139">If the correct execution of the code depends on the procedure changing the underlying element in the calling code, declare the parameter `ByRef`.</span></span> <span data-ttu-id="697d1-140">如果按值传递它，或者调用代码通过将参数括在括号中来覆盖 `ByRef` 传递机制，则过程调用可能会产生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="697d1-140">If you pass it by value, or if the calling code overrides the `ByRef` passing mechanism by enclosing the argument in parentheses, the procedure call might produce unexpected results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="697d1-141">示例</span><span class="sxs-lookup"><span data-stu-id="697d1-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="697d1-142">说明</span><span class="sxs-lookup"><span data-stu-id="697d1-142">Description</span></span>  
 <span data-ttu-id="697d1-143">下面的示例说明何时按值传递参数，以及何时通过引用传递参数。</span><span class="sxs-lookup"><span data-stu-id="697d1-143">The following example illustrates when to pass arguments by value and when to pass them by reference.</span></span> <span data-ttu-id="697d1-144">过程 `Calculate` 具有 `ByVal` 和 `ByRef` 参数。</span><span class="sxs-lookup"><span data-stu-id="697d1-144">Procedure `Calculate` has both a `ByVal` and a `ByRef` parameter.</span></span> <span data-ttu-id="697d1-145">对于利率、`rate`和金钱的总和 `debt`，该过程的任务是计算 `debt` 的新值，这是将利率应用于 `debt`的原始值的结果。</span><span class="sxs-lookup"><span data-stu-id="697d1-145">Given an interest rate, `rate`, and a sum of money, `debt`, the task of the procedure is to calculate a new value for `debt` that is the result of applying the interest rate to the original value of `debt`.</span></span> <span data-ttu-id="697d1-146">由于 `debt` 是 `ByRef` 参数，因此新的总计将反映在与 `debt`对应的调用代码中的参数值中。</span><span class="sxs-lookup"><span data-stu-id="697d1-146">Because `debt` is a `ByRef` parameter, the new total is reflected in the value of the argument in the calling code that corresponds to `debt`.</span></span> <span data-ttu-id="697d1-147">参数 `rate` 是 `ByVal` 参数，因为 `Calculate` 不应更改其值。</span><span class="sxs-lookup"><span data-stu-id="697d1-147">Parameter `rate` is a `ByVal` parameter because `Calculate` should not change its value.</span></span>  
  
### <a name="code"></a><span data-ttu-id="697d1-148">代码</span><span class="sxs-lookup"><span data-stu-id="697d1-148">Code</span></span>  
 [!code-vb[VbVbcnProcedures#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class2.vb#74)]  
  
## <a name="see-also"></a><span data-ttu-id="697d1-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="697d1-149">See also</span></span>

- [<span data-ttu-id="697d1-150">过程</span><span class="sxs-lookup"><span data-stu-id="697d1-150">Procedures</span></span>](./index.md)
- [<span data-ttu-id="697d1-151">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="697d1-151">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="697d1-152">如何：将自变量传递给过程</span><span class="sxs-lookup"><span data-stu-id="697d1-152">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="697d1-153">如何：更改过程自变量的值</span><span class="sxs-lookup"><span data-stu-id="697d1-153">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="697d1-154">如何：防止过程自变量的值被更改</span><span class="sxs-lookup"><span data-stu-id="697d1-154">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="697d1-155">如何：强制通过值传递自变量</span><span class="sxs-lookup"><span data-stu-id="697d1-155">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="697d1-156">按位置和按名称传递自变量</span><span class="sxs-lookup"><span data-stu-id="697d1-156">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="697d1-157">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="697d1-157">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
