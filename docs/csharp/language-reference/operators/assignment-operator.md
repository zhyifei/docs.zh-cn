---
title: = 运算符 - C# 参考
ms.custom: seodec18
ms.date: 06/21/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: ef9c9bab5c1cebb06edf934254507180e2197349
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306570"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="3987e-102">= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3987e-102">= operator (C# reference)</span></span>

<span data-ttu-id="3987e-103">赋值运算符 `=` 将其右操作数的值赋给变量、[属性](../../programming-guide/classes-and-structs/properties.md)或由其左操作数给出的[索引器](../../../csharp/programming-guide/indexers/index.md)元素。</span><span class="sxs-lookup"><span data-stu-id="3987e-103">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../../csharp/programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="3987e-104">赋值表达式的结果是分配给左操作数的值。</span><span class="sxs-lookup"><span data-stu-id="3987e-104">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="3987e-105">右操作数类型必须与左操作数类型相同，或可隐式转换为左操作数的类型。</span><span class="sxs-lookup"><span data-stu-id="3987e-105">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="3987e-106">赋值运算符为右联运算符，即形式的表达式</span><span class="sxs-lookup"><span data-stu-id="3987e-106">The assignment operator is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="3987e-107">计算结果为</span><span class="sxs-lookup"><span data-stu-id="3987e-107">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="3987e-108">以下示例演示使用局部变量、属性和索引器元素作为其左操作数的赋值运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="3987e-108">The following example demonstrates the usage of the assignment operator with a local variable, a property, and an indexer element as its left-hand operand:</span></span>

[!code-csharp-interactive[simple assignment](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#Simple)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="3987e-109">ref 赋值运算符</span><span class="sxs-lookup"><span data-stu-id="3987e-109">ref assignment operator</span></span>

<span data-ttu-id="3987e-110">从 C# 7.3 开始，可以使用 ref 赋值运算符 `= ref` 重新分配 [ref local](../keywords/ref.md#ref-locals) 或 [ref readonly local](../keywords/ref.md#ref-readonly-locals) 变量。</span><span class="sxs-lookup"><span data-stu-id="3987e-110">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="3987e-111">下面的示例演示 ref 赋值运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="3987e-111">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#RefAssignment)]

<span data-ttu-id="3987e-112">对于 ref 赋值运算符，其两个操作数的类型必须相同。</span><span class="sxs-lookup"><span data-stu-id="3987e-112">In the case of the ref assignment operator, the type of both its operands must be the same.</span></span>

<span data-ttu-id="3987e-113">有关详细信息，请参阅[功能建议说明](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md)。</span><span class="sxs-lookup"><span data-stu-id="3987e-113">For more information, see the [feature proposal note](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="3987e-114">复合赋值</span><span class="sxs-lookup"><span data-stu-id="3987e-114">Compound assignment</span></span>

<span data-ttu-id="3987e-115">对于二元运算符 `op`，窗体的复合赋值表达式</span><span class="sxs-lookup"><span data-stu-id="3987e-115">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="3987e-116">等效于</span><span class="sxs-lookup"><span data-stu-id="3987e-116">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="3987e-117">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="3987e-117">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="3987e-118">[算术](arithmetic-operators.md#compound-assignment)、[布尔逻辑](boolean-logical-operators.md#compound-assignment)以及[逻辑位和移位](bitwise-and-shift-operators.md#compound-assignment)运算符支持复合赋值。</span><span class="sxs-lookup"><span data-stu-id="3987e-118">Compound assignment is supported by [arithmetic](arithmetic-operators.md#compound-assignment), [Boolean logical](boolean-logical-operators.md#compound-assignment), and [bitwise logical and shift](bitwise-and-shift-operators.md#compound-assignment) operators.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="3987e-119">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="3987e-119">Operator overloadability</span></span>

<span data-ttu-id="3987e-120">用户定义类型不能重载赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="3987e-120">A user-defined type cannot overload the assignment operator.</span></span> <span data-ttu-id="3987e-121">但是，用户定义类型可以定义到其他类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="3987e-121">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="3987e-122">这样，可以将用户定义类型的值分配给其他类型的变量、属性或索引器元素。</span><span class="sxs-lookup"><span data-stu-id="3987e-122">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="3987e-123">有关详细信息，请参阅[隐式](../keywords/implicit.md)关键字一文。</span><span class="sxs-lookup"><span data-stu-id="3987e-123">For more information, see the [implicit](../keywords/implicit.md) keyword article.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3987e-124">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="3987e-124">C# language specification</span></span>

<span data-ttu-id="3987e-125">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[分配运算符](~/_csharplang/spec/expressions.md#assignment-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="3987e-125">For more information, see the [Assignment operators](~/_csharplang/spec/expressions.md#assignment-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3987e-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="3987e-126">See also</span></span>

- [<span data-ttu-id="3987e-127">C# 参考</span><span class="sxs-lookup"><span data-stu-id="3987e-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="3987e-128">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="3987e-128">C# operators</span></span>](index.md)
- [<span data-ttu-id="3987e-129">ref 关键字</span><span class="sxs-lookup"><span data-stu-id="3987e-129">ref keyword</span></span>](../keywords/ref.md)
