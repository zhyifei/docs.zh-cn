---
title: C# 运算符 - C# 参考
ms.date: 04/30/2019
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
ms.openlocfilehash: bc5e2c88314c2f590aeddcfd37bd04c3a7400804
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796480"
---
# <a name="c-operators-c-reference"></a><span data-ttu-id="0f181-102">C# 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="0f181-102">C# operators (C# reference)</span></span>

<span data-ttu-id="0f181-103">C# 提供了许多由内置类型支持的预定义运算符。</span><span class="sxs-lookup"><span data-stu-id="0f181-103">C# provides a number of predefined operators supported by the built-in types.</span></span> <span data-ttu-id="0f181-104">例如，[算术运算符](arithmetic-operators.md)使用内置数值类型的操作数执行算术运算，[布尔逻辑运算符](boolean-logical-operators.md)使用 [bool](../keywords/bool.md) 操作数执行逻辑运算。</span><span class="sxs-lookup"><span data-stu-id="0f181-104">For example, [arithmetic operators](arithmetic-operators.md) perform arithmetic operations with operands of built-in numeric types and [Boolean logical operators](boolean-logical-operators.md) perform logical operations with the [bool](../keywords/bool.md) operands.</span></span>

<span data-ttu-id="0f181-105">用户定义类型可以重载某些运算符来定义该类型的操作数的相应行为。</span><span class="sxs-lookup"><span data-stu-id="0f181-105">A user-defined type can overload certain operators to define the corresponding behavior for the operands of that type.</span></span> <span data-ttu-id="0f181-106">有关详细信息，请参阅[运算符重载](operator-overloading.md)。</span><span class="sxs-lookup"><span data-stu-id="0f181-106">For more information, see [Operator overloading](operator-overloading.md).</span></span>

<span data-ttu-id="0f181-107">以下各部分按最高优先级到最低优先级的顺序列出 C# 运算符。</span><span class="sxs-lookup"><span data-stu-id="0f181-107">The following sections list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="0f181-108">各章节内运算符的优先级相同。</span><span class="sxs-lookup"><span data-stu-id="0f181-108">The operators within each section share the same precedence level.</span></span>

## <a name="primary-operators"></a><span data-ttu-id="0f181-109">主要运算符</span><span class="sxs-lookup"><span data-stu-id="0f181-109">Primary operators</span></span>

<span data-ttu-id="0f181-110">以下是具有最高优先级的运算符。</span><span class="sxs-lookup"><span data-stu-id="0f181-110">These are the highest precedence operators.</span></span>

<span data-ttu-id="0f181-111">[x.y](member-access-operators.md#member-access-operator-)：成员访问。</span><span class="sxs-lookup"><span data-stu-id="0f181-111">[x.y](member-access-operators.md#member-access-operator-) – member access.</span></span>

<span data-ttu-id="0f181-112">[x?.y](member-access-operators.md#null-conditional-operators--and-)：null 条件成员访问。</span><span class="sxs-lookup"><span data-stu-id="0f181-112">[x?.y](member-access-operators.md#null-conditional-operators--and-) – null conditional member access.</span></span> <span data-ttu-id="0f181-113">如果左操作数计算结果为 `null`，则返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="0f181-113">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="0f181-114">[x?[y]](member-access-operators.md#null-conditional-operators--and-)：null 条件数组元素或类型索引器访问。</span><span class="sxs-lookup"><span data-stu-id="0f181-114">[x?[y]](member-access-operators.md#null-conditional-operators--and-) - null conditional array element or type indexer access.</span></span> <span data-ttu-id="0f181-115">如果左操作数计算结果为 `null`，则返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="0f181-115">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="0f181-116">[f(x)](member-access-operators.md#invocation-operator-)：方法调用或委托调用。</span><span class="sxs-lookup"><span data-stu-id="0f181-116">[f(x)](member-access-operators.md#invocation-operator-) – method call or delegate invocation.</span></span>

<span data-ttu-id="0f181-117">[a&#91;x&#93;](member-access-operators.md#indexer-operator-)：数组元素或类型索引器访问。</span><span class="sxs-lookup"><span data-stu-id="0f181-117">[a&#91;x&#93;](member-access-operators.md#indexer-operator-) – array element or type indexer access.</span></span>

<span data-ttu-id="0f181-118">[x++](arithmetic-operators.md#increment-operator-)：后缀递增。</span><span class="sxs-lookup"><span data-stu-id="0f181-118">[x++](arithmetic-operators.md#increment-operator-) – postfix increment.</span></span> <span data-ttu-id="0f181-119">先返回 x 值，然后用加 1（通常加整数 1）后的 x 值更新存储位置。</span><span class="sxs-lookup"><span data-stu-id="0f181-119">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="0f181-120">[x--](arithmetic-operators.md#decrement-operator---)：后缀递减。</span><span class="sxs-lookup"><span data-stu-id="0f181-120">[x--](arithmetic-operators.md#decrement-operator---) –  postfix decrement.</span></span> <span data-ttu-id="0f181-121">先返回 x 值，然后用减 1（通常减整数 1）后的 x 值更新存储位置。</span><span class="sxs-lookup"><span data-stu-id="0f181-121">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="0f181-122">[new](new-operator.md)：类型实例化。</span><span class="sxs-lookup"><span data-stu-id="0f181-122">[new](new-operator.md) – type instantiation.</span></span>

<span data-ttu-id="0f181-123">[typeof](type-testing-and-conversion-operators.md#typeof-operator) - 返回表示操作数的 <xref:System.Type> 对象。</span><span class="sxs-lookup"><span data-stu-id="0f181-123">[typeof](type-testing-and-conversion-operators.md#typeof-operator) – returns the <xref:System.Type> object representing the operand.</span></span>

<span data-ttu-id="0f181-124">[checked](../keywords/checked.md)：对整数运算启用溢出检查。</span><span class="sxs-lookup"><span data-stu-id="0f181-124">[checked](../keywords/checked.md) – enables overflow checking for integer operations.</span></span>

<span data-ttu-id="0f181-125">[unchecked](../keywords/unchecked.md)：对整数运算禁用溢出检查。</span><span class="sxs-lookup"><span data-stu-id="0f181-125">[unchecked](../keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="0f181-126">这是默认的编译器行为。</span><span class="sxs-lookup"><span data-stu-id="0f181-126">This is the default compiler behavior.</span></span>

<span data-ttu-id="0f181-127">[default(T)](default.md) - 生成类型 T 的默认值。</span><span class="sxs-lookup"><span data-stu-id="0f181-127">[default(T)](default.md) – produces the default value of type T.</span></span>

<span data-ttu-id="0f181-128">[nameof](nameof.md)：获取变量、类型或成员的简单（非限定）名称作为常数字符串。</span><span class="sxs-lookup"><span data-stu-id="0f181-128">[nameof](nameof.md) - obtains the simple (unqualified) name of a variable, type, or member as a constant string.</span></span>

<span data-ttu-id="0f181-129">[delegate](delegate-operator.md)：声明并返回委托实例。</span><span class="sxs-lookup"><span data-stu-id="0f181-129">[delegate](delegate-operator.md) – declares and returns a delegate instance.</span></span>

<span data-ttu-id="0f181-130">[sizeof](sizeof.md)：返回类型操作数的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="0f181-130">[sizeof](sizeof.md) – returns the size in bytes of the type operand.</span></span>

<span data-ttu-id="0f181-131">[stackalloc](stackalloc.md)：在堆栈上分配内存块。</span><span class="sxs-lookup"><span data-stu-id="0f181-131">[stackalloc](stackalloc.md) - allocates a block of memory on the stack.</span></span>

<span data-ttu-id="0f181-132">[->](pointer-related-operators.md#pointer-member-access-operator--)：指针间接寻址与成员访问相结合。</span><span class="sxs-lookup"><span data-stu-id="0f181-132">[->](pointer-related-operators.md#pointer-member-access-operator--) – pointer indirection combined with member access.</span></span>

## <a name="unary-operators"></a><span data-ttu-id="0f181-133">一元运算符</span><span class="sxs-lookup"><span data-stu-id="0f181-133">Unary operators</span></span>

<span data-ttu-id="0f181-134">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="0f181-134">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0f181-135">[+x](addition-operator.md)：返回 x 的值。</span><span class="sxs-lookup"><span data-stu-id="0f181-135">[+x](addition-operator.md) – returns the value of x.</span></span>

<span data-ttu-id="0f181-136">[-x](subtraction-operator.md)：数值取反。</span><span class="sxs-lookup"><span data-stu-id="0f181-136">[-x](subtraction-operator.md) – numeric negation.</span></span>

<span data-ttu-id="0f181-137">[\!x](boolean-logical-operators.md#logical-negation-operator-)：逻辑取反。</span><span class="sxs-lookup"><span data-stu-id="0f181-137">[\!x](boolean-logical-operators.md#logical-negation-operator-) – logical negation.</span></span>

<span data-ttu-id="0f181-138">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-)：按位求补。</span><span class="sxs-lookup"><span data-stu-id="0f181-138">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) – bitwise complement.</span></span>

<span data-ttu-id="0f181-139">[++x](arithmetic-operators.md#increment-operator-)：前缀递增。</span><span class="sxs-lookup"><span data-stu-id="0f181-139">[++x](arithmetic-operators.md#increment-operator-) – prefix increment.</span></span> <span data-ttu-id="0f181-140">先用加 1（通常加整数 1）后的 x 值更新存储位置，然后返回 x 值。</span><span class="sxs-lookup"><span data-stu-id="0f181-140">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="0f181-141">[--x](arithmetic-operators.md#decrement-operator---)：前缀递减。</span><span class="sxs-lookup"><span data-stu-id="0f181-141">[--x](arithmetic-operators.md#decrement-operator---) – prefix decrement.</span></span> <span data-ttu-id="0f181-142">先用减 1（通常减整数 1）后的 x 值更新存储位置，然后返回 x 值。</span><span class="sxs-lookup"><span data-stu-id="0f181-142">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="0f181-143">[(T)x](type-testing-and-conversion-operators.md#cast-operator-)：类型显式转换。</span><span class="sxs-lookup"><span data-stu-id="0f181-143">[(T)x](type-testing-and-conversion-operators.md#cast-operator-) – type casting.</span></span>

<span data-ttu-id="0f181-144">[await](../keywords/await.md)：等待 `Task`。</span><span class="sxs-lookup"><span data-stu-id="0f181-144">[await](../keywords/await.md) – awaits a `Task`.</span></span>

<span data-ttu-id="0f181-145">[&x](pointer-related-operators.md#address-of-operator-)：变量的地址。</span><span class="sxs-lookup"><span data-stu-id="0f181-145">[&x](pointer-related-operators.md#address-of-operator-) – address of a variable.</span></span>

<span data-ttu-id="0f181-146">[\*x](pointer-related-operators.md#pointer-indirection-operator-)：指针间接寻址或取消引用。</span><span class="sxs-lookup"><span data-stu-id="0f181-146">[\*x](pointer-related-operators.md#pointer-indirection-operator-) – pointer indirection, or dereference.</span></span>

<span data-ttu-id="0f181-147">[true 运算符](true-false-operators.md) - 返回 [bool](../keywords/bool.md) 值 `true` 以指明操作数一定为 true。</span><span class="sxs-lookup"><span data-stu-id="0f181-147">[true operator](true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely true.</span></span>

<span data-ttu-id="0f181-148">[false 运算符](true-false-operators.md) - 返回 [bool](../keywords/bool.md) 值 `true` 以指明操作数一定为 false。</span><span class="sxs-lookup"><span data-stu-id="0f181-148">[false operator](true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely false.</span></span>

## <a name="multiplicative-operators"></a><span data-ttu-id="0f181-149">乘法运算符</span><span class="sxs-lookup"><span data-stu-id="0f181-149">Multiplicative operators</span></span>

<span data-ttu-id="0f181-150">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="0f181-150">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0f181-151">[x \* y](arithmetic-operators.md#multiplication-operator-)：乘法。</span><span class="sxs-lookup"><span data-stu-id="0f181-151">[x \* y](arithmetic-operators.md#multiplication-operator-) – multiplication.</span></span>

<span data-ttu-id="0f181-152">[x / y](arithmetic-operators.md#division-operator-)：除法。</span><span class="sxs-lookup"><span data-stu-id="0f181-152">[x / y](arithmetic-operators.md#division-operator-) – division.</span></span> <span data-ttu-id="0f181-153">如果操作数均为整数，则结果为整数，舍去小数（例如，`-7 / 2 is -3`）。</span><span class="sxs-lookup"><span data-stu-id="0f181-153">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>

<span data-ttu-id="0f181-154">[x % y](arithmetic-operators.md#remainder-operator-)：余数。</span><span class="sxs-lookup"><span data-stu-id="0f181-154">[x % y](arithmetic-operators.md#remainder-operator-) – remainder.</span></span> <span data-ttu-id="0f181-155">如果操作数均为整数，则返回 x 除以 y 后的余数。</span><span class="sxs-lookup"><span data-stu-id="0f181-155">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="0f181-156">如果 `q = x / y` 且 `r = x % y`，则 `x = q * y + r`。</span><span class="sxs-lookup"><span data-stu-id="0f181-156">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>

## <a name="additive-operators"></a><span data-ttu-id="0f181-157">相加运算符</span><span class="sxs-lookup"><span data-stu-id="0f181-157">Additive operators</span></span>

<span data-ttu-id="0f181-158">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="0f181-158">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0f181-159">[x + y](arithmetic-operators.md#addition-operator-)：加法。</span><span class="sxs-lookup"><span data-stu-id="0f181-159">[x + y](arithmetic-operators.md#addition-operator-) – addition.</span></span>

<span data-ttu-id="0f181-160">[x - y](arithmetic-operators.md#subtraction-operator--)：减法。</span><span class="sxs-lookup"><span data-stu-id="0f181-160">[x – y](arithmetic-operators.md#subtraction-operator--) – subtraction.</span></span>

## <a name="shift-operators"></a><span data-ttu-id="0f181-161">移位运算符</span><span class="sxs-lookup"><span data-stu-id="0f181-161">Shift operators</span></span>

<span data-ttu-id="0f181-162">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="0f181-162">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0f181-163">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-)：左移位，右侧用 0 填充。</span><span class="sxs-lookup"><span data-stu-id="0f181-163">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-) – shift bits left and fill with zero on the right.</span></span>

<span data-ttu-id="0f181-164">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-)：右移位。</span><span class="sxs-lookup"><span data-stu-id="0f181-164">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) – shift bits right.</span></span> <span data-ttu-id="0f181-165">如果左操作数是 `int` 或 `long`，则左位数补符号位。</span><span class="sxs-lookup"><span data-stu-id="0f181-165">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="0f181-166">如果左操作数是 `uint` 或 `ulong`，则左位数补零。</span><span class="sxs-lookup"><span data-stu-id="0f181-166">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>

## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="0f181-167">关系和类型测试运算符</span><span class="sxs-lookup"><span data-stu-id="0f181-167">Relational and type-testing operators</span></span>

<span data-ttu-id="0f181-168">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="0f181-168">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0f181-169">[x \< y](comparison-operators.md#less-than-operator-)：小于（如果 x 小于 y，则为 true）。</span><span class="sxs-lookup"><span data-stu-id="0f181-169">[x \< y](comparison-operators.md#less-than-operator-) – less than (true if x is less than y).</span></span>

<span data-ttu-id="0f181-170">[x > y](comparison-operators.md#greater-than-operator-)：大于（如果 x 大于 y，则为 true）。</span><span class="sxs-lookup"><span data-stu-id="0f181-170">[x > y](comparison-operators.md#greater-than-operator-) – greater than (true if x is greater than y).</span></span>

<span data-ttu-id="0f181-171">[x \<= y](comparison-operators.md#less-than-or-equal-operator-)：小于或等于。</span><span class="sxs-lookup"><span data-stu-id="0f181-171">[x \<= y](comparison-operators.md#less-than-or-equal-operator-) – less than or equal to.</span></span>

<span data-ttu-id="0f181-172">[x >= y](comparison-operators.md#greater-than-or-equal-operator-)：大于或等于。</span><span class="sxs-lookup"><span data-stu-id="0f181-172">[x >= y](comparison-operators.md#greater-than-or-equal-operator-) – greater than or equal to.</span></span>

<span data-ttu-id="0f181-173">[is](type-testing-and-conversion-operators.md#is-operator)：类型兼容性。</span><span class="sxs-lookup"><span data-stu-id="0f181-173">[is](type-testing-and-conversion-operators.md#is-operator) – type compatibility.</span></span> <span data-ttu-id="0f181-174">如果求值后的左操作数可以转换为右操作数中指定的类型，则返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="0f181-174">Returns `true` if the evaluated left operand can be cast to the type specified by the right operand.</span></span>

<span data-ttu-id="0f181-175">[as](type-testing-and-conversion-operators.md#as-operator)：类型转换。</span><span class="sxs-lookup"><span data-stu-id="0f181-175">[as](type-testing-and-conversion-operators.md#as-operator) – type conversion.</span></span> <span data-ttu-id="0f181-176">返回左操作数并转换为右操作数中指定的类型，但 `as` 返回 `null`，其中 `(T)x` 会引发异常。</span><span class="sxs-lookup"><span data-stu-id="0f181-176">Returns the left operand cast to the type specified by the right operand, but `as` returns `null` where `(T)x` would throw an exception.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="0f181-177">相等运算符</span><span class="sxs-lookup"><span data-stu-id="0f181-177">Equality operators</span></span>

<span data-ttu-id="0f181-178">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="0f181-178">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0f181-179">[x == y](equality-operators.md#equality-operator-)：相等。</span><span class="sxs-lookup"><span data-stu-id="0f181-179">[x == y](equality-operators.md#equality-operator-) – equality.</span></span> <span data-ttu-id="0f181-180">默认情况下，对于 `string` 以外的引用类型，此运算符返回引用相等（标识测试）。</span><span class="sxs-lookup"><span data-stu-id="0f181-180">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="0f181-181">但是，类型可以重载 `==`，因此，如果你想测试标识，最好对 `object` 使用 `ReferenceEquals` 方法。</span><span class="sxs-lookup"><span data-stu-id="0f181-181">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>

<span data-ttu-id="0f181-182">[x != y](equality-operators.md#inequality-operator-)：不相等。</span><span class="sxs-lookup"><span data-stu-id="0f181-182">[x != y](equality-operators.md#inequality-operator-) – not equal.</span></span> <span data-ttu-id="0f181-183">请参阅有关 `==` 的注释。</span><span class="sxs-lookup"><span data-stu-id="0f181-183">See comment for `==`.</span></span> <span data-ttu-id="0f181-184">如果某个类型重载 `==`，则它必须重载 `!=`。</span><span class="sxs-lookup"><span data-stu-id="0f181-184">If a type overloads `==`, then it must overload `!=`.</span></span>

## <a name="logical-and-operator"></a><span data-ttu-id="0f181-185">逻辑 AND 运算符</span><span class="sxs-lookup"><span data-stu-id="0f181-185">Logical AND operator</span></span>

<span data-ttu-id="0f181-186">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="0f181-186">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0f181-187">`x & y` - `bool` 操作数的[逻辑与](boolean-logical-operators.md#logical-and-operator-)或整型类型操作数的[位逻辑与](bitwise-and-shift-operators.md#logical-and-operator-)。</span><span class="sxs-lookup"><span data-stu-id="0f181-187">`x & y` – [logical AND](boolean-logical-operators.md#logical-and-operator-) for the `bool` operands or [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) for the operands of the integral types.</span></span>

## <a name="logical-xor-operator"></a><span data-ttu-id="0f181-188">辑 XOR 运算</span><span class="sxs-lookup"><span data-stu-id="0f181-188">Logical XOR operator</span></span>

<span data-ttu-id="0f181-189">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="0f181-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0f181-190">`x ^ y` - `bool` 操作数的[逻辑异或](boolean-logical-operators.md#logical-exclusive-or-operator-)或整型类型操作数的[位逻辑异或](bitwise-and-shift-operators.md#logical-exclusive-or-operator-)。</span><span class="sxs-lookup"><span data-stu-id="0f181-190">`x ^ y` – [logical XOR](boolean-logical-operators.md#logical-exclusive-or-operator-) for the `bool` operands or [bitwise logical XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) for the operands of the integral types.</span></span>

## <a name="logical-or-operator"></a><span data-ttu-id="0f181-191">逻辑 OR 运算符</span><span class="sxs-lookup"><span data-stu-id="0f181-191">Logical OR operator</span></span>

<span data-ttu-id="0f181-192">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="0f181-192">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0f181-193">`x | y` - `bool` 操作数的[逻辑或](boolean-logical-operators.md#logical-or-operator-)或整型类型操作数的[位逻辑或](bitwise-and-shift-operators.md#logical-or-operator-)。</span><span class="sxs-lookup"><span data-stu-id="0f181-193">`x | y` – [logical OR](boolean-logical-operators.md#logical-or-operator-) for the `bool` operands or [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) for the operands of the integral types.</span></span>

## <a name="conditional-and-operator"></a><span data-ttu-id="0f181-194">条件 AND 运算符</span><span class="sxs-lookup"><span data-stu-id="0f181-194">Conditional AND operator</span></span>

<span data-ttu-id="0f181-195">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="0f181-195">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0f181-196">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-)：逻辑 AND。</span><span class="sxs-lookup"><span data-stu-id="0f181-196">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – logical AND.</span></span> <span data-ttu-id="0f181-197">如果 `x` 的计算结果为 `false`，则不计算 `y`。</span><span class="sxs-lookup"><span data-stu-id="0f181-197">If `x` evaluates to `false`, then `y` is not evaluated.</span></span>

## <a name="conditional-or-operator"></a><span data-ttu-id="0f181-198">条件 OR 运算符</span><span class="sxs-lookup"><span data-stu-id="0f181-198">Conditional OR operator</span></span>

<span data-ttu-id="0f181-199">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="0f181-199">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0f181-200">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-)：逻辑 OR。</span><span class="sxs-lookup"><span data-stu-id="0f181-200">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – logical OR.</span></span> <span data-ttu-id="0f181-201">如果 `x` 的计算结果为 `true`，则不计算 `y`。</span><span class="sxs-lookup"><span data-stu-id="0f181-201">If `x` evaluates to `true`, then `y` is not evaluated.</span></span>

## <a name="null-coalescing-operator"></a><span data-ttu-id="0f181-202">Null 合并运算符</span><span class="sxs-lookup"><span data-stu-id="0f181-202">Null-coalescing operator</span></span>

<span data-ttu-id="0f181-203">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="0f181-203">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0f181-204">[x ?? y](null-coalescing-operator.md)：如果不为 `null`，则返回 `x`；否则返回 `y`。</span><span class="sxs-lookup"><span data-stu-id="0f181-204">[x ?? y](null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>

## <a name="conditional-operator"></a><span data-ttu-id="0f181-205">条件运算符</span><span class="sxs-lookup"><span data-stu-id="0f181-205">Conditional operator</span></span>

<span data-ttu-id="0f181-206">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="0f181-206">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0f181-207">[t ? x : y](conditional-operator.md) - 如果测试 `t` 计算结果为 true，则计算并返回 `x`；否则，计算并返回 `y`。</span><span class="sxs-lookup"><span data-stu-id="0f181-207">[t ? x : y](conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>

## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="0f181-208">赋值和 lambda 运算符</span><span class="sxs-lookup"><span data-stu-id="0f181-208">Assignment and lambda operators</span></span>

<span data-ttu-id="0f181-209">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="0f181-209">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0f181-210">[x = y](assignment-operator.md)：赋值。</span><span class="sxs-lookup"><span data-stu-id="0f181-210">[x = y](assignment-operator.md) – assignment.</span></span>

<span data-ttu-id="0f181-211">[x += y](arithmetic-operators.md#compound-assignment)：递增。</span><span class="sxs-lookup"><span data-stu-id="0f181-211">[x += y](arithmetic-operators.md#compound-assignment) – increment.</span></span> <span data-ttu-id="0f181-212">`x` 值加 `y` 值，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="0f181-212">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="0f181-213">如果 `x` 指定 [event](../keywords/event.md)，则 `y` 必须是 C# 作为事件处理程序添加的相应方法。</span><span class="sxs-lookup"><span data-stu-id="0f181-213">If `x` designates an [event](../keywords/event.md), then `y` must be an appropriate method that C# adds as an event handler.</span></span>

<span data-ttu-id="0f181-214">[x -= y](arithmetic-operators.md#compound-assignment)：递减。</span><span class="sxs-lookup"><span data-stu-id="0f181-214">[x -= y](arithmetic-operators.md#compound-assignment) – decrement.</span></span> <span data-ttu-id="0f181-215">`x` 值减 `y` 值，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="0f181-215">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="0f181-216">如果 `x` 指定 [event](../keywords/event.md)，则 `y` 必须是 C# 作为事件处理程序删除的相应方法。</span><span class="sxs-lookup"><span data-stu-id="0f181-216">If `x` designates an [event](../keywords/event.md), then `y` must be an appropriate method that C# removes as an event handler.</span></span>

<span data-ttu-id="0f181-217">[x \*= y](arithmetic-operators.md#compound-assignment)：乘法赋值。</span><span class="sxs-lookup"><span data-stu-id="0f181-217">[x \*= y](arithmetic-operators.md#compound-assignment) – multiplication assignment.</span></span> <span data-ttu-id="0f181-218">`x` 值乘以 `y` 值，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="0f181-218">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="0f181-219">[x /= y](arithmetic-operators.md#compound-assignment)：除法赋值。</span><span class="sxs-lookup"><span data-stu-id="0f181-219">[x /= y](arithmetic-operators.md#compound-assignment) – division assignment.</span></span> <span data-ttu-id="0f181-220">`x` 值除以 `y` 值，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="0f181-220">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="0f181-221">[x %= y](arithmetic-operators.md#compound-assignment)：余数赋值。</span><span class="sxs-lookup"><span data-stu-id="0f181-221">[x %= y](arithmetic-operators.md#compound-assignment) – remainder assignment.</span></span> <span data-ttu-id="0f181-222">`x` 值除以 `y` 值，余数存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="0f181-222">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>

<span data-ttu-id="0f181-223">[x &= y](boolean-logical-operators.md#compound-assignment)：AND 赋值。</span><span class="sxs-lookup"><span data-stu-id="0f181-223">[x &= y](boolean-logical-operators.md#compound-assignment) – AND assignment.</span></span> <span data-ttu-id="0f181-224">`y` 值和 `x` 值相与，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="0f181-224">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="0f181-225">[x &#124;= y](boolean-logical-operators.md#compound-assignment)：OR 赋值。</span><span class="sxs-lookup"><span data-stu-id="0f181-225">[x &#124;= y](boolean-logical-operators.md#compound-assignment) – OR assignment.</span></span> <span data-ttu-id="0f181-226">`y` 值和 `x` 值相或，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="0f181-226">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="0f181-227">[x ^= y](boolean-logical-operators.md#compound-assignment)：XOR 赋值。</span><span class="sxs-lookup"><span data-stu-id="0f181-227">[x ^= y](boolean-logical-operators.md#compound-assignment) – XOR assignment.</span></span> <span data-ttu-id="0f181-228">`y` 值和 `x` 值相异或，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="0f181-228">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="0f181-229">[x <<= y](bitwise-and-shift-operators.md#compound-assignment)：左移赋值。</span><span class="sxs-lookup"><span data-stu-id="0f181-229">[x <<= y](bitwise-and-shift-operators.md#compound-assignment) – left-shift assignment.</span></span> <span data-ttu-id="0f181-230">将 `x` 值向左移动 `y` 位，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="0f181-230">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="0f181-231">[x >>= y](bitwise-and-shift-operators.md#compound-assignment)：右移赋值。</span><span class="sxs-lookup"><span data-stu-id="0f181-231">[x >>= y](bitwise-and-shift-operators.md#compound-assignment) – right-shift assignment.</span></span> <span data-ttu-id="0f181-232">将 `x` 值向右移动 `y` 位，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="0f181-232">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="0f181-233">[=>](lambda-operator.md)：lambda 声明。</span><span class="sxs-lookup"><span data-stu-id="0f181-233">[=>](lambda-operator.md) – lambda declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f181-234">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f181-234">See also</span></span>

- [<span data-ttu-id="0f181-235">C# 参考</span><span class="sxs-lookup"><span data-stu-id="0f181-235">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0f181-236">运算符</span><span class="sxs-lookup"><span data-stu-id="0f181-236">Operators</span></span>](../../programming-guide/statements-expressions-operators/operators.md)
