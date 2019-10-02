---
title: 使用可为空的值类型 - C# 编程指南
ms.custom: seodec18
description: 了解如何使用 C# 可为空的值类型
ms.date: 09/26/2019
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: 65fc3b0ca94f9a41c9375e96000449b52cb7db26
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2019
ms.locfileid: "71396173"
---
# <a name="using-nullable-value-types-c-programming-guide"></a><span data-ttu-id="aa571-103">使用可为空的值类型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="aa571-103">Using nullable value types (C# Programming Guide)</span></span>

<span data-ttu-id="aa571-104">可为空的值类型是表示基础值类型 `T` 的所有值的类型，还可表示一个 [NULL](../../language-reference/keywords/null.md) 值。</span><span class="sxs-lookup"><span data-stu-id="aa571-104">Nullable value types are types that represent all the values of an underlying value type `T`, and an additional [null](../../language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="aa571-105">有关详细信息，请参阅[可为空的值类型](index.md)主题。</span><span class="sxs-lookup"><span data-stu-id="aa571-105">For more information, see the [Nullable value types](index.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="aa571-106">C# 8.0 引入了可为空引用类型功能。</span><span class="sxs-lookup"><span data-stu-id="aa571-106">C# 8.0 introduces the nullable reference types feature.</span></span> <span data-ttu-id="aa571-107">有关详细信息，请参阅[可为空引用类型](../../nullable-references.md)。</span><span class="sxs-lookup"><span data-stu-id="aa571-107">For more information, see [Nullable reference types](../../nullable-references.md).</span></span> <span data-ttu-id="aa571-108">自 C# 2 起，提供可以为 null 的值类型。</span><span class="sxs-lookup"><span data-stu-id="aa571-108">The nullable value types are available starting with C# 2.</span></span>

<span data-ttu-id="aa571-109">可使用以下任何一种形式引用可为空的值类型：`Nullable<T>` 或 `T?`。</span><span class="sxs-lookup"><span data-stu-id="aa571-109">You can refer to a nullable value type in any of the following interchangeable forms: `Nullable<T>` or `T?`.</span></span> <span data-ttu-id="aa571-110">`T` 必须是一个值类型。</span><span class="sxs-lookup"><span data-stu-id="aa571-110">`T` must be a value type.</span></span>

## <a name="declaration-and-assignment"></a><span data-ttu-id="aa571-111">声明和赋值</span><span class="sxs-lookup"><span data-stu-id="aa571-111">Declaration and assignment</span></span>

<span data-ttu-id="aa571-112">由于值类型可隐式转换为相应的可为空的值类型，因此可像为其基础值类型赋值一样，为可为空的类型赋值。</span><span class="sxs-lookup"><span data-stu-id="aa571-112">As a value type can be implicitly converted to the corresponding nullable value type, you assign a value to a nullable type as you would for its underlying value type.</span></span> <span data-ttu-id="aa571-113">还可分配 `null` 值。</span><span class="sxs-lookup"><span data-stu-id="aa571-113">You also can assign the `null` value.</span></span> <span data-ttu-id="aa571-114">例如:</span><span class="sxs-lookup"><span data-stu-id="aa571-114">For example:</span></span>

[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a><span data-ttu-id="aa571-115">检查可以为 null 的类型的值</span><span class="sxs-lookup"><span data-stu-id="aa571-115">Examination of a nullable type value</span></span>

<span data-ttu-id="aa571-116">使用以下只读属性检查可为空的值类型的实例是否为 NULL，并检索基础类型的值：</span><span class="sxs-lookup"><span data-stu-id="aa571-116">Use the following readonly properties to examine an instance of a nullable value type for null and retrieve a value of an underlying type:</span></span>

- <span data-ttu-id="aa571-117"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> 指示可以为 null 的类型的实例是否具有其基础类型的值。</span><span class="sxs-lookup"><span data-stu-id="aa571-117"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indicates whether an instance of a nullable type has a value of its underlying type.</span></span>

- <span data-ttu-id="aa571-118">如果 <xref:System.Nullable%601.HasValue%2A> 为 `true`，则 <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> 获取基础类型的值。</span><span class="sxs-lookup"><span data-stu-id="aa571-118"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> gets the value of an underlying type if <xref:System.Nullable%601.HasValue%2A> is `true`.</span></span> <span data-ttu-id="aa571-119">如果 <xref:System.Nullable%601.HasValue%2A> 为 `false`，则 <xref:System.Nullable%601.Value%2A> 属性将引发 <xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="aa571-119">If <xref:System.Nullable%601.HasValue%2A> is `false`, the <xref:System.Nullable%601.Value%2A> property throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="aa571-120">以下示例中的代码使用 `HasValue` 属性在显示值之前测试变量是否包含该值：</span><span class="sxs-lookup"><span data-stu-id="aa571-120">The code in the following example uses the `HasValue` property to test whether the variable contains a value before displaying it:</span></span>

[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]

<span data-ttu-id="aa571-121">还可将可为空的值类型的变量与 `null` 进行比较，而不是使用 `HasValue` 属性，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="aa571-121">You also can compare a variable of a nullable value type with `null` instead of using the `HasValue` property, as the following example shows:</span></span>

[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

<span data-ttu-id="aa571-122">从 C# 7.0 开始，可以使用[模式匹配](../../pattern-matching.md)来检查和获取可为空的值类型的值：</span><span class="sxs-lookup"><span data-stu-id="aa571-122">Beginning with C# 7.0, you can use [pattern matching](../../pattern-matching.md) to both examine and get a value of a nullable value type:</span></span>

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-value-type-to-an-underlying-type"></a><span data-ttu-id="aa571-123">从可为空的值类型转换为基础类型</span><span class="sxs-lookup"><span data-stu-id="aa571-123">Conversion from a nullable value type to an underlying type</span></span>

<span data-ttu-id="aa571-124">如果需要将可为空的值类型的值分配给不可为空的类型，请使用 [null-coalescing 运算符`??`](../../language-reference/operators/null-coalescing-operator.md)指定可为空的值类型的值为 NULL 时要分配的值（也可使用 <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> 方法来执行此操作）：</span><span class="sxs-lookup"><span data-stu-id="aa571-124">If you need to assign a value of a nullable value type to a non-nullable type, use the [null-coalescing operator `??`](../../language-reference/operators/null-coalescing-operator.md) to specify the value to be assigned if a value of a nullable value type is null (you also can use the <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> method to do that):</span></span>

[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

<span data-ttu-id="aa571-125">如果可为空的值类型的值为 `null` 时要使用的值应为基础值类型的默认值，请使用 <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="aa571-125">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a value of a nullable value type is `null` should be the default value of the underlying value type.</span></span>

<span data-ttu-id="aa571-126">可将可为空的值类型显式强制转换为不可为空的类型。</span><span class="sxs-lookup"><span data-stu-id="aa571-126">You can explicitly cast a nullable value type to a non-nullable type.</span></span> <span data-ttu-id="aa571-127">例如:</span><span class="sxs-lookup"><span data-stu-id="aa571-127">For example:</span></span>

[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

<span data-ttu-id="aa571-128">在运行时，如果可为空的值类型的值为 `null`，则显式强制转换将抛出 <xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="aa571-128">At run time, if the value of a nullable value type is `null`, the explicit cast throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="aa571-129">不可以为 null 的值类型隐式转换为相应的可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="aa571-129">A non-nullable value type is implicitly converted to the corresponding nullable type.</span></span>

## <a name="operators"></a><span data-ttu-id="aa571-130">运算符</span><span class="sxs-lookup"><span data-stu-id="aa571-130">Operators</span></span>

<span data-ttu-id="aa571-131">相应的可为空的类型还可使用预定义的一元运算符和二元运算符以及任何用于值类型的用户定义的运算符。</span><span class="sxs-lookup"><span data-stu-id="aa571-131">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by corresponding nullable types.</span></span> <span data-ttu-id="aa571-132">如果一个或两个操作数为 `null`，则这些运算符将生成一个 `null`；否则，运算符使用所包含的值来计算结果。</span><span class="sxs-lookup"><span data-stu-id="aa571-132">These operators produce `null` if one or both operands are `null`; otherwise, the operator uses the contained values to calculate the result.</span></span> <span data-ttu-id="aa571-133">例如:</span><span class="sxs-lookup"><span data-stu-id="aa571-133">For example:</span></span>

[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]

> [!NOTE]
> <span data-ttu-id="aa571-134">对于 `bool?` 类型，预定义的 `&` 和 `|` 运算符不遵循此部分中描述的规则：即使其中一个操作数为 `null`，运算符计算结果也可以不为 NULL。</span><span class="sxs-lookup"><span data-stu-id="aa571-134">For the `bool?` type, the predefined `&` and `|` operators don't follow the rules described in this section: the result of an operator evaluation can be non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="aa571-135">有关详细信息，请参阅[布尔逻辑运算符](../../language-reference/operators/boolean-logical-operators.md)一文的[可以为 null 的布尔逻辑运算符](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="aa571-135">For more information, see the [Nullable Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md) article.</span></span>
  
<span data-ttu-id="aa571-136">对于关系运算符（`<`、`>`、`<=`、`>=`），如果一个或两个操作数为 `null`，则结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="aa571-136">For the relational operators (`<`, `>`, `<=`, `>=`), if one or both operands are `null`, the result is `false`.</span></span> <span data-ttu-id="aa571-137">请勿作出如下假定：由于某个特定的比较（例如 `<=`）返回 `false`，则相反的比较 (`>`) 返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="aa571-137">Do not assume that because a particular comparison (for example, `<=`) returns `false`, the opposite comparison (`>`) returns `true`.</span></span> <span data-ttu-id="aa571-138">以下示例显示 10</span><span class="sxs-lookup"><span data-stu-id="aa571-138">The following example shows that 10 is</span></span>

- <span data-ttu-id="aa571-139">既不大于等于 `null`，</span><span class="sxs-lookup"><span data-stu-id="aa571-139">neither greater than or equal to `null`,</span></span>
- <span data-ttu-id="aa571-140">也不小于 `null`。</span><span class="sxs-lookup"><span data-stu-id="aa571-140">nor less than `null`.</span></span>

[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]

<span data-ttu-id="aa571-141">以上示例还表明，对两个均为 NULL 的可为空的值类型进行相等比较，其计算结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="aa571-141">The above example also shows that an equality comparison of two nullable value types that are both null evaluates to `true`.</span></span>

<span data-ttu-id="aa571-142">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的[提升运算符](~/_csharplang/spec/expressions.md#lifted-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="aa571-142">For more information, see the [Lifted operators](~/_csharplang/spec/expressions.md#lifted-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="boxing-and-unboxing"></a><span data-ttu-id="aa571-143">装箱和取消装箱</span><span class="sxs-lookup"><span data-stu-id="aa571-143">Boxing and unboxing</span></span>

<span data-ttu-id="aa571-144">可通过以下规则将可以为 null 的值类型[装箱](../types/boxing-and-unboxing.md)：</span><span class="sxs-lookup"><span data-stu-id="aa571-144">A nullable value type is [boxed](../types/boxing-and-unboxing.md) by the following rules:</span></span>

- <span data-ttu-id="aa571-145">如果 <xref:System.Nullable%601.HasValue%2A> 返回 `false`，则生成空引用。</span><span class="sxs-lookup"><span data-stu-id="aa571-145">If <xref:System.Nullable%601.HasValue%2A> returns `false`, the null reference is produced.</span></span>
- <span data-ttu-id="aa571-146">如果 <xref:System.Nullable%601.HasValue%2A> 返回 `true`，则基础值类型 `T` 的值将装箱，而不对 <xref:System.Nullable%601> 的实例进行装箱。</span><span class="sxs-lookup"><span data-stu-id="aa571-146">If <xref:System.Nullable%601.HasValue%2A> returns `true`, a value of the underlying value type `T` is boxed, not the instance of <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="aa571-147">可将已装箱的值类型取消装箱到相应的可以为 null 的类型，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="aa571-147">You can unbox the boxed value type to the corresponding nullable type, as the following example shows:</span></span>

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="see-also"></a><span data-ttu-id="aa571-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa571-148">See also</span></span>

- [<span data-ttu-id="aa571-149">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="aa571-149">Nullable value types</span></span>](index.md)
- [<span data-ttu-id="aa571-150">“提升”的准确含义是什么？</span><span class="sxs-lookup"><span data-stu-id="aa571-150">What exactly does 'lifted' mean?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)
