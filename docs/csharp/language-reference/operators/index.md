---
title: "C# 运算符"
ms.date: 03/09/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f18c2332f3576847800423c5c0bf7471bf37aafc
ms.sourcegitcommit: 15316053918995cc1380163a7d7e7edd5c44e6d7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2018
---
# <a name="c-operators"></a><span data-ttu-id="db46a-102">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="db46a-102">C# Operators</span></span>
<span data-ttu-id="db46a-103">C# 提供了许多运算符，这些运算符是指定要在表达式中执行哪些操作（数学、索引、函数调用等等）的符号。</span><span class="sxs-lookup"><span data-stu-id="db46a-103">C# provides many operators, which are symbols that specify which operations (math, indexing, function call, etc.) to perform in an expression.</span></span>  <span data-ttu-id="db46a-104">可以[重载](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)许多应用于用户定义类型的运算符，从而更改其含义。</span><span class="sxs-lookup"><span data-stu-id="db46a-104">You can [overload](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md) many operators to change their meaning when applied to a user-defined type.</span></span>  
  
 <span data-ttu-id="db46a-105">对整数类型执行的运算（如 `==`、`!=`、`<`、`>`、`&`、`|`）通常也可对枚举 (`enum`) 类型执行。</span><span class="sxs-lookup"><span data-stu-id="db46a-105">Operations on integral types (such as `==`, `!=`, `<`, `>`, `&`, `|`) are generally allowed on enumeration (`enum`) types.</span></span>  
  
 <span data-ttu-id="db46a-106">以下章节按最高优先级到最低优先级的顺序列示 C# 运算符。</span><span class="sxs-lookup"><span data-stu-id="db46a-106">The sections lists the C# operators starting with the highest precedence to the lowest.</span></span>  <span data-ttu-id="db46a-107">各章节内运算符的优先级相同。</span><span class="sxs-lookup"><span data-stu-id="db46a-107">The operators within each section share the same precedence level.</span></span>  
  
## <a name="primary-operators"></a><span data-ttu-id="db46a-108">主要运算符</span><span class="sxs-lookup"><span data-stu-id="db46a-108">Primary Operators</span></span>  
 <span data-ttu-id="db46a-109">以下是具有最高优先级的运算符。</span><span class="sxs-lookup"><span data-stu-id="db46a-109">These are the highest precedence operators.</span></span>  <span data-ttu-id="db46a-110">请注意，你可以单击运算符转到包含示例的详细页面。</span><span class="sxs-lookup"><span data-stu-id="db46a-110">NOTE, you can click on the operators to go the detailed pages with examples.</span></span>  
  
 <span data-ttu-id="db46a-111">[x.y](../../../csharp/language-reference/operators/member-access-operator.md)：成员访问。</span><span class="sxs-lookup"><span data-stu-id="db46a-111">[x.y](../../../csharp/language-reference/operators/member-access-operator.md) – member access.</span></span>  
  
 <span data-ttu-id="db46a-112">[x?.y](../../../csharp/language-reference/operators/null-conditional-operators.md)：null 条件成员访问。</span><span class="sxs-lookup"><span data-stu-id="db46a-112">[x?.y](../../../csharp/language-reference/operators/null-conditional-operators.md) – null conditional member access.</span></span>  <span data-ttu-id="db46a-113">如果左操作数为 `null`，则返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="db46a-113">Returns `null` if the left-hand operand is `null`.</span></span>  
 
 <span data-ttu-id="db46a-114">[x?[y]](../../../csharp/language-reference/operators/null-conditional-operators.md)：null 条件索引访问。</span><span class="sxs-lookup"><span data-stu-id="db46a-114">[x?[y]](../../../csharp/language-reference/operators/null-conditional-operators.md) - null conditional index access.</span></span> <span data-ttu-id="db46a-115">如果左操作数为 `null`，则返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="db46a-115">Returns `null` if the left-hand operand is `null`.</span></span>
 
 <span data-ttu-id="db46a-116">[f(x)](../../../csharp/language-reference/operators/invocation-operator.md)：函数调用。</span><span class="sxs-lookup"><span data-stu-id="db46a-116">[f(x)](../../../csharp/language-reference/operators/invocation-operator.md) – function invocation.</span></span>  
  
 <span data-ttu-id="db46a-117">[a&#91;x&#93;](../../../csharp/language-reference/operators/index-operator.md)：聚合对象索引。</span><span class="sxs-lookup"><span data-stu-id="db46a-117">[a&#91;x&#93;](../../../csharp/language-reference/operators/index-operator.md) – aggregate object indexing.</span></span>  
   
 <span data-ttu-id="db46a-118">[x++](../../../csharp/language-reference/operators/increment-operator.md)：后缀递增。</span><span class="sxs-lookup"><span data-stu-id="db46a-118">[x++](../../../csharp/language-reference/operators/increment-operator.md) – postfix increment.</span></span>  <span data-ttu-id="db46a-119">先返回 x 值，然后用加 1（通常加整数 1）后的 x 值更新存储位置。</span><span class="sxs-lookup"><span data-stu-id="db46a-119">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>  
  
 <span data-ttu-id="db46a-120">[x--](../../../csharp/language-reference/operators/decrement-operator.md)：后缀递减。</span><span class="sxs-lookup"><span data-stu-id="db46a-120">[x--](../../../csharp/language-reference/operators/decrement-operator.md) –  postfix decrement.</span></span>  <span data-ttu-id="db46a-121">先返回 x 值，然后用减 1（通常减整数 1）后的 x 值更新存储位置。</span><span class="sxs-lookup"><span data-stu-id="db46a-121">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>  
  
 <span data-ttu-id="db46a-122">[new](../../../csharp/language-reference/keywords/new-operator.md)：类型实例化。</span><span class="sxs-lookup"><span data-stu-id="db46a-122">[new](../../../csharp/language-reference/keywords/new-operator.md) – type instantiation.</span></span>  
  
 <span data-ttu-id="db46a-123">[typeof](../../../csharp/language-reference/keywords/typeof.md)：返回表示操作数的 System.Type 对象。</span><span class="sxs-lookup"><span data-stu-id="db46a-123">[typeof](../../../csharp/language-reference/keywords/typeof.md) – returns the System.Type object representing the operand.</span></span>  
  
 <span data-ttu-id="db46a-124">[checked](../../../csharp/language-reference/keywords/checked.md)：对整数运算启用溢出检查。</span><span class="sxs-lookup"><span data-stu-id="db46a-124">[checked](../../../csharp/language-reference/keywords/checked.md) – enables overflow checking for integer operations.</span></span>  
  
 <span data-ttu-id="db46a-125">[unchecked](../../../csharp/language-reference/keywords/unchecked.md)：对整数运算禁用溢出检查。</span><span class="sxs-lookup"><span data-stu-id="db46a-125">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) – disables overflow checking for integer operations.</span></span>  <span data-ttu-id="db46a-126">这是默认的编译器行为。</span><span class="sxs-lookup"><span data-stu-id="db46a-126">This is the default compiler behavior.</span></span>  
  
 <span data-ttu-id="db46a-127">[default(T)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md)：返回类型 T 的默认值，引用类型的默认值为 `null`，数值类型的默认值为 0，结构类型成员的默认填充值为 0/`null`。</span><span class="sxs-lookup"><span data-stu-id="db46a-127">[default(T)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md) – returns the default value of type T, `null` for reference types, zero for numeric types, and zero/`null` filled in members for struct types.</span></span>  
  
 <span data-ttu-id="db46a-128">[delegate](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)：声明并返回委托实例。</span><span class="sxs-lookup"><span data-stu-id="db46a-128">[delegate](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) – declares and returns a delegate instance.</span></span>  
  
 <span data-ttu-id="db46a-129">[sizeof](../../../csharp/language-reference/keywords/sizeof.md)：返回类型操作数的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="db46a-129">[sizeof](../../../csharp/language-reference/keywords/sizeof.md) – returns the size in bytes of the type operand.</span></span>  
  
 <span data-ttu-id="db46a-130">[->](../../../csharp/language-reference/operators/dereference-operator.md)：指针取消引用与成员访问相结合。</span><span class="sxs-lookup"><span data-stu-id="db46a-130">[->](../../../csharp/language-reference/operators/dereference-operator.md) – pointer dereferencing combined with member access.</span></span>  
  
## <a name="unary-operators"></a><span data-ttu-id="db46a-131">一元运算符</span><span class="sxs-lookup"><span data-stu-id="db46a-131">Unary Operators</span></span>  
 <span data-ttu-id="db46a-132">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="db46a-132">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  <span data-ttu-id="db46a-133">请注意，你可以单击运算符转到包含示例的详细页面。</span><span class="sxs-lookup"><span data-stu-id="db46a-133">NOTE, you can click on the operators to go the detailed pages with examples.</span></span>  
  
 <span data-ttu-id="db46a-134">[+x](../../../csharp/language-reference/operators/addition-operator.md)：返回 x 的值。</span><span class="sxs-lookup"><span data-stu-id="db46a-134">[+x](../../../csharp/language-reference/operators/addition-operator.md) – returns the value of x.</span></span>  
  
 <span data-ttu-id="db46a-135">[-x](../../../csharp/language-reference/operators/subtraction-operator.md)：数值取反。</span><span class="sxs-lookup"><span data-stu-id="db46a-135">[-x](../../../csharp/language-reference/operators/subtraction-operator.md) – numeric negation.</span></span>  
  
 <span data-ttu-id="db46a-136">[\!x](../../../csharp/language-reference/operators/logical-negation-operator.md)：逻辑取反。</span><span class="sxs-lookup"><span data-stu-id="db46a-136">[\!x](../../../csharp/language-reference/operators/logical-negation-operator.md) – logical negation.</span></span>  
  
 <span data-ttu-id="db46a-137">[~x](../../../csharp/language-reference/operators/bitwise-complement-operator.md)：按位求补。</span><span class="sxs-lookup"><span data-stu-id="db46a-137">[~x](../../../csharp/language-reference/operators/bitwise-complement-operator.md) – bitwise complement.</span></span>  
  
 <span data-ttu-id="db46a-138">[++x](../../../csharp/language-reference/operators/increment-operator.md)：前缀递增。</span><span class="sxs-lookup"><span data-stu-id="db46a-138">[++x](../../../csharp/language-reference/operators/increment-operator.md) – prefix increment.</span></span>  <span data-ttu-id="db46a-139">先用加 1（通常加整数 1）后的 x 值更新存储位置，然后返回 x 值。</span><span class="sxs-lookup"><span data-stu-id="db46a-139">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>  
  
 <span data-ttu-id="db46a-140">[--x](../../../csharp/language-reference/operators/decrement-operator.md)：前缀递减。</span><span class="sxs-lookup"><span data-stu-id="db46a-140">[--x](../../../csharp/language-reference/operators/decrement-operator.md) – prefix decrement.</span></span>  <span data-ttu-id="db46a-141">先用减 1（通常减整数 1）后的 x 值更新存储位置，然后返回 x 值。</span><span class="sxs-lookup"><span data-stu-id="db46a-141">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>  
  
 <span data-ttu-id="db46a-142">[(T)x](../../../csharp/language-reference/operators/invocation-operator.md)：类型显式转换。</span><span class="sxs-lookup"><span data-stu-id="db46a-142">[(T)x](../../../csharp/language-reference/operators/invocation-operator.md) – type casting.</span></span>  
  
 <span data-ttu-id="db46a-143">[await](../../../csharp/language-reference/keywords/await.md)：等待 `Task`。</span><span class="sxs-lookup"><span data-stu-id="db46a-143">[await](../../../csharp/language-reference/keywords/await.md) – awaits a `Task`.</span></span>  
  
 <span data-ttu-id="db46a-144">[&x](../../../csharp/language-reference/operators/and-operator.md)：地址。</span><span class="sxs-lookup"><span data-stu-id="db46a-144">[&x](../../../csharp/language-reference/operators/and-operator.md) – address of.</span></span>  
  
 <span data-ttu-id="db46a-145">[\*x](../../../csharp/language-reference/operators/multiplication-operator.md)：取消引用。</span><span class="sxs-lookup"><span data-stu-id="db46a-145">[\*x](../../../csharp/language-reference/operators/multiplication-operator.md) – dereferencing.</span></span>  
  
## <a name="multiplicative-operators"></a><span data-ttu-id="db46a-146">乘法运算符</span><span class="sxs-lookup"><span data-stu-id="db46a-146">Multiplicative Operators</span></span>  
 <span data-ttu-id="db46a-147">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="db46a-147">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  <span data-ttu-id="db46a-148">请注意，你可以单击运算符转到包含示例的详细页面。</span><span class="sxs-lookup"><span data-stu-id="db46a-148">NOTE, you can click on the operators to go the detailed pages with examples.</span></span>  
  
 <span data-ttu-id="db46a-149">[x \* y](../../../csharp/language-reference/operators/multiplication-operator.md)：乘法。</span><span class="sxs-lookup"><span data-stu-id="db46a-149">[x \* y](../../../csharp/language-reference/operators/multiplication-operator.md) – multiplication.</span></span>  
  
 <span data-ttu-id="db46a-150">[x / y](../../../csharp/language-reference/operators/division-operator.md)：除法。</span><span class="sxs-lookup"><span data-stu-id="db46a-150">[x / y](../../../csharp/language-reference/operators/division-operator.md) – division.</span></span>  <span data-ttu-id="db46a-151">如果操作数均为整数，则结果为整数，舍去小数（例如，`-7 / 2 is -3`）。</span><span class="sxs-lookup"><span data-stu-id="db46a-151">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>  
  
 <span data-ttu-id="db46a-152">[x % y](../../../csharp/language-reference/operators/modulus-operator.md)：取模。</span><span class="sxs-lookup"><span data-stu-id="db46a-152">[x % y](../../../csharp/language-reference/operators/modulus-operator.md) – modulus.</span></span>  <span data-ttu-id="db46a-153">如果操作数均为整数，则返回 x 除以 y 后的余数。</span><span class="sxs-lookup"><span data-stu-id="db46a-153">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="db46a-154">如果 `q = x / y` 且 `r = x % y`，则 `x = q * y + r`。</span><span class="sxs-lookup"><span data-stu-id="db46a-154">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>  
  
## <a name="additive-operators"></a><span data-ttu-id="db46a-155">相加运算符</span><span class="sxs-lookup"><span data-stu-id="db46a-155">Additive Operators</span></span>  
 <span data-ttu-id="db46a-156">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="db46a-156">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  <span data-ttu-id="db46a-157">请注意，你可以单击运算符转到包含示例的详细页面。</span><span class="sxs-lookup"><span data-stu-id="db46a-157">NOTE, you can click on the operators to go the detailed pages with examples.</span></span>  
  
 <span data-ttu-id="db46a-158">[x + y](../../../csharp/language-reference/operators/addition-operator.md)：加法。</span><span class="sxs-lookup"><span data-stu-id="db46a-158">[x + y](../../../csharp/language-reference/operators/addition-operator.md) – addition.</span></span>  
  
 <span data-ttu-id="db46a-159">[x：y](../../../csharp/language-reference/operators/subtraction-operator.md)：减法。</span><span class="sxs-lookup"><span data-stu-id="db46a-159">[x – y](../../../csharp/language-reference/operators/subtraction-operator.md) – subtraction.</span></span>  
  
## <a name="shift-operators"></a><span data-ttu-id="db46a-160">移位运算符</span><span class="sxs-lookup"><span data-stu-id="db46a-160">Shift Operators</span></span>  
 <span data-ttu-id="db46a-161">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="db46a-161">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  <span data-ttu-id="db46a-162">请注意，你可以单击运算符转到包含示例的详细页面。</span><span class="sxs-lookup"><span data-stu-id="db46a-162">NOTE, you can click on the operators to go the detailed pages with examples.</span></span>  
  
 <span data-ttu-id="db46a-163">[x <\<  y](../../../csharp/language-reference/operators/left-shift-operator.md)：左移位，右侧用 0 填充。</span><span class="sxs-lookup"><span data-stu-id="db46a-163">[x <\<  y](../../../csharp/language-reference/operators/left-shift-operator.md) – shift bits left and fill with zero on the right.</span></span>  
  
 <span data-ttu-id="db46a-164">[x >> y](../../../csharp/language-reference/operators/right-shift-operator.md)：右移位。</span><span class="sxs-lookup"><span data-stu-id="db46a-164">[x >> y](../../../csharp/language-reference/operators/right-shift-operator.md) – shift bits right.</span></span>  <span data-ttu-id="db46a-165">如果左操作数是 `int` 或 `long`，则左位数补符号位。</span><span class="sxs-lookup"><span data-stu-id="db46a-165">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span>  <span data-ttu-id="db46a-166">如果左操作数是 `uint` 或 `ulong`，则左位数补零。</span><span class="sxs-lookup"><span data-stu-id="db46a-166">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>  
  
## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="db46a-167">关系和类型测试运算符</span><span class="sxs-lookup"><span data-stu-id="db46a-167">Relational and Type-testing Operators</span></span>  
 <span data-ttu-id="db46a-168">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="db46a-168">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  <span data-ttu-id="db46a-169">请注意，你可以单击运算符转到包含示例的详细页面。</span><span class="sxs-lookup"><span data-stu-id="db46a-169">NOTE, you can click on the operators to go the detailed pages with examples.</span></span>  
  
 <span data-ttu-id="db46a-170">[x \< y](../../../csharp/language-reference/operators/less-than-operator.md)：小于（如果 x 小于 y，则为 true）。</span><span class="sxs-lookup"><span data-stu-id="db46a-170">[x \< y](../../../csharp/language-reference/operators/less-than-operator.md) – less than (true if x is less than y).</span></span>  
  
 <span data-ttu-id="db46a-171">[x > y](../../../csharp/language-reference/operators/greater-than-operator.md)：大于（如果 x 大于 y，则为 true）。</span><span class="sxs-lookup"><span data-stu-id="db46a-171">[x > y](../../../csharp/language-reference/operators/greater-than-operator.md) – greater than (true if x is greater than y).</span></span>  
  
 <span data-ttu-id="db46a-172">[x \<= y](../../../csharp/language-reference/operators/less-than-equal-operator.md)：小于或等于。</span><span class="sxs-lookup"><span data-stu-id="db46a-172">[x \<= y](../../../csharp/language-reference/operators/less-than-equal-operator.md) – less than or equal to.</span></span>  
  
 <span data-ttu-id="db46a-173">[x >= y](../../../csharp/language-reference/operators/greater-than-equal-operator.md)：大于或等于。</span><span class="sxs-lookup"><span data-stu-id="db46a-173">[x >= y](../../../csharp/language-reference/operators/greater-than-equal-operator.md) – greater than or equal to.</span></span>  
  
 <span data-ttu-id="db46a-174">[is](../../../csharp/language-reference/keywords/is.md)：类型兼容性。</span><span class="sxs-lookup"><span data-stu-id="db46a-174">[is](../../../csharp/language-reference/keywords/is.md) – type compatibility.</span></span>  <span data-ttu-id="db46a-175">如果求值后的左操作数可以转换为右操作数中指定的类型（静态类型），则返回 true。</span><span class="sxs-lookup"><span data-stu-id="db46a-175">Returns true if the evaluated left operand can be cast to the type specified in the right operand (a static type).</span></span>  
  
 <span data-ttu-id="db46a-176">[as](../../../csharp/language-reference/keywords/as.md)：类型转换。</span><span class="sxs-lookup"><span data-stu-id="db46a-176">[as](../../../csharp/language-reference/keywords/as.md) – type conversion.</span></span>  <span data-ttu-id="db46a-177">返回左操作数并转换为右操作数中指定的类型（静态类型），但 `as` 返回 `null`，其中 `(T)x` 会引发异常。</span><span class="sxs-lookup"><span data-stu-id="db46a-177">Returns the left operand cast to the type specified by the right operand (a static type), but `as` returns `null` where `(T)x` would throw an exception.</span></span>  
  
## <a name="equality-operators"></a><span data-ttu-id="db46a-178">相等运算符</span><span class="sxs-lookup"><span data-stu-id="db46a-178">Equality Operators</span></span>  
 <span data-ttu-id="db46a-179">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="db46a-179">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  <span data-ttu-id="db46a-180">请注意，你可以单击运算符转到包含示例的详细页面。</span><span class="sxs-lookup"><span data-stu-id="db46a-180">NOTE, you can click on the operators to go the detailed pages with examples.</span></span>  
  
 <span data-ttu-id="db46a-181">[x == y](../../../csharp/language-reference/operators/equality-comparison-operator.md)：相等。</span><span class="sxs-lookup"><span data-stu-id="db46a-181">[x == y](../../../csharp/language-reference/operators/equality-comparison-operator.md) – equality.</span></span>  <span data-ttu-id="db46a-182">默认情况下，对于 `string` 以外的引用类型，此运算符返回引用相等（标识测试）。</span><span class="sxs-lookup"><span data-stu-id="db46a-182">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span>  <span data-ttu-id="db46a-183">但是，类型可以重载 `==`，因此，如果你想测试标识，最好对 `object` 使用 `ReferenceEquals` 方法。</span><span class="sxs-lookup"><span data-stu-id="db46a-183">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>  
  
 <span data-ttu-id="db46a-184">[x != y](../../../csharp/language-reference/operators/not-equal-operator.md)：不相等。</span><span class="sxs-lookup"><span data-stu-id="db46a-184">[x != y](../../../csharp/language-reference/operators/not-equal-operator.md) – not equal.</span></span>  <span data-ttu-id="db46a-185">请参阅有关 `==` 的注释。</span><span class="sxs-lookup"><span data-stu-id="db46a-185">See comment for `==`.</span></span>  <span data-ttu-id="db46a-186">如果某个类型重载 `==`，则它必须重载 `!=`。</span><span class="sxs-lookup"><span data-stu-id="db46a-186">If a type overloads `==`, then it must overload `!=`.</span></span>  
  
## <a name="logical-and-operator"></a><span data-ttu-id="db46a-187">逻辑 AND 运算符</span><span class="sxs-lookup"><span data-stu-id="db46a-187">Logical AND Operator</span></span>  
 <span data-ttu-id="db46a-188">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="db46a-188">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  <span data-ttu-id="db46a-189">请注意，你可以单击该运算符转到包含示例的详细页面。</span><span class="sxs-lookup"><span data-stu-id="db46a-189">NOTE, you can click on the operator to go the details page with examples.</span></span>  
  
 <span data-ttu-id="db46a-190">[x & y](../../../csharp/language-reference/operators/and-operator.md)：逻辑或位 AND。</span><span class="sxs-lookup"><span data-stu-id="db46a-190">[x & y](../../../csharp/language-reference/operators/and-operator.md) – logical or bitwise AND.</span></span>  <span data-ttu-id="db46a-191">与整数类型一起使用，并且通常允许 `enum` 类型。</span><span class="sxs-lookup"><span data-stu-id="db46a-191">Use with integer types and `enum` types is generally allowed.</span></span>  
  
## <a name="logical-xor-operator"></a><span data-ttu-id="db46a-192">逻辑 XOR 运算符</span><span class="sxs-lookup"><span data-stu-id="db46a-192">Logical XOR Operator</span></span>  
 <span data-ttu-id="db46a-193">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="db46a-193">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  <span data-ttu-id="db46a-194">请注意，你可以单击该运算符转到包含示例的详细页面。</span><span class="sxs-lookup"><span data-stu-id="db46a-194">NOTE, you can click on the operator to go the details page with examples.</span></span>  
  
 <span data-ttu-id="db46a-195">[x ^ y](../../../csharp/language-reference/operators/xor-operator.md)：逻辑或位 XOR。</span><span class="sxs-lookup"><span data-stu-id="db46a-195">[x ^ y](../../../csharp/language-reference/operators/xor-operator.md) – logical or bitwise XOR.</span></span>  <span data-ttu-id="db46a-196">通常可以将此运算符与整数类型和 `enum` 类型一起使用。</span><span class="sxs-lookup"><span data-stu-id="db46a-196">You can generally use this with integer types and `enum` types.</span></span>  
  
## <a name="logical-or-operator"></a><span data-ttu-id="db46a-197">逻辑 OR 运算符</span><span class="sxs-lookup"><span data-stu-id="db46a-197">Logical OR Operator</span></span>  
 <span data-ttu-id="db46a-198">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="db46a-198">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  <span data-ttu-id="db46a-199">请注意，你可以单击该运算符转到包含示例的详细页面。</span><span class="sxs-lookup"><span data-stu-id="db46a-199">NOTE, you can click on the operator to go the details page with examples.</span></span>  
  
 <span data-ttu-id="db46a-200">[x &#124; y](../../../csharp/language-reference/operators/or-operator.md)：逻辑或位 OR。</span><span class="sxs-lookup"><span data-stu-id="db46a-200">[x &#124; y](../../../csharp/language-reference/operators/or-operator.md) – logical or bitwise OR.</span></span>  <span data-ttu-id="db46a-201">与整数类型一起使用，并且通常允许 `enum` 类型。</span><span class="sxs-lookup"><span data-stu-id="db46a-201">Use with integer types and `enum` types is generally allowed.</span></span>  
  
## <a name="conditional-and-operator"></a><span data-ttu-id="db46a-202">条件 AND 运算符</span><span class="sxs-lookup"><span data-stu-id="db46a-202">Conditional AND Operator</span></span>  
 <span data-ttu-id="db46a-203">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="db46a-203">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  <span data-ttu-id="db46a-204">请注意，你可以单击该运算符转到包含示例的详细页面。</span><span class="sxs-lookup"><span data-stu-id="db46a-204">NOTE, you can click on the operator to go the details page with examples.</span></span>  
  
 <span data-ttu-id="db46a-205">[x && y](../../../csharp/language-reference/operators/conditional-and-operator.md)：逻辑 AND。</span><span class="sxs-lookup"><span data-stu-id="db46a-205">[x && y](../../../csharp/language-reference/operators/conditional-and-operator.md) – logical AND.</span></span>  <span data-ttu-id="db46a-206">如果第一个操作数为 false，则 C# 不对第二个操作数求值。</span><span class="sxs-lookup"><span data-stu-id="db46a-206">If the first operand is false, then C# does not evaluate the second operand.</span></span>  
  
## <a name="conditional-or-operator"></a><span data-ttu-id="db46a-207">条件 OR 运算符</span><span class="sxs-lookup"><span data-stu-id="db46a-207">Conditional OR Operator</span></span>  
 <span data-ttu-id="db46a-208">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="db46a-208">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  <span data-ttu-id="db46a-209">请注意，你可以单击该运算符转到包含示例的详细页面。</span><span class="sxs-lookup"><span data-stu-id="db46a-209">NOTE, you can click on the operator to go the details page with examples.</span></span>  
  
 <span data-ttu-id="db46a-210">[x &#124;&#124; y](../../../csharp/language-reference/operators/conditional-or-operator.md)：逻辑 OR。</span><span class="sxs-lookup"><span data-stu-id="db46a-210">[x &#124;&#124; y](../../../csharp/language-reference/operators/conditional-or-operator.md) – logical OR.</span></span>  <span data-ttu-id="db46a-211">如果第一个操作数为 true，则 C# 不对第二个操作数求值。</span><span class="sxs-lookup"><span data-stu-id="db46a-211">If the first operand is true, then C# does not evaluate the second operand.</span></span>  
  
## <a name="null-coalescing-operator"></a><span data-ttu-id="db46a-212">Null 合并运算符</span><span class="sxs-lookup"><span data-stu-id="db46a-212">Null-coalescing Operator</span></span>  
 <span data-ttu-id="db46a-213">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="db46a-213">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  <span data-ttu-id="db46a-214">请注意，你可以单击该运算符转到包含示例的详细页面。</span><span class="sxs-lookup"><span data-stu-id="db46a-214">NOTE, you can click on the operator to go the details page with examples.</span></span>  
  
 <span data-ttu-id="db46a-215">[x ?? y](../../../csharp/language-reference/operators/null-conditional-operator.md)：如果不为 `null`，则返回 `x`；否则返回 `y`。</span><span class="sxs-lookup"><span data-stu-id="db46a-215">[x ?? y](../../../csharp/language-reference/operators/null-conditional-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>  
  
## <a name="conditional-operator"></a><span data-ttu-id="db46a-216">条件运算符</span><span class="sxs-lookup"><span data-stu-id="db46a-216">Conditional Operator</span></span>  
 <span data-ttu-id="db46a-217">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="db46a-217">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  <span data-ttu-id="db46a-218">请注意，你可以单击该运算符转到包含示例的详细页面。</span><span class="sxs-lookup"><span data-stu-id="db46a-218">NOTE, you can click on the operator to go the details page with examples.</span></span>  
  
 <span data-ttu-id="db46a-219">[t ? x : y](../../../csharp/language-reference/operators/conditional-operator.md)：如果测试 `t` 为 true，则计算并返回 `x`；否则，计算并返回 `y`。</span><span class="sxs-lookup"><span data-stu-id="db46a-219">[t ? x : y](../../../csharp/language-reference/operators/conditional-operator.md) – if test `t` is true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>  
  
## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="db46a-220">赋值和 Lambda 运算符</span><span class="sxs-lookup"><span data-stu-id="db46a-220">Assignment and Lambda Operators</span></span>  
 <span data-ttu-id="db46a-221">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="db46a-221">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  <span data-ttu-id="db46a-222">请注意，你可以单击运算符转到包含示例的详细页面。</span><span class="sxs-lookup"><span data-stu-id="db46a-222">NOTE, you can click on the operators to go the detailed pages with examples.</span></span>  
  
 <span data-ttu-id="db46a-223">[x = y](../../../csharp/language-reference/operators/assignment-operator.md)：赋值。</span><span class="sxs-lookup"><span data-stu-id="db46a-223">[x = y](../../../csharp/language-reference/operators/assignment-operator.md) – assignment.</span></span>  
  
 <span data-ttu-id="db46a-224">[x += y](../../../csharp/language-reference/operators/addition-assignment-operator.md)：递增。</span><span class="sxs-lookup"><span data-stu-id="db46a-224">[x += y](../../../csharp/language-reference/operators/addition-assignment-operator.md) – increment.</span></span>  <span data-ttu-id="db46a-225">`x` 值加 `y` 值，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="db46a-225">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>  <span data-ttu-id="db46a-226">如果 `x` 指定 `event`，则 `y` 必须是 C# 作为事件处理程序添加的相应函数。</span><span class="sxs-lookup"><span data-stu-id="db46a-226">If `x` designates an `event`, then `y` must be an appropriate function that C# adds as an event handler.</span></span>  
  
 <span data-ttu-id="db46a-227">[x -= y](../../../csharp/language-reference/operators/subtraction-assignment-operator.md)：递减。</span><span class="sxs-lookup"><span data-stu-id="db46a-227">[x -= y](../../../csharp/language-reference/operators/subtraction-assignment-operator.md) – decrement.</span></span>  <span data-ttu-id="db46a-228">`x` 值减 `y` 值，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="db46a-228">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span>  <span data-ttu-id="db46a-229">如果 `x` 指定 `event`，则 `y` 必须是 C# 作为事件处理程序删除的相应函数</span><span class="sxs-lookup"><span data-stu-id="db46a-229">If `x` designates an `event`, then `y` must be an appropriate function that C# removes as an event handler</span></span>  
  
 <span data-ttu-id="db46a-230">[x \*= y](../../../csharp/language-reference/operators/multiplication-assignment-operator.md)：乘法赋值。</span><span class="sxs-lookup"><span data-stu-id="db46a-230">[x \*= y](../../../csharp/language-reference/operators/multiplication-assignment-operator.md) – multiplication assignment.</span></span>  <span data-ttu-id="db46a-231">`x` 值乘以 `y` 值，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="db46a-231">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="db46a-232">[x /= y](../../../csharp/language-reference/operators/division-assignment-operator.md)：除法赋值。</span><span class="sxs-lookup"><span data-stu-id="db46a-232">[x /= y](../../../csharp/language-reference/operators/division-assignment-operator.md) – division assignment.</span></span>  <span data-ttu-id="db46a-233">`x` 值除以 `y` 值，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="db46a-233">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="db46a-234">[x %= y](../../../csharp/language-reference/operators/modulus-assignment-operator.md)：取模赋值。</span><span class="sxs-lookup"><span data-stu-id="db46a-234">[x %= y](../../../csharp/language-reference/operators/modulus-assignment-operator.md) – modulus assignment.</span></span>  <span data-ttu-id="db46a-235">`x` 值除以 `y` 值，余数存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="db46a-235">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="db46a-236">[x &= y](../../../csharp/language-reference/operators/and-assignment-operator.md)：AND 赋值。</span><span class="sxs-lookup"><span data-stu-id="db46a-236">[x &= y](../../../csharp/language-reference/operators/and-assignment-operator.md) – AND assignment.</span></span>  <span data-ttu-id="db46a-237">`y` 值和 `x` 值相与，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="db46a-237">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="db46a-238">[x &#124;= y](../../../csharp/language-reference/operators/or-assignment-operator.md)：OR 赋值。</span><span class="sxs-lookup"><span data-stu-id="db46a-238">[x &#124;= y](../../../csharp/language-reference/operators/or-assignment-operator.md) – OR assignment.</span></span>  <span data-ttu-id="db46a-239">`y` 值和 `x` 值相或，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="db46a-239">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="db46a-240">[x ^= y](../../../csharp/language-reference/operators/xor-assignment-operator.md)：XOR 赋值。</span><span class="sxs-lookup"><span data-stu-id="db46a-240">[x ^= y](../../../csharp/language-reference/operators/xor-assignment-operator.md) – XOR assignment.</span></span>  <span data-ttu-id="db46a-241">`y` 值和 `x` 值相异或，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="db46a-241">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="db46a-242">[x <<= y](../../../csharp/language-reference/operators/left-shift-assignment-operator.md)：左移赋值。</span><span class="sxs-lookup"><span data-stu-id="db46a-242">[x <<= y](../../../csharp/language-reference/operators/left-shift-assignment-operator.md) – left-shift assignment.</span></span>  <span data-ttu-id="db46a-243">将 `x` 值向左移动 `y` 位，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="db46a-243">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="db46a-244">[x >>= y](../../../csharp/language-reference/operators/right-shift-assignment-operator.md)：右移赋值。</span><span class="sxs-lookup"><span data-stu-id="db46a-244">[x >>= y](../../../csharp/language-reference/operators/right-shift-assignment-operator.md) – right-shift assignment.</span></span>  <span data-ttu-id="db46a-245">将 `x` 值向右移动 `y` 位，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="db46a-245">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="db46a-246">[=>](../../../csharp/language-reference/operators/lambda-operator.md)：lambda 声明。</span><span class="sxs-lookup"><span data-stu-id="db46a-246">[=>](../../../csharp/language-reference/operators/lambda-operator.md) – lambda declaration.</span></span>  
  
## <a name="arithmetic-overflow"></a><span data-ttu-id="db46a-247">算术溢出</span><span class="sxs-lookup"><span data-stu-id="db46a-247">Arithmetic Overflow</span></span>  
 <span data-ttu-id="db46a-248">算术运算符（[+](../../../csharp/language-reference/operators/addition-operator.md)、[-](../../../csharp/language-reference/operators/subtraction-operator.md)、[\*](../../../csharp/language-reference/operators/multiplication-operator.md)、[/](../../../csharp/language-reference/operators/division-operator.md)）的计算结果可能会超出所涉数值类型的可取值范围。</span><span class="sxs-lookup"><span data-stu-id="db46a-248">The arithmetic operators ([+](../../../csharp/language-reference/operators/addition-operator.md), [-](../../../csharp/language-reference/operators/subtraction-operator.md), [\*](../../../csharp/language-reference/operators/multiplication-operator.md), [/](../../../csharp/language-reference/operators/division-operator.md)) can produce results that are outside the range of possible values for the numeric type involved.</span></span> <span data-ttu-id="db46a-249">详细信息应参考特定运算符的相关章节，而一般情况下：</span><span class="sxs-lookup"><span data-stu-id="db46a-249">You should refer to the section on a particular operator for details, but in general:</span></span>  
  
- <span data-ttu-id="db46a-250">整数算术溢出或者引发 <xref:System.OverflowException>，或者放弃结果的最高有效位。</span><span class="sxs-lookup"><span data-stu-id="db46a-250">Integer arithmetic overflow either throws an <xref:System.OverflowException> or discards the most significant bits of the result.</span></span> <span data-ttu-id="db46a-251">整数被零除总是引发 <xref:System.DivideByZeroException>。</span><span class="sxs-lookup"><span data-stu-id="db46a-251">Integer division by zero always throws a <xref:System.DivideByZeroException>.</span></span>  

   <span data-ttu-id="db46a-252">发生整数溢出时，具体影响视执行上下文而定，上下文可为 [checked 或 unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)。</span><span class="sxs-lookup"><span data-stu-id="db46a-252">When integer overflow occurs, what happens depends on the execution context, which can be [checked or unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md).</span></span> <span data-ttu-id="db46a-253">在 checked 上下文中引发 <xref:System.OverflowException>。</span><span class="sxs-lookup"><span data-stu-id="db46a-253">In a checked context, an <xref:System.OverflowException> is thrown.</span></span> <span data-ttu-id="db46a-254">在 unchecked 上下文中，放弃结果的最高有效位并继续执行。</span><span class="sxs-lookup"><span data-stu-id="db46a-254">In an unchecked context, the most significant bits of the result are discarded and execution continues.</span></span> <span data-ttu-id="db46a-255">因此，C# 让你有机会选择处理或忽略溢出。</span><span class="sxs-lookup"><span data-stu-id="db46a-255">Thus, C# gives you the choice of handling or ignoring overflow.</span></span> <span data-ttu-id="db46a-256">默认情况下，算术运算发生在 *unchecked* 上下文中。</span><span class="sxs-lookup"><span data-stu-id="db46a-256">By default, arithmetic operations occur in an *unchecked* context.</span></span> 

   <span data-ttu-id="db46a-257">除算术运算以外，整型类型之间的显式转换也会导致溢出（例如，将 [long](../../../csharp/language-reference/keywords/long.md) 显式转换成 [int](../../../csharp/language-reference/keywords/int.md)），并受到 checked 或 unchecked 执行的约束。</span><span class="sxs-lookup"><span data-stu-id="db46a-257">In addition to the arithmetic operations, integral-type to integral-type casts can cause overflow (such as when you cast a [long](../../../csharp/language-reference/keywords/long.md) to an [int](../../../csharp/language-reference/keywords/int.md)), and are subject to checked or unchecked execution.</span></span> <span data-ttu-id="db46a-258">但是，位运算符和移位运算符永远不会导致溢出。</span><span class="sxs-lookup"><span data-stu-id="db46a-258">However, bitwise operators and shift operators never cause overflow.</span></span>  
   
-   <span data-ttu-id="db46a-259">浮点算术溢出或被零除从不引发异常，因为浮点类型基于 IEEE 754，因此可以表示无穷大和 NaN（非数值）。</span><span class="sxs-lookup"><span data-stu-id="db46a-259">Floating-point arithmetic overflow or division by zero never throws an exception, because floating-point types are based on IEEE 754 and so have provisions for representing infinity and NaN (Not a Number).</span></span>  
  
-   <span data-ttu-id="db46a-260">[小数](../../../csharp/language-reference/keywords/decimal.md)算术溢出总是引发 <xref:System.OverflowException>。</span><span class="sxs-lookup"><span data-stu-id="db46a-260">[Decimal](../../../csharp/language-reference/keywords/decimal.md) arithmetic overflow always throws an <xref:System.OverflowException>.</span></span> <span data-ttu-id="db46a-261">小数被零除总是引发 <xref:System.DivideByZeroException>。</span><span class="sxs-lookup"><span data-stu-id="db46a-261">Decimal division by zero always throws a <xref:System.DivideByZeroException>.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="db46a-262">请参阅</span><span class="sxs-lookup"><span data-stu-id="db46a-262">See Also</span></span>  
 [<span data-ttu-id="db46a-263">C# 参考</span><span class="sxs-lookup"><span data-stu-id="db46a-263">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="db46a-264">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="db46a-264">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 <span data-ttu-id="db46a-265">[C#](../../../csharp/index.md) [可重载运算符](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)</span><span class="sxs-lookup"><span data-stu-id="db46a-265">[C#](../../../csharp/index.md) [Overloadable Operators](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)</span></span>  
 [<span data-ttu-id="db46a-266">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="db46a-266">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
