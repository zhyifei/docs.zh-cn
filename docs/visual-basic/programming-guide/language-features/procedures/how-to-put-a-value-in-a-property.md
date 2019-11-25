---
title: 如何：在属性中放置值
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: ad0d0e81f94dd3dead50f21c3bd6ff580c004dd6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346056"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="f0534-102">如何：在属性中放置值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0534-102">How to: Put a Value in a Property (Visual Basic)</span></span>
<span data-ttu-id="f0534-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span><span class="sxs-lookup"><span data-stu-id="f0534-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="f0534-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span><span class="sxs-lookup"><span data-stu-id="f0534-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="f0534-105">You use the property just as you would use a variable.</span><span class="sxs-lookup"><span data-stu-id="f0534-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="f0534-106">Visual Basic makes the calls to the property's procedures.</span><span class="sxs-lookup"><span data-stu-id="f0534-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="f0534-107">To store a value in a property</span><span class="sxs-lookup"><span data-stu-id="f0534-107">To store a value in a property</span></span>  
  
1. <span data-ttu-id="f0534-108">Use the property name on the left side of an assignment statement.</span><span class="sxs-lookup"><span data-stu-id="f0534-108">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="f0534-109">The following example sets the value of the Visual Basic `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span><span class="sxs-lookup"><span data-stu-id="f0534-109">The following example sets the value of the Visual Basic `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="f0534-110">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span><span class="sxs-lookup"><span data-stu-id="f0534-110">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="f0534-111">If there are no arguments, you can optionally omit the parentheses.</span><span class="sxs-lookup"><span data-stu-id="f0534-111">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="f0534-112">Place the arguments in the argument list within the parentheses, separated by commas.</span><span class="sxs-lookup"><span data-stu-id="f0534-112">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="f0534-113">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span><span class="sxs-lookup"><span data-stu-id="f0534-113">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4. <span data-ttu-id="f0534-114">The value generated on the right side of the assignment statement is stored in the property.</span><span class="sxs-lookup"><span data-stu-id="f0534-114">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0534-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0534-115">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>
- [<span data-ttu-id="f0534-116">属性过程</span><span class="sxs-lookup"><span data-stu-id="f0534-116">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="f0534-117">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="f0534-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="f0534-118">Property 语句</span><span class="sxs-lookup"><span data-stu-id="f0534-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="f0534-119">Differences Between Properties and Variables in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0534-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="f0534-120">如何：创建属性</span><span class="sxs-lookup"><span data-stu-id="f0534-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="f0534-121">如何：声明具有混合访问级别的属性</span><span class="sxs-lookup"><span data-stu-id="f0534-121">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="f0534-122">如何：调用 Property 过程</span><span class="sxs-lookup"><span data-stu-id="f0534-122">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="f0534-123">How to: Declare and Call a Default Property in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0534-123">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="f0534-124">如何：从属性获取值</span><span class="sxs-lookup"><span data-stu-id="f0534-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
