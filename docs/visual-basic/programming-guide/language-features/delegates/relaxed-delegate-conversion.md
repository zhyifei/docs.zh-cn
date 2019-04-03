---
title: 宽松委托转换 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: 57e863d9781721a997ae49e1a5c9d8f3562a1bd0
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842715"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="53c4c-102">宽松委托转换 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53c4c-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="53c4c-103">宽松的委托转换，可将子例程和函数分配给委托或处理程序，即使它们的签名不相同。</span><span class="sxs-lookup"><span data-stu-id="53c4c-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="53c4c-104">因此，绑定到委托将与已允许为方法调用的绑定一致。</span><span class="sxs-lookup"><span data-stu-id="53c4c-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="53c4c-105">参数和返回类型</span><span class="sxs-lookup"><span data-stu-id="53c4c-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="53c4c-106">替代签名完全匹配，宽松的转换需要满足以下条件时`Option Strict`设置为`On`:</span><span class="sxs-lookup"><span data-stu-id="53c4c-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
-   <span data-ttu-id="53c4c-107">扩大转换为已分配的函数的相应参数的数据类型必须存在从每个委托参数的数据类型或`Sub`。</span><span class="sxs-lookup"><span data-stu-id="53c4c-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="53c4c-108">在下面的示例中，委托`Del1`具有一个参数、 `Integer`。</span><span class="sxs-lookup"><span data-stu-id="53c4c-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="53c4c-109">参数`m`中已分配的 lambda 表达式必须具有的扩大转换的数据类型`Integer`，如`Long`或`Double`。</span><span class="sxs-lookup"><span data-stu-id="53c4c-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     <span data-ttu-id="53c4c-110">允许收缩转换时，才`Option Strict`设置为`Off`。</span><span class="sxs-lookup"><span data-stu-id="53c4c-110">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
-   <span data-ttu-id="53c4c-111">扩大转换必须存在于已分配的函数的返回类型的相反方向或`Sub`到委托的返回类型。</span><span class="sxs-lookup"><span data-stu-id="53c4c-111">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="53c4c-112">在以下示例中，每个已分配的 lambda 表达式的主体必须为数据类型扩大到`Integer`因为的返回类型`del1`是`Integer`。</span><span class="sxs-lookup"><span data-stu-id="53c4c-112">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 <span data-ttu-id="53c4c-113">如果`Option Strict`设置为`Off`，则两个方向中删除了扩大限制。</span><span class="sxs-lookup"><span data-stu-id="53c4c-113">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="53c4c-114">省略参数规范</span><span class="sxs-lookup"><span data-stu-id="53c4c-114">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="53c4c-115">放松要求的委托还允许你完全忽略中的分配方法的参数规范：</span><span class="sxs-lookup"><span data-stu-id="53c4c-115">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 <span data-ttu-id="53c4c-116">请注意，不能指定某些参数，并省略其他人。</span><span class="sxs-lookup"><span data-stu-id="53c4c-116">Note that you cannot specify some parameters and omit others.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 <span data-ttu-id="53c4c-117">若要省略参数的功能非常有用的情况下，例如定义事件处理程序，其中涉及多个复杂的参数。</span><span class="sxs-lookup"><span data-stu-id="53c4c-117">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="53c4c-118">不使用一些事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="53c4c-118">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="53c4c-119">相反，处理程序直接访问的控件的事件注册时，并忽略这些参数的状态。</span><span class="sxs-lookup"><span data-stu-id="53c4c-119">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="53c4c-120">放松要求的委托，可省略不产生多义性时此类声明中的自变量。</span><span class="sxs-lookup"><span data-stu-id="53c4c-120">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="53c4c-121">在下面的示例中，完全指定的方法`OnClick`可以重写为`RelaxedOnClick`。</span><span class="sxs-lookup"><span data-stu-id="53c4c-121">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="53c4c-122">AddressOf 示例</span><span class="sxs-lookup"><span data-stu-id="53c4c-122">AddressOf Examples</span></span>  
 <span data-ttu-id="53c4c-123">在前面的示例使用 lambda 表达式以便轻松查看类型关系。</span><span class="sxs-lookup"><span data-stu-id="53c4c-123">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="53c4c-124">但是，允许使用的委托分配相同松弛法`AddressOf`， `Handles`，或`AddHandler`。</span><span class="sxs-lookup"><span data-stu-id="53c4c-124">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="53c4c-125">在以下示例中，函数`f1`， `f2`， `f3`，和`f4`都可以分配到`Del1`。</span><span class="sxs-lookup"><span data-stu-id="53c4c-125">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 <span data-ttu-id="53c4c-126">下面的示例是仅当`Option Strict`设置为`Off`。</span><span class="sxs-lookup"><span data-stu-id="53c4c-126">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="53c4c-127">删除函数返回值</span><span class="sxs-lookup"><span data-stu-id="53c4c-127">Dropping Function Returns</span></span>  
 <span data-ttu-id="53c4c-128">宽松的委托转换使您能够分配到函数`Sub`委托，有效地忽略该函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="53c4c-128">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="53c4c-129">但是，不能分配`Sub`到函数委托。</span><span class="sxs-lookup"><span data-stu-id="53c4c-129">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="53c4c-130">在下面的示例中，函数的地址`doubler`分配给`Sub`委托`Del3`。</span><span class="sxs-lookup"><span data-stu-id="53c4c-130">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="53c4c-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="53c4c-131">See also</span></span>

- [<span data-ttu-id="53c4c-132">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="53c4c-132">Lambda Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="53c4c-133">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="53c4c-133">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="53c4c-134">委托</span><span class="sxs-lookup"><span data-stu-id="53c4c-134">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="53c4c-135">如何：将过程传递给 Visual Basic 中的另一个过程</span><span class="sxs-lookup"><span data-stu-id="53c4c-135">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="53c4c-136">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="53c4c-136">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="53c4c-137">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="53c4c-137">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
