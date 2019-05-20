---
title: 运算符 - C# 编程指南
ms.custom: seodec18
ms.date: 04/30/2019
helpviewer_keywords:
- operators [C#]
- C# language, operators
- operators [C#], about operators
ms.assetid: 214e7b83-1a41-4f7c-9867-64e9c0bab39f
ms.openlocfilehash: fd10999066f599d819ef188e09028c64c6a5e9e6
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2019
ms.locfileid: "65064043"
---
# <a name="operators-c-programming-guide"></a><span data-ttu-id="5e415-102">运算符（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="5e415-102">Operators (C# Programming Guide)</span></span>

<span data-ttu-id="5e415-103">在 C# 中，运算符  是应用于表达式或语句中的一个或多个操作数  的程序元素。</span><span class="sxs-lookup"><span data-stu-id="5e415-103">In C#, an *operator* is a program element that is applied to one or more *operands* in an expression or statement.</span></span> <span data-ttu-id="5e415-104">接受一个操作数的运算符称为`++`一元 `new`运算符，例如递增运算符 ( *) 或* 。</span><span class="sxs-lookup"><span data-stu-id="5e415-104">Operators that take one operand, such as the increment operator (`++`) or `new`, are referred to as *unary* operators.</span></span> <span data-ttu-id="5e415-105">接受两个操作数的运算符称为`+`二元`-`运算符，例如算术运算符（`*`、`/`、 *、* ）。</span><span class="sxs-lookup"><span data-stu-id="5e415-105">Operators that take two operands, such as arithmetic operators (`+`,`-`,`*`,`/`), are referred to as *binary* operators.</span></span> <span data-ttu-id="5e415-106">条件运算符`?:`接受三个操作数，是 C# 中唯一的三元运算符。</span><span class="sxs-lookup"><span data-stu-id="5e415-106">One operator, the conditional operator (`?:`), takes three operands and is the sole ternary operator in C#.</span></span>  
  
 <span data-ttu-id="5e415-107">下面的 C# 语句包含一个一元运算符和一个操作数。</span><span class="sxs-lookup"><span data-stu-id="5e415-107">The following C# statement contains a single unary operator and a single operand.</span></span> <span data-ttu-id="5e415-108">递增运算符 `++`修改操作数 `y`的值。</span><span class="sxs-lookup"><span data-stu-id="5e415-108">The increment operator, `++`, modifies the value of the operand `y`.</span></span>  
  
 [!code-csharp[csProgGuideStatements#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#5)]  
  
 <span data-ttu-id="5e415-109">下面的 C# 语句包含两个二元运算符，它们分别有两个操作数。</span><span class="sxs-lookup"><span data-stu-id="5e415-109">The following C# statement contains two binary operators, each with two operands.</span></span> <span data-ttu-id="5e415-110">赋值运算符 `=` 将一个整数变量 `y` 和一个表达式 `2 + 3` 作为操作数。</span><span class="sxs-lookup"><span data-stu-id="5e415-110">The assignment operator, `=`, has the integer variable `y` and the expression `2 + 3` as operands.</span></span> <span data-ttu-id="5e415-111">表达式 `2 + 3` 本身由加法运算符和两个操作数 `2` 和 `3` 组成。</span><span class="sxs-lookup"><span data-stu-id="5e415-111">The expression `2 + 3` itself consists of the addition operator and two operands, `2` and `3`.</span></span>  
  
 [!code-csharp[csProgGuideStatements#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#6)]  
  
<span data-ttu-id="5e415-112">操作数可以是由任何长度的代码组成的有效表达式，且可包含任意数量的子表达式。</span><span class="sxs-lookup"><span data-stu-id="5e415-112">An operand can be a valid expression that is composed of any length of code, and it can comprise any number of sub expressions.</span></span> <span data-ttu-id="5e415-113">在包含多个运算符的表达式中，运算符的应用顺序由运算符优先级 、关联性 和括号确定。</span><span class="sxs-lookup"><span data-stu-id="5e415-113">In an expression that contains multiple operators, the order in which the operators are applied is determined by *operator precedence*, *associativity*, and parentheses.</span></span>  

## <a name="operator-precedence"></a><span data-ttu-id="5e415-114">运算符优先级</span><span class="sxs-lookup"><span data-stu-id="5e415-114">Operator precedence</span></span>
  
<span data-ttu-id="5e415-115">每个运算符都具有已定义的优先级。</span><span class="sxs-lookup"><span data-stu-id="5e415-115">Each operator has a defined precedence.</span></span> <span data-ttu-id="5e415-116">在包含具有不同优先级级别的多个运算符的表达式中，运算符的优先级确定运算符的计算顺序。</span><span class="sxs-lookup"><span data-stu-id="5e415-116">In an expression that contains multiple operators that have different precedence levels, the precedence of the operators determines the order in which the operators are evaluated.</span></span> <span data-ttu-id="5e415-117">例如，下列语句将 3 赋给 `n1`：</span><span class="sxs-lookup"><span data-stu-id="5e415-117">For example, the following statement assigns 3 to `n1`:</span></span>

```csharp
n1 = 11 - 2 * 4;
```

<span data-ttu-id="5e415-118">因为乘法的优先级高于减法，所以首先执行乘法。</span><span class="sxs-lookup"><span data-stu-id="5e415-118">The multiplication is executed first because multiplication takes precedence over subtraction.</span></span>

<span data-ttu-id="5e415-119">要了解按优先级排序的完整 C# 运算符列表，请参阅 [C# 运算符](../../language-reference/operators/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5e415-119">For the complete list of C# operators ordered by precedence level, see [C# operators](../../language-reference/operators/index.md).</span></span>
  
## <a name="associativity"></a><span data-ttu-id="5e415-120">结合性</span><span class="sxs-lookup"><span data-stu-id="5e415-120">Associativity</span></span>

 <span data-ttu-id="5e415-121">当表达式中出现两个或两个以上具有相同优先级的运算符时，将根据结合性计算它们。</span><span class="sxs-lookup"><span data-stu-id="5e415-121">When two or more operators that have the same precedence are present in an expression, they are evaluated based on associativity.</span></span> <span data-ttu-id="5e415-122">左结合运算符按从左到右的顺序计算。</span><span class="sxs-lookup"><span data-stu-id="5e415-122">Left-associative operators are evaluated in order from left to right.</span></span> <span data-ttu-id="5e415-123">例如，`x * y / z` 将计算为 `(x * y) / z`。</span><span class="sxs-lookup"><span data-stu-id="5e415-123">For example, `x * y / z` is evaluated as `(x * y) / z`.</span></span> <span data-ttu-id="5e415-124">右结合运算符按从右到左的顺序计算。</span><span class="sxs-lookup"><span data-stu-id="5e415-124">Right-associative operators are evaluated in order from right to left.</span></span> <span data-ttu-id="5e415-125">例如，赋值运算符是右关联的。</span><span class="sxs-lookup"><span data-stu-id="5e415-125">For example, the assignment operator is right associative.</span></span> <span data-ttu-id="5e415-126">如果不是，下面的代码将导致错误。</span><span class="sxs-lookup"><span data-stu-id="5e415-126">If it were not, the following code would result in an error.</span></span>  
  
```csharp  
int a, b, c;  
c = 1;  
// The following two lines are equivalent.  
a = b = c;  
a = (b = c);  
  
// The following line, which forces left associativity, causes an error.  
//(a = b) = c;  
```  
  
 <span data-ttu-id="5e415-127">再举一个例子，三元运算符 ([?:](../../../csharp/language-reference/operators/conditional-operator.md)) 是右结合运算符。</span><span class="sxs-lookup"><span data-stu-id="5e415-127">As another example the ternary operator ([?:](../../../csharp/language-reference/operators/conditional-operator.md)) is right associative.</span></span> <span data-ttu-id="5e415-128">大多数的二元运算符是左结合运算符。</span><span class="sxs-lookup"><span data-stu-id="5e415-128">Most binary operators are left associative.</span></span>  
  
 <span data-ttu-id="5e415-129">无论表达式中的运算符是左结合运算符还是右结合运算符，都将先从左至右评估各表达式的操作数。</span><span class="sxs-lookup"><span data-stu-id="5e415-129">Whether the operators in an expression are left associative or right associative, the operands of each expression are evaluated first, from left to right.</span></span> <span data-ttu-id="5e415-130">以下示例显示运算符和操作数的计算顺序。</span><span class="sxs-lookup"><span data-stu-id="5e415-130">The following examples illustrate the order of evaluation of operators and operands.</span></span>  
  
|<span data-ttu-id="5e415-131">语句</span><span class="sxs-lookup"><span data-stu-id="5e415-131">Statement</span></span>|<span data-ttu-id="5e415-132">计算顺序</span><span class="sxs-lookup"><span data-stu-id="5e415-132">Order of evaluation</span></span>|  
|---------------|-------------------------|  
|`a = b`|<span data-ttu-id="5e415-133">a、b、=</span><span class="sxs-lookup"><span data-stu-id="5e415-133">a, b, =</span></span>|  
|`a = b + c`|<span data-ttu-id="5e415-134">a、b、c、+、=</span><span class="sxs-lookup"><span data-stu-id="5e415-134">a, b, c, +, =</span></span>|  
|`a = b + c * d`|<span data-ttu-id="5e415-135">a、b、c、d、\*、+、=</span><span class="sxs-lookup"><span data-stu-id="5e415-135">a, b, c, d, \*, +, =</span></span>|  
|`a = b * c + d`|<span data-ttu-id="5e415-136">a、b、c、\*、d、+、=</span><span class="sxs-lookup"><span data-stu-id="5e415-136">a, b, c, \*, d, +, =</span></span>|  
|`a = b - c + d`|<span data-ttu-id="5e415-137">a、b、c、-、d、+、=</span><span class="sxs-lookup"><span data-stu-id="5e415-137">a, b, c, -, d, +, =</span></span>|  
|`a += b -= c`|<span data-ttu-id="5e415-138">a、b、c、-=、+=</span><span class="sxs-lookup"><span data-stu-id="5e415-138">a, b, c, -=, +=</span></span>|  
  
## <a name="adding-parentheses"></a><span data-ttu-id="5e415-139">添加括号</span><span class="sxs-lookup"><span data-stu-id="5e415-139">Adding parentheses</span></span>

 <span data-ttu-id="5e415-140">可通过使用圆括号更改运算符优先级和相关性。</span><span class="sxs-lookup"><span data-stu-id="5e415-140">You can change the order imposed by operator precedence and associativity by using parentheses.</span></span> <span data-ttu-id="5e415-141">例如，`2 + 3 * 2` 通常计算结果为 8，因为乘法运算符的优先级高于加法运算符。</span><span class="sxs-lookup"><span data-stu-id="5e415-141">For example, `2 + 3 * 2` ordinarily evaluates to 8, because multiplicative operators take precedence over additive operators.</span></span> <span data-ttu-id="5e415-142">但是，如果你将表达式编写为 `(2 + 3) * 2`，则先计算加法，再计算乘法，且结果为 10。</span><span class="sxs-lookup"><span data-stu-id="5e415-142">However, if you write the expression as `(2 + 3) * 2`, the addition is evaluated before the multiplication, and the result is 10.</span></span> <span data-ttu-id="5e415-143">以下示例显示括号表达式中的计算顺序。</span><span class="sxs-lookup"><span data-stu-id="5e415-143">The following examples illustrate the order of evaluation in parenthesized expressions.</span></span> <span data-ttu-id="5e415-144">如前面的示例中所示，计算操作数之前会应用运算符。</span><span class="sxs-lookup"><span data-stu-id="5e415-144">As in previous examples, the operands are evaluated before the operator is applied.</span></span>  
  
|<span data-ttu-id="5e415-145">语句</span><span class="sxs-lookup"><span data-stu-id="5e415-145">Statement</span></span>|<span data-ttu-id="5e415-146">计算顺序</span><span class="sxs-lookup"><span data-stu-id="5e415-146">Order of evaluation</span></span>|  
|---------------|-------------------------|  
|`a = (b + c) * d`|<span data-ttu-id="5e415-147">a、b、c、+、d、\*、=</span><span class="sxs-lookup"><span data-stu-id="5e415-147">a, b, c, +, d, \*, =</span></span>|  
|`a = b - (c + d)`|<span data-ttu-id="5e415-148">a、b、c、d、+、-、=</span><span class="sxs-lookup"><span data-stu-id="5e415-148">a, b, c, d, +, -, =</span></span>|  
|`a = (b + c) * (d - e)`|<span data-ttu-id="5e415-149">a、b、c、+、d、e、-、\*、=</span><span class="sxs-lookup"><span data-stu-id="5e415-149">a, b, c, +, d, e, -, \*, =</span></span>|  
  
## <a name="operator-overloading"></a><span data-ttu-id="5e415-150">运算符重载</span><span class="sxs-lookup"><span data-stu-id="5e415-150">Operator overloading</span></span>

<span data-ttu-id="5e415-151">可以为自定义类和结构定义特定运算符的行为。</span><span class="sxs-lookup"><span data-stu-id="5e415-151">You can define the behavior of certain operators for custom classes and structs.</span></span> <span data-ttu-id="5e415-152">此过程称为“运算符重载” 。</span><span class="sxs-lookup"><span data-stu-id="5e415-152">This process is referred to as *operator overloading*.</span></span> <span data-ttu-id="5e415-153">有关详细信息，请参阅[可重载运算符](overloadable-operators.md)和[运算符](../../language-reference/keywords/operator.md)关键字文章。</span><span class="sxs-lookup"><span data-stu-id="5e415-153">For more information, see [Overloadable operators](overloadable-operators.md) and the [operator](../../language-reference/keywords/operator.md) keyword article.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5e415-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e415-154">See also</span></span>

- [<span data-ttu-id="5e415-155">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5e415-155">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5e415-156">语句、表达式和运算符</span><span class="sxs-lookup"><span data-stu-id="5e415-156">Statements, Expressions, and Operators</span></span>](index.md)
- [<span data-ttu-id="5e415-157">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="5e415-157">C# Operators</span></span>](../../language-reference/operators/index.md)
- [<span data-ttu-id="5e415-158">运算符关键字</span><span class="sxs-lookup"><span data-stu-id="5e415-158">Operator Keywords</span></span>](../../language-reference/keywords/operator-keywords.md)
