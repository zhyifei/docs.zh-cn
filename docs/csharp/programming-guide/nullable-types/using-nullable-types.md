---
title: 使用可以为 null 的类型（C# 编程指南）
description: 了解如何使用 C# 可以为 null 的类型
ms.date: 08/02/2018
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: 8ef875aee8c40f60472df52c19d1c1f2c73e95e8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515432"
---
# <a name="using-nullable-types-c-programming-guide"></a><span data-ttu-id="91a23-103">使用可以为 null 的类型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="91a23-103">Using nullable types (C# Programming Guide)</span></span>

<span data-ttu-id="91a23-104">可以为 null 的类型是表示基础值类型 `T` 的所有值的类型，还可表示一个 [NULL](../../language-reference/keywords/null.md) 值。</span><span class="sxs-lookup"><span data-stu-id="91a23-104">Nullable types are types that represent all the values of an underlying value type `T`, and an additional [null](../../language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="91a23-105">有关详细信息，请参阅[可以为 null 的类型](index.md)主题。</span><span class="sxs-lookup"><span data-stu-id="91a23-105">For more information, see the [Nullable types](index.md) topic.</span></span>

<span data-ttu-id="91a23-106">可使用以下任何一种形式引用可以为 null 的类型：`Nullable<T>` 或 `T?`。</span><span class="sxs-lookup"><span data-stu-id="91a23-106">You can refer to a nullable type in any of the following forms: `Nullable<T>` or `T?`.</span></span> <span data-ttu-id="91a23-107">这两种形式是可互换的。</span><span class="sxs-lookup"><span data-stu-id="91a23-107">These two forms are interchangeable.</span></span>  
  
## <a name="declaration-and-assignment"></a><span data-ttu-id="91a23-108">声明和赋值</span><span class="sxs-lookup"><span data-stu-id="91a23-108">Declaration and assignment</span></span>

<span data-ttu-id="91a23-109">由于值类型可隐式转换为相应的可以为 null 的类型，因此可像为其基础值类型赋值一样，为可以为 null 的类型赋值。</span><span class="sxs-lookup"><span data-stu-id="91a23-109">As a value type can be implicitly converted to the corresponding nullable type, you assign a value to a nullable type as you would for its underlying value type.</span></span> <span data-ttu-id="91a23-110">还可分配 `null` 值。</span><span class="sxs-lookup"><span data-stu-id="91a23-110">You also can assign the `null` value.</span></span>  <span data-ttu-id="91a23-111">例如:</span><span class="sxs-lookup"><span data-stu-id="91a23-111">For example:</span></span>
  
[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a><span data-ttu-id="91a23-112">检查可以为 null 的类型的值</span><span class="sxs-lookup"><span data-stu-id="91a23-112">Examination of a nullable type value</span></span>

<span data-ttu-id="91a23-113">使用以下只读属性检查可以为 null 的类型的实例是否为 null，并检索基础类型的值：</span><span class="sxs-lookup"><span data-stu-id="91a23-113">Use the following readonly properties to examine an instance of a nullable type for null and retrieve a value of an underlying type:</span></span>  
  
- <span data-ttu-id="91a23-114"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> 指示可以为 null 的类型的实例是否具有其基础类型的值。</span><span class="sxs-lookup"><span data-stu-id="91a23-114"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indicates whether an instance of a nullable type has a value of its underlying type.</span></span>
  
- <span data-ttu-id="91a23-115">如果 <xref:System.Nullable%601.HasValue%2A> 为 `true`，则 <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> 获取基础类型的值。</span><span class="sxs-lookup"><span data-stu-id="91a23-115"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> gets the value of an underlying type if <xref:System.Nullable%601.HasValue%2A> is `true`.</span></span> <span data-ttu-id="91a23-116">如果 <xref:System.Nullable%601.HasValue%2A> 为 `false`，则 <xref:System.Nullable%601.Value%2A> 属性将引发 <xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="91a23-116">If <xref:System.Nullable%601.HasValue%2A> is `false`, the <xref:System.Nullable%601.Value%2A> property throws an <xref:System.InvalidOperationException>.</span></span>
  
<span data-ttu-id="91a23-117">以下示例中的代码使用 `HasValue` 属性在显示值之前测试变量是否包含该值：</span><span class="sxs-lookup"><span data-stu-id="91a23-117">The code in the following example uses the `HasValue` property to test whether the variable contains a value before displaying it:</span></span>
  
[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]
  
<span data-ttu-id="91a23-118">还可将可以为 null 的类型的变量与 `null` 进行比较，而不是使用 `HasValue` 属性，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="91a23-118">You also can compare a nullable type variable with `null` instead of using the `HasValue` property, as the following example shows:</span></span>  
  
[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

<span data-ttu-id="91a23-119">从 C# 7.0 开始，可以使用[模式匹配](../../pattern-matching.md)来检查和获取可以为 null 的类型的值：</span><span class="sxs-lookup"><span data-stu-id="91a23-119">Beginning with C# 7.0, you can use [pattern matching](../../pattern-matching.md) to both examine and get a value of a nullable type:</span></span>

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-type-to-an-underlying-type"></a><span data-ttu-id="91a23-120">从可以为 null 的类型转换为基础类型</span><span class="sxs-lookup"><span data-stu-id="91a23-120">Conversion from a nullable type to an underlying type</span></span>

<span data-ttu-id="91a23-121">如果需要将可以为 null 的类型的值分配给不可以为 null 的类型，请使用 [null-coalescing 运算符`??`](../../language-reference/operators/null-coalescing-operator.md)指定可以为 null 的类型的值为 null 时要分配的值（也可使用 <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> 方法来执行此操作）：</span><span class="sxs-lookup"><span data-stu-id="91a23-121">If you need to assign a nullable type value to a non-nullable type, use the [null-coalescing operator `??`](../../language-reference/operators/null-coalescing-operator.md) to specify the value to be assigned if a nullable type value is null (you also can use the <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> method to do that):</span></span>
  
[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

<span data-ttu-id="91a23-122">如果可以为 null 的类型的值为 null 时要使用的值应为基础值类型的默认值，请使用 <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="91a23-122">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is null should be the default value of the underlying value type.</span></span>
  
<span data-ttu-id="91a23-123">可显式地将可以为 null 的类型强制转换为不可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="91a23-123">You can explicitly cast a nullable type to a non-nullable type.</span></span> <span data-ttu-id="91a23-124">例如:</span><span class="sxs-lookup"><span data-stu-id="91a23-124">For example:</span></span>  
  
[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

<span data-ttu-id="91a23-125">在运行时，如果可以为 null 的类型的值为 null，则显式强制转换将引发 <xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="91a23-125">At run time, if the value of a nullable type is null, the explicit cast throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="91a23-126">不可以为 null 的值类型隐式转换为相应的可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="91a23-126">A non-nullable value type is implicitly converted to the corresponding nullable type.</span></span>
  
## <a name="operators"></a><span data-ttu-id="91a23-127">运算符</span><span class="sxs-lookup"><span data-stu-id="91a23-127">Operators</span></span>

<span data-ttu-id="91a23-128">可为 null 的类型还可使用预定义的一元运算符和二元运算符以及任何用于值类型的用户定义的运算符。</span><span class="sxs-lookup"><span data-stu-id="91a23-128">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by nullable types.</span></span> <span data-ttu-id="91a23-129">如果一个或两个操作数为 null，则这些运算符将生成一个 null 值；否则，运算符使用所包含的值来计算结果。</span><span class="sxs-lookup"><span data-stu-id="91a23-129">These operators produce a null value if one or both operands are null; otherwise, the operator uses the contained values to calculate the result.</span></span> <span data-ttu-id="91a23-130">例如:</span><span class="sxs-lookup"><span data-stu-id="91a23-130">For example:</span></span>  
  
[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]
  
<span data-ttu-id="91a23-131">对于关系运算符（`<`、`>`、`<=`、`>=`），如果一个或两个操作数为 null，则结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="91a23-131">For the relational operators (`<`, `>`, `<=`, `>=`), if one or both operands are null, the result is `false`.</span></span> <span data-ttu-id="91a23-132">请勿作出如下假定：由于某个特定的比较（例如 `<=`）返回 `false`，则相反的比较 (`>`) 返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="91a23-132">Do not assume that because a particular comparison (for example, `<=`) returns `false`, the opposite comparison (`>`) returns `true`.</span></span> <span data-ttu-id="91a23-133">以下示例显示 10</span><span class="sxs-lookup"><span data-stu-id="91a23-133">The following example shows that 10 is</span></span>

- <span data-ttu-id="91a23-134">既不大于等于 null，</span><span class="sxs-lookup"><span data-stu-id="91a23-134">neither greater than or equal to null,</span></span>
- <span data-ttu-id="91a23-135">也不小于 null。</span><span class="sxs-lookup"><span data-stu-id="91a23-135">nor less than null.</span></span>
  
[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]
  
<span data-ttu-id="91a23-136">以上示例还表明，对两个均为 null 的可以为 null 的类型进行相等比较，其计算结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="91a23-136">The above example also shows that an equality comparison of two nullable types that are both null evaluates to `true`.</span></span>

## <a name="boxing-and-unboxing"></a><span data-ttu-id="91a23-137">装箱和取消装箱</span><span class="sxs-lookup"><span data-stu-id="91a23-137">Boxing and unboxing</span></span>

<span data-ttu-id="91a23-138">可通过以下规则将可以为 null 的值类型[装箱](../types/boxing-and-unboxing.md)：</span><span class="sxs-lookup"><span data-stu-id="91a23-138">A nullable value type is [boxed](../types/boxing-and-unboxing.md) by the following rules:</span></span>

- <span data-ttu-id="91a23-139">如果 <xref:System.Nullable%601.HasValue%2A> 返回 `false`，则生成空引用。</span><span class="sxs-lookup"><span data-stu-id="91a23-139">If <xref:System.Nullable%601.HasValue%2A> returns `false`, the null reference is produced.</span></span>  
- <span data-ttu-id="91a23-140">如果 <xref:System.Nullable%601.HasValue%2A> 返回 `true`，则基础值类型 `T` 的值将装箱，而不对 <xref:System.Nullable%601> 的实例进行装箱。</span><span class="sxs-lookup"><span data-stu-id="91a23-140">If <xref:System.Nullable%601.HasValue%2A> returns `true`, a value of the underlying value type `T` is boxed, not the instance of <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="91a23-141">可将已装箱的值类型取消装箱到相应的可以为 null 的类型，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="91a23-141">You can unbox the boxed value type to the corresponding nullable type, as the following example shows:</span></span>

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="the-bool-type"></a><span data-ttu-id="91a23-142">bool? 类型</span><span class="sxs-lookup"><span data-stu-id="91a23-142">The bool? type</span></span>

<span data-ttu-id="91a23-143">可以为 null 的类型 `bool?` 可包含三个不同的值：[true](../../language-reference/keywords/true-literal.md)、[false](../../language-reference/keywords/false-literal.md) 和 [null](../../language-reference/keywords/null.md)。</span><span class="sxs-lookup"><span data-stu-id="91a23-143">The `bool?` nullable type can contain three different values: [true](../../language-reference/keywords/true-literal.md), [false](../../language-reference/keywords/false-literal.md) and [null](../../language-reference/keywords/null.md).</span></span> <span data-ttu-id="91a23-144">`bool?` 类型类似于在 SQL 中使用的布尔变量类型。</span><span class="sxs-lookup"><span data-stu-id="91a23-144">The `bool?` type is like the Boolean variable type that is used in SQL.</span></span> <span data-ttu-id="91a23-145">为确保 `&` 和 `|` 运算符产生的结果与 SQL 中具有三个值的布尔值类型一致，在此提供以下预定义运算符：</span><span class="sxs-lookup"><span data-stu-id="91a23-145">To ensure that the results produced by the `&` and `|` operators are consistent with the three-valued Boolean type in SQL, the following predefined operators are provided:</span></span>

- `bool? operator &(bool? x, bool? y)`  
- `bool? operator |(bool? x, bool? y)`  
  
<span data-ttu-id="91a23-146">由下表定义这些运算符的语义：</span><span class="sxs-lookup"><span data-stu-id="91a23-146">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="91a23-147">x</span><span class="sxs-lookup"><span data-stu-id="91a23-147">x</span></span>|<span data-ttu-id="91a23-148">y</span><span class="sxs-lookup"><span data-stu-id="91a23-148">y</span></span>|<span data-ttu-id="91a23-149">x 和 y</span><span class="sxs-lookup"><span data-stu-id="91a23-149">x&y</span></span>|<span data-ttu-id="91a23-150">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="91a23-150">x&#124;y</span></span>|  
|-------|-------|---------|--------------|  
|<span data-ttu-id="91a23-151">true</span><span class="sxs-lookup"><span data-stu-id="91a23-151">true</span></span>|<span data-ttu-id="91a23-152">true</span><span class="sxs-lookup"><span data-stu-id="91a23-152">true</span></span>|<span data-ttu-id="91a23-153">true</span><span class="sxs-lookup"><span data-stu-id="91a23-153">true</span></span>|<span data-ttu-id="91a23-154">true</span><span class="sxs-lookup"><span data-stu-id="91a23-154">true</span></span>|  
|<span data-ttu-id="91a23-155">true</span><span class="sxs-lookup"><span data-stu-id="91a23-155">true</span></span>|<span data-ttu-id="91a23-156">False</span><span class="sxs-lookup"><span data-stu-id="91a23-156">false</span></span>|<span data-ttu-id="91a23-157">false</span><span class="sxs-lookup"><span data-stu-id="91a23-157">false</span></span>|<span data-ttu-id="91a23-158">true</span><span class="sxs-lookup"><span data-stu-id="91a23-158">true</span></span>|  
|<span data-ttu-id="91a23-159">true</span><span class="sxs-lookup"><span data-stu-id="91a23-159">true</span></span>|<span data-ttu-id="91a23-160">null</span><span class="sxs-lookup"><span data-stu-id="91a23-160">null</span></span>|<span data-ttu-id="91a23-161">null</span><span class="sxs-lookup"><span data-stu-id="91a23-161">null</span></span>|<span data-ttu-id="91a23-162">true</span><span class="sxs-lookup"><span data-stu-id="91a23-162">true</span></span>|  
|<span data-ttu-id="91a23-163">False</span><span class="sxs-lookup"><span data-stu-id="91a23-163">false</span></span>|<span data-ttu-id="91a23-164">true</span><span class="sxs-lookup"><span data-stu-id="91a23-164">true</span></span>|<span data-ttu-id="91a23-165">False</span><span class="sxs-lookup"><span data-stu-id="91a23-165">false</span></span>|<span data-ttu-id="91a23-166">true</span><span class="sxs-lookup"><span data-stu-id="91a23-166">true</span></span>|  
|<span data-ttu-id="91a23-167">False</span><span class="sxs-lookup"><span data-stu-id="91a23-167">false</span></span>|<span data-ttu-id="91a23-168">False</span><span class="sxs-lookup"><span data-stu-id="91a23-168">false</span></span>|<span data-ttu-id="91a23-169">False</span><span class="sxs-lookup"><span data-stu-id="91a23-169">false</span></span>|<span data-ttu-id="91a23-170">False</span><span class="sxs-lookup"><span data-stu-id="91a23-170">false</span></span>|  
|<span data-ttu-id="91a23-171">False</span><span class="sxs-lookup"><span data-stu-id="91a23-171">false</span></span>|<span data-ttu-id="91a23-172">null</span><span class="sxs-lookup"><span data-stu-id="91a23-172">null</span></span>|<span data-ttu-id="91a23-173">False</span><span class="sxs-lookup"><span data-stu-id="91a23-173">false</span></span>|<span data-ttu-id="91a23-174">null</span><span class="sxs-lookup"><span data-stu-id="91a23-174">null</span></span>|  
|<span data-ttu-id="91a23-175">null</span><span class="sxs-lookup"><span data-stu-id="91a23-175">null</span></span>|<span data-ttu-id="91a23-176">true</span><span class="sxs-lookup"><span data-stu-id="91a23-176">true</span></span>|<span data-ttu-id="91a23-177">null</span><span class="sxs-lookup"><span data-stu-id="91a23-177">null</span></span>|<span data-ttu-id="91a23-178">true</span><span class="sxs-lookup"><span data-stu-id="91a23-178">true</span></span>|  
|<span data-ttu-id="91a23-179">null</span><span class="sxs-lookup"><span data-stu-id="91a23-179">null</span></span>|<span data-ttu-id="91a23-180">False</span><span class="sxs-lookup"><span data-stu-id="91a23-180">false</span></span>|<span data-ttu-id="91a23-181">False</span><span class="sxs-lookup"><span data-stu-id="91a23-181">false</span></span>|<span data-ttu-id="91a23-182">null</span><span class="sxs-lookup"><span data-stu-id="91a23-182">null</span></span>|  
|<span data-ttu-id="91a23-183">null</span><span class="sxs-lookup"><span data-stu-id="91a23-183">null</span></span>|<span data-ttu-id="91a23-184">null</span><span class="sxs-lookup"><span data-stu-id="91a23-184">null</span></span>|<span data-ttu-id="91a23-185">null</span><span class="sxs-lookup"><span data-stu-id="91a23-185">null</span></span>|<span data-ttu-id="91a23-186">null</span><span class="sxs-lookup"><span data-stu-id="91a23-186">null</span></span>|  

<span data-ttu-id="91a23-187">请注意，这两个运算符不遵循[运算符](#operators)部分中描述的规则：即使其中一个操作数为 null，运算符求值的结果也可以为非 null。</span><span class="sxs-lookup"><span data-stu-id="91a23-187">Note that these two operators don't follow the rules described in the [Operators](#operators) section: the result of an operator evaluation can be non-null even if one of the operands is null.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="91a23-188">请参阅</span><span class="sxs-lookup"><span data-stu-id="91a23-188">See Also</span></span>

- [<span data-ttu-id="91a23-189">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="91a23-189">Nullable types</span></span>](index.md)  
- [<span data-ttu-id="91a23-190">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="91a23-190">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="91a23-191">“提升”的准确含义是什么？</span><span class="sxs-lookup"><span data-stu-id="91a23-191">What exactly does 'lifted' mean?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)  
