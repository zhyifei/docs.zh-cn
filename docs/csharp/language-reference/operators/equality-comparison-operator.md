---
title: == 运算符 - C# 参考
ms.custom: seodec18
ms.date: 12/14/2018
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: 6d86348eefc87e847267f262141ff49e5d51faae
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/20/2018
ms.locfileid: "53655954"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="3a71c-102">== 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3a71c-102">== Operator (C# Reference)</span></span>

<span data-ttu-id="3a71c-103">如果操作数相等，等于运算符 `==` 返回 `true`，否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="3a71c-103">The equality operator `==` returns `true` if its operands are equal, `false` otherwise.</span></span>

## <a name="value-types-equality"></a><span data-ttu-id="3a71c-104">值类型的相等性</span><span class="sxs-lookup"><span data-stu-id="3a71c-104">Value types equality</span></span>

<span data-ttu-id="3a71c-105">如果[内置值类型](../keywords/value-types-table.md)的值相等，则其操作数相等：</span><span class="sxs-lookup"><span data-stu-id="3a71c-105">Operands of the [built-in value types](../keywords/value-types-table.md) are equal if their values are equal:</span></span>

[!code-csharp-interactive[value types equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ValueTypesEquality)]

> [!NOTE]
> <span data-ttu-id="3a71c-106">对于关系运算符 `==`、`>`、`<`、`>=` 和 `<=`，如果任何操作数不是数字 (<xref:System.Double.NaN?displayProperty=nameWithType> 或 <xref:System.Single.NaN?displayProperty=nameWithType>)，操作数的结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="3a71c-106">For relational operators `==`, `>`, `<`, `>=`, and `<=`, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>) the result of operation is `false`.</span></span> <span data-ttu-id="3a71c-107">这意味着 `NaN` 值不大于、小于或等于任何其他 `double` （或 `float`）值。</span><span class="sxs-lookup"><span data-stu-id="3a71c-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value.</span></span> <span data-ttu-id="3a71c-108">有关更多信息和示例，请参阅 <xref:System.Double.NaN?displayProperty=nameWithType> 或 <xref:System.Single.NaN?displayProperty=nameWithType> 参考文章。</span><span class="sxs-lookup"><span data-stu-id="3a71c-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="3a71c-109">如果基本整数类型的相应值相等，则相同[枚举](../keywords/enum.md)类型的两个操作数相等。</span><span class="sxs-lookup"><span data-stu-id="3a71c-109">Two operands of the same [enum](../keywords/enum.md) type are equal if the corresponding values of the underlying integral type are equal.</span></span>

<span data-ttu-id="3a71c-110">默认情况下，没有为用户定义的[结构](../keywords/struct.md)类型定义 `==` 运算符。</span><span class="sxs-lookup"><span data-stu-id="3a71c-110">By default, the `==` operator is not defined for a user-defined [struct](../keywords/struct.md) type.</span></span> <span data-ttu-id="3a71c-111">用户定义的类型可以[重载](#operator-overloadability) `==` 运算符。</span><span class="sxs-lookup"><span data-stu-id="3a71c-111">A user-defined type can [overload](#operator-overloadability) the `==` operator.</span></span>

<span data-ttu-id="3a71c-112">从 C# 7.3 开始，`==` 和 [`!=`](not-equal-operator.md) 运算符由 C# [元组](../../tuples.md)支持。</span><span class="sxs-lookup"><span data-stu-id="3a71c-112">Beginning with C# 7.3, the `==` and [`!=`](not-equal-operator.md) operators are supported by C# [tuples](../../tuples.md).</span></span> <span data-ttu-id="3a71c-113">有关详细信息，请参阅 [C# 元组类型](../../tuples.md)一文的[相等性和元组](../../tuples.md#equality-and-tuples)部分。</span><span class="sxs-lookup"><span data-stu-id="3a71c-113">For more information, see the [Equality and tuples](../../tuples.md#equality-and-tuples) section of the [C# tuple types](../../tuples.md) article.</span></span>

## <a name="string-equality"></a><span data-ttu-id="3a71c-114">字符串相等性</span><span class="sxs-lookup"><span data-stu-id="3a71c-114">String equality</span></span>

<span data-ttu-id="3a71c-115">如果两个字符串均为 `null` 或者两个字符串实例具有相等长度且在每个字符位置有相同字符，则这两个[字符串](../keywords/string.md)操作数相等：</span><span class="sxs-lookup"><span data-stu-id="3a71c-115">Two [string](../keywords/string.md) operands are equal when both of them are `null` or both string instances are of the same length and have identical characters in each character position:</span></span>

[!code-csharp-interactive[string equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#StringEquality)]

<span data-ttu-id="3a71c-116">这就是区分大小写的序号比较。</span><span class="sxs-lookup"><span data-stu-id="3a71c-116">That is case-sensitive ordinal comparison.</span></span> <span data-ttu-id="3a71c-117">有关如何比较字符串的详细信息，请参阅[如何在 C# 中比较字符串](../../how-to/compare-strings.md)。</span><span class="sxs-lookup"><span data-stu-id="3a71c-117">For more information about how to compare strings, see [How to compare strings in C#](../../how-to/compare-strings.md).</span></span>

## <a name="reference-types-equality"></a><span data-ttu-id="3a71c-118">引用类型的相等性</span><span class="sxs-lookup"><span data-stu-id="3a71c-118">Reference types equality</span></span>

<span data-ttu-id="3a71c-119">当两个非 `string` 引用类型引用同一对象时，其操作数相等：</span><span class="sxs-lookup"><span data-stu-id="3a71c-119">Two other than `string` reference type operands are equal when they refer to the same object:</span></span>

[!code-csharp-interactive[reference type equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ReferenceTypesEquality)]

<span data-ttu-id="3a71c-120">该示例表明，`==` 运算符由用户定义的引用类型支持。</span><span class="sxs-lookup"><span data-stu-id="3a71c-120">The example shows that the `==` operator is supported by user-defined reference types.</span></span> <span data-ttu-id="3a71c-121">但是，用户定义的引用类型可以重载 `==` 运算符。</span><span class="sxs-lookup"><span data-stu-id="3a71c-121">However, a user-defined reference type can overload the `==` operator.</span></span> <span data-ttu-id="3a71c-122">如果引用类型重载 `==` 运算符，使用 <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> 方法来检查该类型的两个引用是否引用同一对象。</span><span class="sxs-lookup"><span data-stu-id="3a71c-122">If a reference type overloads the `==` operator, use the <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method to check if two references of that type refer to the same object.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="3a71c-123">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="3a71c-123">Operator overloadability</span></span>

<span data-ttu-id="3a71c-124">用户定义的类型可以[重载](../keywords/operator.md) `==` 运算符。</span><span class="sxs-lookup"><span data-stu-id="3a71c-124">User-defined types can [overload](../keywords/operator.md) the `==` operator.</span></span> <span data-ttu-id="3a71c-125">如果类型重载等于运算符 `==`，它也必须重载[不等于运算符](not-equal-operator.md) `!=`。</span><span class="sxs-lookup"><span data-stu-id="3a71c-125">If a type overloads the equality operator `==`, it must also overload the [inequality operator](not-equal-operator.md) `!=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3a71c-126">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="3a71c-126">C# language specification</span></span>

<span data-ttu-id="3a71c-127">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[关系和类型测试运算符](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="3a71c-127">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3a71c-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a71c-128">See also</span></span>

- [<span data-ttu-id="3a71c-129">C# 参考</span><span class="sxs-lookup"><span data-stu-id="3a71c-129">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3a71c-130">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="3a71c-130">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3a71c-131">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="3a71c-131">C# Operators</span></span>](index.md)
- [<span data-ttu-id="3a71c-132">相等性比较</span><span class="sxs-lookup"><span data-stu-id="3a71c-132">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
