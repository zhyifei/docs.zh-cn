---
title: ~ 运算符（C# 参考）
ms.date: 11/05/2018
f1_keywords:
- ~_CSharpKeyword
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
ms.openlocfilehash: 1bcb07c5639a098e3a8c566e92083ca0d48efb81
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153210"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="64ed8-102">~ 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="64ed8-102">~ Operator (C# Reference)</span></span>

<span data-ttu-id="64ed8-103">按位求补运算符 `~` 是一元运算符，通过反转每个位生成其操作数的按位求补。</span><span class="sxs-lookup"><span data-stu-id="64ed8-103">The bitwise complement operator `~` is a unary operator that produces a bitwise complement of its operand by reversing each bit.</span></span> <span data-ttu-id="64ed8-104">所有整数类型都支持 `~` 运算符。</span><span class="sxs-lookup"><span data-stu-id="64ed8-104">All integer types support the `~` operator.</span></span>

> [!NOTE]
> <span data-ttu-id="64ed8-105">`~` 符号还用于声明终结器。</span><span class="sxs-lookup"><span data-stu-id="64ed8-105">The `~` symbol is also used to declare finalizers.</span></span> <span data-ttu-id="64ed8-106">有关详细信息，请参阅[终结器](../../programming-guide/classes-and-structs/destructors.md)。</span><span class="sxs-lookup"><span data-stu-id="64ed8-106">For more information, see [Finalizers](../../programming-guide/classes-and-structs/destructors.md).</span></span>

<span data-ttu-id="64ed8-107">下面的示例演示 `~` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="64ed8-107">The following example demonstrates the usage of the `~` operator:</span></span>

[!code-csharp-interactive[bitwise NOT](~/samples/snippets/csharp/language-reference/operators/BitwiseComplementExamples.cs#Example)]

> [!NOTE]
> <span data-ttu-id="64ed8-108">之前的示例使用[在 C# 7.0 中引入](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements)并[在 C# 7.2 中增强](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals)的二进制文本。</span><span class="sxs-lookup"><span data-stu-id="64ed8-108">The preceding example uses the binary literals [introduced in C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) and [enhanced  in C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="64ed8-109">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="64ed8-109">Operator overloadability</span></span>

<span data-ttu-id="64ed8-110">用户定义的类型可以[重载](../keywords/operator.md) `~` 运算符。</span><span class="sxs-lookup"><span data-stu-id="64ed8-110">User-defined types can [overload](../keywords/operator.md) the `~` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="64ed8-111">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="64ed8-111">C# language specification</span></span>

<span data-ttu-id="64ed8-112">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[按位求补运算符](~/_csharplang/spec/expressions.md#bitwise-complement-operator)部分。</span><span class="sxs-lookup"><span data-stu-id="64ed8-112">For more information, see the [Bitwise complement operator](~/_csharplang/spec/expressions.md#bitwise-complement-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="64ed8-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="64ed8-113">See also</span></span>

- [<span data-ttu-id="64ed8-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="64ed8-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="64ed8-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="64ed8-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="64ed8-116">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="64ed8-116">C# Operators</span></span>](index.md)
- [<span data-ttu-id="64ed8-117">终结器</span><span class="sxs-lookup"><span data-stu-id="64ed8-117">Finalizers</span></span>](../../programming-guide/classes-and-structs/destructors.md)
- [<span data-ttu-id="64ed8-118">& 运算符</span><span class="sxs-lookup"><span data-stu-id="64ed8-118">& operator</span></span>](and-operator.md)
- [<span data-ttu-id="64ed8-119">| 运算符</span><span class="sxs-lookup"><span data-stu-id="64ed8-119">| operator</span></span>](or-operator.md)
- [<span data-ttu-id="64ed8-120">^ 运算符</span><span class="sxs-lookup"><span data-stu-id="64ed8-120">^ operator</span></span>](xor-operator.md)
