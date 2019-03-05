---
title: '*= 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 70461f79e714e44354fe4137e5360769fa048d3e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967381"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="dd703-102">\*= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="dd703-102">\*= Operator (C# Reference)</span></span>

<span data-ttu-id="dd703-103">乘法赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="dd703-103">The multiplication assignment operator.</span></span>

<span data-ttu-id="dd703-104">使用 `*=` 运算符的表达式，例如</span><span class="sxs-lookup"><span data-stu-id="dd703-104">An expression using the `*=` operator, such as</span></span>

```csharp
x *= y
```

<span data-ttu-id="dd703-105">等效于</span><span class="sxs-lookup"><span data-stu-id="dd703-105">is equivalent to</span></span>

```csharp
x = x * y
```

<span data-ttu-id="dd703-106">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="dd703-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="dd703-107">对于数字类型，[\* 运算符](multiplication-operator.md)计算其操作数的乘积。</span><span class="sxs-lookup"><span data-stu-id="dd703-107">For numeric types, the [\* operator](multiplication-operator.md) computes the product of its operands.</span></span>

<span data-ttu-id="dd703-108">下面的示例演示 `*=` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="dd703-108">The following example demonstrates the usage of the `*=` operator:</span></span>

[!code-csharp-interactive[multiply and assign](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#MultiplyAndAssign)]

## <a name="operator-overloadability"></a><span data-ttu-id="dd703-109">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="dd703-109">Operator overloadability</span></span>

<span data-ttu-id="dd703-110">如果用户定义类型[重载](../keywords/operator.md)[乘法运算符](multiplication-operator.md) `*`，则乘法赋值运算符 `*=` 为隐式重载。</span><span class="sxs-lookup"><span data-stu-id="dd703-110">If a user-defined type [overloads](../keywords/operator.md) the [multiplication operator](multiplication-operator.md) `*`, the multiplication assignment operator `*=` is implicitly overloaded.</span></span> <span data-ttu-id="dd703-111">用户定义类型不能显式重载乘法赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="dd703-111">A user-defined type cannot explicitly overload the multiplication assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="dd703-112">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="dd703-112">C# language specification</span></span>

<span data-ttu-id="dd703-113">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[复合赋值](~/_csharplang/spec/expressions.md#compound-assignment)部分。</span><span class="sxs-lookup"><span data-stu-id="dd703-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dd703-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd703-114">See also</span></span>

- [<span data-ttu-id="dd703-115">C# 参考</span><span class="sxs-lookup"><span data-stu-id="dd703-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="dd703-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="dd703-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="dd703-117">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="dd703-117">C# Operators</span></span>](index.md)
