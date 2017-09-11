---
title: "is（C# 参考）"
keywords: "is 关键字 (C#), is (C#)"
ms.date: 2017-02-17
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- is_CSharpKeyword
- is
dev_langs:
- CSharp
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 58b18284b12ca0c636ed3fa923c43d94f202597f
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="is-c-reference"></a><span data-ttu-id="3dd7b-103">is（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3dd7b-103">is (C# Reference)</span></span> #

<span data-ttu-id="3dd7b-104">检查对象是否与给定类型兼容，或（从 C# 7 开始）针对某个模式测试表达式。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-104">Checks if an object is compatible with a given type, or (starting with C# 7) tests an expression against a pattern.</span></span>

## <a name="testing-for-type-compatibility"></a><span data-ttu-id="3dd7b-105">类型兼容性测试</span><span class="sxs-lookup"><span data-stu-id="3dd7b-105">Testing for type compatibility</span></span> ##

<span data-ttu-id="3dd7b-106">`is` 关键字在运行时评估类型兼容性。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-106">The `is` keyword evaluates type compatibility at runtime.</span></span> <span data-ttu-id="3dd7b-107">它确定对象实例或表达式结果是否可转换为指定类型。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-107">It determines whether an object instance or the result of an expression can be converted to a specified type.</span></span> <span data-ttu-id="3dd7b-108">语法如下：</span><span class="sxs-lookup"><span data-stu-id="3dd7b-108">It has the syntax</span></span>

```csharp
   expr is type
```

<span data-ttu-id="3dd7b-109">其中 *expr* 是计算结果为某个类型的实例的表达式，而 *type* 是 *expr* 结果要转换到的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-109">where *expr* is an expression that evaluates to an instance of some type, and *type* is the name of the type to which the result of *expr* is to be converted.</span></span> <span data-ttu-id="3dd7b-110">如果 *expr* 非空，并且通过计算表达式得出的对象可转换为 *type*，则 `is` 语句为 `true`；否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-110">The `is` statement is `true` if *expr* is non-null and the object that results from evaluating the expression can be converted to *type*; otherwise, it returns `false`.</span></span>

<span data-ttu-id="3dd7b-111">例如，以下代码确定 `obj` 是否可转换为 `Person` 类型的实例：</span><span class="sxs-lookup"><span data-stu-id="3dd7b-111">For example, the following code determines if `obj` can be cast to an instance of the `Person` type:</span></span>

<span data-ttu-id="3dd7b-112">[!code-cs[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="3dd7b-112">[!code-cs[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]</span></span>

<span data-ttu-id="3dd7b-113">如果满足以下条件，则 `is` 语句为 true：</span><span class="sxs-lookup"><span data-stu-id="3dd7b-113">The `is` statement is true if:</span></span>

- <span data-ttu-id="3dd7b-114">*expr* 是与 *type* 具有相同类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-114">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="3dd7b-115">*expr* 是派生自 *type* 的类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-115">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="3dd7b-116">换言之，*expr* 结果可以向上转换为 *type* 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-116">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="3dd7b-117">*expr* 具有属于 *type* 的一个基类的编译时类型，*expr* 还具有属于 *type* 或派生自 *type* 的运行时类型。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-117">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="3dd7b-118">变量的编译时类型是其声明中定义的变量类型。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-118">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="3dd7b-119">变量的运行时类型是分配给该变量的实例类型。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-119">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="3dd7b-120">*expr* 是实现 *type* 接口的类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-120">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="3dd7b-121">下例表明，对于所有这些转换，`is` 表达式的计算结果都为 `true`。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-121">The following example shows that the `is` expression evaluates to `true` for each of these conversions.</span></span>

<span data-ttu-id="3dd7b-122">[!code-cs[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]</span><span class="sxs-lookup"><span data-stu-id="3dd7b-122">[!code-cs[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]</span></span>

<span data-ttu-id="3dd7b-123">如果已知表达式始终为 `true` 或 `false`，则 `is` 关键字会生成编译时警告。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-123">The `is` keyword generates a compile-time warning if the expression is known to always be either `true` or `false`.</span></span> <span data-ttu-id="3dd7b-124">它只考虑引用转换、装箱转换和取消装箱转换；不考虑用户定义的转换或由类型的[隐式](implicit.md)和[显式](explicit.md)运算符定义的转换。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-124">It only considers reference conversions, boxing conversions, and unboxing conversions; it does not consider user-defined conversions or conversions defined by a type's [implicit](implicit.md) and [explicit](explicit.md) operators.</span></span> <span data-ttu-id="3dd7b-125">下例生成警告，因为转换结果在编译时就已知。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-125">The following example generates warnings because the result of the conversion is known at compile-time.</span></span> <span data-ttu-id="3dd7b-126">请注意，`is` 表达式从 `int` 到 `long` 和 `double` 的转换会返回 false，因为这些转换由[隐式](implicit.md)运算符处理。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-126">Note that the `is` expression for conversions from `int` to `long` and `double` return false, since these conversions are handled by the [implicit](implicit.md) operator.</span></span>

<span data-ttu-id="3dd7b-127">[!code-cs[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="3dd7b-127">[!code-cs[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]</span></span>

<span data-ttu-id="3dd7b-128">`expr` 可以是返回值的任何表达式，匿名方法和 Lambda 表达式除外。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-128">`expr` can be any expression that returns a value, with the exception of anonymous methods and lambda expressions.</span></span> <span data-ttu-id="3dd7b-129">下例使用 `is` 来计算方法调用的返回值。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-129">The following example uses  `is` to evaluate the return value of a method call.</span></span>   
<span data-ttu-id="3dd7b-130">[!code-cs[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]</span><span class="sxs-lookup"><span data-stu-id="3dd7b-130">[!code-cs[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]</span></span>

<span data-ttu-id="3dd7b-131">从 C# 7 开始，可以使用[类型模式](#type)的模式匹配来编写代码，代码使用 `is` 语句更为简洁。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-131">Starting with C# 7, you can use pattern matching with the [type pattern](#type) to write more concise code that uses the `is` statement.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="3dd7b-132">利用 `is` 的模式匹配</span><span class="sxs-lookup"><span data-stu-id="3dd7b-132">Pattern matching with `is`</span></span> ##

<span data-ttu-id="3dd7b-133">从 C# 7 开始，`is` 和 [switch](../../../csharp/language-reference/keywords/switch.md) 语句支持模式匹配。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-133">Starting with C# 7, the `is` and [switch](../../../csharp/language-reference/keywords/switch.md) statements support pattern matching.</span></span> <span data-ttu-id="3dd7b-134">`is` 关键字支持以下模式：</span><span class="sxs-lookup"><span data-stu-id="3dd7b-134">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="3dd7b-135">[类型模式](#type)，用于测试表达式是否可转换为指定类型，如果可以，则将其转换为该类型的一个变量。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-135">[Type pattern](#type),  which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="3dd7b-136">[常量模式](#constant)，用于测试表达式计算结果是否为指定的常数值。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-136">[Constant pattern](#constant), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="3dd7b-137">[var 模式](#var)，始终成功的匹配，可将表达式的值绑定到新局部变量。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-137">[var pattern](#var), a match that always succeeds and binds the value of an expression to a new local variable.</span></span> 

### <span data-ttu-id="3dd7b-138"><a name="type" />类型模式</a></span><span class="sxs-lookup"><span data-stu-id="3dd7b-138"><a name="type" /> Type pattern </a></span></span>

<span data-ttu-id="3dd7b-139">使用类型模式执行模式匹配时，`is` 会测试表达式是否可转换为指定类型，如果可以，则将其转换为该类型的一个变量。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-139">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="3dd7b-140">它是 `is` 语句的直接扩展，可执行简单的类型计算和转换。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-140">It is a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="3dd7b-141">`is` 类型模式的一般形式为：</span><span class="sxs-lookup"><span data-stu-id="3dd7b-141">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname 
```

<span data-ttu-id="3dd7b-142">其中 *expr* 是计算结果为某个类型的实例的表达式，*type* 是 *expr* 结果要转换到的类型的名称，*varname* 是 *expr* 结果要转换到的对象（如果 `is` 测试为 `true`）。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-142">where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span> 

<span data-ttu-id="3dd7b-143">如果以下任一条件成立，则 `is` 表达式为 `true`：</span><span class="sxs-lookup"><span data-stu-id="3dd7b-143">The `is` expression is `true` if any of the following is true:</span></span>

- <span data-ttu-id="3dd7b-144">*expr* 是与 *type* 具有相同类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-144">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="3dd7b-145">*expr* 是派生自 *type* 的类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-145">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="3dd7b-146">换言之，*expr* 结果可以向上转换为 *type* 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-146">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="3dd7b-147">*expr* 具有属于 *type* 的一个基类的编译时类型，*expr* 还具有属于 *type* 或派生自 *type* 的运行时类型。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-147">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="3dd7b-148">变量的编译时类型是其声明中定义的变量类型。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-148">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="3dd7b-149">变量的运行时类型是分配给该变量的实例类型。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-149">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="3dd7b-150">*expr* 是实现 *type* 接口的类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-150">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="3dd7b-151">如果 *exp* 为 `true`，且 `is` 与 `if` 语句一起使用，则会分配 *varname*，并且其仅在 `if` 语句中具有局部范围。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-151">If *exp* is `true` and `is` is used with an `if` statement, *varname* is assigned and has local scope within the `if` statement only.</span></span>

<span data-ttu-id="3dd7b-152">下列示例使用 `is` 类型模式为类型的 <xref:System.IComparable.CompareTo(System.Object)?displayProperty=fullName> 方法提供实现。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-152">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=fullName> method.</span></span>

<span data-ttu-id="3dd7b-153">[!code-cs[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]</span><span class="sxs-lookup"><span data-stu-id="3dd7b-153">[!code-cs[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]</span></span>

<span data-ttu-id="3dd7b-154">如果没有模式匹配，则可以按以下方式编写此代码。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-154">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="3dd7b-155">使用类型模式匹配无需测试转换结果是否为 `null`，从而生成更紧凑易读的代码。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-155">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

<span data-ttu-id="3dd7b-156">[!code-cs[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]</span><span class="sxs-lookup"><span data-stu-id="3dd7b-156">[!code-cs[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]</span></span>

<span data-ttu-id="3dd7b-157">确定值类型的类型时，`is` 类型模式也会生成更紧凑的代码。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-157">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="3dd7b-158">下例在显示相应属性的值之前使用 `is` 类型模式来确定对象是 `Person` 还是 `Dog` 实例。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-158">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span> 

<span data-ttu-id="3dd7b-159">[!code-cs[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]</span><span class="sxs-lookup"><span data-stu-id="3dd7b-159">[!code-cs[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]</span></span>

<span data-ttu-id="3dd7b-160">对于无模式匹配的等效代码，需要为其单独分配显式转换。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-160">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

<span data-ttu-id="3dd7b-161">[!code-cs[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]</span><span class="sxs-lookup"><span data-stu-id="3dd7b-161">[!code-cs[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]</span></span>

### <a name="a-nameconstant--constant-pattern"></a><span data-ttu-id="3dd7b-162"><a name="constant" />常量模式</span><span class="sxs-lookup"><span data-stu-id="3dd7b-162"><a name="constant" /> Constant pattern</span></span> ###

<span data-ttu-id="3dd7b-163">使用常量模式执行模式匹配时，`is` 会测试表达式结果是否等于指定常量。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-163">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="3dd7b-164">在 C# 6 和更低版本中，[switch](switch.md) 语句支持常量模式。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-164">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="3dd7b-165">从 C# 7 开始，`is` 语句也支持常量模式。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-165">Starting with C# 7, it is supported by the `is` statement as well.</span></span> <span data-ttu-id="3dd7b-166">语法为：</span><span class="sxs-lookup"><span data-stu-id="3dd7b-166">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="3dd7b-167">其中 *expr* 是要计算的表达式，*constant* 是要测试的值。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-167">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="3dd7b-168">*constant* 可以是以下任何常数表达式：</span><span class="sxs-lookup"><span data-stu-id="3dd7b-168">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="3dd7b-169">一个文本值。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-169">A literal value.</span></span>

- <span data-ttu-id="3dd7b-170">已声明 `const` 变量的名称。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-170">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="3dd7b-171">一个枚举常量。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-171">An enumeration constant.</span></span>

<span data-ttu-id="3dd7b-172">常数表达式的计算方式如下：</span><span class="sxs-lookup"><span data-stu-id="3dd7b-172">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="3dd7b-173">如果 *expr* 和 *constant* 均为整型类型，则 C# 相等运算符确定表示式是否返回 `true`（即，是否为 `expr == constant`）。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-173">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="3dd7b-174">否则，由对静态 [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) 方法的调用来确定表达式的值。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-174">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="3dd7b-175">下例同时使用了类型模式和常量模式来测试对象是否为 `Dice` 实例，如果是，则确定骰子的值是否为 6。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-175">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

<span data-ttu-id="3dd7b-176">[!code-cs[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]</span><span class="sxs-lookup"><span data-stu-id="3dd7b-176">[!code-cs[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]</span></span>
 
### <span data-ttu-id="3dd7b-177"><a name="var" />var 模式</a></span><span class="sxs-lookup"><span data-stu-id="3dd7b-177"><a name="var" /> var pattern </a></span></span>

<span data-ttu-id="3dd7b-178">具有 var 模式的模式匹配始终成功。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-178">A pattern match with the var pattern always succeeds.</span></span> <span data-ttu-id="3dd7b-179">语法为</span><span class="sxs-lookup"><span data-stu-id="3dd7b-179">Its syntax is</span></span>

```csharp 
   expr is var varname
```

<span data-ttu-id="3dd7b-180">其中，*expr* 的值始终分配给名为 *varname* 的局部变量。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-180">where the value of *expr* is always assigned to a local variable named *varname*.</span></span> <span data-ttu-id="3dd7b-181">*varname* 是一个与 *expr* 具有相同类型的静态变量。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-181">*varname* is a static variable of the same type as *expr*.</span></span> <span data-ttu-id="3dd7b-182">下例使用 var 模式向名为 `obj` 的变量分配表达式。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-182">The following example uses the var pattern to assign an expression to a variable named `obj`.</span></span> <span data-ttu-id="3dd7b-183">然后，显示 `obj` 的值和类型。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-183">It then displays the value and the type of `obj`.</span></span>

<span data-ttu-id="3dd7b-184">[!code-cs[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]</span><span class="sxs-lookup"><span data-stu-id="3dd7b-184">[!code-cs[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]</span></span>

<span data-ttu-id="3dd7b-185">请注意，如果 *expr* 为 `null`，则 `is` 表达式仍为 true 并向 *varname* 分配 `null`。</span><span class="sxs-lookup"><span data-stu-id="3dd7b-185">Note that if *expr* is `null`, the `is` expression still is true and assigns `null` to *varname*.</span></span> 

# <a name="c-language-specification"></a><span data-ttu-id="3dd7b-186">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="3dd7b-186">C# Language Specification</span></span>
  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3dd7b-187">请参阅</span><span class="sxs-lookup"><span data-stu-id="3dd7b-187">See also</span></span>  
 <span data-ttu-id="3dd7b-188">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3dd7b-188">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3dd7b-189">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="3dd7b-189">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="3dd7b-190">[typeof](../../../csharp/language-reference/keywords/typeof.md) </span><span class="sxs-lookup"><span data-stu-id="3dd7b-190">[typeof](../../../csharp/language-reference/keywords/typeof.md) </span></span>  
 <span data-ttu-id="3dd7b-191">[as](../../../csharp/language-reference/keywords/as.md) </span><span class="sxs-lookup"><span data-stu-id="3dd7b-191">[as](../../../csharp/language-reference/keywords/as.md) </span></span>  
 [<span data-ttu-id="3dd7b-192">运算符关键字</span><span class="sxs-lookup"><span data-stu-id="3dd7b-192">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)

