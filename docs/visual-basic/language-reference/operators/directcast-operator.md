---
title: DirectCast 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 03e632bad538f65d010dfaa12f7eb5da15c11091
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979822"
---
# <a name="directcast-operator-visual-basic"></a><span data-ttu-id="c1504-102">DirectCast 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1504-102">DirectCast Operator (Visual Basic)</span></span>
<span data-ttu-id="c1504-103">引入了基于继承或实现的类型转换运算。</span><span class="sxs-lookup"><span data-stu-id="c1504-103">Introduces a type conversion operation based on inheritance or implementation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1504-104">备注</span><span class="sxs-lookup"><span data-stu-id="c1504-104">Remarks</span></span>  
 <span data-ttu-id="c1504-105">`DirectCast` 不使用 Visual Basic 运行时帮助器例程进行转换，以便它可以提供某种程度上更好的性能比`CType`时从数据类型进行来回转换`Object`。</span><span class="sxs-lookup"><span data-stu-id="c1504-105">`DirectCast` does not use the Visual Basic run-time helper routines for conversion, so it can provide somewhat better performance than `CType` when converting to and from data type `Object`.</span></span>  
  
 <span data-ttu-id="c1504-106">您使用`DirectCast`关键字类似于您使用的方式[CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)并且[TryCast 运算符](../../../visual-basic/language-reference/operators/trycast-operator.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="c1504-106">You use the `DirectCast` keyword similar to the way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) keyword.</span></span> <span data-ttu-id="c1504-107">提供作为第一个参数，并将其转换为作为第二个参数的类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="c1504-107">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="c1504-108">`DirectCast` 需要两个参数的数据类型之间的继承或实现关系。</span><span class="sxs-lookup"><span data-stu-id="c1504-108">`DirectCast` requires an inheritance or implementation relationship between the data types of the two arguments.</span></span> <span data-ttu-id="c1504-109">这意味着，必须继承自或实现另一种类型。</span><span class="sxs-lookup"><span data-stu-id="c1504-109">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="c1504-110">错误和失败</span><span class="sxs-lookup"><span data-stu-id="c1504-110">Errors and Failures</span></span>  
 <span data-ttu-id="c1504-111">`DirectCast` 如果它检测到任何继承或实现关系不存在，将生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="c1504-111">`DirectCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="c1504-112">但缺少的编译器错误不会保证成功转换。</span><span class="sxs-lookup"><span data-stu-id="c1504-112">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="c1504-113">如果所需的转换收缩转换，它可能在运行时失败。</span><span class="sxs-lookup"><span data-stu-id="c1504-113">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="c1504-114">如果发生这种情况，则运行时会引发<xref:System.InvalidCastException>错误。</span><span class="sxs-lookup"><span data-stu-id="c1504-114">If this happens, the runtime throws an <xref:System.InvalidCastException> error.</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="c1504-115">转换关键字</span><span class="sxs-lookup"><span data-stu-id="c1504-115">Conversion Keywords</span></span>  
 <span data-ttu-id="c1504-116">类型转换关键字的比较是按如下所示。</span><span class="sxs-lookup"><span data-stu-id="c1504-116">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="c1504-117">关键字</span><span class="sxs-lookup"><span data-stu-id="c1504-117">Keyword</span></span>|<span data-ttu-id="c1504-118">数据类型</span><span class="sxs-lookup"><span data-stu-id="c1504-118">Data types</span></span>|<span data-ttu-id="c1504-119">自变量的关系</span><span class="sxs-lookup"><span data-stu-id="c1504-119">Argument relationship</span></span>|<span data-ttu-id="c1504-120">运行时失败</span><span class="sxs-lookup"><span data-stu-id="c1504-120">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="c1504-121">CType 函数</span><span class="sxs-lookup"><span data-stu-id="c1504-121">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="c1504-122">任何数据类型</span><span class="sxs-lookup"><span data-stu-id="c1504-122">Any data types</span></span>|<span data-ttu-id="c1504-123">必须在两个数据类型之间定义扩大或收缩转换</span><span class="sxs-lookup"><span data-stu-id="c1504-123">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="c1504-124">将引发 <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="c1504-124">Throws <xref:System.InvalidCastException></span></span>|  
|`DirectCast`|<span data-ttu-id="c1504-125">任何数据类型</span><span class="sxs-lookup"><span data-stu-id="c1504-125">Any data types</span></span>|<span data-ttu-id="c1504-126">一种类型必须继承自或实现另一个类型</span><span class="sxs-lookup"><span data-stu-id="c1504-126">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="c1504-127">将引发 <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="c1504-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="c1504-128">TryCast 运算符</span><span class="sxs-lookup"><span data-stu-id="c1504-128">TryCast Operator</span></span>](../../../visual-basic/language-reference/operators/trycast-operator.md)|<span data-ttu-id="c1504-129">仅适用于引用类型</span><span class="sxs-lookup"><span data-stu-id="c1504-129">Reference types only</span></span>|<span data-ttu-id="c1504-130">一种类型必须继承自或实现另一个类型</span><span class="sxs-lookup"><span data-stu-id="c1504-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="c1504-131">返回[执行任何操作](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="c1504-131">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c1504-132">示例</span><span class="sxs-lookup"><span data-stu-id="c1504-132">Example</span></span>  
 <span data-ttu-id="c1504-133">下面的示例演示的两种用法`DirectCast`，一个在运行的时，另一个失败的成功。</span><span class="sxs-lookup"><span data-stu-id="c1504-133">The following example demonstrates two uses of `DirectCast`, one that fails at run time and one that succeeds.</span></span>  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 <span data-ttu-id="c1504-134">在前面的示例中，运行时类型`q`是`Double`。</span><span class="sxs-lookup"><span data-stu-id="c1504-134">In the preceding example, the run-time type of `q` is `Double`.</span></span> <span data-ttu-id="c1504-135">`CType` 会成功，因为`Double`可转换为`Integer`。</span><span class="sxs-lookup"><span data-stu-id="c1504-135">`CType` succeeds because `Double` can be converted to `Integer`.</span></span> <span data-ttu-id="c1504-136">但是，第一个`DirectCast`在运行时失败，因为运行时类型的`Double`具有不到具有继承关系`Integer`，即使已存在的转换。</span><span class="sxs-lookup"><span data-stu-id="c1504-136">However, the first `DirectCast` fails at run time because the run-time type of `Double` has no inheritance relationship with `Integer`, even though a conversion exists.</span></span> <span data-ttu-id="c1504-137">第二个`DirectCast`成功，因为它将从类型转换<xref:System.Windows.Forms.Form>键入<xref:System.Windows.Forms.Control>，从其<xref:System.Windows.Forms.Form>继承。</span><span class="sxs-lookup"><span data-stu-id="c1504-137">The second `DirectCast` succeeds because it converts from type <xref:System.Windows.Forms.Form> to type <xref:System.Windows.Forms.Control>, from which <xref:System.Windows.Forms.Form> inherits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1504-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1504-138">See also</span></span>
- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c1504-139">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="c1504-139">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="c1504-140">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="c1504-140">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
