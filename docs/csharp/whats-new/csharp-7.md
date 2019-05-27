---
title: C# 7.0 中的新增功能 - C# 指南
description: 大致了解 C# 语言的版本 7.0 中的新增功能。
ms.date: 02/20/2019
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: 942a126ae026897d608c9fb077fc5f10ff73c110
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64753058"
---
# <a name="whats-new-in-c-70"></a><span data-ttu-id="92a20-103">C# 7.0 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="92a20-103">What's new in C# 7.0</span></span>

<span data-ttu-id="92a20-104">C# 7.0 向 C# 语言添加了许多新功能：</span><span class="sxs-lookup"><span data-stu-id="92a20-104">C# 7.0 adds a number of new features to the C# language:</span></span>
* [<span data-ttu-id="92a20-105">`out` 变量</span><span class="sxs-lookup"><span data-stu-id="92a20-105">`out` variables</span></span>](#out-variables)
  - <span data-ttu-id="92a20-106">可以将 `out` 值内联作为参数声明到使用这些参数的方法中。</span><span class="sxs-lookup"><span data-stu-id="92a20-106">You can declare `out` values inline as arguments to the method where they're used.</span></span>
* [<span data-ttu-id="92a20-107">元组</span><span class="sxs-lookup"><span data-stu-id="92a20-107">Tuples</span></span>](#tuples)
  - <span data-ttu-id="92a20-108">可以创建包含多个公共字段的轻量级未命名类型。</span><span class="sxs-lookup"><span data-stu-id="92a20-108">You can create lightweight, unnamed types that contain multiple public fields.</span></span> <span data-ttu-id="92a20-109">编译器和 IDE 工具可理解这些类型的语义。</span><span class="sxs-lookup"><span data-stu-id="92a20-109">Compilers and IDE tools understand the semantics of these types.</span></span>
* [<span data-ttu-id="92a20-110">弃元</span><span class="sxs-lookup"><span data-stu-id="92a20-110">Discards</span></span>](#discards)
  - <span data-ttu-id="92a20-111">弃元是指在不关心所赋予的值时，赋值中使用的临时只写变量。</span><span class="sxs-lookup"><span data-stu-id="92a20-111">Discards are temporary, write-only variables used in assignments when you don't care about the value assigned.</span></span> <span data-ttu-id="92a20-112">在对元组和用户定义类型进行解构，以及在使用 `out` 参数调用方法时，它们的作用最大。</span><span class="sxs-lookup"><span data-stu-id="92a20-112">They're most useful when deconstructing tuples and user-defined types, as well as when calling methods with `out` parameters.</span></span>
* [<span data-ttu-id="92a20-113">模式匹配</span><span class="sxs-lookup"><span data-stu-id="92a20-113">Pattern Matching</span></span>](#pattern-matching)
  - <span data-ttu-id="92a20-114">可以基于任意类型和这些类型的成员的值创建分支逻辑。</span><span class="sxs-lookup"><span data-stu-id="92a20-114">You can create branching logic based on arbitrary types and values of the members of those types.</span></span>
* [<span data-ttu-id="92a20-115">`ref` 局部变量和返回结果</span><span class="sxs-lookup"><span data-stu-id="92a20-115">`ref` locals and returns</span></span>](#ref-locals-and-returns)
  - <span data-ttu-id="92a20-116">方法局部参数和返回值可以是对其他存储的引用。</span><span class="sxs-lookup"><span data-stu-id="92a20-116">Method local variables and return values can be references to other storage.</span></span>
* [<span data-ttu-id="92a20-117">本地函数</span><span class="sxs-lookup"><span data-stu-id="92a20-117">Local Functions</span></span>](#local-functions)
  - <span data-ttu-id="92a20-118">可以将函数嵌套在其他函数内，以限制其范围和可见性。</span><span class="sxs-lookup"><span data-stu-id="92a20-118">You can nest functions inside other functions to limit their scope and visibility.</span></span>
* [<span data-ttu-id="92a20-119">更多的 expression-bodied 成员</span><span class="sxs-lookup"><span data-stu-id="92a20-119">More expression-bodied members</span></span>](#more-expression-bodied-members)
  - <span data-ttu-id="92a20-120">可使用表达式创作的成员列表有所增长。</span><span class="sxs-lookup"><span data-stu-id="92a20-120">The list of members that can be authored using expressions has grown.</span></span>
* [<span data-ttu-id="92a20-121">`throw` 表达式</span><span class="sxs-lookup"><span data-stu-id="92a20-121">`throw` Expressions</span></span>](#throw-expressions)
  - <span data-ttu-id="92a20-122">可以在之前因为 `throw` 是语句而不被允许的代码构造中引发异常。</span><span class="sxs-lookup"><span data-stu-id="92a20-122">You can throw exceptions in code constructs that previously weren't allowed because `throw` was a statement.</span></span>
* [<span data-ttu-id="92a20-123">通用的异步返回类型</span><span class="sxs-lookup"><span data-stu-id="92a20-123">Generalized async return types</span></span>](#generalized-async-return-types)
  - <span data-ttu-id="92a20-124">使用 `async` 修饰符声明的方法可以返回除 `Task` 和 `Task<T>` 以外的其他类型。</span><span class="sxs-lookup"><span data-stu-id="92a20-124">Methods declared with the `async` modifier can return other types in addition to `Task` and `Task<T>`.</span></span>
* [<span data-ttu-id="92a20-125">数字文本语法改进</span><span class="sxs-lookup"><span data-stu-id="92a20-125">Numeric literal syntax improvements</span></span>](#numeric-literal-syntax-improvements)
  - <span data-ttu-id="92a20-126">新令牌可提高数值常量的可读性。</span><span class="sxs-lookup"><span data-stu-id="92a20-126">New tokens improve readability for numeric constants.</span></span>

<span data-ttu-id="92a20-127">本文的其余部分概述了每个功能。</span><span class="sxs-lookup"><span data-stu-id="92a20-127">The remainder of this article provides an overview of each feature.</span></span> <span data-ttu-id="92a20-128">你将了解每项功能背后的原理。</span><span class="sxs-lookup"><span data-stu-id="92a20-128">For each feature, you'll learn the reasoning behind it.</span></span> <span data-ttu-id="92a20-129">将了解语法。</span><span class="sxs-lookup"><span data-stu-id="92a20-129">You'll learn the syntax.</span></span> <span data-ttu-id="92a20-130">可以在这些功能的[交互式探索](../tutorials/exploration/csharp-7.yml)中探索这些功能。</span><span class="sxs-lookup"><span data-stu-id="92a20-130">You can explore these features in our [interactive exploration](../tutorials/exploration/csharp-7.yml) of these features.</span></span>

## <a name="out-variables"></a><span data-ttu-id="92a20-131">`out` 变量</span><span class="sxs-lookup"><span data-stu-id="92a20-131">`out` variables</span></span>

<span data-ttu-id="92a20-132">支持 `out` 参数的现有语法已在此版本中得到改进。</span><span class="sxs-lookup"><span data-stu-id="92a20-132">The existing syntax that supports `out` parameters has been improved in this version.</span></span> <span data-ttu-id="92a20-133">现在可以在方法调用的参数列表中声明 `out` 变量，而不是编写单独的声明语句：</span><span class="sxs-lookup"><span data-stu-id="92a20-133">You can now declare `out` variables in the argument list of a method call, rather than writing a separate declaration statement:</span></span>

[!code-csharp[OutVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVariableDeclarations "Out variable declarations")]

<span data-ttu-id="92a20-134">为清晰明了，可能需指定 `out` 变量的类型，如上所示。</span><span class="sxs-lookup"><span data-stu-id="92a20-134">You may want to specify the type of the `out` variable for clarity, as shown above.</span></span> <span data-ttu-id="92a20-135">但是，该语言支持使用隐式类型的局部变量：</span><span class="sxs-lookup"><span data-stu-id="92a20-135">However, the language does support using an implicitly typed local variable:</span></span>

[!code-csharp[OutVarVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVarVariableDeclarations "Implicitly typed Out variable")]

* <span data-ttu-id="92a20-136">代码更易于阅读。</span><span class="sxs-lookup"><span data-stu-id="92a20-136">The code is easier to read.</span></span>
  - <span data-ttu-id="92a20-137">在使用 out 变量的地方声明 out 变量，而不是在上面的另一行。</span><span class="sxs-lookup"><span data-stu-id="92a20-137">You declare the out variable where you use it, not on another line above.</span></span>
* <span data-ttu-id="92a20-138">无需分配初始值。</span><span class="sxs-lookup"><span data-stu-id="92a20-138">No need to assign an initial value.</span></span>
  - <span data-ttu-id="92a20-139">通过在方法调用中使用 `out` 变量的位置声明该变量，使得在分配它之前不可能意外使用它。</span><span class="sxs-lookup"><span data-stu-id="92a20-139">By declaring the `out` variable where it's used in a method call, you can't accidentally use it before it is assigned.</span></span>

## <a name="tuples"></a><span data-ttu-id="92a20-140">元组</span><span class="sxs-lookup"><span data-stu-id="92a20-140">Tuples</span></span>

<span data-ttu-id="92a20-141">C# 为用于说明设计意图的类和结构提供了丰富的语法。</span><span class="sxs-lookup"><span data-stu-id="92a20-141">C# provides a rich syntax for classes and structs that is used to explain your design intent.</span></span> <span data-ttu-id="92a20-142">但是，这种丰富的语法有时会需要额外的工作，但益处却很少。</span><span class="sxs-lookup"><span data-stu-id="92a20-142">But sometimes that rich syntax requires extra work with minimal benefit.</span></span> <span data-ttu-id="92a20-143">你可能经常编写需要包含多个数据元素的简单结构的方法。</span><span class="sxs-lookup"><span data-stu-id="92a20-143">You may often write methods that need a simple structure containing more than one data element.</span></span> <span data-ttu-id="92a20-144">为了支持这些方案，已将元组添加到了 C#。</span><span class="sxs-lookup"><span data-stu-id="92a20-144">To support these scenarios *tuples* were added to C#.</span></span> <span data-ttu-id="92a20-145">元组是包含多个字段以表示数据成员的轻量级数据结构。</span><span class="sxs-lookup"><span data-stu-id="92a20-145">Tuples are lightweight data structures that contain multiple fields to represent the data members.</span></span>
<span data-ttu-id="92a20-146">这些字段没有经过验证，并且你无法定义自己的方法</span><span class="sxs-lookup"><span data-stu-id="92a20-146">The fields aren't validated, and you can't define your own methods</span></span>

> [!NOTE]
> <span data-ttu-id="92a20-147">低于 C# 7.0 的版本中也提供元组，但它们效率低下且不具有语言支持。</span><span class="sxs-lookup"><span data-stu-id="92a20-147">Tuples were available before C# 7.0, but they were inefficient and had no language support.</span></span>
> <span data-ttu-id="92a20-148">这意味着元组元素只能作为 `Item1` 和 `Item2` 等引用。</span><span class="sxs-lookup"><span data-stu-id="92a20-148">This meant that tuple elements could only be referenced as `Item1`, `Item2` and so on.</span></span> <span data-ttu-id="92a20-149">C# 7.0 引入了对元组的语言支持，可利用更有效的新元组类型向元组字段赋予语义名称。</span><span class="sxs-lookup"><span data-stu-id="92a20-149">C# 7.0 introduces language support for tuples, which enables semantic names for the fields of a tuple using new, more efficient tuple types.</span></span>

<span data-ttu-id="92a20-150">可以通过为每个成员赋值来创建元组，并可选择为元组的每个成员提供语义名称：</span><span class="sxs-lookup"><span data-stu-id="92a20-150">You can create a tuple by assigning a value to each member, and optionally providing semantic names to each of the members of the tuple:</span></span>

[!code-csharp[NamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#NamedTuple "Named tuple")]

<span data-ttu-id="92a20-151">`namedLetters` 元组包含称为 `Alpha` 和 `Beta` 的字段。</span><span class="sxs-lookup"><span data-stu-id="92a20-151">The `namedLetters` tuple contains fields referred to as `Alpha` and `Beta`.</span></span> <span data-ttu-id="92a20-152">这些名称仅存在于编译时且不保留，例如在运行时使用反射来检查元组时。</span><span class="sxs-lookup"><span data-stu-id="92a20-152">Those names exist only at compile time and aren't preserved, for example when inspecting the tuple using reflection at runtime.</span></span>

<span data-ttu-id="92a20-153">在进行元组赋值时，还可以指定赋值右侧的字段的名称：</span><span class="sxs-lookup"><span data-stu-id="92a20-153">In a tuple assignment, you can also specify the names of the fields on the right-hand side of the assignment:</span></span>

[!code-csharp[ImplicitNamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#ImplicitNamedTuple "Implicitly named tuple")]

<span data-ttu-id="92a20-154">在某些时候，你可能想要解包从方法返回的元组的成员。</span><span class="sxs-lookup"><span data-stu-id="92a20-154">There may be times when you want to unpackage the members of a tuple that were returned from a method.</span></span>  <span data-ttu-id="92a20-155">可通过为元组中的每个值声明单独的变量来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="92a20-155">You can do that by declaring separate variables for each of the values in the tuple.</span></span> <span data-ttu-id="92a20-156">这种解包操作称为解构元组：</span><span class="sxs-lookup"><span data-stu-id="92a20-156">This unpackaging is called *deconstructing* the tuple:</span></span>

[!code-csharp[CallingWithDeconstructor](~/samples/snippets/csharp/new-in-7/program.cs#CallingWithDeconstructor "Deconstructing a tuple")]

<span data-ttu-id="92a20-157">还可以为 .NET 中的任何类型提供类似的析构。</span><span class="sxs-lookup"><span data-stu-id="92a20-157">You can also provide a similar deconstruction for any type in .NET.</span></span> <span data-ttu-id="92a20-158">编写 `Deconstruct` 方法，用作类的成员。</span><span class="sxs-lookup"><span data-stu-id="92a20-158">You write a `Deconstruct` method as a member of the class.</span></span> <span data-ttu-id="92a20-159">`Deconstruct` 方法为你要提取的每个属性提供一组 `out` 参数。</span><span class="sxs-lookup"><span data-stu-id="92a20-159">That `Deconstruct` method provides a set of `out` arguments for each of the properties you want to extract.</span></span> <span data-ttu-id="92a20-160">考虑提供析构函数方法的此 `Point` 类，该方法提取 `X` 和 `Y` 坐标：</span><span class="sxs-lookup"><span data-stu-id="92a20-160">Consider this `Point` class that provides a deconstructor method that extracts the `X` and `Y` coordinates:</span></span>

[!code-csharp[PointWithDeconstruction](~/samples/snippets/csharp/new-in-7/point.cs#PointWithDeconstruction "Point with deconstruction method")]

<span data-ttu-id="92a20-161">可以通过向元组分配 `Point` 来提取各个字段：</span><span class="sxs-lookup"><span data-stu-id="92a20-161">You can extract the individual fields by assigning a `Point` to a tuple:</span></span>

[!code-csharp[DeconstructPoint](~/samples/snippets/csharp/new-in-7/program.cs#DeconstructPoint "Deconstruct a point")]

<span data-ttu-id="92a20-162">可在[元组相关文章](../tuples.md)中深入了解有关元组的详细信息。</span><span class="sxs-lookup"><span data-stu-id="92a20-162">You can learn more in depth about tuples in the [tuples article](../tuples.md).</span></span>

## <a name="discards"></a><span data-ttu-id="92a20-163">弃元</span><span class="sxs-lookup"><span data-stu-id="92a20-163">Discards</span></span>

<span data-ttu-id="92a20-164">通常，在进行元组解构或使用 `out` 参数调用方法时，必须定义一个其值无关紧要且你不打算使用的变量。</span><span class="sxs-lookup"><span data-stu-id="92a20-164">Often when deconstructing a tuple or calling a method with `out` parameters, you're forced to define a variable whose value you don't care about and don't intend to use.</span></span> <span data-ttu-id="92a20-165">为处理此情况，C# 增添了对弃元的支持。</span><span class="sxs-lookup"><span data-stu-id="92a20-165">C# adds support for *discards* to handle this scenario.</span></span> <span data-ttu-id="92a20-166">弃元是一个名为 `_`（下划线字符）的只写变量，可向单个变量赋予要放弃的所有值。</span><span class="sxs-lookup"><span data-stu-id="92a20-166">A discard is a write-only variable whose name is `_` (the underscore character); you can assign all of the values that you intend to discard to the single variable.</span></span> <span data-ttu-id="92a20-167">弃元类似于未赋值的变量；不可在代码中使用弃元（赋值语句除外）。</span><span class="sxs-lookup"><span data-stu-id="92a20-167">A discard is like an unassigned variable; apart from the assignment statement, the discard can't be used in code.</span></span>

<span data-ttu-id="92a20-168">在以下方案中支持弃元：</span><span class="sxs-lookup"><span data-stu-id="92a20-168">Discards are supported in the following scenarios:</span></span>

* <span data-ttu-id="92a20-169">在对元组或用户定义的类型进行解构时。</span><span class="sxs-lookup"><span data-stu-id="92a20-169">When deconstructing tuples or user-defined types.</span></span>
* <span data-ttu-id="92a20-170">在使用 [out](../language-reference/keywords/out-parameter-modifier.md) 参数调用方法时。</span><span class="sxs-lookup"><span data-stu-id="92a20-170">When calling methods with [out](../language-reference/keywords/out-parameter-modifier.md) parameters.</span></span>
* <span data-ttu-id="92a20-171">在使用 [is](../language-reference/keywords/is.md) 和 [switch](../language-reference/keywords/switch.md) 语句匹配操作的模式中。</span><span class="sxs-lookup"><span data-stu-id="92a20-171">In a pattern matching operation with the [is](../language-reference/keywords/is.md) and [switch](../language-reference/keywords/switch.md) statements.</span></span>
* <span data-ttu-id="92a20-172">在要将某赋值的值显式标识为弃元时用作独立标识符。</span><span class="sxs-lookup"><span data-stu-id="92a20-172">As a standalone identifier when you want to explicitly identify the value of an assignment as a discard.</span></span>

<span data-ttu-id="92a20-173">以下示例定义了 `QueryCityDataForYears` 方法，它返回一个包含两个不同年份的城市数据的六元组。</span><span class="sxs-lookup"><span data-stu-id="92a20-173">The following example defines a `QueryCityDataForYears` method that returns a 6-tuple that contains a data for a city for two different years.</span></span> <span data-ttu-id="92a20-174">本例中，方法调用仅与此方法返回的两个人口值相关，因此在进行元组解构时，将元组中的其余值视为弃元。</span><span class="sxs-lookup"><span data-stu-id="92a20-174">The method call in the example is concerned only with the two population values returned by the method and so treats the remaining values in the tuple as discards when it deconstructs the tuple.</span></span>

[!code-csharp[Tuple-discard](~/samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

<span data-ttu-id="92a20-175">有关详细信息，请参阅[弃元](../discards.md)。</span><span class="sxs-lookup"><span data-stu-id="92a20-175">For more information, see [Discards](../discards.md).</span></span>

## <a name="pattern-matching"></a><span data-ttu-id="92a20-176">模式匹配</span><span class="sxs-lookup"><span data-stu-id="92a20-176">Pattern matching</span></span>

<span data-ttu-id="92a20-177">模式匹配是一种可让你对除对象类型以外的属性实现方法分派的功能。</span><span class="sxs-lookup"><span data-stu-id="92a20-177">*Pattern matching* is a feature that allows you to implement method dispatch on properties other than the type of an object.</span></span> <span data-ttu-id="92a20-178">你可能已经熟悉基于对象类型的方法分派。</span><span class="sxs-lookup"><span data-stu-id="92a20-178">You're probably already familiar with method dispatch based on the type of an object.</span></span> <span data-ttu-id="92a20-179">在面向对象的编程中，虚拟和重写方法提供语言语法来实现基于对象类型的方法分派。</span><span class="sxs-lookup"><span data-stu-id="92a20-179">In object-oriented programming, virtual and override methods provide language syntax to implement method dispatching based on an object's type.</span></span> <span data-ttu-id="92a20-180">基类和派生类提供不同的实现。</span><span class="sxs-lookup"><span data-stu-id="92a20-180">Base and Derived classes provide different implementations.</span></span>
<span data-ttu-id="92a20-181">模式匹配表达式扩展了这一概念，以便你可以通过继承层次结构为不相关的类型和数据元素轻松实现类似的分派模式。</span><span class="sxs-lookup"><span data-stu-id="92a20-181">Pattern matching expressions extend this concept so that you can easily implement similar dispatch patterns for types and data elements that aren't related through an inheritance hierarchy.</span></span>

<span data-ttu-id="92a20-182">模式匹配支持 `is` 表达式和 `switch` 表达式。</span><span class="sxs-lookup"><span data-stu-id="92a20-182">Pattern matching supports `is` expressions and `switch` expressions.</span></span> <span data-ttu-id="92a20-183">每个表达式都允许检查对象及其属性以确定该对象是否满足所寻求的模式。</span><span class="sxs-lookup"><span data-stu-id="92a20-183">Each enables inspecting an object and its properties to determine if that object satisfies the sought pattern.</span></span> <span data-ttu-id="92a20-184">使用 `when` 关键字来指定模式的其他规则。</span><span class="sxs-lookup"><span data-stu-id="92a20-184">You use the `when` keyword to specify additional rules to the pattern.</span></span>

<span data-ttu-id="92a20-185">`is` 模式表达式扩展了常用 [`is` 运算符](../language-reference/keywords/is.md#pattern-matching-with-is)以查询关于其类型的对象，并在一条指令分配结果。</span><span class="sxs-lookup"><span data-stu-id="92a20-185">The `is` pattern expression extends the familiar [`is` operator](../language-reference/keywords/is.md#pattern-matching-with-is) to query an object about its type and assign the result in one instruction.</span></span> <span data-ttu-id="92a20-186">以下代码检查变量是否为 `int`，如果是，则将其添加到当前总和：</span><span class="sxs-lookup"><span data-stu-id="92a20-186">The following code checks if a variable is an `int`, and if so, adds it to the current sum:</span></span>

```csharp
if (input is int count)
    sum += count;
```

<span data-ttu-id="92a20-187">前面的小型示例演示了 `is` 表达式的增强功能。</span><span class="sxs-lookup"><span data-stu-id="92a20-187">The preceding small example demonstrates the enhancements to the `is` expression.</span></span> <span data-ttu-id="92a20-188">可以针对值类型和引用类型进行测试，并且可以将成功结果分配给类型正确的新变量。</span><span class="sxs-lookup"><span data-stu-id="92a20-188">You can test against value types as well as reference types, and you can assign the successful result to a new variable of the correct type.</span></span>

<span data-ttu-id="92a20-189">switch 匹配表达式具有常见的语法，它基于已包含在 C# 语言中的 `switch` 语句。</span><span class="sxs-lookup"><span data-stu-id="92a20-189">The switch match expression has a familiar syntax, based on the `switch` statement already part of the C# language.</span></span> <span data-ttu-id="92a20-190">更新后的 switch 语句有几个新构造：</span><span class="sxs-lookup"><span data-stu-id="92a20-190">The updated switch statement has several new constructs:</span></span>

- <span data-ttu-id="92a20-191">`switch` 表达式的控制类型不再局限于整数类型、`Enum` 类型、`string` 或与这些类型之一对应的可为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="92a20-191">The governing type of a `switch` expression is no longer restricted to integral types, `Enum` types, `string`, or a nullable type corresponding to one of those types.</span></span> <span data-ttu-id="92a20-192">可能会使用任何类型。</span><span class="sxs-lookup"><span data-stu-id="92a20-192">Any type may be used.</span></span>
- <span data-ttu-id="92a20-193">可以在每个 `case` 标签中测试 `switch` 表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="92a20-193">You can test the type of the `switch` expression in each `case` label.</span></span> <span data-ttu-id="92a20-194">与 `is` 表达式一样，可以为该类型指定一个新变量。</span><span class="sxs-lookup"><span data-stu-id="92a20-194">As with the `is` expression, you may assign a new variable to that type.</span></span>
- <span data-ttu-id="92a20-195">可以添加 `when` 子句以进一步测试该变量的条件。</span><span class="sxs-lookup"><span data-stu-id="92a20-195">You may add a `when` clause to further test conditions on that variable.</span></span>
- <span data-ttu-id="92a20-196">`case` 标签的顺序现在很重要。</span><span class="sxs-lookup"><span data-stu-id="92a20-196">The order of `case` labels is now important.</span></span> <span data-ttu-id="92a20-197">执行匹配的第一个分支；其他将跳过。</span><span class="sxs-lookup"><span data-stu-id="92a20-197">The first branch to match is executed; others are skipped.</span></span>

<span data-ttu-id="92a20-198">以下代码演示了这些新功能：</span><span class="sxs-lookup"><span data-stu-id="92a20-198">The following code demonstrates these new features:</span></span>

```csharp
public static int SumPositiveNumbers(IEnumerable<object> sequence)
{
    int sum = 0;
    foreach (var i in sequence)
    {
        switch (i)
        {
            case 0:
                break;
            case IEnumerable<int> childSequence:
            {
                foreach(var item in childSequence)
                    sum += (item > 0) ? item : 0;
                break;
            }
            case int n when n > 0:
                sum += n;
                break;
            case null:
                throw new NullReferenceException("Null found in sequence");
            default:
                throw new InvalidOperationException("Unrecognized type");
        }
    }
    return sum;
}
```

- <span data-ttu-id="92a20-199">`case 0:` 是常见的常量模式。</span><span class="sxs-lookup"><span data-stu-id="92a20-199">`case 0:` is the familiar constant pattern.</span></span>
- <span data-ttu-id="92a20-200">`case IEnumerable<int> childSequence:` 是一种类型模式。</span><span class="sxs-lookup"><span data-stu-id="92a20-200">`case IEnumerable<int> childSequence:` is a type pattern.</span></span>
- <span data-ttu-id="92a20-201">`case int n when n > 0:` 是具有附加 `when` 条件的类型模式。</span><span class="sxs-lookup"><span data-stu-id="92a20-201">`case int n when n > 0:` is a type pattern with an additional `when` condition.</span></span>
- <span data-ttu-id="92a20-202">`case null:` 是 null 模式。</span><span class="sxs-lookup"><span data-stu-id="92a20-202">`case null:` is the null pattern.</span></span>
- <span data-ttu-id="92a20-203">`default:` 是常见的默认事例。</span><span class="sxs-lookup"><span data-stu-id="92a20-203">`default:` is the familiar default case.</span></span>

<span data-ttu-id="92a20-204">可以在 [C# 中的模式匹配](../pattern-matching.md)中了解有关模式匹配的更多信息。</span><span class="sxs-lookup"><span data-stu-id="92a20-204">You can learn more about pattern matching in [Pattern Matching in C#](../pattern-matching.md).</span></span>

## <a name="ref-locals-and-returns"></a><span data-ttu-id="92a20-205">Ref 局部变量和返回结果</span><span class="sxs-lookup"><span data-stu-id="92a20-205">Ref locals and returns</span></span>

<span data-ttu-id="92a20-206">此功能允许使用并返回对变量的引用的算法，这些变量在其他位置定义。</span><span class="sxs-lookup"><span data-stu-id="92a20-206">This feature enables algorithms that use and return references to variables defined elsewhere.</span></span> <span data-ttu-id="92a20-207">一个示例是使用大型矩阵并查找具有某些特征的单个位置。</span><span class="sxs-lookup"><span data-stu-id="92a20-207">One example is working with large matrices, and finding a single location with certain characteristics.</span></span> <span data-ttu-id="92a20-208">下面的方法在矩阵中向该存储返回“引用”：</span><span class="sxs-lookup"><span data-stu-id="92a20-208">The following method returns a **reference** to that storage in the matrix:</span></span>

[!code-csharp[FindReturningRef](~/samples/snippets/csharp/new-in-7/MatrixSearch.cs#FindReturningRef "Find returning by reference")]

<span data-ttu-id="92a20-209">可以将返回值声明为 `ref` 并在矩阵中修改该值，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="92a20-209">You can declare the return value as a `ref` and modify that value in the matrix, as shown in the following code:</span></span>

[!code-csharp[AssignRefReturn](~/samples/snippets/csharp/new-in-7/Program.cs#AssignRefReturn "Assign ref return")]

<span data-ttu-id="92a20-210">C# 语言还有多个规则，可保护你免于误用 `ref` 局部变量和返回结果：</span><span class="sxs-lookup"><span data-stu-id="92a20-210">The C# language has several rules that protect you from misusing the `ref` locals and returns:</span></span>

* <span data-ttu-id="92a20-211">必须将 `ref` 关键字添加到方法签名和方法中的所有 `return` 语句中。</span><span class="sxs-lookup"><span data-stu-id="92a20-211">You must add the `ref` keyword to the method signature and to all `return` statements in a method.</span></span>
  - <span data-ttu-id="92a20-212">这清楚地表明，该方法在整个方法中通过引用返回。</span><span class="sxs-lookup"><span data-stu-id="92a20-212">That makes it clear the method returns by reference throughout the method.</span></span>
* <span data-ttu-id="92a20-213">可以将 `ref return` 分配给值变量或 `ref` 变量。</span><span class="sxs-lookup"><span data-stu-id="92a20-213">A `ref return` may be assigned to a value variable, or a `ref` variable.</span></span>
  - <span data-ttu-id="92a20-214">调用方控制是否复制返回值。</span><span class="sxs-lookup"><span data-stu-id="92a20-214">The caller controls whether the return value is copied or not.</span></span> <span data-ttu-id="92a20-215">在分配返回值时省略 `ref` 修饰符表示调用方需要该值的副本，而不是对存储的引用。</span><span class="sxs-lookup"><span data-stu-id="92a20-215">Omitting the `ref` modifier when assigning the return value indicates that the caller wants a copy of the value, not a reference to the storage.</span></span>
* <span data-ttu-id="92a20-216">不可向 `ref` 本地变量赋予标准方法返回值。</span><span class="sxs-lookup"><span data-stu-id="92a20-216">You can't assign a standard method return value to a `ref` local variable.</span></span>
  - <span data-ttu-id="92a20-217">因为那将禁止类似 `ref int i = sequence.Count();` 这样的语句</span><span class="sxs-lookup"><span data-stu-id="92a20-217">That disallows statements like `ref int i = sequence.Count();`</span></span>
* <span data-ttu-id="92a20-218">不能将 `ref` 返回给其生存期不超出方法执行的变量。</span><span class="sxs-lookup"><span data-stu-id="92a20-218">You can't return a `ref` to a variable whose lifetime doesn't extend beyond the execution of the method.</span></span>
  - <span data-ttu-id="92a20-219">这意味着不可返回对本地变量或对类似作用域变量的引用。</span><span class="sxs-lookup"><span data-stu-id="92a20-219">That means you can't return a reference to a local variable or a variable with a similar scope.</span></span>
* <span data-ttu-id="92a20-220">`ref` 局部变量和返回结果不可用于异步方法。</span><span class="sxs-lookup"><span data-stu-id="92a20-220">`ref` locals and returns can't be used with async methods.</span></span>
  - <span data-ttu-id="92a20-221">编译器无法知道异步方法返回时，引用的变量是否已设置为其最终值。</span><span class="sxs-lookup"><span data-stu-id="92a20-221">The compiler can't know if the referenced variable has been set to its final value when the async method returns.</span></span>

<span data-ttu-id="92a20-222">添加 ref 局部变量和 ref 返回结果可通过避免复制值或多次执行取消引用操作，允许更为高效的算法。</span><span class="sxs-lookup"><span data-stu-id="92a20-222">The addition of ref locals and ref returns enables algorithms that are more efficient by avoiding copying values, or performing dereferencing operations multiple times.</span></span>

<span data-ttu-id="92a20-223">向返回值添加 `ref` 是[源兼容的更改](version-update-considerations.md#source-compatible-changes)。</span><span class="sxs-lookup"><span data-stu-id="92a20-223">Adding `ref` to the return value is a [source compatible change](version-update-considerations.md#source-compatible-changes).</span></span> <span data-ttu-id="92a20-224">现有代码会进行编译，但在分配时复制 ref 返回值。</span><span class="sxs-lookup"><span data-stu-id="92a20-224">Existing code compiles, but the ref return value is copied when assigned.</span></span> <span data-ttu-id="92a20-225">调用方必须将存储的返回值更新为 `ref` 局部变量，从而将返回值存储为引用。</span><span class="sxs-lookup"><span data-stu-id="92a20-225">Callers must update the storage for the return value to a `ref` local variable to store the return as a reference.</span></span>

<span data-ttu-id="92a20-226">有关详细信息，请参阅 [ref 关键字](../language-reference/keywords/ref.md)一文。</span><span class="sxs-lookup"><span data-stu-id="92a20-226">For more information, see the [ref keyword](../language-reference/keywords/ref.md) article.</span></span>

## <a name="local-functions"></a><span data-ttu-id="92a20-227">本地函数</span><span class="sxs-lookup"><span data-stu-id="92a20-227">Local functions</span></span>

<span data-ttu-id="92a20-228">许多类的设计都包括仅从一个位置调用的方法。</span><span class="sxs-lookup"><span data-stu-id="92a20-228">Many designs for classes include methods that are called from only one location.</span></span> <span data-ttu-id="92a20-229">这些额外的私有方法使每个方法保持小且集中。</span><span class="sxs-lookup"><span data-stu-id="92a20-229">These additional private methods keep each method small and focused.</span></span> <span data-ttu-id="92a20-230">本地函数使你能够在另一个方法的上下文内声明方法。</span><span class="sxs-lookup"><span data-stu-id="92a20-230">*Local functions* enable you to declare methods inside the context of another method.</span></span> <span data-ttu-id="92a20-231">本地函数使得类的阅读者更容易看到本地方法仅从声明它的上下文中调用。</span><span class="sxs-lookup"><span data-stu-id="92a20-231">Local functions make it easier for readers of the class to see that the local method is only called from the context in which it is declared.</span></span>

<span data-ttu-id="92a20-232">对于本地函数有两个常见的用例：公共迭代器方法和公共异步方法。</span><span class="sxs-lookup"><span data-stu-id="92a20-232">There are two common use cases for local functions: public iterator methods and public async methods.</span></span> <span data-ttu-id="92a20-233">这两种类型的方法都生成报告错误的时间晚于程序员期望时间的代码。</span><span class="sxs-lookup"><span data-stu-id="92a20-233">Both types of methods generate code that reports errors later than programmers might expect.</span></span> <span data-ttu-id="92a20-234">在迭代器方法中，只有在调用枚举返回的序列的代码时才会观察到任何异常。</span><span class="sxs-lookup"><span data-stu-id="92a20-234">In iterator methods, any exceptions are observed only when calling code that enumerates the returned sequence.</span></span> <span data-ttu-id="92a20-235">在异步方法中，只有当返回的 `Task` 处于等待状态时才会观察到任何异常。</span><span class="sxs-lookup"><span data-stu-id="92a20-235">In async methods, any exceptions are only observed when the returned `Task` is awaited.</span></span> <span data-ttu-id="92a20-236">以下示例演示如何使用本地函数将参数验证与迭代器实现分离：</span><span class="sxs-lookup"><span data-stu-id="92a20-236">The following example demonstrates separating parameter validation from the iterator implementation using a local function:</span></span>

[!code-csharp[22_IteratorMethodLocal](~/samples/snippets/csharp/new-in-7/Iterator.cs#IteratorMethodLocal "Iterator method with local function")]

<span data-ttu-id="92a20-237">可以对 `async` 方法采用相同的技术，以确保在异步工作开始之前引发由参数验证引起的异常：</span><span class="sxs-lookup"><span data-stu-id="92a20-237">The same technique can be employed with `async` methods to ensure that exceptions arising from argument validation are thrown before the asynchronous work begins:</span></span>

[!code-csharp[TaskExample](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

> [!NOTE]
> <span data-ttu-id="92a20-238">本地函数支持的某些设计也可以使用 lambda 表达式来完成。</span><span class="sxs-lookup"><span data-stu-id="92a20-238">Some of the designs that are supported by local functions could also be accomplished using *lambda expressions*.</span></span> <span data-ttu-id="92a20-239">感兴趣的人可以[阅读有关差异的详细信息](../local-functions-vs-lambdas.md)</span><span class="sxs-lookup"><span data-stu-id="92a20-239">Those interested can [read more about the differences](../local-functions-vs-lambdas.md)</span></span>

## <a name="more-expression-bodied-members"></a><span data-ttu-id="92a20-240">更多的 expression-bodied 成员</span><span class="sxs-lookup"><span data-stu-id="92a20-240">More expression-bodied members</span></span>

<span data-ttu-id="92a20-241">C# 6 为成员函数和只读属性引入了 [expression-bodied 成员](csharp-6.md#expression-bodied-function-members)。</span><span class="sxs-lookup"><span data-stu-id="92a20-241">C# 6 introduced [expression-bodied members](csharp-6.md#expression-bodied-function-members) for member functions, and read-only properties.</span></span> <span data-ttu-id="92a20-242">C# 7.0 扩展了可作为表达式实现的允许的成员。</span><span class="sxs-lookup"><span data-stu-id="92a20-242">C# 7.0 expands the allowed members that can be implemented as expressions.</span></span> <span data-ttu-id="92a20-243">在 C# 7.0 中，你可以在属性和索引器上实现构造函数、终结器以及 `get` 和 `set` 访问器。</span><span class="sxs-lookup"><span data-stu-id="92a20-243">In C# 7.0, you can implement *constructors*, *finalizers*, and `get` and `set` accessors on *properties* and *indexers*.</span></span> <span data-ttu-id="92a20-244">以下代码演示了每种情况的示例：</span><span class="sxs-lookup"><span data-stu-id="92a20-244">The following code shows examples of each:</span></span>

[!code-csharp[ExpressionBodiedMembers](~/samples/snippets/csharp/new-in-7/expressionmembers.cs#ExpressionBodiedEverything "new expression-bodied members")]

> [!NOTE]
> <span data-ttu-id="92a20-245">本示例不需要终结器，但显示它是为了演示语法。</span><span class="sxs-lookup"><span data-stu-id="92a20-245">This example does not need a finalizer, but it is shown to demonstrate the syntax.</span></span> <span data-ttu-id="92a20-246">不应在类中实现终结器，除非有必要发布非托管资源。</span><span class="sxs-lookup"><span data-stu-id="92a20-246">You should not implement a finalizer in your class unless it is necessary to  release unmanaged resources.</span></span> <span data-ttu-id="92a20-247">还应考虑使用 <xref:System.Runtime.InteropServices.SafeHandle> 类，而不是直接管理非托管资源。</span><span class="sxs-lookup"><span data-stu-id="92a20-247">You should also consider using the <xref:System.Runtime.InteropServices.SafeHandle> class instead of managing unmanaged resources directly.</span></span>

<span data-ttu-id="92a20-248">这些 expression-bodied 成员的新位置代表了 C# 语言的一个重要里程碑：这些功能由致力于开发开放源代码 [Roslyn](https://github.com/dotnet/Roslyn) 项目的社区成员实现。</span><span class="sxs-lookup"><span data-stu-id="92a20-248">These new locations for expression-bodied members represent an important milestone for the C# language: These features were implemented by community members working on the open-source [Roslyn](https://github.com/dotnet/Roslyn) project.</span></span>

<span data-ttu-id="92a20-249">将方法更改为 expression bodied 成员是[二进制兼容的更改](version-update-considerations.md#binary-compatible-changes)。</span><span class="sxs-lookup"><span data-stu-id="92a20-249">Changing a method to an expression bodied member is a [binary compatible change](version-update-considerations.md#binary-compatible-changes).</span></span>

## <a name="throw-expressions"></a><span data-ttu-id="92a20-250">引发表达式</span><span class="sxs-lookup"><span data-stu-id="92a20-250">Throw expressions</span></span>

<span data-ttu-id="92a20-251">在 C# 中，`throw` 始终是一个语句。</span><span class="sxs-lookup"><span data-stu-id="92a20-251">In C#, `throw` has always been a statement.</span></span> <span data-ttu-id="92a20-252">因为 `throw` 是一个语句而非表达式，所以在某些 C# 构造中无法使用它。</span><span class="sxs-lookup"><span data-stu-id="92a20-252">Because `throw` is a statement, not an expression, there were C# constructs where you couldn't use it.</span></span> <span data-ttu-id="92a20-253">它们包括条件表达式、null 合并表达式和一些 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="92a20-253">These included conditional expressions, null coalescing expressions, and some lambda expressions.</span></span> <span data-ttu-id="92a20-254">添加 expression-bodied 成员将添加更多位置，在这些位置中，`throw` 表达式会很有用。</span><span class="sxs-lookup"><span data-stu-id="92a20-254">The addition of expression-bodied members adds more locations where `throw` expressions would be useful.</span></span> <span data-ttu-id="92a20-255">为了可以编写任何这些构造，C# 7.0 引入了引发表达式。</span><span class="sxs-lookup"><span data-stu-id="92a20-255">So that you can write any of these constructs, C# 7.0 introduces *throw expressions*.</span></span>

<span data-ttu-id="92a20-256">这使得编写更多基于表达式的代码变得更容易。</span><span class="sxs-lookup"><span data-stu-id="92a20-256">This addition makes it easier to write more expression-based code.</span></span> <span data-ttu-id="92a20-257">不需要其他语句来进行错误检查。</span><span class="sxs-lookup"><span data-stu-id="92a20-257">You don't need additional statements for error checking.</span></span>

## <a name="generalized-async-return-types"></a><span data-ttu-id="92a20-258">通用的异步返回类型</span><span class="sxs-lookup"><span data-stu-id="92a20-258">Generalized async return types</span></span>

<span data-ttu-id="92a20-259">从异步方法返回 `Task` 对象可能在某些路径中导致性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="92a20-259">Returning a `Task` object from async methods can introduce performance bottlenecks in certain paths.</span></span> <span data-ttu-id="92a20-260">`Task` 是引用类型，因此使用它意味着分配对象。</span><span class="sxs-lookup"><span data-stu-id="92a20-260">`Task` is a reference type, so using it means allocating an object.</span></span> <span data-ttu-id="92a20-261">如果使用 `async` 修饰符声明的方法返回缓存结果或以同步方式完成，那么额外的分配在代码的性能关键部分可能要耗费相当长的时间。</span><span class="sxs-lookup"><span data-stu-id="92a20-261">In cases where a method declared with the `async` modifier returns a cached result, or completes synchronously, the extra allocations can become a significant time cost in performance critical sections of code.</span></span> <span data-ttu-id="92a20-262">如果这些分配发生在紧凑循环中，则成本会变高。</span><span class="sxs-lookup"><span data-stu-id="92a20-262">It can become costly if those allocations occur in tight loops.</span></span>

<span data-ttu-id="92a20-263">新语言功能意味着异步方法返回类型不限于 `Task`、`Task<T>` 和 `void`。</span><span class="sxs-lookup"><span data-stu-id="92a20-263">The new language feature means that async method return types aren't limited to `Task`, `Task<T>`, and `void`.</span></span> <span data-ttu-id="92a20-264">返回类型必须仍满足异步模式，这意味着 `GetAwaiter` 方法必须是可访问的。</span><span class="sxs-lookup"><span data-stu-id="92a20-264">The returned type must still satisfy the async pattern, meaning a `GetAwaiter` method must be accessible.</span></span> <span data-ttu-id="92a20-265">作为一个具体示例，已将 `ValueTask` 类型添加到 .NET framework 中，以使用这一新语言功能：</span><span class="sxs-lookup"><span data-stu-id="92a20-265">As one concrete example, the `ValueTask` type has been added to the .NET framework to make use of this new language feature:</span></span>

[!code-csharp[UsingValueTask](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#UsingValueTask "Using ValueTask")]

> [!NOTE]
> <span data-ttu-id="92a20-266">需要添加 NuGet 包 [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) 才能使用 <xref:System.Threading.Tasks.ValueTask%601> 类型。</span><span class="sxs-lookup"><span data-stu-id="92a20-266">You need to add the NuGet package [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) in order to use the <xref:System.Threading.Tasks.ValueTask%601> type.</span></span>

<span data-ttu-id="92a20-267">此增强功能对于库作者最有用，可避免在性能关键型代码中分配 `Task`。</span><span class="sxs-lookup"><span data-stu-id="92a20-267">This enhancement is most useful for library authors to avoid allocating a `Task` in performance critical code.</span></span>

## <a name="numeric-literal-syntax-improvements"></a><span data-ttu-id="92a20-268">数字文本语法改进</span><span class="sxs-lookup"><span data-stu-id="92a20-268">Numeric literal syntax improvements</span></span>

<span data-ttu-id="92a20-269">误读的数值常量可能使第一次阅读代码时更难理解。</span><span class="sxs-lookup"><span data-stu-id="92a20-269">Misreading numeric constants can make it harder to understand code when reading it for the first time.</span></span> <span data-ttu-id="92a20-270">位掩码或其他符号值容易产生误解。</span><span class="sxs-lookup"><span data-stu-id="92a20-270">Bit masks or other symbolic values are prone to misunderstanding.</span></span> <span data-ttu-id="92a20-271">C# 7.0 包括两项新功能，可用于以最可读的方式写入数字来用于预期用途：二进制文本和数字分隔符。</span><span class="sxs-lookup"><span data-stu-id="92a20-271">C# 7.0 includes two new features to write numbers in the most readable fashion for the intended use: *binary literals*, and *digit separators*.</span></span>

<span data-ttu-id="92a20-272">在创建位掩码时，或每当数字的二进制表示形式使代码最具可读性时，以二进制形式写入该数字：</span><span class="sxs-lookup"><span data-stu-id="92a20-272">For those times when you're creating bit masks, or whenever a binary representation of a number makes the most readable code, write that number in binary:</span></span>

[!code-csharp[ThousandSeparators](~/samples/snippets/csharp/new-in-7/Program.cs#ThousandSeparators "Thousands separators")]

<span data-ttu-id="92a20-273">常量开头的 `0b` 表示该数字以二进制数形式写入。</span><span class="sxs-lookup"><span data-stu-id="92a20-273">The `0b` at the beginning of the constant indicates that the number is written as a binary number.</span></span> <span data-ttu-id="92a20-274">二进制数可能会很长，因此通过引入 `_` 作为数字分隔符通常更易于查看位模式，如上面二进制常量所示。</span><span class="sxs-lookup"><span data-stu-id="92a20-274">Binary numbers can get long, so it's often easier to see the bit patterns by introducing the `_` as a digit separator, as shown above in the binary constant.</span></span> <span data-ttu-id="92a20-275">数字分隔符可以出现在常量的任何位置。</span><span class="sxs-lookup"><span data-stu-id="92a20-275">The digit separator can appear anywhere in the constant.</span></span> <span data-ttu-id="92a20-276">对于十进制数字，通常将其用作千位分隔符：</span><span class="sxs-lookup"><span data-stu-id="92a20-276">For base 10 numbers, it is common to use it as a thousands separator:</span></span>

[!code-csharp[LargeIntegers](~/samples/snippets/csharp/new-in-7/Program.cs#LargeIntegers "Large integer")]

<span data-ttu-id="92a20-277">数字分隔符也可以与 `decimal`、`float` 和 `double` 类型一起使用：</span><span class="sxs-lookup"><span data-stu-id="92a20-277">The digit separator can be used with `decimal`, `float`, and `double` types as well:</span></span>

[!code-csharp[OtherConstants](~/samples/snippets/csharp/new-in-7/Program.cs#OtherConstants "non-integral constants")]

<span data-ttu-id="92a20-278">综观来说，你可以声明可读性更强的数值常量。</span><span class="sxs-lookup"><span data-stu-id="92a20-278">Taken together, you can declare numeric constants with much more readability.</span></span>
