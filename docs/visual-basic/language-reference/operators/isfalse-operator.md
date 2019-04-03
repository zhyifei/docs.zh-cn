---
title: IsFalse 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 9f25c406038486224c2c4708c86ef86889c44c15
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818483"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="ba91e-102">IsFalse 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ba91e-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="ba91e-103">确定表达式是否为`False`。</span><span class="sxs-lookup"><span data-stu-id="ba91e-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="ba91e-104">不能调用`IsFalse`显式中你的代码，而 Visual Basic 编译器可以使用它来生成代码从`AndAlso`子句。</span><span class="sxs-lookup"><span data-stu-id="ba91e-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="ba91e-105">如果你定义类或结构，然后使用在该类型的变量`AndAlso`子句，则必须定义`IsFalse`类或结构上。</span><span class="sxs-lookup"><span data-stu-id="ba91e-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="ba91e-106">编译器会考虑`IsFalse`并`IsTrue`作为运算符*匹配对*。</span><span class="sxs-lookup"><span data-stu-id="ba91e-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="ba91e-107">这意味着，如果其中一个定义，您还必须定义另一个。</span><span class="sxs-lookup"><span data-stu-id="ba91e-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba91e-108">`IsFalse`运算符可以被*重载*，这意味着，某个类或结构可以重新定义其行为时，其操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="ba91e-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="ba91e-109">如果你的代码对此类的类或结构使用此运算符，请确保了解其被重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="ba91e-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="ba91e-110">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="ba91e-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba91e-111">示例</span><span class="sxs-lookup"><span data-stu-id="ba91e-111">Example</span></span>  
 <span data-ttu-id="ba91e-112">下面的代码示例定义一个结构，其中包含定义大纲`IsFalse`和`IsTrue`运算符。</span><span class="sxs-lookup"><span data-stu-id="ba91e-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="ba91e-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba91e-113">See also</span></span>

- [<span data-ttu-id="ba91e-114">IsTrue 运算符</span><span class="sxs-lookup"><span data-stu-id="ba91e-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="ba91e-115">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="ba91e-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="ba91e-116">AndAlso 运算符</span><span class="sxs-lookup"><span data-stu-id="ba91e-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
