---
title: 如何：测试两个对象是否相同 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: dbb268175d197e7b931af45a98f3a273c593e5a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864372"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="b1fa8-102">如何：测试两个对象是否相同 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1fa8-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="b1fa8-103">如果您有两个引用的对象的变量，可以使用`Is`或`IsNot`运算符，或两者，以确定它们是否引用同一个实例。</span><span class="sxs-lookup"><span data-stu-id="b1fa8-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="b1fa8-104">若要测试两个对象是否相同</span><span class="sxs-lookup"><span data-stu-id="b1fa8-104">To test whether two objects are the same</span></span>  
  
-   <span data-ttu-id="b1fa8-105">使用[Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)或[IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)与两个变量作为操作数。</span><span class="sxs-lookup"><span data-stu-id="b1fa8-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 <span data-ttu-id="b1fa8-106">您可能想要执行的具体操作取决于两个对象是否引用相同的实例。</span><span class="sxs-lookup"><span data-stu-id="b1fa8-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="b1fa8-107">前面的示例进行比较的控件`c`窗体上的活动控件针对`f`。</span><span class="sxs-lookup"><span data-stu-id="b1fa8-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="b1fa8-108">如果没有活动的控件，或者如果没有一个但这不是相同的控件实例作为`c`，则`If`语句将失败，该过程将返回而不会进一步处理。</span><span class="sxs-lookup"><span data-stu-id="b1fa8-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="b1fa8-109">无论是使用`Is`或`IsNot`是对您的个人方便起见。</span><span class="sxs-lookup"><span data-stu-id="b1fa8-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="b1fa8-110">一个可能更易读比另一个给定表达式中。</span><span class="sxs-lookup"><span data-stu-id="b1fa8-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1fa8-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1fa8-111">See also</span></span>

- [<span data-ttu-id="b1fa8-112">在 Visual Basic 中的比较运算符</span><span class="sxs-lookup"><span data-stu-id="b1fa8-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
