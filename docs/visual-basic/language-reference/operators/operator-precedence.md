---
title: Visual Basic 中的运算符优先级
ms.date: 07/20/2015
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
ms.openlocfilehash: 568927eb4759c214311ad34a5b45e28094dd80be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013525"
---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="a6031-102">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="a6031-102">Operator Precedence in Visual Basic</span></span>
<span data-ttu-id="a6031-103">如果在表达式中出现多个运算，每个部分进行计算，并在预先确定的顺序调用中解析*运算符优先级*。</span><span class="sxs-lookup"><span data-stu-id="a6031-103">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>  
  
## <a name="precedence-rules"></a><span data-ttu-id="a6031-104">优先规则</span><span class="sxs-lookup"><span data-stu-id="a6031-104">Precedence Rules</span></span>  
 <span data-ttu-id="a6031-105">当表达式包含多个类别中的运算符时，它们会根据以下规则进行评估：</span><span class="sxs-lookup"><span data-stu-id="a6031-105">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>  
  
- <span data-ttu-id="a6031-106">算术运算和串联运算符具有下面部分中所述的优先顺序，都具有更高的优先级高于比较、 逻辑和位运算符。</span><span class="sxs-lookup"><span data-stu-id="a6031-106">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>  
  
- <span data-ttu-id="a6031-107">所有比较运算符都具有相同的优先级，以及所有都具有更高的优先级高于逻辑运算符和位运算符，但算术运算和串联运算符的优先顺序更低。</span><span class="sxs-lookup"><span data-stu-id="a6031-107">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>  
  
- <span data-ttu-id="a6031-108">逻辑和位运算符具有下面部分中所述的优先顺序，并且所有优先级低于算术运算符、 串联和比较运算符。</span><span class="sxs-lookup"><span data-stu-id="a6031-108">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>  
  
- <span data-ttu-id="a6031-109">具有相同的优先级的运算符左到右求值表达式中出现的顺序。</span><span class="sxs-lookup"><span data-stu-id="a6031-109">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>  
  
## <a name="precedence-order"></a><span data-ttu-id="a6031-110">优先顺序</span><span class="sxs-lookup"><span data-stu-id="a6031-110">Precedence Order</span></span>  
 <span data-ttu-id="a6031-111">运算符按以下优先顺序计算：</span><span class="sxs-lookup"><span data-stu-id="a6031-111">Operators are evaluated in the following order of precedence:</span></span>  
  
### <a name="await-operator"></a><span data-ttu-id="a6031-112">Await 运算符</span><span class="sxs-lookup"><span data-stu-id="a6031-112">Await Operator</span></span>  
 <span data-ttu-id="a6031-113">Await</span><span class="sxs-lookup"><span data-stu-id="a6031-113">Await</span></span>  
  
### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="a6031-114">算术运算符和串联运算符</span><span class="sxs-lookup"><span data-stu-id="a6031-114">Arithmetic and Concatenation Operators</span></span>  
 <span data-ttu-id="a6031-115">求幂 (`^`)</span><span class="sxs-lookup"><span data-stu-id="a6031-115">Exponentiation (`^`)</span></span>  
  
 <span data-ttu-id="a6031-116">一元标识和求反 (`+`， `–`)</span><span class="sxs-lookup"><span data-stu-id="a6031-116">Unary identity and negation (`+`, `–`)</span></span>  
  
 <span data-ttu-id="a6031-117">乘法和浮点除法 (`*`， `/`)</span><span class="sxs-lookup"><span data-stu-id="a6031-117">Multiplication and floating-point division (`*`, `/`)</span></span>  
  
 <span data-ttu-id="a6031-118">整数除法 (`\`)</span><span class="sxs-lookup"><span data-stu-id="a6031-118">Integer division (`\`)</span></span>  
  
 <span data-ttu-id="a6031-119">取模算术 (`Mod`)</span><span class="sxs-lookup"><span data-stu-id="a6031-119">Modulus arithmetic (`Mod`)</span></span>  
  
 <span data-ttu-id="a6031-120">加法和减法 (`+`， `–`)</span><span class="sxs-lookup"><span data-stu-id="a6031-120">Addition and subtraction (`+`, `–`)</span></span>  
  
 <span data-ttu-id="a6031-121">字符串串联 (`&`)</span><span class="sxs-lookup"><span data-stu-id="a6031-121">String concatenation (`&`)</span></span>  
  
 <span data-ttu-id="a6031-122">算术移位 (`<<`， `>>`)</span><span class="sxs-lookup"><span data-stu-id="a6031-122">Arithmetic bit shift (`<<`, `>>`)</span></span>  
  
### <a name="comparison-operators"></a><span data-ttu-id="a6031-123">比较运算符</span><span class="sxs-lookup"><span data-stu-id="a6031-123">Comparison Operators</span></span>  
 <span data-ttu-id="a6031-124">所有比较运算符 (`=`， `<>`， `<`， `<=`， `>`， `>=`， `Is`， `IsNot`， `Like`， `TypeOf`...`Is`)</span><span class="sxs-lookup"><span data-stu-id="a6031-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>  
  
### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="a6031-125">逻辑运算符和位运算符</span><span class="sxs-lookup"><span data-stu-id="a6031-125">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="a6031-126">求反 (`Not`)</span><span class="sxs-lookup"><span data-stu-id="a6031-126">Negation (`Not`)</span></span>  
  
 <span data-ttu-id="a6031-127">一起使用 (`And`， `AndAlso`)</span><span class="sxs-lookup"><span data-stu-id="a6031-127">Conjunction (`And`, `AndAlso`)</span></span>  
  
 <span data-ttu-id="a6031-128">包含析取 (`Or`， `OrElse`)</span><span class="sxs-lookup"><span data-stu-id="a6031-128">Inclusive disjunction (`Or`, `OrElse`)</span></span>  
  
 <span data-ttu-id="a6031-129">异或运算 (`Xor`)</span><span class="sxs-lookup"><span data-stu-id="a6031-129">Exclusive disjunction (`Xor`)</span></span>  
  
### <a name="comments"></a><span data-ttu-id="a6031-130">注释</span><span class="sxs-lookup"><span data-stu-id="a6031-130">Comments</span></span>  
 <span data-ttu-id="a6031-131">`=`运算符只是相等性比较运算符，不是赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="a6031-131">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="a6031-132">字符串串联运算符 (`&`) 不是算术运算符，但它在优先级方面与算术运算符一组。</span><span class="sxs-lookup"><span data-stu-id="a6031-132">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>  
  
 <span data-ttu-id="a6031-133">`Is`和`IsNot`运算符是对象的引用比较运算符。</span><span class="sxs-lookup"><span data-stu-id="a6031-133">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="a6031-134">它们不比较两个对象; 的值它们检查仅以确定两个对象变量是否引用相同的对象实例。</span><span class="sxs-lookup"><span data-stu-id="a6031-134">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>  
  
## <a name="associativity"></a><span data-ttu-id="a6031-135">结合性</span><span class="sxs-lookup"><span data-stu-id="a6031-135">Associativity</span></span>  
 <span data-ttu-id="a6031-136">当相同优先级的运算符一起出现在表达式中，例如乘法和除法，编译器将计算每个操作遇到它从左到右。</span><span class="sxs-lookup"><span data-stu-id="a6031-136">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="a6031-137">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="a6031-137">The following example illustrates this.</span></span>  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 <span data-ttu-id="a6031-138">第一个表达式的计算结果除法 96 / 8 （这会导致 12），然后划分为 12 / 4 中，这样，在三个。</span><span class="sxs-lookup"><span data-stu-id="a6031-138">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="a6031-139">由于编译器将计算的操作`n1`计算从左到右，是相同的显式指示该顺序`n2`。</span><span class="sxs-lookup"><span data-stu-id="a6031-139">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="a6031-140">这两`n1`和`n2`具有三个结果。</span><span class="sxs-lookup"><span data-stu-id="a6031-140">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="a6031-141">与此相反，`n3`的结果为 48，是因为在圆括号强制编译器可以计算 8 / 4 第一个。</span><span class="sxs-lookup"><span data-stu-id="a6031-141">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>  
  
 <span data-ttu-id="a6031-142">由于此行为，运算符被称为*左结合运算符*在 Visual Basic 中。</span><span class="sxs-lookup"><span data-stu-id="a6031-142">Because of this behavior, operators are said to be *left associative* in Visual Basic.</span></span>  
  
## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="a6031-143">重写优先级和结合性</span><span class="sxs-lookup"><span data-stu-id="a6031-143">Overriding Precedence and Associativity</span></span>  
 <span data-ttu-id="a6031-144">可以使用括号强制先于其他计算的表达式的某些部分。</span><span class="sxs-lookup"><span data-stu-id="a6031-144">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="a6031-145">这可重写的优先顺序和左的关联性。</span><span class="sxs-lookup"><span data-stu-id="a6031-145">This can override both the order of precedence and the left associativity.</span></span> <span data-ttu-id="a6031-146">Visual Basic 始终执行括在括号外之前的操作。</span><span class="sxs-lookup"><span data-stu-id="a6031-146">Visual Basic always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="a6031-147">但是，在括号内，它将保留普通优先级和关联性，除非使用括号中的括号。</span><span class="sxs-lookup"><span data-stu-id="a6031-147">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="a6031-148">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="a6031-148">The following example illustrates this.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a6031-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6031-149">See also</span></span>

- [<span data-ttu-id="a6031-150">= 运算符</span><span class="sxs-lookup"><span data-stu-id="a6031-150">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [<span data-ttu-id="a6031-151">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="a6031-151">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="a6031-152">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="a6031-152">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="a6031-153">Like 运算符</span><span class="sxs-lookup"><span data-stu-id="a6031-153">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="a6031-154">TypeOf 运算符</span><span class="sxs-lookup"><span data-stu-id="a6031-154">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="a6031-155">Await 运算符</span><span class="sxs-lookup"><span data-stu-id="a6031-155">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)
- [<span data-ttu-id="a6031-156">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="a6031-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="a6031-157">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="a6031-157">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
