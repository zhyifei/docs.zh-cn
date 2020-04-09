---
title: 成员访问运算符和表达式 - C# 参考
description: 了解可用于访问类型成员的 C# 运算符。
ms.date: 03/31/2020
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
- ^_CSharpKeyword
- .._CSharpKeyword
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
- ^ operator [C#]
- index from end operator [C#]
- hat operator [C#]
- .. operator [C#]
- range operator [C#]
ms.openlocfilehash: a132e527deadcffb4826c1965987fc09da470a09
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635300"
---
# <a name="member-access-operators-and-expressions-c-reference"></a><span data-ttu-id="c9378-103">成员访问运算符和表达式（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c9378-103">Member access operators and expressions (C# reference)</span></span>

<span data-ttu-id="c9378-104">访问类型成员时，可以使用以下运算符和表达式：</span><span class="sxs-lookup"><span data-stu-id="c9378-104">You can use the following operators and expressions when you access a type member:</span></span>

- <span data-ttu-id="c9378-105">[`.`（成员访问）](#member-access-expression-)：用于访问命名空间或类型的成员</span><span class="sxs-lookup"><span data-stu-id="c9378-105">[`.` (member access)](#member-access-expression-): to access a member of a namespace or a type</span></span>
- <span data-ttu-id="c9378-106">[`[]`（数组元素或索引器访问）](#indexer-operator-)：用于访问数组元素或类型索引器</span><span class="sxs-lookup"><span data-stu-id="c9378-106">[`[]` (array element or indexer access)](#indexer-operator-): to access an array element or a type indexer</span></span>
- <span data-ttu-id="c9378-107">[`?.` 和 `?[]`（null 条件运算符）](#null-conditional-operators--and-)：仅当操作数为非 null 时才用于执行成员或元素访问运算</span><span class="sxs-lookup"><span data-stu-id="c9378-107">[`?.` and `?[]` (null-conditional operators)](#null-conditional-operators--and-): to perform a member or element access operation only if an operand is non-null</span></span>
- <span data-ttu-id="c9378-108">[`()`（调用）](#invocation-expression-)：用于调用被访问的方法或调用委托</span><span class="sxs-lookup"><span data-stu-id="c9378-108">[`()` (invocation)](#invocation-expression-): to call an accessed method or invoke a delegate</span></span>
- <span data-ttu-id="c9378-109">[`^`（从末尾开始索引）](#index-from-end-operator-)：指示元素位置来自序列的末尾</span><span class="sxs-lookup"><span data-stu-id="c9378-109">[`^` (index from end)](#index-from-end-operator-): to indicate that the element position is from the end of a sequence</span></span>
- <span data-ttu-id="c9378-110">[`..`（范围）](#range-operator-)：指定可用于获取一系列序列元素的索引范围</span><span class="sxs-lookup"><span data-stu-id="c9378-110">[`..` (range)](#range-operator-): to specify a range of indices that you can use to obtain a range of sequence elements</span></span>

## <a name="member-access-expression-"></a><span data-ttu-id="c9378-111">成员访问表达式。</span><span class="sxs-lookup"><span data-stu-id="c9378-111">Member access expression .</span></span>

<span data-ttu-id="c9378-112">可以使用 `.` 标记来访问命名空间或类型的成员，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="c9378-112">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="c9378-113">使用 `.` 访问命名空间内的嵌套命名空间，如以下 [`using` directive](../keywords/using-directive.md) 的示例所示：</span><span class="sxs-lookup"><span data-stu-id="c9378-113">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](snippets/MemberAccessOperators.cs#NestedNamespace)]

- <span data-ttu-id="c9378-114">使用 `.` 构成限定名称  以访问命名空间中的类型，如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="c9378-114">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](snippets/MemberAccessOperators.cs#QualifiedName)]

  <span data-ttu-id="c9378-115">使用 [`using` 指令](../keywords/using-directive.md)来使用可选的限定名称。</span><span class="sxs-lookup"><span data-stu-id="c9378-115">Use a [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="c9378-116">使用 `.` 访问[类型成员](../../programming-guide/classes-and-structs/index.md#members)（静态和非静态），如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="c9378-116">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](snippets/MemberAccessOperators.cs#TypeMemberAccess)]

<span data-ttu-id="c9378-117">还可以使用 `.` 访问[扩展方法](../../programming-guide/classes-and-structs/extension-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="c9378-117">You can also use `.` to access an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="indexer-operator-"></a><span data-ttu-id="c9378-118">索引器运算符 []</span><span class="sxs-lookup"><span data-stu-id="c9378-118">Indexer operator []</span></span>

<span data-ttu-id="c9378-119">方括号 `[]` 通常用于数组、索引器或指针元素访问。</span><span class="sxs-lookup"><span data-stu-id="c9378-119">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

### <a name="array-access"></a><span data-ttu-id="c9378-120">数组访问</span><span class="sxs-lookup"><span data-stu-id="c9378-120">Array access</span></span>

<span data-ttu-id="c9378-121">下面的示例演示如何访问数组元素：</span><span class="sxs-lookup"><span data-stu-id="c9378-121">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](snippets/MemberAccessOperators.cs#Arrays)]

<span data-ttu-id="c9378-122">如果数组索引超出数组相应维度的边界，将引发 <xref:System.IndexOutOfRangeException>。</span><span class="sxs-lookup"><span data-stu-id="c9378-122">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="c9378-123">如上述示例所示，在声明数组类型或实例化数组实例时，还会使用方括号。</span><span class="sxs-lookup"><span data-stu-id="c9378-123">As the preceding example shows, you also use square brackets when you declare an array type or instantiate an array instance.</span></span>

<span data-ttu-id="c9378-124">有关数组的详细信息，请参阅[数组](../../programming-guide/arrays/index.md)。</span><span class="sxs-lookup"><span data-stu-id="c9378-124">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

### <a name="indexer-access"></a><span data-ttu-id="c9378-125">索引器访问</span><span class="sxs-lookup"><span data-stu-id="c9378-125">Indexer access</span></span>

<span data-ttu-id="c9378-126">下面的示例使用 .NET <xref:System.Collections.Generic.Dictionary%602> 类型来演示索引器访问：</span><span class="sxs-lookup"><span data-stu-id="c9378-126">The following example uses the .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](snippets/MemberAccessOperators.cs#Indexers)]

<span data-ttu-id="c9378-127">使用索引器，可通过类似于编制数组索引的方式对用户定义类型的实例编制索引。</span><span class="sxs-lookup"><span data-stu-id="c9378-127">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="c9378-128">与必须是整数的数组索引不同，可以将索引器参数声明为任何类型。</span><span class="sxs-lookup"><span data-stu-id="c9378-128">Unlike array indices, which must be integer, the indexer parameters can be declared to be of any type.</span></span>

<span data-ttu-id="c9378-129">有关索引器的详细信息，请参阅[索引器](../../programming-guide/indexers/index.md)。</span><span class="sxs-lookup"><span data-stu-id="c9378-129">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="c9378-130">[] 的其他用法</span><span class="sxs-lookup"><span data-stu-id="c9378-130">Other usages of []</span></span>

<span data-ttu-id="c9378-131">要了解指针元素访问，请参阅[与指针相关的运算符](pointer-related-operators.md)一文的[指针元素访问运算符 []](pointer-related-operators.md#pointer-element-access-operator-) 部分。</span><span class="sxs-lookup"><span data-stu-id="c9378-131">For information about pointer element access, see the [Pointer element access operator []](pointer-related-operators.md#pointer-element-access-operator-) section of the [Pointer related operators](pointer-related-operators.md) article.</span></span>

<span data-ttu-id="c9378-132">方括号还用于指定[属性](../../programming-guide/concepts/attributes/index.md)：</span><span class="sxs-lookup"><span data-stu-id="c9378-132">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a><span data-ttu-id="c9378-133">Null 条件运算符 ?.</span><span class="sxs-lookup"><span data-stu-id="c9378-133">Null-conditional operators ?.</span></span> <span data-ttu-id="c9378-134">和 ?[]</span><span class="sxs-lookup"><span data-stu-id="c9378-134">and ?[]</span></span>

<span data-ttu-id="c9378-135">Null 条件运算符在 C# 6 及更高版本中可用，仅当操作数的计算结果为非 null 时，null 条件运算符才会将[成员访问](#member-access-expression-) `?.` 或[元素访问](#indexer-operator-) `?[]` 运算应用于其操作数；否则，将返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="c9378-135">Available in C# 6 and later, a null-conditional operator applies a [member access](#member-access-expression-), `?.`, or [element access](#indexer-operator-), `?[]`, operation to its operand only if that operand evaluates to non-null; otherwise, it returns `null`.</span></span> <span data-ttu-id="c9378-136">即：</span><span class="sxs-lookup"><span data-stu-id="c9378-136">That is,</span></span>

- <span data-ttu-id="c9378-137">如果 `a` 的计算结果为 `null`，则 `a?.x` 或 `a?[x]` 的结果为 `null`。</span><span class="sxs-lookup"><span data-stu-id="c9378-137">If `a` evaluates to `null`, the result of `a?.x` or `a?[x]` is `null`.</span></span>
- <span data-ttu-id="c9378-138">如果 `a` 的计算结果为非 null，则 `a?.x` 或 `a?[x]` 的结果将分别与 `a.x` 或 `a[x]` 的结果相同。</span><span class="sxs-lookup"><span data-stu-id="c9378-138">If `a` evaluates to non-null, the result of `a?.x` or `a?[x]` is the same as the result of `a.x` or `a[x]`, respectively.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c9378-139">如果 `a.x` 或 `a[x]` 引发异常，则 `a?.x` 或 `a?[x]` 将对非 null `a` 引发相同的异常。</span><span class="sxs-lookup"><span data-stu-id="c9378-139">If `a.x` or `a[x]` throws an exception, `a?.x` or `a?[x]` would throw the same exception for non-null `a`.</span></span> <span data-ttu-id="c9378-140">例如，如果 `a` 为非 null 数组实例且 `x` 在 `a`的边界之外，则 `a?[x]` 将引发 <xref:System.IndexOutOfRangeException>。</span><span class="sxs-lookup"><span data-stu-id="c9378-140">For example, if `a` is a non-null array instance and `x` is outside the bounds of `a`, `a?[x]` would throw an <xref:System.IndexOutOfRangeException>.</span></span>

<span data-ttu-id="c9378-141">NULL 条件运算符采用最小化求值策略。</span><span class="sxs-lookup"><span data-stu-id="c9378-141">The null-conditional operators are short-circuiting.</span></span> <span data-ttu-id="c9378-142">也就是说，如果条件成员或元素访问运算链中的一个运算返回 `null`，则链的其余部分不会执行。</span><span class="sxs-lookup"><span data-stu-id="c9378-142">That is, if one operation in a chain of conditional member or element access operations returns `null`, the rest of the chain doesn't execute.</span></span> <span data-ttu-id="c9378-143">在以下示例中，如果 `A` 的计算结果为 `null`，则不会计算 `B`；如果 `A` 或 `B` 的计算结果为 `null`，则不会计算 `C`：</span><span class="sxs-lookup"><span data-stu-id="c9378-143">In the following example, `B` is not evaluated if `A` evaluates to `null` and `C` is not evaluated if `A` or `B` evaluates to `null`:</span></span>

```csharp
A?.B?.Do(C);
A?.B?[C];
```

<span data-ttu-id="c9378-144">以下示例演示了 `?.` 和 `?[]` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="c9378-144">The following example demonstrates the usage of the `?.` and `?[]` operators:</span></span>

[!code-csharp-interactive[null-conditional operators](snippets/MemberAccessOperators.cs#NullConditional)]

<span data-ttu-id="c9378-145">前面的示例还使用 [Null 合并运算符 `??`](null-coalescing-operator.md) 来指定替代表达式，以便在 null 条件运算的结果为 `null` 时用于计算。</span><span class="sxs-lookup"><span data-stu-id="c9378-145">The preceding example also uses the [null-coalescing operator `??`](null-coalescing-operator.md) to specify an alternative expression to evaluate in case the result of a null-conditional operation is `null`.</span></span>

<span data-ttu-id="c9378-146">如果 `a.x` 或 `a[x]` 是不可为 null 的值类型 `T`，则 `a?.x` 或 `a?[x]` 属于对应的[可为 null 的值类型](../builtin-types/nullable-value-types.md) `T?`。</span><span class="sxs-lookup"><span data-stu-id="c9378-146">If `a.x` or `a[x]` is of a non-nullable value type `T`, `a?.x` or `a?[x]` is of the corresponding [nullable value type](../builtin-types/nullable-value-types.md) `T?`.</span></span> <span data-ttu-id="c9378-147">如果需要 `T` 类型的表达式，请将 Null 合并操作符 `??` 应用于 null 条件表达式，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="c9378-147">If you need an expression of type `T`, apply the null-coalescing operator `??` to a null-conditional expression, as the following example shows:</span></span>

[!code-csharp-interactive[null-conditional with null-coalescing](snippets/MemberAccessOperators.cs#NullConditionalWithNullCoalescing)]

<span data-ttu-id="c9378-148">在前面的示例中，如果不使用 `??` 运算符，则在 `numbers` 为 `null` 时，`numbers?.Length < 2` 的计算结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="c9378-148">In the preceding example, if you don't use the `??` operator, `numbers?.Length < 2` evaluates to `false` when `numbers` is `null`.</span></span>

<span data-ttu-id="c9378-149">Null 条件成员访问运算符 `?.` 也称为 Elvis 运算符。</span><span class="sxs-lookup"><span data-stu-id="c9378-149">The null-conditional member access operator `?.` is also known as the Elvis operator.</span></span>

### <a name="thread-safe-delegate-invocation"></a><span data-ttu-id="c9378-150">线程安全的委托调用</span><span class="sxs-lookup"><span data-stu-id="c9378-150">Thread-safe delegate invocation</span></span>

<span data-ttu-id="c9378-151">使用 `?.` 运算符来检查委托是否非 null 并以线程安全的方式调用它（例如，[引发事件](../../../standard/events/how-to-raise-and-consume-events.md)时），如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="c9378-151">Use the `?.` operator to check if a delegate is non-null and invoke it in a thread-safe way (for example, when you [raise an event](../../../standard/events/how-to-raise-and-consume-events.md)), as the following code shows:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="c9378-152">该代码等同于将在 C# 5 或更低版本中使用的以下代码：</span><span class="sxs-lookup"><span data-stu-id="c9378-152">That code is equivalent to the following code that you would use in C# 5 or earlier:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

## <a name="invocation-expression-"></a><span data-ttu-id="c9378-153">调用表达式 ()</span><span class="sxs-lookup"><span data-stu-id="c9378-153">Invocation expression ()</span></span>

<span data-ttu-id="c9378-154">使用括号 `()` 调用[方法](../../programming-guide/classes-and-structs/methods.md)或调用[委托](../../programming-guide/delegates/index.md)。</span><span class="sxs-lookup"><span data-stu-id="c9378-154">Use parentheses, `()`, to call a [method](../../programming-guide/classes-and-structs/methods.md) or invoke a [delegate](../../programming-guide/delegates/index.md).</span></span>

<span data-ttu-id="c9378-155">以下示例演示如何在使用或不使用参数的情况下调用方法，以及调用委托：</span><span class="sxs-lookup"><span data-stu-id="c9378-155">The following example demonstrates how to call a method, with or without arguments, and invoke a delegate:</span></span>

[!code-csharp-interactive[invocation with ()](snippets/MemberAccessOperators.cs#Invocation)]

<span data-ttu-id="c9378-156">在调用带 [`new`](new-operator.md) 运算符的[构造函数](../../programming-guide/classes-and-structs/constructors.md)时，还可以使用括号。</span><span class="sxs-lookup"><span data-stu-id="c9378-156">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with the [`new`](new-operator.md) operator.</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="c9378-157">() 的其他用法</span><span class="sxs-lookup"><span data-stu-id="c9378-157">Other usages of ()</span></span>

<span data-ttu-id="c9378-158">此外可以使用括号来调整表达式中计算操作的顺序。</span><span class="sxs-lookup"><span data-stu-id="c9378-158">You also use parentheses to adjust the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="c9378-159">有关详细信息，请参阅 [C# 运算符](index.md)。</span><span class="sxs-lookup"><span data-stu-id="c9378-159">For more information, see [C# operators](index.md).</span></span>

<span data-ttu-id="c9378-160">[强制转换表达式](type-testing-and-cast.md#cast-operator-)，其执行显式类型转换，也可以使用括号。</span><span class="sxs-lookup"><span data-stu-id="c9378-160">[Cast expressions](type-testing-and-cast.md#cast-operator-), which perform explicit type conversions, also use parentheses.</span></span>

## <a name="index-from-end-operator-"></a><span data-ttu-id="c9378-161">从末尾运算符 ^ 开始索引</span><span class="sxs-lookup"><span data-stu-id="c9378-161">Index from end operator ^</span></span>

<span data-ttu-id="c9378-162">`^` 运算符在 C# 8.0 和更高版本中提供，指示序列末尾的元素位置。</span><span class="sxs-lookup"><span data-stu-id="c9378-162">Available in C# 8.0 and later, the `^` operator indicates the element position from the end of a sequence.</span></span> <span data-ttu-id="c9378-163">对于长度为 `length` 的序列，`^n` 指向与序列开头偏移 `length - n` 的元素。</span><span class="sxs-lookup"><span data-stu-id="c9378-163">For a sequence of length `length`, `^n` points to the element with offset `length - n` from the start of a sequence.</span></span> <span data-ttu-id="c9378-164">例如，`^1` 指向序列的最后一个元素，`^length` 指向序列的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="c9378-164">For example, `^1` points to the last element of a sequence and `^length` points to the first element of a sequence.</span></span>

[!code-csharp[index from end](snippets/MemberAccessOperators.cs#IndexFromEnd)]

<span data-ttu-id="c9378-165">如前面的示例所示，表达式 `^e` 属于 <xref:System.Index?displayProperty=nameWithType> 类型。</span><span class="sxs-lookup"><span data-stu-id="c9378-165">As the preceding example shows, expression `^e` is of the <xref:System.Index?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="c9378-166">在表达式 `^e` 中，`e` 的结果必须隐式转换为 `int`。</span><span class="sxs-lookup"><span data-stu-id="c9378-166">In expression `^e`, the result of `e` must be implicitly convertible to `int`.</span></span>

<span data-ttu-id="c9378-167">还可以将 `^` 运算符与[范围运算符](#range-operator-)一起使用以创建一个索引范围。</span><span class="sxs-lookup"><span data-stu-id="c9378-167">You also can use the `^` operator with the [range operator](#range-operator-) to create a range of indices.</span></span> <span data-ttu-id="c9378-168">有关详细信息，请参阅[索引和范围](../../tutorials/ranges-indexes.md)。</span><span class="sxs-lookup"><span data-stu-id="c9378-168">For more information, see [Indices and ranges](../../tutorials/ranges-indexes.md).</span></span>

## <a name="range-operator-"></a><span data-ttu-id="c9378-169">范围运算符 .</span><span class="sxs-lookup"><span data-stu-id="c9378-169">Range operator ..</span></span>

<span data-ttu-id="c9378-170">`..` 运算符在 C# 8.0 和更高版本中提供，指定索引范围的开头和末尾作为其操作数。</span><span class="sxs-lookup"><span data-stu-id="c9378-170">Available in C# 8.0 and later, the `..` operator specifies the start and end of a range of indices as its operands.</span></span> <span data-ttu-id="c9378-171">左侧操作数是范围的包含性  开头。</span><span class="sxs-lookup"><span data-stu-id="c9378-171">The left-hand operand is an *inclusive* start of a range.</span></span> <span data-ttu-id="c9378-172">右侧操作数是范围的包含性  末尾。</span><span class="sxs-lookup"><span data-stu-id="c9378-172">The right-hand operand is an *exclusive* end of a range.</span></span> <span data-ttu-id="c9378-173">任一操作数都可以是序列开头或末尾的索引，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="c9378-173">Either of operands can be an index from the start or from the end of a sequence, as the following example shows:</span></span>

[!code-csharp[range examples](snippets/MemberAccessOperators.cs#Ranges)]

<span data-ttu-id="c9378-174">如前面的示例所示，表达式 `a..b` 属于 <xref:System.Range?displayProperty=nameWithType> 类型。</span><span class="sxs-lookup"><span data-stu-id="c9378-174">As the preceding example shows, expression `a..b` is of the <xref:System.Range?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="c9378-175">在表达式 `a..b` 中，`a` 和 `b` 的结果必须隐式转换为 `int` 或 <xref:System.Index>。</span><span class="sxs-lookup"><span data-stu-id="c9378-175">In expression `a..b`, the results of `a` and `b` must be implicitly convertible to `int` or <xref:System.Index>.</span></span>

<span data-ttu-id="c9378-176">可以省略 `..` 运算符的任何操作数来获取无限制范围：</span><span class="sxs-lookup"><span data-stu-id="c9378-176">You can omit any of the operands of the `..` operator to obtain an open-ended range:</span></span>

- <span data-ttu-id="c9378-177">`a..` 等效于 `a..^0`</span><span class="sxs-lookup"><span data-stu-id="c9378-177">`a..` is equivalent to `a..^0`</span></span>
- <span data-ttu-id="c9378-178">`..b` 等效于 `0..b`</span><span class="sxs-lookup"><span data-stu-id="c9378-178">`..b` is equivalent to `0..b`</span></span>
- <span data-ttu-id="c9378-179">`..` 等效于 `0..^0`</span><span class="sxs-lookup"><span data-stu-id="c9378-179">`..` is equivalent to `0..^0`</span></span>

[!code-csharp[ranges with omitted operands](snippets/MemberAccessOperators.cs#RangesOptional)]

<span data-ttu-id="c9378-180">有关详细信息，请参阅[索引和范围](../../tutorials/ranges-indexes.md)。</span><span class="sxs-lookup"><span data-stu-id="c9378-180">For more information, see [Indices and ranges](../../tutorials/ranges-indexes.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="c9378-181">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="c9378-181">Operator overloadability</span></span>

<span data-ttu-id="c9378-182">`.`、`()`、`^` 和 `..` 运算符无法进行重载。</span><span class="sxs-lookup"><span data-stu-id="c9378-182">The `.`, `()`, `^`, and `..` operators cannot be overloaded.</span></span> <span data-ttu-id="c9378-183">`[]` 运算符也被视为非可重载运算符。</span><span class="sxs-lookup"><span data-stu-id="c9378-183">The `[]` operator is also considered a non-overloadable operator.</span></span> <span data-ttu-id="c9378-184">使用[索引器](../../programming-guide/indexers/index.md)以支持对用户定义的类型编制索引。</span><span class="sxs-lookup"><span data-stu-id="c9378-184">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c9378-185">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="c9378-185">C# language specification</span></span>

<span data-ttu-id="c9378-186">有关更多信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的以下部分：</span><span class="sxs-lookup"><span data-stu-id="c9378-186">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="c9378-187">成员访问</span><span class="sxs-lookup"><span data-stu-id="c9378-187">Member access</span></span>](~/_csharplang/spec/expressions.md#member-access)
- [<span data-ttu-id="c9378-188">元素访问</span><span class="sxs-lookup"><span data-stu-id="c9378-188">Element access</span></span>](~/_csharplang/spec/expressions.md#element-access)
- [<span data-ttu-id="c9378-189">Null 条件运算符</span><span class="sxs-lookup"><span data-stu-id="c9378-189">Null-conditional operator</span></span>](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [<span data-ttu-id="c9378-190">调用表达式</span><span class="sxs-lookup"><span data-stu-id="c9378-190">Invocation expressions</span></span>](~/_csharplang/spec/expressions.md#invocation-expressions)

<span data-ttu-id="c9378-191">有关索引和范围的详细信息，请参阅[功能建议说明](~/_csharplang/proposals/csharp-8.0/ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="c9378-191">For more information about indices and ranges, see the [feature proposal note](~/_csharplang/proposals/csharp-8.0/ranges.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c9378-192">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9378-192">See also</span></span>

- [<span data-ttu-id="c9378-193">C# 参考</span><span class="sxs-lookup"><span data-stu-id="c9378-193">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c9378-194">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="c9378-194">C# operators</span></span>](index.md)
- [<span data-ttu-id="c9378-195">??（空合运算符）</span><span class="sxs-lookup"><span data-stu-id="c9378-195">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="c9378-196">:: 运算符</span><span class="sxs-lookup"><span data-stu-id="c9378-196">:: operator</span></span>](namespace-alias-qualifier.md)
