---
title: "&gt;&gt;= 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e7e388471b9adf424c55b1ad1042e5aed1ea8ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="gtgt-operator-visual-basic"></a><span data-ttu-id="77dc2-102">&gt;&gt;= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77dc2-102">&gt;&gt;= Operator (Visual Basic)</span></span>
<span data-ttu-id="77dc2-103">对变量或属性的值执行算术右移位运算，并将结果赋回给该变量或属性。</span><span class="sxs-lookup"><span data-stu-id="77dc2-103">Performs an arithmetic right shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77dc2-104">语法</span><span class="sxs-lookup"><span data-stu-id="77dc2-104">Syntax</span></span>  
  
```  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="77dc2-105">部件</span><span class="sxs-lookup"><span data-stu-id="77dc2-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="77dc2-106">必需。</span><span class="sxs-lookup"><span data-stu-id="77dc2-106">Required.</span></span> <span data-ttu-id="77dc2-107">变量或属性的整数类型 (`SByte`， `Byte`， `Short`， `UShort`， `Integer`， `UInteger`， `Long`，或`ULong`)。</span><span class="sxs-lookup"><span data-stu-id="77dc2-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="77dc2-108">必需。</span><span class="sxs-lookup"><span data-stu-id="77dc2-108">Required.</span></span> <span data-ttu-id="77dc2-109">数值表达式的数据类型扩大到`Integer`。</span><span class="sxs-lookup"><span data-stu-id="77dc2-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77dc2-110">备注</span><span class="sxs-lookup"><span data-stu-id="77dc2-110">Remarks</span></span>  
 <span data-ttu-id="77dc2-111">在左侧的元素`>>=`运算符可以是简单的标量变量、 属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="77dc2-111">The element on the left side of the `>>=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="77dc2-112">变量或属性不能为[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="77dc2-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="77dc2-113">`>>=`运算符先执行算术右移位运算的变量或属性的值。</span><span class="sxs-lookup"><span data-stu-id="77dc2-113">The `>>=` operator first performs an arithmetic right shift on the value of the variable or property.</span></span> <span data-ttu-id="77dc2-114">然后，运算符将该操作的结果赋回给该变量或属性。</span><span class="sxs-lookup"><span data-stu-id="77dc2-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="77dc2-115">算术移位不是循环，这意味着移出结果的一个 end 的数位另一端不重新移入。</span><span class="sxs-lookup"><span data-stu-id="77dc2-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="77dc2-116">在算术右移位运算移出最右边的位位置的位将被丢弃，并最左边的位传播到左侧空出的位位置。</span><span class="sxs-lookup"><span data-stu-id="77dc2-116">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="77dc2-117">这意味着，如果`variableorproperty`具有负值，空出的位置将设置为一。</span><span class="sxs-lookup"><span data-stu-id="77dc2-117">This means that if `variableorproperty` has a negative value, the vacated positions are set to one.</span></span> <span data-ttu-id="77dc2-118">如果`variableorproperty`为正，或者如果其数据类型是无符号的类型，空出的位置被设置为零。</span><span class="sxs-lookup"><span data-stu-id="77dc2-118">If `variableorproperty` is positive, or if its data type is an unsigned type, the vacated positions are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="77dc2-119">重载</span><span class="sxs-lookup"><span data-stu-id="77dc2-119">Overloading</span></span>  
 <span data-ttu-id="77dc2-120">[>> 运算符](../../../visual-basic/language-reference/operators/right-shift-operator.md)可以是*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="77dc2-120">The [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="77dc2-121">重载`>>`运算符会影响的行为`>>=`运算符。</span><span class="sxs-lookup"><span data-stu-id="77dc2-121">Overloading the `>>` operator affects the behavior of the `>>=` operator.</span></span> <span data-ttu-id="77dc2-122">如果你的代码使用`>>=`对类或重载的结构`>>`，确保你理解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="77dc2-122">If your code uses `>>=` on a class or structure that overloads `>>`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="77dc2-123">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="77dc2-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="77dc2-124">示例</span><span class="sxs-lookup"><span data-stu-id="77dc2-124">Example</span></span>  
 <span data-ttu-id="77dc2-125">下面的示例使用`>>=`运算符以将移动的位模式`Integer`变量权限中指定的量和数据将结果赋给变量。</span><span class="sxs-lookup"><span data-stu-id="77dc2-125">The following example uses the `>>=` operator to shift the bit pattern of an `Integer` variable right by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="77dc2-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77dc2-126">See Also</span></span>  
 [<span data-ttu-id="77dc2-127">>> 运算符</span><span class="sxs-lookup"><span data-stu-id="77dc2-127">>> Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-operator.md)  
 [<span data-ttu-id="77dc2-128">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="77dc2-128">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="77dc2-129">移位运算符</span><span class="sxs-lookup"><span data-stu-id="77dc2-129">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="77dc2-130">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="77dc2-130">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="77dc2-131">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="77dc2-131">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="77dc2-132">语句</span><span class="sxs-lookup"><span data-stu-id="77dc2-132">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
