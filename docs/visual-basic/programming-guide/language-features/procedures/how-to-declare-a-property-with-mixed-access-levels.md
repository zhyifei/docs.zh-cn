---
title: 如何：声明具有混合的访问级别 (Visual Basic 中) 的属性
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
ms.openlocfilehash: d2b1a80863fe29901554b4912acbbfbdfdab4122
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972576"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a><span data-ttu-id="d1f70-102">如何：声明具有混合的访问级别 (Visual Basic 中) 的属性</span><span class="sxs-lookup"><span data-stu-id="d1f70-102">How to: Declare a Property with Mixed Access Levels (Visual Basic)</span></span>
<span data-ttu-id="d1f70-103">如果你想`Get`并`Set`要具有不同的访问级别的属性的过程，您可以使用中的限制性更弱级别`Property`语句，并在限制性更强的级别`Get`或`Set`语句。</span><span class="sxs-lookup"><span data-stu-id="d1f70-103">If you want the `Get` and `Set` procedures on a property to have different access levels, you can use the more permissive level in the `Property` statement and the more restrictive level in either the `Get` or `Set` statement.</span></span> <span data-ttu-id="d1f70-104">当你想要能够获取属性的值的代码的某些部分和某些其他部分的代码要能够更改的值时，可以在属性上使用混合的访问级别。</span><span class="sxs-lookup"><span data-stu-id="d1f70-104">You use mixed access levels on a property when you want certain parts of the code to be able to get the property's value, and certain other parts of the code to be able to change the value.</span></span>  
  
 <span data-ttu-id="d1f70-105">有关访问级别的详细信息，请参阅[访问 Visual Basic 中的级别](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="d1f70-105">For more information on access levels, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a><span data-ttu-id="d1f70-106">若要声明具有混合的访问级别的属性</span><span class="sxs-lookup"><span data-stu-id="d1f70-106">To declare a property with mixed access levels</span></span>  
  
1.  <span data-ttu-id="d1f70-107">以正常方式声明的属性和指定限制性较弱的访问级别 (如`Public`) 中`Property`语句。</span><span class="sxs-lookup"><span data-stu-id="d1f70-107">Declare the property in the normal way, and specify the less restrictive access level (such as `Public`) in the `Property` statement.</span></span>  
  
2.  <span data-ttu-id="d1f70-108">声明`Get`或`Set`过程指定限制性更强的访问级别 (如`Friend`)。</span><span class="sxs-lookup"><span data-stu-id="d1f70-108">Declare either the `Get` or the `Set` procedure specifying the more restrictive access level (such as `Friend`).</span></span>  
  
3.  <span data-ttu-id="d1f70-109">不要对其他属性过程指定访问级别。</span><span class="sxs-lookup"><span data-stu-id="d1f70-109">Do not specify an access level on the other property procedure.</span></span> <span data-ttu-id="d1f70-110">它假定中声明的访问级别`Property`语句。</span><span class="sxs-lookup"><span data-stu-id="d1f70-110">It assumes the access level declared in the `Property` statement.</span></span> <span data-ttu-id="d1f70-111">你可以限制属性过程之一上的访问。</span><span class="sxs-lookup"><span data-stu-id="d1f70-111">You can restrict access on only one of the property procedures.</span></span>  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     <span data-ttu-id="d1f70-112">在前面的示例中，`Get`过程具有相同`Protected`与该属性本身的访问权限时`Set`过程包含`Private`访问。</span><span class="sxs-lookup"><span data-stu-id="d1f70-112">In the preceding example, the `Get` procedure has the same `Protected` access as the property itself, while the `Set` procedure has `Private` access.</span></span> <span data-ttu-id="d1f70-113">一个类派生自`employee`可以读取`salary`值，但只有`employee`类可以将其设置。</span><span class="sxs-lookup"><span data-stu-id="d1f70-113">A class derived from `employee` can read the `salary` value, but only the `employee` class can set it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1f70-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1f70-114">See also</span></span>
- [<span data-ttu-id="d1f70-115">过程</span><span class="sxs-lookup"><span data-stu-id="d1f70-115">Procedures</span></span>](./index.md)
- [<span data-ttu-id="d1f70-116">属性过程</span><span class="sxs-lookup"><span data-stu-id="d1f70-116">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="d1f70-117">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="d1f70-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="d1f70-118">Property 语句</span><span class="sxs-lookup"><span data-stu-id="d1f70-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="d1f70-119">在 Visual Basic 中属性和变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="d1f70-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="d1f70-120">如何：创建属性</span><span class="sxs-lookup"><span data-stu-id="d1f70-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="d1f70-121">如何：调用 Property 过程</span><span class="sxs-lookup"><span data-stu-id="d1f70-121">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="d1f70-122">如何：声明并在 Visual Basic 中调用默认属性</span><span class="sxs-lookup"><span data-stu-id="d1f70-122">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="d1f70-123">如何：在属性中放置值</span><span class="sxs-lookup"><span data-stu-id="d1f70-123">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="d1f70-124">如何：从属性获取一个值</span><span class="sxs-lookup"><span data-stu-id="d1f70-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
