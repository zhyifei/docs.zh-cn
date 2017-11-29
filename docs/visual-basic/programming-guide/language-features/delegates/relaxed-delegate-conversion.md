---
title: "宽松委托转换 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0cca3d09b538905714f627c9fa006187b8927383
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="d1d5d-102">宽松委托转换 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1d5d-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="d1d5d-103">宽松的委托转换，可将订阅和函数分配给委托或处理程序，即使在它们的签名不相同。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="d1d5d-104">因此，绑定到委托将与已允许的方法调用绑定保持一致。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="d1d5d-105">参数和返回类型</span><span class="sxs-lookup"><span data-stu-id="d1d5d-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="d1d5d-106">替代签名完全匹配宽松的转换需要满足以下条件时`Option Strict`设置为`On`:</span><span class="sxs-lookup"><span data-stu-id="d1d5d-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
-   <span data-ttu-id="d1d5d-107">扩大转换为所分配函数的相应参数的数据类型必须存在从每个委托参数的数据类型或`Sub`。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="d1d5d-108">在下面的示例中，委托`Del1`具有一个参数、 `Integer`。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="d1d5d-109">参数`m`中分配的 lambda 表达式必须具有的扩大转换数据类型`Integer`，如`Long`或`Double`。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]  
  
     <span data-ttu-id="d1d5d-110">收缩转换允许仅当`Option Strict`设置为`Off`。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-110">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]  
  
-   <span data-ttu-id="d1d5d-111">扩大转换必须存在分配的函数的返回类型从相反的方向或`Sub`到委托的返回类型。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-111">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="d1d5d-112">在以下示例中，每个分配的 lambda 表达式的主体计算结果必须为数据类型扩大到`Integer`因为返回类型的`del1`是`Integer`。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-112">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]  
  
 <span data-ttu-id="d1d5d-113">如果`Option Strict`设置为`Off`，扩大限制已从两个方向中删除。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-113">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="d1d5d-114">省略参数规范</span><span class="sxs-lookup"><span data-stu-id="d1d5d-114">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="d1d5d-115">宽松的委托还允许您将能够完全省略分配的方法中的参数规范：</span><span class="sxs-lookup"><span data-stu-id="d1d5d-115">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]  
  
 <span data-ttu-id="d1d5d-116">请注意，你不能指定某些参数并且省略其他人。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-116">Note that you cannot specify some parameters and omit others.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]  
  
 <span data-ttu-id="d1d5d-117">若要省略参数的能力是如定义事件处理程序，其中包含多个复杂参数的情况下有用。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-117">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="d1d5d-118">不使用某些事件处理程序的自变量。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-118">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="d1d5d-119">相反，该处理程序直接访问的控件的事件在其注册，并忽略这些参数的状态。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-119">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="d1d5d-120">宽松的委托允许你忽略不产生多义性时此类声明中的参数。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-120">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="d1d5d-121">在下面的示例中，完全指定的方法`OnClick`可以重写为`RelaxedOnClick`。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-121">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="d1d5d-122">AddressOf 示例</span><span class="sxs-lookup"><span data-stu-id="d1d5d-122">AddressOf Examples</span></span>  
 <span data-ttu-id="d1d5d-123">在前面的示例使用 lambda 表达式以便可以方便地查看类型关系。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-123">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="d1d5d-124">但是，相同松弛法允许使用的委托分配`AddressOf`， `Handles`，或`AddHandler`。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-124">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="d1d5d-125">在下面的示例中，函数`f1`， `f2`， `f3`，和`f4`都可以分配到`Del1`。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-125">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]  
  
 <span data-ttu-id="d1d5d-126">下面的示例是仅当`Option Strict`设置为`Off`。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-126">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="d1d5d-127">删除函数返回值</span><span class="sxs-lookup"><span data-stu-id="d1d5d-127">Dropping Function Returns</span></span>  
 <span data-ttu-id="d1d5d-128">宽松的委托转换使您能够分配到函数`Sub`委托，有效地忽略该函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-128">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="d1d5d-129">但是，不能将分配`Sub`到函数委托。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-129">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="d1d5d-130">在下面的示例中，函数的地址`doubler`分配给`Sub`委托`Del3`。</span><span class="sxs-lookup"><span data-stu-id="d1d5d-130">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d1d5d-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1d5d-131">See Also</span></span>  
 [<span data-ttu-id="d1d5d-132">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="d1d5d-132">Lambda Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="d1d5d-133">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="d1d5d-133">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="d1d5d-134">委托</span><span class="sxs-lookup"><span data-stu-id="d1d5d-134">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="d1d5d-135">如何：在 Visual Basic 中将过程传递给另一过程</span><span class="sxs-lookup"><span data-stu-id="d1d5d-135">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)  
 [<span data-ttu-id="d1d5d-136">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="d1d5d-136">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="d1d5d-137">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="d1d5d-137">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
