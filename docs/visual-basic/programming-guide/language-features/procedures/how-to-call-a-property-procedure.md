---
title: "如何：调用 Property 过程 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf9080e3c2b23302257499f13e734231f3614495
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="70ff1-102">如何：调用 Property 过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70ff1-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="70ff1-103">通过将值存储在属性中或检索其值调用 property 过程。</span><span class="sxs-lookup"><span data-stu-id="70ff1-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="70ff1-104">访问的属性相同的方式访问的变量。</span><span class="sxs-lookup"><span data-stu-id="70ff1-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="70ff1-105">该属性的`Set`过程存储一个值，并将其`Get`过程检索的值。</span><span class="sxs-lookup"><span data-stu-id="70ff1-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="70ff1-106">但是，你不显式调用这些过程的名称。</span><span class="sxs-lookup"><span data-stu-id="70ff1-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="70ff1-107">就像将存储或检索变量的值时，才使用赋值语句或表达式中的属性。</span><span class="sxs-lookup"><span data-stu-id="70ff1-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="70ff1-108">调用属性的过程。</span><span class="sxs-lookup"><span data-stu-id="70ff1-108"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="70ff1-109">调用属性的 Get 过程</span><span class="sxs-lookup"><span data-stu-id="70ff1-109">To call a property's Get procedure</span></span>  
  
1.  <span data-ttu-id="70ff1-110">你将使用的变量的名称相同的方式的表达式中使用的属性名称。</span><span class="sxs-lookup"><span data-stu-id="70ff1-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="70ff1-111">你可以使用属性任意位置，你可以使用变量或常量。</span><span class="sxs-lookup"><span data-stu-id="70ff1-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="70ff1-112">- 或 -</span><span class="sxs-lookup"><span data-stu-id="70ff1-112">-or-</span></span>  
  
     <span data-ttu-id="70ff1-113">使用以下等的属性名称 (`=`) 在赋值语句登录。</span><span class="sxs-lookup"><span data-stu-id="70ff1-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="70ff1-114">下面的示例读取值<xref:Microsoft.VisualBasic.DateAndTime.Now%2A>属性，隐式调用其`Get`过程。</span><span class="sxs-lookup"><span data-stu-id="70ff1-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]  
  
2.  <span data-ttu-id="70ff1-115">如果该属性接受参数，请按照用括号将自变量列表括起来的属性名称。</span><span class="sxs-lookup"><span data-stu-id="70ff1-115">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="70ff1-116">如果不有任何自变量，你可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="70ff1-116">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="70ff1-117">将自变量放在括号里，用逗号分隔参数列表中。</span><span class="sxs-lookup"><span data-stu-id="70ff1-117">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="70ff1-118">请确保你提供属性定义的相应参数的相同顺序的自变量。</span><span class="sxs-lookup"><span data-stu-id="70ff1-118">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="70ff1-119">属性的值参与像变量表达式或常数那样，或存储在变量或赋值语句左侧的属性。</span><span class="sxs-lookup"><span data-stu-id="70ff1-119">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="70ff1-120">若要调用属性的设置过程</span><span class="sxs-lookup"><span data-stu-id="70ff1-120">To call a property's Set procedure</span></span>  
  
1.  <span data-ttu-id="70ff1-121">在赋值语句的左侧使用的属性名称。</span><span class="sxs-lookup"><span data-stu-id="70ff1-121">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="70ff1-122">下面的示例设置的值<xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>属性，隐式调用`Set`过程。</span><span class="sxs-lookup"><span data-stu-id="70ff1-122">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]  
  
2.  <span data-ttu-id="70ff1-123">如果该属性接受参数，请按照用括号将自变量列表括起来的属性名称。</span><span class="sxs-lookup"><span data-stu-id="70ff1-123">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="70ff1-124">如果不有任何自变量，你可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="70ff1-124">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="70ff1-125">将自变量放在括号里，用逗号分隔参数列表中。</span><span class="sxs-lookup"><span data-stu-id="70ff1-125">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="70ff1-126">请确保你提供属性定义的相应参数的相同顺序的自变量。</span><span class="sxs-lookup"><span data-stu-id="70ff1-126">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="70ff1-127">赋值语句右侧生成的值存储在属性。</span><span class="sxs-lookup"><span data-stu-id="70ff1-127">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70ff1-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70ff1-128">See Also</span></span>  
 [<span data-ttu-id="70ff1-129">属性过程</span><span class="sxs-lookup"><span data-stu-id="70ff1-129">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="70ff1-130">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="70ff1-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="70ff1-131">Property 语句</span><span class="sxs-lookup"><span data-stu-id="70ff1-131">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="70ff1-132">在 Visual Basic 中属性和变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="70ff1-132">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="70ff1-133">如何：创建属性</span><span class="sxs-lookup"><span data-stu-id="70ff1-133">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="70ff1-134">如何：声明具有混合访问级别的属性</span><span class="sxs-lookup"><span data-stu-id="70ff1-134">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="70ff1-135">如何： 声明和 Visual Basic 中调用默认属性</span><span class="sxs-lookup"><span data-stu-id="70ff1-135">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="70ff1-136">如何：在属性中放置值</span><span class="sxs-lookup"><span data-stu-id="70ff1-136">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="70ff1-137">如何：从属性获取值</span><span class="sxs-lookup"><span data-stu-id="70ff1-137">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)  
 [<span data-ttu-id="70ff1-138">Get 语句</span><span class="sxs-lookup"><span data-stu-id="70ff1-138">Get Statement</span></span>](../../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="70ff1-139">Set 语句</span><span class="sxs-lookup"><span data-stu-id="70ff1-139">Set Statement</span></span>](../../../../visual-basic/language-reference/statements/set-statement.md)
