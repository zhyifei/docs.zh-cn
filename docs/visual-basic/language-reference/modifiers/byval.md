---
title: ByVal (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: 5e534eac2300327d4c54c5ce93d8b2c6c538e794
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832486"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="8f9f9-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f9f9-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="8f9f9-103">指定的被调用的过程或属性不能更改基础调用代码中的参数的变量的值的方式来传递参数。</span><span class="sxs-lookup"><span data-stu-id="8f9f9-103">Specifies that an argument is passed in such a way that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f9f9-104">备注</span><span class="sxs-lookup"><span data-stu-id="8f9f9-104">Remarks</span></span>  
 <span data-ttu-id="8f9f9-105">`ByVal` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="8f9f9-105">The `ByVal` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="8f9f9-106">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="8f9f9-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="8f9f9-107">Function 语句</span><span class="sxs-lookup"><span data-stu-id="8f9f9-107">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="8f9f9-108">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="8f9f9-108">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="8f9f9-109">Property 语句</span><span class="sxs-lookup"><span data-stu-id="8f9f9-109">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="8f9f9-110">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="8f9f9-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a><span data-ttu-id="8f9f9-111">示例</span><span class="sxs-lookup"><span data-stu-id="8f9f9-111">Example</span></span>  
 <span data-ttu-id="8f9f9-112">下面的示例演示如何将`ByVal`参数传递机制与引用类型自变量。</span><span class="sxs-lookup"><span data-stu-id="8f9f9-112">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="8f9f9-113">在示例中，参数是`c1`，类的实例`Class1`。</span><span class="sxs-lookup"><span data-stu-id="8f9f9-113">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="8f9f9-114">`ByVal` 阻止过程中的代码进行更改的基础值的引用自变量， `c1`，但不会保护的可访问的字段和属性`c1`。</span><span class="sxs-lookup"><span data-stu-id="8f9f9-114">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="8f9f9-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f9f9-115">See also</span></span>

- [<span data-ttu-id="8f9f9-116">关键字</span><span class="sxs-lookup"><span data-stu-id="8f9f9-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="8f9f9-117">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="8f9f9-117">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
