---
title: 如何：声明具有混合访问级别的属性 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
ms.openlocfilehash: 8d25086fe6f8b5f5300006466ef49782cb065edf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a><span data-ttu-id="c95ca-102">如何：声明具有混合访问级别的属性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c95ca-102">How to: Declare a Property with Mixed Access Levels (Visual Basic)</span></span>
<span data-ttu-id="c95ca-103">如果你想`Get`和`Set`要具有不同的访问级别的属性的过程，你可以使用中的更多的权限级别`Property`语句和中限制性更强的级别`Get`或`Set`语句。</span><span class="sxs-lookup"><span data-stu-id="c95ca-103">If you want the `Get` and `Set` procedures on a property to have different access levels, you can use the more permissive level in the `Property` statement and the more restrictive level in either the `Get` or `Set` statement.</span></span> <span data-ttu-id="c95ca-104">当你想要能够获取属性的值的代码的某些部分和某些其他部分的代码将无法更改的值时，可以在属性上使用混合的访问级别。</span><span class="sxs-lookup"><span data-stu-id="c95ca-104">You use mixed access levels on a property when you want certain parts of the code to be able to get the property's value, and certain other parts of the code to be able to change the value.</span></span>  
  
 <span data-ttu-id="c95ca-105">有关访问级别的详细信息，请参阅[访问 Visual Basic 中的级别](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="c95ca-105">For more information on access levels, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a><span data-ttu-id="c95ca-106">若要声明具有混合的访问级别的属性</span><span class="sxs-lookup"><span data-stu-id="c95ca-106">To declare a property with mixed access levels</span></span>  
  
1.  <span data-ttu-id="c95ca-107">将该属性声明以常规方式，并指定限制性较弱的访问级别 (如`Public`) 中`Property`语句。</span><span class="sxs-lookup"><span data-stu-id="c95ca-107">Declare the property in the normal way, and specify the less restrictive access level (such as `Public`) in the `Property` statement.</span></span>  
  
2.  <span data-ttu-id="c95ca-108">声明是`Get`或`Set`指定限制性更强的访问级别的过程 (如`Friend`)。</span><span class="sxs-lookup"><span data-stu-id="c95ca-108">Declare either the `Get` or the `Set` procedure specifying the more restrictive access level (such as `Friend`).</span></span>  
  
3.  <span data-ttu-id="c95ca-109">不要在另一个属性过程指定访问级别。</span><span class="sxs-lookup"><span data-stu-id="c95ca-109">Do not specify an access level on the other property procedure.</span></span> <span data-ttu-id="c95ca-110">它假定中声明的访问级别`Property`语句。</span><span class="sxs-lookup"><span data-stu-id="c95ca-110">It assumes the access level declared in the `Property` statement.</span></span> <span data-ttu-id="c95ca-111">你可以限制仅其中一个属性过程上的访问。</span><span class="sxs-lookup"><span data-stu-id="c95ca-111">You can restrict access on only one of the property procedures.</span></span>  
  
     [!code-vb[VbVbcnProcedures#10](./codesnippet/VisualBasic/how-to-declare-a-property-with-mixed-access-levels_1.vb)]  
  
     <span data-ttu-id="c95ca-112">在前面的示例中，`Get`过程具有相同`Protected`访问属性本身，而`Set`过程有`Private`访问。</span><span class="sxs-lookup"><span data-stu-id="c95ca-112">In the preceding example, the `Get` procedure has the same `Protected` access as the property itself, while the `Set` procedure has `Private` access.</span></span> <span data-ttu-id="c95ca-113">从派生的类`employee`可以读取`salary`值，但只有`employee`类可将其设置。</span><span class="sxs-lookup"><span data-stu-id="c95ca-113">A class derived from `employee` can read the `salary` value, but only the `employee` class can set it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c95ca-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c95ca-114">See Also</span></span>  
 [<span data-ttu-id="c95ca-115">过程</span><span class="sxs-lookup"><span data-stu-id="c95ca-115">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="c95ca-116">属性过程</span><span class="sxs-lookup"><span data-stu-id="c95ca-116">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="c95ca-117">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="c95ca-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="c95ca-118">Property 语句</span><span class="sxs-lookup"><span data-stu-id="c95ca-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="c95ca-119">在 Visual Basic 中属性和变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="c95ca-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="c95ca-120">如何：创建属性</span><span class="sxs-lookup"><span data-stu-id="c95ca-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="c95ca-121">如何：调用 Property 过程</span><span class="sxs-lookup"><span data-stu-id="c95ca-121">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="c95ca-122">如何： 声明和 Visual Basic 中调用默认属性</span><span class="sxs-lookup"><span data-stu-id="c95ca-122">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="c95ca-123">如何：在属性中放置值</span><span class="sxs-lookup"><span data-stu-id="c95ca-123">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="c95ca-124">如何：从属性获取值</span><span class="sxs-lookup"><span data-stu-id="c95ca-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
