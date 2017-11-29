---
title: "DirectCast 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords: DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d9b81abea364e328b831ee98c3b847161c3f7dd3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="directcast-operator-visual-basic"></a><span data-ttu-id="c1bd6-102">DirectCast 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1bd6-102">DirectCast Operator (Visual Basic)</span></span>
<span data-ttu-id="c1bd6-103">引入了基于继承或实现的类型转换操作。</span><span class="sxs-lookup"><span data-stu-id="c1bd6-103">Introduces a type conversion operation based on inheritance or implementation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1bd6-104">备注</span><span class="sxs-lookup"><span data-stu-id="c1bd6-104">Remarks</span></span>  
 <span data-ttu-id="c1bd6-105">`DirectCast`不使用 Visual Basic 运行时帮助器例程进行转换，因此它可以提供某种程度上更好的性能比`CType`转换到和从数据类型时`Object`。</span><span class="sxs-lookup"><span data-stu-id="c1bd6-105">`DirectCast` does not use the Visual Basic run-time helper routines for conversion, so it can provide somewhat better performance than `CType` when converting to and from data type `Object`.</span></span>  
  
 <span data-ttu-id="c1bd6-106">你使用`DirectCast`关键字类似于你使用的方式[CType 函数](../../../visual-basic/language-reference/functions/ctype-function.md)和[TryCast 运算符](../../../visual-basic/language-reference/operators/trycast-operator.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="c1bd6-106">You use the `DirectCast` keyword similar to the way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) keyword.</span></span> <span data-ttu-id="c1bd6-107">提供作为第一个参数，并将它转换为第二个参数的类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="c1bd6-107">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="c1bd6-108">`DirectCast`需要两个自变量的数据类型之间的继承或实现关系。</span><span class="sxs-lookup"><span data-stu-id="c1bd6-108">`DirectCast` requires an inheritance or implementation relationship between the data types of the two arguments.</span></span> <span data-ttu-id="c1bd6-109">这意味着一个类型必须继承自或实现其他。</span><span class="sxs-lookup"><span data-stu-id="c1bd6-109">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="c1bd6-110">错误和失败</span><span class="sxs-lookup"><span data-stu-id="c1bd6-110">Errors and Failures</span></span>  
 <span data-ttu-id="c1bd6-111">`DirectCast`如果它检测到没有继承或实现关系不存在，请生成一个编译器错误。</span><span class="sxs-lookup"><span data-stu-id="c1bd6-111">`DirectCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="c1bd6-112">但是，编译器错误缺乏不保证成功的转换。</span><span class="sxs-lookup"><span data-stu-id="c1bd6-112">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="c1bd6-113">如果所需的转换收缩转换，则它可能在运行时失败。</span><span class="sxs-lookup"><span data-stu-id="c1bd6-113">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="c1bd6-114">如果发生这种情况，则运行时会引发<xref:System.InvalidCastException>错误。</span><span class="sxs-lookup"><span data-stu-id="c1bd6-114">If this happens, the runtime throws an <xref:System.InvalidCastException> error.</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="c1bd6-115">转换关键字</span><span class="sxs-lookup"><span data-stu-id="c1bd6-115">Conversion Keywords</span></span>  
 <span data-ttu-id="c1bd6-116">类型转换关键字的比较是，如下所示。</span><span class="sxs-lookup"><span data-stu-id="c1bd6-116">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="c1bd6-117">关键字</span><span class="sxs-lookup"><span data-stu-id="c1bd6-117">Keyword</span></span>|<span data-ttu-id="c1bd6-118">数据类型</span><span class="sxs-lookup"><span data-stu-id="c1bd6-118">Data types</span></span>|<span data-ttu-id="c1bd6-119">自变量关系</span><span class="sxs-lookup"><span data-stu-id="c1bd6-119">Argument relationship</span></span>|<span data-ttu-id="c1bd6-120">运行时失败</span><span class="sxs-lookup"><span data-stu-id="c1bd6-120">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="c1bd6-121">CType 函数</span><span class="sxs-lookup"><span data-stu-id="c1bd6-121">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="c1bd6-122">任何数据类型</span><span class="sxs-lookup"><span data-stu-id="c1bd6-122">Any data types</span></span>|<span data-ttu-id="c1bd6-123">两个数据类型之间必须定义扩大或收缩转换</span><span class="sxs-lookup"><span data-stu-id="c1bd6-123">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="c1bd6-124">引发<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="c1bd6-124">Throws <xref:System.InvalidCastException></span></span>|  
|`DirectCast`|<span data-ttu-id="c1bd6-125">任何数据类型</span><span class="sxs-lookup"><span data-stu-id="c1bd6-125">Any data types</span></span>|<span data-ttu-id="c1bd6-126">一个类型必须继承自或实现其他类型</span><span class="sxs-lookup"><span data-stu-id="c1bd6-126">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="c1bd6-127">引发<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="c1bd6-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="c1bd6-128">TryCast 运算符</span><span class="sxs-lookup"><span data-stu-id="c1bd6-128">TryCast Operator</span></span>](../../../visual-basic/language-reference/operators/trycast-operator.md)|<span data-ttu-id="c1bd6-129">仅适用于引用类型</span><span class="sxs-lookup"><span data-stu-id="c1bd6-129">Reference types only</span></span>|<span data-ttu-id="c1bd6-130">一个类型必须继承自或实现其他类型</span><span class="sxs-lookup"><span data-stu-id="c1bd6-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="c1bd6-131">返回[执行任何操作](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="c1bd6-131">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c1bd6-132">示例</span><span class="sxs-lookup"><span data-stu-id="c1bd6-132">Example</span></span>  
 <span data-ttu-id="c1bd6-133">下面的示例演示两种含义`DirectCast`，未在运行的时，另一个成功。</span><span class="sxs-lookup"><span data-stu-id="c1bd6-133">The following example demonstrates two uses of `DirectCast`, one that fails at run time and one that succeeds.</span></span>  
  
 [!code-vb[VbVbalrKeywords#1](../../../visual-basic/language-reference/codesnippet/VisualBasic/directcast-operator_1.vb)]  
  
 <span data-ttu-id="c1bd6-134">在前面的示例中，运行时类型`q`是`Double`。</span><span class="sxs-lookup"><span data-stu-id="c1bd6-134">In the preceding example, the run-time type of `q` is `Double`.</span></span> <span data-ttu-id="c1bd6-135">`CType`将成功，因为`Double`可以转换为`Integer`。</span><span class="sxs-lookup"><span data-stu-id="c1bd6-135">`CType` succeeds because `Double` can be converted to `Integer`.</span></span> <span data-ttu-id="c1bd6-136">但是，第一个`DirectCast`在运行时失败，因为运行时类型的`Double`不具有与任何继承关系`Integer`，即使已存在的转换。</span><span class="sxs-lookup"><span data-stu-id="c1bd6-136">However, the first `DirectCast` fails at run time because the run-time type of `Double` has no inheritance relationship with `Integer`, even though a conversion exists.</span></span> <span data-ttu-id="c1bd6-137">第二个`DirectCast`会成功，因为它将从类型转换<xref:System.Windows.Forms.Form>类型<xref:System.Windows.Forms.Control>，从中<xref:System.Windows.Forms.Form>继承。</span><span class="sxs-lookup"><span data-stu-id="c1bd6-137">The second `DirectCast` succeeds because it converts from type <xref:System.Windows.Forms.Form> to type <xref:System.Windows.Forms.Control>, from which <xref:System.Windows.Forms.Form> inherits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1bd6-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1bd6-138">See Also</span></span>  
 <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="c1bd6-139">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="c1bd6-139">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="c1bd6-140">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="c1bd6-140">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
