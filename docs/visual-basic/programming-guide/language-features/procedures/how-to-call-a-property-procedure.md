---
title: 如何：调用 Property 过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: d05c1b63f5567ade9935f80ecc022eb4840e0af0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318738"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="12a41-102">如何：调用 Property 过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12a41-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="12a41-103">在属性中存储一个值，或检索其值由调用 property 过程。</span><span class="sxs-lookup"><span data-stu-id="12a41-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="12a41-104">访问属性访问的变量的相同方法。</span><span class="sxs-lookup"><span data-stu-id="12a41-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="12a41-105">该属性的`Set`过程存储一个值，并将其`Get`过程检索的值。</span><span class="sxs-lookup"><span data-stu-id="12a41-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="12a41-106">但是，不显式调用这些过程的名称。</span><span class="sxs-lookup"><span data-stu-id="12a41-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="12a41-107">就像将存储或检索变量的值使用赋值语句或表达式中的属性。</span><span class="sxs-lookup"><span data-stu-id="12a41-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> <span data-ttu-id="12a41-108">Visual Basic 可以对该属性的过程的调用。</span><span class="sxs-lookup"><span data-stu-id="12a41-108">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="12a41-109">若要调用 property Get 过程</span><span class="sxs-lookup"><span data-stu-id="12a41-109">To call a property's Get procedure</span></span>  
  
1. <span data-ttu-id="12a41-110">将使用变量名的相同方式在表达式中使用的属性名称。</span><span class="sxs-lookup"><span data-stu-id="12a41-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="12a41-111">可以使用属性可以在任意位置使用一个变量或常量。</span><span class="sxs-lookup"><span data-stu-id="12a41-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="12a41-112">或</span><span class="sxs-lookup"><span data-stu-id="12a41-112">-or-</span></span>  
  
     <span data-ttu-id="12a41-113">使用属性名称之后等号 (`=`) 在赋值语句登录。</span><span class="sxs-lookup"><span data-stu-id="12a41-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="12a41-114">下面的示例读取的值<xref:Microsoft.VisualBasic.DateAndTime.Now%2A>属性外，隐式调用其`Get`过程。</span><span class="sxs-lookup"><span data-stu-id="12a41-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="12a41-115">如果该属性接受参数，请按照使用括号将参数列表括起来的属性名称。</span><span class="sxs-lookup"><span data-stu-id="12a41-115">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="12a41-116">如果没有任何自变量，可以选择性地省略括号。</span><span class="sxs-lookup"><span data-stu-id="12a41-116">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="12a41-117">将参数放在括号中，由逗号分隔参数列表中。</span><span class="sxs-lookup"><span data-stu-id="12a41-117">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="12a41-118">请确保提供的属性定义的相应参数的相同顺序中的自变量。</span><span class="sxs-lookup"><span data-stu-id="12a41-118">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="12a41-119">属性的值出现在中，只需为变量表达式或常数那样，或存储在变量或赋值语句左侧的属性。</span><span class="sxs-lookup"><span data-stu-id="12a41-119">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="12a41-120">若要调用属性的设置过程</span><span class="sxs-lookup"><span data-stu-id="12a41-120">To call a property's Set procedure</span></span>  
  
1. <span data-ttu-id="12a41-121">在赋值语句左侧使用属性名称。</span><span class="sxs-lookup"><span data-stu-id="12a41-121">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="12a41-122">下面的示例设置的值<xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>属性外，隐式调用`Set`过程。</span><span class="sxs-lookup"><span data-stu-id="12a41-122">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="12a41-123">如果该属性接受参数，请按照使用括号将参数列表括起来的属性名称。</span><span class="sxs-lookup"><span data-stu-id="12a41-123">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="12a41-124">如果没有任何自变量，可以选择性地省略括号。</span><span class="sxs-lookup"><span data-stu-id="12a41-124">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="12a41-125">将参数放在括号中，由逗号分隔参数列表中。</span><span class="sxs-lookup"><span data-stu-id="12a41-125">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="12a41-126">请确保提供的属性定义的相应参数的相同顺序中的自变量。</span><span class="sxs-lookup"><span data-stu-id="12a41-126">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="12a41-127">在属性中存储生成的赋值语句右侧的值。</span><span class="sxs-lookup"><span data-stu-id="12a41-127">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12a41-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="12a41-128">See also</span></span>

- [<span data-ttu-id="12a41-129">Property 过程</span><span class="sxs-lookup"><span data-stu-id="12a41-129">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="12a41-130">过程形参和实参</span><span class="sxs-lookup"><span data-stu-id="12a41-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="12a41-131">Property Statement</span><span class="sxs-lookup"><span data-stu-id="12a41-131">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="12a41-132">Visual Basic 中属性和变量的差异</span><span class="sxs-lookup"><span data-stu-id="12a41-132">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="12a41-133">如何：创建属性</span><span class="sxs-lookup"><span data-stu-id="12a41-133">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="12a41-134">如何：声明具有混合访问级别的属性</span><span class="sxs-lookup"><span data-stu-id="12a41-134">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="12a41-135">如何：声明并在 Visual Basic 中调用默认属性</span><span class="sxs-lookup"><span data-stu-id="12a41-135">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="12a41-136">如何：在属性中放置值</span><span class="sxs-lookup"><span data-stu-id="12a41-136">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="12a41-137">如何：从属性获取值</span><span class="sxs-lookup"><span data-stu-id="12a41-137">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
- [<span data-ttu-id="12a41-138">Get 语句</span><span class="sxs-lookup"><span data-stu-id="12a41-138">Get Statement</span></span>](../../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="12a41-139">Set 语句</span><span class="sxs-lookup"><span data-stu-id="12a41-139">Set Statement</span></span>](../../../../visual-basic/language-reference/statements/set-statement.md)
