---
title: "&lt;&lt;= 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5c5c36e4f91155c09d01b448777483941d018d9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltlt-operator-visual-basic"></a><span data-ttu-id="97973-102">&lt;&lt;= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97973-102">&lt;&lt;= Operator (Visual Basic)</span></span>
<span data-ttu-id="97973-103">对变量或属性的值执行算术左的移位运算，并将结果赋回给该变量或属性。</span><span class="sxs-lookup"><span data-stu-id="97973-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97973-104">语法</span><span class="sxs-lookup"><span data-stu-id="97973-104">Syntax</span></span>  
  
```  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="97973-105">部件</span><span class="sxs-lookup"><span data-stu-id="97973-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="97973-106">必需。</span><span class="sxs-lookup"><span data-stu-id="97973-106">Required.</span></span> <span data-ttu-id="97973-107">变量或属性的整数类型 (`SByte`， `Byte`， `Short`， `UShort`， `Integer`， `UInteger`， `Long`，或`ULong`)。</span><span class="sxs-lookup"><span data-stu-id="97973-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="97973-108">必需。</span><span class="sxs-lookup"><span data-stu-id="97973-108">Required.</span></span> <span data-ttu-id="97973-109">数值表达式的数据类型扩大到`Integer`。</span><span class="sxs-lookup"><span data-stu-id="97973-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97973-110">备注</span><span class="sxs-lookup"><span data-stu-id="97973-110">Remarks</span></span>  
 <span data-ttu-id="97973-111">在左侧的元素`<<=`运算符可以是简单的标量变量、 属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="97973-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="97973-112">变量或属性不能为[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="97973-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="97973-113">`<<=`运算符先执行算术左的移位运算的变量或属性的值。</span><span class="sxs-lookup"><span data-stu-id="97973-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span></span> <span data-ttu-id="97973-114">然后，运算符将该操作的结果赋回给该变量或属性。</span><span class="sxs-lookup"><span data-stu-id="97973-114">The operator then assigns the result of that operation back to that variable or property.</span></span>  
  
 <span data-ttu-id="97973-115">算术移位不是循环，这意味着移出结果的一个 end 的数位另一端不重新移入。</span><span class="sxs-lookup"><span data-stu-id="97973-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="97973-116">在算术左移位运算移出的结果数据类型范围的位将被丢弃，并在右侧空出的位设置为零。</span><span class="sxs-lookup"><span data-stu-id="97973-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="97973-117">重载</span><span class="sxs-lookup"><span data-stu-id="97973-117">Overloading</span></span>  
 <span data-ttu-id="97973-118">[<< 运算符](../../../visual-basic/language-reference/operators/left-shift-operator.md)可以是*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="97973-118">The [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="97973-119">重载`<<`运算符会影响的行为`<<=`运算符。</span><span class="sxs-lookup"><span data-stu-id="97973-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span></span> <span data-ttu-id="97973-120">如果你的代码使用`<<=`对类或重载的结构`<<`，确保你理解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="97973-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="97973-121">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="97973-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="97973-122">示例</span><span class="sxs-lookup"><span data-stu-id="97973-122">Example</span></span>  
 <span data-ttu-id="97973-123">下面的示例使用`<<=`运算符以将移动的位模式`Integer`变量留下指定的量并将结果赋给变量。</span><span class="sxs-lookup"><span data-stu-id="97973-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="97973-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97973-124">See Also</span></span>  
 [<span data-ttu-id="97973-125"><< 运算符</span><span class="sxs-lookup"><span data-stu-id="97973-125"><< Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-operator.md)  
 [<span data-ttu-id="97973-126">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="97973-126">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="97973-127">移位运算符</span><span class="sxs-lookup"><span data-stu-id="97973-127">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="97973-128">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="97973-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="97973-129">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="97973-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="97973-130">语句</span><span class="sxs-lookup"><span data-stu-id="97973-130">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
