---
title: '>>= 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 51914bb5e9ebffd5d868528b5a8d3072a956cea6
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220908"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="1604a-102">>>= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="1604a-102">>>= operator (C# Reference)</span></span>

<span data-ttu-id="1604a-103">右移赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="1604a-103">The right-shift assignment operator.</span></span>

<span data-ttu-id="1604a-104">使用 `>>=` 运算符的表达式，例如</span><span class="sxs-lookup"><span data-stu-id="1604a-104">An expression using the `>>=` operator, such as</span></span>

```csharp
x >>= y
```

<span data-ttu-id="1604a-105">等效于</span><span class="sxs-lookup"><span data-stu-id="1604a-105">is equivalent to</span></span>

```csharp
x = x >> y
```

<span data-ttu-id="1604a-106">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="1604a-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="1604a-107">[`>>` 运算符](right-shift-operator.md) 将第一个操作数向右移动第二个操作数定义的位数。</span><span class="sxs-lookup"><span data-stu-id="1604a-107">The [`>>` operator](right-shift-operator.md) shifts its first operand right by the number of bits defined by its second operand.</span></span>

<span data-ttu-id="1604a-108">下面的示例演示 `>>=` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="1604a-108">The following example demonstrates the usage of the `>>=` operator:</span></span>

[!code-csharp-interactive[right shift assignment](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShiftAssignment)]

## <a name="operator-overloadability"></a><span data-ttu-id="1604a-109">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="1604a-109">Operator overloadability</span></span>

<span data-ttu-id="1604a-110">如果用户定义类型[重载](../keywords/operator.md) [`>>` 运算符](right-shift-operator.md)，则隐式重载右移赋值运算符 `>>=`。</span><span class="sxs-lookup"><span data-stu-id="1604a-110">If a user-defined type [overloads](../keywords/operator.md) the [`>>` operator](right-shift-operator.md), the right-shift assignment operator `>>=` is implicitly overloaded.</span></span> <span data-ttu-id="1604a-111">用户定义类型不得显式重载右移赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="1604a-111">A user-defined type cannot explicitly overload the right-shift assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1604a-112">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="1604a-112">C# language specification</span></span>

<span data-ttu-id="1604a-113">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[复合赋值](~/_csharplang/spec/expressions.md#compound-assignment)部分。</span><span class="sxs-lookup"><span data-stu-id="1604a-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1604a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="1604a-114">See also</span></span>

- [<span data-ttu-id="1604a-115">C# 参考</span><span class="sxs-lookup"><span data-stu-id="1604a-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1604a-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="1604a-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1604a-117">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="1604a-117">C# operators</span></span>](index.md)