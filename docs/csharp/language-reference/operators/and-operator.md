---
title: '&amp; 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 10/29/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: 67d60709e1c6c76071ecfb7aac74c83dec6f372a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59310039"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="1df12-102">&amp; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="1df12-102">&amp; Operator (C# Reference)</span></span>

<span data-ttu-id="1df12-103">以下两种形式支持 `&` 运算符：一元 address-of 运算符或二元逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="1df12-103">The `&` operator is supported in two forms: a unary address-of operator or a binary logical operator.</span></span>

## <a name="unary-address-of-operator"></a><span data-ttu-id="1df12-104">一元 address-of 运算符</span><span class="sxs-lookup"><span data-stu-id="1df12-104">Unary address-of operator</span></span>

<span data-ttu-id="1df12-105">一元 `&` 运算符返回其操作数的地址。</span><span class="sxs-lookup"><span data-stu-id="1df12-105">The unary `&` operator returns the address of its operand.</span></span> <span data-ttu-id="1df12-106">有关详细信息，请参阅[如何：获取变量的地址](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md)。</span><span class="sxs-lookup"><span data-stu-id="1df12-106">For more information, see [How to: obtain the address of a variable](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md).</span></span>

<span data-ttu-id="1df12-107">Address-of 运算符 `&` 需要 [不安全](../keywords/unsafe.md)上下文。</span><span class="sxs-lookup"><span data-stu-id="1df12-107">The address-of operator `&` requires [unsafe](../keywords/unsafe.md) context.</span></span>

## <a name="integer-logical-bitwise-and-operator"></a><span data-ttu-id="1df12-108">整型逻辑按位 AND 运算符</span><span class="sxs-lookup"><span data-stu-id="1df12-108">Integer logical bitwise AND operator</span></span>

<span data-ttu-id="1df12-109">对于整数类型，`&` 运算符对其操作数执行逻辑按位 AND 运算：</span><span class="sxs-lookup"><span data-stu-id="1df12-109">For integer types, the `&` operator computes the logical bitwise AND of its operands:</span></span>

[!code-csharp-interactive[integer logical bitwise AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#IntegerOperands)]

> [!NOTE]
> <span data-ttu-id="1df12-110">之前的示例使用[在 C# 7.0 中引入](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements)并[在 C# 7.2 中增强](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals)的二进制文本。</span><span class="sxs-lookup"><span data-stu-id="1df12-110">The preceding example uses the binary literals [introduced in C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) and [enhanced in C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span></span>

<span data-ttu-id="1df12-111">由于针对整数类型的运算通常也允许针对枚举类型进行，因此 `&` 运算符也支持[枚举](../keywords/enum.md)操作数。</span><span class="sxs-lookup"><span data-stu-id="1df12-111">Because operations on integer types are generally allowed on enumeration types, the `&` operator also supports [enum](../keywords/enum.md) operands.</span></span>

## <a name="boolean-logical-and-operator"></a><span data-ttu-id="1df12-112">布尔逻辑 AND 运算符</span><span class="sxs-lookup"><span data-stu-id="1df12-112">Boolean logical AND operator</span></span>

<span data-ttu-id="1df12-113">对于 [bool](../keywords/bool.md) 操作数，`&` 运算符对其操作数执行逻辑 AND 运算。</span><span class="sxs-lookup"><span data-stu-id="1df12-113">For [bool](../keywords/bool.md) operands, the `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="1df12-114">如果 `x` 和 `y` 都为 `true`，则 `x & y` 的结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="1df12-114">The result of `x & y` is `true` if both `x` and `y` are `true`.</span></span> <span data-ttu-id="1df12-115">否则，结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="1df12-115">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="1df12-116">即使第一个操作数计算结果为 `false`，`&` 运算符也会计算这两个操作数，而在这种情况下，无论第二个操作数的值为何，结果都肯定为 `false`。</span><span class="sxs-lookup"><span data-stu-id="1df12-116">The `&` operator evaluates both operands even if the first operand evaluates to `false`, so that the result must be `false` regardless of the value of the second operand.</span></span> <span data-ttu-id="1df12-117">以下示例演示了该行为：</span><span class="sxs-lookup"><span data-stu-id="1df12-117">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[bool logical AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#BooleanOperands)]

<span data-ttu-id="1df12-118">[条件与运算符](boolean-logical-operators.md#conditional-logical-and-operator-) `&&` 也计算操作数的逻辑与，但如果第一个操作数的计算结果为 `false`，它就不会计算第二个操作数。</span><span class="sxs-lookup"><span data-stu-id="1df12-118">The [conditional AND operator](boolean-logical-operators.md#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the second operand if the first operand evaluates to `false`.</span></span>

<span data-ttu-id="1df12-119">对于可为 null 的 bool 操作数，`&` 操作数的行为与 SQL 的三值逻辑一致。</span><span class="sxs-lookup"><span data-stu-id="1df12-119">For nullable bool operands, the behavior of the `&` operator is consistent with SQL's three-valued logic.</span></span> <span data-ttu-id="1df12-120">有关详细信息，请参阅[布尔逻辑运算符](boolean-logical-operators.md)一文的[可以为 null 的布尔逻辑运算符](boolean-logical-operators.md#nullable-boolean-logical-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="1df12-120">For more information, see the [Nullable Boolean logical operators](boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](boolean-logical-operators.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="1df12-121">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="1df12-121">Operator overloadability</span></span>

<span data-ttu-id="1df12-122">用户定义类型可以[重载](../keywords/operator.md)二元 `&` 运算符。</span><span class="sxs-lookup"><span data-stu-id="1df12-122">User-defined types can [overload](../keywords/operator.md) the binary `&` operator.</span></span> <span data-ttu-id="1df12-123">重载二元 `&` 运算符后，也会隐式重载 [AND 赋值运算符](and-assignment-operator.md) `&=`。</span><span class="sxs-lookup"><span data-stu-id="1df12-123">When a binary `&` operator is overloaded, the [AND assignment operator](and-assignment-operator.md) `&=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1df12-124">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="1df12-124">C# language specification</span></span>

<span data-ttu-id="1df12-125">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的 [address-of 运算符](~/_csharplang/spec/unsafe-code.md#the-address-of-operator)和[逻辑运算符](~/_csharplang/spec/expressions.md#logical-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="1df12-125">For more information, see [The address-of operator](~/_csharplang/spec/unsafe-code.md#the-address-of-operator) and [Logical operators](~/_csharplang/spec/expressions.md#logical-operators) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1df12-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="1df12-126">See also</span></span>

- [<span data-ttu-id="1df12-127">C# 参考</span><span class="sxs-lookup"><span data-stu-id="1df12-127">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1df12-128">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="1df12-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1df12-129">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="1df12-129">C# Operators</span></span>](index.md)
- [<span data-ttu-id="1df12-130">Boolean 逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="1df12-130">Boolean logical operators</span></span>](boolean-logical-operators.md)
- [<span data-ttu-id="1df12-131">指针类型</span><span class="sxs-lookup"><span data-stu-id="1df12-131">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="1df12-132">| 运算符</span><span class="sxs-lookup"><span data-stu-id="1df12-132">| operator</span></span>](or-operator.md)
- [<span data-ttu-id="1df12-133">^ 运算符</span><span class="sxs-lookup"><span data-stu-id="1df12-133">^ operator</span></span>](xor-operator.md)
- [<span data-ttu-id="1df12-134">~ 运算符</span><span class="sxs-lookup"><span data-stu-id="1df12-134">~ operator</span></span>](bitwise-complement-operator.md)
