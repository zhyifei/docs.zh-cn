---
title: ?:运算符 - C# 参考
ms.custom: seodec18
ms.date: 11/20/2018
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: c03fa202b413c98230ba70ca7a0b709d7865cb91
ms.sourcegitcommit: d21bee9dbd32b9540ad30f9d0e2e874227040be3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59427378"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c8cd3-102">?:运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c8cd3-102">?: Operator (C# Reference)</span></span>

<span data-ttu-id="c8cd3-103">条件运算符 (`?:`) 通常被称为三元条件运算符，用于计算 Boolean 表达式，并根据 Boolean 表达式的计算结果为 `true` 还是 `false` 来返回计算两个表达式其中之一的结果。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-103">The conditional operator `?:`, commonly known as the ternary conditional operator, evaluates a Boolean expression, and returns the result of evaluating one of two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span> <span data-ttu-id="c8cd3-104">从 C# 7.2 开始，[ref 条件表达式](#conditional-ref-expression)将返回对两个表示式之一的结果的引用。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-104">Beginning with C# 7.2, the [conditional ref expression](#conditional-ref-expression) returns the reference to the result of one of the two expressions.</span></span>

<span data-ttu-id="c8cd3-105">条件运算符的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="c8cd3-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="c8cd3-106">`condition` 表达式的计算结果必须为 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="c8cd3-107">若 `condition` 的计算结果为 `true`，将计算 `consequent`，其结果成为运算结果。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-107">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="c8cd3-108">若 `condition` 的计算结果为 `false`，将计算 `alternative`，其结果成为运算结果。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="c8cd3-109">只会计算 `consequent` 或 `alternative`。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-109">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="c8cd3-110">`consequent` 和 `alternative` 的类型必须相同，或者必须存在从一种类型到另一种类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-110">The type of `consequent` and `alternative` must be the same, or there must be an implicit conversion from one type to the other.</span></span>

<span data-ttu-id="c8cd3-111">条件运算符为右联运算符，即形式的表达式</span><span class="sxs-lookup"><span data-stu-id="c8cd3-111">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="c8cd3-112">计算结果为</span><span class="sxs-lookup"><span data-stu-id="c8cd3-112">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

<span data-ttu-id="c8cd3-113">下面的示例演示条件运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="c8cd3-113">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp[non ref conditional](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="c8cd3-114">ref 条件表达式</span><span class="sxs-lookup"><span data-stu-id="c8cd3-114">Conditional ref expression</span></span>

<span data-ttu-id="c8cd3-115">从 C# 7.2 开始，可以使用 ref 条件表达式返回对两个表示式之一的结果的引用。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-115">Beginning with C# 7.2, you can use the conditional ref expression to return the reference to the result of one of the two expressions.</span></span> <span data-ttu-id="c8cd3-116">可以将该引用分配到 [ref local](../keywords/ref.md#ref-locals) 或 [ref readonly local](../keywords/ref.md#ref-readonly-locals) 变量，或将它用作[引用返回值](../keywords/ref.md#reference-return-values)或 [`ref` 方法参数](../keywords/ref.md#passing-an-argument-by-reference)。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-116">You can assign that reference to a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable, or use it as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method parameter](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="c8cd3-117">ref 条件表达式的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="c8cd3-117">The syntax for the conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="c8cd3-118">ref 条件表达式与原始的条件运算符相似，仅计算两个表达式其中之一：`consequent` 或 `alternative`。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-118">Like the original conditional operator, the conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="c8cd3-119">在 ref 条件表达式中，`consequent` 和 `alternative` 的类型必须相同。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-119">In the case of the conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span>

<span data-ttu-id="c8cd3-120">下面的示例演示 ref 条件表达式的用法：</span><span class="sxs-lookup"><span data-stu-id="c8cd3-120">The following example demonstrates the usage of the conditional ref expression:</span></span>

[!code-csharp[conditional ref](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

<span data-ttu-id="c8cd3-121">有关详细信息，请参阅[功能建议说明](../../../../_csharplang/proposals/csharp-7.2/conditional-ref.md)。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-121">For more information, see the [feature proposal note](../../../../_csharplang/proposals/csharp-7.2/conditional-ref.md).</span></span>

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="c8cd3-122">条件运算符和 `if..else` 语句</span><span class="sxs-lookup"><span data-stu-id="c8cd3-122">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="c8cd3-123">需要根据条件计算值时，在 [if-else](../keywords/if-else.md) 语句中使用条件运算符可以使代码更简洁。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-123">Use of the conditional operator over an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="c8cd3-124">下面的示例演示了将整数归类为负数或非负数的两种方法：</span><span class="sxs-lookup"><span data-stu-id="c8cd3-124">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="c8cd3-125">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="c8cd3-125">Operator overloadability</span></span>

<span data-ttu-id="c8cd3-126">无法重载条件运算符。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-126">The conditional operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c8cd3-127">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="c8cd3-127">C# language specification</span></span>

<span data-ttu-id="c8cd3-128">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[条件运算符](~/_csharplang/spec/expressions.md#conditional-operator)部分。</span><span class="sxs-lookup"><span data-stu-id="c8cd3-128">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c8cd3-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8cd3-129">See also</span></span>

- [<span data-ttu-id="c8cd3-130">C# 参考</span><span class="sxs-lookup"><span data-stu-id="c8cd3-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c8cd3-131">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c8cd3-131">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c8cd3-132">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="c8cd3-132">C# Operators</span></span>](index.md)
- [<span data-ttu-id="c8cd3-133">if-else 语句</span><span class="sxs-lookup"><span data-stu-id="c8cd3-133">if-else statement</span></span>](../keywords/if-else.md)
- [<span data-ttu-id="c8cd3-134">?.</span><span class="sxs-lookup"><span data-stu-id="c8cd3-134">?.</span></span> <span data-ttu-id="c8cd3-135">和 ?[] 运算符</span><span class="sxs-lookup"><span data-stu-id="c8cd3-135">and ?[] Operators</span></span>](null-conditional-operators.md)
- [<span data-ttu-id="c8cd3-136">??</span><span class="sxs-lookup"><span data-stu-id="c8cd3-136">??</span></span> <span data-ttu-id="c8cd3-137">运算符</span><span class="sxs-lookup"><span data-stu-id="c8cd3-137">Operator</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="c8cd3-138">ref 关键字</span><span class="sxs-lookup"><span data-stu-id="c8cd3-138">ref keyword</span></span>](../keywords/ref.md)
