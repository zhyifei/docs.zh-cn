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
ms.openlocfilehash: 076289ff303dce58f036d6c7cb1505b151da19f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602978"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="d32b9-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d32b9-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="d32b9-103">指定的参数传递的调用的过程或属性不能更改基础中调用代码的自变量的变量的值的方式。</span><span class="sxs-lookup"><span data-stu-id="d32b9-103">Specifies that an argument is passed in such a way that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d32b9-104">备注</span><span class="sxs-lookup"><span data-stu-id="d32b9-104">Remarks</span></span>  
 <span data-ttu-id="d32b9-105">`ByVal` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="d32b9-105">The `ByVal` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="d32b9-106">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="d32b9-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="d32b9-107">Function 语句</span><span class="sxs-lookup"><span data-stu-id="d32b9-107">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="d32b9-108">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="d32b9-108">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="d32b9-109">Property 语句</span><span class="sxs-lookup"><span data-stu-id="d32b9-109">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="d32b9-110">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="d32b9-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a><span data-ttu-id="d32b9-111">示例</span><span class="sxs-lookup"><span data-stu-id="d32b9-111">Example</span></span>  
 <span data-ttu-id="d32b9-112">下面的示例演示了利用`ByVal`参数传递使用引用类型参数的机制。</span><span class="sxs-lookup"><span data-stu-id="d32b9-112">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="d32b9-113">在本示例中，参数是`c1`，类的实例`Class1`。</span><span class="sxs-lookup"><span data-stu-id="d32b9-113">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="d32b9-114">`ByVal` 防止过程中的代码更改基础值的引用自变量， `c1`，但不会保护的可访问的字段和属性`c1`。</span><span class="sxs-lookup"><span data-stu-id="d32b9-114">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#10](../../../visual-basic/language-reference/codesnippet/VisualBasic/byval_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d32b9-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d32b9-115">See Also</span></span>  
 [<span data-ttu-id="d32b9-116">关键字</span><span class="sxs-lookup"><span data-stu-id="d32b9-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="d32b9-117">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="d32b9-117">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
