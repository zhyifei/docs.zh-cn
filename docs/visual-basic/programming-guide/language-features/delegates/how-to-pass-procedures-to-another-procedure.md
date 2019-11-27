---
title: 如何：将过程传递给另一过程
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 300489935ce54d78b989d09211a7f6ba95c2f514
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345250"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="539e7-102">如何：在 Visual Basic 中将过程传递给另一过程</span><span class="sxs-lookup"><span data-stu-id="539e7-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="539e7-103">此示例演示如何使用委托将过程传递给另一个过程。</span><span class="sxs-lookup"><span data-stu-id="539e7-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="539e7-104">委托是一种类型，您可以像在 Visual Basic 中那样使用任何其他类型。</span><span class="sxs-lookup"><span data-stu-id="539e7-104">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="539e7-105">当应用于过程名称时，`AddressOf` 运算符返回一个委托对象。</span><span class="sxs-lookup"><span data-stu-id="539e7-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="539e7-106">此示例包含一个带有委托参数的过程，该参数可以引用使用 `AddressOf` 运算符获得的另一个过程。</span><span class="sxs-lookup"><span data-stu-id="539e7-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="539e7-107">创建委托和匹配过程</span><span class="sxs-lookup"><span data-stu-id="539e7-107">Create the delegate and matching procedures</span></span>  
  
1. <span data-ttu-id="539e7-108">创建一个名为 `MathOperator`的委托。</span><span class="sxs-lookup"><span data-stu-id="539e7-108">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. <span data-ttu-id="539e7-109">创建一个名为 `AddNumbers` 的过程，该过程的参数和返回值与 `MathOperator`的参数和返回值匹配，以便签名匹配。</span><span class="sxs-lookup"><span data-stu-id="539e7-109">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. <span data-ttu-id="539e7-110">使用与 `MathOperator`匹配的签名创建名为 `SubtractNumbers` 的过程。</span><span class="sxs-lookup"><span data-stu-id="539e7-110">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. <span data-ttu-id="539e7-111">创建一个名为 `DelegateTest` 的过程，该过程采用委托作为参数。</span><span class="sxs-lookup"><span data-stu-id="539e7-111">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="539e7-112">此过程可以接受对 `AddNumbers` 或 `SubtractNumbers`的引用，因为它们的签名与 `MathOperator` 签名相匹配。</span><span class="sxs-lookup"><span data-stu-id="539e7-112">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. <span data-ttu-id="539e7-113">创建一个名为 `Test` 的过程，该过程使用 `AddNumbers` 作为参数的委托调用一次 `DelegateTest`，并再次使用 `SubtractNumbers` 的委托作为参数。</span><span class="sxs-lookup"><span data-stu-id="539e7-113">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     <span data-ttu-id="539e7-114">调用 `Test` 时，它首先显示对 `5` 和 `3`（为8） `AddNumbers` 的结果。</span><span class="sxs-lookup"><span data-stu-id="539e7-114">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="539e7-115">然后，将显示 `SubtractNumbers` 作用于 `9` 和 `3` 的结果，即6。</span><span class="sxs-lookup"><span data-stu-id="539e7-115">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="539e7-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="539e7-116">See also</span></span>

- [<span data-ttu-id="539e7-117">委托</span><span class="sxs-lookup"><span data-stu-id="539e7-117">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="539e7-118">AddressOf 运算符</span><span class="sxs-lookup"><span data-stu-id="539e7-118">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="539e7-119">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="539e7-119">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="539e7-120">如何：调用委托方法</span><span class="sxs-lookup"><span data-stu-id="539e7-120">How to: Invoke a Delegate Method</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
