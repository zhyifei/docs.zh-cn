---
title: 赋值运算符 - C# 参考
ms.date: 09/10/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 420b41f586a6980d40cf1171eef00dad37bf5abf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398057"
---
# <a name="assignment-operators-c-reference"></a><span data-ttu-id="01489-102">赋值运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="01489-102">Assignment operators (C# reference)</span></span>

<span data-ttu-id="01489-103">赋值运算符 `=` 将其右操作数的值赋给变量、[属性](../../programming-guide/classes-and-structs/properties.md)或由其左操作数给出的[索引器](../../programming-guide/indexers/index.md)元素。</span><span class="sxs-lookup"><span data-stu-id="01489-103">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="01489-104">赋值表达式的结果是分配给左操作数的值。</span><span class="sxs-lookup"><span data-stu-id="01489-104">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="01489-105">右操作数类型必须与左操作数类型相同，或可隐式转换为左操作数的类型。</span><span class="sxs-lookup"><span data-stu-id="01489-105">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="01489-106">赋值运算符 `=` 为右联运算符，即形式的表达式</span><span class="sxs-lookup"><span data-stu-id="01489-106">The assignment operator `=` is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="01489-107">计算结果为</span><span class="sxs-lookup"><span data-stu-id="01489-107">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="01489-108">以下示例演示使用局部变量、属性和索引器元素作为其左操作数的赋值运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="01489-108">The following example demonstrates the usage of the assignment operator with a local variable, a property, and an indexer element as its left-hand operand:</span></span>

[!code-csharp-interactive[simple assignment](snippets/AssignmentOperator.cs#Simple)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="01489-109">ref 赋值运算符</span><span class="sxs-lookup"><span data-stu-id="01489-109">ref assignment operator</span></span>

<span data-ttu-id="01489-110">从 C# 7.3 开始，可以使用 ref 赋值运算符 `= ref` 重新分配 [ref local](../keywords/ref.md#ref-locals) 或 [ref readonly local](../keywords/ref.md#ref-readonly-locals) 变量。</span><span class="sxs-lookup"><span data-stu-id="01489-110">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="01489-111">下面的示例演示 ref 赋值运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="01489-111">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](snippets/AssignmentOperator.cs#RefAssignment)]

<span data-ttu-id="01489-112">对于 ref 赋值运算符，其两个操作数的类型必须相同。</span><span class="sxs-lookup"><span data-stu-id="01489-112">In the case of the ref assignment operator, the both of its operands must be of the same type.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="01489-113">复合赋值</span><span class="sxs-lookup"><span data-stu-id="01489-113">Compound assignment</span></span>

<span data-ttu-id="01489-114">对于二元运算符 `op`，窗体的复合赋值表达式</span><span class="sxs-lookup"><span data-stu-id="01489-114">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="01489-115">等效于</span><span class="sxs-lookup"><span data-stu-id="01489-115">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="01489-116">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="01489-116">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="01489-117">[算术](arithmetic-operators.md#compound-assignment)、[布尔逻辑](boolean-logical-operators.md#compound-assignment)以及[逻辑位和移位](bitwise-and-shift-operators.md#compound-assignment)运算符支持复合赋值。</span><span class="sxs-lookup"><span data-stu-id="01489-117">Compound assignment is supported by [arithmetic](arithmetic-operators.md#compound-assignment), [Boolean logical](boolean-logical-operators.md#compound-assignment), and [bitwise logical and shift](bitwise-and-shift-operators.md#compound-assignment) operators.</span></span>

## <a name="null-coalescing-assignment"></a><span data-ttu-id="01489-118">Null 合并赋值</span><span class="sxs-lookup"><span data-stu-id="01489-118">Null-coalescing assignment</span></span>

<span data-ttu-id="01489-119">从 C# 8.0 开始，只有在左操作数计算为 `??=` 时，才能使用 null 合并赋值运算符 `null` 将其右操作数的值分配给左操作数。</span><span class="sxs-lookup"><span data-stu-id="01489-119">Beginning with C# 8.0, you can use the null-coalescing assignment operator `??=` to assign the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="01489-120">有关详细信息，请参阅 [?? 和 ??= 运算符](null-coalescing-operator.md)一文。</span><span class="sxs-lookup"><span data-stu-id="01489-120">For more information, see the [?? and ??= operators](null-coalescing-operator.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="01489-121">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="01489-121">Operator overloadability</span></span>

<span data-ttu-id="01489-122">用户定义类型不能[重载](operator-overloading.md)赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="01489-122">A user-defined type cannot [overload](operator-overloading.md) the assignment operator.</span></span> <span data-ttu-id="01489-123">但是，用户定义类型可以定义到其他类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="01489-123">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="01489-124">这样，可以将用户定义类型的值分配给其他类型的变量、属性或索引器元素。</span><span class="sxs-lookup"><span data-stu-id="01489-124">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="01489-125">有关详细信息，请参阅[用户定义转换运算符](user-defined-conversion-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="01489-125">For more information, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

<span data-ttu-id="01489-126">用户定义类型不能显式重载复合赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="01489-126">A user-defined type cannot explicitly overload a compound assignment operator.</span></span> <span data-ttu-id="01489-127">但是，如果用户定义类型重载了二元运算符 `op`，则 `op=` 运算符（如果存在）也将被隐式重载。</span><span class="sxs-lookup"><span data-stu-id="01489-127">However, if a user-defined type overloads a binary operator `op`, the `op=` operator, if it exists, is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="01489-128">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="01489-128">C# language specification</span></span>

<span data-ttu-id="01489-129">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/expressions.md#assignment-operators)中的[分配运算符](~/_csharplang/spec/introduction.md)部分。</span><span class="sxs-lookup"><span data-stu-id="01489-129">For more information, see the [Assignment operators](~/_csharplang/spec/expressions.md#assignment-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="01489-130">如需了解有关 ref 赋值运算符 `= ref` 的详细信息，请参阅[功能建议说明](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md)。</span><span class="sxs-lookup"><span data-stu-id="01489-130">For more information about the ref assignment operator `= ref`, see the [feature proposal note](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="01489-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01489-131">See also</span></span>

- [<span data-ttu-id="01489-132">C# 参考</span><span class="sxs-lookup"><span data-stu-id="01489-132">C# reference</span></span>](../index.md)
- [<span data-ttu-id="01489-133">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="01489-133">C# operators</span></span>](index.md)
- [<span data-ttu-id="01489-134">ref 关键字</span><span class="sxs-lookup"><span data-stu-id="01489-134">ref keyword</span></span>](../keywords/ref.md)
