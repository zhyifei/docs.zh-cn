---
title: "如何︰ 调用 Property 过程 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures, calling
- properties [Visual Basic], property procedures
- procedure calls, property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d0d37fc2b7ae1d563a7e9d0a8e75343dd690089b
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="4f3cb-102">如何：调用 Property 过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f3cb-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="4f3cb-103">在属性中存储一个值或检索其值由调用 property 过程。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="4f3cb-104">访问属性相同的方式访问的变量。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="4f3cb-105">该属性的`Set`过程存储一个值，并将其`Get`过程会检索该值。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="4f3cb-106">但是，您不显式调用这些过程的名称。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="4f3cb-107">就像将存储或检索变量的值时，才使用在赋值语句或表达式，该属性。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="4f3cb-108">调用该属性的过程。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-108"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="4f3cb-109">若要调用 property Get 过程</span><span class="sxs-lookup"><span data-stu-id="4f3cb-109">To call a property's Get procedure</span></span>  
  
1.  <span data-ttu-id="4f3cb-110">像使用变量名一样，在表达式中使用属性名称。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="4f3cb-111">可以使用属性任何可以使用一个变量或常量。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="4f3cb-112">- 或 -</span><span class="sxs-lookup"><span data-stu-id="4f3cb-112">-or-</span></span>  
  
     <span data-ttu-id="4f3cb-113">使用属性名称后面等号 (`=`) 登录在赋值语句。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="4f3cb-114">下面的示例读取的值<xref:Microsoft.VisualBasic.DateAndTime.Now%2A>属性外，隐式调用其`Get`过程。</xref:Microsoft.VisualBasic.DateAndTime.Now%2A></span><span class="sxs-lookup"><span data-stu-id="4f3cb-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     <span data-ttu-id="4f3cb-115">[!code-vb[VbVbalrDateProperties #&4;](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4f3cb-115">[!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]</span></span>  
  
2.  <span data-ttu-id="4f3cb-116">如果该属性接受参数，请按照用括号括起的参数列表的属性名称。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-116">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="4f3cb-117">如果不有任何参数，可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-117">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="4f3cb-118">将参数放在括号内，用逗号分隔参数列表中。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-118">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="4f3cb-119">请确保您的属性定义的相应参数的相同顺序的参数提供。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-119">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="4f3cb-120">属性的值参与像变量表达式或常数那样，或存储在变量或赋值语句左侧的属性。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-120">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="4f3cb-121">若要调用的属性的设置过程</span><span class="sxs-lookup"><span data-stu-id="4f3cb-121">To call a property's Set procedure</span></span>  
  
1.  <span data-ttu-id="4f3cb-122">在赋值语句左侧使用的属性名称。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-122">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="4f3cb-123">下面的示例设置的值<xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>属性外，隐式调用`Set`过程。</xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></span><span class="sxs-lookup"><span data-stu-id="4f3cb-123">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     <span data-ttu-id="4f3cb-124">[!code-vb[VbVbcnProcedures #&11;](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="4f3cb-124">[!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]</span></span>  
  
2.  <span data-ttu-id="4f3cb-125">如果该属性接受参数，请按照用括号括起的参数列表的属性名称。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-125">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="4f3cb-126">如果不有任何参数，可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-126">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="4f3cb-127">将参数放在括号内，用逗号分隔参数列表中。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-127">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="4f3cb-128">请确保您的属性定义的相应参数的相同顺序的参数提供。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-128">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="4f3cb-129">生成的赋值语句右侧的值存储在该属性。</span><span class="sxs-lookup"><span data-stu-id="4f3cb-129">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f3cb-130">请参见</span><span class="sxs-lookup"><span data-stu-id="4f3cb-130">See Also</span></span>  
 <span data-ttu-id="4f3cb-131">[属性过程](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="4f3cb-131">[Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="4f3cb-132"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="4f3cb-132"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="4f3cb-133"> [Property 语句](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4f3cb-133"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="4f3cb-134"> [在 Visual Basic 中属性和变量之间的差异](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="4f3cb-134"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="4f3cb-135"> [如何︰ 创建属性](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="4f3cb-135"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="4f3cb-136"> [如何︰ 声明具有混合的访问级别的属性](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="4f3cb-136"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="4f3cb-137"> [如何︰ 声明和调用默认属性在 Visual Basic 中](./how-to-declare-and-call-a-default-property.md) </span><span class="sxs-lookup"><span data-stu-id="4f3cb-137"> [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span></span>  
<span data-ttu-id="4f3cb-138"> [如何︰ 在属性中放置值](./how-to-put-a-value-in-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="4f3cb-138"> [How to: Put a Value in a Property](./how-to-put-a-value-in-a-property.md) </span></span>  
<span data-ttu-id="4f3cb-139"> [如何︰ 从属性获取一个值](./how-to-get-a-value-from-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="4f3cb-139"> [How to: Get a Value from a Property](./how-to-get-a-value-from-a-property.md) </span></span>  
<span data-ttu-id="4f3cb-140"> [Get 语句](../../../../visual-basic/language-reference/statements/get-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4f3cb-140"> [Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md) </span></span>  
<span data-ttu-id="4f3cb-141"> [Set 语句](../../../../visual-basic/language-reference/statements/set-statement.md)</span><span class="sxs-lookup"><span data-stu-id="4f3cb-141"> [Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)</span></span>
