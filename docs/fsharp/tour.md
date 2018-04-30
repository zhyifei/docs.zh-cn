---
title: '介绍 F # 的'
description: '检查某些 F # 编程语言中使用代码示例本教程的主要功能。'
author: cartermp
ms.author: phcart
ms.date: 02/28/2018
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 6821c74827b928cdd0c5aff101be4f9103986e3e
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="tour-of-f"></a><span data-ttu-id="69f7d-103">介绍 F # 的</span><span class="sxs-lookup"><span data-stu-id="69f7d-103">Tour of F#</span></span> #

<span data-ttu-id="69f7d-104">若要了解有关 F # 的最佳方法是读取和写入 F # 代码。</span><span class="sxs-lookup"><span data-stu-id="69f7d-104">The best way to learn about F# is to read and write F# code.</span></span>  <span data-ttu-id="69f7d-105">本文将充当浏览了某些 F # 语言的主要功能并使你可以在您的计算机执行某些代码片段。</span><span class="sxs-lookup"><span data-stu-id="69f7d-105">This article will act as a tour through some of the key features of the F# language and give you some code snippets that you can execute on your machine.</span></span>  <span data-ttu-id="69f7d-106">若要了解有关设置开发环境的信息，请查看[入门](tutorials/getting-started/index.md)。</span><span class="sxs-lookup"><span data-stu-id="69f7d-106">To learn about setting up a development environment, check out [Getting Started](tutorials/getting-started/index.md).</span></span>

<span data-ttu-id="69f7d-107">F # 中有两个主要概念： 函数和类型。</span><span class="sxs-lookup"><span data-stu-id="69f7d-107">There are two primary concepts in F#: functions and types.</span></span>  <span data-ttu-id="69f7d-108">本教程将强调的语言功能，这些功能划分为这两个概念。</span><span class="sxs-lookup"><span data-stu-id="69f7d-108">This tour will emphasize features of the language which fall into these two concepts.</span></span>

## <a name="functions-and-modules"></a><span data-ttu-id="69f7d-109">函数和模块</span><span class="sxs-lookup"><span data-stu-id="69f7d-109">Functions and Modules</span></span>

<span data-ttu-id="69f7d-110">任何 F # 程序的最基本的块是***函数***组织成***模块***。</span><span class="sxs-lookup"><span data-stu-id="69f7d-110">The most fundamental pieces of any F# program are ***functions*** organized into ***modules***.</span></span>  <span data-ttu-id="69f7d-111">[函数](language-reference/functions/index.md)输入生成输出，在执行工作和其下组织[模块](language-reference/modules.md)，这是组 F # 中的操作的主要方法。</span><span class="sxs-lookup"><span data-stu-id="69f7d-111">[Functions](language-reference/functions/index.md) perform work on inputs to produce outputs, and they are organized under [Modules](language-reference/modules.md), which are the primary way you group things in F#.</span></span>  <span data-ttu-id="69f7d-112">它们定义使用[`let`绑定](language-reference/functions/let-bindings.md)，它为函数提供一个名称，并定义其自变量。</span><span class="sxs-lookup"><span data-stu-id="69f7d-112">They are defined using the [`let` binding](language-reference/functions/let-bindings.md), which give the function a name and define its arguments.</span></span>

[!code-fsharp[BasicFunctions](../../samples/snippets/fsharp/tour.fs#L101-L133)]

<span data-ttu-id="69f7d-113">`let` 绑定也是如何将一个值绑定到类似于其他语言中的变量的名称。</span><span class="sxs-lookup"><span data-stu-id="69f7d-113">`let` bindings are also how you bind a value to a name, similar to a variable in other languages.</span></span>  <span data-ttu-id="69f7d-114">`let` 绑定是***不可变***默认情况下，这意味着，一旦值或函数绑定到一个名称，它不能更改在原位。</span><span class="sxs-lookup"><span data-stu-id="69f7d-114">`let` bindings are ***immutable*** by default, which means that once a value or function is bound to a name, it cannot be changed in-place.</span></span>  <span data-ttu-id="69f7d-115">这是在其他语言中，这些变量相反的***可变***，这意味着它们的值可以更改的任何时刻时间。</span><span class="sxs-lookup"><span data-stu-id="69f7d-115">This is in contrast to variables in other languages, which are ***mutable***, meaning their values can be changed at any point in time.</span></span>  <span data-ttu-id="69f7d-116">如果你需要使用可变绑定，则可以使用`let mutable ...`语法。</span><span class="sxs-lookup"><span data-stu-id="69f7d-116">If you require a mutable binding, you can use `let mutable ...` syntax.</span></span>

[!code-fsharp[Immutability](../../samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a><span data-ttu-id="69f7d-117">数字、 布尔值和字符串</span><span class="sxs-lookup"><span data-stu-id="69f7d-117">Numbers, Booleans, and Strings</span></span>

<span data-ttu-id="69f7d-118">作为一种.NET 语言，F # 支持相同的基础[基元类型](language-reference/primitive-types.md).NET 中存在。</span><span class="sxs-lookup"><span data-stu-id="69f7d-118">As a .NET language, F# supports the same underlying [primitive types](language-reference/primitive-types.md) that exist in .NET.</span></span>

<span data-ttu-id="69f7d-119">下面是如何各种数值类型表示在 F # 中：</span><span class="sxs-lookup"><span data-stu-id="69f7d-119">Here is how various numeric types are represented in F#:</span></span>

[!code-fsharp[Numbers](../../samples/snippets/fsharp/tour.fs#L49-L68)]

<span data-ttu-id="69f7d-120">下面是布尔值和执行基本的条件逻辑如下所示：</span><span class="sxs-lookup"><span data-stu-id="69f7d-120">Here's what Boolean values and performing basic conditional logic looks like:</span></span>

[!code-fsharp[Bools](../../samples/snippets/fsharp/tour.fs#L142-L152)]

<span data-ttu-id="69f7d-121">这是什么 basic[字符串](language-reference/strings.md)操作如下所示：</span><span class="sxs-lookup"><span data-stu-id="69f7d-121">And here's what basic [string](language-reference/strings.md) manipulation looks like:</span></span>

[!code-fsharp[Strings](../../samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a><span data-ttu-id="69f7d-122">元组</span><span class="sxs-lookup"><span data-stu-id="69f7d-122">Tuples</span></span>

<span data-ttu-id="69f7d-123">[元组](language-reference/tuples.md)是 F # 中了不起。</span><span class="sxs-lookup"><span data-stu-id="69f7d-123">[Tuples](language-reference/tuples.md) are a big deal in F#.</span></span>  <span data-ttu-id="69f7d-124">它们是未命名，但有序值，可以被视为值本身的分组。</span><span class="sxs-lookup"><span data-stu-id="69f7d-124">They are a grouping of unnamed, but ordered values, that can be treated as values themselves.</span></span>  <span data-ttu-id="69f7d-125">可以将它们视为汇总从其他值的值。</span><span class="sxs-lookup"><span data-stu-id="69f7d-125">Think of them as values which are aggregated from other values.</span></span>  <span data-ttu-id="69f7d-126">它们有许多用途，例如方便地从一个函数，返回多个值或分组一些即席便利的值。</span><span class="sxs-lookup"><span data-stu-id="69f7d-126">They have many uses, such as conveniently returning multiple values from a function, or grouping values for some ad-hoc convenience.</span></span>

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L186-L203)]

<span data-ttu-id="69f7d-127">截至 F # 4.1 中，你可以创建`struct`元组。</span><span class="sxs-lookup"><span data-stu-id="69f7d-127">As of F# 4.1, you can also create `struct` tuples.</span></span>  <span data-ttu-id="69f7d-128">这些还与进行互操作完全 C# 7/Visual 基本 15 元组，也是`struct`元组：</span><span class="sxs-lookup"><span data-stu-id="69f7d-128">These also interoperate fully with C#7/Visual Basic 15 tuples, which are also `struct` tuples:</span></span>

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L205-L218)]

<span data-ttu-id="69f7d-129">务必请注意，因为`struct`元组是值类型，它们不能隐式转换以引用元组，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="69f7d-129">It's important to note that because `struct` tuples are value types, they cannot be implicitly converted to reference tuples, or vice versa.</span></span>  <span data-ttu-id="69f7d-130">你必须显式转换之间的引用和结构的元组。</span><span class="sxs-lookup"><span data-stu-id="69f7d-130">You must explicitly convert between a reference and struct tuple.</span></span>

## <a name="pipelines-and-composition"></a><span data-ttu-id="69f7d-131">管道和组合</span><span class="sxs-lookup"><span data-stu-id="69f7d-131">Pipelines and Composition</span></span>

<span data-ttu-id="69f7d-132">管道运算符 (`|>`， `<|`， `||>`， `<||`， `|||>`， `<|||`) 和组合运算符 (`>>`和`<<`) 处理 F # 中的数据时广泛使用。</span><span class="sxs-lookup"><span data-stu-id="69f7d-132">Pipe operators (`|>`, `<|`, `||>`, `<||`, `|||>`, `<|||`) and composition operators (`>>` and `<<`) are used extensively when processing data in F#.</span></span>  <span data-ttu-id="69f7d-133">这些运算符是可用于以灵活的方式建立"管道"的函数的函数。</span><span class="sxs-lookup"><span data-stu-id="69f7d-133">These operators are functions which allow you to establish "pipelines" of functions in a flexible manner.</span></span>  <span data-ttu-id="69f7d-134">下面的示例将指导你无法在如何充分利用这些运算符来生成简单的功能管道。</span><span class="sxs-lookup"><span data-stu-id="69f7d-134">The following example walks through how you could take advantage of these operators to build a simple functional pipeline.</span></span>

[!code-fsharp[Pipelines](../../samples/snippets/fsharp/tour.fs#L227-L300)]

<span data-ttu-id="69f7d-135">上面的示例中所做的许多 F # 的功能，包括列表处理功能，第一类函数的使用和[部分应用](language-reference/functions/index.md#partial-application-of-arguments)。</span><span class="sxs-lookup"><span data-stu-id="69f7d-135">The above sample made use of many features of F#, including list processing functions, first-class functions, and [partial application](language-reference/functions/index.md#partial-application-of-arguments).</span></span>  <span data-ttu-id="69f7d-136">尽管这些概念的深入了解可以变得有点高级，应该已经很明确如何轻松地使用函数来生成管道时处理数据。</span><span class="sxs-lookup"><span data-stu-id="69f7d-136">Although a deep understanding of each of those concepts can become somewhat advanced, it should be clear how easily functions can be used to process data when building pipelines.</span></span>

## <a name="lists-arrays-and-sequences"></a><span data-ttu-id="69f7d-137">列表、 数组和序列</span><span class="sxs-lookup"><span data-stu-id="69f7d-137">Lists, Arrays, and Sequences</span></span>

<span data-ttu-id="69f7d-138">列表、 数组和序列是 F # 核心库中的三个主要集合类型。</span><span class="sxs-lookup"><span data-stu-id="69f7d-138">Lists, Arrays, and Sequences are three primary collection types in the F# core library.</span></span>

<span data-ttu-id="69f7d-139">[列出](language-reference/lists.md)是相同类型的元素的有序的、 不可变集合。</span><span class="sxs-lookup"><span data-stu-id="69f7d-139">[Lists](language-reference/lists.md) are ordered, immutable collections of elements of the same type.</span></span>  <span data-ttu-id="69f7d-140">它们是单向链接列表中，这意味着它们必须为枚举，但随机访问和串联的不佳选择如果他们是大。</span><span class="sxs-lookup"><span data-stu-id="69f7d-140">They are singly-linked lists, which means they are meant for enumeration, but a poor choice for random access and concatenation if they're large.</span></span>  <span data-ttu-id="69f7d-141">这与其他流行的语言，通常不使用单向链接列表来表示列表中的列表。</span><span class="sxs-lookup"><span data-stu-id="69f7d-141">This in contrast to Lists in other popular languages, which typically do not use a singly-linked list to represent Lists.</span></span>

[!code-fsharp[Lists](../../samples/snippets/fsharp/tour.fs#L309-L359)]

<span data-ttu-id="69f7d-142">[数组](language-reference/arrays.md)是固定大小、*可变*相同类型的元素组成的集合。</span><span class="sxs-lookup"><span data-stu-id="69f7d-142">[Arrays](language-reference/arrays.md) are fixed-size, *mutable* collections of elements of the same type.</span></span>  <span data-ttu-id="69f7d-143">它们支持快速随机访问的元素，并不是 F # 列出因为它们是只是连续内存块的能力，速度更快。</span><span class="sxs-lookup"><span data-stu-id="69f7d-143">They support fast random access of elements, and are faster than F# lists because they are just contiguous blocks of memory.</span></span>

[!code-fsharp[Arrays](../../samples/snippets/fsharp/tour.fs#L368-L407)]

<span data-ttu-id="69f7d-144">[序列](language-reference/sequences.md)是逻辑的一系列元素，所有相同的类型。</span><span class="sxs-lookup"><span data-stu-id="69f7d-144">[Sequences](language-reference/sequences.md) are a logical series of elements, all of the same type.</span></span>  <span data-ttu-id="69f7d-145">这些是比列表和数组，可为任何逻辑系列的元素"视图"更多常规类型。</span><span class="sxs-lookup"><span data-stu-id="69f7d-145">These are a more general type than Lists and Arrays, capable of being your "view" into any logical series of elements.</span></span>  <span data-ttu-id="69f7d-146">它们还醒目因为它们可以是***延迟***，这意味着仅在需要时可以计算元素。</span><span class="sxs-lookup"><span data-stu-id="69f7d-146">They also stand out because they can be ***lazy***, which means that elements can be computed only when they are needed.</span></span>

[!code-fsharp[Sequences](../../samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a><span data-ttu-id="69f7d-147">递归函数</span><span class="sxs-lookup"><span data-stu-id="69f7d-147">Recursive Functions</span></span>

<span data-ttu-id="69f7d-148">通常使用完成处理集合或元素的序列[递归](language-reference/functions/index.md#recursive-functions)F # 中。</span><span class="sxs-lookup"><span data-stu-id="69f7d-148">Processing collections or sequences of elements is typically done with [recursion](language-reference/functions/index.md#recursive-functions) in F#.</span></span>  <span data-ttu-id="69f7d-149">尽管 F # 具有对循环和命令性编程的支持，但递归是首选，因为它是更轻松地保证正确性。</span><span class="sxs-lookup"><span data-stu-id="69f7d-149">Although F# has support for loops and imperative programming, recursion is preferred because it is easier to guarantee correctness.</span></span>

>[!NOTE]
<span data-ttu-id="69f7d-150">下面的示例使用的模式匹配通过`match`表达式。</span><span class="sxs-lookup"><span data-stu-id="69f7d-150">The following example makes use of the pattern matching via the `match` expression.</span></span>  <span data-ttu-id="69f7d-151">更高版本中这篇文章介绍了此基本结构。</span><span class="sxs-lookup"><span data-stu-id="69f7d-151">This fundamental construct is covered later in this article.</span></span>

[!code-fsharp[RecursiveFunctions](../../samples/snippets/fsharp/tour.fs#L461-L500)]

<span data-ttu-id="69f7d-152">F # 还具有完全支持尾调用优化，这是一种优化递归调用，以便它们循环构造一样快。</span><span class="sxs-lookup"><span data-stu-id="69f7d-152">F# also has full support for Tail Call Optimization, which is a way to optimize recursive calls so that they are just as fast as a loop construct.</span></span>

## <a name="record-and-discriminated-union-types"></a><span data-ttu-id="69f7d-153">记录和可区分联合类型</span><span class="sxs-lookup"><span data-stu-id="69f7d-153">Record and Discriminated Union Types</span></span>

<span data-ttu-id="69f7d-154">记录和联合类型是在 F # 代码中，使用的两个基本数据类型，通常是用于表示在 F # 程序中的数据的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="69f7d-154">Record and Union types are two fundamental data types used in F# code, and are generally the best way to represent data in an F# program.</span></span>  <span data-ttu-id="69f7d-155">虽然这使得它们成为类似于类以其他语言，其主要区别之一是它们具有结构上相等语义。</span><span class="sxs-lookup"><span data-stu-id="69f7d-155">Although this makes them similar to classes in other languages, one of their primary differences is that they have structural equality semantics.</span></span>  <span data-ttu-id="69f7d-156">这意味着它们是"本机"比较和相等性非常简单-只检查是否等于另一个。</span><span class="sxs-lookup"><span data-stu-id="69f7d-156">This means that they are "natively" comparable and equality is straightforward - just check if one is equal to the other.</span></span>

<span data-ttu-id="69f7d-157">[记录](language-reference/records.md)是已命名的值，与 （如方法） 的可选成员聚合。</span><span class="sxs-lookup"><span data-stu-id="69f7d-157">[Records](language-reference/records.md) are an aggregate of named values, with optional members (such as methods).</span></span>  <span data-ttu-id="69f7d-158">如果你熟悉 C# 或 Java，然后这些应感觉类似于 POCOs 或 Pojo-只需与结构相等性和更低的方案。</span><span class="sxs-lookup"><span data-stu-id="69f7d-158">If you're familiar with C# or Java, then these should feel similar to POCOs or POJOs - just with structural equality and less ceremony.</span></span>

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L507-L559)]

<span data-ttu-id="69f7d-159">截至 F # 4.1 中，你还可以表示记录作为`struct`s。</span><span class="sxs-lookup"><span data-stu-id="69f7d-159">As of F# 4.1, you can also represent Records as `struct`s.</span></span>  <span data-ttu-id="69f7d-160">这通过完成`[<Struct>]`属性：</span><span class="sxs-lookup"><span data-stu-id="69f7d-160">This is done with the `[<Struct>]` attribute:</span></span>

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L561-L568)]

<span data-ttu-id="69f7d-161">[可区分联合 (Du)](language-reference/discriminated-unions.md)值可以是大量命名窗体或用例。</span><span class="sxs-lookup"><span data-stu-id="69f7d-161">[Discriminated Unions (DUs)](language-reference/discriminated-unions.md) are values which could be a number of named forms or cases.</span></span>  <span data-ttu-id="69f7d-162">类型中存储的数据可以是多个非重复值之一。</span><span class="sxs-lookup"><span data-stu-id="69f7d-162">Data stored in the type can be one of several distinct values.</span></span>

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L575-L631)]

<span data-ttu-id="69f7d-163">你还可以使用作为 Du*单用例可区分联合*，来帮助与域通过基元类型建模。</span><span class="sxs-lookup"><span data-stu-id="69f7d-163">You can also use DUs as *Single-Case Discriminated Unions*, to help with domain modeling over primitive types.</span></span>  <span data-ttu-id="69f7d-164">通常情况下，字符串和其他基元类型用于表示的一些东西，并因此具有特殊含义。</span><span class="sxs-lookup"><span data-stu-id="69f7d-164">Often times, strings and other primitive types are used to represent something, and are thus given a particular meaning.</span></span>  <span data-ttu-id="69f7d-165">但是，使用仅基元数据的表示形式可能会导致错误地分配的值不正确 ！</span><span class="sxs-lookup"><span data-stu-id="69f7d-165">However, using only the primitive representation of the data can result in mistakenly assigning an incorrect value!</span></span>  <span data-ttu-id="69f7d-166">表示每种类型的信息作为一个不同的单用例联合可以强制执行在此方案中的正确性。</span><span class="sxs-lookup"><span data-stu-id="69f7d-166">Representing each type of information as a distinct single-case union can enforce correctness in this scenario.</span></span>

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L633-L654)]

<span data-ttu-id="69f7d-167">如上面的示例所示，若要在单用例可区分联合，获取基础值必须显式打开它。</span><span class="sxs-lookup"><span data-stu-id="69f7d-167">As the above sample demonstrates, to get the underlying value in a single-case Discriminated Union, you must explicitly unwrap it.</span></span>

<span data-ttu-id="69f7d-168">此外，Du 还支持递归定义，从而可以轻松地表示树和本质上是递归数据。</span><span class="sxs-lookup"><span data-stu-id="69f7d-168">Additionally, DUs also support recursive definitions, allowing you to easily represent trees and inherently recursive data.</span></span>  <span data-ttu-id="69f7d-169">例如，下面是如何可以表示具有二进制搜索树`exists`和`insert`函数。</span><span class="sxs-lookup"><span data-stu-id="69f7d-169">For example, here's how you can represent a Binary Search Tree with `exists` and `insert` functions.</span></span>

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L656-L683)]

<span data-ttu-id="69f7d-170">因为 Du 使您可以表示的树中的数据类型的递归结构，对此递归结构非常简单，可保证正确性。</span><span class="sxs-lookup"><span data-stu-id="69f7d-170">Because DUs allow you to represent the recursive structure of the tree in the data type, operating on this recursive structure is straightforward and guarantees correctness.</span></span>  <span data-ttu-id="69f7d-171">它还支持在模式匹配，如下所示。</span><span class="sxs-lookup"><span data-stu-id="69f7d-171">It is also supported in pattern matching, as shown below.</span></span>

<span data-ttu-id="69f7d-172">此外，您可以表示为 Du`struct`与`[<Struct>]`属性：</span><span class="sxs-lookup"><span data-stu-id="69f7d-172">Additionally, you can represent DUs as `struct`s with the `[<Struct>]` attribute:</span></span>

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L685-L696)]

<span data-ttu-id="69f7d-173">但是，有两个执行此操作时需要牢记的重要事项：</span><span class="sxs-lookup"><span data-stu-id="69f7d-173">However, there are two key things to keep in mind when doing so:</span></span>

1. <span data-ttu-id="69f7d-174">太平洋结构不能以递归方式定义。</span><span class="sxs-lookup"><span data-stu-id="69f7d-174">A struct DU cannot be recursively-defined.</span></span>
2. <span data-ttu-id="69f7d-175">结构是必须具有唯一的名称，为每个及其用例。</span><span class="sxs-lookup"><span data-stu-id="69f7d-175">A struct DU must have unique names for each of its cases.</span></span>

<span data-ttu-id="69f7d-176">未能遵循上述将导致编译错误。</span><span class="sxs-lookup"><span data-stu-id="69f7d-176">Failure to follow the above will result in a compilation error.</span></span>

## <a name="pattern-matching"></a><span data-ttu-id="69f7d-177">模式匹配</span><span class="sxs-lookup"><span data-stu-id="69f7d-177">Pattern Matching</span></span>

<span data-ttu-id="69f7d-178">[模式匹配](language-reference/pattern-matching.md)是 F # 语言功能，这样对 F # 类型的正确性。</span><span class="sxs-lookup"><span data-stu-id="69f7d-178">[Pattern Matching](language-reference/pattern-matching.md) is the F# language feature which enables correctness for operating on F# types.</span></span>  <span data-ttu-id="69f7d-179">在上面的示例中，你可能注意到相当多的`match x with ...`语法。</span><span class="sxs-lookup"><span data-stu-id="69f7d-179">In the above samples, you probably noticed quite a bit of `match x with ...` syntax.</span></span>  <span data-ttu-id="69f7d-180">该构造允许编译器可以理解的数据类型，以强制你来应对所有可能的情况下，使用通过通常所说的数据类型作为详尽模式匹配时的"形状"。</span><span class="sxs-lookup"><span data-stu-id="69f7d-180">This construct allows the compiler, which can understand the "shape" of data types, to force you to account for all possible cases when using a data type through what is known as Exhaustive Pattern Matching.</span></span>  <span data-ttu-id="69f7d-181">这是非常强大的正确性，，，可以巧妙地使用以"提升"通常是运行时需考虑到编译时什么。</span><span class="sxs-lookup"><span data-stu-id="69f7d-181">This is incredibly powerful for correctness, and can be cleverly used to "lift" what would normally be a runtime concern into compile-time.</span></span>

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L705-L739)]

<span data-ttu-id="69f7d-182">你还可以使用速记`function`与模式匹配，这很有用，当你编写的函数使您能够使用的构造[部分应用](language-reference/functions/index.md#partial-application-of-arguments):</span><span class="sxs-lookup"><span data-stu-id="69f7d-182">You can also use the shorthand `function` construct for pattern matching, which is useful when you're writing functions which make use of [Partial Application](language-reference/functions/index.md#partial-application-of-arguments):</span></span>

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L741-L759)]

<span data-ttu-id="69f7d-183">你可能已经注意到的内容是使用`_`模式。</span><span class="sxs-lookup"><span data-stu-id="69f7d-183">Something you may have noticed is the use of the `_` pattern.</span></span>  <span data-ttu-id="69f7d-184">这称为[通配符模式](language-reference/pattern-matching.md#wildcard-pattern)，这是一种说"我不会关心的内容是"。</span><span class="sxs-lookup"><span data-stu-id="69f7d-184">This is known as the [Wildcard Pattern](language-reference/pattern-matching.md#wildcard-pattern), which is a way of saying "I don't care what something is".</span></span>  <span data-ttu-id="69f7d-185">虽然便利，然而可以意外绕过详尽模式匹配并且不再受益执行进行编译时，如果你不小心使用`_`。</span><span class="sxs-lookup"><span data-stu-id="69f7d-185">Although convenient, you can accidentally bypass Exhaustive Pattern Matching and no longer benefit from compile-time enforcements if you aren't careful in using `_`.</span></span>  <span data-ttu-id="69f7d-186">它最适用时你不关心分解后的类型的某些部分时模式匹配，或最终的子句时具有枚举所有有意义的情况下在模式匹配表达式。</span><span class="sxs-lookup"><span data-stu-id="69f7d-186">It is best used when you don't care about certain pieces of a decomposed type when pattern matching, or the final clause when you have enumerated all meaningful cases in a pattern matching expression.</span></span>

<span data-ttu-id="69f7d-187">[活动模式](language-reference/active-patterns.md)是另一个功能强大的结构与模式匹配一起使用。</span><span class="sxs-lookup"><span data-stu-id="69f7d-187">[Active Patterns](language-reference/active-patterns.md) are another powerful construct to use with pattern matching.</span></span>  <span data-ttu-id="69f7d-188">它们允许您输入的数据分区到自定义窗体，将它们分解的模式匹配调用站点。</span><span class="sxs-lookup"><span data-stu-id="69f7d-188">They allow you to partition input data into custom forms, decomposing them at the pattern match call site.</span></span>  <span data-ttu-id="69f7d-189">它们还可参数化，从而允许为函数定义分区。</span><span class="sxs-lookup"><span data-stu-id="69f7d-189">They can also be parameterized, thus allowing to define the partition as a function.</span></span>  <span data-ttu-id="69f7d-190">扩展前面的示例以支持活动模式如下所示：</span><span class="sxs-lookup"><span data-stu-id="69f7d-190">Expanding the previous example to support Active Patterns looks something like this:</span></span>

[!code-fsharp[ActivePatterns](../../samples/snippets/fsharp/tour.fs#L761-L783)]

## <a name="optional-types"></a><span data-ttu-id="69f7d-191">可选类型</span><span class="sxs-lookup"><span data-stu-id="69f7d-191">Optional Types</span></span>

<span data-ttu-id="69f7d-192">可区分联合类型使用了一个特殊的情况下是选项类型，这是很有用，它是 F # 核心库的一部分。</span><span class="sxs-lookup"><span data-stu-id="69f7d-192">One special case of Discriminated Union types is the Option Type, which is so useful that it's a part of the F# core library.</span></span>

<span data-ttu-id="69f7d-193">[选项类型](language-reference/options.md)是类型表示两种情况之一： 一个值，或在所有执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="69f7d-193">[The Option Type](language-reference/options.md) is a type which represents one of two cases: a value, or nothing at all.</span></span>  <span data-ttu-id="69f7d-194">它用在任何方案，其中可能或可能不会造成从某一特定操作的值。</span><span class="sxs-lookup"><span data-stu-id="69f7d-194">It is used in any scenario where a value may or may not result from a particular operation.</span></span>  <span data-ttu-id="69f7d-195">这将强制你以这两种情况，因而编译时需考虑，而不是运行时需考虑的帐户。</span><span class="sxs-lookup"><span data-stu-id="69f7d-195">This then forces you to account for both cases, making it a compile-time concern rather than a runtime concern.</span></span>  <span data-ttu-id="69f7d-196">这些通常在 Api 中使用其中`null`用于表示"nothing"相反，因此不再需要担心`NullReferenceException`在许多情况下。</span><span class="sxs-lookup"><span data-stu-id="69f7d-196">These are often used in APIs where `null` is used to represent "nothing" instead, thus eliminating the need to worry about `NullReferenceException` in many circumstances.</span></span>

[!code-fsharp[Options](../../samples/snippets/fsharp/tour.fs#L791-L811)]

## <a name="units-of-measure"></a><span data-ttu-id="69f7d-197">度量单位</span><span class="sxs-lookup"><span data-stu-id="69f7d-197">Units of Measure</span></span>

<span data-ttu-id="69f7d-198">F # 类型系统的独特功能是能够通过度量单位的数值为提供的上下文。</span><span class="sxs-lookup"><span data-stu-id="69f7d-198">One unique feature of F#'s type system is the ability to provide context for numeric literals through Units of Measure.</span></span>

<span data-ttu-id="69f7d-199">[度量单位](language-reference/units-of-measure.md)允许您将关联到一个单元，如米，数值类型和具有函数执行单位，而不是数值。</span><span class="sxs-lookup"><span data-stu-id="69f7d-199">[Units of Measure](language-reference/units-of-measure.md) allow you to associate a numeric type to a unit, such as Meters, and have functions perform work on units rather than numeric literals.</span></span>  <span data-ttu-id="69f7d-200">这使编译器若要验证传入的数值的类型在某些上下文有意义，从而消除运行时错误与该类型的工作。</span><span class="sxs-lookup"><span data-stu-id="69f7d-200">This enables the compiler to verify that the types of numeric literals passed in make sense under a certain context, thus eliminating runtime errors associated with that kind of work.</span></span>

[!code-fsharp[UnitsOfMeasure](../../samples/snippets/fsharp/tour.fs#L818-L839)]

<span data-ttu-id="69f7d-201">F # 核心库定义了许多 SI 单位类型和单元转换。</span><span class="sxs-lookup"><span data-stu-id="69f7d-201">The F# Core library defines many SI unit types and unit conversions.</span></span>  <span data-ttu-id="69f7d-202">若要了解详细信息，请查看[Microsoft.FSharp.Data.UnitSystems.SI Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d)。</span><span class="sxs-lookup"><span data-stu-id="69f7d-202">To learn more, check out the [Microsoft.FSharp.Data.UnitSystems.SI Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d).</span></span>

## <a name="classes-and-interfaces"></a><span data-ttu-id="69f7d-203">类和接口</span><span class="sxs-lookup"><span data-stu-id="69f7d-203">Classes and Interfaces</span></span>

<span data-ttu-id="69f7d-204">F # 还具有对.NET 类的完全支持[接口](language-reference/interfaces.md)，[抽象类](language-reference/abstract-classes.md)，[继承](language-reference/inheritance.md)，依次类推。</span><span class="sxs-lookup"><span data-stu-id="69f7d-204">F# also has full support for .NET classes, [Interfaces](language-reference/interfaces.md), [Abstract Classes](language-reference/abstract-classes.md), [Inheritance](language-reference/inheritance.md), and so on.</span></span>

<span data-ttu-id="69f7d-205">[类](language-reference/classes.md)是表示.NET 对象的类型可以属性、 方法和事件作为其[成员](language-reference/members/index.md)。</span><span class="sxs-lookup"><span data-stu-id="69f7d-205">[Classes](language-reference/classes.md) are types that represent .NET objects, which can have properties, methods, and events as its [Members](language-reference/members/index.md).</span></span>

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L848-L877)]

<span data-ttu-id="69f7d-206">定义泛型类也是非常简单的。</span><span class="sxs-lookup"><span data-stu-id="69f7d-206">Defining generic classes is also very straightforward.</span></span>

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L884-L905)]

<span data-ttu-id="69f7d-207">若要实现接口，你可以使用`interface ... with`语法或[对象表达式](language-reference/object-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="69f7d-207">To implement an Interface, you can use either `interface ... with` syntax or an [Object Expression](language-reference/object-expressions.md).</span></span>

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L912-L931)]

## <a name="which-types-to-use"></a><span data-ttu-id="69f7d-208">使用哪些类型</span><span class="sxs-lookup"><span data-stu-id="69f7d-208">Which Types to Use</span></span>

<span data-ttu-id="69f7d-209">类、 记录、 可区分联合和元组是否存在产生了一个重要问题： 你应使用的？</span><span class="sxs-lookup"><span data-stu-id="69f7d-209">The presence of Classes, Records, Discriminated Unions, and Tuples leads to an important question: which should you use?</span></span>  <span data-ttu-id="69f7d-210">如大多数中的所有内容生命，答案取决于你的情况。</span><span class="sxs-lookup"><span data-stu-id="69f7d-210">Like most everything in life, the answer depends on your circumstances.</span></span>

<span data-ttu-id="69f7d-211">元组则非常适合用于从一个函数，返回多个值，并使用作为值本身的值的即席聚合。</span><span class="sxs-lookup"><span data-stu-id="69f7d-211">Tuples are great for returning multiple values from a function, and using an ad-hoc aggregate of values as a value itself.</span></span>

<span data-ttu-id="69f7d-212">记录是"中的步骤向上"具有名为标签和支持可选的成员的元组。</span><span class="sxs-lookup"><span data-stu-id="69f7d-212">Records are a "step up" from Tuples, having named labels and support for optional members.</span></span>  <span data-ttu-id="69f7d-213">它们是非常适合于正在传输的数据通过你计划的低方案表示。</span><span class="sxs-lookup"><span data-stu-id="69f7d-213">They are great for a low-ceremony representation of data in-transit through your program.</span></span>  <span data-ttu-id="69f7d-214">因为它们具有结构相等性，它们是比较易于使用。</span><span class="sxs-lookup"><span data-stu-id="69f7d-214">Because they have structural equality, they are easy to use with comparison.</span></span>

<span data-ttu-id="69f7d-215">可区分的联合有许多用途，但核心优势是能够与模式匹配来应对所有可能"形状"可以具有数据结合使用它们。</span><span class="sxs-lookup"><span data-stu-id="69f7d-215">Discriminated Unions have many uses, but the core benefit is to be able to utilize them in conjunction with Pattern Matching to account for all possible "shapes" that a data can have.</span></span>  

<span data-ttu-id="69f7d-216">类非常适合用于大量的原因，例如，当你需要表示信息以及还如何关联到功能该信息。</span><span class="sxs-lookup"><span data-stu-id="69f7d-216">Classes are great for a huge number of reasons, such as when you need to represent information and also tie that information to functionality.</span></span>  <span data-ttu-id="69f7d-217">根据经验，你会获得对某些数据，从概念上讲绑定的功能时使用类和的面向对象的编程原则是很大的优势。</span><span class="sxs-lookup"><span data-stu-id="69f7d-217">As a rule of thumb, when you have functionality which is conceptually tied to some data, using Classes and the principles of Object-Oriented Programming is a big benefit.</span></span>  <span data-ttu-id="69f7d-218">类也是首选的数据类型与 C# 和 Visual Basic 互操作时为这些语言几乎所有操作使用的类。</span><span class="sxs-lookup"><span data-stu-id="69f7d-218">Classes are also the preferred data type when interoperating with C# and Visual Basic, as these languages use classes for nearly everything.</span></span>

## <a name="next-steps"></a><span data-ttu-id="69f7d-219">后续步骤</span><span class="sxs-lookup"><span data-stu-id="69f7d-219">Next Steps</span></span>

<span data-ttu-id="69f7d-220">现在，你已了解的一些主要功能的语言，你应该已准备好编写第一个 F # 程序 ！</span><span class="sxs-lookup"><span data-stu-id="69f7d-220">Now that you've seen some of the primary features of the language, you should be ready to write your first F# programs!</span></span>  <span data-ttu-id="69f7d-221">签出[入门](tutorials/getting-started/index.md)若要了解如何设置开发环境和编写一些代码。</span><span class="sxs-lookup"><span data-stu-id="69f7d-221">Check out [Getting Started](tutorials/getting-started/index.md) to learn how to set up your development environment and write some code.</span></span>

<span data-ttu-id="69f7d-222">若要了解有关的后续步骤可以是你希望的任何内容，但我们建议[函数作为一类值](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming in F#](introduction-to-functional-programming/index.md)-->获取熟悉函数编程的核心概念。</span><span class="sxs-lookup"><span data-stu-id="69f7d-222">The next steps for learning more can be whatever you like, but we recommend [Functions as First-Class Values](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming in F#](introduction-to-functional-programming/index.md)--> to get comfortable with core Functional Programming concepts.</span></span>  <span data-ttu-id="69f7d-223">这些将是基本中生成 F # 中的可靠程序。</span><span class="sxs-lookup"><span data-stu-id="69f7d-223">These will be essential in building robust programs in F#.</span></span>

<span data-ttu-id="69f7d-224">此外，请查看[F # 语言参考](language-reference/index.md)以在 F # 中查看概念性内容的全面集合。</span><span class="sxs-lookup"><span data-stu-id="69f7d-224">Also, check out the [F# Language Reference](language-reference/index.md) to see a comprehensive collection of conceptual content on F#.</span></span>
