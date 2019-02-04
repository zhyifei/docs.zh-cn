---
title: '> 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 12/18/2018
f1_keywords:
- '>_CSharpKeyword'
helpviewer_keywords:
- '> operator [C#]'
- greater than operator (>) [C#]
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
ms.openlocfilehash: 3b036c491d9663bf4ab0971d84a0a8d58d902ee6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287204"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="fd38a-102">> 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="fd38a-102">> Operator (C# Reference)</span></span>

<span data-ttu-id="fd38a-103">如果第一操作数大于第二操作数，“大于”关系运算符 `>` 返回 `true`，否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="fd38a-103">The "greater than" relational operator `>` returns `true` if its first operand is greater than its second operand, `false` otherwise.</span></span> <span data-ttu-id="fd38a-104">所有数值和枚举类型都支持 `>` 运算符。</span><span class="sxs-lookup"><span data-stu-id="fd38a-104">All numeric and enumeration types support the `>` operator.</span></span> <span data-ttu-id="fd38a-105">对于相同[枚举](../keywords/enum.md)类型的操作数，基础整数类型的相应值会进行比较。</span><span class="sxs-lookup"><span data-stu-id="fd38a-105">For operands of the same [enum](../keywords/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

> [!NOTE]
> <span data-ttu-id="fd38a-106">对于关系运算符 `==`、`>`、`<`、`>=` 和 `<=`，如果任何操作数不是数字 (<xref:System.Double.NaN?displayProperty=nameWithType> 或 <xref:System.Single.NaN?displayProperty=nameWithType>)，操作数的结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="fd38a-106">For relational operators `==`, `>`, `<`, `>=`, and `<=`, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>) the result of operation is `false`.</span></span> <span data-ttu-id="fd38a-107">这意味着 `NaN` 值不大于、小于或等于任何其他 `double` （或 `float`）值。</span><span class="sxs-lookup"><span data-stu-id="fd38a-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value.</span></span> <span data-ttu-id="fd38a-108">有关更多信息和示例，请参阅 <xref:System.Double.NaN?displayProperty=nameWithType> 或 <xref:System.Single.NaN?displayProperty=nameWithType> 参考文章。</span><span class="sxs-lookup"><span data-stu-id="fd38a-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="fd38a-109">下面的示例演示 `>` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="fd38a-109">The following example demonstrates the usage of the `>` operator:</span></span>

[!code-csharp-interactive[greater than example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#Greater)]

## <a name="operator-overloadability"></a><span data-ttu-id="fd38a-110">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="fd38a-110">Operator overloadability</span></span>

<span data-ttu-id="fd38a-111">用户定义的类型可以[重载](../keywords/operator.md) `>` 运算符。</span><span class="sxs-lookup"><span data-stu-id="fd38a-111">User-defined types can [overload](../keywords/operator.md) the `>` operator.</span></span> <span data-ttu-id="fd38a-112">如果类型重载“大于”运算符 `>`，它必须也重载[“小于”运算符](less-than-operator.md) `<`。</span><span class="sxs-lookup"><span data-stu-id="fd38a-112">If a type overloads the "greater than" operator `>`, it must also overload the ["less than" operator](less-than-operator.md) `<`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="fd38a-113">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="fd38a-113">C# language specification</span></span>

<span data-ttu-id="fd38a-114">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[关系和类型测试运算符](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="fd38a-114">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fd38a-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd38a-115">See also</span></span>

- [<span data-ttu-id="fd38a-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="fd38a-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fd38a-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="fd38a-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fd38a-118">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="fd38a-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="fd38a-119">>= 运算符</span><span class="sxs-lookup"><span data-stu-id="fd38a-119">>= Operator</span></span>](greater-than-equal-operator.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
