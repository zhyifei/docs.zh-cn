---
title: < < = 运算符（Visual Basic）
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
ms.openlocfilehash: aae71069bdcb88efa5842526dd7eb47806f248d0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701109"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="ec1f7-102">\<\<= 运算符（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="ec1f7-102">\<\<= Operator (Visual Basic)</span></span>
<span data-ttu-id="ec1f7-103">对变量或属性的值执行算术左移位，并将结果赋回变量或属性。</span><span class="sxs-lookup"><span data-stu-id="ec1f7-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec1f7-104">语法</span><span class="sxs-lookup"><span data-stu-id="ec1f7-104">Syntax</span></span>  
  
```vb  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="ec1f7-105">部件</span><span class="sxs-lookup"><span data-stu-id="ec1f7-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="ec1f7-106">必需。</span><span class="sxs-lookup"><span data-stu-id="ec1f7-106">Required.</span></span> <span data-ttu-id="ec1f7-107">整数类型（`SByte`、`Byte`、`Short`、`UShort`、`Integer`、`UInteger`、`Long`或 `ULong`）的变量或属性。</span><span class="sxs-lookup"><span data-stu-id="ec1f7-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="ec1f7-108">必需。</span><span class="sxs-lookup"><span data-stu-id="ec1f7-108">Required.</span></span> <span data-ttu-id="ec1f7-109">扩大到 `Integer`的数据类型的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="ec1f7-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec1f7-110">备注</span><span class="sxs-lookup"><span data-stu-id="ec1f7-110">Remarks</span></span>  
 <span data-ttu-id="ec1f7-111">`<<=` 运算符左侧的元素可以是简单的标量变量、属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="ec1f7-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="ec1f7-112">变量或属性不能是[只读](../../../visual-basic/language-reference/modifiers/readonly.md)的。</span><span class="sxs-lookup"><span data-stu-id="ec1f7-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="ec1f7-113">`<<=` 运算符首先对变量或属性的值执行算术左移位运算。</span><span class="sxs-lookup"><span data-stu-id="ec1f7-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span></span> <span data-ttu-id="ec1f7-114">然后，运算符将该操作的结果赋给该变量或属性。</span><span class="sxs-lookup"><span data-stu-id="ec1f7-114">The operator then assigns the result of that operation back to that variable or property.</span></span>  
  
 <span data-ttu-id="ec1f7-115">算术移位不是循环的，这意味着，不会在另一端重新引入结果的末尾以外的位。</span><span class="sxs-lookup"><span data-stu-id="ec1f7-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="ec1f7-116">在算术左移位中，将丢弃超出结果数据类型范围的位，并将在右侧空出的位位置设置为零。</span><span class="sxs-lookup"><span data-stu-id="ec1f7-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="ec1f7-117">重载</span><span class="sxs-lookup"><span data-stu-id="ec1f7-117">Overloading</span></span>  
 <span data-ttu-id="ec1f7-118">[< < 运算符](../../../visual-basic/language-reference/operators/left-shift-operator.md)可*重载*，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="ec1f7-118">The [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ec1f7-119">重载 `<<` 运算符会影响 `<<=` 运算符的行为。</span><span class="sxs-lookup"><span data-stu-id="ec1f7-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span></span> <span data-ttu-id="ec1f7-120">如果你的代码在重载 `<<`的类或结构上使用 `<<=`，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="ec1f7-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="ec1f7-121">有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1f7-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec1f7-122">示例</span><span class="sxs-lookup"><span data-stu-id="ec1f7-122">Example</span></span>  
 <span data-ttu-id="ec1f7-123">下面的示例使用 `<<=` 运算符将 `Integer` 变量的位模式向左移动指定的量，并将结果赋给该变量。</span><span class="sxs-lookup"><span data-stu-id="ec1f7-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="ec1f7-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec1f7-124">See also</span></span>

- [<span data-ttu-id="ec1f7-125"><< 运算符</span><span class="sxs-lookup"><span data-stu-id="ec1f7-125"><< Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-operator.md)
- [<span data-ttu-id="ec1f7-126">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="ec1f7-126">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="ec1f7-127">移位运算符</span><span class="sxs-lookup"><span data-stu-id="ec1f7-127">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="ec1f7-128">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="ec1f7-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="ec1f7-129">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="ec1f7-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="ec1f7-130">语句</span><span class="sxs-lookup"><span data-stu-id="ec1f7-130">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
