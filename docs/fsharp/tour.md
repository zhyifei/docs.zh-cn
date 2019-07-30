---
title: F# 概览
description: 通过示例来介绍 F# 语言中的一些主要特性。
ms.date: 11/06/2018
ms.openlocfilehash: 35b811b580cd7c3b4a620f45b602150a92479052
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630070"
---
# <a name="tour-of-f"></a><span data-ttu-id="859ce-103">F 教程\#</span><span class="sxs-lookup"><span data-stu-id="859ce-103">Tour of F\#</span></span>

<span data-ttu-id="859ce-104">了解 F# 语言的最好方式就是阅读和编写 F# 代码。</span><span class="sxs-lookup"><span data-stu-id="859ce-104">The best way to learn about F# is to read and write F# code.</span></span> <span data-ttu-id="859ce-105">本文将介绍 F# 语言的一些关键特性，并提供一些可以在计算机上执行的代码片段。</span><span class="sxs-lookup"><span data-stu-id="859ce-105">This article will act as a tour through some of the key features of the F# language and give you some code snippets that you can execute on your machine.</span></span> <span data-ttu-id="859ce-106">若要了解如何设置开发环境，请查看[入门](./tutorials/getting-started/index.md)。</span><span class="sxs-lookup"><span data-stu-id="859ce-106">To learn about setting up a development environment, check out [Getting Started](./tutorials/getting-started/index.md).</span></span>

<span data-ttu-id="859ce-107">F# 中有两个主要概念：函数和类型。</span><span class="sxs-lookup"><span data-stu-id="859ce-107">There are two primary concepts in F#: functions and types.</span></span>  <span data-ttu-id="859ce-108">本文主要介绍该语言中属于这两个概念范畴的特性。</span><span class="sxs-lookup"><span data-stu-id="859ce-108">This tour will emphasize features of the language which fall into these two concepts.</span></span>

## <a name="executing-the-code-online"></a><span data-ttu-id="859ce-109">在线执行代码</span><span class="sxs-lookup"><span data-stu-id="859ce-109">Executing the code online</span></span>

<span data-ttu-id="859ce-110">如果未在计算机F#上安装, 则可以在浏览器[ F# ](https://tryfsharp.fsbolero.io/)中执行 WebAssembly 中的所有示例。</span><span class="sxs-lookup"><span data-stu-id="859ce-110">If you don't have F# installed on your machine, you can execute all of the samples in your browser with [Try F# on WebAssembly](https://tryfsharp.fsbolero.io/).</span></span> <span data-ttu-id="859ce-111">Fable 是一种用于直接在浏览器中执行 F# 的方言。</span><span class="sxs-lookup"><span data-stu-id="859ce-111">Fable is a dialect of F# that executes directly in your browser.</span></span> <span data-ttu-id="859ce-112">若要在 REPL 中查看以下示例，请查看 Fable REPL 左侧菜单栏中的“示例”>“了解”>“F# 概览”  。</span><span class="sxs-lookup"><span data-stu-id="859ce-112">To view the samples that follow in the REPL, check out **Samples > Learn > Tour of F#** in the left-hand menu bar of the Fable REPL.</span></span>

## <a name="functions-and-modules"></a><span data-ttu-id="859ce-113">函数和模块</span><span class="sxs-lookup"><span data-stu-id="859ce-113">Functions and Modules</span></span>

<span data-ttu-id="859ce-114">任何 F# 程序的最基本的片段都是由***函数***组织成的***模块***。</span><span class="sxs-lookup"><span data-stu-id="859ce-114">The most fundamental pieces of any F# program are ***functions*** organized into ***modules***.</span></span>  <span data-ttu-id="859ce-115">[函数](./language-reference/functions/index.md)会处理输入并产生输出，并被组织到[模块](./language-reference/modules.md)中，模块是在 F # 中对事物进行归组的主要方式。</span><span class="sxs-lookup"><span data-stu-id="859ce-115">[Functions](./language-reference/functions/index.md) perform work on inputs to produce outputs, and they are organized under [Modules](./language-reference/modules.md), which are the primary way you group things in F#.</span></span>  <span data-ttu-id="859ce-116">它们是使用[`let`绑定](./language-reference/functions/let-bindings.md)定义对的，后者为函数提供一个名称并定义其参数。</span><span class="sxs-lookup"><span data-stu-id="859ce-116">They are defined using the [`let` binding](./language-reference/functions/let-bindings.md), which give the function a name and define its arguments.</span></span>

[!code-fsharp[BasicFunctions](../../samples/snippets/fsharp/tour.fs#L101-L133)]

<span data-ttu-id="859ce-117">`let` 绑定也是将值绑定到名称的方式，类似于其他语言中的变量。</span><span class="sxs-lookup"><span data-stu-id="859ce-117">`let` bindings are also how you bind a value to a name, similar to a variable in other languages.</span></span>  <span data-ttu-id="859ce-118">默认情况下`let` 绑定是***不可变***的，这意味着，一旦值或函数绑定到一个名称，它不能在原位更改。</span><span class="sxs-lookup"><span data-stu-id="859ce-118">`let` bindings are ***immutable*** by default, which means that once a value or function is bound to a name, it cannot be changed in-place.</span></span>  <span data-ttu-id="859ce-119">这与在其他语言中的变量相反，这些变量是***可变的***，意味着它们的值可以在任何位置任何时间被更改。</span><span class="sxs-lookup"><span data-stu-id="859ce-119">This is in contrast to variables in other languages, which are ***mutable***, meaning their values can be changed at any point in time.</span></span>  <span data-ttu-id="859ce-120">如果需要一个可变的绑定，可以使用 `let mutable ...` 语法。</span><span class="sxs-lookup"><span data-stu-id="859ce-120">If you require a mutable binding, you can use `let mutable ...` syntax.</span></span>

[!code-fsharp[Immutability](../../samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a><span data-ttu-id="859ce-121">数值、布尔值和字符串</span><span class="sxs-lookup"><span data-stu-id="859ce-121">Numbers, Booleans, and Strings</span></span>

<span data-ttu-id="859ce-122">F# 是一种 .NET 语言，支持 .NET 中包含的相同的基本[基元类型](./language-reference/primitive-types.md)。</span><span class="sxs-lookup"><span data-stu-id="859ce-122">As a .NET language, F# supports the same underlying [primitive types](./language-reference/primitive-types.md) that exist in .NET.</span></span>

<span data-ttu-id="859ce-123">下面是各种数值类型在 F# 中的表示方式：</span><span class="sxs-lookup"><span data-stu-id="859ce-123">Here is how various numeric types are represented in F#:</span></span>

[!code-fsharp[Numbers](../../samples/snippets/fsharp/tour.fs#L49-L68)]

<span data-ttu-id="859ce-124">下面是布尔值的表示和基本条件逻辑的执行方式：</span><span class="sxs-lookup"><span data-stu-id="859ce-124">Here's what Boolean values and performing basic conditional logic looks like:</span></span>

[!code-fsharp[Bools](../../samples/snippets/fsharp/tour.fs#L142-L152)]

<span data-ttu-id="859ce-125">下面是[字符串](./language-reference/strings.md)的基本操作方式：</span><span class="sxs-lookup"><span data-stu-id="859ce-125">And here's what basic [string](./language-reference/strings.md) manipulation looks like:</span></span>

[!code-fsharp[Strings](../../samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a><span data-ttu-id="859ce-126">元组</span><span class="sxs-lookup"><span data-stu-id="859ce-126">Tuples</span></span>

<span data-ttu-id="859ce-127">[元组](./language-reference/tuples.md)是 F# 中的重要内容。</span><span class="sxs-lookup"><span data-stu-id="859ce-127">[Tuples](./language-reference/tuples.md) are a big deal in F#.</span></span>  <span data-ttu-id="859ce-128">它们是一组未命名但已排序的值，可将其视为值进行处理。</span><span class="sxs-lookup"><span data-stu-id="859ce-128">They are a grouping of unnamed, but ordered values, that can be treated as values themselves.</span></span>  <span data-ttu-id="859ce-129">将它们视为聚合自其他值的值。</span><span class="sxs-lookup"><span data-stu-id="859ce-129">Think of them as values which are aggregated from other values.</span></span>  <span data-ttu-id="859ce-130">元组有许多用途，比如，以便捷方式从函数返回多个值，或对值进行分组以提供暂时的便利。</span><span class="sxs-lookup"><span data-stu-id="859ce-130">They have many uses, such as conveniently returning multiple values from a function, or grouping values for some ad-hoc convenience.</span></span>

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L186-L203)]

<span data-ttu-id="859ce-131">从 F# 4.1 开始，还可以创建 `struct` 元组。</span><span class="sxs-lookup"><span data-stu-id="859ce-131">As of F# 4.1, you can also create `struct` tuples.</span></span>  <span data-ttu-id="859ce-132">它们可以与 C# 7/Visual Basic 15 元组完全交互，因为后者也是 `struct` 元组：</span><span class="sxs-lookup"><span data-stu-id="859ce-132">These also interoperate fully with C#7/Visual Basic 15 tuples, which are also `struct` tuples:</span></span>

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L205-L218)]

<span data-ttu-id="859ce-133">请务必注意，由于 `struct` 元组是值类型，它们不能隐式转换为引用元组，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="859ce-133">It's important to note that because `struct` tuples are value types, they cannot be implicitly converted to reference tuples, or vice versa.</span></span>  <span data-ttu-id="859ce-134">必须在引用元组和 struct 元组之间进行显式转换。</span><span class="sxs-lookup"><span data-stu-id="859ce-134">You must explicitly convert between a reference and struct tuple.</span></span>

## <a name="pipelines-and-composition"></a><span data-ttu-id="859ce-135">管道和组合</span><span class="sxs-lookup"><span data-stu-id="859ce-135">Pipelines and Composition</span></span>

<span data-ttu-id="859ce-136">在 F# 中处理数据时，会广泛使用 `|>` 等管道运算符。</span><span class="sxs-lookup"><span data-stu-id="859ce-136">Pipe operators such as `|>` are used extensively when processing data in F#.</span></span> <span data-ttu-id="859ce-137">这些运算符是使你能够灵活建立函数的“管道”的函数。</span><span class="sxs-lookup"><span data-stu-id="859ce-137">These operators are functions that allow you to establish "pipelines" of functions in a flexible manner.</span></span> <span data-ttu-id="859ce-138">下面的示例将完整演示如利用这些运算符来构建一个简单的功能管道：</span><span class="sxs-lookup"><span data-stu-id="859ce-138">The following example walks through how you can take advantage of these operators to build a simple functional pipeline:</span></span>

[!code-fsharp[Pipelines](../../samples/snippets/fsharp/tour.fs#L227-L282)]

<span data-ttu-id="859ce-139">上面的示例使用了 F# 的许多特性，包括列表处理函数、头等函数和[偏函数应用](./language-reference/functions/index.md#partial-application-of-arguments)。</span><span class="sxs-lookup"><span data-stu-id="859ce-139">The previous sample made use of many features of F#, including list processing functions, first-class functions, and [partial application](./language-reference/functions/index.md#partial-application-of-arguments).</span></span> <span data-ttu-id="859ce-140">尽管深入理解所有这些概念有难度，但有一点应该非常明显 - 在构建管道时可以轻松使用函数来处理数据。</span><span class="sxs-lookup"><span data-stu-id="859ce-140">Although a deep understanding of each of those concepts can become somewhat advanced, it should be clear how easily functions can be used to process data when building pipelines.</span></span>

## <a name="lists-arrays-and-sequences"></a><span data-ttu-id="859ce-141">列表、数组和序列</span><span class="sxs-lookup"><span data-stu-id="859ce-141">Lists, Arrays, and Sequences</span></span>

<span data-ttu-id="859ce-142">列表、数组和序列是 F# 核心库中的三个主要集合类型。</span><span class="sxs-lookup"><span data-stu-id="859ce-142">Lists, Arrays, and Sequences are three primary collection types in the F# core library.</span></span>

<span data-ttu-id="859ce-143">[列表](./language-reference/lists.md)是相同类型元素的有序、不可变集合。</span><span class="sxs-lookup"><span data-stu-id="859ce-143">[Lists](./language-reference/lists.md) are ordered, immutable collections of elements of the same type.</span></span>  <span data-ttu-id="859ce-144">“列表”是单向链接列表，即它们旨在用于枚举，较大时则不适合用于随机访问和串联。</span><span class="sxs-lookup"><span data-stu-id="859ce-144">They are singly-linked lists, which means they are meant for enumeration, but a poor choice for random access and concatenation if they're large.</span></span>  <span data-ttu-id="859ce-145">请注意，这与其他常用语言中的“列表”相反，那些语言通常不使用单向链接列表表示“列表”。</span><span class="sxs-lookup"><span data-stu-id="859ce-145">This in contrast to Lists in other popular languages, which typically do not use a singly-linked list to represent Lists.</span></span>

[!code-fsharp[Lists](../../samples/snippets/fsharp/tour.fs#L309-L359)]

<span data-ttu-id="859ce-146">[数组](./language-reference/arrays.md)是具有相同类型的元素的固定大小、*可变*集合。</span><span class="sxs-lookup"><span data-stu-id="859ce-146">[Arrays](./language-reference/arrays.md) are fixed-size, *mutable* collections of elements of the same type.</span></span>  <span data-ttu-id="859ce-147">它们支持快速随机访问的元素，并不是 F# 列表，因为它们是只需连续内存块的速度更快。</span><span class="sxs-lookup"><span data-stu-id="859ce-147">They support fast random access of elements, and are faster than F# lists because they are just contiguous blocks of memory.</span></span>

[!code-fsharp[Arrays](../../samples/snippets/fsharp/tour.fs#L368-L407)]

<span data-ttu-id="859ce-148">[序列](./language-reference/sequences.md)是一系列逻辑元素, 它们都属于同一类型。</span><span class="sxs-lookup"><span data-stu-id="859ce-148">[Sequences](./language-reference/sequences.md) are a logical series of elements, all of the same type.</span></span>  <span data-ttu-id="859ce-149">这些是比列表和数组更通用的类型, 可以是 "视图" 到任何逻辑序列的元素。</span><span class="sxs-lookup"><span data-stu-id="859ce-149">These are a more general type than Lists and Arrays, capable of being your "view" into any logical series of elements.</span></span>  <span data-ttu-id="859ce-150">它们还会显得很明显, 因为它们可能是***延迟***的, 也就是说, 仅当需要时才可以计算元素。</span><span class="sxs-lookup"><span data-stu-id="859ce-150">They also stand out because they can be ***lazy***, which means that elements can be computed only when they are needed.</span></span>

[!code-fsharp[Sequences](../../samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a><span data-ttu-id="859ce-151">递归函数</span><span class="sxs-lookup"><span data-stu-id="859ce-151">Recursive Functions</span></span>

<span data-ttu-id="859ce-152">在 F# 中，对元素集合与元素序列的操作往往通过[递归](./language-reference/functions/index.md#recursive-functions)完成。</span><span class="sxs-lookup"><span data-stu-id="859ce-152">Processing collections or sequences of elements is typically done with [recursion](./language-reference/functions/index.md#recursive-functions) in F#.</span></span>  <span data-ttu-id="859ce-153">尽管 F# 支持循环和命令式编程，但递归仍然是首选，因为它更容易保证正确性。</span><span class="sxs-lookup"><span data-stu-id="859ce-153">Although F# has support for loops and imperative programming, recursion is preferred because it is easier to guarantee correctness.</span></span>

> [!NOTE]
> <span data-ttu-id="859ce-154">下面的示例利用了通过 `match` 表达式匹配的模式。</span><span class="sxs-lookup"><span data-stu-id="859ce-154">The following example makes use of the pattern matching via the `match` expression.</span></span>  <span data-ttu-id="859ce-155">本文后面部分将介绍这一构造。</span><span class="sxs-lookup"><span data-stu-id="859ce-155">This fundamental construct is covered later in this article.</span></span>

[!code-fsharp[RecursiveFunctions](../../samples/snippets/fsharp/tour.fs#L461-L500)]

<span data-ttu-id="859ce-156">F# 还完全支持尾调用优化，这是一种优化递归调用并使其与循环构造具有相同速率的方式。</span><span class="sxs-lookup"><span data-stu-id="859ce-156">F# also has full support for Tail Call Optimization, which is a way to optimize recursive calls so that they are just as fast as a loop construct.</span></span>

## <a name="record-and-discriminated-union-types"></a><span data-ttu-id="859ce-157">记录和可区分联合类型</span><span class="sxs-lookup"><span data-stu-id="859ce-157">Record and Discriminated Union Types</span></span>

<span data-ttu-id="859ce-158">“记录”和“联合”是 F# 代码中使用的两种基本数据类型，它们通常是表示 F# 程序中数据的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="859ce-158">Record and Union types are two fundamental data types used in F# code, and are generally the best way to represent data in an F# program.</span></span>  <span data-ttu-id="859ce-159">尽管在这一点上它们与其他语言中的类很相似，但它们具有结构相等性语义，这是一个主要差异。</span><span class="sxs-lookup"><span data-stu-id="859ce-159">Although this makes them similar to classes in other languages, one of their primary differences is that they have structural equality semantics.</span></span>  <span data-ttu-id="859ce-160">这意味着它们“天生”就可比较，相等性则非常简单 - 只需检查一项是否等于另一项。</span><span class="sxs-lookup"><span data-stu-id="859ce-160">This means that they are "natively" comparable and equality is straightforward - just check if one is equal to the other.</span></span>

<span data-ttu-id="859ce-161">[记录](./language-reference/records.md)是包含成员（例如，方法）的命名值的聚合。</span><span class="sxs-lookup"><span data-stu-id="859ce-161">[Records](./language-reference/records.md) are an aggregate of named values, with optional members (such as methods).</span></span>  <span data-ttu-id="859ce-162">如果熟悉 C# 或 Java，便会发现“记录”类似于 POCO 或 POCO - 只是比它们多了结构相等性，而且更易于使用。</span><span class="sxs-lookup"><span data-stu-id="859ce-162">If you're familiar with C# or Java, then these should feel similar to POCOs or POJOs - just with structural equality and less ceremony.</span></span>

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L507-L559)]

<span data-ttu-id="859ce-163">从 F# 4.1 开始，还可以将“记录”表示为 `struct`。</span><span class="sxs-lookup"><span data-stu-id="859ce-163">As of F# 4.1, you can also represent Records as `struct`s.</span></span>  <span data-ttu-id="859ce-164">此操作通过 `[<Struct>]` 属性实现：</span><span class="sxs-lookup"><span data-stu-id="859ce-164">This is done with the `[<Struct>]` attribute:</span></span>

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L561-L568)]

<span data-ttu-id="859ce-165">[可区分联合 (DU)](./language-reference/discriminated-unions.md) 是一些值，可能是大量的已命名窗体或事例。</span><span class="sxs-lookup"><span data-stu-id="859ce-165">[Discriminated Unions (DUs)](./language-reference/discriminated-unions.md) are values which could be a number of named forms or cases.</span></span>  <span data-ttu-id="859ce-166">存储的该类型的值可能是多个非重复值之一。</span><span class="sxs-lookup"><span data-stu-id="859ce-166">Data stored in the type can be one of several distinct values.</span></span>

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L575-L631)]

<span data-ttu-id="859ce-167">你还可以使用 Du 作为*单用例可区分联合*, 以帮助进行基于基元类型的域建模。</span><span class="sxs-lookup"><span data-stu-id="859ce-167">You can also use DUs as *Single-Case Discriminated Unions*, to help with domain modeling over primitive types.</span></span>  <span data-ttu-id="859ce-168">通常情况下, 字符串和其他基元类型用于表示某些内容, 因此具有特定的含义。</span><span class="sxs-lookup"><span data-stu-id="859ce-168">Often times, strings and other primitive types are used to represent something, and are thus given a particular meaning.</span></span>  <span data-ttu-id="859ce-169">但是, 仅使用数据的基元表示形式可能会导致错误地分配不正确的值!</span><span class="sxs-lookup"><span data-stu-id="859ce-169">However, using only the primitive representation of the data can result in mistakenly assigning an incorrect value!</span></span>  <span data-ttu-id="859ce-170">将每种类型的信息表示为不同的单用例联合可在这种情况下强制执行正确性。</span><span class="sxs-lookup"><span data-stu-id="859ce-170">Representing each type of information as a distinct single-case union can enforce correctness in this scenario.</span></span>

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L633-L654)]

<span data-ttu-id="859ce-171">如上面的示例所示，若要获取单用例 DU 的基础值，则必须显式将其解包。</span><span class="sxs-lookup"><span data-stu-id="859ce-171">As the above sample demonstrates, to get the underlying value in a single-case Discriminated Union, you must explicitly unwrap it.</span></span>

<span data-ttu-id="859ce-172">此外，DU 还支持递归定义，使你可以轻松地表示树和本质上的递归数据。</span><span class="sxs-lookup"><span data-stu-id="859ce-172">Additionally, DUs also support recursive definitions, allowing you to easily represent trees and inherently recursive data.</span></span>  <span data-ttu-id="859ce-173">例如，下面演示了如何使用 `exists` 和 `insert` 函数表示二进制文件搜索树。</span><span class="sxs-lookup"><span data-stu-id="859ce-173">For example, here's how you can represent a Binary Search Tree with `exists` and `insert` functions.</span></span>

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L656-L683)]

<span data-ttu-id="859ce-174">由于 DU 可以表示该数据类型的树中的递归结构，因此对此类递归结构执行操作非常简单并且能保证正确性。</span><span class="sxs-lookup"><span data-stu-id="859ce-174">Because DUs allow you to represent the recursive structure of the tree in the data type, operating on this recursive structure is straightforward and guarantees correctness.</span></span>  <span data-ttu-id="859ce-175">模式匹配中也支持此方法，如下所示。</span><span class="sxs-lookup"><span data-stu-id="859ce-175">It is also supported in pattern matching, as shown below.</span></span>

<span data-ttu-id="859ce-176">此外，可以利用 `[<Struct>]` 属性将 DU 表示为 `struct`：</span><span class="sxs-lookup"><span data-stu-id="859ce-176">Additionally, you can represent DUs as `struct`s with the `[<Struct>]` attribute:</span></span>

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L685-L696)]

<span data-ttu-id="859ce-177">但是，执行此操作时要牢记以下两个关键事项：</span><span class="sxs-lookup"><span data-stu-id="859ce-177">However, there are two key things to keep in mind when doing so:</span></span>

1. <span data-ttu-id="859ce-178">struct DU 不能以递归方式定义。</span><span class="sxs-lookup"><span data-stu-id="859ce-178">A struct DU cannot be recursively-defined.</span></span>
2. <span data-ttu-id="859ce-179">struct DU 的每个事例必须具有唯一的标识符。</span><span class="sxs-lookup"><span data-stu-id="859ce-179">A struct DU must have unique names for each of its cases.</span></span>

<span data-ttu-id="859ce-180">未能遵循上述注意事项将导致编译错误。</span><span class="sxs-lookup"><span data-stu-id="859ce-180">Failure to follow the above will result in a compilation error.</span></span>

## <a name="pattern-matching"></a><span data-ttu-id="859ce-181">模式匹配</span><span class="sxs-lookup"><span data-stu-id="859ce-181">Pattern Matching</span></span>

<span data-ttu-id="859ce-182">[模式匹配](./language-reference/pattern-matching.md)是 F# 语言的特性，可确保对 F# 类型执行操作时的正确性。</span><span class="sxs-lookup"><span data-stu-id="859ce-182">[Pattern Matching](./language-reference/pattern-matching.md) is the F# language feature which enables correctness for operating on F# types.</span></span>  <span data-ttu-id="859ce-183">在上述示例中，你可能已经注意到了很多 `match x with ...` 语法。</span><span class="sxs-lookup"><span data-stu-id="859ce-183">In the above samples, you probably noticed quite a bit of `match x with ...` syntax.</span></span>  <span data-ttu-id="859ce-184">使用某个数据类型时，此构造可允许编译器（可以理解数据类型的“形状”）通过所谓的穷举模式匹配来强制你考虑所有可能出现的情况。</span><span class="sxs-lookup"><span data-stu-id="859ce-184">This construct allows the compiler, which can understand the "shape" of data types, to force you to account for all possible cases when using a data type through what is known as Exhaustive Pattern Matching.</span></span>  <span data-ttu-id="859ce-185">此方法能有效确保正确性，可以将通常在运行时考虑的问题引入编译时。</span><span class="sxs-lookup"><span data-stu-id="859ce-185">This is incredibly powerful for correctness, and can be cleverly used to "lift" what would normally be a runtime concern into compile-time.</span></span>

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L705-L742)]

<span data-ttu-id="859ce-186">你可能注意到的是使用`_`模式。</span><span class="sxs-lookup"><span data-stu-id="859ce-186">Something you may have noticed is the use of the `_` pattern.</span></span>  <span data-ttu-id="859ce-187">这称为[通配符模式](./language-reference/pattern-matching.md#wildcard-pattern), 这是一种 "我不在意什么内容" 的方法。</span><span class="sxs-lookup"><span data-stu-id="859ce-187">This is known as the [Wildcard Pattern](./language-reference/pattern-matching.md#wildcard-pattern), which is a way of saying "I don't care what something is".</span></span>  <span data-ttu-id="859ce-188">尽管很方便, 但如果不小心使用`_`, 则可能会意外绕过穷举模式匹配, 并且不再受益于编译时操作。</span><span class="sxs-lookup"><span data-stu-id="859ce-188">Although convenient, you can accidentally bypass Exhaustive Pattern Matching and no longer benefit from compile-time enforcements if you aren't careful in using `_`.</span></span>  <span data-ttu-id="859ce-189">当您在模式匹配时不关心分解类型的某些部分时, 最好使用此方法; 当您枚举了模式匹配表达式中的所有有意义的事例时, 最好使用该方法。</span><span class="sxs-lookup"><span data-stu-id="859ce-189">It is best used when you don't care about certain pieces of a decomposed type when pattern matching, or the final clause when you have enumerated all meaningful cases in a pattern matching expression.</span></span>

<span data-ttu-id="859ce-190">[活动模式](./language-reference/active-patterns.md)是另一个功能强大的构造, 可与模式匹配一起使用。</span><span class="sxs-lookup"><span data-stu-id="859ce-190">[Active Patterns](./language-reference/active-patterns.md) are another powerful construct to use with pattern matching.</span></span>  <span data-ttu-id="859ce-191">它们允许您将输入数据分区为自定义窗体, 并在模式匹配调用站点分解它们。</span><span class="sxs-lookup"><span data-stu-id="859ce-191">They allow you to partition input data into custom forms, decomposing them at the pattern match call site.</span></span>  <span data-ttu-id="859ce-192">它们也可以参数化, 从而允许将分区定义为函数。</span><span class="sxs-lookup"><span data-stu-id="859ce-192">They can also be parameterized, thus allowing to define the partition as a function.</span></span>  <span data-ttu-id="859ce-193">扩展前面的示例以支持活动模式, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="859ce-193">Expanding the previous example to support Active Patterns looks something like this:</span></span>

[!code-fsharp[ActivePatterns](../../samples/snippets/fsharp/tour.fs#L764-L786)]

## <a name="optional-types"></a><span data-ttu-id="859ce-194">可选类型</span><span class="sxs-lookup"><span data-stu-id="859ce-194">Optional Types</span></span>

<span data-ttu-id="859ce-195">可区分联合类型的一个特殊情况是选项类型，这是很有用，它是 F# 核心库的一部分。</span><span class="sxs-lookup"><span data-stu-id="859ce-195">One special case of Discriminated Union types is the Option Type, which is so useful that it's a part of the F# core library.</span></span>

<span data-ttu-id="859ce-196">[选项类型](./language-reference/options.md)是一种类型, 该类型表示以下两种情况之一: 值或根本不显示任何内容。</span><span class="sxs-lookup"><span data-stu-id="859ce-196">[The Option Type](./language-reference/options.md) is a type which represents one of two cases: a value, or nothing at all.</span></span>  <span data-ttu-id="859ce-197">它用于某个值可能因特定操作而不会产生的任何情况。</span><span class="sxs-lookup"><span data-stu-id="859ce-197">It is used in any scenario where a value may or may not result from a particular operation.</span></span>  <span data-ttu-id="859ce-198">这会强制你考虑这两种情况, 使其成为编译时问题, 而不是运行时问题。</span><span class="sxs-lookup"><span data-stu-id="859ce-198">This then forces you to account for both cases, making it a compile-time concern rather than a runtime concern.</span></span>  <span data-ttu-id="859ce-199">这通常用于 api 中, 其中`null`用于表示 "无", 从而避免了`NullReferenceException`在许多情况下需要担心的情况。</span><span class="sxs-lookup"><span data-stu-id="859ce-199">These are often used in APIs where `null` is used to represent "nothing" instead, thus eliminating the need to worry about `NullReferenceException` in many circumstances.</span></span>

[!code-fsharp[Options](../../samples/snippets/fsharp/tour.fs#L789-L814)]

## <a name="units-of-measure"></a><span data-ttu-id="859ce-200">度量单位</span><span class="sxs-lookup"><span data-stu-id="859ce-200">Units of Measure</span></span>

<span data-ttu-id="859ce-201">F# 类型系统的一项独特功能是能够为通过度量单位的数字文本提供上下文。</span><span class="sxs-lookup"><span data-stu-id="859ce-201">One unique feature of F#'s type system is the ability to provide context for numeric literals through Units of Measure.</span></span>

<span data-ttu-id="859ce-202">[度量单位](./language-reference/units-of-measure.md)允许您将数值类型与单位 (例如计量) 相关联, 并使函数可对单元 (而不是数字文本) 执行工作。</span><span class="sxs-lookup"><span data-stu-id="859ce-202">[Units of Measure](./language-reference/units-of-measure.md) allow you to associate a numeric type to a unit, such as Meters, and have functions perform work on units rather than numeric literals.</span></span>  <span data-ttu-id="859ce-203">这使编译器能够验证传入的数值类型在特定上下文中是否有效, 从而消除了与此类工作相关的运行时错误。</span><span class="sxs-lookup"><span data-stu-id="859ce-203">This enables the compiler to verify that the types of numeric literals passed in make sense under a certain context, thus eliminating runtime errors associated with that kind of work.</span></span>

[!code-fsharp[UnitsOfMeasure](../../samples/snippets/fsharp/tour.fs#L817-L842)]

<span data-ttu-id="859ce-204">F# 核心库定义了许多的 SI 单位类型和单位转换。</span><span class="sxs-lookup"><span data-stu-id="859ce-204">The F# Core library defines many SI unit types and unit conversions.</span></span>  <span data-ttu-id="859ce-205">若要了解详细信息, 请查看[Microsoft.FSharp.Data.UnitSystems.SI 命名空间](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d)。</span><span class="sxs-lookup"><span data-stu-id="859ce-205">To learn more, check out the [Microsoft.FSharp.Data.UnitSystems.SI Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d).</span></span>

## <a name="classes-and-interfaces"></a><span data-ttu-id="859ce-206">类和接口</span><span class="sxs-lookup"><span data-stu-id="859ce-206">Classes and Interfaces</span></span>

<span data-ttu-id="859ce-207">F# 还具有对.NET 类的完全支持[接口](./language-reference/interfaces.md)，[抽象类](./language-reference/abstract-classes.md)，[继承](./language-reference/inheritance.md)，依次类推。</span><span class="sxs-lookup"><span data-stu-id="859ce-207">F# also has full support for .NET classes, [Interfaces](./language-reference/interfaces.md), [Abstract Classes](./language-reference/abstract-classes.md), [Inheritance](./language-reference/inheritance.md), and so on.</span></span>

<span data-ttu-id="859ce-208">[类](./language-reference/classes.md)是表示 .net 对象的类型, 这些对象可以具有属性、方法和事件作为其[成员](./language-reference/members/index.md)。</span><span class="sxs-lookup"><span data-stu-id="859ce-208">[Classes](./language-reference/classes.md) are types that represent .NET objects, which can have properties, methods, and events as its [Members](./language-reference/members/index.md).</span></span>

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L845-L880)]

<span data-ttu-id="859ce-209">定义泛型类也非常简单。</span><span class="sxs-lookup"><span data-stu-id="859ce-209">Defining generic classes is also very straightforward.</span></span>

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L883-L908)]

<span data-ttu-id="859ce-210">若要实现接口, 可以使用`interface ... with`语法或[对象表达式](./language-reference/object-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="859ce-210">To implement an Interface, you can use either `interface ... with` syntax or an [Object Expression](./language-reference/object-expressions.md).</span></span>

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L911-L934)]

## <a name="which-types-to-use"></a><span data-ttu-id="859ce-211">要使用的类型</span><span class="sxs-lookup"><span data-stu-id="859ce-211">Which Types to Use</span></span>

<span data-ttu-id="859ce-212">类、记录、可区分联合和元组的存在导致了重要问题: 应使用哪一个？</span><span class="sxs-lookup"><span data-stu-id="859ce-212">The presence of Classes, Records, Discriminated Unions, and Tuples leads to an important question: which should you use?</span></span>  <span data-ttu-id="859ce-213">与生活中的大多数操作一样, 答案取决于你的情况。</span><span class="sxs-lookup"><span data-stu-id="859ce-213">Like most everything in life, the answer depends on your circumstances.</span></span>

<span data-ttu-id="859ce-214">元组非常适合从函数返回多个值, 并使用临时值聚合作为值本身。</span><span class="sxs-lookup"><span data-stu-id="859ce-214">Tuples are great for returning multiple values from a function, and using an ad-hoc aggregate of values as a value itself.</span></span>

<span data-ttu-id="859ce-215">记录是元组中的 "单步执行", 其命名标签和对可选成员的支持。</span><span class="sxs-lookup"><span data-stu-id="859ce-215">Records are a "step up" from Tuples, having named labels and support for optional members.</span></span>  <span data-ttu-id="859ce-216">它们非常适用于通过您的程序传输的数据的低计划表示形式。</span><span class="sxs-lookup"><span data-stu-id="859ce-216">They are great for a low-ceremony representation of data in-transit through your program.</span></span>  <span data-ttu-id="859ce-217">由于它们具有结构相等性, 因此它们可用于比较。</span><span class="sxs-lookup"><span data-stu-id="859ce-217">Because they have structural equality, they are easy to use with comparison.</span></span>

<span data-ttu-id="859ce-218">可区分联合具有许多用途, 但核心好处是能够将它们与模式匹配一起使用, 以考虑数据可以具有的所有可能的 "形状"。</span><span class="sxs-lookup"><span data-stu-id="859ce-218">Discriminated Unions have many uses, but the core benefit is to be able to utilize them in conjunction with Pattern Matching to account for all possible "shapes" that a data can have.</span></span>  

<span data-ttu-id="859ce-219">类对于大量原因非常有用, 例如, 当你需要表示信息并将该信息绑定到功能时。</span><span class="sxs-lookup"><span data-stu-id="859ce-219">Classes are great for a huge number of reasons, such as when you need to represent information and also tie that information to functionality.</span></span>  <span data-ttu-id="859ce-220">作为经验法则, 当你具有在概念上与某些数据关联的功能时, 使用类和面向对象编程的原则是一项巨大的好处。</span><span class="sxs-lookup"><span data-stu-id="859ce-220">As a rule of thumb, when you have functionality which is conceptually tied to some data, using Classes and the principles of Object-Oriented Programming is a big benefit.</span></span>  <span data-ttu-id="859ce-221">与C#和 Visual Basic 互操作时, 类也是首选的数据类型, 因为这些语言几乎都使用类。</span><span class="sxs-lookup"><span data-stu-id="859ce-221">Classes are also the preferred data type when interoperating with C# and Visual Basic, as these languages use classes for nearly everything.</span></span>

## <a name="next-steps"></a><span data-ttu-id="859ce-222">后续步骤</span><span class="sxs-lookup"><span data-stu-id="859ce-222">Next Steps</span></span>

<span data-ttu-id="859ce-223">现在，已了解的一些主要功能的语言，您应准备好开始编写第一个 F# 程序 ！</span><span class="sxs-lookup"><span data-stu-id="859ce-223">Now that you've seen some of the primary features of the language, you should be ready to write your first F# programs!</span></span>  <span data-ttu-id="859ce-224">请查看[入门](./tutorials/getting-started/index.md), 了解如何设置开发环境并编写一些代码。</span><span class="sxs-lookup"><span data-stu-id="859ce-224">Check out [Getting Started](./tutorials/getting-started/index.md) to learn how to set up your development environment and write some code.</span></span>

<span data-ttu-id="859ce-225">用于了解详细信息的后续步骤可以是你喜欢的任何内容, 但建议你[在中F#介绍函数编程](./introduction-to-functional-programming/index.md), 以熟悉核心功能编程概念。</span><span class="sxs-lookup"><span data-stu-id="859ce-225">The next steps for learning more can be whatever you like, but we recommend [Introduction to Functional Programming in F#](./introduction-to-functional-programming/index.md) to get comfortable with core Functional Programming concepts.</span></span>  <span data-ttu-id="859ce-226">这些将是在中构建 F# 中的可靠程序必不可少。</span><span class="sxs-lookup"><span data-stu-id="859ce-226">These will be essential in building robust programs in F#.</span></span>

<span data-ttu-id="859ce-227">此外，请查看[F# 语言参考](./language-reference/index.md)若要查看有关 F# 的概念内容全面集合。</span><span class="sxs-lookup"><span data-stu-id="859ce-227">Also, check out the [F# Language Reference](./language-reference/index.md) to see a comprehensive collection of conceptual content on F#.</span></span>
