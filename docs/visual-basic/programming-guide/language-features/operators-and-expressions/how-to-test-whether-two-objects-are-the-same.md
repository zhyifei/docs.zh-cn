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
ms.openlocfilehash: 005c91e6f4ec556a7e1bf255b47c8276a5d3d185
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647600"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="dd021-102">如何：测试两个对象是否相同 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd021-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="dd021-103">如果你有两个引用对象的变量，可以使用`Is`或`IsNot`运算符，或两者，来确定它们是否引用相同实例。</span><span class="sxs-lookup"><span data-stu-id="dd021-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="dd021-104">若要测试两个对象是否相同</span><span class="sxs-lookup"><span data-stu-id="dd021-104">To test whether two objects are the same</span></span>  
  
-   <span data-ttu-id="dd021-105">使用[Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)或[IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)与两个变量作为操作数。</span><span class="sxs-lookup"><span data-stu-id="dd021-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-test-whether-two-objects-are-the-same_1.vb)]  
  
 <span data-ttu-id="dd021-106">你可能想要执行某些操作具体取决于两个对象是否引用相同实例。</span><span class="sxs-lookup"><span data-stu-id="dd021-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="dd021-107">前面的示例比较控件`c`针对窗体上的活动控件`f`。</span><span class="sxs-lookup"><span data-stu-id="dd021-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="dd021-108">如果没有活动的控件，或如果没有一个但这不是相同的控件实例`c`，则`If`语句将失败并且过程将返回而不会进一步处理。</span><span class="sxs-lookup"><span data-stu-id="dd021-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="dd021-109">是否使用`Is`或`IsNot`个人方便你只是。</span><span class="sxs-lookup"><span data-stu-id="dd021-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="dd021-110">一个可能更易读比另一个给定表达式中。</span><span class="sxs-lookup"><span data-stu-id="dd021-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd021-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd021-111">See Also</span></span>  
 [<span data-ttu-id="dd021-112">在 Visual Basic 中的比较运算符</span><span class="sxs-lookup"><span data-stu-id="dd021-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
