---
title: "C# 的 C# 指南的历史记录"
description: "未语言查看喜欢什么在其最早的版本中，以及如何它已发展自？"
keywords: "C#，.NET，.NET 核心，最新内容、 C# 历史记录"
author: erikdietrich
ms.author: wiwagn
ms.date: 09/20/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.openlocfilehash: 207c97c5dd7e04f815da61bff7f44393aea86222
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="the-history-of-c"></a>C# 的历史记录 #

未语言怎样的在其最早的版本？ 和如何具有它改进以来？

## <a name="c-version-10"></a>C# 1.0 版

当你返回去查找时，C# 1.0 版 的样子大量 Java。 作为[ECMA 及其规定的设计目标的一部分](http://feeldotneteasy.blogspot.com/2011/01/c-design-goals.html)，它查找为"简单、 现代、 常规用途面向对象的语言。"  当时，看起来像 Java 意味着它来实现这些早期的设计目标。

但如果你重新查看在 C# 1.0 上现在，你会发现自己有点 dizzy。 它不具备内置的异步功能并介绍一些围绕我们执行授予的泛型的巧妙功能。 事实上，它不具备泛型完全。  和[LINQ](../linq/index.md)？ 不可用尚未。 这会打开未来某些几年。

C# 1.0 版 看上去去除的功能，为今天比较。 你会发现自己编写一些详细的代码。 但是，必须从零开始。 C# 1.0 版 已在 Windows 平台上的与 Java 代替。

## <a name="c-version-20"></a>C# 2.0 版

现在，事情开始令人感兴趣。 让我们看看 C# 2.0 中，于 2005，以及 Visual Studio 2005 年发布的一些主要功能：

- [泛型](../programming-guide/generics/index.md)
- [分部类型](../programming-guide/classes-and-structs/partial-classes-and-methods.md#partial-classes)
- [匿名方法](../programming-guide/statements-expressions-operators/anonymous-methods.md)
- [可以为 null 的类型](../programming-guide/nullable-types/index.md)
- [迭代器](../programming-guide/concepts/iterators.md)
- [协变和逆变](../programming-guide/concepts/covariance-contravariance/index.md)

虽然 C# 可能启动作为非常泛型面向 (OO) 语言，C# 2.0 版更改的时间紧。 一旦他们已有在其下的其英尺，它们后并重新某些严重的开发人员的难点。 和它们后并重新它们的力度。

采用泛型必须类型和可以应用于任意类型同时仍然保留类型安全的方法。 因此，例如，具有<xref:System.Collections.Generic.List%601>您可以让`List<string>`或`List<int>`，并对这些字符串或整数的类型安全操作在执行循环访问它们。 这是创建更好`ListInt`继承者或从强制转换`Object`执行每个操作。

C# 2.0 版使迭代器。 若要用于简单地说，这样就可以循环访问中的项`List`（或其他可枚举类型） 与`foreach`循环。 无语言的第一类的一部分这显著增强语言和人的功能的代码的相关的原因的可读性。

而尚未，C# 继续执行播放追赶 Java 位。 Java 具有已发布版本，包括泛型和迭代器。 但，很快将更改为不断提高，拆分的语言。

## <a name="c-version-30"></a>C# 3.0 版

C# 3.0 版提供在后期 2007 中，以及 Visual Studio 2008 起，尽管语言功能完整船将实际附带 C# 版本 3.5。 此版本标记中的 C# 增长了重大更改。 它在建立 C# 作为真正强大的编程语言。 在此版本中，让我们看一些主要功能：

- [自动实现属性](../programming-guide/classes-and-structs/auto-implemented-properties.md)
- [匿名类型](../programming-guide/classes-and-structs/anonymous-types.md)
- [查询表达式](../linq/query-expression-basics.md)
- [Lambda 表达式](https://www.daedtech.com/introduction-to-c-lambda-expressions/)
- [表达式树](https://blogs.msdn.microsoft.com/charlie/2008/01/31/expression-tree-basics/)
- [扩展方法](https://www.codeproject.com/Tips/709310/Extension-Method-In-Csharp)

回顾，其中的许多功能看起来不可避免地和不可分离。 它们都组合在一起，多个巧妙布局。 通常认为 C# 版本的最酷功能是查询表达式，也称为语言集成查询 (LINQ)。

更能体现细微差别的视图检查作为在其构造 LINQ 基础表达式 tress、 lambda 表达式和匿名类型。 但是，在任一情况下，C# 3.0 呈现的革命性工作的概念。 C# 3.0 已开始奠定了用于将 C# 为混合面向对象 / 函数语言。

具体而言，你现在可以编写 SQL 样式，执行对集合，以及其他用途的操作的声明性查询。 而不是编写`for`循环计算整数列表的平均值，你无法立即执行该操作简单地作为`list.Average()`。 查询表达式和扩展方法的组合进行它看上去就好像该列表的整数中的已收到整个批次更智能。

所花费的时间给用户真正抓住和将其集成了概念，但在逐渐相同。 现在，更高版本，年代码更简洁、 更简单而且功能。

## <a name="c-version-40"></a>C# 4.0 版

C# 版本 4.0，则必须难居住到版本 3.0 的创新状态。 3.0 版开始，C# 已移语言牢固地缩小从阴影的 Java，并放入突出。 语言已迅速成为简洁。

下一版本未引入一些有趣的新功能：

- [动态绑定](../language-reference/keywords/dynamic.md)
- [名为/可选自变量](../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- [泛型协变和逆变](../../standard/generics/covariance-and-contravariance.md)
- [嵌入互操作类型](https://stackoverflow.com/questions/20514240/whats-the-difference-setting-embed-interop-types-true-and-false-in-visual-studi)

嵌入互操作类型缓解部署困难。 泛型协变和逆变为你提供更多的能力，若要使用的泛型，但它们有点学术机构和框架和库作者可能最高兴。 命名参数和可选参数，可以消除了许多方法重载并提供方便。 但所有这些功能完全范例更改。

主要功能已引入`dynamic`关键字。 `dynamic`关键字引入到 C# 版本 4.0 能够替代编译器在编译时类型。 通过使用动态关键字，可以创建类似于动态类型化 JavaScript 等语言构造。 你可以创建`dynamic x = "a string"`，然后添加六个到它，将其保留到运行以理清应执行的操作下一步。

这样，您可能的错误，但还语言内的能力。

## <a name="c-version-50"></a>C# 5.0 版

C# 5.0 版 时非常有针对性的版本的语言。 几乎所有该版本的工作已加入到另一个突破性语言概念。  此处是主要功能列表：

- [异步成员](../async.md)
- [调用方信息特性](https://www.codeproject.com/Tips/606379/Caller-Info-Attributes-in-Csharp)

调用方信息特性使你能够轻松地检索有关要在其中运行而无需进行大量的样板文件反射代码的上下文信息。 它有许多用途在诊断和日志记录任务中。

但是`async`和`await`是此版本的实际星号。 当时这些功能在 2012年中，C# 游戏再次更改通过异步烤到作为第一类参与者的语言。 如果你曾经处理长时间运行的操作和回调 webs 的实现，可能会非常喜欢此语言功能。

## <a name="c-version-60"></a>C# 6.0 版

版本 3.0 和 5.0，C# 具有添加一些令人印象深刻的功能的面向对象的语言。 使用版本 6.0，它将转离开执行基准最酷的功能，并改为释放满意语言的用户的许多功能。 下面是其中一些：

- [静态导入](../language-reference/keywords/using-static.md)
- [异常筛选器](https://www.thomaslevesque.com/2015/06/21/exception-filters-in-c-6/)
- [属性初始值设定项](http://geekswithblogs.net/WinAZ/archive/2015/06/30/whatrsquos-new-in-c-6.0-auto-property-initializers.aspx)
- [表达式正文成员](https://lostechies.com/jimmybogard/2015/12/17/c-6-feature-review-expression-bodied-function-members/)
- [Null 传播器](https://davefancher.com/2014/08/14/c-6-0-null-propagation-operator/)
- [字符串内插](../language-reference/keywords/interpolated-strings.md)
- [nameof 运算符](https://stackoverflow.com/questions/31695900/what-is-the-purpose-of-nameof)
- [字典初始值设定项](../programming-guide/classes-and-structs/how-to-initialize-a-dictionary-with-a-collection-initializer.md)

上述每项功能是捕获的自己的权限。 但如果你完全看一下它们，你看到的有趣的模式。 在此版本中，C# 消除语言样本，若要使代码更简洁、 更具可读性。 因此对于风扇的干净且简单，此语言版本是代码的一种极大的成功。

在相同此版本中，以及一件事，但它不是本身是传统的语言功能。 当发布它们[Roslyn 作为服务编译器](https://github.com/dotnet/roslyn)。 在 C# 中，现在编写 C# 编译器，并且可以作为你的编程工作的一部分使用编译器。

## <a name="c-version-70"></a>C# 7.0 版

最新的主要版本是 C# 7.0 版。 此版本作为服务在情况下，C# 6.0 中，但不编译器会有一些演化和冷的内容。 下面是一些新功能：

- [out变量](http://www.c-sharpcorner.com/article/out-variables-in-c-sharp-7-0/)
- [元组和析构](https://www.thomaslevesque.com/2016/08/23/tuple-deconstruction-in-c-7/)
- [模式匹配](./csharp-7.md#pattern-matching)
- [本地函数](http://www.infoworld.com/article/3182416/application-development/c-7-in-depth-exploring-local-functions.html)
- [展开的表达式正文成员](./csharp-7.md#more-expression-bodied-members)
- [Ref 局部变量和返回结果](./csharp-7.md#ref-locals-and-returns)

所有这些功能提供了面向开发人员和机会编写比以往任何时候的代码甚至更干净的冷新功能。 突出显示紧缩若要使用的变量的声明`out`关键字，以及允许通过元组的多个返回值。

但 C# 被放到曾经更广泛使用。 .NET 核心现在面向任何操作系统并具有其眼睛牢固地在云上和在可移植性。  这肯定占用语言设计器的想法和时间，除了构思新功能。

_文章_ [_最初发布 NDepend 博客上_](https://blog.ndepend.com/c-versions-look-language-history/)_。 艾力克 Dietrich 和 Patrick Smacchia。_
