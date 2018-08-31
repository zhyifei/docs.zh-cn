---
title: C# 发展历史 - C# 指南
description: 这些语言在最早版本中是什么样的，它又是如何演化的？
author: erikdietrich
ms.date: 09/20/2017
ms.openlocfilehash: 90f480d7b25ebe308d1f1cb3d4c117f36f7dd9bf
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "42752073"
---
# <a name="the-history-of-c"></a><span data-ttu-id="abae3-103">C# 发展历史</span><span class="sxs-lookup"><span data-stu-id="abae3-103">The history of C#</span></span> #

<span data-ttu-id="abae3-104">最初版本的语言是什么样的？</span><span class="sxs-lookup"><span data-stu-id="abae3-104">What did the language look like in its earliest incarnations?</span></span> <span data-ttu-id="abae3-105">之后又是如何演化的？</span><span class="sxs-lookup"><span data-stu-id="abae3-105">And how has it evolved in the years since?</span></span>

## <a name="c-version-10"></a><span data-ttu-id="abae3-106">C# 1.0 版</span><span class="sxs-lookup"><span data-stu-id="abae3-106">C# version 1.0</span></span>

<span data-ttu-id="abae3-107">回想起来，C# 1.0 版非常像 Java。</span><span class="sxs-lookup"><span data-stu-id="abae3-107">When you go back and look, C# version 1.0 looked a lot like Java.</span></span> <span data-ttu-id="abae3-108">在 [ECMA 制定的设计目标](http://feeldotneteasy.blogspot.com/2011/01/c-design-goals.html)中，它旨在成为一种“简单、现代、面向对象的常规用途语言”。</span><span class="sxs-lookup"><span data-stu-id="abae3-108">As [part of its stated design goals for ECMA](http://feeldotneteasy.blogspot.com/2011/01/c-design-goals.html), it sought to be a "simple, modern, general-purpose object-oriented language."</span></span>  <span data-ttu-id="abae3-109">当时，它和 Java 类似，说明已经实现了上述早期设计目标。</span><span class="sxs-lookup"><span data-stu-id="abae3-109">At the time, looking like Java meant it achieved those early design goals.</span></span>

<span data-ttu-id="abae3-110">不过如果现在回顾 C# 1.0，你会觉得有点晕。</span><span class="sxs-lookup"><span data-stu-id="abae3-110">But if you look back on C# 1.0 now, you'd find yourself a little dizzy.</span></span> <span data-ttu-id="abae3-111">它没有习以为常的内置异步功能和以泛型为中心的巧妙功能。</span><span class="sxs-lookup"><span data-stu-id="abae3-111">It lacked the built-in async capabilities and some of the slick functionality around generics you take for granted.</span></span> <span data-ttu-id="abae3-112">其实它完全不具备泛型。</span><span class="sxs-lookup"><span data-stu-id="abae3-112">As a matter of fact, it lacked generics altogether.</span></span>  <span data-ttu-id="abae3-113">那 [LINQ](../linq/index.md) 呢？</span><span class="sxs-lookup"><span data-stu-id="abae3-113">And [LINQ](../linq/index.md)?</span></span> <span data-ttu-id="abae3-114">尚不可用。</span><span class="sxs-lookup"><span data-stu-id="abae3-114">Not available yet.</span></span> <span data-ttu-id="abae3-115">这些新增内容需要几年才能推出。</span><span class="sxs-lookup"><span data-stu-id="abae3-115">Those additions would take some years to come out.</span></span>

<span data-ttu-id="abae3-116">与现在的 C# 相比，C# 1.0 版少了很多功能。</span><span class="sxs-lookup"><span data-stu-id="abae3-116">C# version 1.0 looked stripped of features, compared to today.</span></span> <span data-ttu-id="abae3-117">你会发现自己的代码很冗长。</span><span class="sxs-lookup"><span data-stu-id="abae3-117">You'd find yourself writing some verbose code.</span></span> <span data-ttu-id="abae3-118">不过凡事总要有个开始。</span><span class="sxs-lookup"><span data-stu-id="abae3-118">But yet, you have to start somewhere.</span></span> <span data-ttu-id="abae3-119">在 Windows 平台上，C# 1.0 版是 Java 的一个可行的替代之选。</span><span class="sxs-lookup"><span data-stu-id="abae3-119">C# version 1.0 was a viable alternative to Java on the Windows platform.</span></span>

<span data-ttu-id="abae3-120">C# 1.0 的主要功能包括：</span><span class="sxs-lookup"><span data-stu-id="abae3-120">The major features of C# 1.0 included:</span></span>

- [<span data-ttu-id="abae3-121">类</span><span class="sxs-lookup"><span data-stu-id="abae3-121">Classes</span></span>](../programming-guide/classes-and-structs/classes.md)
- [<span data-ttu-id="abae3-122">结构</span><span class="sxs-lookup"><span data-stu-id="abae3-122">Structs</span></span>](../programming-guide/classes-and-structs/structs.md)
- [<span data-ttu-id="abae3-123">接口</span><span class="sxs-lookup"><span data-stu-id="abae3-123">Interfaces</span></span>](../programming-guide/interfaces/index.md)
- [<span data-ttu-id="abae3-124">事件</span><span class="sxs-lookup"><span data-stu-id="abae3-124">Events</span></span>](../events-overview.md)
- [<span data-ttu-id="abae3-125">属性</span><span class="sxs-lookup"><span data-stu-id="abae3-125">Properties</span></span>](../properties.md)
- [<span data-ttu-id="abae3-126">委托</span><span class="sxs-lookup"><span data-stu-id="abae3-126">Delegates</span></span>](../delegates-overview.md)
- [<span data-ttu-id="abae3-127">表达式</span><span class="sxs-lookup"><span data-stu-id="abae3-127">Expressions</span></span>](../programming-guide/statements-expressions-operators/expressions.md)
- [<span data-ttu-id="abae3-128">语句</span><span class="sxs-lookup"><span data-stu-id="abae3-128">Statements</span></span>](../programming-guide/statements-expressions-operators/statements.md)
- [<span data-ttu-id="abae3-129">特性</span><span class="sxs-lookup"><span data-stu-id="abae3-129">Attributes</span></span>](../programming-guide/concepts/attributes/index.md)
- <span data-ttu-id="abae3-130">文本</span><span class="sxs-lookup"><span data-stu-id="abae3-130">Literals</span></span>

## <a name="c-version-20"></a><span data-ttu-id="abae3-131">C# 2.0 版</span><span class="sxs-lookup"><span data-stu-id="abae3-131">C# version 2.0</span></span>

<span data-ttu-id="abae3-132">从此以后事情变得有趣起来。</span><span class="sxs-lookup"><span data-stu-id="abae3-132">Now things start to get interesting.</span></span> <span data-ttu-id="abae3-133">让我们看看 C# 2.0（2005 年发布）和 Visual Studio 2005 中的一些主要功能：</span><span class="sxs-lookup"><span data-stu-id="abae3-133">Let's take a look at some major features of C# 2.0, released in 2005, along with Visual Studio 2005:</span></span>

- [<span data-ttu-id="abae3-134">泛型</span><span class="sxs-lookup"><span data-stu-id="abae3-134">Generics</span></span>](../programming-guide/generics/index.md)
- [<span data-ttu-id="abae3-135">分部类型</span><span class="sxs-lookup"><span data-stu-id="abae3-135">Partial types</span></span>](../programming-guide/classes-and-structs/partial-classes-and-methods.md#partial-classes)
- [<span data-ttu-id="abae3-136">匿名方法</span><span class="sxs-lookup"><span data-stu-id="abae3-136">Anonymous methods</span></span>](../programming-guide/statements-expressions-operators/anonymous-methods.md)
- [<span data-ttu-id="abae3-137">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="abae3-137">Nullable types</span></span>](../programming-guide/nullable-types/index.md)
- [<span data-ttu-id="abae3-138">迭代器</span><span class="sxs-lookup"><span data-stu-id="abae3-138">Iterators</span></span>](../programming-guide/concepts/iterators.md)
- [<span data-ttu-id="abae3-139">协变和逆变</span><span class="sxs-lookup"><span data-stu-id="abae3-139">Covariance and contravariance</span></span>](../programming-guide/concepts/covariance-contravariance/index.md)

<span data-ttu-id="abae3-140">除现有功能以外的其他 C# 2.0 功能：</span><span class="sxs-lookup"><span data-stu-id="abae3-140">Other C# 2.0 features added capabilities to existing features:</span></span>

- <span data-ttu-id="abae3-141">getter/setter 单独可访问性</span><span class="sxs-lookup"><span data-stu-id="abae3-141">Getter/setter separate accessibility</span></span>
- <span data-ttu-id="abae3-142">方法组转换（委托）</span><span class="sxs-lookup"><span data-stu-id="abae3-142">Method group conversions (delegates)</span></span>
- <span data-ttu-id="abae3-143">静态类</span><span class="sxs-lookup"><span data-stu-id="abae3-143">Static classes</span></span>
- <span data-ttu-id="abae3-144">委托推断</span><span class="sxs-lookup"><span data-stu-id="abae3-144">Delegate inference</span></span>

<span data-ttu-id="abae3-145">C# 一开始是面向对象的 (OO) 通用语言，而 C# 2.0 版很快改变了这一点。</span><span class="sxs-lookup"><span data-stu-id="abae3-145">While C# may have started as a generic Object-Oriented (OO) language, C# version 2.0 changed that in a hurry.</span></span> <span data-ttu-id="abae3-146">做好基础准备后，他们开始追求解决一些严重影响开发者的难点。</span><span class="sxs-lookup"><span data-stu-id="abae3-146">Once they had their feet under them, they went after some serious developer pain points.</span></span> <span data-ttu-id="abae3-147">且他们以显著的方式追求这些难点。</span><span class="sxs-lookup"><span data-stu-id="abae3-147">And they went after them in a significant way.</span></span>

<span data-ttu-id="abae3-148">通过泛型，类型和方法可以操作任意类型，同时保持类型安全性。</span><span class="sxs-lookup"><span data-stu-id="abae3-148">With generics, types and methods can operate on an arbitrary type while still retaining type safety.</span></span> <span data-ttu-id="abae3-149">例如，通过 <xref:System.Collections.Generic.List%601>，将获得 `List<string>` 或 `List<int>` 并且可以对这些字符串或整数执行类型安全操作，同时对其进行循环访问。</span><span class="sxs-lookup"><span data-stu-id="abae3-149">For instance, having a <xref:System.Collections.Generic.List%601> lets you have `List<string>` or `List<int>` and perform type-safe operations on those strings or integers while you iterate through them.</span></span> <span data-ttu-id="abae3-150">使用泛型优于创建派生自 `ArrayList` 的 `ListInt` 或者从每个操作的 `Object` 强制转换。</span><span class="sxs-lookup"><span data-stu-id="abae3-150">Using generics is better than create `ListInt` that derives from `ArrayList`  or casting from `Object` for every operation.</span></span>

<span data-ttu-id="abae3-151">C# 2.0 版引入了迭代器。</span><span class="sxs-lookup"><span data-stu-id="abae3-151">C# version 2.0 brought iterators.</span></span> <span data-ttu-id="abae3-152">简单来说，迭代器允许使用 `foreach` 循环来检查 `List`（或其他可枚举类型）中的所有项。</span><span class="sxs-lookup"><span data-stu-id="abae3-152">To put it succinctly, iterators let you examine all the items in a `List` (or other Enumerable types) with a `foreach` loop.</span></span> <span data-ttu-id="abae3-153">拥有迭代器是该语言最重要的一部分，显著提升了语言的可读性以及人们推出代码的能力。</span><span class="sxs-lookup"><span data-stu-id="abae3-153">Having iterators as a first-class part of the language dramatically enhanced readability of the language and people's ability to reason about the code.</span></span>

<span data-ttu-id="abae3-154">不过 C# 依然在追赶 Java 的道路上。</span><span class="sxs-lookup"><span data-stu-id="abae3-154">And yet, C# continued to play a bit of catch-up with Java.</span></span> <span data-ttu-id="abae3-155">当时 Java 已发布包含泛型和迭代器的版本。</span><span class="sxs-lookup"><span data-stu-id="abae3-155">Java had already released versions that included generics and iterators.</span></span> <span data-ttu-id="abae3-156">但是随着语言各自的演化，形势很快发生了变化。</span><span class="sxs-lookup"><span data-stu-id="abae3-156">But that would soon change as the languages continued to evolve apart.</span></span>

## <a name="c-version-30"></a><span data-ttu-id="abae3-157">C# 3.0 版</span><span class="sxs-lookup"><span data-stu-id="abae3-157">C# version 3.0</span></span>

<span data-ttu-id="abae3-158">C# 3.0 版和 Visual Studio 2008 一起发布于 2007 年下半年，但完整的语言功能是在 .NET Framework 3.5 版中发布的。</span><span class="sxs-lookup"><span data-stu-id="abae3-158">C# version 3.0 came in late 2007, along with Visual Studio 2008, though the full boat of language features would actually come with .NET Framework version 3.5.</span></span> <span data-ttu-id="abae3-159">此版本标示着 C# 发展过程中的重大更改。</span><span class="sxs-lookup"><span data-stu-id="abae3-159">This version marked a major change in the growth of C#.</span></span> <span data-ttu-id="abae3-160">C# 成为了真正强大的编程语言。</span><span class="sxs-lookup"><span data-stu-id="abae3-160">It established C# as a truly formidable programming language.</span></span> <span data-ttu-id="abae3-161">我们来看看此版本中的一些主要功能：</span><span class="sxs-lookup"><span data-stu-id="abae3-161">Let's take a look at some major features in this version:</span></span>

- [<span data-ttu-id="abae3-162">自动实现的属性</span><span class="sxs-lookup"><span data-stu-id="abae3-162">Auto implemented properties</span></span>](../programming-guide/classes-and-structs/auto-implemented-properties.md)
- [<span data-ttu-id="abae3-163">匿名类型</span><span class="sxs-lookup"><span data-stu-id="abae3-163">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="abae3-164">查询表达式</span><span class="sxs-lookup"><span data-stu-id="abae3-164">Query expressions</span></span>](../linq/query-expression-basics.md)
- [<span data-ttu-id="abae3-165">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="abae3-165">Lambda expression</span></span>](https://www.daedtech.com/introduction-to-c-lambda-expressions/)
- [<span data-ttu-id="abae3-166">表达式树</span><span class="sxs-lookup"><span data-stu-id="abae3-166">Expression trees</span></span>](https://blogs.msdn.microsoft.com/charlie/2008/01/31/expression-tree-basics/)
- [<span data-ttu-id="abae3-167">扩展方法</span><span class="sxs-lookup"><span data-stu-id="abae3-167">Extension methods</span></span>](https://www.codeproject.com/Tips/709310/Extension-Method-In-Csharp)
- [<span data-ttu-id="abae3-168">隐式类型本地变量</span><span class="sxs-lookup"><span data-stu-id="abae3-168">Implicitly typed local variables</span></span>](../language-reference/keywords/var.md)
- [<span data-ttu-id="abae3-169">分部方法</span><span class="sxs-lookup"><span data-stu-id="abae3-169">Partial methods</span></span>](../language-reference/keywords/partial-method.md)
- [<span data-ttu-id="abae3-170">对象和集合初始值设定项</span><span class="sxs-lookup"><span data-stu-id="abae3-170">Object and collection initializers</span></span>](../programming-guide/classes-and-structs/object-and-collection-initializers.md)

<span data-ttu-id="abae3-171">回顾过去，这些功能中大多数似乎都是不可或缺，难以分割的。</span><span class="sxs-lookup"><span data-stu-id="abae3-171">In retrospect, many of these features seem both inevitable and inseparable.</span></span> <span data-ttu-id="abae3-172">它们的组合都是经过巧妙布局。</span><span class="sxs-lookup"><span data-stu-id="abae3-172">They all fit together strategically.</span></span> <span data-ttu-id="abae3-173">我们通常认为 C# 版本的杀手锏是查询表达式，也就是语言集成查询 (LINQ)。</span><span class="sxs-lookup"><span data-stu-id="abae3-173">It's generally thought that C# version's killer feature was the query expression, also known as Language-Integrated Query (LINQ).</span></span>

<span data-ttu-id="abae3-174">LINQ 的构造可以建立在更细微的视图检查表达式树、Lambda 表达式以及匿名类型的基础上。</span><span class="sxs-lookup"><span data-stu-id="abae3-174">A more nuanced view examines expression trees, lambda expressions, and anonymous types as the foundation upon which LINQ is constructed.</span></span> <span data-ttu-id="abae3-175">不过无论如何 C# 3.0 都提出了革命性的概念。</span><span class="sxs-lookup"><span data-stu-id="abae3-175">But, in either case, C# 3.0 presented a revolutionary concept.</span></span> <span data-ttu-id="abae3-176">C# 3.0 开始为 C# 转变为面向对象/函数式混合语言打下基础。</span><span class="sxs-lookup"><span data-stu-id="abae3-176">C# 3.0 had begun to lay the groundwork for turning C# into a hybrid Object-Oriented / Functional language.</span></span>

<span data-ttu-id="abae3-177">具体来说，你现在可以编写 SQL 样式的声明性查询对集合以及其他项目执行操作。</span><span class="sxs-lookup"><span data-stu-id="abae3-177">Specifically, you could now write SQL-style, declarative queries to perform operations on collections, among other things.</span></span> <span data-ttu-id="abae3-178">无需再编写 `for` 循环来计算整数列表的平均值，现在可改用简单的 `list.Average()` 方法。</span><span class="sxs-lookup"><span data-stu-id="abae3-178">Instead of writing a `for` loop to compute the average of a list of integers, you could now do that as simply as `list.Average()`.</span></span> <span data-ttu-id="abae3-179">组合使用查询表达式和扩展方法让各种数字变得智能多了。</span><span class="sxs-lookup"><span data-stu-id="abae3-179">The combination of query expressions and extension methods made it look as though that list of integers had gotten a whole lot smarter.</span></span>

<span data-ttu-id="abae3-180">人们需要一些时间来掌握和吸收这种概念，不过已经逐渐做到了。</span><span class="sxs-lookup"><span data-stu-id="abae3-180">It took time for people to really grasp and integrate the concept, but they gradually did.</span></span> <span data-ttu-id="abae3-181">现在又过了几年，代码变得更简洁，功能也更强大了。</span><span class="sxs-lookup"><span data-stu-id="abae3-181">And now, years later, code is much more concise, simple, and functional.</span></span>

## <a name="c-version-40"></a><span data-ttu-id="abae3-182">C# 4.0 版</span><span class="sxs-lookup"><span data-stu-id="abae3-182">C# version 4.0</span></span>

<span data-ttu-id="abae3-183">C# 4.0 版很难达到 3.0 版的创新水平。</span><span class="sxs-lookup"><span data-stu-id="abae3-183">C# version 4.0 would have had a difficult time living up to the groundbreaking status of version 3.0.</span></span> <span data-ttu-id="abae3-184">在 3.0 版中，C# 已经完全从 Java 的阴影中脱颖而出，崭露头角。</span><span class="sxs-lookup"><span data-stu-id="abae3-184">With version 3.0, C# had moved the language firmly out from the shadow of Java and into prominence.</span></span> <span data-ttu-id="abae3-185">很快成为一种简洁精炼的语言。</span><span class="sxs-lookup"><span data-stu-id="abae3-185">The language was quickly becoming elegant.</span></span>

<span data-ttu-id="abae3-186">下一版本引入了一些有趣的新功能：</span><span class="sxs-lookup"><span data-stu-id="abae3-186">The next version did introduce some interesting new features:</span></span>

- [<span data-ttu-id="abae3-187">动态绑定</span><span class="sxs-lookup"><span data-stu-id="abae3-187">Dynamic binding</span></span>](../language-reference/keywords/dynamic.md)
- [<span data-ttu-id="abae3-188">命名参数/可选参数</span><span class="sxs-lookup"><span data-stu-id="abae3-188">Named/optional arguments</span></span>](../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- [<span data-ttu-id="abae3-189">泛型协变和逆变</span><span class="sxs-lookup"><span data-stu-id="abae3-189">Generic covariant and contravariant</span></span>](../../standard/generics/covariance-and-contravariance.md)
- [<span data-ttu-id="abae3-190">嵌入的互操作类型</span><span class="sxs-lookup"><span data-stu-id="abae3-190">Embedded interop types</span></span>](https://stackoverflow.com/questions/20514240/whats-the-difference-setting-embed-interop-types-true-and-false-in-visual-studi)

<span data-ttu-id="abae3-191">嵌入的互操作类型缓和了部署难点。</span><span class="sxs-lookup"><span data-stu-id="abae3-191">Embedded interop types alleviated a deployment pain.</span></span> <span data-ttu-id="abae3-192">泛型协变和逆变提供了更强的功能来使用泛型，但风格比较偏学术，应该最受框架和库创建者的喜爱。</span><span class="sxs-lookup"><span data-stu-id="abae3-192">Generic covariance and contravariance give you more power to use generics, but they're a bit academic and probably most appreciated by framework and library authors.</span></span> <span data-ttu-id="abae3-193">命名参数和可选参数帮助消除了很多方法重载，让使用更方便。</span><span class="sxs-lookup"><span data-stu-id="abae3-193">Named and optional parameters let you eliminate many method overloads and provide convenience.</span></span> <span data-ttu-id="abae3-194">但是这些功能都没有完全改变模式。</span><span class="sxs-lookup"><span data-stu-id="abae3-194">But none of those features are exactly paradigm altering.</span></span>

<span data-ttu-id="abae3-195">主要功能是引入 `dynamic` 关键字。</span><span class="sxs-lookup"><span data-stu-id="abae3-195">The major feature was the introduction of the `dynamic` keyword.</span></span> <span data-ttu-id="abae3-196">在 C# 4.0 版中引入 `dynamic` 关键字让用户可以替代编译时类型上的编译器。</span><span class="sxs-lookup"><span data-stu-id="abae3-196">The `dynamic` keyword introduced into C# version 4.0 the ability to override the compiler on compile-time typing.</span></span> <span data-ttu-id="abae3-197">通过使用 dynamic 关键字，可以创建和动态类型语言（例如 JavaScript）类似的构造。</span><span class="sxs-lookup"><span data-stu-id="abae3-197">By using the dynamic keyword, you can create constructs similar to dynamically typed languages like JavaScript.</span></span> <span data-ttu-id="abae3-198">可以创建 `dynamic x = "a string"` 再向它添加六个，然后让运行时理清下一步操作。</span><span class="sxs-lookup"><span data-stu-id="abae3-198">You can create a `dynamic x = "a string"` and then add six to it, leaving it up to the runtime to sort out what should happen next.</span></span>

<span data-ttu-id="abae3-199">动态绑定存在出错的可能性，不过同时也为你提供了强大的语言功能。</span><span class="sxs-lookup"><span data-stu-id="abae3-199">Dynamic binding gives you the potential for errors but also great power within the language.</span></span>

## <a name="c-version-50"></a><span data-ttu-id="abae3-200">C# 5.0 版</span><span class="sxs-lookup"><span data-stu-id="abae3-200">C# version 5.0</span></span>

<span data-ttu-id="abae3-201">C# 5.0 版是该语言有针对性的一个版本。</span><span class="sxs-lookup"><span data-stu-id="abae3-201">C# version 5.0 was a focused version of the language.</span></span> <span data-ttu-id="abae3-202">在此版本中所做的所有工作几乎都针对另一个突破性的语言概念：适用于异步编程的 `async` 和 `await` 模型。</span><span class="sxs-lookup"><span data-stu-id="abae3-202">Nearly all of the effort for that version went into another groundbreaking language concept: the `async` and `await` model for asynchronous programming .</span></span>  <span data-ttu-id="abae3-203">下面是主要功能列表：</span><span class="sxs-lookup"><span data-stu-id="abae3-203">Here is the major features list:</span></span>

- [<span data-ttu-id="abae3-204">异步成员</span><span class="sxs-lookup"><span data-stu-id="abae3-204">Asynchronous members</span></span>](../async.md)
- [<span data-ttu-id="abae3-205">调用方信息特性</span><span class="sxs-lookup"><span data-stu-id="abae3-205">Caller info attributes</span></span>](../programming-guide/concepts/caller-information.md)

### <a name="see-also"></a><span data-ttu-id="abae3-206">请参阅</span><span class="sxs-lookup"><span data-stu-id="abae3-206">See Also</span></span>

* [<span data-ttu-id="abae3-207">代码项目：C# 5.0 中的调用方信息属性</span><span class="sxs-lookup"><span data-stu-id="abae3-207">Code Project: Caller Info Attributes in C# 5.0</span></span>](https://www.codeproject.com/Tips/606379/Caller-Info-Attributes-in-Csharp)

<span data-ttu-id="abae3-208">调用方信息特性让你可以轻松检索上下文的信息，不需要采用大量样本反射代码。</span><span class="sxs-lookup"><span data-stu-id="abae3-208">The caller info attribute lets you easily retrieve information about the context in which you're running without resorting to a ton of boilerplate reflection code.</span></span> <span data-ttu-id="abae3-209">这在诊断和日志记录任务中也很有用。</span><span class="sxs-lookup"><span data-stu-id="abae3-209">It has many uses in diagnostics and logging tasks.</span></span>

<span data-ttu-id="abae3-210">但是 `async` 和 `await` 才是此版本真正的主角。</span><span class="sxs-lookup"><span data-stu-id="abae3-210">But `async` and `await` are the real stars of this release.</span></span> <span data-ttu-id="abae3-211">C# 在 2012 年推出这些功能时，将异步引入语言作为最重要的组成部分，另现状大为改观。</span><span class="sxs-lookup"><span data-stu-id="abae3-211">When these features came out in 2012, C# changed the game again by baking asynchrony into the language as a first-class participant.</span></span> <span data-ttu-id="abae3-212">如果你以前处理过冗长的运行操作以及实现回调的 Web，应该会爱上这项语言功能。</span><span class="sxs-lookup"><span data-stu-id="abae3-212">If you've ever dealt with long running operations and the implementation of webs of callbacks, you probably loved this language feature.</span></span>

## <a name="c-version-60"></a><span data-ttu-id="abae3-213">C# 6.0 版</span><span class="sxs-lookup"><span data-stu-id="abae3-213">C# version 6.0</span></span>

<span data-ttu-id="abae3-214">C# 在 3.0 版和 5.0 版对面向对象的语言添加了主要的新功能。</span><span class="sxs-lookup"><span data-stu-id="abae3-214">With versions 3.0 and 5.0, C# had added major new features in an object-oriented language.</span></span> <span data-ttu-id="abae3-215">在 6.0 版中，它不再推出主导性的杀手锏，而是发布了很多使得 C# 编程更有效率的小功能。</span><span class="sxs-lookup"><span data-stu-id="abae3-215">With version 6.0, it would go away from doing a dominant killer feature and instead release many smaller features that made C# programming more productive.</span></span> <span data-ttu-id="abae3-216">以下介绍了部分功能：</span><span class="sxs-lookup"><span data-stu-id="abae3-216">Here are some of them:</span></span>

- [<span data-ttu-id="abae3-217">静态导入</span><span class="sxs-lookup"><span data-stu-id="abae3-217">Static imports</span></span>](../language-reference/keywords/using-static.md)
- [<span data-ttu-id="abae3-218">异常筛选器</span><span class="sxs-lookup"><span data-stu-id="abae3-218">Exception filters</span></span>](https://www.thomaslevesque.com/2015/06/21/exception-filters-in-c-6/)
- [<span data-ttu-id="abae3-219">属性初始值设定项</span><span class="sxs-lookup"><span data-stu-id="abae3-219">Property initializers</span></span>](http://geekswithblogs.net/WinAZ/archive/2015/06/30/whatrsquos-new-in-c-6.0-auto-property-initializers.aspx)
- [<span data-ttu-id="abae3-220">Expression bodied 成员</span><span class="sxs-lookup"><span data-stu-id="abae3-220">Expression bodied members</span></span>](https://lostechies.com/jimmybogard/2015/12/17/c-6-feature-review-expression-bodied-function-members/)
- [<span data-ttu-id="abae3-221">Null 传播器</span><span class="sxs-lookup"><span data-stu-id="abae3-221">Null propagator</span></span>](https://davefancher.com/2014/08/14/c-6-0-null-propagation-operator/)
- [<span data-ttu-id="abae3-222">字符串内插</span><span class="sxs-lookup"><span data-stu-id="abae3-222">String interpolation</span></span>](../language-reference/tokens/interpolated.md)
- [<span data-ttu-id="abae3-223">nameof 运算符</span><span class="sxs-lookup"><span data-stu-id="abae3-223">nameof operator</span></span>](https://stackoverflow.com/questions/31695900/what-is-the-purpose-of-nameof)
- [<span data-ttu-id="abae3-224">索引初始值设定项</span><span class="sxs-lookup"><span data-stu-id="abae3-224">Index initializers</span></span>](csharp-6.md#index-initializers)

<span data-ttu-id="abae3-225">其他新功能包括：</span><span class="sxs-lookup"><span data-stu-id="abae3-225">Other new features include:</span></span>

- <span data-ttu-id="abae3-226">Catch/Finally 块中的 Await</span><span class="sxs-lookup"><span data-stu-id="abae3-226">Await in catch/finally blocks</span></span>
- <span data-ttu-id="abae3-227">仅限 getter 属性的默认值</span><span class="sxs-lookup"><span data-stu-id="abae3-227">Default values for getter-only properties</span></span>

<span data-ttu-id="abae3-228">这些功能每一个都很有趣。</span><span class="sxs-lookup"><span data-stu-id="abae3-228">Each of these features is interesting in its own right.</span></span> <span data-ttu-id="abae3-229">但从整体来看，可以发现一个有趣的模式。</span><span class="sxs-lookup"><span data-stu-id="abae3-229">But if you look at them altogether, you see an interesting pattern.</span></span> <span data-ttu-id="abae3-230">在此版本中，C# 消除语言样本，让代码更简洁且更具可读性。</span><span class="sxs-lookup"><span data-stu-id="abae3-230">In this version, C# eliminated language boilerplate to make code more terse and readable.</span></span> <span data-ttu-id="abae3-231">所以对喜欢简洁代码的用户来说，此语言版本非常成功。</span><span class="sxs-lookup"><span data-stu-id="abae3-231">So for fans of clean, simple code, this language version was a huge win.</span></span>

<span data-ttu-id="abae3-232">除了发布此版本，他们还做了另一件事，虽然这件事本身与传统的语言功能无关。</span><span class="sxs-lookup"><span data-stu-id="abae3-232">They did one other thing along with this version, though it's not a traditional language feature in itself.</span></span> <span data-ttu-id="abae3-233">他们发布了 [Roslyn 编译器即服务](https://github.com/dotnet/roslyn)。</span><span class="sxs-lookup"><span data-stu-id="abae3-233">They released [Roslyn the compiler as a service](https://github.com/dotnet/roslyn).</span></span> <span data-ttu-id="abae3-234">C# 编译器现在是用 C# 编写的，你可以使用编译器作为编程工作的一部分。</span><span class="sxs-lookup"><span data-stu-id="abae3-234">The C# compiler is now written in C#, and you can use the compiler as part of your programming efforts.</span></span>

## <a name="c-version-70"></a><span data-ttu-id="abae3-235">C# 7.0 版</span><span class="sxs-lookup"><span data-stu-id="abae3-235">C# version 7.0</span></span>

<span data-ttu-id="abae3-236">C# 7.0 版是最新的主版本。</span><span class="sxs-lookup"><span data-stu-id="abae3-236">The most recent major version is C# version 7.0.</span></span> <span data-ttu-id="abae3-237">虽然该版本继承和发展了 C# 6.0，但不包含编译器即服务。</span><span class="sxs-lookup"><span data-stu-id="abae3-237">This version has some evolutionary and cool stuff in the vein of C# 6.0, but without the compiler as a service.</span></span> <span data-ttu-id="abae3-238">以下介绍了部分新增功能：</span><span class="sxs-lookup"><span data-stu-id="abae3-238">Here are some of the new features:</span></span>

- [<span data-ttu-id="abae3-239">Out 变量</span><span class="sxs-lookup"><span data-stu-id="abae3-239">Out variables</span></span>](http://www.c-sharpcorner.com/article/out-variables-in-c-sharp-7-0/)
- [<span data-ttu-id="abae3-240">元组和析构函数</span><span class="sxs-lookup"><span data-stu-id="abae3-240">Tuples and deconstruction</span></span>](https://www.thomaslevesque.com/2016/08/23/tuple-deconstruction-in-c-7/)
- [<span data-ttu-id="abae3-241">模式匹配</span><span class="sxs-lookup"><span data-stu-id="abae3-241">Pattern matching</span></span>](./csharp-7.md#pattern-matching)
- [<span data-ttu-id="abae3-242">本地函数</span><span class="sxs-lookup"><span data-stu-id="abae3-242">Local functions</span></span>](http://www.infoworld.com/article/3182416/application-development/c-7-in-depth-exploring-local-functions.html)
- [<span data-ttu-id="abae3-243">已扩展 expression bodied 成员</span><span class="sxs-lookup"><span data-stu-id="abae3-243">Expanded expression bodied members</span></span>](./csharp-7.md#more-expression-bodied-members)
- [<span data-ttu-id="abae3-244">Ref 局部变量和返回结果</span><span class="sxs-lookup"><span data-stu-id="abae3-244">Ref locals and returns</span></span>](./csharp-7.md#ref-locals-and-returns)

<span data-ttu-id="abae3-245">其他功能包括：</span><span class="sxs-lookup"><span data-stu-id="abae3-245">Other features included:</span></span>

- [<span data-ttu-id="abae3-246">弃元</span><span class="sxs-lookup"><span data-stu-id="abae3-246">Discards</span></span>](../discards.md)
- [<span data-ttu-id="abae3-247">二进制文本</span><span class="sxs-lookup"><span data-stu-id="abae3-247">Binary Literals</span></span>](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.0/binary-literals.md)
- [<span data-ttu-id="abae3-248">数字分隔符</span><span class="sxs-lookup"><span data-stu-id="abae3-248">Digit Separators</span></span>](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.0/digit-separators.md)
- <span data-ttu-id="abae3-249">ref 返回值和局部变量</span><span class="sxs-lookup"><span data-stu-id="abae3-249">Ref returns and locals</span></span>
- [<span data-ttu-id="abae3-250">引发表达式</span><span class="sxs-lookup"><span data-stu-id="abae3-250">Throw expressions</span></span>](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.0/throw-expression.md)

<span data-ttu-id="abae3-251">这些都为开发者提供了很棒的新功能，帮助编写比以往任何时候都简洁的代码。</span><span class="sxs-lookup"><span data-stu-id="abae3-251">All of these features offer cool new capabilities for developers and the opportunity to write even cleaner code than ever.</span></span> <span data-ttu-id="abae3-252">重点是缩减了使用 `out` 关键字的变量声明，并通过元组实现了多个返回值。</span><span class="sxs-lookup"><span data-stu-id="abae3-252">A highlight is condensing the declaration of variables to use with the `out` keyword and by allowing multiple return values via tuple.</span></span>

<span data-ttu-id="abae3-253">但 C# 的用途更加广泛了。</span><span class="sxs-lookup"><span data-stu-id="abae3-253">But C# is being put to ever broader use.</span></span> <span data-ttu-id="abae3-254">.NET Core 现在面向所有操作系统，着眼于云和可移植性。</span><span class="sxs-lookup"><span data-stu-id="abae3-254">.NET Core now targets any operating system and has its eyes firmly on the cloud and on portability.</span></span>  <span data-ttu-id="abae3-255">语言设计者除了推出新功能外，也会在这些新功能方面付出时间和精力。</span><span class="sxs-lookup"><span data-stu-id="abae3-255">These new capabilities certainly occupy the language designers' thoughts and time, in addition to coming up with new features.</span></span>

<span data-ttu-id="abae3-256">_文章_[_最初发布在 NDepend 博客上_](https://blog.ndepend.com/c-versions-look-language-history/)_，由 Erik Dietrich 和 Patrick Smacchia 提供_。</span><span class="sxs-lookup"><span data-stu-id="abae3-256">_Article_ [_originally published on the NDepend blog_](https://blog.ndepend.com/c-versions-look-language-history/)_, courtesy of Erik Dietrich and Patrick Smacchia._</span></span>
