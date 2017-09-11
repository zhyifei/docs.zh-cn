---
title: "如何︰ 将值放属性 (Visual Basic 中) |Microsoft 文档"
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
- property values
- Visual Basic code, procedures
- values, properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
caps.latest.revision: 13
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
ms.openlocfilehash: c838141a27c30b11765d30ae8b0c19bccc929f4b
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="4c9a6-102">如何：在属性中放置值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c9a6-102">How to: Put a Value in a Property (Visual Basic)</span></span>
<span data-ttu-id="4c9a6-103">通过将属性名称放在赋值语句的左侧，可以在属性中存储一个值。</span><span class="sxs-lookup"><span data-stu-id="4c9a6-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="4c9a6-104">该属性的`Set`过程存储一个值，但并不按名称显式调用它。</span><span class="sxs-lookup"><span data-stu-id="4c9a6-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="4c9a6-105">就像您使用一个变量，您可以使用该属性。</span><span class="sxs-lookup"><span data-stu-id="4c9a6-105">You use the property just as you would use a variable.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="4c9a6-106">调用该属性的过程。</span><span class="sxs-lookup"><span data-stu-id="4c9a6-106"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="4c9a6-107">在属性中存储的值</span><span class="sxs-lookup"><span data-stu-id="4c9a6-107">To store a value in a property</span></span>  
  
1.  <span data-ttu-id="4c9a6-108">在赋值语句左侧使用的属性名称。</span><span class="sxs-lookup"><span data-stu-id="4c9a6-108">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="4c9a6-109">下面的示例设置的值[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]`TimeOfDay`属性设置为中午，隐式调用其`Set`过程。</span><span class="sxs-lookup"><span data-stu-id="4c9a6-109">The following example sets the value of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     <span data-ttu-id="4c9a6-110">[!code-vb[VbVbcnProcedures #&11;](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4c9a6-110">[!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]</span></span>  
  
2.  <span data-ttu-id="4c9a6-111">如果该属性接受参数，请按照用括号括起的参数列表的属性名称。</span><span class="sxs-lookup"><span data-stu-id="4c9a6-111">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="4c9a6-112">如果不有任何参数，可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="4c9a6-112">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="4c9a6-113">将参数放在括号内，用逗号分隔参数列表中。</span><span class="sxs-lookup"><span data-stu-id="4c9a6-113">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="4c9a6-114">请确保您的属性定义的相应参数的相同顺序的参数提供。</span><span class="sxs-lookup"><span data-stu-id="4c9a6-114">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4.  <span data-ttu-id="4c9a6-115">生成的赋值语句右侧的值存储在该属性。</span><span class="sxs-lookup"><span data-stu-id="4c9a6-115">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c9a6-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c9a6-116">See Also</span></span>  
 <span data-ttu-id="4c9a6-117"><xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></span><span class="sxs-lookup"><span data-stu-id="4c9a6-117"><xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></span></span>   
<span data-ttu-id="4c9a6-118"> [属性过程](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="4c9a6-118"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="4c9a6-119"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="4c9a6-119"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="4c9a6-120"> [Property 语句](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4c9a6-120"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="4c9a6-121"> [在 Visual Basic 中属性和变量之间的差异](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="4c9a6-121"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="4c9a6-122"> [如何︰ 创建属性](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="4c9a6-122"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="4c9a6-123"> [如何︰ 声明具有混合的访问级别的属性](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="4c9a6-123"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="4c9a6-124"> [如何︰ 调用 Property 过程](./how-to-call-a-property-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="4c9a6-124"> [How to: Call a Property Procedure](./how-to-call-a-property-procedure.md) </span></span>  
<span data-ttu-id="4c9a6-125"> [如何︰ 声明和调用默认属性在 Visual Basic 中](./how-to-declare-and-call-a-default-property.md) </span><span class="sxs-lookup"><span data-stu-id="4c9a6-125"> [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span></span>  
<span data-ttu-id="4c9a6-126"> [如何：从属性获取值](./how-to-get-a-value-from-a-property.md)</span><span class="sxs-lookup"><span data-stu-id="4c9a6-126"> [How to: Get a Value from a Property](./how-to-get-a-value-from-a-property.md)</span></span>
