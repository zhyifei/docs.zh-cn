---
title: 'C# 运算符'
ms.date: 04/04/2018
f1_keywords:
  - cs.operators
helpviewer_keywords:
  - 'boolean operators [C#]'
  - 'expressions [C#], operators'
  - 'logical operators [C#]'
  - 'operators [C#]'
  - 'Visual C#, operators'
  - 'indirection operators [C#]'
  - 'assignment operators [C#]'
  - 'shift operators [C#]'
  - 'relational operators [C#]'
  - 'bitwise operators [C#]'
  - 'address operators [C#]'
  - 'keywords [C#], operators'
  - 'arithmetic operators [C#]'
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
---
# <a name="c-operators"></a><span data-ttu-id="be5f0-102">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="be5f0-102">C# operators</span></span>

<span data-ttu-id="be5f0-103">C# 提供了许多运算符，这些运算符是指定要在表达式中执行哪些操作（数学、索引、函数调用等等）的符号。</span><span class="sxs-lookup"><span data-stu-id="be5f0-103">C# provides many operators, which are symbols that specify which operations (math, indexing, function call, etc.) to perform in an expression.</span></span> <span data-ttu-id="be5f0-104">可以[重载](../../programming-guide/statements-expressions-operators/overloadable-operators.md)许多应用于用户定义类型的运算符，从而更改其含义。</span><span class="sxs-lookup"><span data-stu-id="be5f0-104">You can [overload](../../programming-guide/statements-expressions-operators/overloadable-operators.md) many operators to change their meaning when applied to a user-defined type.</span></span>

<span data-ttu-id="be5f0-105">对整数类型执行的运算（如 `==`、`!=`、`<`、`>`、`&`、`|`）通常也可对枚举 (`enum`) 类型执行。</span><span class="sxs-lookup"><span data-stu-id="be5f0-105">Operations on integral types (such as `==`, `!=`, `<`, `>`, `&`, `|`) are generally allowed on enumeration (`enum`) types.</span></span>

<span data-ttu-id="be5f0-106">以下章节按最高优先级到最低优先级的顺序列示 C# 运算符。</span><span class="sxs-lookup"><span data-stu-id="be5f0-106">The sections below list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="be5f0-107">各章节内运算符的优先级相同。</span><span class="sxs-lookup"><span data-stu-id="be5f0-107">The operators within each section share the same precedence level.</span></span>

## <a name="primary-operators"></a><span data-ttu-id="be5f0-108">主要运算符</span><span class="sxs-lookup"><span data-stu-id="be5f0-108">Primary operators</span></span>

<span data-ttu-id="be5f0-109">以下是具有最高优先级的运算符。</span><span class="sxs-lookup"><span data-stu-id="be5f0-109">These are the highest precedence operators.</span></span>

<span data-ttu-id="be5f0-110">[x.y](member-access-operator.md)：成员访问。</span><span class="sxs-lookup"><span data-stu-id="be5f0-110">[x.y](member-access-operator.md) – member access.</span></span>

<span data-ttu-id="be5f0-111">[x?.y](null-conditional-operators.md)：null 条件成员访问。</span><span class="sxs-lookup"><span data-stu-id="be5f0-111">[x?.y](null-conditional-operators.md) – null conditional member access.</span></span> <span data-ttu-id="be5f0-112">如果左操作数计算结果为 `null`，则返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="be5f0-112">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="be5f0-113">[x?[y]](null-conditional-operators.md)：null 条件索引访问。</span><span class="sxs-lookup"><span data-stu-id="be5f0-113">[x?[y]](null-conditional-operators.md) - null conditional index access.</span></span> <span data-ttu-id="be5f0-114">如果左操作数计算结果为 `null`，则返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="be5f0-114">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="be5f0-115">[f(x)](invocation-operator.md)：函数调用。</span><span class="sxs-lookup"><span data-stu-id="be5f0-115">[f(x)](invocation-operator.md) – function invocation.</span></span>

<span data-ttu-id="be5f0-116">[a&#91;x&#93;](index-operator.md)：聚合对象索引。</span><span class="sxs-lookup"><span data-stu-id="be5f0-116">[a&#91;x&#93;](index-operator.md) – aggregate object indexing.</span></span>

<span data-ttu-id="be5f0-117">[x++](arithmetic-operators.md#increment-operator-)：后缀递增。</span><span class="sxs-lookup"><span data-stu-id="be5f0-117">[x++](arithmetic-operators.md#increment-operator-) – postfix increment.</span></span> <span data-ttu-id="be5f0-118">先返回 x 值，然后用加 1（通常加整数 1）后的 x 值更新存储位置。</span><span class="sxs-lookup"><span data-stu-id="be5f0-118">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="be5f0-119">[x--](arithmetic-operators.md#decrement-operator---)：后缀递减。</span><span class="sxs-lookup"><span data-stu-id="be5f0-119">[x--](arithmetic-operators.md#decrement-operator---) –  postfix decrement.</span></span> <span data-ttu-id="be5f0-120">先返回 x 值，然后用减 1（通常减整数 1）后的 x 值更新存储位置。</span><span class="sxs-lookup"><span data-stu-id="be5f0-120">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="be5f0-121">[new](../keywords/new-operator.md)：类型实例化。</span><span class="sxs-lookup"><span data-stu-id="be5f0-121">[new](../keywords/new-operator.md) – type instantiation.</span></span>

<span data-ttu-id="be5f0-122">[typeof](../keywords/typeof.md) - 返回表示操作数的 <xref:System.Type> 对象。</span><span class="sxs-lookup"><span data-stu-id="be5f0-122">[typeof](../keywords/typeof.md) – returns the <xref:System.Type> object representing the operand.</span></span>

<span data-ttu-id="be5f0-123">[checked](../keywords/checked.md)：对整数运算启用溢出检查。</span><span class="sxs-lookup"><span data-stu-id="be5f0-123">[checked](../keywords/checked.md) – enables overflow checking for integer operations.</span></span>

<span data-ttu-id="be5f0-124">[unchecked](../keywords/unchecked.md)：对整数运算禁用溢出检查。</span><span class="sxs-lookup"><span data-stu-id="be5f0-124">[unchecked](../keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="be5f0-125">这是默认的编译器行为。</span><span class="sxs-lookup"><span data-stu-id="be5f0-125">This is the default compiler behavior.</span></span>

<span data-ttu-id="be5f0-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) - 生成类型 T 的默认值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – produces the default value of type T.</span></span>

<span data-ttu-id="be5f0-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md)：声明并返回委托实例。</span><span class="sxs-lookup"><span data-stu-id="be5f0-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – declares and returns a delegate instance.</span></span>

<span data-ttu-id="be5f0-128">[sizeof](../keywords/sizeof.md)：返回类型操作数的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="be5f0-128">[sizeof](../keywords/sizeof.md) – returns the size in bytes of the type operand.</span></span>

<span data-ttu-id="be5f0-129">[->](dereference-operator.md)：指针取消引用与成员访问相结合。</span><span class="sxs-lookup"><span data-stu-id="be5f0-129">[->](dereference-operator.md) – pointer dereferencing combined with member access.</span></span>

## <a name="unary-operators"></a><span data-ttu-id="be5f0-130">一元运算符</span><span class="sxs-lookup"><span data-stu-id="be5f0-130">Unary operators</span></span>

<span data-ttu-id="be5f0-131">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="be5f0-131">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="be5f0-132">[+x](addition-operator.md)：返回 x 的值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-132">[+x](addition-operator.md) – returns the value of x.</span></span>

<span data-ttu-id="be5f0-133">[-x](subtraction-operator.md)：数值取反。</span><span class="sxs-lookup"><span data-stu-id="be5f0-133">[-x](subtraction-operator.md) – numeric negation.</span></span>

<span data-ttu-id="be5f0-134">[\!x](logical-negation-operator.md)：逻辑取反。</span><span class="sxs-lookup"><span data-stu-id="be5f0-134">[\!x](logical-negation-operator.md) – logical negation.</span></span>

<span data-ttu-id="be5f0-135">[~x](bitwise-complement-operator.md)：按位求补。</span><span class="sxs-lookup"><span data-stu-id="be5f0-135">[~x](bitwise-complement-operator.md) – bitwise complement.</span></span>

<span data-ttu-id="be5f0-136">[++x](arithmetic-operators.md#increment-operator-)：前缀递增。</span><span class="sxs-lookup"><span data-stu-id="be5f0-136">[++x](arithmetic-operators.md#increment-operator-) – prefix increment.</span></span> <span data-ttu-id="be5f0-137">先用加 1（通常加整数 1）后的 x 值更新存储位置，然后返回 x 值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-137">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="be5f0-138">[--x](arithmetic-operators.md#decrement-operator---)：前缀递减。</span><span class="sxs-lookup"><span data-stu-id="be5f0-138">[--x](arithmetic-operators.md#decrement-operator---) – prefix decrement.</span></span> <span data-ttu-id="be5f0-139">先用减 1（通常减整数 1）后的 x 值更新存储位置，然后返回 x 值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-139">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="be5f0-140">[(T)x](invocation-operator.md)：类型显式转换。</span><span class="sxs-lookup"><span data-stu-id="be5f0-140">[(T)x](invocation-operator.md) – type casting.</span></span>

<span data-ttu-id="be5f0-141">[await](../keywords/await.md)：等待 `Task`。</span><span class="sxs-lookup"><span data-stu-id="be5f0-141">[await](../keywords/await.md) – awaits a `Task`.</span></span>

<span data-ttu-id="be5f0-142">[&x](and-operator.md)：地址。</span><span class="sxs-lookup"><span data-stu-id="be5f0-142">[&x](and-operator.md) – address of.</span></span>

<span data-ttu-id="be5f0-143">[\*x](multiplication-operator.md)：取消引用。</span><span class="sxs-lookup"><span data-stu-id="be5f0-143">[\*x](multiplication-operator.md) – dereferencing.</span></span>

## <a name="multiplicative-operators"></a><span data-ttu-id="be5f0-144">乘法运算符</span><span class="sxs-lookup"><span data-stu-id="be5f0-144">Multiplicative operators</span></span>

<span data-ttu-id="be5f0-145">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="be5f0-145">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="be5f0-146">[x \* y](arithmetic-operators.md#multiplication-operator-)：乘法。</span><span class="sxs-lookup"><span data-stu-id="be5f0-146">[x \* y](arithmetic-operators.md#multiplication-operator-) – multiplication.</span></span>

<span data-ttu-id="be5f0-147">[x / y](arithmetic-operators.md#division-operator-)：除法。</span><span class="sxs-lookup"><span data-stu-id="be5f0-147">[x / y](arithmetic-operators.md#division-operator-) – division.</span></span> <span data-ttu-id="be5f0-148">如果操作数均为整数，则结果为整数，舍去小数（例如，`-7 / 2 is -3`）。</span><span class="sxs-lookup"><span data-stu-id="be5f0-148">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>

<span data-ttu-id="be5f0-149">[x % y](arithmetic-operators.md#remainder-operator-)：余数。</span><span class="sxs-lookup"><span data-stu-id="be5f0-149">[x % y](arithmetic-operators.md#remainder-operator-) – remainder.</span></span> <span data-ttu-id="be5f0-150">如果操作数均为整数，则返回 x 除以 y 后的余数。</span><span class="sxs-lookup"><span data-stu-id="be5f0-150">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="be5f0-151">如果 `q = x / y` 且 `r = x % y`，则 `x = q * y + r`。</span><span class="sxs-lookup"><span data-stu-id="be5f0-151">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>

## <a name="additive-operators"></a><span data-ttu-id="be5f0-152">相加运算符</span><span class="sxs-lookup"><span data-stu-id="be5f0-152">Additive operators</span></span>

<span data-ttu-id="be5f0-153">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="be5f0-153">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="be5f0-154">[x + y](arithmetic-operators.md#addition-operator-)：加法。</span><span class="sxs-lookup"><span data-stu-id="be5f0-154">[x + y](arithmetic-operators.md#addition-operator-) – addition.</span></span>

<span data-ttu-id="be5f0-155">[x - y](arithmetic-operators.md#subtraction-operator--)：减法。</span><span class="sxs-lookup"><span data-stu-id="be5f0-155">[x – y](arithmetic-operators.md#subtraction-operator--) – subtraction.</span></span>

## <a name="shift-operators"></a><span data-ttu-id="be5f0-156">移位运算符</span><span class="sxs-lookup"><span data-stu-id="be5f0-156">Shift operators</span></span>

<span data-ttu-id="be5f0-157">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="be5f0-157">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="be5f0-158">[x <\<  y](left-shift-operator.md)：左移位，右侧用 0 填充。</span><span class="sxs-lookup"><span data-stu-id="be5f0-158">[x <\<  y](left-shift-operator.md) – shift bits left and fill with zero on the right.</span></span>

<span data-ttu-id="be5f0-159">[x >> y](right-shift-operator.md)：右移位。</span><span class="sxs-lookup"><span data-stu-id="be5f0-159">[x >> y](right-shift-operator.md) – shift bits right.</span></span> <span data-ttu-id="be5f0-160">如果左操作数是 `int` 或 `long`，则左位数补符号位。</span><span class="sxs-lookup"><span data-stu-id="be5f0-160">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="be5f0-161">如果左操作数是 `uint` 或 `ulong`，则左位数补零。</span><span class="sxs-lookup"><span data-stu-id="be5f0-161">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>

## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="be5f0-162">关系和类型测试运算符</span><span class="sxs-lookup"><span data-stu-id="be5f0-162">Relational and type-testing operators</span></span>

<span data-ttu-id="be5f0-163">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="be5f0-163">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="be5f0-164">[x \< y](less-than-operator.md)：小于（如果 x 小于 y，则为 true）。</span><span class="sxs-lookup"><span data-stu-id="be5f0-164">[x \< y](less-than-operator.md) – less than (true if x is less than y).</span></span>

<span data-ttu-id="be5f0-165">[x > y](greater-than-operator.md)：大于（如果 x 大于 y，则为 true）。</span><span class="sxs-lookup"><span data-stu-id="be5f0-165">[x > y](greater-than-operator.md) – greater than (true if x is greater than y).</span></span>

<span data-ttu-id="be5f0-166">[x \<= y](less-than-equal-operator.md)：小于或等于。</span><span class="sxs-lookup"><span data-stu-id="be5f0-166">[x \<= y](less-than-equal-operator.md) – less than or equal to.</span></span>

<span data-ttu-id="be5f0-167">[x >= y](greater-than-equal-operator.md)：大于或等于。</span><span class="sxs-lookup"><span data-stu-id="be5f0-167">[x >= y](greater-than-equal-operator.md) – greater than or equal to.</span></span>

<span data-ttu-id="be5f0-168">[is](../keywords/is.md)：类型兼容性。</span><span class="sxs-lookup"><span data-stu-id="be5f0-168">[is](../keywords/is.md) – type compatibility.</span></span> <span data-ttu-id="be5f0-169">如果求值后的左操作数可以转换为右操作数中指定的类型（静态类型），则返回 true。</span><span class="sxs-lookup"><span data-stu-id="be5f0-169">Returns true if the evaluated left operand can be cast to the type specified in the right operand (a static type).</span></span>

<span data-ttu-id="be5f0-170">[as](../keywords/as.md)：类型转换。</span><span class="sxs-lookup"><span data-stu-id="be5f0-170">[as](../keywords/as.md) – type conversion.</span></span> <span data-ttu-id="be5f0-171">返回左操作数并转换为右操作数中指定的类型（静态类型），但 `as` 返回 `null`，其中 `(T)x` 会引发异常。</span><span class="sxs-lookup"><span data-stu-id="be5f0-171">Returns the left operand cast to the type specified by the right operand (a static type), but `as` returns `null` where `(T)x` would throw an exception.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="be5f0-172">相等运算符</span><span class="sxs-lookup"><span data-stu-id="be5f0-172">Equality operators</span></span>

<span data-ttu-id="be5f0-173">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="be5f0-173">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="be5f0-174">[x == y](equality-operators.md#equality-operator-)：相等。</span><span class="sxs-lookup"><span data-stu-id="be5f0-174">[x == y](equality-operators.md#equality-operator-) – equality.</span></span> <span data-ttu-id="be5f0-175">默认情况下，对于 `string` 以外的引用类型，此运算符返回引用相等（标识测试）。</span><span class="sxs-lookup"><span data-stu-id="be5f0-175">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="be5f0-176">但是，类型可以重载 `==`，因此，如果你想测试标识，最好对 `object` 使用 `ReferenceEquals` 方法。</span><span class="sxs-lookup"><span data-stu-id="be5f0-176">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>

<span data-ttu-id="be5f0-177">[x != y](equality-operators.md#inequality-operator-)：不相等。</span><span class="sxs-lookup"><span data-stu-id="be5f0-177">[x != y](equality-operators.md#inequality-operator-) – not equal.</span></span> <span data-ttu-id="be5f0-178">请参阅有关 `==` 的注释。</span><span class="sxs-lookup"><span data-stu-id="be5f0-178">See comment for `==`.</span></span> <span data-ttu-id="be5f0-179">如果某个类型重载 `==`，则它必须重载 `!=`。</span><span class="sxs-lookup"><span data-stu-id="be5f0-179">If a type overloads `==`, then it must overload `!=`.</span></span>

## <a name="logical-and-operator"></a><span data-ttu-id="be5f0-180">逻辑 AND 运算符</span><span class="sxs-lookup"><span data-stu-id="be5f0-180">Logical AND operator</span></span>

<span data-ttu-id="be5f0-181">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="be5f0-181">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="be5f0-182">[x & y](and-operator.md)：逻辑或位 AND。</span><span class="sxs-lookup"><span data-stu-id="be5f0-182">[x & y](and-operator.md) – logical or bitwise AND.</span></span> <span data-ttu-id="be5f0-183">通常可以将此运算符与整数类型和 `enum` 类型一起使用。</span><span class="sxs-lookup"><span data-stu-id="be5f0-183">You can generally use this with integer types and `enum` types.</span></span>

## <a name="logical-xor-operator"></a><span data-ttu-id="be5f0-184">辑 XOR 运算</span><span class="sxs-lookup"><span data-stu-id="be5f0-184">Logical XOR operator</span></span>

<span data-ttu-id="be5f0-185">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="be5f0-185">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="be5f0-186">[x ^ y](xor-operator.md)：逻辑或位 XOR。</span><span class="sxs-lookup"><span data-stu-id="be5f0-186">[x ^ y](xor-operator.md) – logical or bitwise XOR.</span></span> <span data-ttu-id="be5f0-187">通常可以将此运算符与整数类型和 `enum` 类型一起使用。</span><span class="sxs-lookup"><span data-stu-id="be5f0-187">You can generally use this with integer types and `enum` types.</span></span>

## <a name="logical-or-operator"></a><span data-ttu-id="be5f0-188">逻辑 OR 运算符</span><span class="sxs-lookup"><span data-stu-id="be5f0-188">Logical OR operator</span></span>

<span data-ttu-id="be5f0-189">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="be5f0-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="be5f0-190">[x &#124; y](or-operator.md)：逻辑或位 OR。</span><span class="sxs-lookup"><span data-stu-id="be5f0-190">[x &#124; y](or-operator.md) – logical or bitwise OR.</span></span> <span data-ttu-id="be5f0-191">通常可以将此运算符与整数类型和 `enum` 类型一起使用。</span><span class="sxs-lookup"><span data-stu-id="be5f0-191">You can generally use this with integer types and `enum` types.</span></span>

## <a name="conditional-and-operator"></a><span data-ttu-id="be5f0-192">条件 AND 运算符</span><span class="sxs-lookup"><span data-stu-id="be5f0-192">Conditional AND operator</span></span>

<span data-ttu-id="be5f0-193">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="be5f0-193">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="be5f0-194">[x && y](conditional-and-operator.md)：逻辑 AND。</span><span class="sxs-lookup"><span data-stu-id="be5f0-194">[x && y](conditional-and-operator.md) – logical AND.</span></span> <span data-ttu-id="be5f0-195">如果第一个操作数计算结果为 false，则 C# 不对第二个操作数求值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-195">If the first operand evaluates to false, then C# does not evaluate the second operand.</span></span>

## <a name="conditional-or-operator"></a><span data-ttu-id="be5f0-196">条件 OR 运算符</span><span class="sxs-lookup"><span data-stu-id="be5f0-196">Conditional OR operator</span></span>

<span data-ttu-id="be5f0-197">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="be5f0-197">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="be5f0-198">[x &#124;&#124; y](conditional-or-operator.md)：逻辑 OR。</span><span class="sxs-lookup"><span data-stu-id="be5f0-198">[x &#124;&#124; y](conditional-or-operator.md) – logical OR.</span></span> <span data-ttu-id="be5f0-199">如果第一个操作数计算结果为 true，则 C# 不对第二个操作数求值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-199">If the first operand evaluates to true, then C# does not evaluate the second operand.</span></span>

## <a name="null-coalescing-operator"></a><span data-ttu-id="be5f0-200">Null 合并运算符</span><span class="sxs-lookup"><span data-stu-id="be5f0-200">Null-coalescing operator</span></span>

<span data-ttu-id="be5f0-201">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="be5f0-201">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="be5f0-202">[x ?? y](null-coalescing-operator.md)：如果不为 `null`，则返回 `x`；否则返回 `y`。</span><span class="sxs-lookup"><span data-stu-id="be5f0-202">[x ?? y](null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>

## <a name="conditional-operator"></a><span data-ttu-id="be5f0-203">条件运算符</span><span class="sxs-lookup"><span data-stu-id="be5f0-203">Conditional operator</span></span>

<span data-ttu-id="be5f0-204">此运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="be5f0-204">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="be5f0-205">[t ? x : y](conditional-operator.md) - 如果测试 `t` 计算结果为 true，则计算并返回 `x`；否则，计算并返回 `y`。</span><span class="sxs-lookup"><span data-stu-id="be5f0-205">[t ? x : y](conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>

## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="be5f0-206">赋值和 Lambda 运算符</span><span class="sxs-lookup"><span data-stu-id="be5f0-206">Assignment and Lambda operators</span></span>

<span data-ttu-id="be5f0-207">这些运算符的优先级比下一章节高，比上一章节低。</span><span class="sxs-lookup"><span data-stu-id="be5f0-207">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="be5f0-208">[x = y](assignment-operator.md)：赋值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-208">[x = y](assignment-operator.md) – assignment.</span></span>

<span data-ttu-id="be5f0-209">[x += y](addition-assignment-operator.md)：递增。</span><span class="sxs-lookup"><span data-stu-id="be5f0-209">[x += y](addition-assignment-operator.md) – increment.</span></span> <span data-ttu-id="be5f0-210">`x` 值加 `y` 值，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-210">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="be5f0-211">如果 `x` 指定 `event`，则 `y` 必须是 C# 作为事件处理程序添加的相应函数。</span><span class="sxs-lookup"><span data-stu-id="be5f0-211">If `x` designates an `event`, then `y` must be an appropriate function that C# adds as an event handler.</span></span>

<span data-ttu-id="be5f0-212">[x -= y](subtraction-assignment-operator.md)：递减。</span><span class="sxs-lookup"><span data-stu-id="be5f0-212">[x -= y](subtraction-assignment-operator.md) – decrement.</span></span> <span data-ttu-id="be5f0-213">`x` 值减 `y` 值，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-213">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="be5f0-214">如果 `x` 指定 `event`，则 `y` 必须是 C# 作为事件处理程序删除的相应函数</span><span class="sxs-lookup"><span data-stu-id="be5f0-214">If `x` designates an `event`, then `y` must be an appropriate function that C# removes as an event handler</span></span>

<span data-ttu-id="be5f0-215">[x \*= y](multiplication-assignment-operator.md)：乘法赋值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-215">[x \*= y](multiplication-assignment-operator.md) – multiplication assignment.</span></span> <span data-ttu-id="be5f0-216">`x` 值乘以 `y` 值，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-216">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="be5f0-217">[x /= y](arithmetic-operators.md#compound-assignment)：除法赋值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-217">[x /= y](arithmetic-operators.md#compound-assignment) – division assignment.</span></span> <span data-ttu-id="be5f0-218">`x` 值除以 `y` 值，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-218">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="be5f0-219">[x %= y](arithmetic-operators.md#compound-assignment)：余数赋值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-219">[x %= y](arithmetic-operators.md#compound-assignment) – remainder assignment.</span></span> <span data-ttu-id="be5f0-220">`x` 值除以 `y` 值，余数存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-220">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>

<span data-ttu-id="be5f0-221">[x &= y](and-assignment-operator.md)：AND 赋值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-221">[x &= y](and-assignment-operator.md) – AND assignment.</span></span> <span data-ttu-id="be5f0-222">`y` 值和 `x` 值相与，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-222">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="be5f0-223">[x &#124;= y](or-assignment-operator.md)：OR 赋值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-223">[x &#124;= y](or-assignment-operator.md) – OR assignment.</span></span> <span data-ttu-id="be5f0-224">`y` 值和 `x` 值相或，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-224">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="be5f0-225">[x ^= y](xor-assignment-operator.md)：XOR 赋值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-225">[x ^= y](xor-assignment-operator.md) – XOR assignment.</span></span> <span data-ttu-id="be5f0-226">`y` 值和 `x` 值相异或，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-226">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="be5f0-227">[x <<= y](left-shift-assignment-operator.md)：左移赋值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-227">[x <<= y](left-shift-assignment-operator.md) – left-shift assignment.</span></span> <span data-ttu-id="be5f0-228">将 `x` 值向左移动 `y` 位，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-228">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="be5f0-229">[x >>= y](right-shift-assignment-operator.md)：右移赋值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-229">[x >>= y](right-shift-assignment-operator.md) – right-shift assignment.</span></span> <span data-ttu-id="be5f0-230">将 `x` 值向右移动 `y` 位，结果存储在 `x` 中，并返回新值。</span><span class="sxs-lookup"><span data-stu-id="be5f0-230">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="be5f0-231">[=>](lambda-operator.md)：lambda 声明。</span><span class="sxs-lookup"><span data-stu-id="be5f0-231">[=>](lambda-operator.md) – lambda declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="be5f0-232">请参阅</span><span class="sxs-lookup"><span data-stu-id="be5f0-232">See also</span></span>

- [<span data-ttu-id="be5f0-233">C# 参考</span><span class="sxs-lookup"><span data-stu-id="be5f0-233">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="be5f0-234">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="be5f0-234">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="be5f0-235">C#</span><span class="sxs-lookup"><span data-stu-id="be5f0-235">C#</span></span>](../../index.md)
- [<span data-ttu-id="be5f0-236">可重载运算符</span><span class="sxs-lookup"><span data-stu-id="be5f0-236">Overloadable Operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="be5f0-237">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="be5f0-237">C# Keywords</span></span>](../keywords/index.md)