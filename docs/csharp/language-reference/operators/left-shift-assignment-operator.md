---
title: <<= 运算符 - C# 参考
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: d2105fbee4ddfe1b2cb3325d82b0f2f8c5559297
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219444"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="40379-102">\<\<= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="40379-102">\<\<= operator (C# Reference)</span></span>

<span data-ttu-id="40379-103">左移赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="40379-103">The left-shift assignment operator.</span></span>

<span data-ttu-id="40379-104">使用 `<<=` 运算符的表达式，例如</span><span class="sxs-lookup"><span data-stu-id="40379-104">An expression using the `<<=` operator, such as</span></span>

```csharp
x <<= y
```

<span data-ttu-id="40379-105">等效于</span><span class="sxs-lookup"><span data-stu-id="40379-105">is equivalent to</span></span>

```csharp
x = x << y
```

<span data-ttu-id="40379-106">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="40379-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="40379-107">[`<<` 运算符](left-shift-operator.md) 将第一个操作数向左移动第二个操作数定义的位数。</span><span class="sxs-lookup"><span data-stu-id="40379-107">The [`<<` operator](left-shift-operator.md) shifts its first operand left by the number of bits defined by its second operand.</span></span>

<span data-ttu-id="40379-108">下面的示例演示 `<<=` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="40379-108">The following example demonstrates the usage of the `<<=` operator:</span></span>

[!code-csharp-interactive[left shift assignment](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShiftAssignment)]

## <a name="operator-overloadability"></a><span data-ttu-id="40379-109">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="40379-109">Operator overloadability</span></span>

<span data-ttu-id="40379-110">如果用户定义类型[重载](../keywords/operator.md) [`<<` 运算符](left-shift-operator.md)，则会隐式重载左移赋值运算符 `<<=`。</span><span class="sxs-lookup"><span data-stu-id="40379-110">If a user-defined type [overloads](../keywords/operator.md) the [`<<` operator](left-shift-operator.md), the left-shift assignment operator `<<=` is implicitly overloaded.</span></span> <span data-ttu-id="40379-111">用户定义类型不得显式重载左移赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="40379-111">A user-defined type cannot explicitly overload the left-shift assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="40379-112">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="40379-112">C# language specification</span></span>

<span data-ttu-id="40379-113">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[复合赋值](~/_csharplang/spec/expressions.md#compound-assignment)部分。</span><span class="sxs-lookup"><span data-stu-id="40379-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="40379-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="40379-114">See also</span></span>

- [<span data-ttu-id="40379-115">C# 参考</span><span class="sxs-lookup"><span data-stu-id="40379-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="40379-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="40379-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="40379-117">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="40379-117">C# Operators</span></span>](index.md)
