---
title: 宽松委托转换
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: ffb242842553382ba26121333c38fc65eaa168a9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345222"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="adfe3-102">宽松委托转换 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="adfe3-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="adfe3-103">通过宽松委托转换，您可以将 sub 和函数分配给委托或处理程序，即使它们的签名不相同。</span><span class="sxs-lookup"><span data-stu-id="adfe3-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="adfe3-104">因此，绑定到委托将与已允许方法调用的绑定一致。</span><span class="sxs-lookup"><span data-stu-id="adfe3-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="adfe3-105">参数和返回类型</span><span class="sxs-lookup"><span data-stu-id="adfe3-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="adfe3-106">宽松转换要求在将 `Option Strict` 设置为 `On`时满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="adfe3-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
- <span data-ttu-id="adfe3-107">必须将每个委托参数的数据类型的扩大转换为分配的函数或 `Sub`的相应参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="adfe3-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="adfe3-108">在下面的示例中，委托 `Del1` 具有一个参数，即一个 `Integer`。</span><span class="sxs-lookup"><span data-stu-id="adfe3-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="adfe3-109">已分配 lambda 表达式中的参数 `m` 必须具有一个数据类型，该数据类型的数据类型为，其中存在从 `Integer`的扩大转换，如 `Long` 或 `Double`。</span><span class="sxs-lookup"><span data-stu-id="adfe3-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     <span data-ttu-id="adfe3-110">仅当 `Option Strict` 设置为 `Off`时，才允许收缩转换。</span><span class="sxs-lookup"><span data-stu-id="adfe3-110">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- <span data-ttu-id="adfe3-111">扩大转换必须与指定函数的返回类型或 `Sub` 为委托的返回类型的方向相反。</span><span class="sxs-lookup"><span data-stu-id="adfe3-111">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="adfe3-112">在下面的示例中，每个已分配 lambda 表达式的主体的计算结果都必须是扩大到 `Integer` 的数据类型，因为 `del1` 的返回类型是 `Integer`的。</span><span class="sxs-lookup"><span data-stu-id="adfe3-112">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 <span data-ttu-id="adfe3-113">如果 `Option Strict` 设置为 `Off`，则将在这两个方向上删除扩大限制。</span><span class="sxs-lookup"><span data-stu-id="adfe3-113">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="adfe3-114">省略参数规范</span><span class="sxs-lookup"><span data-stu-id="adfe3-114">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="adfe3-115">宽松委托还允许您完全省略分配的方法中的参数规范：</span><span class="sxs-lookup"><span data-stu-id="adfe3-115">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 <span data-ttu-id="adfe3-116">请注意，不能指定某些参数并忽略其他参数。</span><span class="sxs-lookup"><span data-stu-id="adfe3-116">Note that you cannot specify some parameters and omit others.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 <span data-ttu-id="adfe3-117">在某些情况下，忽略参数的功能非常有用，例如定义一个事件处理程序，其中涉及多个复杂参数。</span><span class="sxs-lookup"><span data-stu-id="adfe3-117">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="adfe3-118">不使用某些事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="adfe3-118">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="adfe3-119">相反，处理程序将直接访问在其上注册事件的控件的状态，并忽略参数。</span><span class="sxs-lookup"><span data-stu-id="adfe3-119">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="adfe3-120">宽松的委托允许在没有歧义结果时省略此类声明中的参数。</span><span class="sxs-lookup"><span data-stu-id="adfe3-120">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="adfe3-121">在下面的示例中，`OnClick` 的完全指定方法可以重写为 `RelaxedOnClick`。</span><span class="sxs-lookup"><span data-stu-id="adfe3-121">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="adfe3-122">AddressOf 示例</span><span class="sxs-lookup"><span data-stu-id="adfe3-122">AddressOf Examples</span></span>  
 <span data-ttu-id="adfe3-123">前面的示例中使用了 Lambda 表达式，使类型关系易于查看。</span><span class="sxs-lookup"><span data-stu-id="adfe3-123">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="adfe3-124">但是，允许使用 `AddressOf`、`Handles`或 `AddHandler`的委托分配使用相同的松弛法。</span><span class="sxs-lookup"><span data-stu-id="adfe3-124">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="adfe3-125">在下面的示例中，函数 `f1`、`f2`、`f3`和 `f4` 都可以分配给 `Del1`。</span><span class="sxs-lookup"><span data-stu-id="adfe3-125">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 <span data-ttu-id="adfe3-126">仅当 `Option Strict` 设置为 `Off`时，下面的示例才有效。</span><span class="sxs-lookup"><span data-stu-id="adfe3-126">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="adfe3-127">删除函数返回</span><span class="sxs-lookup"><span data-stu-id="adfe3-127">Dropping Function Returns</span></span>  
 <span data-ttu-id="adfe3-128">通过宽松委托转换，您可以将函数分配给 `Sub` 委托，从而有效地忽略函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="adfe3-128">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="adfe3-129">但是，不能向函数委托分配 `Sub`。</span><span class="sxs-lookup"><span data-stu-id="adfe3-129">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="adfe3-130">在下面的示例中，函数 `doubler` 的地址分配给 `Sub` 委托 `Del3`。</span><span class="sxs-lookup"><span data-stu-id="adfe3-130">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="adfe3-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="adfe3-131">See also</span></span>

- [<span data-ttu-id="adfe3-132">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="adfe3-132">Lambda Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="adfe3-133">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="adfe3-133">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="adfe3-134">委托</span><span class="sxs-lookup"><span data-stu-id="adfe3-134">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="adfe3-135">如何：在 Visual Basic 中将过程传递给另一过程</span><span class="sxs-lookup"><span data-stu-id="adfe3-135">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="adfe3-136">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="adfe3-136">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="adfe3-137">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="adfe3-137">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
