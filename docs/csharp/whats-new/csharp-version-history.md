---
title: C# 发展历史 - C# 指南
description: 这些语言在最早版本中是什么样的，它又是如何演化的？
author: erikdietrich
ms.date: 09/20/2017
ms.openlocfilehash: 7a7030eb9479ebae553f3bb4d569c9a9f931db9a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504408"
---
# <a name="the-history-of-c"></a>C# 发展历史 #

最初版本的语言是什么样的？ 之后又是如何演化的？

## <a name="c-version-10"></a>C# 1.0 版

回想起来，C# 1.0 版非常像 Java。 在 [ECMA 制定的设计目标](http://feeldotneteasy.blogspot.com/2011/01/c-design-goals.html)中，它旨在成为一种“简单、现代、面向对象的常规用途语言”。  当时，它和 Java 类似，说明已经实现了上述早期设计目标。

不过如果现在回顾 C# 1.0，你会觉得有点晕。 它没有习以为常的内置异步功能和以泛型为中心的巧妙功能。 其实它完全不具备泛型。  那 [LINQ](../linq/index.md) 呢？ 尚不可用。 这些新增内容需要几年才能推出。

与现在的 C# 相比，C# 1.0 版少了很多功能。 你会发现自己的代码很冗长。 不过凡事总要有个开始。 在 Windows 平台上，C# 1.0 版是 Java 的一个可行的替代之选。

C# 1.0 的主要功能包括：

- [类](../programming-guide/classes-and-structs/classes.md)
- [结构](../programming-guide/classes-and-structs/structs.md)
- [接口](../programming-guide/interfaces/index.md)
- [事件](../events-overview.md)
- [属性](../properties.md)
- [委托](../delegates-overview.md)
- [表达式](../programming-guide/statements-expressions-operators/expressions.md)
- [语句](../programming-guide/statements-expressions-operators/statements.md)
- [特性](../programming-guide/concepts/attributes/index.md)
- 文本

## <a name="c-version-12"></a>C# 版本 1.2

随 Visual Studio 2003 一起提供的 C# 版本 1.2。 它对语言做了一些小改进。 最值得注意的是，从此版本开始，当 <xref:System.Collections.IEnumerator> 实现 <xref:System.IDisposable> 时，`foreach` 循环中生成的代码会在 <xref:System.Collections.IEnumerator> 上调用 <xref:System.IDisposable.Dispose%2A>。

## <a name="c-version-20"></a>C# 2.0 版

从此以后事情变得有趣起来。 让我们看看 C# 2.0（2005 年发布）和 Visual Studio 2005 中的一些主要功能：

- [泛型](../programming-guide/generics/index.md)
- [分部类型](../programming-guide/classes-and-structs/partial-classes-and-methods.md#partial-classes)
- [匿名方法](../programming-guide/statements-expressions-operators/anonymous-methods.md)
- [可以为 null 的类型](../programming-guide/nullable-types/index.md)
- [迭代器](../programming-guide/concepts/iterators.md)
- [协变和逆变](../programming-guide/concepts/covariance-contravariance/index.md)

除现有功能以外的其他 C# 2.0 功能：

- getter/setter 单独可访问性
- 方法组转换（委托）
- 静态类
- 委托推断

C# 一开始是面向对象的 (OO) 通用语言，而 C# 2.0 版很快改变了这一点。 做好基础准备后，他们开始追求解决一些严重影响开发者的难点。 且他们以显著的方式追求这些难点。

通过泛型，类型和方法可以操作任意类型，同时保持类型安全性。 例如，通过 <xref:System.Collections.Generic.List%601>，将获得 `List<string>` 或 `List<int>` 并且可以对这些字符串或整数执行类型安全操作，同时对其进行循环访问。 使用泛型优于创建派生自 `ArrayList` 的 `ListInt` 或者从每个操作的 `Object` 强制转换。

C# 2.0 版引入了迭代器。 简单来说，迭代器允许使用 `foreach` 循环来检查 `List`（或其他可枚举类型）中的所有项。 拥有迭代器是该语言最重要的一部分，显著提升了语言的可读性以及人们推出代码的能力。

不过 C# 依然在追赶 Java 的道路上。 当时 Java 已发布包含泛型和迭代器的版本。 但是随着语言各自的演化，形势很快发生了变化。

## <a name="c-version-30"></a>C# 3.0 版

C# 3.0 版和 Visual Studio 2008 一起发布于 2007 年下半年，但完整的语言功能是在 .NET Framework 3.5 版中发布的。 此版本标示着 C# 发展过程中的重大更改。 C# 成为了真正强大的编程语言。 我们来看看此版本中的一些主要功能：

- [自动实现的属性](../programming-guide/classes-and-structs/auto-implemented-properties.md)
- [匿名类型](../programming-guide/classes-and-structs/anonymous-types.md)
- [查询表达式](../linq/query-expression-basics.md)
- [Lambda 表达式](https://www.daedtech.com/introduction-to-c-lambda-expressions/)
- [表达式树](https://blogs.msdn.microsoft.com/charlie/2008/01/31/expression-tree-basics/)
- [扩展方法](https://www.codeproject.com/Tips/709310/Extension-Method-In-Csharp)
- [隐式类型本地变量](../language-reference/keywords/var.md)
- [分部方法](../language-reference/keywords/partial-method.md)
- [对象和集合初始值设定项](../programming-guide/classes-and-structs/object-and-collection-initializers.md)

回顾过去，这些功能中大多数似乎都是不可或缺，难以分割的。 它们的组合都是经过巧妙布局。 我们通常认为 C# 版本的杀手锏是查询表达式，也就是语言集成查询 (LINQ)。

LINQ 的构造可以建立在更细微的视图检查表达式树、Lambda 表达式以及匿名类型的基础上。 不过无论如何 C# 3.0 都提出了革命性的概念。 C# 3.0 开始为 C# 转变为面向对象/函数式混合语言打下基础。

具体来说，你现在可以编写 SQL 样式的声明性查询对集合以及其他项目执行操作。 无需再编写 `for` 循环来计算整数列表的平均值，现在可改用简单的 `list.Average()` 方法。 组合使用查询表达式和扩展方法让各种数字变得智能多了。

人们需要一些时间来掌握和吸收这种概念，不过已经逐渐做到了。 现在又过了几年，代码变得更简洁，功能也更强大了。

## <a name="c-version-40"></a>C# 4.0 版

C# 4.0 版很难达到 3.0 版的创新水平。 在 3.0 版中，C# 已经完全从 Java 的阴影中脱颖而出，崭露头角。 很快成为一种简洁精炼的语言。

下一版本引入了一些有趣的新功能：

- [动态绑定](../language-reference/keywords/dynamic.md)
- [命名参数/可选参数](../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- [泛型协变和逆变](../../standard/generics/covariance-and-contravariance.md)
- [嵌入的互操作类型](https://stackoverflow.com/questions/20514240/whats-the-difference-setting-embed-interop-types-true-and-false-in-visual-studi)

嵌入的互操作类型缓和了部署难点。 泛型协变和逆变提供了更强的功能来使用泛型，但风格比较偏学术，应该最受框架和库创建者的喜爱。 命名参数和可选参数帮助消除了很多方法重载，让使用更方便。 但是这些功能都没有完全改变模式。

主要功能是引入 `dynamic` 关键字。 在 C# 4.0 版中引入 `dynamic` 关键字让用户可以替代编译时类型上的编译器。 通过使用 dynamic 关键字，可以创建和动态类型语言（例如 JavaScript）类似的构造。 可以创建 `dynamic x = "a string"` 再向它添加六个，然后让运行时理清下一步操作。

动态绑定存在出错的可能性，不过同时也为你提供了强大的语言功能。

## <a name="c-version-50"></a>C# 5.0 版

C# 5.0 版是该语言有针对性的一个版本。 在此版本中所做的所有工作几乎都针对另一个突破性的语言概念：适用于异步编程的 `async` 和 `await` 模型。  下面是主要功能列表：

- [异步成员](../async.md)
- [调用方信息特性](../programming-guide/concepts/caller-information.md)

### <a name="see-also"></a>请参阅

* [代码项目：C# 5.0 中的调用方信息属性](https://www.codeproject.com/Tips/606379/Caller-Info-Attributes-in-Csharp)

调用方信息特性让你可以轻松检索上下文的信息，不需要采用大量样本反射代码。 这在诊断和日志记录任务中也很有用。

但是 `async` 和 `await` 才是此版本真正的主角。 C# 在 2012 年推出这些功能时，将异步引入语言作为最重要的组成部分，另现状大为改观。 如果你以前处理过冗长的运行操作以及实现回调的 Web，应该会爱上这项语言功能。

## <a name="c-version-60"></a>C# 6.0 版

C# 在 3.0 版和 5.0 版对面向对象的语言添加了主要的新功能。 在 6.0 版中，它不再推出主导性的杀手锏，而是发布了很多使得 C# 编程更有效率的小功能。 以下介绍了部分功能：

- [静态导入](../language-reference/keywords/using-static.md)
- [异常筛选器](https://www.thomaslevesque.com/2015/06/21/exception-filters-in-c-6/)
- [属性初始值设定项](http://geekswithblogs.net/WinAZ/archive/2015/06/30/whatrsquos-new-in-c-6.0-auto-property-initializers.aspx)
- [Expression bodied 成员](https://lostechies.com/jimmybogard/2015/12/17/c-6-feature-review-expression-bodied-function-members/)
- [Null 传播器](https://davefancher.com/2014/08/14/c-6-0-null-propagation-operator/)
- [字符串内插](../language-reference/tokens/interpolated.md)
- [nameof 运算符](https://stackoverflow.com/questions/31695900/what-is-the-purpose-of-nameof)
- [索引初始值设定项](csharp-6.md#index-initializers)

其他新功能包括：

- Catch/Finally 块中的 Await
- 仅限 getter 属性的默认值

这些功能每一个都很有趣。 但从整体来看，可以发现一个有趣的模式。 在此版本中，C# 消除语言样本，让代码更简洁且更具可读性。 所以对喜欢简洁代码的用户来说，此语言版本非常成功。

除了发布此版本，他们还做了另一件事，虽然这件事本身与传统的语言功能无关。 他们发布了 [Roslyn 编译器即服务](https://github.com/dotnet/roslyn)。 C# 编译器现在是用 C# 编写的，你可以使用编译器作为编程工作的一部分。

## <a name="c-version-70"></a>C# 7.0 版

C# 7.0 版是最新的主版本。 虽然该版本继承和发展了 C# 6.0，但不包含编译器即服务。 以下介绍了部分新增功能：

- [Out 变量](http://www.c-sharpcorner.com/article/out-variables-in-c-sharp-7-0/)
- [元组和析构函数](https://www.thomaslevesque.com/2016/08/23/tuple-deconstruction-in-c-7/)
- [模式匹配](./csharp-7.md#pattern-matching)
- [本地函数](http://www.infoworld.com/article/3182416/application-development/c-7-in-depth-exploring-local-functions.html)
- [已扩展 expression bodied 成员](./csharp-7.md#more-expression-bodied-members)
- [Ref 局部变量和返回结果](./csharp-7.md#ref-locals-and-returns)

其他功能包括：

- [弃元](../discards.md)
- [二进制文本](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.0/binary-literals.md)
- [数字分隔符](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.0/digit-separators.md)
- ref 返回值和局部变量
- [引发表达式](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.0/throw-expression.md)

这些都为开发者提供了很棒的新功能，帮助编写比以往任何时候都简洁的代码。 重点是缩减了使用 `out` 关键字的变量声明，并通过元组实现了多个返回值。

但 C# 的用途更加广泛了。 .NET Core 现在面向所有操作系统，着眼于云和可移植性。  语言设计者除了推出新功能外，也会在这些新功能方面付出时间和精力。

_文章_[_最初发布在 NDepend 博客上_](https://blog.ndepend.com/c-versions-look-language-history/)_，由 Erik Dietrich 和 Patrick Smacchia 提供_。
