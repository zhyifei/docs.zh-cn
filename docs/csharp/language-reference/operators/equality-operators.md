---
title: 相等运算符 - C# 参考
ms.date: 03/28/2019
author: pkulikov
f1_keywords:
- ==_CSharpKeyword
- '!=_CSharpKeyword'
helpviewer_keywords:
- equality operator [C#]
- equals operator [C#]
- == operator [C#]
- inequality operator [C#]
- not equals operator [C#]
- '!= operator [C#]'
ms.openlocfilehash: 98b96f5b4c6d6ea70687a97c849e89573c67c37e
ms.sourcegitcommit: 4a8c2b8d0df44142728b68ebc842575840476f6d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2019
ms.locfileid: "58545886"
---
# <a name="equality-operators-c-reference"></a><span data-ttu-id="12cb6-102">相等运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="12cb6-102">Equality operators (C# Reference)</span></span>

<span data-ttu-id="12cb6-103">[`==`（相等）](#equality-operator-) 和 [`!=`（不等）](#inequality-operator-) 运算符检查其操作数是否相等。</span><span class="sxs-lookup"><span data-stu-id="12cb6-103">The [`==` (equality)](#equality-operator-) and [`!=` (inequality)](#inequality-operator-) operators check if their operands are equal or not.</span></span>

## <a name="equality-operator-"></a><span data-ttu-id="12cb6-104">相等运算符 ==</span><span class="sxs-lookup"><span data-stu-id="12cb6-104">Equality operator ==</span></span>

<span data-ttu-id="12cb6-105">如果操作数相等，等于运算符 `==` 返回 `true`，否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="12cb6-105">The equality operator `==` returns `true` if its operands are equal, `false` otherwise.</span></span>

### <a name="value-types-equality"></a><span data-ttu-id="12cb6-106">值类型的相等性</span><span class="sxs-lookup"><span data-stu-id="12cb6-106">Value types equality</span></span>

<span data-ttu-id="12cb6-107">如果[内置值类型](../keywords/value-types-table.md)的值相等，则其操作数相等：</span><span class="sxs-lookup"><span data-stu-id="12cb6-107">Operands of the [built-in value types](../keywords/value-types-table.md) are equal if their values are equal:</span></span>

[!code-csharp-interactive[value types equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ValueTypesEquality)]

> [!NOTE]
> <span data-ttu-id="12cb6-108">对于相等和关系运算符 `==`、`>`、`<`、`>=` 和 `<=`，如果任何操作数不是数字（<xref:System.Double.NaN?displayProperty=nameWithType> 或 <xref:System.Single.NaN?displayProperty=nameWithType>），则操作数的结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="12cb6-108">For equality and relational operators `==`, `>`, `<`, `>=`, and `<=`, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="12cb6-109">这意味着 `NaN` 值不大于、小于或等于任何其他 `double`（或 `float`）值，包括 `NaN`。</span><span class="sxs-lookup"><span data-stu-id="12cb6-109">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="12cb6-110">有关更多信息和示例，请参阅 <xref:System.Double.NaN?displayProperty=nameWithType> 或 <xref:System.Single.NaN?displayProperty=nameWithType> 参考文章。</span><span class="sxs-lookup"><span data-stu-id="12cb6-110">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="12cb6-111">如果基本整数类型的相应值相等，则相同[枚举](../keywords/enum.md)类型的两个操作数相等。</span><span class="sxs-lookup"><span data-stu-id="12cb6-111">Two operands of the same [enum](../keywords/enum.md) type are equal if the corresponding values of the underlying integral type are equal.</span></span>

<span data-ttu-id="12cb6-112">用户定义的 [struct](../keywords/struct.md) 类型默认情况下不支持 `==` 运算符。</span><span class="sxs-lookup"><span data-stu-id="12cb6-112">User-defined [struct](../keywords/struct.md) types don't support the `==` operator by default.</span></span> <span data-ttu-id="12cb6-113">要支持 `==` 运算符，用户定义的结构必须[重载](#operator-overloadability)它。</span><span class="sxs-lookup"><span data-stu-id="12cb6-113">To support the `==` operator, a user-defined struct must [overload](#operator-overloadability) it.</span></span>

<span data-ttu-id="12cb6-114">从 C# 7.3 开始，`==` 和 `!=` 运算符由 C# [元组](../../tuples.md)支持。</span><span class="sxs-lookup"><span data-stu-id="12cb6-114">Beginning with C# 7.3, the `==` and `!=` operators are supported by C# [tuples](../../tuples.md).</span></span> <span data-ttu-id="12cb6-115">有关详细信息，请参阅 [C# 元组类型](../../tuples.md)一文的[相等性和元组](../../tuples.md#equality-and-tuples)部分。</span><span class="sxs-lookup"><span data-stu-id="12cb6-115">For more information, see the [Equality and tuples](../../tuples.md#equality-and-tuples) section of the [C# tuple types](../../tuples.md) article.</span></span>

### <a name="string-equality"></a><span data-ttu-id="12cb6-116">字符串相等性</span><span class="sxs-lookup"><span data-stu-id="12cb6-116">String equality</span></span>

<span data-ttu-id="12cb6-117">如果两个字符串均为 `null` 或者两个字符串实例具有相等长度且在每个字符位置有相同字符，则这两个[字符串](../keywords/string.md)操作数相等：</span><span class="sxs-lookup"><span data-stu-id="12cb6-117">Two [string](../keywords/string.md) operands are equal when both of them are `null` or both string instances are of the same length and have identical characters in each character position:</span></span>

[!code-csharp-interactive[string equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#StringEquality)]

<span data-ttu-id="12cb6-118">这就是区分大小写的序号比较。</span><span class="sxs-lookup"><span data-stu-id="12cb6-118">That is case-sensitive ordinal comparison.</span></span> <span data-ttu-id="12cb6-119">有关字符串比较的详细信息，请参阅[如何在 C# 中比较字符串](../../how-to/compare-strings.md)。</span><span class="sxs-lookup"><span data-stu-id="12cb6-119">For more information about string comparison, see [How to compare strings in C#](../../how-to/compare-strings.md).</span></span>

### <a name="reference-types-equality"></a><span data-ttu-id="12cb6-120">引用类型的相等性</span><span class="sxs-lookup"><span data-stu-id="12cb6-120">Reference types equality</span></span>

<span data-ttu-id="12cb6-121">当两个非 `string` 引用类型引用同一对象时，其操作数相等：</span><span class="sxs-lookup"><span data-stu-id="12cb6-121">Two other than `string` reference type operands are equal when they refer to the same object:</span></span>

[!code-csharp-interactive[reference type equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ReferenceTypesEquality)]

<span data-ttu-id="12cb6-122">如示例所示，默认情况下，用户定义的引用类型支持 `==` 运算符。</span><span class="sxs-lookup"><span data-stu-id="12cb6-122">As the example shows, user-defined reference types support the `==` operator by default.</span></span> <span data-ttu-id="12cb6-123">但是，用户定义的引用类型可以重载 `==` 运算符。</span><span class="sxs-lookup"><span data-stu-id="12cb6-123">However, a user-defined reference type can overload the `==` operator.</span></span> <span data-ttu-id="12cb6-124">如果引用类型重载 `==` 运算符，使用 <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> 方法来检查该类型的两个引用是否引用同一对象。</span><span class="sxs-lookup"><span data-stu-id="12cb6-124">If a reference type overloads the `==` operator, use the <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method to check if two references of that type refer to the same object.</span></span>

## <a name="inequality-operator-"></a><span data-ttu-id="12cb6-125">不等运算符 !=</span><span class="sxs-lookup"><span data-stu-id="12cb6-125">Inequality operator !=</span></span>

<span data-ttu-id="12cb6-126">如果操作数不相等，不等于运算符 `!=` 返回 `true`，否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="12cb6-126">The inequality operator `!=` returns `true` if its operands are not equal, `false` otherwise.</span></span> <span data-ttu-id="12cb6-127">对于[内置类型](../keywords/built-in-types-table.md)的操作数，表达式 `x != y` 生成与表达式 `!(x == y)` 相同的结果。</span><span class="sxs-lookup"><span data-stu-id="12cb6-127">For the operands of the [built-in types](../keywords/built-in-types-table.md), the expression `x != y` produces the same result as the expression `!(x == y)`.</span></span> <span data-ttu-id="12cb6-128">有关类型相等性的更多信息，请参阅[相等运算符](#equality-operator-)部分。</span><span class="sxs-lookup"><span data-stu-id="12cb6-128">For more information about type equality, see the [Equality operator](#equality-operator-) section.</span></span>

<span data-ttu-id="12cb6-129">下面的示例演示 `!=` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="12cb6-129">The following example demonstrates the usage of the `!=` operator:</span></span>

[!code-csharp-interactive[non-equality examples](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#NonEquality)]

## <a name="operator-overloadability"></a><span data-ttu-id="12cb6-130">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="12cb6-130">Operator overloadability</span></span>

<span data-ttu-id="12cb6-131">用户定义的类型可以[重载](../keywords/operator.md) `==` 和 `!=` 运算符。</span><span class="sxs-lookup"><span data-stu-id="12cb6-131">User-defined types can [overload](../keywords/operator.md) the `==` and `!=` operators.</span></span> <span data-ttu-id="12cb6-132">如果某类型重载这两个运算符之一，它还必须重载另一个运算符。</span><span class="sxs-lookup"><span data-stu-id="12cb6-132">If a type overloads one of the two operators, it must also overload another one.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="12cb6-133">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="12cb6-133">C# language specification</span></span>

<span data-ttu-id="12cb6-134">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的[关系和类型测试运算符](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="12cb6-134">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="12cb6-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="12cb6-135">See also</span></span>

- [<span data-ttu-id="12cb6-136">C# 参考</span><span class="sxs-lookup"><span data-stu-id="12cb6-136">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="12cb6-137">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="12cb6-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="12cb6-138">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="12cb6-138">C# Operators</span></span>](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="12cb6-139">相等性比较</span><span class="sxs-lookup"><span data-stu-id="12cb6-139">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
