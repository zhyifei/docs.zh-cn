---
title: 成员访问运算符 - C# 参考
description: 了解可用于访问类型成员的 C# 运算符。
ms.date: 05/09/2019
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
helpviewer_keywords:
- member access operators [C#]
- member access operator [C#]
- dot operator [C#]
- . operator [C#]
- subscript operator [C#]
- square brackets [] operator [C#]
- indexer operator [C#]
- '[] operator [C#]'
- null-conditional operators [C#]
- Elvis operator [C#]
- ?. operator [C#]
- ?[] operator [C#]
- invocation operator [C#]
- method call [C#]
- method invocation [C#]
- delegate invocation [C#]
- () operator [C#]
ms.openlocfilehash: de0715a2ac946fa47f0d83ac8569595e622f0b97
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758083"
---
# <a name="member-access-operators-c-reference"></a><span data-ttu-id="5d3ea-103">成员访问运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5d3ea-103">Member access operators (C# Reference)</span></span>

<span data-ttu-id="5d3ea-104">访问类型成员时，可能会使用以下运算符：</span><span class="sxs-lookup"><span data-stu-id="5d3ea-104">You might use the following operators when you access a type member:</span></span>

- <span data-ttu-id="5d3ea-105">[`.`（成员访问）](#member-access-operator-)：用于访问命名空间或类型的成员</span><span class="sxs-lookup"><span data-stu-id="5d3ea-105">[`.` (member access)](#member-access-operator-): to access a member of a namespace or a type</span></span>
- <span data-ttu-id="5d3ea-106">[`[]`（数组元素或索引器访问）](#indexer-operator-)：用于访问数组元素或类型索引器</span><span class="sxs-lookup"><span data-stu-id="5d3ea-106">[`[]` (array element or indexer access)](#indexer-operator-): to access an array element or a type indexer</span></span>
- <span data-ttu-id="5d3ea-107">[`?.` 和 `?[]`（null 条件运算符）](#null-conditional-operators--and-)：仅当操作数为非 null 时才用于执行成员或元素访问运算</span><span class="sxs-lookup"><span data-stu-id="5d3ea-107">[`?.` and `?[]` (null-conditional operators)](#null-conditional-operators--and-): to perform a member or element access operation only if an operand is non-null</span></span>
- <span data-ttu-id="5d3ea-108">[`()`（调用）](#invocation-operator-)：用于调用被访问的方法或调用委托</span><span class="sxs-lookup"><span data-stu-id="5d3ea-108">[`()` (invocation)](#invocation-operator-): to call an accessed method or invoke a delegate</span></span>

## <a name="member-access-operator-"></a><span data-ttu-id="5d3ea-109">成员访问运算符 .</span><span class="sxs-lookup"><span data-stu-id="5d3ea-109">Member access operator .</span></span>

<span data-ttu-id="5d3ea-110">可以使用 `.` 标记来访问命名空间或类型的成员，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="5d3ea-110">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="5d3ea-111">使用 `.` 访问命名空间内的嵌套命名空间，如以下 [`using` directive](../keywords/using-directive.md) 的示例所示：</span><span class="sxs-lookup"><span data-stu-id="5d3ea-111">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NestedNamespace)]

- <span data-ttu-id="5d3ea-112">使用 `.` 构成限定名称  以访问命名空间中的类型，如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="5d3ea-112">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#QualifiedName)]

  <span data-ttu-id="5d3ea-113">使用 [`using` 指令](../keywords/using-directive.md)来使用可选的限定名称。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-113">Use a [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="5d3ea-114">使用 `.` 访问[类型成员](../../programming-guide/classes-and-structs/index.md#members)（静态和非静态），如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="5d3ea-114">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#TypeMemberAccess)]

<span data-ttu-id="5d3ea-115">还可以使用 `.` 访问[扩展方法](../../programming-guide/classes-and-structs/extension-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-115">You can also use `.` to access an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="indexer-operator-"></a><span data-ttu-id="5d3ea-116">索引器运算符 []</span><span class="sxs-lookup"><span data-stu-id="5d3ea-116">Indexer operator []</span></span>

<span data-ttu-id="5d3ea-117">方括号 `[]` 通常用于数组、索引器或指针元素访问。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-117">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

### <a name="array-access"></a><span data-ttu-id="5d3ea-118">数组访问</span><span class="sxs-lookup"><span data-stu-id="5d3ea-118">Array access</span></span>

<span data-ttu-id="5d3ea-119">下面的示例演示如何访问数组元素：</span><span class="sxs-lookup"><span data-stu-id="5d3ea-119">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Arrays)]

<span data-ttu-id="5d3ea-120">如果数组索引超出数组相应维度的边界，将引发 <xref:System.IndexOutOfRangeException>。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-120">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="5d3ea-121">如上述示例所示，在声明数组类型或实例化数组实例时，还会使用方括号。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-121">As the preceding example shows, you also use square brackets when you declare an array type or instantiate an array instance.</span></span>

<span data-ttu-id="5d3ea-122">有关数组的详细信息，请参阅[数组](../../programming-guide/arrays/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-122">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

### <a name="indexer-access"></a><span data-ttu-id="5d3ea-123">索引器访问</span><span class="sxs-lookup"><span data-stu-id="5d3ea-123">Indexer access</span></span>

<span data-ttu-id="5d3ea-124">下面的示例使用 .NET <xref:System.Collections.Generic.Dictionary%602>类型来演示索引器访问：</span><span class="sxs-lookup"><span data-stu-id="5d3ea-124">The following example uses .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Indexers)]

<span data-ttu-id="5d3ea-125">使用索引器，可通过类似于编制数组索引的方式对用户定义类型的实例编制索引。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-125">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="5d3ea-126">与必须是整数的数组索引不同，可以将索引器参数声明为任何类型。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-126">Unlike array indices, which must be integer, the indexer arguments can be declared to be of any type.</span></span>

<span data-ttu-id="5d3ea-127">有关索引器的详细信息，请参阅[索引器](../../programming-guide/indexers/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-127">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="5d3ea-128">[] 的其他用法</span><span class="sxs-lookup"><span data-stu-id="5d3ea-128">Other usages of []</span></span>

<span data-ttu-id="5d3ea-129">要了解指针元素访问，请参阅[与指针相关的运算符](pointer-related-operators.md)一文的[指针元素访问运算符 []](pointer-related-operators.md#pointer-element-access-operator-) 部分。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-129">For information about pointer element access, see the [Pointer element access operator []](pointer-related-operators.md#pointer-element-access-operator-) section of the [Pointer related operators](pointer-related-operators.md) article.</span></span>

<span data-ttu-id="5d3ea-130">方括号还用于指定[属性](../../programming-guide/concepts/attributes/index.md)：</span><span class="sxs-lookup"><span data-stu-id="5d3ea-130">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a><span data-ttu-id="5d3ea-131">Null 条件运算符 ?.</span><span class="sxs-lookup"><span data-stu-id="5d3ea-131">Null-conditional operators ?.</span></span> <span data-ttu-id="5d3ea-132">和 ?[]</span><span class="sxs-lookup"><span data-stu-id="5d3ea-132">and ?[]</span></span>

<span data-ttu-id="5d3ea-133">Null 条件运算符在 C# 6 及更高版本中可用，仅当操作数的计算结果为非 null 时，null 条件运算符才会将成员访问 `?.` 或元素访问 `?[]` 运算应用于其操作数。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-133">Available in C# 6 and later, a null-conditional operator applies a member access, `?.`, or element access, `?[]`, operation to its operand only if that operand evaluates to non-null.</span></span> <span data-ttu-id="5d3ea-134">如果操作数的计算结果为 `null`，则应用运算符的结果为 `null`。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-134">If the operand evaluates to `null`, the result of applying the operator is `null`.</span></span> <span data-ttu-id="5d3ea-135">Null 条件成员访问运算符 `?.` 也称为 Elvis 运算符。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-135">The null-conditional member access operator `?.` is also known as the Elvis operator.</span></span>

<span data-ttu-id="5d3ea-136">NULL 条件运算符采用最小化求值策略。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-136">The null-conditional operators are short-circuiting.</span></span> <span data-ttu-id="5d3ea-137">也就是说，如果条件成员或元素访问运算链中的一个运算返回 `null`，则链的其余部分不会执行。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-137">That is, if one operation in a chain of conditional member or element access operations returns `null`, the rest of the chain doesn't execute.</span></span> <span data-ttu-id="5d3ea-138">在以下示例中，如果 `A` 的计算结果为 `null`，则不会计算 `B`；如果 `A` 或 `B` 的计算结果为 `null`，则不会计算 `C`：</span><span class="sxs-lookup"><span data-stu-id="5d3ea-138">In the following example, `B` is not evaluated if `A` evaluates to `null` and `C` is not evaluated if `A` or `B` evaluates to `null`:</span></span>

```csharp
A?.B?.Do(C);
A?.B?[C];
```

<span data-ttu-id="5d3ea-139">以下示例演示了 `?.` 和 `?[]` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="5d3ea-139">The following example demonstrates the usage of the `?.` and `?[]` operators:</span></span>

[!code-csharp-interactive[null-conditional operators](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NullConditional)]

<span data-ttu-id="5d3ea-140">上述示例还展示了 [null 合并运算符](null-coalescing-operator.md)的用法。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-140">The preceding example also shows the usage of the [null-coalescing operator](null-coalescing-operator.md).</span></span> <span data-ttu-id="5d3ea-141">可能会使用 null 合并运算符来提供替代表达式，以便在 null 条件运算的结果为 `null` 时用于计算。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-141">You might use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the null-conditional operation is `null`.</span></span>

### <a name="thread-safe-delegate-invocation"></a><span data-ttu-id="5d3ea-142">线程安全的委托调用</span><span class="sxs-lookup"><span data-stu-id="5d3ea-142">Thread-safe delegate invocation</span></span>

<span data-ttu-id="5d3ea-143">使用 `?.` 运算符来检查委托是否非 null 并以线程安全的方式调用它（例如，[引发事件](../../../standard/events/how-to-raise-and-consume-events.md)时），如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="5d3ea-143">Use the `?.` operator to check if a delegate is non-null and invoke it in a thread-safe way (for example, when you [raise an event](../../../standard/events/how-to-raise-and-consume-events.md)), as the following code shows:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="5d3ea-144">该代码等同于将在 C# 5 或更低版本中使用的以下代码：</span><span class="sxs-lookup"><span data-stu-id="5d3ea-144">That code is equivalent to the following code that you would use in C# 5 or earlier:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

## <a name="invocation-operator-"></a><span data-ttu-id="5d3ea-145">调用运算符 ()</span><span class="sxs-lookup"><span data-stu-id="5d3ea-145">Invocation operator ()</span></span>

<span data-ttu-id="5d3ea-146">使用括号 `()` 调用[方法](../../programming-guide/classes-and-structs/methods.md)或调用[委托](../../programming-guide/delegates/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-146">Use parentheses, `()`, to call a [method](../../programming-guide/classes-and-structs/methods.md) or invoke a [delegate](../../programming-guide/delegates/index.md).</span></span>

<span data-ttu-id="5d3ea-147">以下示例演示如何在使用或不使用参数的情况下调用方法，以及调用委托：</span><span class="sxs-lookup"><span data-stu-id="5d3ea-147">The following example demonstrates how to call a method, with or without arguments, and invoke a delegate:</span></span>

[!code-csharp-interactive[invocation with ()](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Invocation)]

<span data-ttu-id="5d3ea-148">在调用带 [`new`](../keywords/new-operator.md) 运算符的[构造函数](../../programming-guide/classes-and-structs/constructors.md)时，还可以使用括号。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-148">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with a [`new`](../keywords/new-operator.md) operator.</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="5d3ea-149">() 的其他用法</span><span class="sxs-lookup"><span data-stu-id="5d3ea-149">Other usages of ()</span></span>

<span data-ttu-id="5d3ea-150">此外可以使用括号来指定表达式中计算操作的顺序。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-150">You also use parentheses to specify the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="5d3ea-151">有关详细信息，请参阅[运算符](../../programming-guide/statements-expressions-operators/operators.md)一文中的[添加括号](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses)部分。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-151">For more information, see the [Adding parentheses](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) section of the [Operators](../../programming-guide/statements-expressions-operators/operators.md) article.</span></span> <span data-ttu-id="5d3ea-152">对于按优先级排序的运算符列表，请参阅 [C# 运算符](index.md)。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-152">For the list of operators ordered by precedence level, see [C# operators](index.md).</span></span>

<span data-ttu-id="5d3ea-153">[强制转换表达式](invocation-operator.md#cast-expression)，调用转换运算符，还使用括号。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-153">[Cast expressions](invocation-operator.md#cast-expression), which invoke a conversion operator, also use parentheses.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="5d3ea-154">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="5d3ea-154">Operator overloadability</span></span>

<span data-ttu-id="5d3ea-155">`.` 和 `()` 运算符不能重载。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-155">The `.` and `()` operators cannot be overloaded.</span></span> <span data-ttu-id="5d3ea-156">`[]` 运算符也被视为非可重载运算符。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-156">The `[]` operator is also considered a non-overloadable operator.</span></span> <span data-ttu-id="5d3ea-157">使用[索引器](../../programming-guide/indexers/index.md)以支持对用户定义的类型编制索引。</span><span class="sxs-lookup"><span data-stu-id="5d3ea-157">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5d3ea-158">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5d3ea-158">C# language specification</span></span>

<span data-ttu-id="5d3ea-159">有关更多信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的以下部分：</span><span class="sxs-lookup"><span data-stu-id="5d3ea-159">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="5d3ea-160">成员访问</span><span class="sxs-lookup"><span data-stu-id="5d3ea-160">Member access</span></span>](~/_csharplang/spec/expressions.md#member-access)
- [<span data-ttu-id="5d3ea-161">元素访问</span><span class="sxs-lookup"><span data-stu-id="5d3ea-161">Element access</span></span>](~/_csharplang/spec/expressions.md#element-access)
- [<span data-ttu-id="5d3ea-162">Null 条件运算符</span><span class="sxs-lookup"><span data-stu-id="5d3ea-162">Null-conditional operator</span></span>](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [<span data-ttu-id="5d3ea-163">调用表达式</span><span class="sxs-lookup"><span data-stu-id="5d3ea-163">Invocation expressions</span></span>](~/_csharplang/spec/expressions.md#invocation-expressions)

## <a name="see-also"></a><span data-ttu-id="5d3ea-164">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d3ea-164">See also</span></span>

- [<span data-ttu-id="5d3ea-165">C# 参考</span><span class="sxs-lookup"><span data-stu-id="5d3ea-165">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5d3ea-166">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5d3ea-166">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5d3ea-167">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="5d3ea-167">C# Operators</span></span>](index.md)
- [<span data-ttu-id="5d3ea-168">??（空合运算符）</span><span class="sxs-lookup"><span data-stu-id="5d3ea-168">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)
