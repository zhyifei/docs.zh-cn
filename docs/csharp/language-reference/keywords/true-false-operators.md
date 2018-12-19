---
title: true 和 false 运算符 - C# 参考
ms.custom: seodec18
ms.date: 12/10/2018
helpviewer_keywords:
- false operator [C#]
- true operator [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: 0a75566fdb6222157ecda12a50fd78e22f92fcb4
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245728"
---
# <a name="true-and-false-operators-c-reference"></a><span data-ttu-id="0945c-102">true 和 false 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="0945c-102">true and false operators (C# Reference)</span></span>

<span data-ttu-id="0945c-103">`true` 运算符返回 [bool](bool.md) 值 `true`，以指明操作数一定为 true。</span><span class="sxs-lookup"><span data-stu-id="0945c-103">The `true` operator returns the [bool](bool.md) value `true` to indicate that an operand is definitely true.</span></span> <span data-ttu-id="0945c-104">`false` 运算符返回 `bool` 值 `true`，以指明操作数一定为 false。</span><span class="sxs-lookup"><span data-stu-id="0945c-104">The `false` operator returns the `bool` value `true` to indicate that an operand is definitely false.</span></span> <span data-ttu-id="0945c-105">无法确保 `true` 和 `false` 运算符互补。</span><span class="sxs-lookup"><span data-stu-id="0945c-105">The `true` and `false` operators are not guaranteed to complement each other.</span></span> <span data-ttu-id="0945c-106">也就是说，`true` 和 `false` 运算符可能同时针对同一个操作数返回 `bool` 值 `false`。</span><span class="sxs-lookup"><span data-stu-id="0945c-106">That is, both the `true` and `false` operator might return the `bool` value `false` for the same operand.</span></span> <span data-ttu-id="0945c-107">如果某类型定义这两个运算符之一，它还必须定义另一个运算符。</span><span class="sxs-lookup"><span data-stu-id="0945c-107">If a type defines one of the two operators, it must also define another operator.</span></span>

<span data-ttu-id="0945c-108">如果包含已定义 `true` 和 `false` 运算符的类型以某种方式[重载](operator.md)[逻辑 OR 运算符](../operators/or-operator.md) `|` 或[逻辑 AND 运算符](../operators/and-operator.md) `&`，可以对相应类型的操作数分别执行[条件逻辑 OR 运算符](../operators/conditional-or-operator.md) `||` 或[条件逻辑 AND 运算符](../operators/conditional-and-operator.md) `&&` 运算。</span><span class="sxs-lookup"><span data-stu-id="0945c-108">If a type with the defined `true` and `false` operators [overloads](operator.md) the [logical OR operator](../operators/or-operator.md) `|` or the [logical AND operator](../operators/and-operator.md) `&` in a certain way, the [conditional logical OR operator](../operators/conditional-or-operator.md) `||` or [conditional logical AND operator](../operators/conditional-and-operator.md) `&&`, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="0945c-109">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[用户定义条件逻辑运算符](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="0945c-109">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

<span data-ttu-id="0945c-110">包含已定义 `true` 运算符的类型可以是 [if](if-else.md)、[do](do.md)、[while](while.md) 和 [for](for.md) 语句以及[条件运算符 `?:`](../operators/conditional-operator.md) 中控制条件表达式的结果的类型。</span><span class="sxs-lookup"><span data-stu-id="0945c-110">A type with the defined `true` operator can be the type of a result of a controlling conditional expression in the [if](if-else.md), [do](do.md), [while](while.md), and [for](for.md) statements and in the [conditional operator `?:`](../operators/conditional-operator.md).</span></span> <span data-ttu-id="0945c-111">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的 [Boolean 表达式](~/_csharplang/spec/expressions.md#boolean-expressions)部分。</span><span class="sxs-lookup"><span data-stu-id="0945c-111">For more information, see the [Boolean expressions](~/_csharplang/spec/expressions.md#boolean-expressions) section of the [C# language specification](../language-specification/index.md).</span></span>

> [!TIP]
> <span data-ttu-id="0945c-112">如需支持三值逻辑（例如，在使用支持三值逻辑类型的数据库时），请使用 `bool?` 类型。</span><span class="sxs-lookup"><span data-stu-id="0945c-112">Use the `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued logical type.</span></span> <span data-ttu-id="0945c-113">有关详细信息，请参阅[使用可以为 null 的类型](../../programming-guide/nullable-types/using-nullable-types.md)一文的 [bool? 类型](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type)部分。</span><span class="sxs-lookup"><span data-stu-id="0945c-113">For more information, see [The bool? type](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="0945c-114">下面的示例展示了定义 `true` 和 `false` 运算符的类型。</span><span class="sxs-lookup"><span data-stu-id="0945c-114">The following example presents the type that defines both `true` and `false` operators.</span></span> <span data-ttu-id="0945c-115">此外，它还重载了逻辑 AND 运算符 `&`，因此也可以对相应类型的操作数执行运算符 `&&` 运算。</span><span class="sxs-lookup"><span data-stu-id="0945c-115">Moreover, it overloads the logical AND operator `&` in such a way that the operator `&&` also can be evaluated for the operands of that type.</span></span>

[!code-csharp-interactive[true and false operators example](~/samples/snippets/csharp/keywords/TrueFalseOperatorsExample.cs)]

<span data-ttu-id="0945c-116">请注意 `&&` 运算符的短路行为。</span><span class="sxs-lookup"><span data-stu-id="0945c-116">Notice the short-circuiting behavior of the `&&` operator.</span></span> <span data-ttu-id="0945c-117">当 `GetFuelLaunchStatus` 方法返回 `LaunchStatus.Red` 时，不会计算 `&&` 运算符的第二个操作数。</span><span class="sxs-lookup"><span data-stu-id="0945c-117">When the `GetFuelLaunchStatus` method returns `LaunchStatus.Red`, the second operand of the `&&` operator is not evaluated.</span></span> <span data-ttu-id="0945c-118">这是因为 `LaunchStatus.Red` 一定为 false。</span><span class="sxs-lookup"><span data-stu-id="0945c-118">That is because `LaunchStatus.Red` is definitely false.</span></span> <span data-ttu-id="0945c-119">然后，逻辑 AND 运算符的结果不依赖第二个操作数的值。</span><span class="sxs-lookup"><span data-stu-id="0945c-119">Then the result of the logical AND doesn't depend on the value of the second operand.</span></span> <span data-ttu-id="0945c-120">示例输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="0945c-120">The output of the example is as follows:</span></span>

```console
Getting fuel launch status...
Wait!
```

## <a name="see-also"></a><span data-ttu-id="0945c-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="0945c-121">See also</span></span>

- [<span data-ttu-id="0945c-122">C# 参考</span><span class="sxs-lookup"><span data-stu-id="0945c-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0945c-123">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="0945c-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0945c-124">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="0945c-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0945c-125">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="0945c-125">C# Operators</span></span>](../operators/index.md)
- [<span data-ttu-id="0945c-126">`true` 文本</span><span class="sxs-lookup"><span data-stu-id="0945c-126">`true` literal</span></span>](true-literal.md)
- [<span data-ttu-id="0945c-127">`false` 文本</span><span class="sxs-lookup"><span data-stu-id="0945c-127">`false` literal</span></span>](false-literal.md)