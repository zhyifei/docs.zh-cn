---
title: IsFalse 运算符
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 51b7bfb2cf5301a39818e6566b408ee0677689f2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349519"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="a938b-102">IsFalse 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a938b-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="a938b-103">确定表达式是否 `False`。</span><span class="sxs-lookup"><span data-stu-id="a938b-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="a938b-104">你不能在代码中显式调用 `IsFalse`，但 Visual Basic 编译器可以使用它从 `AndAlso` 子句生成代码。</span><span class="sxs-lookup"><span data-stu-id="a938b-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="a938b-105">如果定义类或结构，然后在 `AndAlso` 子句中使用该类型的变量，则必须在该类或结构上定义 `IsFalse`。</span><span class="sxs-lookup"><span data-stu-id="a938b-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="a938b-106">编译器将 `IsFalse` 和 `IsTrue` 运算符视为*匹配对*。</span><span class="sxs-lookup"><span data-stu-id="a938b-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="a938b-107">这意味着，如果定义其中一个类型，则还必须定义另一个。</span><span class="sxs-lookup"><span data-stu-id="a938b-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a938b-108">可以*重载*`IsFalse` 运算符，这意味着当类或结构的操作数具有该类或结构的类型时，它可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="a938b-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="a938b-109">如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="a938b-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a938b-110">有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="a938b-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a938b-111">示例</span><span class="sxs-lookup"><span data-stu-id="a938b-111">Example</span></span>  
 <span data-ttu-id="a938b-112">下面的代码示例定义了结构的轮廓，该结构包含 `IsFalse` 和 `IsTrue` 运算符的定义。</span><span class="sxs-lookup"><span data-stu-id="a938b-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="a938b-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a938b-113">See also</span></span>

- [<span data-ttu-id="a938b-114">IsTrue 运算符</span><span class="sxs-lookup"><span data-stu-id="a938b-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="a938b-115">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="a938b-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="a938b-116">AndAlso 运算符</span><span class="sxs-lookup"><span data-stu-id="a938b-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
