---
title: TryCast 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: c0eea4565d5040bb00743fc7864ac15b0fccdea9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831587"
---
# <a name="trycast-operator-visual-basic"></a><span data-ttu-id="2652f-102">TryCast 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2652f-102">TryCast Operator (Visual Basic)</span></span>
<span data-ttu-id="2652f-103">引入了不会引发异常的类型转换运算。</span><span class="sxs-lookup"><span data-stu-id="2652f-103">Introduces a type conversion operation that does not throw an exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2652f-104">备注</span><span class="sxs-lookup"><span data-stu-id="2652f-104">Remarks</span></span>  
 <span data-ttu-id="2652f-105">如果尝试执行的转换失败，`CType`并`DirectCast`同时引发<xref:System.InvalidCastException>错误。</span><span class="sxs-lookup"><span data-stu-id="2652f-105">If an attempted conversion fails, `CType` and `DirectCast` both throw an <xref:System.InvalidCastException> error.</span></span> <span data-ttu-id="2652f-106">这会产生负面影响应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="2652f-106">This can adversely affect the performance of your application.</span></span> <span data-ttu-id="2652f-107">`TryCast` 返回[Nothing](../../../visual-basic/language-reference/nothing.md)，以便无需处理可能的异常，只需测试针对返回的结果`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="2652f-107">`TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md), so that instead of having to handle a possible exception, you need only test the returned result against `Nothing`.</span></span>  
  
 <span data-ttu-id="2652f-108">您使用`TryCast`关键字使用的相同方式[CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)并且[DirectCast 运算符](../../../visual-basic/language-reference/operators/directcast-operator.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="2652f-108">You use the `TryCast` keyword the same way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) keyword.</span></span> <span data-ttu-id="2652f-109">提供作为第一个参数，并将其转换为作为第二个参数的类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="2652f-109">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="2652f-110">`TryCast` 只对引用类型，如类和接口执行操作。</span><span class="sxs-lookup"><span data-stu-id="2652f-110">`TryCast` operates only on reference types, such as classes and interfaces.</span></span> <span data-ttu-id="2652f-111">它需要两个类型之间的继承或实现关系。</span><span class="sxs-lookup"><span data-stu-id="2652f-111">It requires an inheritance or implementation relationship between the two types.</span></span> <span data-ttu-id="2652f-112">这意味着，必须继承自或实现另一种类型。</span><span class="sxs-lookup"><span data-stu-id="2652f-112">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="2652f-113">错误和失败</span><span class="sxs-lookup"><span data-stu-id="2652f-113">Errors and Failures</span></span>  
 <span data-ttu-id="2652f-114">`TryCast` 如果它检测到任何继承或实现关系不存在，将生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="2652f-114">`TryCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="2652f-115">但缺少的编译器错误不会保证成功转换。</span><span class="sxs-lookup"><span data-stu-id="2652f-115">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="2652f-116">如果所需的转换收缩转换，它可能在运行时失败。</span><span class="sxs-lookup"><span data-stu-id="2652f-116">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="2652f-117">如果发生这种情况，`TryCast`将返回[Nothing](../../../visual-basic/language-reference/nothing.md)。</span><span class="sxs-lookup"><span data-stu-id="2652f-117">If this happens, `TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="2652f-118">转换关键字</span><span class="sxs-lookup"><span data-stu-id="2652f-118">Conversion Keywords</span></span>  
 <span data-ttu-id="2652f-119">类型转换关键字的比较是按如下所示。</span><span class="sxs-lookup"><span data-stu-id="2652f-119">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="2652f-120">关键字</span><span class="sxs-lookup"><span data-stu-id="2652f-120">Keyword</span></span>|<span data-ttu-id="2652f-121">数据类型</span><span class="sxs-lookup"><span data-stu-id="2652f-121">Data types</span></span>|<span data-ttu-id="2652f-122">自变量的关系</span><span class="sxs-lookup"><span data-stu-id="2652f-122">Argument relationship</span></span>|<span data-ttu-id="2652f-123">运行时失败</span><span class="sxs-lookup"><span data-stu-id="2652f-123">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="2652f-124">CType 函数</span><span class="sxs-lookup"><span data-stu-id="2652f-124">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="2652f-125">任何数据类型</span><span class="sxs-lookup"><span data-stu-id="2652f-125">Any data types</span></span>|<span data-ttu-id="2652f-126">必须在两个数据类型之间定义扩大或收缩转换</span><span class="sxs-lookup"><span data-stu-id="2652f-126">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="2652f-127">将引发 <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="2652f-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="2652f-128">DirectCast 运算符</span><span class="sxs-lookup"><span data-stu-id="2652f-128">DirectCast Operator</span></span>](../../../visual-basic/language-reference/operators/directcast-operator.md)|<span data-ttu-id="2652f-129">任何数据类型</span><span class="sxs-lookup"><span data-stu-id="2652f-129">Any data types</span></span>|<span data-ttu-id="2652f-130">一种类型必须继承自或实现另一个类型</span><span class="sxs-lookup"><span data-stu-id="2652f-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="2652f-131">将引发 <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="2652f-131">Throws <xref:System.InvalidCastException></span></span>|  
|`TryCast`|<span data-ttu-id="2652f-132">仅适用于引用类型</span><span class="sxs-lookup"><span data-stu-id="2652f-132">Reference types only</span></span>|<span data-ttu-id="2652f-133">一种类型必须继承自或实现另一个类型</span><span class="sxs-lookup"><span data-stu-id="2652f-133">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="2652f-134">返回[执行任何操作](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="2652f-134">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2652f-135">示例</span><span class="sxs-lookup"><span data-stu-id="2652f-135">Example</span></span>  
 <span data-ttu-id="2652f-136">下面的示例说明如何使用 `TryCast`。</span><span class="sxs-lookup"><span data-stu-id="2652f-136">The following example shows how to use `TryCast`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="2652f-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="2652f-137">See also</span></span>

- [<span data-ttu-id="2652f-138">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="2652f-138">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="2652f-139">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="2652f-139">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
