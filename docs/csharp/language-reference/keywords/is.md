---
title: is - C# 参考
ms.custom: seodec18
ms.date: 04/09/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: ac1ec7da7da465f4290000ac9c7254e9492c3c81
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "66421814"
---
# <a name="is-c-reference"></a><span data-ttu-id="42bee-102">is（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="42bee-102">is (C# Reference)</span></span>

<span data-ttu-id="42bee-103">检查对象是否与给定类型兼容，或（从 C# 7.0 开始）针对某个模式测试表达式。</span><span class="sxs-lookup"><span data-stu-id="42bee-103">Checks if an object is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span>

## <a name="testing-for-type-compatibility"></a><span data-ttu-id="42bee-104">类型兼容性测试</span><span class="sxs-lookup"><span data-stu-id="42bee-104">Testing for type compatibility</span></span>

<span data-ttu-id="42bee-105">`is` 关键字在运行时评估类型兼容性。</span><span class="sxs-lookup"><span data-stu-id="42bee-105">The `is` keyword evaluates type compatibility at runtime.</span></span> <span data-ttu-id="42bee-106">它确定对象实例或表达式结果是否可转换为指定类型。</span><span class="sxs-lookup"><span data-stu-id="42bee-106">It determines whether an object instance or the result of an expression can be converted to a specified type.</span></span> <span data-ttu-id="42bee-107">语法如下：</span><span class="sxs-lookup"><span data-stu-id="42bee-107">It has the syntax</span></span>

```csharp
   expr is type
```

<span data-ttu-id="42bee-108">其中 *expr* 是计算结果为某个类型的实例的表达式，而 *type* 是 *expr* 结果要转换到的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="42bee-108">where *expr* is an expression that evaluates to an instance of some type, and *type* is the name of the type to which the result of *expr* is to be converted.</span></span> <span data-ttu-id="42bee-109">如果 *expr* 非空，并且通过计算表达式得出的对象可转换为 *type*，则 `is` 语句为 `true`；否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="42bee-109">The `is` statement is `true` if *expr* is non-null and the object that results from evaluating the expression can be converted to *type*; otherwise, it returns `false`.</span></span>

<span data-ttu-id="42bee-110">例如，以下代码确定 `obj` 是否可转换为 `Person` 类型的实例：</span><span class="sxs-lookup"><span data-stu-id="42bee-110">For example, the following code determines if `obj` can be cast to an instance of the `Person` type:</span></span>

[!code-csharp[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]

<span data-ttu-id="42bee-111">如果满足以下条件，则 `is` 语句为 true：</span><span class="sxs-lookup"><span data-stu-id="42bee-111">The `is` statement is true if:</span></span>

- <span data-ttu-id="42bee-112">*expr* 是与 *type* 具有相同类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="42bee-112">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="42bee-113">*expr* 是派生自 *type* 的类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="42bee-113">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="42bee-114">换言之，*expr* 结果可以向上转换为 *type* 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="42bee-114">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="42bee-115">*expr* 具有属于 *type* 的一个基类的编译时类型，*expr* 还具有属于 *type* 或派生自 *type* 的运行时类型。</span><span class="sxs-lookup"><span data-stu-id="42bee-115">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="42bee-116">变量的编译时类型  是其声明中定义的变量类型。</span><span class="sxs-lookup"><span data-stu-id="42bee-116">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="42bee-117">变量的运行时类型  是分配给该变量的实例类型。</span><span class="sxs-lookup"><span data-stu-id="42bee-117">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="42bee-118">*expr* 是实现 *type* 接口的类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="42bee-118">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="42bee-119">下例表明，对于所有这些转换，`is` 表达式的计算结果都为 `true`。</span><span class="sxs-lookup"><span data-stu-id="42bee-119">The following example shows that the `is` expression evaluates to `true` for each of these conversions.</span></span>

[!code-csharp[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]

<span data-ttu-id="42bee-120">如果已知表达式始终为 `true` 或 `false`，则 `is` 关键字会生成编译时警告。</span><span class="sxs-lookup"><span data-stu-id="42bee-120">The `is` keyword generates a compile-time warning if the expression is known to always be either `true` or `false`.</span></span> <span data-ttu-id="42bee-121">它只考虑引用转换、装箱转换和取消装箱转换；不考虑用户定义的转换或由类型的[隐式](implicit.md)和[显式](explicit.md)运算符定义的转换。</span><span class="sxs-lookup"><span data-stu-id="42bee-121">It only considers reference conversions, boxing conversions, and unboxing conversions; it does not consider user-defined conversions or conversions defined by a type's [implicit](implicit.md) and [explicit](explicit.md) operators.</span></span> <span data-ttu-id="42bee-122">下面的示例生成警告，因为转换结果在编译时就已知。</span><span class="sxs-lookup"><span data-stu-id="42bee-122">The following example generates warnings because the result of the conversion is known at compile time.</span></span> <span data-ttu-id="42bee-123">用于从 `int` 转换到 `long` 和 `double` 的 `is` 表达式返回 false，因为这些转换由[隐式](implicit.md)运算符处理。</span><span class="sxs-lookup"><span data-stu-id="42bee-123">The `is` expression for conversions from `int` to `long` and `double` return false, since these conversions are handled by the [implicit](implicit.md) operator.</span></span>

[!code-csharp[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]

<span data-ttu-id="42bee-124">`expr` 不得为匿名方法或 Lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="42bee-124">`expr` cannot be an anonymous method or lambda expression.</span></span> <span data-ttu-id="42bee-125">它可以是其他任何返回值的表达式。</span><span class="sxs-lookup"><span data-stu-id="42bee-125">It can be any other expression that returns a value.</span></span> <span data-ttu-id="42bee-126">下例使用 `is` 来计算方法调用的返回值。</span><span class="sxs-lookup"><span data-stu-id="42bee-126">The following example uses  `is` to evaluate the return value of a method call.</span></span>   
[!code-csharp[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]

<span data-ttu-id="42bee-127">从 C# 7.0 开始，可以使用[类型模式](#type)的模式匹配来编写代码，代码使用 `is` 语句更为简洁。</span><span class="sxs-lookup"><span data-stu-id="42bee-127">Starting with C# 7.0, you can use pattern matching with the [type pattern](#type) to write more concise code that uses the `is` statement.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="42bee-128">利用 `is` 的模式匹配</span><span class="sxs-lookup"><span data-stu-id="42bee-128">Pattern matching with `is`</span></span>

<span data-ttu-id="42bee-129">从 C# 7.0 开始，`is` 和 [switch](../../../csharp/language-reference/keywords/switch.md) 语句支持模式匹配。</span><span class="sxs-lookup"><span data-stu-id="42bee-129">Starting with C# 7.0, the `is` and [switch](../../../csharp/language-reference/keywords/switch.md) statements support pattern matching.</span></span> <span data-ttu-id="42bee-130">`is` 关键字支持以下模式：</span><span class="sxs-lookup"><span data-stu-id="42bee-130">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="42bee-131">[类型模式](#type)，用于测试表达式是否可转换为指定类型，如果可以，则将其转换为该类型的一个变量。</span><span class="sxs-lookup"><span data-stu-id="42bee-131">[Type pattern](#type),  which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="42bee-132">[常量模式](#constant)，用于测试表达式计算结果是否为指定的常数值。</span><span class="sxs-lookup"><span data-stu-id="42bee-132">[Constant pattern](#constant), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="42bee-133">[var 模式](#var)，始终成功的匹配，可将表达式的值绑定到新局部变量。</span><span class="sxs-lookup"><span data-stu-id="42bee-133">[var pattern](#var), a match that always succeeds and binds the value of an expression to a new local variable.</span></span> 

### <a name="a-nametype-type-pattern"></a><span data-ttu-id="42bee-134"><a name="type" />类型模式</span><span class="sxs-lookup"><span data-stu-id="42bee-134"><a name="type" />Type pattern</span></span>

<span data-ttu-id="42bee-135">使用类型模式执行模式匹配时，`is` 会测试表达式是否可转换为指定类型，如果可以，则将其转换为该类型的一个变量。</span><span class="sxs-lookup"><span data-stu-id="42bee-135">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="42bee-136">它是 `is` 语句的直接扩展，可执行简单的类型计算和转换。</span><span class="sxs-lookup"><span data-stu-id="42bee-136">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="42bee-137">`is` 类型模式的一般形式为：</span><span class="sxs-lookup"><span data-stu-id="42bee-137">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname 
```

<span data-ttu-id="42bee-138">其中 *expr* 是计算结果为某个类型的实例的表达式，*type* 是 *expr* 结果要转换到的类型的名称，*varname* 是 *expr* 结果要转换到的对象（如果 `is` 测试为 `true`）。</span><span class="sxs-lookup"><span data-stu-id="42bee-138">where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span> 

<span data-ttu-id="42bee-139">如果 expr  不为 `null` 且以下任意内容为 true，那么 `is` 表达式为 `true`：</span><span class="sxs-lookup"><span data-stu-id="42bee-139">The `is` expression is `true` if *expr* isn't `null`, and any of the following is true:</span></span>

- <span data-ttu-id="42bee-140">*expr* 是与 *type* 具有相同类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="42bee-140">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="42bee-141">*expr* 是派生自 *type* 的类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="42bee-141">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="42bee-142">换言之，*expr* 结果可以向上转换为 *type* 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="42bee-142">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="42bee-143">*expr* 具有属于 *type* 的一个基类的编译时类型，*expr* 还具有属于 *type* 或派生自 *type* 的运行时类型。</span><span class="sxs-lookup"><span data-stu-id="42bee-143">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="42bee-144">变量的编译时类型  是其声明中定义的变量类型。</span><span class="sxs-lookup"><span data-stu-id="42bee-144">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="42bee-145">变量的运行时类型  是分配给该变量的实例类型。</span><span class="sxs-lookup"><span data-stu-id="42bee-145">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="42bee-146">*expr* 是实现 *type* 接口的类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="42bee-146">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="42bee-147">自 C# 7.1 起，expr  可能有泛型类型参数及其约束定义的编译时类型。</span><span class="sxs-lookup"><span data-stu-id="42bee-147">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span> 

<span data-ttu-id="42bee-148">如果 *expr* 为 `true` 且 `is` 与 `if` 语句配合使用，则仅在 `if` 语句内分配 *varname*。</span><span class="sxs-lookup"><span data-stu-id="42bee-148">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned within the `if` statement only.</span></span> <span data-ttu-id="42bee-149">*varname* 的使用范围：从 `is` 表达式到封闭 `if` 语句的块的末尾。</span><span class="sxs-lookup"><span data-stu-id="42bee-149">The scope of *varname* is from the `is` expression to the end of the block enclosing the `if` statement.</span></span> <span data-ttu-id="42bee-150">在任何其他位置使用 *varname* 都会因使用尚未分配的变量而生成编译时错误。</span><span class="sxs-lookup"><span data-stu-id="42bee-150">Using *varname* in any other location generates a compile-time error for use of a variable that has not been assigned.</span></span>

<span data-ttu-id="42bee-151">下列示例使用 `is` 类型模式为类型的 <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> 方法提供实现。</span><span class="sxs-lookup"><span data-stu-id="42bee-151">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="42bee-152">如果没有模式匹配，则可能按以下方式编写此代码。</span><span class="sxs-lookup"><span data-stu-id="42bee-152">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="42bee-153">使用类型模式匹配无需测试转换结果是否为 `null`，从而生成更紧凑易读的代码。</span><span class="sxs-lookup"><span data-stu-id="42bee-153">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="42bee-154">确定值类型的类型时，`is` 类型模式也会生成更紧凑的代码。</span><span class="sxs-lookup"><span data-stu-id="42bee-154">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="42bee-155">下例在显示相应属性的值之前使用 `is` 类型模式来确定对象是 `Person` 还是 `Dog` 实例。</span><span class="sxs-lookup"><span data-stu-id="42bee-155">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span> 

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="42bee-156">对于无模式匹配的等效代码，需要为其单独分配显式转换。</span><span class="sxs-lookup"><span data-stu-id="42bee-156">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="a-nameconstant--constant-pattern"></a><span data-ttu-id="42bee-157"><a name="constant" />常量模式</span><span class="sxs-lookup"><span data-stu-id="42bee-157"><a name="constant" /> Constant pattern</span></span>

<span data-ttu-id="42bee-158">使用常量模式执行模式匹配时，`is` 会测试表达式结果是否等于指定常量。</span><span class="sxs-lookup"><span data-stu-id="42bee-158">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="42bee-159">在 C# 6 和更低版本中，[switch](switch.md) 语句支持常量模式。</span><span class="sxs-lookup"><span data-stu-id="42bee-159">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="42bee-160">自 C# 7.0 起，`is` 语句也支持它。</span><span class="sxs-lookup"><span data-stu-id="42bee-160">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="42bee-161">语法为：</span><span class="sxs-lookup"><span data-stu-id="42bee-161">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="42bee-162">其中 *expr* 是要计算的表达式，*constant* 是要测试的值。</span><span class="sxs-lookup"><span data-stu-id="42bee-162">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="42bee-163">*constant* 可以是以下任何常数表达式：</span><span class="sxs-lookup"><span data-stu-id="42bee-163">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="42bee-164">一个文本值。</span><span class="sxs-lookup"><span data-stu-id="42bee-164">A literal value.</span></span>

- <span data-ttu-id="42bee-165">已声明 `const` 变量的名称。</span><span class="sxs-lookup"><span data-stu-id="42bee-165">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="42bee-166">一个枚举常量。</span><span class="sxs-lookup"><span data-stu-id="42bee-166">An enumeration constant.</span></span>

<span data-ttu-id="42bee-167">常数表达式的计算方式如下：</span><span class="sxs-lookup"><span data-stu-id="42bee-167">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="42bee-168">如果 *expr* 和 *constant* 均为整型类型，则 C# 相等运算符确定表示式是否返回 `true`（即，是否为 `expr == constant`）。</span><span class="sxs-lookup"><span data-stu-id="42bee-168">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="42bee-169">否则，由对静态 [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) 方法的调用来确定表达式的值。</span><span class="sxs-lookup"><span data-stu-id="42bee-169">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="42bee-170">下例同时使用了类型模式和常量模式来测试对象是否为 `Dice` 实例，如果是，则确定骰子的值是否为 6。</span><span class="sxs-lookup"><span data-stu-id="42bee-170">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="42bee-171">可以使用常量模式执行 `null` 检查。</span><span class="sxs-lookup"><span data-stu-id="42bee-171">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="42bee-172">`is` 语句支持 `null` 关键字。</span><span class="sxs-lookup"><span data-stu-id="42bee-172">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="42bee-173">语法为：</span><span class="sxs-lookup"><span data-stu-id="42bee-173">Its syntax is:</span></span>

```csharp 
   expr is null
```

<span data-ttu-id="42bee-174">下面的示例显示 `null` 检查的比较：</span><span class="sxs-lookup"><span data-stu-id="42bee-174">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]
 
### <span data-ttu-id="42bee-175"><a name="var" />var 模式</a></span><span class="sxs-lookup"><span data-stu-id="42bee-175"><a name="var" /> var pattern </a></span></span>

<span data-ttu-id="42bee-176">`var` 模式对于任何类型或值均为 catch-all。</span><span class="sxs-lookup"><span data-stu-id="42bee-176">The `var` pattern is a catch-all for any type or value.</span></span> <span data-ttu-id="42bee-177">expr  值始终分配给与 expr  的编译时类型相同的本地变量。</span><span class="sxs-lookup"><span data-stu-id="42bee-177">The value of *expr* is always assigned to a local variable the same type as the compile time type of *expr*.</span></span> <span data-ttu-id="42bee-178">`is` 表达式的结果始终为 `true`。</span><span class="sxs-lookup"><span data-stu-id="42bee-178">The result of the `is` expression is always `true`.</span></span> <span data-ttu-id="42bee-179">语法为：</span><span class="sxs-lookup"><span data-stu-id="42bee-179">Its syntax is:</span></span>

```csharp 
   expr is var varname
```

<span data-ttu-id="42bee-180">下例使用 var 模式向名为 `obj` 的变量分配表达式。</span><span class="sxs-lookup"><span data-stu-id="42bee-180">The following example uses the var pattern to assign an expression to a variable named `obj`.</span></span> <span data-ttu-id="42bee-181">然后，显示 `obj` 的值和类型。</span><span class="sxs-lookup"><span data-stu-id="42bee-181">It then displays the value and the type of `obj`.</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="42bee-182">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="42bee-182">C# Language Specification</span></span>
  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="42bee-183">请参阅</span><span class="sxs-lookup"><span data-stu-id="42bee-183">See also</span></span>

- [<span data-ttu-id="42bee-184">C# 参考</span><span class="sxs-lookup"><span data-stu-id="42bee-184">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="42bee-185">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="42bee-185">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="42bee-186">typeof</span><span class="sxs-lookup"><span data-stu-id="42bee-186">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)
- [<span data-ttu-id="42bee-187">as</span><span class="sxs-lookup"><span data-stu-id="42bee-187">as</span></span>](../../../csharp/language-reference/keywords/as.md)
