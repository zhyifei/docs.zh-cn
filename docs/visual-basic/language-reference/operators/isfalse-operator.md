---
title: IsFalse 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: e84b2162eb0763725f05bc52d5c4223d7c430b81
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600040"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="a7efa-102">IsFalse 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7efa-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="a7efa-103">确定表达式是否为`False`。</span><span class="sxs-lookup"><span data-stu-id="a7efa-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="a7efa-104">不能调用`IsFalse`显式中你的代码，而 Visual Basic 编译器可以用它来生成代码从`AndAlso`子句。</span><span class="sxs-lookup"><span data-stu-id="a7efa-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="a7efa-105">如果你定义的类或结构，然后使用在该类型的变量的`AndAlso`子句中，你必须定义`IsFalse`在类或结构上。</span><span class="sxs-lookup"><span data-stu-id="a7efa-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="a7efa-106">编译器认为`IsFalse`和`IsTrue`与运算符*匹配对*。</span><span class="sxs-lookup"><span data-stu-id="a7efa-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="a7efa-107">这意味着，如果其中一个定义，你必须还定义另一个。</span><span class="sxs-lookup"><span data-stu-id="a7efa-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7efa-108">`IsFalse`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，其操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="a7efa-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="a7efa-109">如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="a7efa-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a7efa-110">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="a7efa-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7efa-111">示例</span><span class="sxs-lookup"><span data-stu-id="a7efa-111">Example</span></span>  
 <span data-ttu-id="a7efa-112">下面的代码示例定义的结构，其中包含定义大纲`IsFalse`和`IsTrue`运算符。</span><span class="sxs-lookup"><span data-stu-id="a7efa-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isfalse-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a7efa-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7efa-113">See Also</span></span>  
 [<span data-ttu-id="a7efa-114">IsTrue 运算符</span><span class="sxs-lookup"><span data-stu-id="a7efa-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [<span data-ttu-id="a7efa-115">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="a7efa-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="a7efa-116">AndAlso 运算符</span><span class="sxs-lookup"><span data-stu-id="a7efa-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
