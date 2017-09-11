---
title: "如何︰ 从属性 (Visual Basic 中) 中获取一个值 |Microsoft 文档"
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
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
caps.latest.revision: 11
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
ms.openlocfilehash: 719a4fc9ff163fb4437ea40c8265a5e36232347e
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a><span data-ttu-id="dff6b-102">如何：从属性获取值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dff6b-102">How to: Get a Value from a Property (Visual Basic)</span></span>
<span data-ttu-id="dff6b-103">通过将属性名称包含在表达式中检索属性的值。</span><span class="sxs-lookup"><span data-stu-id="dff6b-103">You retrieve a property's value by including the property name in an expression.</span></span>  
  
 <span data-ttu-id="dff6b-104">该属性的`Get`过程会检索值，但并不按名称显式调用它。</span><span class="sxs-lookup"><span data-stu-id="dff6b-104">The property's `Get` procedure retrieves the value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="dff6b-105">就像您使用一个变量，您可以使用该属性。</span><span class="sxs-lookup"><span data-stu-id="dff6b-105">You use the property just as you would use a variable.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="dff6b-106">调用该属性的过程。</span><span class="sxs-lookup"><span data-stu-id="dff6b-106"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-retrieve-a-value-from-a-property"></a><span data-ttu-id="dff6b-107">从属性中检索值</span><span class="sxs-lookup"><span data-stu-id="dff6b-107">To retrieve a value from a property</span></span>  
  
1.  <span data-ttu-id="dff6b-108">像使用变量名一样，在表达式中使用属性名称。</span><span class="sxs-lookup"><span data-stu-id="dff6b-108">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="dff6b-109">可以使用属性任何可以使用一个变量或常量。</span><span class="sxs-lookup"><span data-stu-id="dff6b-109">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="dff6b-110">- 或 -</span><span class="sxs-lookup"><span data-stu-id="dff6b-110">-or-</span></span>  
  
     <span data-ttu-id="dff6b-111">使用属性名称后面等号 (`=`) 登录在赋值语句。</span><span class="sxs-lookup"><span data-stu-id="dff6b-111">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="dff6b-112">下面的示例读取的值[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]`Now`属性外，隐式调用其`Get`过程。</span><span class="sxs-lookup"><span data-stu-id="dff6b-112">The following example reads the value of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `Now` property, implicitly calling its `Get` procedure.</span></span>  
  
     <span data-ttu-id="dff6b-113">[!code-vb[VbVbalrDateProperties #&4;](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="dff6b-113">[!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]</span></span>  
  
2.  <span data-ttu-id="dff6b-114">如果该属性接受参数，请按照用括号括起的参数列表的属性名称。</span><span class="sxs-lookup"><span data-stu-id="dff6b-114">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="dff6b-115">如果不有任何参数，可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="dff6b-115">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="dff6b-116">将参数放在括号内，用逗号分隔参数列表中。</span><span class="sxs-lookup"><span data-stu-id="dff6b-116">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="dff6b-117">请确保您的属性定义的相应参数的相同顺序的参数提供。</span><span class="sxs-lookup"><span data-stu-id="dff6b-117">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="dff6b-118">属性的值参与像变量表达式或常数那样，或存储在变量或赋值语句左侧的属性。</span><span class="sxs-lookup"><span data-stu-id="dff6b-118">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dff6b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dff6b-119">See Also</span></span>  
 <span data-ttu-id="dff6b-120">[过程](./index.md) </span><span class="sxs-lookup"><span data-stu-id="dff6b-120">[Procedures](./index.md) </span></span>  
<span data-ttu-id="dff6b-121"> [属性过程](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="dff6b-121"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="dff6b-122"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="dff6b-122"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="dff6b-123"> [Property 语句](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="dff6b-123"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="dff6b-124"> [在 Visual Basic 中属性和变量之间的差异](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="dff6b-124"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="dff6b-125"> [如何︰ 创建属性](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="dff6b-125"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="dff6b-126"> [如何︰ 声明具有混合的访问级别的属性](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="dff6b-126"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="dff6b-127"> [如何︰ 调用 Property 过程](./how-to-call-a-property-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="dff6b-127"> [How to: Call a Property Procedure](./how-to-call-a-property-procedure.md) </span></span>  
<span data-ttu-id="dff6b-128"> [如何︰ 声明和调用默认属性在 Visual Basic 中](./how-to-declare-and-call-a-default-property.md) </span><span class="sxs-lookup"><span data-stu-id="dff6b-128"> [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span></span>  
<span data-ttu-id="dff6b-129"> [如何：在属性中放置值](./how-to-put-a-value-in-a-property.md)</span><span class="sxs-lookup"><span data-stu-id="dff6b-129"> [How to: Put a Value in a Property](./how-to-put-a-value-in-a-property.md)</span></span>
