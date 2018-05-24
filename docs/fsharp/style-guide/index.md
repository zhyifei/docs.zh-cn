---
title: 'F # 样式指南'
description: '了解良好的 F # 代码的五个原则。'
ms.date: 05/14/2018
ms.openlocfilehash: 6d8c1336ca991040a8f6e13290d209cb3b70054d
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
---
# <a name="f-style-guide"></a>F # 样式指南

以下文章介绍指引，用于格式设置 F # 代码和适用的语言功能指南以及应如何使用它们。

具有基于已表述本指南在大型的 F # 使用与程序员的不同组的基本代码。 本指南通常会导致 F # 的成功使用，并随着时间的推移程序的需求变化时最大程度减少麻烦。

## <a name="five-principles-of-good-f-code"></a>良好的 F # 代码的五个原则

你应记住以下原则在编写 F # 代码中，尤其是在将随时间变化的系统时。 进一步文章中的指南的每个段起源于这些五个点。

1. **良好的 F # 代码是简洁而易于表示**

    F # 包含许多功能，使您能够更少的代码行中表达的操作并重用一般功能。 F # 核心库还包含许多有用的类型和功能以处理的数据的通用集合。 作为一般规则，如果您可以表示更少的代码，行中的问题的解决方案其他开发人员 （或你将来自助） 将 appreciative。 此外强烈建议你使用库，例如 FSharp.Core， [vast.NET 库](https://docs.microsoft.com/dotnet/api/)F # 运行，或上的第三方包[NuGet](https://www.nuget.org/)何时需要执行重要任务。

2. **良好的 F # 代码是可互操作**

    间的互操作可以采用多种形式，包括使用不同语言的代码。 其他调用方的互操作使用你代码的边界是正确的关键部分。 当编写 F # 时，您应始终认为有关如何其他代码将调入你正在编写的包括如果它们在这样做通过 C# 之类的其他语言的代码。 [F # 组件设计准则](component-design-guidelines.md)描述互操作性详细信息。

3. **良好的 F # 代码使对象编程的使用，不对象方向**

    F # 包含在.NET 中，使用对象进行编程的完全支持包括[类](../language-reference/classes.md)，[接口](../language-reference/interfaces.md)，[访问修饰符](../language-reference/access-control.md)，[抽象类](../language-reference/abstract-classes.md)，依次类推。 对于更复杂的功能代码，如必须上下文感知的函数对象可以轻松地封装函数不能的方式的上下文的信息。 功能如[可选参数](../language-reference/members/methods.md#optional-arguments)和[重载](../language-reference/members/methods.md#overloaded-methods)还帮助此功能的调用方的消耗。

4. **良好的 F # 代码执行，也不公开转变**

    它是，如果要编写高性能代码，必须先使用转变任何机密。 它是计算机的工作原理，别忘了。 此类代码很容易出错且较为困难正确。 避免公开给调用方的转变。 查找功能的接口比基于转变的实现。

5. **良好的 F # 代码是非常有用**

    有关使用大型基本代码，工具是非常重要，可以编写 F # 代码，以便可以使用 F # 语言工具更有效地使用。 一个示例时，必须确保你不要过度用点释放样式编程，以便可以通过调试器检查中间值。 另一个示例使用[XML 文档注释](../language-reference/xml-documentation.md)描述构造，以便在编辑器中的工具提示可以在调用站点处显示这些注释。 始终考虑如何在代码将可以读取、 导航、 调试，和操作其工具与其他程序员。

## <a name="next-steps"></a>后续步骤

[F # 代码格式设置准则](formatting.md)指南提供有关如何设置代码格式，使它易于阅读。

[F # 编码约定](conventions.md)提供有关 F # 编程习语有助于长期维护更大的 F # 的基本代码的指导。

[F # 组件设计准则](component-design-guidelines.md)提供了创作 F # 组件，如库的指南。
