---
title: += 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: f615df50643912beb12eb89d80b922fc30a3e6df
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944472"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="670bf-102">+= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="670bf-102">+= Operator (Visual Basic)</span></span>
<span data-ttu-id="670bf-103">将数值表达式的值添加到数值变量或属性的值, 并将结果赋给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="670bf-103">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="670bf-104">还可用于将`String`表达式连接`String`到变量或属性, 并将结果赋给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="670bf-104">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="670bf-105">语法</span><span class="sxs-lookup"><span data-stu-id="670bf-105">Syntax</span></span>  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="670bf-106">部件</span><span class="sxs-lookup"><span data-stu-id="670bf-106">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="670bf-107">必需。</span><span class="sxs-lookup"><span data-stu-id="670bf-107">Required.</span></span> <span data-ttu-id="670bf-108">任何数值或`String`变量或属性。</span><span class="sxs-lookup"><span data-stu-id="670bf-108">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="670bf-109">必需。</span><span class="sxs-lookup"><span data-stu-id="670bf-109">Required.</span></span> <span data-ttu-id="670bf-110">任何数值或`String`表达式。</span><span class="sxs-lookup"><span data-stu-id="670bf-110">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="670bf-111">备注</span><span class="sxs-lookup"><span data-stu-id="670bf-111">Remarks</span></span>  
 <span data-ttu-id="670bf-112">`+=`运算符左侧的元素可以是简单的标量变量、属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="670bf-112">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="670bf-113">变量或属性不能是[只读](../../../visual-basic/language-reference/modifiers/readonly.md)的。</span><span class="sxs-lookup"><span data-stu-id="670bf-113">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="670bf-114">`+=`运算符将其右侧的值添加到其左侧的变量或属性, 并将结果赋给其左侧的变量或属性。</span><span class="sxs-lookup"><span data-stu-id="670bf-114">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="670bf-115">运算符还可用于将其右侧的`String`表达式连接到左侧的`String`变量或属性, 并将结果分配给其左侧的变量或属性。 `+=`</span><span class="sxs-lookup"><span data-stu-id="670bf-115">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="670bf-116">使用`+=`运算符时, 可能无法确定是进行加法还是字符串串联。</span><span class="sxs-lookup"><span data-stu-id="670bf-116">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="670bf-117">`&=`使用运算符进行串联以消除多义性, 并提供自文档代码。</span><span class="sxs-lookup"><span data-stu-id="670bf-117">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="670bf-118">如果编译环境强制执行严格语义, 则此赋值运算符隐式执行扩大但不进行收缩转换。</span><span class="sxs-lookup"><span data-stu-id="670bf-118">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="670bf-119">有关这些转换的详细信息, 请参阅[扩大和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="670bf-119">For more information on these conversions, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="670bf-120">有关严格语义和许可语义的详细信息, 请参阅[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="670bf-120">For more information on strict and permissive semantics, see [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="670bf-121">如果允许使用允许的隐式`+=`语义, 运算符将隐式执行与`+`运算符执行的操作相同的各种字符串和数值转换。</span><span class="sxs-lookup"><span data-stu-id="670bf-121">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="670bf-122">有关这些转换的详细信息, 请参阅[+ 运算符](../../../visual-basic/language-reference/operators/addition-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="670bf-122">For details on these conversions, see [+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="670bf-123">重载</span><span class="sxs-lookup"><span data-stu-id="670bf-123">Overloading</span></span>  
 <span data-ttu-id="670bf-124">运算符可以重载, 这意味着当操作数具有该类或结构的类型时, 该类或结构可以重新定义其行为。 `+`</span><span class="sxs-lookup"><span data-stu-id="670bf-124">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="670bf-125">重载运算符会影响`+=`运算符的行为。 `+`</span><span class="sxs-lookup"><span data-stu-id="670bf-125">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="670bf-126">如果你的代码`+=`在重载`+`的类或结构上使用, 请确保你了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="670bf-126">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="670bf-127">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="670bf-127">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="670bf-128">示例</span><span class="sxs-lookup"><span data-stu-id="670bf-128">Example</span></span>  
 <span data-ttu-id="670bf-129">下面的示例使用`+=`运算符将一个变量的值与另一个变量组合在一起。</span><span class="sxs-lookup"><span data-stu-id="670bf-129">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="670bf-130">第一部分使用`+=`数值变量将一个值添加到另一个值。</span><span class="sxs-lookup"><span data-stu-id="670bf-130">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="670bf-131">第二部分使用`+=` with `String`变量将一个值与另一个值连接起来。</span><span class="sxs-lookup"><span data-stu-id="670bf-131">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="670bf-132">在这两种情况下, 都会将结果赋给第一个变量。</span><span class="sxs-lookup"><span data-stu-id="670bf-132">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 <span data-ttu-id="670bf-133">的值`num1`现在为 13, 的`str1`值现在为 "103"。</span><span class="sxs-lookup"><span data-stu-id="670bf-133">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="670bf-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="670bf-134">See also</span></span>

- [<span data-ttu-id="670bf-135">+ 运算符</span><span class="sxs-lookup"><span data-stu-id="670bf-135">+ Operator</span></span>](../../../visual-basic/language-reference/operators/addition-operator.md)
- [<span data-ttu-id="670bf-136">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="670bf-136">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="670bf-137">算术运算符</span><span class="sxs-lookup"><span data-stu-id="670bf-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="670bf-138">串联运算符</span><span class="sxs-lookup"><span data-stu-id="670bf-138">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="670bf-139">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="670bf-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="670bf-140">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="670bf-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="670bf-141">语句</span><span class="sxs-lookup"><span data-stu-id="670bf-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
