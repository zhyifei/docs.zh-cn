---
title: + 运算符（C# 参考）
ms.date: 10/22/2018
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: ae2774d96bc50afa271fffdea445e640e68c3647
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192291"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="2b705-102">+ 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="2b705-102">+ Operator (C# Reference)</span></span>

<span data-ttu-id="2b705-103">以下两种形式支持 `+` 运算符：一元加运算符或二元加运算符。</span><span class="sxs-lookup"><span data-stu-id="2b705-103">The `+` operator is supported in two forms: a unary plus operator or a binary addition operator.</span></span>

<span data-ttu-id="2b705-104">用户定义的类型可以[重载](../keywords/operator.md)一元和二元 `+` 运算符。</span><span class="sxs-lookup"><span data-stu-id="2b705-104">User-defined types can [overload](../keywords/operator.md) the unary and binary `+` operators.</span></span> <span data-ttu-id="2b705-105">重载二元 `+` 运算符后，也会隐式重载[加法赋值运算符](addition-assignment-operator.md) `+=`。</span><span class="sxs-lookup"><span data-stu-id="2b705-105">When a binary `+` operator is overloaded, the [addition assignment operator](addition-assignment-operator.md) `+=` is also implicitly overloaded.</span></span>

## <a name="unary-plus-operator"></a><span data-ttu-id="2b705-106">一元加运算符</span><span class="sxs-lookup"><span data-stu-id="2b705-106">Unary plus operator</span></span>

<span data-ttu-id="2b705-107">一元 `+` 运算符返回其操作数的值。</span><span class="sxs-lookup"><span data-stu-id="2b705-107">The unary `+` operator returns the value of its operand.</span></span> <span data-ttu-id="2b705-108">它受所有数值类型支持。</span><span class="sxs-lookup"><span data-stu-id="2b705-108">It's supported by all numeric types.</span></span>

## <a name="numeric-addition"></a><span data-ttu-id="2b705-109">数值加</span><span class="sxs-lookup"><span data-stu-id="2b705-109">Numeric addition</span></span>

<span data-ttu-id="2b705-110">对于数字类型，`+` 运算符计算其操作数的和：</span><span class="sxs-lookup"><span data-stu-id="2b705-110">For numeric types, the `+` operator computes the sum of its operands:</span></span>

[!code-csharp-interactive[numeric addition](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddNumerics)]

## <a name="string-concatenation"></a><span data-ttu-id="2b705-111">字符串串联</span><span class="sxs-lookup"><span data-stu-id="2b705-111">String concatenation</span></span>

<span data-ttu-id="2b705-112">当其中的一个操作数是[字符串](../keywords/string.md)类型或两个操作数都是字符串类型时，`+` 运算符将其操作数的字符串表示形式串联在一起：</span><span class="sxs-lookup"><span data-stu-id="2b705-112">When one or both operands are of type [string](../keywords/string.md), the `+` operator concatenates the string representations of its operands:</span></span>

[!code-csharp-interactive[string concatenation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddStrings)]

<span data-ttu-id="2b705-113">从 C# 6 开始，[字符串内插](../tokens/interpolated.md)提供了格式化字符串的更便捷方式：</span><span class="sxs-lookup"><span data-stu-id="2b705-113">Starting with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="2b705-114">委托组合</span><span class="sxs-lookup"><span data-stu-id="2b705-114">Delegate combination</span></span>

<span data-ttu-id="2b705-115">对于[委托](../keywords/delegate.md)类型，`+` 运算符在调用时返回新的委托实例，调用第一个操作数，然后调用第二个操作数。</span><span class="sxs-lookup"><span data-stu-id="2b705-115">For [delegate](../keywords/delegate.md) types, the `+` operator returns a new delegate instance that, when invoked, invokes the first operand and then invokes the second operand.</span></span> <span data-ttu-id="2b705-116">如果任何操作数均为 `null`，则 `+` 运算符将返回另一个操作数（也可能是 `null`）的值。</span><span class="sxs-lookup"><span data-stu-id="2b705-116">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="2b705-117">下面的示例演示如何组合使用委托和 `+` 运算符：</span><span class="sxs-lookup"><span data-stu-id="2b705-117">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddDelegates)]

<span data-ttu-id="2b705-118">有关委托类型的详细信息，请参阅[委托](../../programming-guide/delegates/index.md)。</span><span class="sxs-lookup"><span data-stu-id="2b705-118">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2b705-119">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="2b705-119">C# language specification</span></span>

<span data-ttu-id="2b705-120">有关详细信息，请参阅[C# 语言规范](../language-specification/index.md)的[一元加运算符](~/_csharplang/spec/expressions.md#unary-plus-operator)和[加法运算符](~/_csharplang/spec/expressions.md#addition-operator)部分。</span><span class="sxs-lookup"><span data-stu-id="2b705-120">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2b705-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b705-121">See also</span></span>

- [<span data-ttu-id="2b705-122">C# 参考</span><span class="sxs-lookup"><span data-stu-id="2b705-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2b705-123">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="2b705-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2b705-124">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="2b705-124">C# Operators</span></span>](index.md)
- [<span data-ttu-id="2b705-125">字符串内插</span><span class="sxs-lookup"><span data-stu-id="2b705-125">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="2b705-126">如何：串联多个字符串</span><span class="sxs-lookup"><span data-stu-id="2b705-126">How to: Concatenate Multiple Strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="2b705-127">委托</span><span class="sxs-lookup"><span data-stu-id="2b705-127">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="2b705-128">Checked 和 unchecked</span><span class="sxs-lookup"><span data-stu-id="2b705-128">Checked and unchecked</span></span>](../keywords/checked-and-unchecked.md)
