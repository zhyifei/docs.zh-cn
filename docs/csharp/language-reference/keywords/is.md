---
title: is - C# 参考
ms.date: 06/21/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: e64b690482419963a92764b2c97a42dbb231fbfc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398303"
---
# <a name="is-c-reference"></a><span data-ttu-id="4f650-102">is（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="4f650-102">is (C# Reference)</span></span>

<span data-ttu-id="4f650-103">`is` 运算符检查表达式的结果是否与给定类型兼容，或（从 C# 7.0 开始）针对某个模式测试表达式。</span><span class="sxs-lookup"><span data-stu-id="4f650-103">The `is` operator checks if the result of an expression is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span> <span data-ttu-id="4f650-104">有关类型测试 `is` 运算符的信息，请参阅文章[类型测试和强制转换运算符](../operators/type-testing-and-cast.md)的 [is 运算符](../operators/type-testing-and-cast.md#is-operator)部分。</span><span class="sxs-lookup"><span data-stu-id="4f650-104">For information about the type-testing `is` operator see the [is operator](../operators/type-testing-and-cast.md#is-operator) section of the [Type-testing and cast operators](../operators/type-testing-and-cast.md) article.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="4f650-105">利用 `is` 的模式匹配</span><span class="sxs-lookup"><span data-stu-id="4f650-105">Pattern matching with `is`</span></span>

<span data-ttu-id="4f650-106">从 C# 7.0 开始，`is` 和 [switch](switch.md) 语句支持模式匹配。</span><span class="sxs-lookup"><span data-stu-id="4f650-106">Starting with C# 7.0, the `is` and [switch](switch.md) statements support pattern matching.</span></span> <span data-ttu-id="4f650-107">`is` 关键字支持以下模式：</span><span class="sxs-lookup"><span data-stu-id="4f650-107">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="4f650-108">[类型模式](#type-pattern)，用于测试表达式是否可转换为指定类型，如果可以，则将其转换为该类型的一个变量。</span><span class="sxs-lookup"><span data-stu-id="4f650-108">[Type pattern](#type-pattern), which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="4f650-109">[常量模式](#constant-pattern)，用于测试表达式计算结果是否为指定的常数值。</span><span class="sxs-lookup"><span data-stu-id="4f650-109">[Constant pattern](#constant-pattern), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="4f650-110">[var 模式](#var-pattern)，始终成功的匹配，可将表达式的值绑定到新局部变量。</span><span class="sxs-lookup"><span data-stu-id="4f650-110">[var pattern](#var-pattern), a match that always succeeds and binds the value of an expression to a new local variable.</span></span>

### <a name="type-pattern"></a><span data-ttu-id="4f650-111">类型模式</span><span class="sxs-lookup"><span data-stu-id="4f650-111">Type pattern</span></span>

<span data-ttu-id="4f650-112">使用类型模式执行模式匹配时，`is` 会测试表达式是否可转换为指定类型，如果可以，则将其转换为该类型的一个变量。</span><span class="sxs-lookup"><span data-stu-id="4f650-112">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="4f650-113">它是 `is` 语句的直接扩展，可执行简单的类型计算和转换。</span><span class="sxs-lookup"><span data-stu-id="4f650-113">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="4f650-114">`is` 类型模式的一般形式为：</span><span class="sxs-lookup"><span data-stu-id="4f650-114">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname
```

<span data-ttu-id="4f650-115">其中 expr 是计算结果为某个类型的实例的表达式，type 是 expr 结果要转换到的类型的名称，varname 是 expr 结果要转换到的对象（如果 `is` 测试为 `true`）。</span><span class="sxs-lookup"><span data-stu-id="4f650-115">Where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span>

<span data-ttu-id="4f650-116">如果 expr 不为 `null` 且以下任意内容为 true，那么 `is` 表达式为 `true`：</span><span class="sxs-lookup"><span data-stu-id="4f650-116">The `is` expression is `true` if *expr* isn't `null`, and any of the following is true:</span></span>

- <span data-ttu-id="4f650-117">*expr* 是与 *type* 具有相同类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="4f650-117">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="4f650-118">*expr* 是派生自 *type* 的类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="4f650-118">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="4f650-119">换言之，*expr* 结果可以向上转换为 *type* 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="4f650-119">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="4f650-120">*expr* 具有属于 *type* 的一个基类的编译时类型，*expr* 还具有属于 *type* 或派生自 *type* 的运行时类型。</span><span class="sxs-lookup"><span data-stu-id="4f650-120">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="4f650-121">变量的编译时类型是其声明中定义的变量类型。</span><span class="sxs-lookup"><span data-stu-id="4f650-121">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="4f650-122">变量的运行时类型是分配给该变量的实例类型。</span><span class="sxs-lookup"><span data-stu-id="4f650-122">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="4f650-123">*expr* 是实现 *type* 接口的类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="4f650-123">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="4f650-124">自 C# 7.1 起，expr 可能有泛型类型参数及其约束定义的编译时类型。</span><span class="sxs-lookup"><span data-stu-id="4f650-124">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span>

<span data-ttu-id="4f650-125">如果 *expr* 为 `true` 且 `is` 与 `if` 语句配合使用，则仅在 `if` 语句内分配 *varname*。</span><span class="sxs-lookup"><span data-stu-id="4f650-125">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned within the `if` statement only.</span></span> <span data-ttu-id="4f650-126">*varname* 的使用范围：从 `is` 表达式到封闭 `if` 语句的块的末尾。</span><span class="sxs-lookup"><span data-stu-id="4f650-126">The scope of *varname* is from the `is` expression to the end of the block enclosing the `if` statement.</span></span> <span data-ttu-id="4f650-127">在任何其他位置使用 *varname* 都会因使用尚未分配的变量而生成编译时错误。</span><span class="sxs-lookup"><span data-stu-id="4f650-127">Using *varname* in any other location generates a compile-time error for use of a variable that has not been assigned.</span></span>

<span data-ttu-id="4f650-128">下列示例使用 `is` 类型模式为类型的 <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> 方法提供实现。</span><span class="sxs-lookup"><span data-stu-id="4f650-128">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="4f650-129">如果没有模式匹配，则可能按以下方式编写此代码。</span><span class="sxs-lookup"><span data-stu-id="4f650-129">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="4f650-130">使用类型模式匹配无需测试转换结果是否为 `null`，从而生成更紧凑易读的代码。</span><span class="sxs-lookup"><span data-stu-id="4f650-130">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="4f650-131">确定值类型的类型时，`is` 类型模式也会生成更紧凑的代码。</span><span class="sxs-lookup"><span data-stu-id="4f650-131">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="4f650-132">下例在显示相应属性的值之前使用 `is` 类型模式来确定对象是 `Person` 还是 `Dog` 实例。</span><span class="sxs-lookup"><span data-stu-id="4f650-132">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span>

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="4f650-133">对于无模式匹配的等效代码，需要为其单独分配显式转换。</span><span class="sxs-lookup"><span data-stu-id="4f650-133">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="constant-pattern"></a><span data-ttu-id="4f650-134">常量模式</span><span class="sxs-lookup"><span data-stu-id="4f650-134">Constant pattern</span></span>

<span data-ttu-id="4f650-135">使用常量模式执行模式匹配时，`is` 会测试表达式结果是否等于指定常量。</span><span class="sxs-lookup"><span data-stu-id="4f650-135">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="4f650-136">在 C# 6 和更低版本中，[switch](switch.md) 语句支持常量模式。</span><span class="sxs-lookup"><span data-stu-id="4f650-136">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="4f650-137">自 C# 7.0 起，`is` 语句也支持它。</span><span class="sxs-lookup"><span data-stu-id="4f650-137">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="4f650-138">语法为：</span><span class="sxs-lookup"><span data-stu-id="4f650-138">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="4f650-139">其中 *expr* 是要计算的表达式，*constant* 是要测试的值。</span><span class="sxs-lookup"><span data-stu-id="4f650-139">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="4f650-140">*constant* 可以是以下任何常数表达式：</span><span class="sxs-lookup"><span data-stu-id="4f650-140">*constant* can be any of the following constant expressions:</span></span>

- <span data-ttu-id="4f650-141">一个文本值。</span><span class="sxs-lookup"><span data-stu-id="4f650-141">A literal value.</span></span>

- <span data-ttu-id="4f650-142">已声明 `const` 变量的名称。</span><span class="sxs-lookup"><span data-stu-id="4f650-142">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="4f650-143">一个枚举常量。</span><span class="sxs-lookup"><span data-stu-id="4f650-143">An enumeration constant.</span></span>

<span data-ttu-id="4f650-144">常数表达式的计算方式如下：</span><span class="sxs-lookup"><span data-stu-id="4f650-144">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="4f650-145">如果 *expr* 和 *constant* 均为整型类型，则 C# 相等运算符确定表示式是否返回 `true`（即，是否为 `expr == constant`）。</span><span class="sxs-lookup"><span data-stu-id="4f650-145">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="4f650-146">否则，由对静态 [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) 方法的调用来确定表达式的值。</span><span class="sxs-lookup"><span data-stu-id="4f650-146">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="4f650-147">下例同时使用了类型模式和常量模式来测试对象是否为 `Dice` 实例，如果是，则确定骰子的值是否为 6。</span><span class="sxs-lookup"><span data-stu-id="4f650-147">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="4f650-148">可以使用常量模式执行 `null` 检查。</span><span class="sxs-lookup"><span data-stu-id="4f650-148">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="4f650-149">`is` 语句支持 `null` 关键字。</span><span class="sxs-lookup"><span data-stu-id="4f650-149">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="4f650-150">语法为：</span><span class="sxs-lookup"><span data-stu-id="4f650-150">Its syntax is:</span></span>

```csharp
   expr is null
```

<span data-ttu-id="4f650-151">下面的示例显示 `null` 检查的比较：</span><span class="sxs-lookup"><span data-stu-id="4f650-151">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]

### <a name="var-pattern"></a><span data-ttu-id="4f650-152">var 模式</span><span class="sxs-lookup"><span data-stu-id="4f650-152">var pattern</span></span>

<span data-ttu-id="4f650-153">具有 `var` 模式的模式匹配始终成功。</span><span class="sxs-lookup"><span data-stu-id="4f650-153">A pattern match with the `var` pattern always succeeds.</span></span> <span data-ttu-id="4f650-154">语法为：</span><span class="sxs-lookup"><span data-stu-id="4f650-154">Its syntax is:</span></span>

```csharp
   expr is var varname
```

<span data-ttu-id="4f650-155">其中，expr 的值始终分配给名为 varname 的局部变量。</span><span class="sxs-lookup"><span data-stu-id="4f650-155">Where the value of *expr* is always assigned to a local variable named *varname*.</span></span> <span data-ttu-id="4f650-156">varname 变量的类型与 expr 的编译时类型相同。</span><span class="sxs-lookup"><span data-stu-id="4f650-156">*varname* is a variable of the same type as the compile-time type of *expr*.</span></span>

<span data-ttu-id="4f650-157">如果 expr 的计算结果为 `null`，则 `is` 表达式将生成 `true` 并将 `null` 分配给 varname。</span><span class="sxs-lookup"><span data-stu-id="4f650-157">If *expr* evaluates to `null`, the `is` expression produces `true` and assigns `null` to *varname*.</span></span> <span data-ttu-id="4f650-158">var 模式是 `is` 对 `null` 值生成 `true` 的少数用途之一。</span><span class="sxs-lookup"><span data-stu-id="4f650-158">The var pattern is one of the few uses of `is` that produces `true` for a `null` value.</span></span>

<span data-ttu-id="4f650-159">可以使用 `var` 模式在布尔表达式中创建临时变量，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="4f650-159">You can use the `var` pattern to create a temporary variable within a Boolean expression, as the following example shows:</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

<span data-ttu-id="4f650-160">在前面的示例中，临时变量用于存储代价高昂的操作的结果。</span><span class="sxs-lookup"><span data-stu-id="4f650-160">In the preceding example, the temporary variable is used to store the result of an expensive operation.</span></span> <span data-ttu-id="4f650-161">然后，可以多次使用该变量。</span><span class="sxs-lookup"><span data-stu-id="4f650-161">The variable can then be used multiple times.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4f650-162">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="4f650-162">C# language specification</span></span>
  
<span data-ttu-id="4f650-163">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的 [is 运算符](~/_csharplang/spec/expressions.md#the-is-operator)部分以及下面的 C# 语言建议：</span><span class="sxs-lookup"><span data-stu-id="4f650-163">For more information, see [The is operator](~/_csharplang/spec/expressions.md#the-is-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the following C# language proposals:</span></span>

- [<span data-ttu-id="4f650-164">模式匹配</span><span class="sxs-lookup"><span data-stu-id="4f650-164">Pattern matching</span></span>](~/_csharplang/proposals/csharp-7.0/pattern-matching.md)
- [<span data-ttu-id="4f650-165">使用泛型的模式匹配</span><span class="sxs-lookup"><span data-stu-id="4f650-165">Pattern matching with generics</span></span>](~/_csharplang/proposals/csharp-7.1/generics-pattern-match.md)
  
## <a name="see-also"></a><span data-ttu-id="4f650-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f650-166">See also</span></span>

- [<span data-ttu-id="4f650-167">C# 参考</span><span class="sxs-lookup"><span data-stu-id="4f650-167">C# reference</span></span>](../index.md)
- [<span data-ttu-id="4f650-168">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="4f650-168">C# keywords</span></span>](index.md)
- [<span data-ttu-id="4f650-169">类型测试和强制转换运算符</span><span class="sxs-lookup"><span data-stu-id="4f650-169">Type-testing and cast operators</span></span>](../operators/type-testing-and-cast.md)
