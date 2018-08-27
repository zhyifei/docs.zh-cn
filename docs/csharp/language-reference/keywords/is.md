---
title: is（C# 参考）
ms.date: 02/17/2017
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: 974e0c3ab29da582e7b22c909650a61d179ec3f7
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2018
ms.locfileid: "42931161"
---
# <a name="is-c-reference"></a><span data-ttu-id="903a9-102">is（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="903a9-102">is (C# Reference)</span></span> #

<span data-ttu-id="903a9-103">检查对象是否与给定类型兼容，或（从 C# 7.0 开始）针对某个模式测试表达式。</span><span class="sxs-lookup"><span data-stu-id="903a9-103">Checks if an object is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span>

## <a name="testing-for-type-compatibility"></a><span data-ttu-id="903a9-104">类型兼容性测试</span><span class="sxs-lookup"><span data-stu-id="903a9-104">Testing for type compatibility</span></span> ##

<span data-ttu-id="903a9-105">`is` 关键字在运行时评估类型兼容性。</span><span class="sxs-lookup"><span data-stu-id="903a9-105">The `is` keyword evaluates type compatibility at runtime.</span></span> <span data-ttu-id="903a9-106">它确定对象实例或表达式结果是否可转换为指定类型。</span><span class="sxs-lookup"><span data-stu-id="903a9-106">It determines whether an object instance or the result of an expression can be converted to a specified type.</span></span> <span data-ttu-id="903a9-107">语法如下：</span><span class="sxs-lookup"><span data-stu-id="903a9-107">It has the syntax</span></span>

```csharp
   expr is type
```

<span data-ttu-id="903a9-108">其中 *expr* 是计算结果为某个类型的实例的表达式，而 *type* 是 *expr* 结果要转换到的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="903a9-108">where *expr* is an expression that evaluates to an instance of some type, and *type* is the name of the type to which the result of *expr* is to be converted.</span></span> <span data-ttu-id="903a9-109">如果 *expr* 非空，并且通过计算表达式得出的对象可转换为 *type*，则 `is` 语句为 `true`；否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="903a9-109">The `is` statement is `true` if *expr* is non-null and the object that results from evaluating the expression can be converted to *type*; otherwise, it returns `false`.</span></span>

<span data-ttu-id="903a9-110">例如，以下代码确定 `obj` 是否可转换为 `Person` 类型的实例：</span><span class="sxs-lookup"><span data-stu-id="903a9-110">For example, the following code determines if `obj` can be cast to an instance of the `Person` type:</span></span>

[!code-csharp[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]

<span data-ttu-id="903a9-111">如果满足以下条件，则 `is` 语句为 true：</span><span class="sxs-lookup"><span data-stu-id="903a9-111">The `is` statement is true if:</span></span>

- <span data-ttu-id="903a9-112">*expr* 是与 *type* 具有相同类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="903a9-112">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="903a9-113">*expr* 是派生自 *type* 的类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="903a9-113">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="903a9-114">换言之，*expr* 结果可以向上转换为 *type* 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="903a9-114">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="903a9-115">*expr* 具有属于 *type* 的一个基类的编译时类型，*expr* 还具有属于 *type* 或派生自 *type* 的运行时类型。</span><span class="sxs-lookup"><span data-stu-id="903a9-115">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="903a9-116">变量的编译时类型是其声明中定义的变量类型。</span><span class="sxs-lookup"><span data-stu-id="903a9-116">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="903a9-117">变量的运行时类型是分配给该变量的实例类型。</span><span class="sxs-lookup"><span data-stu-id="903a9-117">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="903a9-118">*expr* 是实现 *type* 接口的类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="903a9-118">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="903a9-119">下例表明，对于所有这些转换，`is` 表达式的计算结果都为 `true`。</span><span class="sxs-lookup"><span data-stu-id="903a9-119">The following example shows that the `is` expression evaluates to `true` for each of these conversions.</span></span>

[!code-csharp[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]

<span data-ttu-id="903a9-120">如果已知表达式始终为 `true` 或 `false`，则 `is` 关键字会生成编译时警告。</span><span class="sxs-lookup"><span data-stu-id="903a9-120">The `is` keyword generates a compile-time warning if the expression is known to always be either `true` or `false`.</span></span> <span data-ttu-id="903a9-121">它只考虑引用转换、装箱转换和取消装箱转换；不考虑用户定义的转换或由类型的[隐式](implicit.md)和[显式](explicit.md)运算符定义的转换。</span><span class="sxs-lookup"><span data-stu-id="903a9-121">It only considers reference conversions, boxing conversions, and unboxing conversions; it does not consider user-defined conversions or conversions defined by a type's [implicit](implicit.md) and [explicit](explicit.md) operators.</span></span> <span data-ttu-id="903a9-122">下例生成警告，因为转换结果在编译时就已知。</span><span class="sxs-lookup"><span data-stu-id="903a9-122">The following example generates warnings because the result of the conversion is known at compile-time.</span></span> <span data-ttu-id="903a9-123">请注意，`is` 表达式从 `int` 到 `long` 和 `double` 的转换会返回 false，因为这些转换由[隐式](implicit.md)运算符处理。</span><span class="sxs-lookup"><span data-stu-id="903a9-123">Note that the `is` expression for conversions from `int` to `long` and `double` return false, since these conversions are handled by the [implicit](implicit.md) operator.</span></span>

[!code-csharp[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]

<span data-ttu-id="903a9-124">`expr` 可以是返回值的任何表达式，匿名方法和 Lambda 表达式除外。</span><span class="sxs-lookup"><span data-stu-id="903a9-124">`expr` can be any expression that returns a value, with the exception of anonymous methods and lambda expressions.</span></span> <span data-ttu-id="903a9-125">下例使用 `is` 来计算方法调用的返回值。</span><span class="sxs-lookup"><span data-stu-id="903a9-125">The following example uses  `is` to evaluate the return value of a method call.</span></span>   
[!code-csharp[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]

<span data-ttu-id="903a9-126">从 C# 7.0 开始，可以使用[类型模式](#type)的模式匹配来编写代码，代码使用 `is` 语句更为简洁。</span><span class="sxs-lookup"><span data-stu-id="903a9-126">Starting with C# 7.0, you can use pattern matching with the [type pattern](#type) to write more concise code that uses the `is` statement.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="903a9-127">利用 `is` 的模式匹配</span><span class="sxs-lookup"><span data-stu-id="903a9-127">Pattern matching with `is`</span></span> ##

<span data-ttu-id="903a9-128">从 C# 7.0 开始，`is` 和 [switch](../../../csharp/language-reference/keywords/switch.md) 语句支持模式匹配。</span><span class="sxs-lookup"><span data-stu-id="903a9-128">Starting with C# 7.0, the `is` and [switch](../../../csharp/language-reference/keywords/switch.md) statements support pattern matching.</span></span> <span data-ttu-id="903a9-129">`is` 关键字支持以下模式：</span><span class="sxs-lookup"><span data-stu-id="903a9-129">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="903a9-130">[类型模式](#type)，用于测试表达式是否可转换为指定类型，如果可以，则将其转换为该类型的一个变量。</span><span class="sxs-lookup"><span data-stu-id="903a9-130">[Type pattern](#type),  which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="903a9-131">[常量模式](#constant)，用于测试表达式计算结果是否为指定的常数值。</span><span class="sxs-lookup"><span data-stu-id="903a9-131">[Constant pattern](#constant), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="903a9-132">[var 模式](#var)，始终成功的匹配，可将表达式的值绑定到新局部变量。</span><span class="sxs-lookup"><span data-stu-id="903a9-132">[var pattern](#var), a match that always succeeds and binds the value of an expression to a new local variable.</span></span> 

### <span data-ttu-id="903a9-133"><a name="type" />类型模式</a></span><span class="sxs-lookup"><span data-stu-id="903a9-133"><a name="type" /> Type pattern </a></span></span>

<span data-ttu-id="903a9-134">使用类型模式执行模式匹配时，`is` 会测试表达式是否可转换为指定类型，如果可以，则将其转换为该类型的一个变量。</span><span class="sxs-lookup"><span data-stu-id="903a9-134">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="903a9-135">它是 `is` 语句的直接扩展，可执行简单的类型计算和转换。</span><span class="sxs-lookup"><span data-stu-id="903a9-135">It is a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="903a9-136">`is` 类型模式的一般形式为：</span><span class="sxs-lookup"><span data-stu-id="903a9-136">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname 
```

<span data-ttu-id="903a9-137">其中 *expr* 是计算结果为某个类型的实例的表达式，*type* 是 *expr* 结果要转换到的类型的名称，*varname* 是 *expr* 结果要转换到的对象（如果 `is` 测试为 `true`）。</span><span class="sxs-lookup"><span data-stu-id="903a9-137">where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span> 

<span data-ttu-id="903a9-138">如果 expr 不为 `null` 且以下任意内容为 true，那么 `is` 表达式为 `true`：</span><span class="sxs-lookup"><span data-stu-id="903a9-138">The `is` expression is `true` if *expr* is not `null`, and any of the following is true:</span></span>

- <span data-ttu-id="903a9-139">*expr* 是与 *type* 具有相同类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="903a9-139">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="903a9-140">*expr* 是派生自 *type* 的类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="903a9-140">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="903a9-141">换言之，*expr* 结果可以向上转换为 *type* 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="903a9-141">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="903a9-142">*expr* 具有属于 *type* 的一个基类的编译时类型，*expr* 还具有属于 *type* 或派生自 *type* 的运行时类型。</span><span class="sxs-lookup"><span data-stu-id="903a9-142">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="903a9-143">变量的编译时类型是其声明中定义的变量类型。</span><span class="sxs-lookup"><span data-stu-id="903a9-143">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="903a9-144">变量的运行时类型是分配给该变量的实例类型。</span><span class="sxs-lookup"><span data-stu-id="903a9-144">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="903a9-145">*expr* 是实现 *type* 接口的类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="903a9-145">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="903a9-146">如果 expr 为 `true`，且 `is` 与 `if` 语句一起使用，则会分配 varname，并且其仅在 `if` 语句中具有局部范围。</span><span class="sxs-lookup"><span data-stu-id="903a9-146">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned and has local scope within the `if` statement only.</span></span>

<span data-ttu-id="903a9-147">下列示例使用 `is` 类型模式为类型的 <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> 方法提供实现。</span><span class="sxs-lookup"><span data-stu-id="903a9-147">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="903a9-148">如果没有模式匹配，则可能按以下方式编写此代码。</span><span class="sxs-lookup"><span data-stu-id="903a9-148">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="903a9-149">使用类型模式匹配无需测试转换结果是否为 `null`，从而生成更紧凑易读的代码。</span><span class="sxs-lookup"><span data-stu-id="903a9-149">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="903a9-150">确定值类型的类型时，`is` 类型模式也会生成更紧凑的代码。</span><span class="sxs-lookup"><span data-stu-id="903a9-150">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="903a9-151">下例在显示相应属性的值之前使用 `is` 类型模式来确定对象是 `Person` 还是 `Dog` 实例。</span><span class="sxs-lookup"><span data-stu-id="903a9-151">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span> 

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="903a9-152">对于无模式匹配的等效代码，需要为其单独分配显式转换。</span><span class="sxs-lookup"><span data-stu-id="903a9-152">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="a-nameconstant--constant-pattern"></a><span data-ttu-id="903a9-153"><a name="constant" />常量模式</span><span class="sxs-lookup"><span data-stu-id="903a9-153"><a name="constant" /> Constant pattern</span></span> ###

<span data-ttu-id="903a9-154">使用常量模式执行模式匹配时，`is` 会测试表达式结果是否等于指定常量。</span><span class="sxs-lookup"><span data-stu-id="903a9-154">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="903a9-155">在 C# 6 和更低版本中，[switch](switch.md) 语句支持常量模式。</span><span class="sxs-lookup"><span data-stu-id="903a9-155">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="903a9-156">从 C# 7.0 开始，`is` 语句也支持常量模式。</span><span class="sxs-lookup"><span data-stu-id="903a9-156">Starting with C# 7.0, it is supported by the `is` statement as well.</span></span> <span data-ttu-id="903a9-157">语法为：</span><span class="sxs-lookup"><span data-stu-id="903a9-157">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="903a9-158">其中 *expr* 是要计算的表达式，*constant* 是要测试的值。</span><span class="sxs-lookup"><span data-stu-id="903a9-158">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="903a9-159">*constant* 可以是以下任何常数表达式：</span><span class="sxs-lookup"><span data-stu-id="903a9-159">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="903a9-160">一个文本值。</span><span class="sxs-lookup"><span data-stu-id="903a9-160">A literal value.</span></span>

- <span data-ttu-id="903a9-161">已声明 `const` 变量的名称。</span><span class="sxs-lookup"><span data-stu-id="903a9-161">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="903a9-162">一个枚举常量。</span><span class="sxs-lookup"><span data-stu-id="903a9-162">An enumeration constant.</span></span>

<span data-ttu-id="903a9-163">常数表达式的计算方式如下：</span><span class="sxs-lookup"><span data-stu-id="903a9-163">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="903a9-164">如果 *expr* 和 *constant* 均为整型类型，则 C# 相等运算符确定表示式是否返回 `true`（即，是否为 `expr == constant`）。</span><span class="sxs-lookup"><span data-stu-id="903a9-164">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="903a9-165">否则，由对静态 [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) 方法的调用来确定表达式的值。</span><span class="sxs-lookup"><span data-stu-id="903a9-165">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="903a9-166">下例同时使用了类型模式和常量模式来测试对象是否为 `Dice` 实例，如果是，则确定骰子的值是否为 6。</span><span class="sxs-lookup"><span data-stu-id="903a9-166">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]
 
### <span data-ttu-id="903a9-167"><a name="var" />var 模式</a></span><span class="sxs-lookup"><span data-stu-id="903a9-167"><a name="var" /> var pattern </a></span></span>

<span data-ttu-id="903a9-168">具有 var 模式的模式匹配始终成功。</span><span class="sxs-lookup"><span data-stu-id="903a9-168">A pattern match with the var pattern always succeeds.</span></span> <span data-ttu-id="903a9-169">语法为</span><span class="sxs-lookup"><span data-stu-id="903a9-169">Its syntax is</span></span>

```csharp 
   expr is var varname
```

<span data-ttu-id="903a9-170">其中，*expr* 的值始终分配给名为 *varname* 的局部变量。</span><span class="sxs-lookup"><span data-stu-id="903a9-170">where the value of *expr* is always assigned to a local variable named *varname*.</span></span> <span data-ttu-id="903a9-171">*varname* 是一个与 *expr* 具有相同类型的静态变量。</span><span class="sxs-lookup"><span data-stu-id="903a9-171">*varname* is a static variable of the same type as *expr*.</span></span> <span data-ttu-id="903a9-172">下例使用 var 模式向名为 `obj` 的变量分配表达式。</span><span class="sxs-lookup"><span data-stu-id="903a9-172">The following example uses the var pattern to assign an expression to a variable named `obj`.</span></span> <span data-ttu-id="903a9-173">然后，显示 `obj` 的值和类型。</span><span class="sxs-lookup"><span data-stu-id="903a9-173">It then displays the value and the type of `obj`.</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

<span data-ttu-id="903a9-174">请注意，如果 *expr* 为 `null`，则 `is` 表达式仍为 true 并向 *varname* 分配 `null`。</span><span class="sxs-lookup"><span data-stu-id="903a9-174">Note that if *expr* is `null`, the `is` expression still is true and assigns `null` to *varname*.</span></span> 

# <a name="c-language-specification"></a><span data-ttu-id="903a9-175">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="903a9-175">C# Language Specification</span></span>
  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="903a9-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="903a9-176">See also</span></span>

- [<span data-ttu-id="903a9-177">C# 参考</span><span class="sxs-lookup"><span data-stu-id="903a9-177">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="903a9-178">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="903a9-178">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="903a9-179">typeof</span><span class="sxs-lookup"><span data-stu-id="903a9-179">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)  
- [<span data-ttu-id="903a9-180">as</span><span class="sxs-lookup"><span data-stu-id="903a9-180">as</span></span>](../../../csharp/language-reference/keywords/as.md)  
- [<span data-ttu-id="903a9-181">运算符关键字</span><span class="sxs-lookup"><span data-stu-id="903a9-181">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
