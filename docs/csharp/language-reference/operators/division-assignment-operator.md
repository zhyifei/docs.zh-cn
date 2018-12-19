---
title: /= 运算符 - C# 参考
ms.custom: seodec18
ms.date: 12/13/2018
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: ed4dd6c0c944b77543aae4de8d51534b4df4f4ef
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286515"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="41500-102">/= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="41500-102">/= Operator (C# Reference)</span></span>

<span data-ttu-id="41500-103">除法赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="41500-103">The division assignment operator.</span></span>

<span data-ttu-id="41500-104">使用 `/=` 运算符的表达式，例如</span><span class="sxs-lookup"><span data-stu-id="41500-104">An expression using the `/=` operator, such as</span></span>

```csharp
x /= y
```

<span data-ttu-id="41500-105">等效于</span><span class="sxs-lookup"><span data-stu-id="41500-105">is equivalent to</span></span>

```csharp
x = x / y
```

<span data-ttu-id="41500-106">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="41500-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="41500-107">[除法运算符](division-operator.md) `/` 用它的第一个操作数除以第二个操作数。</span><span class="sxs-lookup"><span data-stu-id="41500-107">The [division operator](division-operator.md) `/` divides its first operand by its second operand.</span></span> <span data-ttu-id="41500-108">它受所有数值类型支持。</span><span class="sxs-lookup"><span data-stu-id="41500-108">It's supported by all numeric types.</span></span>

<span data-ttu-id="41500-109">下面的示例演示 `/=` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="41500-109">The following example demonstrates the usage of the `/=` operator:</span></span>

[!code-csharp-interactive[divide and assign](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#DivisionAssignment)]

## <a name="operator-overloadability"></a><span data-ttu-id="41500-110">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="41500-110">Operator overloadability</span></span>

<span data-ttu-id="41500-111">如果用户定义类型[重载](../keywords/operator.md)[除法运算符](division-operator.md) `/`，除法赋值运算符 `/=` 会隐式重载。</span><span class="sxs-lookup"><span data-stu-id="41500-111">If a user-defined type [overloads](../keywords/operator.md) the [division operator](division-operator.md) `/`, the division assignment operator `/=` is implicitly overloaded.</span></span> <span data-ttu-id="41500-112">用户定义类型不得显式重载除法赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="41500-112">A user-defined type cannot explicitly overload the division assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="41500-113">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="41500-113">C# language specification</span></span>

<span data-ttu-id="41500-114">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[复合赋值](~/_csharplang/spec/expressions.md#compound-assignment)部分。</span><span class="sxs-lookup"><span data-stu-id="41500-114">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="41500-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="41500-115">See also</span></span>

- [<span data-ttu-id="41500-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="41500-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="41500-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="41500-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="41500-118">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="41500-118">C# Operators</span></span>](index.md)
