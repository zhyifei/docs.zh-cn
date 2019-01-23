---
title: 如何：将过程传递给 Visual Basic 中的另一个过程
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: cf5a8447cbedcd8071da98ac6763ff06eb608199
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506753"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="e14be-102">如何：将过程传递给 Visual Basic 中的另一个过程</span><span class="sxs-lookup"><span data-stu-id="e14be-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="e14be-103">此示例演示如何使用委托来将过程传递给另一个过程。</span><span class="sxs-lookup"><span data-stu-id="e14be-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="e14be-104">委托是可以使用类似于在 Visual Basic 中的任何其他类型的类型。</span><span class="sxs-lookup"><span data-stu-id="e14be-104">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="e14be-105">`AddressOf`运算符返回的委托对象时应用于过程名称。</span><span class="sxs-lookup"><span data-stu-id="e14be-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="e14be-106">此示例中有一个具有一个委托参数，可能需要对另一个过程，获得的引用过程`AddressOf`运算符。</span><span class="sxs-lookup"><span data-stu-id="e14be-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="e14be-107">创建委托和匹配过程</span><span class="sxs-lookup"><span data-stu-id="e14be-107">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="e14be-108">创建名为的委托`MathOperator`。</span><span class="sxs-lookup"><span data-stu-id="e14be-108">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  <span data-ttu-id="e14be-109">创建一个名为过程`AddNumbers`使用参数和返回值相匹配的`MathOperator`，以便签名匹配。</span><span class="sxs-lookup"><span data-stu-id="e14be-109">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  <span data-ttu-id="e14be-110">创建一个名为过程`SubtractNumbers`相匹配的签名与`MathOperator`。</span><span class="sxs-lookup"><span data-stu-id="e14be-110">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  <span data-ttu-id="e14be-111">创建一个名为过程`DelegateTest`采用委托作为参数。</span><span class="sxs-lookup"><span data-stu-id="e14be-111">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="e14be-112">此过程可以接受的引用`AddNumbers`或`SubtractNumbers`，因为它们的签名匹配`MathOperator`签名。</span><span class="sxs-lookup"><span data-stu-id="e14be-112">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  <span data-ttu-id="e14be-113">创建一个名为过程`Test`的调用`DelegateTest`一次使用的委托`AddNumbers`作为参数，并再次使用的委托`SubtractNumbers`作为参数。</span><span class="sxs-lookup"><span data-stu-id="e14be-113">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     <span data-ttu-id="e14be-114">当`Test`是其调用，首先显示的结果`AddNumbers`作用于`5`和`3`，也就是 8。</span><span class="sxs-lookup"><span data-stu-id="e14be-114">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="e14be-115">然后的结果`SubtractNumbers`对操作`9`和`3`显示，则其为 6。</span><span class="sxs-lookup"><span data-stu-id="e14be-115">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e14be-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e14be-116">See also</span></span>
- [<span data-ttu-id="e14be-117">委托</span><span class="sxs-lookup"><span data-stu-id="e14be-117">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="e14be-118">AddressOf 运算符</span><span class="sxs-lookup"><span data-stu-id="e14be-118">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="e14be-119">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="e14be-119">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="e14be-120">如何：调用委托方法</span><span class="sxs-lookup"><span data-stu-id="e14be-120">How to: Invoke a Delegate Method</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
