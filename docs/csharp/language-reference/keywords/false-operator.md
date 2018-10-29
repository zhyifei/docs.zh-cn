---
title: false 运算符（C# 参考）
ms.date: 07/20/2015
helpviewer_keywords:
- false operator keyword [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: e73113bd37dbb68590267141ad037f78919520bc
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2018
ms.locfileid: "48848057"
---
# <a name="false-operator-c-reference"></a><span data-ttu-id="5cd23-102">false 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5cd23-102">false operator (C# Reference)</span></span>

<span data-ttu-id="5cd23-103">返回 [bool](bool.md) 值 `true` 以指示操作数为 `false`，否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="5cd23-103">Returns the [bool](bool.md) value `true` to indicate that an operand is `false` and returns `false` otherwise.</span></span>

<span data-ttu-id="5cd23-104">在 C# 2.0 之前，`true` 和 `false` 运算符都用于创建用户定义的可为 null 的值类型，该类型可与 `SqlBool` 等类型兼容。</span><span class="sxs-lookup"><span data-stu-id="5cd23-104">Prior to C# 2.0, the `true` and `false` operators were used to create user-defined nullable value types that were compatible with types such as `SqlBool`.</span></span> <span data-ttu-id="5cd23-105">但是，现在该语言提供对可为 null 的值类型的内置支持，并且应尽可能使用这些支持而不是重载 `true` 和 `false` 运算符。</span><span class="sxs-lookup"><span data-stu-id="5cd23-105">However, the language now provides built-in support for nullable value types, and whenever possible you should use those instead of overloading the `true` and `false` operators.</span></span> <span data-ttu-id="5cd23-106">有关详细信息，请参阅[可以为 Null 的类型](../../programming-guide/nullable-types/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5cd23-106">For more information, see [Nullable Types](../../programming-guide/nullable-types/index.md).</span></span>

<span data-ttu-id="5cd23-107">对于可以为 null 的布尔值，表达式 `a != b` 不一定等同于 `!(a == b)`，因为两个值（或之一）可能为 null。</span><span class="sxs-lookup"><span data-stu-id="5cd23-107">With nullable Booleans, the expression `a != b` is not necessarily equal to `!(a == b)` because one or both of the values might be null.</span></span> <span data-ttu-id="5cd23-108">必须分别重载 `true` 和 `false` 运算符以正确处理表达式中的 null 值。</span><span class="sxs-lookup"><span data-stu-id="5cd23-108">You have to overload both the `true` and `false` operators separately to correctly handle the null values in the expression.</span></span> <span data-ttu-id="5cd23-109">下面的示例演示如何重载和使用 `true` 和 `false` 运算符。</span><span class="sxs-lookup"><span data-stu-id="5cd23-109">The following example shows how to overload and use the `true` and `false` operators.</span></span>

[!code-csharp[csrefKeywordsOperator#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#16)]

<span data-ttu-id="5cd23-110">重载 `true` 和 `false` 运算符的类型可以用于 [if](if-else.md)、[do](do.md)、[while](while.md) 和 [for](for.md) 语句以及[条件表达式](../operators/conditional-operator.md)中的控制表达式。</span><span class="sxs-lookup"><span data-stu-id="5cd23-110">A type that overloads the `true` and `false` operators can be used for the controlling expression in [if](if-else.md), [do](do.md), [while](while.md), and [for](for.md) statements and in [conditional expressions](../operators/conditional-operator.md).</span></span>

<span data-ttu-id="5cd23-111">如果某一类型定义运算符 `false`，则它还必须定义运算符 [true](true.md)。</span><span class="sxs-lookup"><span data-stu-id="5cd23-111">If a type defines operator `false`, it must also define operator [true](true.md).</span></span>

<span data-ttu-id="5cd23-112">类型不能直接重载条件逻辑运算符 [&&](../operators/conditional-and-operator.md) 和 [&#124;&#124;](../operators/conditional-or-operator.md)，但可以通过重载常规逻辑运算符及运算符 `true` 和 `false` 达到同样的效果。</span><span class="sxs-lookup"><span data-stu-id="5cd23-112">A type cannot directly overload the conditional logical operators [&&](../operators/conditional-and-operator.md) and [&#124;&#124;](../operators/conditional-or-operator.md), but an equivalent effect can be achieved by overloading the regular logical operators and operators `true` and `false`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5cd23-113">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5cd23-113">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5cd23-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="5cd23-114">See also</span></span>

- [<span data-ttu-id="5cd23-115">C# 参考</span><span class="sxs-lookup"><span data-stu-id="5cd23-115">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="5cd23-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5cd23-116">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="5cd23-117">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="5cd23-117">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="5cd23-118">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="5cd23-118">C# Operators</span></span>](../operators/index.md)  
- [<span data-ttu-id="5cd23-119">true</span><span class="sxs-lookup"><span data-stu-id="5cd23-119">true</span></span>](true.md)  