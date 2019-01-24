---
title: 如何：将值放在属性 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: d40ca98f94f410bb20c8df0e7f1a3f216cf53bf9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589160"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="32f25-102">如何：将值放在属性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32f25-102">How to: Put a Value in a Property (Visual Basic)</span></span>
<span data-ttu-id="32f25-103">通过将属性名称放在赋值语句左侧，可以在属性中存储值。</span><span class="sxs-lookup"><span data-stu-id="32f25-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="32f25-104">该属性的`Set`过程存储一个值，但并不按名称显式调用它。</span><span class="sxs-lookup"><span data-stu-id="32f25-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="32f25-105">您使用该属性，就像您将使用变量。</span><span class="sxs-lookup"><span data-stu-id="32f25-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="32f25-106">Visual Basic 可以对该属性的过程的调用。</span><span class="sxs-lookup"><span data-stu-id="32f25-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="32f25-107">若要在属性中存储的值</span><span class="sxs-lookup"><span data-stu-id="32f25-107">To store a value in a property</span></span>  
  
1.  <span data-ttu-id="32f25-108">在赋值语句左侧使用属性名称。</span><span class="sxs-lookup"><span data-stu-id="32f25-108">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="32f25-109">下面的示例设置的值的 Visual basic`TimeOfDay`属性设置为中午，隐式调用其`Set`过程。</span><span class="sxs-lookup"><span data-stu-id="32f25-109">The following example sets the value of the Visual Basic `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]  
  
2.  <span data-ttu-id="32f25-110">如果该属性接受参数，请按照使用括号将参数列表括起来的属性名称。</span><span class="sxs-lookup"><span data-stu-id="32f25-110">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="32f25-111">如果没有任何自变量，可以选择性地省略括号。</span><span class="sxs-lookup"><span data-stu-id="32f25-111">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="32f25-112">将参数放在括号中，由逗号分隔参数列表中。</span><span class="sxs-lookup"><span data-stu-id="32f25-112">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="32f25-113">请确保提供的属性定义的相应参数的相同顺序中的自变量。</span><span class="sxs-lookup"><span data-stu-id="32f25-113">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4.  <span data-ttu-id="32f25-114">在属性中存储生成的赋值语句右侧的值。</span><span class="sxs-lookup"><span data-stu-id="32f25-114">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32f25-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="32f25-115">See also</span></span>
- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>
- [<span data-ttu-id="32f25-116">属性过程</span><span class="sxs-lookup"><span data-stu-id="32f25-116">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="32f25-117">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="32f25-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="32f25-118">Property 语句</span><span class="sxs-lookup"><span data-stu-id="32f25-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="32f25-119">在 Visual Basic 中属性和变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="32f25-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="32f25-120">如何：创建属性</span><span class="sxs-lookup"><span data-stu-id="32f25-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="32f25-121">如何：声明具有混合的访问级别的属性</span><span class="sxs-lookup"><span data-stu-id="32f25-121">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="32f25-122">如何：调用 Property 过程</span><span class="sxs-lookup"><span data-stu-id="32f25-122">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="32f25-123">如何：声明并在 Visual Basic 中调用默认属性</span><span class="sxs-lookup"><span data-stu-id="32f25-123">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="32f25-124">如何：从属性获取一个值</span><span class="sxs-lookup"><span data-stu-id="32f25-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
