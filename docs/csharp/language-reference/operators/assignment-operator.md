---
title: = 运算符（C# 参考）
ms.date: 11/26/2018
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 123674f37d17db6dcfe6ae9d45c7176bdff1eda7
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149219"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c368b-102">= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c368b-102">= Operator (C# Reference)</span></span>

<span data-ttu-id="c368b-103">赋值运算符 `=` 将其右操作数的值赋给变量、[属性](../../programming-guide/classes-and-structs/properties.md)或由其左操作数给出的[索引器](../../../csharp/programming-guide/indexers/index.md)元素。</span><span class="sxs-lookup"><span data-stu-id="c368b-103">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../../csharp/programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="c368b-104">赋值表达式的结果是分配给左操作数的值。</span><span class="sxs-lookup"><span data-stu-id="c368b-104">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="c368b-105">右操作数类型必须与左操作数类型相同，或可隐式转换为左操作数的类型。</span><span class="sxs-lookup"><span data-stu-id="c368b-105">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="c368b-106">赋值运算符为右联运算符，即形式的表达式</span><span class="sxs-lookup"><span data-stu-id="c368b-106">The assignment operator is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="c368b-107">计算结果为</span><span class="sxs-lookup"><span data-stu-id="c368b-107">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="c368b-108">以下示例演示赋值运算符将值分配给局部变量、属性和索引器元素的用法：</span><span class="sxs-lookup"><span data-stu-id="c368b-108">The following example demonstrates the usage of the assignment operator to assign values to a local variable, a property, and an indexer element:</span></span>

[!code-csharp-interactive[assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#Assignments)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="c368b-109">ref 赋值运算符</span><span class="sxs-lookup"><span data-stu-id="c368b-109">ref assignment operator</span></span>

<span data-ttu-id="c368b-110">从 C# 7.3 开始，可以使用 ref 赋值运算符 `= ref` 重新分配 [ref local](../keywords/ref.md#ref-locals) 或 [ref readonly local](../keywords/ref.md#ref-readonly-locals) 变量。</span><span class="sxs-lookup"><span data-stu-id="c368b-110">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="c368b-111">下面的示例演示 ref 赋值运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="c368b-111">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#RefAssignment)]

<span data-ttu-id="c368b-112">对于 ref 赋值运算符，左操作数和右操作数的类型必须相同。</span><span class="sxs-lookup"><span data-stu-id="c368b-112">In the case of the ref assignment operator, the type of the left operand and the right operand must be the same.</span></span>

<span data-ttu-id="c368b-113">有关详细信息，请参阅[功能建议说明](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.3/ref-local-reassignment.md)。</span><span class="sxs-lookup"><span data-stu-id="c368b-113">For more information, see the [feature proposal note](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="c368b-114">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="c368b-114">Operator overloadability</span></span>

<span data-ttu-id="c368b-115">用户定义类型不能重载赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="c368b-115">A user-defined type cannot overload the assignment operator.</span></span> <span data-ttu-id="c368b-116">但是，用户定义类型可以定义到其他类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="c368b-116">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="c368b-117">这样，可以将用户定义类型的值分配给其他类型的变量、属性或索引器元素。</span><span class="sxs-lookup"><span data-stu-id="c368b-117">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="c368b-118">有关详细信息，请参阅[隐式](../keywords/implicit.md)关键字一文。</span><span class="sxs-lookup"><span data-stu-id="c368b-118">For more information, see the [implicit](../keywords/implicit.md) keyword article.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c368b-119">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="c368b-119">C# language specification</span></span>

<span data-ttu-id="c368b-120">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[简单赋值](~/_csharplang/spec/expressions.md#simple-assignment)部分。</span><span class="sxs-lookup"><span data-stu-id="c368b-120">For more information, see the [Simple assignment](~/_csharplang/spec/expressions.md#simple-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c368b-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="c368b-121">See also</span></span>

- [<span data-ttu-id="c368b-122">C# 参考</span><span class="sxs-lookup"><span data-stu-id="c368b-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c368b-123">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c368b-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c368b-124">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="c368b-124">C# Operators</span></span>](index.md)
- [<span data-ttu-id="c368b-125">ref 关键字</span><span class="sxs-lookup"><span data-stu-id="c368b-125">ref keyword</span></span>](../keywords/ref.md)
