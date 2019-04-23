---
title: IsTrue 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 6c5ec6d953d174b525dee7ad3034d2d01ae4950f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344944"
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="51c21-102">IsTrue 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51c21-102">IsTrue Operator (Visual Basic)</span></span>
<span data-ttu-id="51c21-103">确定表达式是否为`True`。</span><span class="sxs-lookup"><span data-stu-id="51c21-103">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="51c21-104">不能调用`IsTrue`显式中你的代码，而 Visual Basic 编译器可以使用它来生成代码从`OrElse`子句。</span><span class="sxs-lookup"><span data-stu-id="51c21-104">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="51c21-105">如果你定义类或结构，然后使用在该类型的变量`OrElse`子句，则必须定义`IsTrue`类或结构上。</span><span class="sxs-lookup"><span data-stu-id="51c21-105">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="51c21-106">编译器会考虑`IsTrue`并`IsFalse`作为运算符*匹配对*。</span><span class="sxs-lookup"><span data-stu-id="51c21-106">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="51c21-107">这意味着，如果其中一个定义，您还必须定义另一个。</span><span class="sxs-lookup"><span data-stu-id="51c21-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="51c21-108">为 true 时的编译器使用</span><span class="sxs-lookup"><span data-stu-id="51c21-108">Compiler Use of IsTrue</span></span>  
 <span data-ttu-id="51c21-109">如果已定义类或结构，可以使用中该类型的变量`For`， `If`， `Else If`，或`While`语句，或在`When`子句。</span><span class="sxs-lookup"><span data-stu-id="51c21-109">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="51c21-110">如果这样做，则编译器会要求将转换到类型的运算符`Boolean`值以便可以测试条件。</span><span class="sxs-lookup"><span data-stu-id="51c21-110">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="51c21-111">它会搜索合适的运算符按以下顺序：</span><span class="sxs-lookup"><span data-stu-id="51c21-111">It searches for a suitable operator in the following order:</span></span>  
  
1. <span data-ttu-id="51c21-112">在类或结构的扩大转换运算符`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="51c21-112">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2. <span data-ttu-id="51c21-113">在类或结构的扩大转换运算符`Boolean?`。</span><span class="sxs-lookup"><span data-stu-id="51c21-113">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3. <span data-ttu-id="51c21-114">`IsTrue`运算符在类或结构上的。</span><span class="sxs-lookup"><span data-stu-id="51c21-114">The `IsTrue` operator on your class or structure.</span></span>  
  
4. <span data-ttu-id="51c21-115">收缩转换到`Boolean?`，并不涉及从转换`Boolean`到`Boolean?`。</span><span class="sxs-lookup"><span data-stu-id="51c21-115">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5. <span data-ttu-id="51c21-116">在类或结构的收缩转换运算符`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="51c21-116">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="51c21-117">如果您未定义任何转换为`Boolean`或`IsTrue`运算符，编译器会引发错误。</span><span class="sxs-lookup"><span data-stu-id="51c21-117">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51c21-118">`IsTrue`运算符可以被*重载*，这意味着，某个类或结构可以重新定义其行为时，其操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="51c21-118">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="51c21-119">如果你的代码对此类的类或结构使用此运算符，请确保了解其被重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="51c21-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="51c21-120">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="51c21-120">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="51c21-121">示例</span><span class="sxs-lookup"><span data-stu-id="51c21-121">Example</span></span>  
 <span data-ttu-id="51c21-122">下面的代码示例定义一个结构，其中包含定义大纲`IsFalse`和`IsTrue`运算符。</span><span class="sxs-lookup"><span data-stu-id="51c21-122">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="51c21-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="51c21-123">See also</span></span>

- [<span data-ttu-id="51c21-124">IsFalse 运算符</span><span class="sxs-lookup"><span data-stu-id="51c21-124">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="51c21-125">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="51c21-125">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="51c21-126">OrElse 运算符</span><span class="sxs-lookup"><span data-stu-id="51c21-126">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
