---
title: '&amp;= 运算符（C# 参考）'
ms.date: 10/29/2018
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: 8ce27c999cf21a9059ba23ee3c86b8fa024c7341
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "50980604"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="538c4-102">&amp;= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="538c4-102">&amp;= Operator (C# Reference)</span></span>

<span data-ttu-id="538c4-103">AND 赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="538c4-103">The AND assignment operator.</span></span>

<span data-ttu-id="538c4-104">使用 `&=` 运算符的表达式，例如</span><span class="sxs-lookup"><span data-stu-id="538c4-104">An expression using the `&=` operator, such as</span></span>

```csharp
x &= y
```

<span data-ttu-id="538c4-105">等效于</span><span class="sxs-lookup"><span data-stu-id="538c4-105">is equivalent to</span></span>

```csharp
x = x & y
```

<span data-ttu-id="538c4-106">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="538c4-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="538c4-107">对于整数操作数，[`&` 运算符](and-operator.md)对其操作数执行按位逻辑 AND 运算；而对于 [bool](../keywords/bool.md) 操作数，该运算符对其操作数执行逻辑 AND 运算。</span><span class="sxs-lookup"><span data-stu-id="538c4-107">For integer operands, the [`&` operator](and-operator.md) computes the bitwise logical AND of its operands; for [bool](../keywords/bool.md) operands, it computes the logical AND of its operands.</span></span>

<span data-ttu-id="538c4-108">下面的示例演示 `&=` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="538c4-108">The following example demonstrates the usage of the `&=` operator:</span></span>

[!code-csharp-interactive[AND assignment example](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#AndAssignmentExample)]

## <a name="operator-overloadability"></a><span data-ttu-id="538c4-109">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="538c4-109">Operator overloadability</span></span>

<span data-ttu-id="538c4-110">如果用户定义类型[重载](../keywords/operator.md) [`&` 运算符](and-operator.md)，则 AND 赋值运算符 `&=` 为隐式重载。</span><span class="sxs-lookup"><span data-stu-id="538c4-110">If a user-defined type [overloads](../keywords/operator.md) the [`&` operator](and-operator.md), the AND assignment operator `&=` is implicitly overloaded.</span></span> <span data-ttu-id="538c4-111">用户定义类型不能显式重载 AND 赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="538c4-111">A user-defined type cannot explicitly overload the AND assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="538c4-112">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="538c4-112">C# language specification</span></span>

<span data-ttu-id="538c4-113">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[复合赋值](~/_csharplang/spec/expressions.md#compound-assignment)部分。</span><span class="sxs-lookup"><span data-stu-id="538c4-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="538c4-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="538c4-114">See also</span></span>

- [<span data-ttu-id="538c4-115">C# 参考</span><span class="sxs-lookup"><span data-stu-id="538c4-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="538c4-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="538c4-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="538c4-117">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="538c4-117">C# Operators</span></span>](index.md)
