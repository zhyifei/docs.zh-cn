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
ms.openlocfilehash: 249a19abfb08677c01ac4cc484d049a7ed1a983c
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591649"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="2902e-102">+= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2902e-102">+= Operator (Visual Basic)</span></span>
<span data-ttu-id="2902e-103">将数值表达式的值添加到数值变量或属性的值，并将结果赋给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="2902e-103">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="2902e-104">还可用于将 `String` 表达式连接到 `String` 变量或属性，并将结果分配给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="2902e-104">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2902e-105">语法</span><span class="sxs-lookup"><span data-stu-id="2902e-105">Syntax</span></span>  
  
```vb  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="2902e-106">部件</span><span class="sxs-lookup"><span data-stu-id="2902e-106">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="2902e-107">必需。</span><span class="sxs-lookup"><span data-stu-id="2902e-107">Required.</span></span> <span data-ttu-id="2902e-108">任何数值或 `String` 变量或属性。</span><span class="sxs-lookup"><span data-stu-id="2902e-108">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="2902e-109">必需。</span><span class="sxs-lookup"><span data-stu-id="2902e-109">Required.</span></span> <span data-ttu-id="2902e-110">任何数值表达式或 `String` 表达式。</span><span class="sxs-lookup"><span data-stu-id="2902e-110">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2902e-111">备注</span><span class="sxs-lookup"><span data-stu-id="2902e-111">Remarks</span></span>  
 <span data-ttu-id="2902e-112">`+=` 运算符左侧的元素可以是简单的标量变量、属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="2902e-112">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="2902e-113">变量或属性不能是[只读](../../../visual-basic/language-reference/modifiers/readonly.md)的。</span><span class="sxs-lookup"><span data-stu-id="2902e-113">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="2902e-114">`+=` 运算符将其右侧的值添加到其左边的变量或属性，并将结果赋给其左侧的变量或属性。</span><span class="sxs-lookup"><span data-stu-id="2902e-114">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="2902e-115">`+=` 运算符还可用于将其右侧的 `String` 表达式连接到其左边的 `String` 变量或属性，并将结果分配给其左侧的变量或属性。</span><span class="sxs-lookup"><span data-stu-id="2902e-115">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2902e-116">当使用 `+=` 运算符时，可能无法确定是进行加法还是字符串串联。</span><span class="sxs-lookup"><span data-stu-id="2902e-116">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="2902e-117">使用 `&=` 运算符进行串联以消除多义性，并提供自文档代码。</span><span class="sxs-lookup"><span data-stu-id="2902e-117">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="2902e-118">如果编译环境强制执行严格语义，则此赋值运算符隐式执行扩大但不进行收缩转换。</span><span class="sxs-lookup"><span data-stu-id="2902e-118">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="2902e-119">有关这些转换的详细信息，请参阅[扩大和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="2902e-119">For more information on these conversions, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="2902e-120">有关严格语义和许可语义的详细信息，请参阅[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="2902e-120">For more information on strict and permissive semantics, see [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="2902e-121">如果允许使用允许的语义，则 `+=` 运算符将隐式执行与 `+` 运算符执行的各种字符串和数值转换。</span><span class="sxs-lookup"><span data-stu-id="2902e-121">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="2902e-122">有关这些转换的详细信息，请参阅[+ 运算符](../../../visual-basic/language-reference/operators/addition-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="2902e-122">For details on these conversions, see [+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="2902e-123">重载</span><span class="sxs-lookup"><span data-stu-id="2902e-123">Overloading</span></span>  
 <span data-ttu-id="2902e-124">可以*重载*`+` 运算符，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="2902e-124">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="2902e-125">重载 `+` 运算符会影响 `+=` 运算符的行为。</span><span class="sxs-lookup"><span data-stu-id="2902e-125">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="2902e-126">如果你的代码在重载 `+`的类或结构上使用 `+=`，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="2902e-126">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="2902e-127">有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="2902e-127">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2902e-128">示例</span><span class="sxs-lookup"><span data-stu-id="2902e-128">Example</span></span>  
 <span data-ttu-id="2902e-129">下面的示例使用 `+=` 运算符将一个变量的值与另一个变量组合在一起。</span><span class="sxs-lookup"><span data-stu-id="2902e-129">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="2902e-130">第一部分使用带有数值变量的 `+=` 将一个值添加到另一个值。</span><span class="sxs-lookup"><span data-stu-id="2902e-130">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="2902e-131">第二部分将 `+=` 与 `String` 变量一起使用，以将一个值与另一个值连接起来。</span><span class="sxs-lookup"><span data-stu-id="2902e-131">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="2902e-132">在这两种情况下，都会将结果赋给第一个变量。</span><span class="sxs-lookup"><span data-stu-id="2902e-132">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 <span data-ttu-id="2902e-133">`num1` 的值现在为13，`str1` 的值现在为 "103"。</span><span class="sxs-lookup"><span data-stu-id="2902e-133">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2902e-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2902e-134">See also</span></span>

- [<span data-ttu-id="2902e-135">+ 运算符</span><span class="sxs-lookup"><span data-stu-id="2902e-135">+ Operator</span></span>](../../../visual-basic/language-reference/operators/addition-operator.md)
- [<span data-ttu-id="2902e-136">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="2902e-136">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="2902e-137">算术运算符</span><span class="sxs-lookup"><span data-stu-id="2902e-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="2902e-138">串联运算符</span><span class="sxs-lookup"><span data-stu-id="2902e-138">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="2902e-139">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="2902e-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="2902e-140">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="2902e-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="2902e-141">语句</span><span class="sxs-lookup"><span data-stu-id="2902e-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
