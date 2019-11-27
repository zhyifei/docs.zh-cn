---
title: 如何：从属性获取值
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 85512d4311d3e731a2c4e129d6a01f9b3273b333
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74339830"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a><span data-ttu-id="e078b-102">如何：从属性获取值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e078b-102">How to: Get a Value from a Property (Visual Basic)</span></span>
<span data-ttu-id="e078b-103">通过在表达式中包含属性名称来检索属性的值。</span><span class="sxs-lookup"><span data-stu-id="e078b-103">You retrieve a property's value by including the property name in an expression.</span></span>  
  
 <span data-ttu-id="e078b-104">该属性的 `Get` 过程会检索值，但不会按名称显式调用它。</span><span class="sxs-lookup"><span data-stu-id="e078b-104">The property's `Get` procedure retrieves the value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="e078b-105">像使用变量一样使用属性。</span><span class="sxs-lookup"><span data-stu-id="e078b-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="e078b-106">Visual Basic 对属性的过程进行调用。</span><span class="sxs-lookup"><span data-stu-id="e078b-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-retrieve-a-value-from-a-property"></a><span data-ttu-id="e078b-107">从属性中检索值</span><span class="sxs-lookup"><span data-stu-id="e078b-107">To retrieve a value from a property</span></span>  
  
1. <span data-ttu-id="e078b-108">在表达式中使用属性名称的方式与使用变量名相同。</span><span class="sxs-lookup"><span data-stu-id="e078b-108">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="e078b-109">可以在可以使用变量或常量的任何位置使用属性。</span><span class="sxs-lookup"><span data-stu-id="e078b-109">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="e078b-110">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="e078b-110">-or-</span></span>  
  
     <span data-ttu-id="e078b-111">在赋值语句中使用等号（`=`）后，使用属性名称。</span><span class="sxs-lookup"><span data-stu-id="e078b-111">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="e078b-112">下面的示例读取 Visual Basic `Now` 属性的值，从而隐式调用其 `Get` 过程。</span><span class="sxs-lookup"><span data-stu-id="e078b-112">The following example reads the value of the Visual Basic `Now` property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="e078b-113">如果属性采用参数，请在属性名称后面加上括号，以将参数列表括起来。</span><span class="sxs-lookup"><span data-stu-id="e078b-113">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="e078b-114">如果没有参数，则可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="e078b-114">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="e078b-115">将参数置于括号中的参数列表内，用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="e078b-115">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="e078b-116">请确保以属性定义相应参数的相同顺序提供参数。</span><span class="sxs-lookup"><span data-stu-id="e078b-116">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="e078b-117">属性的值作为变量或常数加入表达式，或者将其存储在赋值语句左侧的变量或属性中。</span><span class="sxs-lookup"><span data-stu-id="e078b-117">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e078b-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e078b-118">See also</span></span>

- [<span data-ttu-id="e078b-119">过程</span><span class="sxs-lookup"><span data-stu-id="e078b-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="e078b-120">属性过程</span><span class="sxs-lookup"><span data-stu-id="e078b-120">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="e078b-121">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="e078b-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="e078b-122">Property 语句</span><span class="sxs-lookup"><span data-stu-id="e078b-122">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="e078b-123">Visual Basic 中的属性和变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="e078b-123">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="e078b-124">如何：创建属性</span><span class="sxs-lookup"><span data-stu-id="e078b-124">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="e078b-125">如何：声明具有混合访问级别的属性</span><span class="sxs-lookup"><span data-stu-id="e078b-125">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="e078b-126">如何：调用 Property 过程</span><span class="sxs-lookup"><span data-stu-id="e078b-126">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="e078b-127">如何：在 Visual Basic 中声明和调用默认属性</span><span class="sxs-lookup"><span data-stu-id="e078b-127">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="e078b-128">如何：在属性中放置值</span><span class="sxs-lookup"><span data-stu-id="e078b-128">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
