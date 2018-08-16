---
title: C# 7.0 中的新增功能 - C# 指南
description: 大致了解 C# 语言即将发布的版本 7 中将推出的新功能。
ms.date: 12/21/2016
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: a78b30411d734d6dadc52b7dbd402763d4eb7f5e
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
ms.locfileid: "33956404"
---
# <a name="whats-new-in-c-70"></a><span data-ttu-id="899d9-103">C# 7.0 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="899d9-103">What's new in C# 7.0</span></span>

<span data-ttu-id="899d9-104">C# 7.0 向 C# 语言添加了许多新功能：</span><span class="sxs-lookup"><span data-stu-id="899d9-104">C# 7.0 adds a number of new features to the C# language:</span></span>
* [<span data-ttu-id="899d9-105">`out` 变量</span><span class="sxs-lookup"><span data-stu-id="899d9-105">`out` variables</span></span>](#out-variables)
    - <span data-ttu-id="899d9-106">可以将 `out` 值内联作为参数声明到使用这些参数的方法中。</span><span class="sxs-lookup"><span data-stu-id="899d9-106">You can declare `out` values inline as arguments to the method where they are used.</span></span>
* [<span data-ttu-id="899d9-107">元组</span><span class="sxs-lookup"><span data-stu-id="899d9-107">Tuples</span></span>](#tuples)
    - <span data-ttu-id="899d9-108">可以创建包含多个公共字段的轻量级未命名类型。</span><span class="sxs-lookup"><span data-stu-id="899d9-108">You can create lightweight, unnamed types that contain multiple public fields.</span></span> <span data-ttu-id="899d9-109">编译器和 IDE 工具可理解这些类型的语义。</span><span class="sxs-lookup"><span data-stu-id="899d9-109">Compilers and IDE tools understand the semantics of these types.</span></span>
* [<span data-ttu-id="899d9-110">弃元</span><span class="sxs-lookup"><span data-stu-id="899d9-110">Discards</span></span>](#discards)
    - <span data-ttu-id="899d9-111">弃元是指在不关心所赋予的值时，赋值中使用的临时只写变量。</span><span class="sxs-lookup"><span data-stu-id="899d9-111">Discards are temporary, write-only variables used in assignments when you don't care about the value assigned.</span></span> <span data-ttu-id="899d9-112">在对元组和用户定义类型进行解构，以及在使用 `out` 参数调用方法时，它们特别有用。</span><span class="sxs-lookup"><span data-stu-id="899d9-112">They are particularly useful when deconstructing tuples and user-defined types, as well as when calling methods with `out` parameters.</span></span>
* [<span data-ttu-id="899d9-113">模式匹配</span><span class="sxs-lookup"><span data-stu-id="899d9-113">Pattern Matching</span></span>](#pattern-matching)
    - <span data-ttu-id="899d9-114">可以基于任意类型和这些类型的成员的值创建分支逻辑。</span><span class="sxs-lookup"><span data-stu-id="899d9-114">You can create branching logic based on arbitrary types and values of the members of those types.</span></span>
* [<span data-ttu-id="899d9-115">`ref` 局部变量和返回结果</span><span class="sxs-lookup"><span data-stu-id="899d9-115">`ref` locals and returns</span></span>](#ref-locals-and-returns)
    - <span data-ttu-id="899d9-116">方法参数和局部变量可以是对其他存储的引用。</span><span class="sxs-lookup"><span data-stu-id="899d9-116">Method arguments and local variables can be references to other storage.</span></span>
* [<span data-ttu-id="899d9-117">本地函数</span><span class="sxs-lookup"><span data-stu-id="899d9-117">Local Functions</span></span>](#local-functions)
    - <span data-ttu-id="899d9-118">可以将函数嵌套在其他函数内，以限制其范围和可见性。</span><span class="sxs-lookup"><span data-stu-id="899d9-118">You can nest functions inside other functions to limit their scope and visibility.</span></span>
* [<span data-ttu-id="899d9-119">更多的 expression-bodied 成员</span><span class="sxs-lookup"><span data-stu-id="899d9-119">More expression-bodied members</span></span>](#more-expression-bodied-members)
    - <span data-ttu-id="899d9-120">可使用表达式创作的成员列表有所增长。</span><span class="sxs-lookup"><span data-stu-id="899d9-120">The list of members that can be authored using expressions has grown.</span></span>
* [<span data-ttu-id="899d9-121">`throw` 表达式</span><span class="sxs-lookup"><span data-stu-id="899d9-121">`throw` Expressions</span></span>](#throw-expressions)
    - <span data-ttu-id="899d9-122">可以在之前因为 `throw` 是语句而不被允许的代码构造中引发异常。</span><span class="sxs-lookup"><span data-stu-id="899d9-122">You can throw exceptions in code constructs that previously were not allowed because `throw` was a statement.</span></span> 
* [<span data-ttu-id="899d9-123">通用的异步返回类型</span><span class="sxs-lookup"><span data-stu-id="899d9-123">Generalized async return types</span></span>](#generalized-async-return-types)
    - <span data-ttu-id="899d9-124">使用 `async` 修饰符声明的方法可以返回除 `Task` 和 `Task<T>` 以外的其他类型。</span><span class="sxs-lookup"><span data-stu-id="899d9-124">Methods declared with the `async` modifier can return other types in addition to `Task` and `Task<T>`.</span></span>
* [<span data-ttu-id="899d9-125">数字文本语法改进</span><span class="sxs-lookup"><span data-stu-id="899d9-125">Numeric literal syntax improvements</span></span>](#numeric-literal-syntax-improvements)
    - <span data-ttu-id="899d9-126">新令牌可提高数值常量的可读性。</span><span class="sxs-lookup"><span data-stu-id="899d9-126">New tokens improve readability for numeric constants.</span></span>

<span data-ttu-id="899d9-127">本主题的其余部分讨论了每项功能。</span><span class="sxs-lookup"><span data-stu-id="899d9-127">The remainder of this topic discusses each of the features.</span></span> <span data-ttu-id="899d9-128">你将了解每项功能背后的原理。</span><span class="sxs-lookup"><span data-stu-id="899d9-128">For each feature, you'll learn the reasoning behind it.</span></span> <span data-ttu-id="899d9-129">将了解语法。</span><span class="sxs-lookup"><span data-stu-id="899d9-129">You'll learn the syntax.</span></span> <span data-ttu-id="899d9-130">将看到一些示例方案，从中可看出使用新功能将提高你作为开发人员的工作效率。</span><span class="sxs-lookup"><span data-stu-id="899d9-130">You'll see some sample scenarios where using the new feature will make you more productive as a developer.</span></span> 

## <a name="out-variables"></a><span data-ttu-id="899d9-131">`out` 变量</span><span class="sxs-lookup"><span data-stu-id="899d9-131">`out` variables</span></span>

<span data-ttu-id="899d9-132">支持 `out` 参数的现有语法已在此版本中得到改进。</span><span class="sxs-lookup"><span data-stu-id="899d9-132">The existing syntax that supports `out` parameters has been improved in this version.</span></span>  

<span data-ttu-id="899d9-133">以前，你需要将 out 变量的声明及其初始化分为两个不同的语句：</span><span class="sxs-lookup"><span data-stu-id="899d9-133">Previously, you would need to separate the declaration of the out variable and its initialization into two different statements:</span></span>

[!code-csharp[OutVariableOldStyle](../../../samples/snippets/csharp/new-in-7/program.cs#03_OutVariableOldStyle "classic out variable declaration")]

<span data-ttu-id="899d9-134">现在可以在方法调用的参数列表中声明 `out` 变量，而不是编写单独的声明语句：</span><span class="sxs-lookup"><span data-stu-id="899d9-134">You can now declare `out` variables in the argument list of a method call, rather than writing a separate declaration statement:</span></span>

[!code-csharp[OutVariableDeclarations](../../../samples/snippets/csharp/new-in-7/program.cs#01_OutVariableDeclarations "Out variable declarations")]

<span data-ttu-id="899d9-135">为清晰明了，可能需指定 `out` 变量的类型，如上所示。</span><span class="sxs-lookup"><span data-stu-id="899d9-135">You may want to specify the type of the `out` variable for clarity, as shown above.</span></span> <span data-ttu-id="899d9-136">但是，该语言不支持使用隐式类型的局部变量：</span><span class="sxs-lookup"><span data-stu-id="899d9-136">However, the language does support using an implicitly typed local variable:</span></span>

[!code-csharp[OutVarVariableDeclarations](../../../samples/snippets/csharp/new-in-7/program.cs#02_OutVarVariableDeclarations "Implicitly typed Out variable")]

* <span data-ttu-id="899d9-137">代码更易于阅读。</span><span class="sxs-lookup"><span data-stu-id="899d9-137">The code is easier to read.</span></span> 
    - <span data-ttu-id="899d9-138">在使用 out 变量的地方声明 out 变量，而不是在上面的另一行。</span><span class="sxs-lookup"><span data-stu-id="899d9-138">You declare the out variable where you use it, not on another line above.</span></span>
* <span data-ttu-id="899d9-139">无需分配初始值。</span><span class="sxs-lookup"><span data-stu-id="899d9-139">No need to assign an initial value.</span></span>
    - <span data-ttu-id="899d9-140">通过在方法调用中使用 `out` 变量的位置声明该变量，使得在分配它之前不可能意外使用它。</span><span class="sxs-lookup"><span data-stu-id="899d9-140">By declaring the `out` variable where it is used in a method call, you can't accidentally use it before it is assigned.</span></span>

<span data-ttu-id="899d9-141">此功能最常见的用法是 `Try` 模式。</span><span class="sxs-lookup"><span data-stu-id="899d9-141">The most common use for this feature will be the `Try` pattern.</span></span> <span data-ttu-id="899d9-142">在此模式下，方法返回指示成功或失败的 `bool`，如果方法成功，则还返回提供结果的 `out` 变量。</span><span class="sxs-lookup"><span data-stu-id="899d9-142">In this pattern, a method returns a `bool` indicating success or failure and an `out` variable that provides the result if the method succeeds.</span></span>

<span data-ttu-id="899d9-143">当使用 `out` 变量声明时，声明的变量“泄漏”到 if 语句的外部作用域。</span><span class="sxs-lookup"><span data-stu-id="899d9-143">When using the `out` variable declaration, the declared variable "leaks" into the outer scope of the if statement.</span></span> <span data-ttu-id="899d9-144">这让你可以在之后使用该变量：</span><span class="sxs-lookup"><span data-stu-id="899d9-144">This allows you to use the variable afterwards:</span></span>

```csharp
if (!int.TryParse(input, out int result))
{    
    return null;
}

return result;
```

## <a name="tuples"></a><span data-ttu-id="899d9-145">元组</span><span class="sxs-lookup"><span data-stu-id="899d9-145">Tuples</span></span>

> [!NOTE]
> <span data-ttu-id="899d9-146">新的元组功能需要 <xref:System.ValueTuple> 类型。</span><span class="sxs-lookup"><span data-stu-id="899d9-146">The new tuples features require the <xref:System.ValueTuple> types.</span></span>
> <span data-ttu-id="899d9-147">为在不包括该类型的平台上使用它，必须添加 NuGet 包 [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/)。</span><span class="sxs-lookup"><span data-stu-id="899d9-147">You must add the NuGet package [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) in order to use it on platforms that do not include the types.</span></span>
>
> <span data-ttu-id="899d9-148">这类似于依赖框架提供的类型的其他语言功能。</span><span class="sxs-lookup"><span data-stu-id="899d9-148">This is similar to other language features that rely on types delivered in the framework.</span></span> <span data-ttu-id="899d9-149">例如，依赖 `INotifyCompletion` 接口的 `async` 和 `await`，以及依赖 `IEnumerable<T>` 的 LINQ。</span><span class="sxs-lookup"><span data-stu-id="899d9-149">Example include `async` and `await` relying on the `INotifyCompletion` interface, and LINQ relying on `IEnumerable<T>`.</span></span> <span data-ttu-id="899d9-150">但是，随着 .NET 越来越不依赖平台，交付机制也在发生改变。</span><span class="sxs-lookup"><span data-stu-id="899d9-150">However, the delivery mechanism is changing as .NET is becoming more platform independent.</span></span> <span data-ttu-id="899d9-151">.NET Framework 交付频率可能不会与语言编译器的始终相同。</span><span class="sxs-lookup"><span data-stu-id="899d9-151">The .NET Framework may not always ship on the same cadence as the language compiler.</span></span> <span data-ttu-id="899d9-152">新语言功能依赖于新类型时，这些类型将在交付语言功能时以 NuGet 包的形式提供。</span><span class="sxs-lookup"><span data-stu-id="899d9-152">When new language features rely on new types, those types will be available as NuGet packages when the language features ship.</span></span> <span data-ttu-id="899d9-153">这些新类型添加到 .NET Standard API 并作为框架的一部分交付后，将删除 NuGet 包要求。</span><span class="sxs-lookup"><span data-stu-id="899d9-153">As these new types get added to the .NET Standard API and delivered as part of the framework, the NuGet package requirement will be removed.</span></span>

<span data-ttu-id="899d9-154">C# 为用于说明设计意图的类和结构提供了丰富的语法。</span><span class="sxs-lookup"><span data-stu-id="899d9-154">C# provides a rich syntax for classes and structs that is used to explain your design intent.</span></span> <span data-ttu-id="899d9-155">但是，这种丰富的语法有时会需要额外的工作，但益处却很少。</span><span class="sxs-lookup"><span data-stu-id="899d9-155">But sometimes that rich syntax requires extra work with minimal benefit.</span></span> <span data-ttu-id="899d9-156">你可能经常编写需要包含多个数据元素的简单结构的方法。</span><span class="sxs-lookup"><span data-stu-id="899d9-156">You may often write methods that need a simple structure containing more than one data element.</span></span> <span data-ttu-id="899d9-157">为了支持这些方案，已将元组添加到了 C#。</span><span class="sxs-lookup"><span data-stu-id="899d9-157">To support these scenarios *tuples* were added to C#.</span></span> <span data-ttu-id="899d9-158">元组是包含多个字段以表示数据成员的轻量级数据结构。</span><span class="sxs-lookup"><span data-stu-id="899d9-158">Tuples are lightweight data structures that contain multiple fields to represent the data members.</span></span>
<span data-ttu-id="899d9-159">这些字段没有经过验证，并且你无法定义自己的方法</span><span class="sxs-lookup"><span data-stu-id="899d9-159">The fields are not validated, and you cannot define your own methods</span></span>

> [!NOTE]
> <span data-ttu-id="899d9-160">低于 C# 7.0 的版本中也提供元组，但它们效率低下且不具有语言支持。</span><span class="sxs-lookup"><span data-stu-id="899d9-160">Tuples were available before C# 7.0, but they were inefficient and had no language support.</span></span>
> <span data-ttu-id="899d9-161">这意味着元组元素只能作为 `Item1` 和 `Item2` 等引用。</span><span class="sxs-lookup"><span data-stu-id="899d9-161">This meant that tuple elements could only be referenced as `Item1`, `Item2` and so on.</span></span> <span data-ttu-id="899d9-162">C# 7.0 引入了对元组的语言支持，可利用更有效的新元组类型向元组字段赋予语义名称。</span><span class="sxs-lookup"><span data-stu-id="899d9-162">C# 7.0 introduces language support for tuples, which enables semantic names for the fields of a tuple using new, more efficient tuple types.</span></span>

<span data-ttu-id="899d9-163">通过为每个成员赋值，可以创建一个元组：</span><span class="sxs-lookup"><span data-stu-id="899d9-163">You can create a tuple by assigning a value to each member:</span></span>

[!code-csharp[UnnamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#04_UnnamedTuple "Unnamed tuple")]

<span data-ttu-id="899d9-164">此赋值会创建其成员为 `Item1` 和 `Item2` 的元组，其使用方式与 <xref:System.Tuple> 的相同。可更改语法，以创建为每个元组成员提供语义名称的元组：</span><span class="sxs-lookup"><span data-stu-id="899d9-164">That assignment creates a tuple whose members are `Item1` and `Item2`, which you can use in the same way as <xref:System.Tuple> You can change the syntax to create a tuple that provides semantic names to each of the members of the tuple:</span></span>

[!code-csharp[NamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#05_NamedTuple "Named tuple")]

<span data-ttu-id="899d9-165">`namedLetters` 元组包含称为 `Alpha` 和 `Beta` 的字段。</span><span class="sxs-lookup"><span data-stu-id="899d9-165">The `namedLetters` tuple contains fields referred to as `Alpha` and `Beta`.</span></span> <span data-ttu-id="899d9-166">这些名称仅存在于编译时且不保留，例如在运行时使用反射来检查元组时。</span><span class="sxs-lookup"><span data-stu-id="899d9-166">Those names exist only at compile time and are not preserved for example when inspecting the tuple using reflection at runtime.</span></span>

<span data-ttu-id="899d9-167">在进行元组赋值时，还可以指定赋值右侧的字段的名称：</span><span class="sxs-lookup"><span data-stu-id="899d9-167">In a tuple assignment, you can also specify the names of the fields on the right-hand side of the assignment:</span></span>

[!code-csharp[ImplicitNamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#06_ImplicitNamedTuple "Implicitly named tuple")]

<span data-ttu-id="899d9-168">可指定赋值左侧和右侧字段的名称：</span><span class="sxs-lookup"><span data-stu-id="899d9-168">You can specify names for the fields on both the left and right-hand side of the assignment:</span></span>

[!code-csharp[NamedTupleConflict](../../../samples/snippets/csharp/new-in-7/program.cs#07_NamedTupleConflict "Named tuple conflict")]

<span data-ttu-id="899d9-169">上面的行会生成警告 `CS8123`，告知你赋值右侧的名称 `Alpha` 和 `Beta` 将被忽略，因为它们与左侧的名称 `First` 和 `Second` 冲突。</span><span class="sxs-lookup"><span data-stu-id="899d9-169">The line above generates a warning, `CS8123`, telling you that the names on the right side of the assignment, `Alpha` and `Beta` are ignored because they conflict with the names on the left side, `First` and `Second`.</span></span>

<span data-ttu-id="899d9-170">上面的示例演示了用于声明元组的基本语法。</span><span class="sxs-lookup"><span data-stu-id="899d9-170">The examples above show the basic syntax to declare tuples.</span></span> <span data-ttu-id="899d9-171">元组在作为 `private` 和 `internal` 方法的返回类型时是最有用的。</span><span class="sxs-lookup"><span data-stu-id="899d9-171">Tuples are most useful as return types for `private` and `internal` methods.</span></span> <span data-ttu-id="899d9-172">元组为这些方法提供了简单的语法以返回多个离散值：不用再费心创作定义返回类型的 `class` 或 `struct`。</span><span class="sxs-lookup"><span data-stu-id="899d9-172">Tuples provide a simple syntax for those methods to return multiple discrete values: You save the work of authoring a `class` or a `struct` that defines the type returned.</span></span> <span data-ttu-id="899d9-173">无需创建新类型。</span><span class="sxs-lookup"><span data-stu-id="899d9-173">There is no need for creating a new type.</span></span>

<span data-ttu-id="899d9-174">创建元组更有效且更高效。</span><span class="sxs-lookup"><span data-stu-id="899d9-174">Creating a tuple is more efficient and more productive.</span></span>
<span data-ttu-id="899d9-175">它是一种更简单的轻量级语法，用于定义携带多个值的数据结构。</span><span class="sxs-lookup"><span data-stu-id="899d9-175">It is a simpler, lightweight syntax to define a data structure that carries more than one value.</span></span> <span data-ttu-id="899d9-176">下面的示例方法返回在一个整数序列中找到的最小值和最大值：</span><span class="sxs-lookup"><span data-stu-id="899d9-176">The example method below returns the minimum and maximum values found in a sequence of integers:</span></span>

[!code-csharp[TupleReturningMethod](../../../samples/snippets/csharp/new-in-7/program.cs#08_TupleReturningMethod "Tuple returning method")]

<span data-ttu-id="899d9-177">以这种方式使用元组有若干优点：</span><span class="sxs-lookup"><span data-stu-id="899d9-177">Using tuples in this way offers several advantages:</span></span>

* <span data-ttu-id="899d9-178">不用再费心创作定义返回类型的 `class` 或 `struct`。</span><span class="sxs-lookup"><span data-stu-id="899d9-178">You save the work of authoring a `class` or a `struct` that defines the type returned.</span></span> 
* <span data-ttu-id="899d9-179">无需创建新类型。</span><span class="sxs-lookup"><span data-stu-id="899d9-179">You do not need to create new type.</span></span>
* <span data-ttu-id="899d9-180">借助该语言增强功能，无需调用 <xref:System.Tuple.Create``1(``0)> 方法。</span><span class="sxs-lookup"><span data-stu-id="899d9-180">The language enhancements removes the need to call the <xref:System.Tuple.Create``1(``0)> methods.</span></span>

<span data-ttu-id="899d9-181">此方法的声明提供返回的元组的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="899d9-181">The declaration for the method provides the names for the fields of the tuple that is returned.</span></span> <span data-ttu-id="899d9-182">调用该方法时，返回值是字段为 `Max` 和`Min` 的元组：</span><span class="sxs-lookup"><span data-stu-id="899d9-182">When you call the method, the return value is a tuple whose fields are `Max` and `Min`:</span></span>

[!code-csharp[CallingTupleMethod](../../../samples/snippets/csharp/new-in-7/program.cs#09_CallingTupleMethod "Calling a tuple returning method")]

<span data-ttu-id="899d9-183">在某些时候，你可能想要解包从方法返回的元组的成员。</span><span class="sxs-lookup"><span data-stu-id="899d9-183">There may be times when you want to unpackage the members of a tuple that were returned from a method.</span></span>  <span data-ttu-id="899d9-184">可通过为元组中的每个值声明单独的变量来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="899d9-184">You can do that by declaring separate variables for each of the values in the tuple.</span></span> <span data-ttu-id="899d9-185">这称为析构元组：</span><span class="sxs-lookup"><span data-stu-id="899d9-185">This is called *deconstructing* the tuple:</span></span>

[!code-csharp[CallingWithDeconstructor](../../../samples/snippets/csharp/new-in-7/program.cs#10_CallingWithDeconstructor "Deconstructing a tuple")]

<span data-ttu-id="899d9-186">还可以为 .NET 中的任何类型提供类似的析构。</span><span class="sxs-lookup"><span data-stu-id="899d9-186">You can also provide a similar deconstruction for any type in .NET.</span></span> <span data-ttu-id="899d9-187">这通过将 `Deconstruct` 方法编写为类的成员来完成。</span><span class="sxs-lookup"><span data-stu-id="899d9-187">This is done by writing a `Deconstruct` method as a member of the class.</span></span> <span data-ttu-id="899d9-188">`Deconstruct` 方法为你要提取的每个属性提供一组 `out` 参数。</span><span class="sxs-lookup"><span data-stu-id="899d9-188">That `Deconstruct` method provides a set of `out` arguments for each of the properties you want to extract.</span></span> <span data-ttu-id="899d9-189">考虑提供析构函数方法的此 `Point` 类，该方法提取 `X` 和 `Y` 坐标：</span><span class="sxs-lookup"><span data-stu-id="899d9-189">Consider this `Point` class that provides a deconstructor method that extracts the `X` and `Y` coordinates:</span></span>

[!code-csharp[PointWithDeconstruction](../../../samples/snippets/csharp/new-in-7/point.cs#11_PointWithDeconstruction "Point with deconstruction method")]
 
<span data-ttu-id="899d9-190">可以通过向元组分配 `Point` 来提取各个字段：</span><span class="sxs-lookup"><span data-stu-id="899d9-190">You can extract the individual fields by assigning a `Point` to a tuple:</span></span>

[!code-csharp[DeconstructPoint](../../../samples/snippets/csharp/new-in-7/program.cs#12_DeconstructPoint "Deconstruct a point")]

<span data-ttu-id="899d9-191">不会受到 `Deconstruct` 方法中定义的名称的约束。</span><span class="sxs-lookup"><span data-stu-id="899d9-191">You are not bound by the names defined in the `Deconstruct` method.</span></span> <span data-ttu-id="899d9-192">可以在分配过程中重命名提取变量：</span><span class="sxs-lookup"><span data-stu-id="899d9-192">You can rename the extract variables as part of the assignment:</span></span>  

[!code-csharp[DeconstructNames](../../../samples/snippets/csharp/new-in-7/program.cs#13_DeconstructNames "Deconstruct with new names")]

<span data-ttu-id="899d9-193">可在[元组主题](../tuples.md)中深入了解有关元组的详细信息。</span><span class="sxs-lookup"><span data-stu-id="899d9-193">You can learn more in depth about tuples in the [tuples topic](../tuples.md).</span></span>

## <a name="discards"></a><span data-ttu-id="899d9-194">弃元</span><span class="sxs-lookup"><span data-stu-id="899d9-194">Discards</span></span>

<span data-ttu-id="899d9-195">通常，在进行元组解构或使用 `out` 参数调用方法时，必须定义一个其值无关紧要且你不打算使用的变量。</span><span class="sxs-lookup"><span data-stu-id="899d9-195">Often when deconstructing a tuple or calling a method with `out` parameters, you're forced to define a variable whose value you don't care about and don't intend to use.</span></span> <span data-ttu-id="899d9-196">为处理此情况，C# 增添了对弃元的支持。</span><span class="sxs-lookup"><span data-stu-id="899d9-196">C# adds support for *discards* to handle this scenario.</span></span> <span data-ttu-id="899d9-197">弃元是一个名为 `_`（下划线字符）的只写变量，可向单个变量赋予要放弃的所有值。</span><span class="sxs-lookup"><span data-stu-id="899d9-197">A discard is a write-only variable whose name is `_` (the underscore character); you can assign all of the values that you intend to discard to the single variable.</span></span> <span data-ttu-id="899d9-198">弃元类似于未赋值的变量；不可在代码中使用弃元（赋值语句除外）。</span><span class="sxs-lookup"><span data-stu-id="899d9-198">A discard is like an unassigned variable; apart from the assignment statement, the discard can't be used in code.</span></span>

<span data-ttu-id="899d9-199">在以下方案中支持弃元：</span><span class="sxs-lookup"><span data-stu-id="899d9-199">Discards are supported in the following scenarios:</span></span>

* <span data-ttu-id="899d9-200">在对元组或用户定义的类型进行解构时。</span><span class="sxs-lookup"><span data-stu-id="899d9-200">When deconstructing tuples or user-defined types.</span></span>

* <span data-ttu-id="899d9-201">在使用 [out](../language-reference/keywords/out-parameter-modifier.md) 参数调用方法时。</span><span class="sxs-lookup"><span data-stu-id="899d9-201">When calling methods with [out](../language-reference/keywords/out-parameter-modifier.md) parameters.</span></span>

* <span data-ttu-id="899d9-202">在使用 [is](../language-reference/keywords/is.md) 和 [switch](../language-reference/keywords/switch.md) 语句匹配操作的模式中。</span><span class="sxs-lookup"><span data-stu-id="899d9-202">In a pattern matching operation with the [is](../language-reference/keywords/is.md) and [switch](../language-reference/keywords/switch.md) statements.</span></span>

* <span data-ttu-id="899d9-203">在要将某赋值的值显式标识为弃元时用作独立标识符。</span><span class="sxs-lookup"><span data-stu-id="899d9-203">As a standalone identifier when you want to explicitly identify the value of an assignment as a discard.</span></span>

<span data-ttu-id="899d9-204">以下示例定义了 `QueryCityDataForYears` 方法，它返回一个包含两个不同年份的城市数据的六元组。</span><span class="sxs-lookup"><span data-stu-id="899d9-204">The following example defines a `QueryCityDataForYears` method that returns a 6-tuple that contains a data for a city for two different years.</span></span> <span data-ttu-id="899d9-205">本例中，方法调用仅与此方法返回的两个人口值相关，因此在进行元组解构时，将元组中的其余值视为弃元。</span><span class="sxs-lookup"><span data-stu-id="899d9-205">The method call in the example is concerned only with the two population values returned by the method and so treats the remaining values in the tuple as discards when it deconstructs the tuple.</span></span>

[!code-csharp[Tuple-discard](../../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

<span data-ttu-id="899d9-206">有关详细信息，请参阅[弃元](../discards.md)。</span><span class="sxs-lookup"><span data-stu-id="899d9-206">For more information, see [Discards](../discards.md).</span></span>
 
## <a name="pattern-matching"></a><span data-ttu-id="899d9-207">模式匹配</span><span class="sxs-lookup"><span data-stu-id="899d9-207">Pattern matching</span></span>

<span data-ttu-id="899d9-208">模式匹配是一种可让你对除对象类型以外的属性实现方法分派的功能。</span><span class="sxs-lookup"><span data-stu-id="899d9-208">*Pattern matching* is a feature that allows you to implement method dispatch on properties other than the type of an object.</span></span> <span data-ttu-id="899d9-209">你可能已经熟悉基于对象类型的方法分派。</span><span class="sxs-lookup"><span data-stu-id="899d9-209">You're probably already familiar with method dispatch based on the type of an object.</span></span> <span data-ttu-id="899d9-210">在面向对象的编程中，虚拟和重写方法提供语言语法来实现基于对象类型的方法分派。</span><span class="sxs-lookup"><span data-stu-id="899d9-210">In Object Oriented programming, virtual and override methods provide language syntax to implement method dispatching based on an object's type.</span></span> <span data-ttu-id="899d9-211">基类和派生类提供不同的实现。</span><span class="sxs-lookup"><span data-stu-id="899d9-211">Base and Derived classes provide different implementations.</span></span> <span data-ttu-id="899d9-212">模式匹配表达式扩展了这一概念，以便你可以通过继承层次结构为不相关的类型和数据元素轻松实现类似的分派模式。</span><span class="sxs-lookup"><span data-stu-id="899d9-212">Pattern matching expressions extend this concept so that you can easily implement similar dispatch patterns for types and data elements that are not related through an inheritance hierarchy.</span></span> 

<span data-ttu-id="899d9-213">模式匹配支持 `is` 表达式和 `switch` 表达式。</span><span class="sxs-lookup"><span data-stu-id="899d9-213">Pattern matching supports `is` expressions and `switch` expressions.</span></span> <span data-ttu-id="899d9-214">每个表达式都允许检查对象及其属性以确定该对象是否满足所寻求的模式。</span><span class="sxs-lookup"><span data-stu-id="899d9-214">Each enables inspecting an object and its properties to determine if that object satisfies the sought pattern.</span></span> <span data-ttu-id="899d9-215">使用 `when` 关键字来指定模式的其他规则。</span><span class="sxs-lookup"><span data-stu-id="899d9-215">You use the `when` keyword to specify additional rules to the pattern.</span></span>

### <a name="is-expression"></a><span data-ttu-id="899d9-216">`is` 表达式</span><span class="sxs-lookup"><span data-stu-id="899d9-216">`is` expression</span></span>

<span data-ttu-id="899d9-217">`is` 模式表达式扩展了常用 `is` 运算符，使其可查询其类型之外的对象。</span><span class="sxs-lookup"><span data-stu-id="899d9-217">The `is` pattern expression extends the familiar `is` operator to query an object beyond its type.</span></span>

<span data-ttu-id="899d9-218">我们以一个简单的方案为例。</span><span class="sxs-lookup"><span data-stu-id="899d9-218">Let's start with a simple scenario.</span></span> <span data-ttu-id="899d9-219">我们将在此方案中添加功能，以便演示模式匹配表达式如何使处理不相关类型的算法变得简单。</span><span class="sxs-lookup"><span data-stu-id="899d9-219">We'll add capabilities to this scenario that demonstrate how pattern matching expressions make algorithms that work with unrelated types easy.</span></span> <span data-ttu-id="899d9-220">我们从计算多次掷骰数之和的方法开始：</span><span class="sxs-lookup"><span data-stu-id="899d9-220">We'll start with a method that computes the sum of a number of die rolls:</span></span>

[!code-csharp[SumDieRolls](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#14_SumDieRolls "Sum die rolls")]

<span data-ttu-id="899d9-221">你可能很快就发现，有时需要在某几次掷骰中骰子多于一个的情况下得出掷骰数总和。</span><span class="sxs-lookup"><span data-stu-id="899d9-221">You might quickly find that you need to find the sum of die rolls where some of the rolls are made with multiple dice (dice is the plural of die).</span></span> <span data-ttu-id="899d9-222">输入序列的一部分可以是多个结果，而非单个数字：</span><span class="sxs-lookup"><span data-stu-id="899d9-222">Part of the input sequence may be multiple results instead of a single number:</span></span>

[!code-csharp[SumDieRollsWithGroups](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#15_SumDieRollsWithGroups "Sum die rolls with groups")]

<span data-ttu-id="899d9-223">`is` 模式表达式在此方案中相当有用处。</span><span class="sxs-lookup"><span data-stu-id="899d9-223">The `is` pattern expression works quite well in this scenario.</span></span> <span data-ttu-id="899d9-224">你可以在检查类型过程中编写变量初始化。</span><span class="sxs-lookup"><span data-stu-id="899d9-224">As part of checking the type, you write a variable initialization.</span></span> <span data-ttu-id="899d9-225">这将创建一个经过验证的运行时类型的新变量。</span><span class="sxs-lookup"><span data-stu-id="899d9-225">This creates a new variable of the validated runtime type.</span></span>

<span data-ttu-id="899d9-226">当继续扩展这些方案时，你可能会发现生成了更多的 `if` 和 `else if` 语句。</span><span class="sxs-lookup"><span data-stu-id="899d9-226">As you keep extending these scenarios, you may find that you build more `if` and `else if` statements.</span></span> <span data-ttu-id="899d9-227">当此情况变得难以处理时，你可能需要切换到 `switch` 模式表达式。</span><span class="sxs-lookup"><span data-stu-id="899d9-227">Once that becomes unwieldy, you'll likely want to switch to `switch` pattern expressions.</span></span>

### <a name="switch-statement-updates"></a><span data-ttu-id="899d9-228">`switch` 语句更新</span><span class="sxs-lookup"><span data-stu-id="899d9-228">`switch` statement updates</span></span>

<span data-ttu-id="899d9-229">匹配表达式具有熟悉的语法，它基于已属于 C# 语言的 `switch` 语句。</span><span class="sxs-lookup"><span data-stu-id="899d9-229">The *match expression* has a familiar syntax, based on the `switch` statement already part of the C# language.</span></span> <span data-ttu-id="899d9-230">在添加新 case 之前，让我们将现有代码转换为使用匹配表达式：</span><span class="sxs-lookup"><span data-stu-id="899d9-230">Let's translate the existing code to use a match expression before adding new cases:</span></span> 

[!code-csharp[SumUsingSwitch](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#16_SumUsingSwitch "Sum using switch")]

<span data-ttu-id="899d9-231">匹配表达式的语法与 `is` 表达式稍有不同，你可以在 `case` 表达式的开头声明类型和变量。</span><span class="sxs-lookup"><span data-stu-id="899d9-231">The match expressions have a slightly different syntax than the `is` expressions, where you declare the type and variable at the beginning of the `case` expression.</span></span>

<span data-ttu-id="899d9-232">匹配表达式也支持常量。</span><span class="sxs-lookup"><span data-stu-id="899d9-232">The match expressions also support constants.</span></span> <span data-ttu-id="899d9-233">这样可以通过分离出简单 case 来节省时间：</span><span class="sxs-lookup"><span data-stu-id="899d9-233">This can save time by factoring out simple cases:</span></span>

[!code-csharp[SwitchWithConstants](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#17_SwitchWithConstants "Switch with constants")]

<span data-ttu-id="899d9-234">上面的代码为 `0` 添加 case 作为 `int` 的特殊 case，为 `null` 添加 case 作为没有输出时的特殊 case。</span><span class="sxs-lookup"><span data-stu-id="899d9-234">The code above adds cases for `0` as a special case of `int`, and `null` as a special case when there is no input.</span></span> <span data-ttu-id="899d9-235">这演示了 switch 模式表达式中一个重要的新功能：`case` 表达式的顺序现在很重要。</span><span class="sxs-lookup"><span data-stu-id="899d9-235">This demonstrates one important new feature in switch pattern expressions: the order of the `case` expressions now matters.</span></span> <span data-ttu-id="899d9-236">`0` case 必须出现在常规 `int` case 之前。</span><span class="sxs-lookup"><span data-stu-id="899d9-236">The `0` case must appear before the general `int` case.</span></span> <span data-ttu-id="899d9-237">否则，要匹配的第一个模式将为 `int` case，即使值为 `0` 时也是如此。</span><span class="sxs-lookup"><span data-stu-id="899d9-237">Otherwise, the first pattern to match would be the `int` case, even when the value is `0`.</span></span> <span data-ttu-id="899d9-238">如果匹配表达式进行意外排序（例如稍后的 case 已经过处理），则编译器将对其标记并生成错误。</span><span class="sxs-lookup"><span data-stu-id="899d9-238">If you accidentally order match expressions such that a later case has already been handled, the compiler will flag that and generate an error.</span></span>

<span data-ttu-id="899d9-239">这一相同行为可实现空输入序列的特殊 case。</span><span class="sxs-lookup"><span data-stu-id="899d9-239">This same behavior enables the special case for an empty input sequence.</span></span>
<span data-ttu-id="899d9-240">可以看到，包含元素的 `IEnumerable` 项的 case 必须出现在常规 `IEnumerable` case 之前。</span><span class="sxs-lookup"><span data-stu-id="899d9-240">You can see that the case for an `IEnumerable` item that has elements must appear before the general `IEnumerable` case.</span></span>

<span data-ttu-id="899d9-241">此版本还添加了一个 `default` case。</span><span class="sxs-lookup"><span data-stu-id="899d9-241">This version has also added a `default` case.</span></span> <span data-ttu-id="899d9-242">无论在源中出现的顺序如何，`default` case 总是最后计算的。</span><span class="sxs-lookup"><span data-stu-id="899d9-242">The `default` case is always evaluated last, regardless of the order it appears in the source.</span></span> <span data-ttu-id="899d9-243">因此，惯例是将 `default` case 放在最后。</span><span class="sxs-lookup"><span data-stu-id="899d9-243">For that reason, convention is to put the `default` case last.</span></span>

<span data-ttu-id="899d9-244">最后，让我们为新样式的骰子添加最后一个 `case`。</span><span class="sxs-lookup"><span data-stu-id="899d9-244">Finally, let's add one last `case` for a new style of die.</span></span> <span data-ttu-id="899d9-245">某些游戏使用百分比骰子来表示更大范围的数字。</span><span class="sxs-lookup"><span data-stu-id="899d9-245">Some games use percentile dice to represent larger ranges of numbers.</span></span> 

> [!NOTE]
> <span data-ttu-id="899d9-246">两个 10 面百分比骰子可以表示 0 到 99 之间的每个数字。</span><span class="sxs-lookup"><span data-stu-id="899d9-246">Two 10-sided percentile dice can represent every number from 0 through 99.</span></span> <span data-ttu-id="899d9-247">一个骰子的各面标记为 `00`、`10`、`20`, ... `90`。</span><span class="sxs-lookup"><span data-stu-id="899d9-247">One die has sides labelled `00`, `10`, `20`, ... `90`.</span></span> <span data-ttu-id="899d9-248">另一个骰子的各面标记为 `0`、`1`、`2`, ... `9`。</span><span class="sxs-lookup"><span data-stu-id="899d9-248">The other die has sides labeled `0`, `1`, `2`, ... `9`.</span></span> <span data-ttu-id="899d9-249">将两个骰子的值加在一起，可以得到 0 到 99 之间的每个数字。</span><span class="sxs-lookup"><span data-stu-id="899d9-249">Add the two die values together and you can get every number from 0 through 99.</span></span>

<span data-ttu-id="899d9-250">要将此类型的骰子添加到集合，请先定义一个类型来表示百分比骰子。</span><span class="sxs-lookup"><span data-stu-id="899d9-250">To add this kind of die to your collection, first define a type to represent the percentile dice.</span></span> <span data-ttu-id="899d9-251">`TensDigit` 属性将值存储为 `0`、`10`、`20`（依次递增，最大为 `90`）：</span><span class="sxs-lookup"><span data-stu-id="899d9-251">The `TensDigit` property stores values `0`, `10`, `20`, up to `90`:</span></span>

[!code-csharp[18_PercentileDice](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#18_PercentileDice "Percentile Die type")]

<span data-ttu-id="899d9-252">然后，为新类型添加一个 `case` 匹配表达式：</span><span class="sxs-lookup"><span data-stu-id="899d9-252">Then, add a `case` match expression for the new type:</span></span>

[!code-csharp[SwitchWithNewTypes](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#19_SwitchWithNewTypes "Include Percentile Die type")]

<span data-ttu-id="899d9-253">模式匹配表达式的新语法使得使用清晰简练的语法创建基于对象的类型或其他属性的分派算法更加容易。</span><span class="sxs-lookup"><span data-stu-id="899d9-253">The new syntax for pattern matching expressions makes it easier to create dispatch algorithms based on an object's type, or other properties, using a clear and concise syntax.</span></span> <span data-ttu-id="899d9-254">模式匹配表达式可以在因继承而无关的数据类型上实现这些构造。</span><span class="sxs-lookup"><span data-stu-id="899d9-254">Pattern matching expressions enable these constructs on data types that are unrelated by inheritance.</span></span>

<span data-ttu-id="899d9-255">你可以在专门介绍 [C# 中的模式匹配](../pattern-matching.md)的主题中了解有关模式匹配的详细信息。</span><span class="sxs-lookup"><span data-stu-id="899d9-255">You can learn more about pattern matching in the topic dedicated to [pattern matching in C#](../pattern-matching.md).</span></span>

## <a name="ref-locals-and-returns"></a><span data-ttu-id="899d9-256">Ref 局部变量和返回结果</span><span class="sxs-lookup"><span data-stu-id="899d9-256">Ref locals and returns</span></span>

<span data-ttu-id="899d9-257">此功能允许使用并返回对变量的引用的算法，这些变量在其他位置定义。</span><span class="sxs-lookup"><span data-stu-id="899d9-257">This feature enables algorithms that use and return references to variables defined elsewhere.</span></span> <span data-ttu-id="899d9-258">一个示例是使用大型矩阵并查找具有某些特征的单个位置。</span><span class="sxs-lookup"><span data-stu-id="899d9-258">One example is working with large matrices, and finding a single location with certain characteristics.</span></span> <span data-ttu-id="899d9-259">有一个方法可返回矩阵中某单个位置的两个索引：</span><span class="sxs-lookup"><span data-stu-id="899d9-259">One method would return the two indices for a single location in the matrix:</span></span>

[!code-csharp[FindReturningIndices](../../../samples/snippets/csharp/new-in-7/MatrixSearch.cs#20_FindReturningIndices "Find returning indices")]

<span data-ttu-id="899d9-260">此代码存在很多问题。</span><span class="sxs-lookup"><span data-stu-id="899d9-260">There are many issues with this code.</span></span> <span data-ttu-id="899d9-261">首先，它是一个返回元组的公共方法。</span><span class="sxs-lookup"><span data-stu-id="899d9-261">First of all, it's a public method that's returning a tuple.</span></span> <span data-ttu-id="899d9-262">语言支持此方法，但对公共 API 来说，用户定义的类型（类或结构）是更优选择。</span><span class="sxs-lookup"><span data-stu-id="899d9-262">The language supports this, but user defined types (either classes or structs) are preferred for public APIs.</span></span>

<span data-ttu-id="899d9-263">其次，此方法返回的是矩阵中的项的索引。</span><span class="sxs-lookup"><span data-stu-id="899d9-263">Second, this method is returning the indices to the item in the matrix.</span></span>
<span data-ttu-id="899d9-264">这会导致调用方编写使用这些索引的代码来取消引用矩阵并修改单个元素：</span><span class="sxs-lookup"><span data-stu-id="899d9-264">That leads callers to write code that uses those indices to dereference the matrix and modify a single element:</span></span>

[!code-csharp[UpdateItemFromIndices](../../../samples/snippets/csharp/new-in-7/program.cs#21_UpdateItemFromIndices "Update Item From Indices")]

<span data-ttu-id="899d9-265">与其这样，还不如编写一个方法，返回对你要更改的矩阵的元素的引用。</span><span class="sxs-lookup"><span data-stu-id="899d9-265">You'd rather write a method that returns a *reference* to the element of the matrix that you want to change.</span></span> <span data-ttu-id="899d9-266">在以前的版本中，你只能通过使用不安全代码并返回一个指向 `int` 的指针来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="899d9-266">You could only accomplish this by using unsafe code and returning a pointer to an `int` in previous versions.</span></span>

<span data-ttu-id="899d9-267">让我们通过一系列更改来演示 ref 局部变量功能，并展示如何创建返回对内部存储的引用的方法。</span><span class="sxs-lookup"><span data-stu-id="899d9-267">Let's walk through a series of changes to demonstrate the ref local feature and show how to create a method that returns a reference to internal storage.</span></span>
<span data-ttu-id="899d9-268">与此同时，你将学习 ref 返回结果的规则以及可保护你免于意外误用它的 ref 局部变量功能。</span><span class="sxs-lookup"><span data-stu-id="899d9-268">Along the way, you'll learn the rules of the ref return and ref local feature that protects you from accidentally misusing it.</span></span>

<span data-ttu-id="899d9-269">首先修改 `Find` 方法声明，使其返回一个 `ref int`，而不是一个元组。</span><span class="sxs-lookup"><span data-stu-id="899d9-269">Start by modifying the `Find` method declaration so that it returns a `ref int` instead of a tuple.</span></span> <span data-ttu-id="899d9-270">然后修改 return 语句，使其返回存储在矩阵中的值，而不是两个索引：</span><span class="sxs-lookup"><span data-stu-id="899d9-270">Then, modify the return statement so it returns the value stored in the matrix instead of the two indices:</span></span>

```csharp
// Note that this won't compile. 
// Method declaration indicates ref return,
// but return statement specifies a value return.
public static ref int Find2(int[,] matrix, Func<int, bool> predicate)
{
    for (int i = 0; i < matrix.GetLength(0); i++)
        for (int j = 0; j < matrix.GetLength(1); j++)
            if (predicate(matrix[i, j]))
                return matrix[i, j];
    throw new InvalidOperationException("Not found");
}
```

<span data-ttu-id="899d9-271">当你声明方法返回 `ref` 变量时，还必须向每个 return 语句添加 `ref` 关键字。</span><span class="sxs-lookup"><span data-stu-id="899d9-271">When you declare that a method returns a `ref` variable, you must also add the `ref` keyword to each return statement.</span></span> <span data-ttu-id="899d9-272">这指示按引用返回，并可帮助以后阅读代码的开发人员记住该方法按引用返回：</span><span class="sxs-lookup"><span data-stu-id="899d9-272">That indicates return by reference, and helps developers reading the code later remember that the method returns by reference:</span></span>

[!code-csharp[FindReturningRef](../../../samples/snippets/csharp/new-in-7/MatrixSearch.cs#22_FindReturningRef "Find returning by reference")]

<span data-ttu-id="899d9-273">因为该方法返回对矩阵中的整数值的引用，所以你需要修改调用它的位置。</span><span class="sxs-lookup"><span data-stu-id="899d9-273">Now that the method returns a reference to the integer value in the matrix, you need to modify where it's called.</span></span>  <span data-ttu-id="899d9-274">`var` 声明意味着 `valItem` 现在是 `int` 而不是元组：</span><span class="sxs-lookup"><span data-stu-id="899d9-274">The `var` declaration means that `valItem` is now an `int` rather than a tuple:</span></span>

[!code-csharp[AssignRefReturnToValue](../../../samples/snippets/csharp/new-in-7/program.cs#23_AssignRefReturnToValue "Assign ref return to value")]

<span data-ttu-id="899d9-275">上例中的第二个 `WriteLine` 语句打印出值 `42`，而不是 `24`。</span><span class="sxs-lookup"><span data-stu-id="899d9-275">The second `WriteLine` statement in the example above prints out the value `42`, not `24`.</span></span> <span data-ttu-id="899d9-276">变量 `valItem` 是 `int`，而不是 `ref int`。</span><span class="sxs-lookup"><span data-stu-id="899d9-276">The variable `valItem` is an `int`, not a `ref int`.</span></span> <span data-ttu-id="899d9-277">`var` 关键字使编译器能够指定类型，但不会隐式添加 `ref` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="899d9-277">The `var` keyword enables the compiler to specify the type, but will not implicitly add the `ref` modifier.</span></span> <span data-ttu-id="899d9-278">相反，`ref return` 引用的值会被复制到赋值左侧的变量。</span><span class="sxs-lookup"><span data-stu-id="899d9-278">Instead, the value referred to by the `ref return` is *copied* to the variable on the left-hand side of the assignment.</span></span> <span data-ttu-id="899d9-279">该变量不是 `ref` 局部变量。</span><span class="sxs-lookup"><span data-stu-id="899d9-279">The variable is not a `ref` local.</span></span>

<span data-ttu-id="899d9-280">为了获得所需的结果，需要在局部变量声明中添加 `ref` 修饰符，使变量在返回值为引用时成为引用：</span><span class="sxs-lookup"><span data-stu-id="899d9-280">In order to get the result you want, you need to add the `ref` modifier to the local variable declaration to make the variable a reference when the return value is a reference:</span></span>

[!code-csharp[AssignRefReturn](../../../samples/snippets/csharp/new-in-7/program.cs#24_AssignRefReturn "Assign ref return")]

<span data-ttu-id="899d9-281">现在，上例中的第二个 `WriteLine` 语句将打印出值 `24`，指示矩阵中的存储已被修改。</span><span class="sxs-lookup"><span data-stu-id="899d9-281">Now, the second `WriteLine` statement in the example above will print out the value `24`, indicating that the storage in the matrix has been modified.</span></span> <span data-ttu-id="899d9-282">局部变量已使用 `ref` 修饰符进行声明，它将返回 `ref`。</span><span class="sxs-lookup"><span data-stu-id="899d9-282">The local variable has been declared with the `ref` modifier, and it will take a `ref` return.</span></span> <span data-ttu-id="899d9-283">必须在声明时初始化 `ref` 变量，不能拆分声明和初始化。</span><span class="sxs-lookup"><span data-stu-id="899d9-283">You must initialize a `ref` variable when it is declared, you cannot split the declaration and the initialization.</span></span>

<span data-ttu-id="899d9-284">C# 语言还设有三条规则，可防止你误用 `ref` 局部变量和返回结果：</span><span class="sxs-lookup"><span data-stu-id="899d9-284">The C# language has three other rules that protect you from misusing the `ref` locals and returns:</span></span>

* <span data-ttu-id="899d9-285">不可向 `ref` 本地变量赋予标准方法返回值。</span><span class="sxs-lookup"><span data-stu-id="899d9-285">You cannot assign a standard method return value to a `ref` local variable.</span></span>
    - <span data-ttu-id="899d9-286">因为那将禁止类似 `ref int i = sequence.Count();` 这样的语句</span><span class="sxs-lookup"><span data-stu-id="899d9-286">That disallows statements like `ref int i = sequence.Count();`</span></span>
* <span data-ttu-id="899d9-287">不能将 `ref` 返回给其生存期不超出方法执行的变量。</span><span class="sxs-lookup"><span data-stu-id="899d9-287">You cannot return a `ref` to a variable whose lifetime does not extend beyond the execution of the method.</span></span>
    - <span data-ttu-id="899d9-288">这意味着不可返回对本地变量或对类似作用域变量的引用。</span><span class="sxs-lookup"><span data-stu-id="899d9-288">That means you cannot return a reference to a local variable or a variable with a similar scope.</span></span>
* <span data-ttu-id="899d9-289">`ref` 局部变量和返回结果不可用于异步方法。</span><span class="sxs-lookup"><span data-stu-id="899d9-289">`ref` locals and returns can't be used with async methods.</span></span>
    - <span data-ttu-id="899d9-290">编译器无法知道异步方法返回时，引用的变量是否已设置为其最终值。</span><span class="sxs-lookup"><span data-stu-id="899d9-290">The compiler can't know if the referenced variable has been set to its final value when the async method returns.</span></span>

<span data-ttu-id="899d9-291">添加 ref 局部变量和 ref 返回结果可通过避免复制值或多次执行取消引用操作，允许更为高效的算法。</span><span class="sxs-lookup"><span data-stu-id="899d9-291">The addition of ref locals and ref returns enable algorithms that are more efficient by avoiding copying values, or performing dereferencing operations multiple times.</span></span> 

## <a name="local-functions"></a><span data-ttu-id="899d9-292">本地函数</span><span class="sxs-lookup"><span data-stu-id="899d9-292">Local functions</span></span>

<span data-ttu-id="899d9-293">许多类的设计都包括仅从一个位置调用的方法。</span><span class="sxs-lookup"><span data-stu-id="899d9-293">Many designs for classes include methods that are called from only one location.</span></span> <span data-ttu-id="899d9-294">这些额外的私有方法使每个方法保持小且集中。</span><span class="sxs-lookup"><span data-stu-id="899d9-294">These additional private methods keep each method small and focused.</span></span> <span data-ttu-id="899d9-295">但是，它们使得在第一次阅读某个类时难以理解它。</span><span class="sxs-lookup"><span data-stu-id="899d9-295">However, they can make it harder to understand a class when reading it the first time.</span></span> <span data-ttu-id="899d9-296">在单个调用位置的上下文之外必须能够理解这些方法。</span><span class="sxs-lookup"><span data-stu-id="899d9-296">These methods must be understood outside of the context of the single calling location.</span></span>

<span data-ttu-id="899d9-297">对于这些设计，本地函数使你能够在另一个方法的上下文内声明方法。</span><span class="sxs-lookup"><span data-stu-id="899d9-297">For those designs, *local functions* enable you to declare methods inside the context of another method.</span></span> <span data-ttu-id="899d9-298">这使得类的阅读者更容易看到本地方法是仅从声明它的上下文中调用的。</span><span class="sxs-lookup"><span data-stu-id="899d9-298">This makes it easier for readers of the class to see that the local method is only called from the context in which is it declared.</span></span>

<span data-ttu-id="899d9-299">对于本地函数有两个非常常见的用例：公共迭代器方法和公共异步方法。</span><span class="sxs-lookup"><span data-stu-id="899d9-299">There are two very common use cases for local functions: public iterator methods and public async methods.</span></span> <span data-ttu-id="899d9-300">这两种类型的方法都生成报告错误的时间晚于程序员期望时间的代码。</span><span class="sxs-lookup"><span data-stu-id="899d9-300">Both types of methods generate code that reports errors later than programmers might expect.</span></span> <span data-ttu-id="899d9-301">在迭代器方法中，只有在调用枚举返回的序列的代码时才会观察到任何异常。</span><span class="sxs-lookup"><span data-stu-id="899d9-301">In the case of iterator methods, any exceptions are observed only when calling code that enumerates the returned sequence.</span></span> <span data-ttu-id="899d9-302">在异步方法中，只有当返回的 `Task` 处于等待状态时才会观察到任何异常。</span><span class="sxs-lookup"><span data-stu-id="899d9-302">In the case of async methods, any exceptions are only observed when the returned `Task` is awaited.</span></span>

<span data-ttu-id="899d9-303">让我们以迭代器方法为例：</span><span class="sxs-lookup"><span data-stu-id="899d9-303">Let's start with an iterator method:</span></span>

[!code-csharp[IteratorMethod](../../../samples/snippets/csharp/new-in-7/Iterator.cs#25_IteratorMethod "Iterator method")]

<span data-ttu-id="899d9-304">检查下面错误调用迭代器方法的代码：</span><span class="sxs-lookup"><span data-stu-id="899d9-304">Examine the code below that calls the iterator method incorrectly:</span></span>

[!code-csharp[CallIteratorMethod](../../../samples/snippets/csharp/new-in-7/program.cs#26_CallIteratorMethod "Call iterator method")]

<span data-ttu-id="899d9-305">在循环访问 `resultSet`（而不是创建 `resultSet`）时引发异常。</span><span class="sxs-lookup"><span data-stu-id="899d9-305">The exception is thrown when `resultSet` is iterated, not when `resultSet` is created.</span></span>
<span data-ttu-id="899d9-306">在这个包含的示例中，大多数开发人员都可快速诊断问题。</span><span class="sxs-lookup"><span data-stu-id="899d9-306">In this contained example, most developers could quickly diagnose the problem.</span></span> <span data-ttu-id="899d9-307">但是，在大型基本代码中，创建迭代器的代码通常不像枚举结果的代码那么接近。</span><span class="sxs-lookup"><span data-stu-id="899d9-307">However, in larger codebases, the code that creates an iterator often isn't as close to the code that enumerates the result.</span></span> <span data-ttu-id="899d9-308">可以重构代码，使公共方法验证所有参数，且私有方法生成枚举：</span><span class="sxs-lookup"><span data-stu-id="899d9-308">You can refactor the code so that the public method validates all arguments, and a private method generates the enumeration:</span></span>

[!code-csharp[IteratorMethodRefactored](../../../samples/snippets/csharp/new-in-7/Iterator.cs#27_IteratorMethodRefactored "Iterator method refactored")]

<span data-ttu-id="899d9-309">此重构版本将立即引发异常，因为公共方法不是迭代器方法；只有私有方法才使用 `yield return` 语法。</span><span class="sxs-lookup"><span data-stu-id="899d9-309">This refactored version will throw exceptions immediately because the public method is not an iterator method; only the private method uses the `yield return` syntax.</span></span> <span data-ttu-id="899d9-310">但是，这种重构存在潜在问题。</span><span class="sxs-lookup"><span data-stu-id="899d9-310">However, there are potential problems with this refactoring.</span></span> <span data-ttu-id="899d9-311">私有方法只应从公共接口方法调用，因为如果不这样，就将跳过所有参数验证。</span><span class="sxs-lookup"><span data-stu-id="899d9-311">The private method should only be called from the public interface method, because otherwise all argument validation is skipped.</span></span>
<span data-ttu-id="899d9-312">类的阅读者必须通过阅读整个类并搜索对 `alphabetSubsetImplementation` 方法的任何其他引用来发现这个事实。</span><span class="sxs-lookup"><span data-stu-id="899d9-312">Readers of the class must discover this fact by reading the entire class and searching for any other references to the `alphabetSubsetImplementation` method.</span></span>

<span data-ttu-id="899d9-313">通过在公共 API 方法内将 `alphabetSubsetImplementation` 声明为本地函数，可以使该设计意图更清楚：</span><span class="sxs-lookup"><span data-stu-id="899d9-313">You can make that design intent more clear by declaring the `alphabetSubsetImplementation` as a local function inside the public API method:</span></span>

[!code-csharp[22_IteratorMethodLocal](../../../samples/snippets/csharp/new-in-7/Iterator.cs#28_IteratorMethodLocal "Iterator method with local function")]

<span data-ttu-id="899d9-314">上面的版本清楚地表明，本地方法仅在外部方法的上下文中引用。</span><span class="sxs-lookup"><span data-stu-id="899d9-314">The version above makes it clear that the local method is referenced only in the context of the outer method.</span></span> <span data-ttu-id="899d9-315">本地函数的规则还确保开发人员不会意外地从类中的另一个位置调用本地函数和绕过参数验证。</span><span class="sxs-lookup"><span data-stu-id="899d9-315">The rules for local functions also ensure that a developer can't accidentally call the local function from another location in the class and bypass the argument validation.</span></span>

<span data-ttu-id="899d9-316">可以对 `async` 方法采用相同的技术，以确保在异步工作开始之前引发由参数验证引起的异常：</span><span class="sxs-lookup"><span data-stu-id="899d9-316">The same technique can be employed with `async` methods to ensure that exceptions arising from argument validation are thrown before the asynchronous work begins:</span></span>

[!code-csharp[TaskExample](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Task returning method with local function")]

> [!NOTE]
> <span data-ttu-id="899d9-317">本地函数支持的某些设计也可以使用 lambda 表达式来完成。</span><span class="sxs-lookup"><span data-stu-id="899d9-317">Some of the designs that are supported by local functions could also be accomplished using *lambda expressions*.</span></span> <span data-ttu-id="899d9-318">感兴趣的人可以[阅读有关差异的详细信息](../local-functions-vs-lambdas.md)</span><span class="sxs-lookup"><span data-stu-id="899d9-318">Those interested can [read more about the differences](../local-functions-vs-lambdas.md)</span></span>

## <a name="more-expression-bodied-members"></a><span data-ttu-id="899d9-319">更多的 expression-bodied 成员</span><span class="sxs-lookup"><span data-stu-id="899d9-319">More expression-bodied members</span></span>

<span data-ttu-id="899d9-320">C# 6 为成员函数和只读属性引入了 [expression-bodied 成员](csharp-6.md#expression-bodied-function-members)。</span><span class="sxs-lookup"><span data-stu-id="899d9-320">C# 6 introduced [expression-bodied members](csharp-6.md#expression-bodied-function-members) for member functions, and read-only properties.</span></span> <span data-ttu-id="899d9-321">C# 7.0 扩展了可作为表达式实现的允许的成员。</span><span class="sxs-lookup"><span data-stu-id="899d9-321">C# 7.0 expands the allowed members that can be implemented as expressions.</span></span> <span data-ttu-id="899d9-322">在 C# 7.0 中，你可以在属性和索引器上实现构造函数、终结器以及 `get` 和 `set` 访问器。</span><span class="sxs-lookup"><span data-stu-id="899d9-322">In C# 7.0, you can implement *constructors*, *finalizers*, and `get` and `set` accessors on *properties* and *indexers*.</span></span> <span data-ttu-id="899d9-323">以下代码演示了每种情况的示例：</span><span class="sxs-lookup"><span data-stu-id="899d9-323">The following code shows examples of each:</span></span>

[!code-csharp[ExpressionBodiedMembers](../../../samples/snippets/csharp/new-in-7/expressionmembers.cs#36_ExpressionBodiedEverything "new expression-bodied members")]

> [!NOTE]
> <span data-ttu-id="899d9-324">本示例不需要终结器，但显示它是为了演示语法。</span><span class="sxs-lookup"><span data-stu-id="899d9-324">This example does not need a finalizer, but it is shown to demonstrate the syntax.</span></span> <span data-ttu-id="899d9-325">不应在类中实现终结器，除非有必要发布非托管资源。</span><span class="sxs-lookup"><span data-stu-id="899d9-325">You should not implement a finalizer in your class unless it is necessary to  release unmanaged resources.</span></span> <span data-ttu-id="899d9-326">还应考虑使用 <xref:System.Runtime.InteropServices.SafeHandle> 类，而不是直接管理非托管资源。</span><span class="sxs-lookup"><span data-stu-id="899d9-326">You should also consider using the <xref:System.Runtime.InteropServices.SafeHandle> class instead of managing unmanaged resources directly.</span></span>

<span data-ttu-id="899d9-327">这些针对 expression-bodied 成员的新位置代表了 C# 语言的一个重要里程碑：这些功能由致力于开放源代码 [Roslyn](https://github.com/dotnet/Roslyn) 项目的社区成员实现。</span><span class="sxs-lookup"><span data-stu-id="899d9-327">These new locations for expression-bodied members represent an important milestone for the C# language: These features were implemented by community members working on the open-source [Roslyn](https://github.com/dotnet/Roslyn) project.</span></span>

## <a name="throw-expressions"></a><span data-ttu-id="899d9-328">引发表达式</span><span class="sxs-lookup"><span data-stu-id="899d9-328">Throw expressions</span></span>

<span data-ttu-id="899d9-329">在 C# 中，`throw` 始终是一个语句。</span><span class="sxs-lookup"><span data-stu-id="899d9-329">In C#, `throw` has always been a statement.</span></span> <span data-ttu-id="899d9-330">因为 `throw` 是一个语句而非表达式，所以在某些 C# 构造中无法使用它。</span><span class="sxs-lookup"><span data-stu-id="899d9-330">Because `throw` is a statement, not an expression, there were C# constructs where you could not use it.</span></span> <span data-ttu-id="899d9-331">它们包括条件表达式、null 合并表达式和一些 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="899d9-331">These included conditional expressions, null coalescing expressions, and some lambda expressions.</span></span> <span data-ttu-id="899d9-332">添加 expression-bodied 成员将添加更多位置，在这些位置中，`throw` 表达式会很有用。</span><span class="sxs-lookup"><span data-stu-id="899d9-332">The addition of expression-bodied members adds more locations where `throw` expressions would be useful.</span></span> <span data-ttu-id="899d9-333">为了可以编写任何这些构造，C# 7.0 引入了引发表达式。</span><span class="sxs-lookup"><span data-stu-id="899d9-333">So that you can write any of these constructs, C# 7.0 introduces *throw expressions*.</span></span>

<span data-ttu-id="899d9-334">语法与你一直以来用于 `throw` 语句的语法相同。</span><span class="sxs-lookup"><span data-stu-id="899d9-334">The syntax is the same as you've always used for `throw` statements.</span></span> <span data-ttu-id="899d9-335">唯一的区别是，现在你可以将它们放在新位置中（例如条件表达式中）：</span><span class="sxs-lookup"><span data-stu-id="899d9-335">The only difference is that now you can place them in new locations, such as in a conditional expression:</span></span>

[!code-csharp[Throw_ExpressionExample](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#37_Throw_ExpressionExample "conditional throw expressions")]

<span data-ttu-id="899d9-336">此功能允许在初始化表达式中使用引发表达式：</span><span class="sxs-lookup"><span data-stu-id="899d9-336">This features enables using throw expressions in initialization expressions:</span></span>

[!code-csharp[ThrowInInitialization](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#38_ThrowInInitialization "conditional throw expressions")]

<span data-ttu-id="899d9-337">以前，这些初始化需要位于构造函数中，且 throw 语句在构造函数的正文中：</span><span class="sxs-lookup"><span data-stu-id="899d9-337">Previously, those initializations would need to be in a constructor, with the throw statements in the body of the constructor:</span></span>


[!code-csharp[ThrowInConstructor](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#39_ThrowInConstructor "throw statements")]

> [!NOTE]
> <span data-ttu-id="899d9-338">前述两种构造都将导致在构造对象过程中引发异常。</span><span class="sxs-lookup"><span data-stu-id="899d9-338">Both of the preceding constructs will cause exceptions to be thrown during the construction of an object.</span></span> <span data-ttu-id="899d9-339">通常很难从这些异常中恢复。</span><span class="sxs-lookup"><span data-stu-id="899d9-339">Those are often difficult to recover from.</span></span>
> <span data-ttu-id="899d9-340">为此，不建议使用在构造过程中引发异常的设计。</span><span class="sxs-lookup"><span data-stu-id="899d9-340">For that reason, designs that throw exceptions during construction are discouraged.</span></span>

## <a name="generalized-async-return-types"></a><span data-ttu-id="899d9-341">通用的异步返回类型</span><span class="sxs-lookup"><span data-stu-id="899d9-341">Generalized async return types</span></span>

<span data-ttu-id="899d9-342">从异步方法返回 `Task` 对象可能在某些路径中导致性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="899d9-342">Returning a `Task` object from async methods can introduce performance bottlenecks in certain paths.</span></span> <span data-ttu-id="899d9-343">`Task` 是引用类型，因此使用它意味着分配对象。</span><span class="sxs-lookup"><span data-stu-id="899d9-343">`Task` is a reference type, so using it means allocating an object.</span></span> <span data-ttu-id="899d9-344">如果使用 `async` 修饰符声明的方法返回缓存结果或以同步方式完成，那么额外的分配在代码的性能关键部分可能要耗费相当长的时间。</span><span class="sxs-lookup"><span data-stu-id="899d9-344">In cases where a method declared with the `async` modifier returns a cached result, or completes synchronously, the extra allocations can become a significant time cost in performance critical sections of code.</span></span> <span data-ttu-id="899d9-345">如果这些分配发生在紧凑循环中，则成本会变得非常高。</span><span class="sxs-lookup"><span data-stu-id="899d9-345">It can become very costly if those allocations occur in tight loops.</span></span>

<span data-ttu-id="899d9-346">新语言功能意味着异步方法可以返回除 `Task`、`Task<T>` 和 `void` 以外的其他类型。</span><span class="sxs-lookup"><span data-stu-id="899d9-346">The new language feature means that async methods may return other types in addition to `Task`, `Task<T>` and `void`.</span></span> <span data-ttu-id="899d9-347">返回类型必须仍满足异步模式，这意味着 `GetAwaiter` 方法必须是可访问的。</span><span class="sxs-lookup"><span data-stu-id="899d9-347">The returned type must still satisfy the async pattern, meaning a `GetAwaiter` method must be accessible.</span></span> <span data-ttu-id="899d9-348">作为一个具体示例，已将 `ValueTask` 类型添加到 .NET framework 中，以使用这一新语言功能：</span><span class="sxs-lookup"><span data-stu-id="899d9-348">As one concrete example, the `ValueTask` type has been added to the .NET framework to make use of this new language feature:</span></span> 

[!code-csharp[UsingValueTask](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#30_UsingValueTask "Using ValueTask")]

> [!NOTE]
> <span data-ttu-id="899d9-349">需要添加 NuGet 包 [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) 才能使用 <xref:System.Threading.Tasks.ValueTask%601> 类型。</span><span class="sxs-lookup"><span data-stu-id="899d9-349">You need to add the NuGet package [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) in order to use the <xref:System.Threading.Tasks.ValueTask%601> type.</span></span>

<span data-ttu-id="899d9-350">一个简单的优化是在之前使用 `Task` 的地方使用 `ValueTask`。</span><span class="sxs-lookup"><span data-stu-id="899d9-350">A simple optimization would be to use `ValueTask` in places where `Task` would be used before.</span></span> <span data-ttu-id="899d9-351">但是，如果要手动执行额外的优化，则可以缓存来自异步工作的结果，并在后续调用中重用结果。</span><span class="sxs-lookup"><span data-stu-id="899d9-351">However, if you want to perform extra optimizations by hand, you can cache results from async work and reuse the result in subsequent calls.</span></span> <span data-ttu-id="899d9-352">`ValueTask` 结构具有带 `Task` 参数的构造函数，以便你可以从任何现有异步方法的返回值构造 `ValueTask`：</span><span class="sxs-lookup"><span data-stu-id="899d9-352">The `ValueTask` struct has a constructor with a `Task` parameter so that you can construct a `ValueTask` from the return value of any existing async method:</span></span>

[!code-csharp[AsyncOptimizedValueTask](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#31_AsyncOptimizedValueTask "Return async result or cached value")]
 
<span data-ttu-id="899d9-353">与所有性能建议一样，应在对代码进行大规模更改之前对两个版本进行基准测试。</span><span class="sxs-lookup"><span data-stu-id="899d9-353">As with all performance recommendations, you should benchmark both versions before making large scale changes to your code.</span></span>

## <a name="numeric-literal-syntax-improvements"></a><span data-ttu-id="899d9-354">数字文本语法改进</span><span class="sxs-lookup"><span data-stu-id="899d9-354">Numeric literal syntax improvements</span></span>

<span data-ttu-id="899d9-355">误读的数值常量可能使第一次阅读代码时更难理解。</span><span class="sxs-lookup"><span data-stu-id="899d9-355">Misreading numeric constants can make it harder to understand code when reading it for the first time.</span></span> <span data-ttu-id="899d9-356">当这些数字被用作位掩码或其他符号而非数字值时，通常会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="899d9-356">This often occurs when those numbers are used as bit masks or other symbolic rather than numeric values.</span></span> <span data-ttu-id="899d9-357">C# 7.0 包括两项新功能，使得更容易以最可读的方式写入数字来用于预期用途：二进制文本和数字分隔符。</span><span class="sxs-lookup"><span data-stu-id="899d9-357">C# 7.0 includes two new features to make it easier to write numbers in the most readable fashion for the intended use: *binary literals*, and *digit separators*.</span></span>

<span data-ttu-id="899d9-358">在创建位掩码时，或每当数字的二进制表示形式使代码最具可读性时，以二进制形式写入该数字：</span><span class="sxs-lookup"><span data-stu-id="899d9-358">For those times when you are creating bit masks, or whenever a binary representation of a number makes the most readable code, write that number in binary:</span></span>

[!code-csharp[BinaryConstants](../../../samples/snippets/csharp/new-in-7/Program.cs#32_BinaryConstants "Binary constants")]

<span data-ttu-id="899d9-359">常量开头的 `0b` 表示该数字以二进制数形式写入。</span><span class="sxs-lookup"><span data-stu-id="899d9-359">The `0b` at the beginning of the constant indicates that the number is written as a binary number.</span></span>

<span data-ttu-id="899d9-360">二进制数可能会很长，因此通过引入 `_` 作为数字分隔符通常更易于查看位模式：</span><span class="sxs-lookup"><span data-stu-id="899d9-360">Binary numbers can get very long, so it's often easier to see the bit patterns by introducing the `_` as a digit separator:</span></span>

[!code-csharp[ThousandSeparators](../../../samples/snippets/csharp/new-in-7/Program.cs#33_ThousandSeparators "Thousands separators")]

<span data-ttu-id="899d9-361">数字分隔符可以出现在常量的任何位置。</span><span class="sxs-lookup"><span data-stu-id="899d9-361">The digit separator can appear anywhere in the constant.</span></span> <span data-ttu-id="899d9-362">对于十进制数字，通常将其用作千位分隔符：</span><span class="sxs-lookup"><span data-stu-id="899d9-362">For base 10 numbers, it would be common to use it as a thousands separator:</span></span>

[!code-csharp[LargeIntegers](../../../samples/snippets/csharp/new-in-7/Program.cs#34_LargeIntegers "Large integer")]

<span data-ttu-id="899d9-363">数字分隔符也可以与 `decimal`、`float` 和 `double` 类型一起使用：</span><span class="sxs-lookup"><span data-stu-id="899d9-363">The digit separator can be used with `decimal`, `float` and `double` types as well:</span></span>

[!code-csharp[OtherConstants](../../../samples/snippets/csharp/new-in-7/Program.cs#35_OtherConstants "non-integral constants")]

<span data-ttu-id="899d9-364">综观来说，你可以声明可读性更强的数值常量。</span><span class="sxs-lookup"><span data-stu-id="899d9-364">Taken together, you can declare numeric constants with much more readability.</span></span>
