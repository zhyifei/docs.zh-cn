---
title: 可以为 null 的类型（C# 编程指南）
description: 了解 C# 中可以为 null 的类型及其使用方法
ms.date: 07/30/2018
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
ms.openlocfilehash: 2af0704abcad00c75a5d40bfe2d0523d07ee6a3f
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2018
ms.locfileid: "44511808"
---
# <a name="nullable-types-c-programming-guide"></a><span data-ttu-id="042f9-103">可以为 null 的类型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="042f9-103">Nullable types (C# Programming Guide)</span></span>

<span data-ttu-id="042f9-104">可以为 null 的类型是 <xref:System.Nullable%601?displayProperty=nameWithType> 结构的实例。</span><span class="sxs-lookup"><span data-stu-id="042f9-104">Nullable types are instances of the <xref:System.Nullable%601?displayProperty=nameWithType> struct.</span></span> <span data-ttu-id="042f9-105">可以为 null 的类型可表示一个基础类型的所有值 `T`，还可以再表示一个 [null](../../language-reference/keywords/null.md) 值。</span><span class="sxs-lookup"><span data-stu-id="042f9-105">Nullable types can represent all the values of an underlying type `T`, and an additional [null](../../language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="042f9-106">基础类型 `T` 可以是任何不可为 null 的[值类型](../../language-reference/keywords/value-types.md)。</span><span class="sxs-lookup"><span data-stu-id="042f9-106">The underlying type `T` can be any non-nullable [value type](../../language-reference/keywords/value-types.md).</span></span> <span data-ttu-id="042f9-107">`T` 不能是引用类型。</span><span class="sxs-lookup"><span data-stu-id="042f9-107">`T` cannot be a reference type.</span></span>

<span data-ttu-id="042f9-108">例如，可以将 `null` 或任何整数值（从 <xref:System.Int32.MinValue?displayProperty=nameWithType> 到 <xref:System.Int32.MaxValue?displayProperty=nameWithType>）赋给 `Nullable<int>`，并可将 [true](../../language-reference/keywords/true-literal.md)[false](../../language-reference/keywords/false-literal.md) 或 `null` 赋给`Nullable<bool>`。</span><span class="sxs-lookup"><span data-stu-id="042f9-108">For example, you can assign `null` or any integer value from <xref:System.Int32.MinValue?displayProperty=nameWithType> to <xref:System.Int32.MaxValue?displayProperty=nameWithType> to a `Nullable<int>` and [true](../../language-reference/keywords/true-literal.md), [false](../../language-reference/keywords/false-literal.md), or `null` to a `Nullable<bool>`.</span></span>

<span data-ttu-id="042f9-109">需要表示基础类型的未定义的值时，请使用可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="042f9-109">You use a nullable type when you need to represent the undefined value of an underlying type.</span></span> <span data-ttu-id="042f9-110">布尔变量只能有两个值：true 和 false。</span><span class="sxs-lookup"><span data-stu-id="042f9-110">A Boolean variable can have only two values: true and false.</span></span> <span data-ttu-id="042f9-111">没有“未定义”的值。</span><span class="sxs-lookup"><span data-stu-id="042f9-111">There is no "undefined" value.</span></span> <span data-ttu-id="042f9-112">在许多编程应用程序中，尤其是数据库交互中，变量值可能未定义或缺失。</span><span class="sxs-lookup"><span data-stu-id="042f9-112">In many programming applications, most notably database interactions, a variable value can be undefined or missing.</span></span> <span data-ttu-id="042f9-113">例如，数据库中的字段可能包含值 true 或 false，但它也可能根本不包含任何值。</span><span class="sxs-lookup"><span data-stu-id="042f9-113">For example, a field in a database may contain the values true or false, or it may contain no value at all.</span></span> <span data-ttu-id="042f9-114">这种情况下要使用 `Nullable<bool>` 类型。</span><span class="sxs-lookup"><span data-stu-id="042f9-114">You use a `Nullable<bool>` type in that case.</span></span>

<span data-ttu-id="042f9-115">可以为 null 的类型具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="042f9-115">Nullable types have the following characteristics:</span></span>
  
- <span data-ttu-id="042f9-116">可以为 null 的类型表示可以向其赋与 `null` 值的值类型变量。</span><span class="sxs-lookup"><span data-stu-id="042f9-116">Nullable types represent value-type variables that can be assigned the `null` value.</span></span> <span data-ttu-id="042f9-117">不能根据引用类型创建可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="042f9-117">You cannot create a nullable type based on a reference type.</span></span> <span data-ttu-id="042f9-118">（引用类型已支持 `null` 值）。</span><span class="sxs-lookup"><span data-stu-id="042f9-118">(Reference types already support the `null` value.)</span></span>  
  
- <span data-ttu-id="042f9-119">语法 `T?` 是 `Nullable<T>` 的简写。</span><span class="sxs-lookup"><span data-stu-id="042f9-119">The syntax `T?` is shorthand for `Nullable<T>`.</span></span> <span data-ttu-id="042f9-120">这两种形式是可互换的。</span><span class="sxs-lookup"><span data-stu-id="042f9-120">The two forms are interchangeable.</span></span>  
  
- <span data-ttu-id="042f9-121">向可以为 null 的类型赋值的方法与向基础值类型赋值的方法相同：`int? x = 10;` 或 `double? d = 4.108;`。</span><span class="sxs-lookup"><span data-stu-id="042f9-121">Assign a value to a nullable type just as you would for an underlying value type: `int? x = 10;` or `double? d = 4.108;`.</span></span> <span data-ttu-id="042f9-122">还可赋予 `null` 值：`int? x = null;`。</span><span class="sxs-lookup"><span data-stu-id="042f9-122">You also can assign the `null` value: `int? x = null;`.</span></span>  
  
- <span data-ttu-id="042f9-123">使用 <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> 和 <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> 只读属性可测试是否存在 null 值并检索值，如以下示例所示：`if (x.HasValue) y = x.Value;`</span><span class="sxs-lookup"><span data-stu-id="042f9-123">Use the <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> and <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> readonly properties to test for null and retrieve the value, as shown in the following example: `if (x.HasValue) y = x.Value;`</span></span>  
  
  - <span data-ttu-id="042f9-124">如果变量包含值，则 <xref:System.Nullable%601.HasValue%2A> 属性返回 `true`；如果值为 `null`，则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="042f9-124">The <xref:System.Nullable%601.HasValue%2A> property returns `true` if the variable contains a value, or `false` if it's `null`.</span></span>
  
  - <span data-ttu-id="042f9-125">如果 <xref:System.Nullable%601.HasValue%2A> 返回 `true`，则 <xref:System.Nullable%601.Value%2A> 属性返回值。</span><span class="sxs-lookup"><span data-stu-id="042f9-125">The <xref:System.Nullable%601.Value%2A> property returns a value if <xref:System.Nullable%601.HasValue%2A> returns `true`.</span></span> <span data-ttu-id="042f9-126">否则会引发 <xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="042f9-126">Otherwise, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
- <span data-ttu-id="042f9-127">还可将 `==` 和 `!=` 运算符用于可以为 null 的类型，如以下示例所示：`if (x != null) y = x.Value;`</span><span class="sxs-lookup"><span data-stu-id="042f9-127">You can also use the `==` and `!=` operators with a nullable type, as shown in the following example: `if (x != null) y = x.Value;`.</span></span> <span data-ttu-id="042f9-128">如果 `a` 和 `b` 均为 null，则 `a == b` 的计算结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="042f9-128">If `a` and `b` are both null, `a == b` evaluates to `true`.</span></span>  

- <span data-ttu-id="042f9-129">从 C# 7.0 开始，可以使用[模式匹配](../../pattern-matching.md#the-is-type-pattern-expression)来检查和获取可以为 null 的类型的值：`if (x is int valueOfX) y = valueOfX;`。</span><span class="sxs-lookup"><span data-stu-id="042f9-129">Beginning with C# 7.0, you can use [pattern matching](../../pattern-matching.md#the-is-type-pattern-expression) to both examine and get a value of a nullable type: `if (x is int valueOfX) y = valueOfX;`.</span></span>
  
- <span data-ttu-id="042f9-130">`T?` 的默认值是一个实例，其 <xref:System.Nullable%601.HasValue%2A> 属性返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="042f9-130">The default value of `T?` is an instance whose <xref:System.Nullable%601.HasValue%2A> property returns `false`.</span></span>  

- <span data-ttu-id="042f9-131">使用 <xref:System.Nullable%601.GetValueOrDefault> 方法可返回赋予的值，如果可以为 null 的类型的值为 `null`，它还可返回基础值类型的[默认](../../language-reference/keywords/default-values-table.md)值。</span><span class="sxs-lookup"><span data-stu-id="042f9-131">Use the <xref:System.Nullable%601.GetValueOrDefault> method to return either the assigned value, or the [default](../../language-reference/keywords/default-values-table.md) value of the underlying value type if the value of the nullable type is `null`.</span></span>  

- <span data-ttu-id="042f9-132">使用 <xref:System.Nullable%601.GetValueOrDefault(%600)> 方法可返回赋予的值，如果可以为 null 的类型的值为 `null`，它还可返回提供的默认值。</span><span class="sxs-lookup"><span data-stu-id="042f9-132">Use the <xref:System.Nullable%601.GetValueOrDefault(%600)> method to return either the assigned value, or the provided default value if the value of the nullable type is `null`.</span></span>
  
- <span data-ttu-id="042f9-133">使用 [null 合并运算符](../../language-reference/operators/null-coalescing-operator.md) `??`，基于可以为 null 的类型的值向基础类型赋值：`int? x = null; int y = x ?? -1;`。</span><span class="sxs-lookup"><span data-stu-id="042f9-133">Use the [null-coalescing operator](../../language-reference/operators/null-coalescing-operator.md), `??`, to assign a value to an underlying type based on a value of the nullable type: `int? x = null; int y = x ?? -1;`.</span></span> <span data-ttu-id="042f9-134">在示例中，由于 `x` 为 null，所以 `y` 的结果值为 `-1`。</span><span class="sxs-lookup"><span data-stu-id="042f9-134">In the example, since `x` is null, the result value of `y` is `-1`.</span></span>

- <span data-ttu-id="042f9-135">如果定义了（用户定义的）两种数据类型之间的转换，还可将同一转换用于这些数据类型的可为 null 的版本。</span><span class="sxs-lookup"><span data-stu-id="042f9-135">If a user-defined conversion is defined between two data types, the same conversion can also be used with the nullable versions of these data types.</span></span>
  
- <span data-ttu-id="042f9-136">不得嵌套可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="042f9-136">Nested nullable types are not allowed.</span></span> <span data-ttu-id="042f9-137">不会编译下面的一行代码：`Nullable<Nullable<int>> n;`</span><span class="sxs-lookup"><span data-stu-id="042f9-137">The following line doesn't compile: `Nullable<Nullable<int>> n;`</span></span>  

<span data-ttu-id="042f9-138">有关详细信息，请参阅[使用可以为 null 的类型](using-nullable-types.md)及[如何：标识可以为 null 的类型](how-to-identify-a-nullable-type.md)主题。</span><span class="sxs-lookup"><span data-stu-id="042f9-138">For more information, see the [Using nullable types](using-nullable-types.md) and [How to: Identify a nullable type](how-to-identify-a-nullable-type.md) topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="042f9-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="042f9-139">See Also</span></span>

- <xref:System.Nullable%601?displayProperty=nameWithType>  
- <xref:System.Nullable?displayProperty=nameWithType>  
- [<span data-ttu-id="042f9-140">??运算符</span><span class="sxs-lookup"><span data-stu-id="042f9-140">?? Operator</span></span>](../../language-reference/operators/null-coalescing-operator.md)  
- [<span data-ttu-id="042f9-141">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="042f9-141">C# Programming Guide</span></span>](../index.md)  
- [<span data-ttu-id="042f9-142">C# 指南</span><span class="sxs-lookup"><span data-stu-id="042f9-142">C# Guide</span></span>](../../index.md)  
- [<span data-ttu-id="042f9-143">C# 参考</span><span class="sxs-lookup"><span data-stu-id="042f9-143">C# Reference</span></span>](../../language-reference/index.md)  
- [<span data-ttu-id="042f9-144">可以为 Null 的值类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="042f9-144">Nullable Value Types (Visual Basic)</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
