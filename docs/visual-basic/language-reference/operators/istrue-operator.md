---
title: "IsTrue 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c0d261186ce68f06cec95251e815248a189f6da5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="1f016-102">IsTrue 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f016-102">IsTrue Operator (Visual Basic)</span></span>
<span data-ttu-id="1f016-103">确定表达式是否为`True`。</span><span class="sxs-lookup"><span data-stu-id="1f016-103">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="1f016-104">不能调用`IsTrue`显式中你的代码，而 Visual Basic 编译器可以用它来生成代码从`OrElse`子句。</span><span class="sxs-lookup"><span data-stu-id="1f016-104">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="1f016-105">如果你定义的类或结构，然后使用在该类型的变量的`OrElse`子句中，你必须定义`IsTrue`在类或结构上。</span><span class="sxs-lookup"><span data-stu-id="1f016-105">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="1f016-106">编译器认为`IsTrue`和`IsFalse`与运算符*匹配对*。</span><span class="sxs-lookup"><span data-stu-id="1f016-106">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="1f016-107">这意味着，如果其中一个定义，你必须还定义另一个。</span><span class="sxs-lookup"><span data-stu-id="1f016-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="1f016-108">编译器使用的 IsTrue</span><span class="sxs-lookup"><span data-stu-id="1f016-108">Compiler Use of IsTrue</span></span>  
 <span data-ttu-id="1f016-109">当你已定义类或结构时，可以使用在该类型的变量`For`， `If`， `Else``If`，或`While`语句，或在`When`子句。</span><span class="sxs-lookup"><span data-stu-id="1f016-109">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else``If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="1f016-110">如果这样做，则编译器会要求将转换到你的类型的运算符`Boolean`值以便可以测试条件。</span><span class="sxs-lookup"><span data-stu-id="1f016-110">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="1f016-111">它搜索合适的运算符按以下顺序：</span><span class="sxs-lookup"><span data-stu-id="1f016-111">It searches for a suitable operator in the following order:</span></span>  
  
1.  <span data-ttu-id="1f016-112">从类或结构的扩大转换运算符`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="1f016-112">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2.  <span data-ttu-id="1f016-113">从类或结构的扩大转换运算符`Boolean?`。</span><span class="sxs-lookup"><span data-stu-id="1f016-113">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3.  <span data-ttu-id="1f016-114">`IsTrue`在类或结构上的运算符。</span><span class="sxs-lookup"><span data-stu-id="1f016-114">The `IsTrue` operator on your class or structure.</span></span>  
  
4.  <span data-ttu-id="1f016-115">收缩转换为`Boolean?`不涉及从转换`Boolean`到`Boolean?`。</span><span class="sxs-lookup"><span data-stu-id="1f016-115">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5.  <span data-ttu-id="1f016-116">从类或结构的收缩转换运算符`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="1f016-116">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="1f016-117">如果你未定义任何转换为`Boolean`或`IsTrue`运算符，编译器将引发错误。</span><span class="sxs-lookup"><span data-stu-id="1f016-117">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f016-118">`IsTrue`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，其操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="1f016-118">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="1f016-119">如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="1f016-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="1f016-120">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="1f016-120">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f016-121">示例</span><span class="sxs-lookup"><span data-stu-id="1f016-121">Example</span></span>  
 <span data-ttu-id="1f016-122">下面的代码示例定义的结构，其中包含定义大纲`IsFalse`和`IsTrue`运算符。</span><span class="sxs-lookup"><span data-stu-id="1f016-122">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/istrue-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1f016-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f016-123">See Also</span></span>  
 [<span data-ttu-id="1f016-124">IsFalse 运算符</span><span class="sxs-lookup"><span data-stu-id="1f016-124">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [<span data-ttu-id="1f016-125">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="1f016-125">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="1f016-126">OrElse 运算符</span><span class="sxs-lookup"><span data-stu-id="1f016-126">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
