---
title: Visual Basic 中的运算符优先级
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arithmetic operators [Visual Basic], precedence
- operator precedence
- logical operators [Visual Basic], precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators [Visual Basic]
- operators [Visual Basic], precedence
- precedence [Visual Basic], of operators
- comparison operators [Visual Basic], precedence
- math operators [Visual Basic]
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d8de9deea84c7f0c11c91b55951cdfc200b017f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="5fa7c-102">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="5fa7c-102">Operator Precedence in Visual Basic</span></span>
<span data-ttu-id="5fa7c-103">如果在表达式中出现多个运算，计算和解析按预设的顺序调用每个部分*运算符优先级*。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-103">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>  
  
## <a name="precedence-rules"></a><span data-ttu-id="5fa7c-104">优先规则</span><span class="sxs-lookup"><span data-stu-id="5fa7c-104">Precedence Rules</span></span>  
 <span data-ttu-id="5fa7c-105">当表达式包含从多个类别的运算符时，它们会根据下列规则进行评估：</span><span class="sxs-lookup"><span data-stu-id="5fa7c-105">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>  
  
-   <span data-ttu-id="5fa7c-106">算术运算符和串联运算符具有的下一节中所述的优先顺序，都具有优先级高于比较、 逻辑和按位运算符。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-106">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>  
  
-   <span data-ttu-id="5fa7c-107">所有比较运算符都具有相同的优先级，以及所有都具有优先级高于逻辑运算符和位运算符，但优先级低于算术和串联运算符。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-107">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>  
  
-   <span data-ttu-id="5fa7c-108">逻辑和按位运算符具有的下一节中所述的优先顺序，都具有较低的优先级比算术、 串联和比较运算符。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-108">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>  
  
-   <span data-ttu-id="5fa7c-109">具有相等的优先级的运算符从左向右进行计算右侧表达式中出现的顺序。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-109">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>  
  
## <a name="precedence-order"></a><span data-ttu-id="5fa7c-110">优先顺序</span><span class="sxs-lookup"><span data-stu-id="5fa7c-110">Precedence Order</span></span>  
 <span data-ttu-id="5fa7c-111">按以下优先顺序计算运算符：</span><span class="sxs-lookup"><span data-stu-id="5fa7c-111">Operators are evaluated in the following order of precedence:</span></span>  
  
### <a name="await-operator"></a><span data-ttu-id="5fa7c-112">Await 运算符</span><span class="sxs-lookup"><span data-stu-id="5fa7c-112">Await Operator</span></span>  
 <span data-ttu-id="5fa7c-113">await</span><span class="sxs-lookup"><span data-stu-id="5fa7c-113">Await</span></span>  
  
### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="5fa7c-114">算术运算符和串联运算符</span><span class="sxs-lookup"><span data-stu-id="5fa7c-114">Arithmetic and Concatenation Operators</span></span>  
 <span data-ttu-id="5fa7c-115">求幂 (`^`)</span><span class="sxs-lookup"><span data-stu-id="5fa7c-115">Exponentiation (`^`)</span></span>  
  
 <span data-ttu-id="5fa7c-116">一元标识和求反 (`+`， `–`)</span><span class="sxs-lookup"><span data-stu-id="5fa7c-116">Unary identity and negation (`+`, `–`)</span></span>  
  
 <span data-ttu-id="5fa7c-117">乘法和浮点除法运算 (`*`， `/`)</span><span class="sxs-lookup"><span data-stu-id="5fa7c-117">Multiplication and floating-point division (`*`, `/`)</span></span>  
  
 <span data-ttu-id="5fa7c-118">整数除法 (`\`)</span><span class="sxs-lookup"><span data-stu-id="5fa7c-118">Integer division (`\`)</span></span>  
  
 <span data-ttu-id="5fa7c-119">取模算术 (`Mod`)</span><span class="sxs-lookup"><span data-stu-id="5fa7c-119">Modulus arithmetic (`Mod`)</span></span>  
  
 <span data-ttu-id="5fa7c-120">加法和减法 (`+`， `–`)</span><span class="sxs-lookup"><span data-stu-id="5fa7c-120">Addition and subtraction (`+`, `–`)</span></span>  
  
 <span data-ttu-id="5fa7c-121">字符串串联 (`&`)</span><span class="sxs-lookup"><span data-stu-id="5fa7c-121">String concatenation (`&`)</span></span>  
  
 <span data-ttu-id="5fa7c-122">算术移位 (`<<`， `>>`)</span><span class="sxs-lookup"><span data-stu-id="5fa7c-122">Arithmetic bit shift (`<<`, `>>`)</span></span>  
  
### <a name="comparison-operators"></a><span data-ttu-id="5fa7c-123">比较运算符</span><span class="sxs-lookup"><span data-stu-id="5fa7c-123">Comparison Operators</span></span>  
 <span data-ttu-id="5fa7c-124">所有比较运算符 (`=`， `<>`， `<`， `<=`， `>`， `>=`， `Is`， `IsNot`， `Like`， `TypeOf`...`Is`)</span><span class="sxs-lookup"><span data-stu-id="5fa7c-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>  
  
### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="5fa7c-125">逻辑和按位运算符</span><span class="sxs-lookup"><span data-stu-id="5fa7c-125">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="5fa7c-126">求反 (`Not`)</span><span class="sxs-lookup"><span data-stu-id="5fa7c-126">Negation (`Not`)</span></span>  
  
 <span data-ttu-id="5fa7c-127">结合使用 (`And`， `AndAlso`)</span><span class="sxs-lookup"><span data-stu-id="5fa7c-127">Conjunction (`And`, `AndAlso`)</span></span>  
  
 <span data-ttu-id="5fa7c-128">包含析取 (`Or`， `OrElse`)</span><span class="sxs-lookup"><span data-stu-id="5fa7c-128">Inclusive disjunction (`Or`, `OrElse`)</span></span>  
  
 <span data-ttu-id="5fa7c-129">异或结果 (`Xor`)</span><span class="sxs-lookup"><span data-stu-id="5fa7c-129">Exclusive disjunction (`Xor`)</span></span>  
  
### <a name="comments"></a><span data-ttu-id="5fa7c-130">注释</span><span class="sxs-lookup"><span data-stu-id="5fa7c-130">Comments</span></span>  
 <span data-ttu-id="5fa7c-131">`=`运算符是仅相等性比较运算符，而不是赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-131">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="5fa7c-132">字符串串联运算符 (`&`) 不是算术的运算符，但它在优先级方面与算术运算符一组。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-132">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>  
  
 <span data-ttu-id="5fa7c-133">`Is`和`IsNot`运算符是对象的引用比较运算符。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-133">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="5fa7c-134">它们不比较两个对象的值它们检查仅以确定是否两个对象变量引用同一对象实例。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-134">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>  
  
## <a name="associativity"></a><span data-ttu-id="5fa7c-135">结合性</span><span class="sxs-lookup"><span data-stu-id="5fa7c-135">Associativity</span></span>  
 <span data-ttu-id="5fa7c-136">当相等的优先级的运算符一起出现在表达式中，例如乘法和除法，编译器将评估每个操作，当它从左到右进行遇到。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-136">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="5fa7c-137">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-137">The following example illustrates this.</span></span>  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 <span data-ttu-id="5fa7c-138">第一个表达式的计算结果除法 96 / 8 （这会导致 12），然后除法 12 / 4，结果为 3。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-138">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="5fa7c-139">因为编译器将评估的操作`n1`从左到右，评估时相同为显式指明该顺序`n2`。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-139">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="5fa7c-140">同时`n1`和`n2`具有三个结果。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-140">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="5fa7c-141">与此相反，`n3`的结果为 48，是因为圆括号强制编译器可以计算 8 / 4 第一个。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-141">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>  
  
 <span data-ttu-id="5fa7c-142">由于此行为，运算符被认为是*左结合运算符*在 Visual Basic 中。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-142">Because of this behavior, operators are said to be *left associative* in Visual Basic.</span></span>  
  
## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="5fa7c-143">重写优先级和关联性</span><span class="sxs-lookup"><span data-stu-id="5fa7c-143">Overriding Precedence and Associativity</span></span>  
 <span data-ttu-id="5fa7c-144">可以使用括号来强制先于其他计算的表达式的某些部分。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-144">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="5fa7c-145">这会重写的优先顺序和左的关联性。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-145">This can override both the order of precedence and the left associativity.</span></span> <span data-ttu-id="5fa7c-146">Visual Basic 始终执行括在括号之前以外的操作。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-146">Visual Basic always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="5fa7c-147">但是，在括号内，这样可保持普通优先级和关联性，除非你使用在括号内的括号。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-147">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="5fa7c-148">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="5fa7c-148">The following example illustrates this.</span></span>  
  
```  
Dim a, b, c, d, e, f, g As Double  
a = 8.0  
b = 3.0  
c = 4.0  
d = 2.0  
e = 1.0  
f = a - b + c / d * e  
' The preceding line sets f to 7.0. Because of natural operator   
' precedence and associativity, it is exactly equivalent to the   
' following line.  
f = (a - b) + ((c / d) * e)  
' The following line overrides the natural operator precedence   
' and left associativity.  
g = (a - (b + c)) / (d * e)  
' The preceding line sets g to 0.5.  
```  
  
## <a name="see-also"></a><span data-ttu-id="5fa7c-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="5fa7c-149">See Also</span></span>  
 [<span data-ttu-id="5fa7c-150">= 运算符</span><span class="sxs-lookup"><span data-stu-id="5fa7c-150">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)  
 [<span data-ttu-id="5fa7c-151">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="5fa7c-151">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="5fa7c-152">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="5fa7c-152">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="5fa7c-153">Like 运算符</span><span class="sxs-lookup"><span data-stu-id="5fa7c-153">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="5fa7c-154">TypeOf 运算符</span><span class="sxs-lookup"><span data-stu-id="5fa7c-154">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [<span data-ttu-id="5fa7c-155">Await 运算符</span><span class="sxs-lookup"><span data-stu-id="5fa7c-155">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)  
 [<span data-ttu-id="5fa7c-156">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="5fa7c-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="5fa7c-157">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="5fa7c-157">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
