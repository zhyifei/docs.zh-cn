---
title: << = 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
ms.openlocfilehash: da2b5ca0b7538d77c3c8d8bc7d45712d656ce63a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58829143"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="dd6ed-102">\<\<= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd6ed-102">\<\<= Operator (Visual Basic)</span></span>
<span data-ttu-id="dd6ed-103">对变量或属性的值执行算术左的移位，并将结果赋回给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="dd6ed-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd6ed-104">语法</span><span class="sxs-lookup"><span data-stu-id="dd6ed-104">Syntax</span></span>  
  
```  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="dd6ed-105">部件</span><span class="sxs-lookup"><span data-stu-id="dd6ed-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="dd6ed-106">必需。</span><span class="sxs-lookup"><span data-stu-id="dd6ed-106">Required.</span></span> <span data-ttu-id="dd6ed-107">变量或属性的一种整型类型 (`SByte`， `Byte`， `Short`， `UShort`， `Integer`， `UInteger`， `Long`，或`ULong`)。</span><span class="sxs-lookup"><span data-stu-id="dd6ed-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="dd6ed-108">必需。</span><span class="sxs-lookup"><span data-stu-id="dd6ed-108">Required.</span></span> <span data-ttu-id="dd6ed-109">数值表达式的数据类型扩大到`Integer`。</span><span class="sxs-lookup"><span data-stu-id="dd6ed-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd6ed-110">备注</span><span class="sxs-lookup"><span data-stu-id="dd6ed-110">Remarks</span></span>  
 <span data-ttu-id="dd6ed-111">在左侧和右侧的元素`<<=`运算符可以是简单的标量变量、 属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="dd6ed-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="dd6ed-112">变量或属性不能[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="dd6ed-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="dd6ed-113">`<<=`运算符首先对变量或属性的值执行算术左的移位运算。</span><span class="sxs-lookup"><span data-stu-id="dd6ed-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span></span> <span data-ttu-id="dd6ed-114">然后，该运算符将该操作的结果赋回给该变量或属性。</span><span class="sxs-lookup"><span data-stu-id="dd6ed-114">The operator then assigns the result of that operation back to that variable or property.</span></span>  
  
 <span data-ttu-id="dd6ed-115">算术移位不是循环，这意味着移出结果的一端的数位另一端不重新移入。</span><span class="sxs-lookup"><span data-stu-id="dd6ed-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="dd6ed-116">在算术左移位运算移出的结果数据类型范围的位将被丢弃，并在右侧而空出的位设置为零。</span><span class="sxs-lookup"><span data-stu-id="dd6ed-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="dd6ed-117">重载</span><span class="sxs-lookup"><span data-stu-id="dd6ed-117">Overloading</span></span>  
 <span data-ttu-id="dd6ed-118">[<< 运算符](../../../visual-basic/language-reference/operators/left-shift-operator.md)可以是*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="dd6ed-118">The [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="dd6ed-119">重载`<<`运算符会影响的行为`<<=`运算符。</span><span class="sxs-lookup"><span data-stu-id="dd6ed-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span></span> <span data-ttu-id="dd6ed-120">如果你的代码使用`<<=`上类或结构的重载`<<`，确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="dd6ed-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="dd6ed-121">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="dd6ed-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd6ed-122">示例</span><span class="sxs-lookup"><span data-stu-id="dd6ed-122">Example</span></span>  
 <span data-ttu-id="dd6ed-123">下面的示例使用`<<=`运算符将该位模式移位的`Integer`变量指定的量，并将结果赋留给变量。</span><span class="sxs-lookup"><span data-stu-id="dd6ed-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="dd6ed-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd6ed-124">See also</span></span>

- [<span data-ttu-id="dd6ed-125"><< 运算符</span><span class="sxs-lookup"><span data-stu-id="dd6ed-125"><< Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-operator.md)
- [<span data-ttu-id="dd6ed-126">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="dd6ed-126">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="dd6ed-127">移位运算符</span><span class="sxs-lookup"><span data-stu-id="dd6ed-127">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="dd6ed-128">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="dd6ed-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="dd6ed-129">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="dd6ed-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="dd6ed-130">语句</span><span class="sxs-lookup"><span data-stu-id="dd6ed-130">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
