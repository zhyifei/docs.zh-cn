---
title: F# 样式指南
description: 了解良好 F# 代码的五个原则。
ms.date: 12/10/2018
ms.openlocfilehash: 9f47257626e04b09b546de2ae315d48d791678be
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401111"
---
# <a name="f-style-guide"></a>F# 样式指南

以下文章介绍了 F# 代码的格式设置指南以及语言功能的专题指南以及如何使用它们。

本指南是根据在具有不同程序员组的大型代码库中使用 F# 制定的。 本指南通常会导致 F# 的成功使用，并最大限度地减少程序要求随时间变化时的挫折感。

## <a name="five-principles-of-good-f-code"></a>良好 F# 代码的五个原则

在编写 F# 代码时，请记住以下原则，尤其是在随时间变化的系统中。 进一步文章中的每一条指导都源于这五点。

1. **好的 F# 代码简洁、富有表现力且可组合**

    F# 具有许多功能，允许您以更少的代码行表示操作并重用通用功能。 F# 核心库还包含许多有用的类型和函数，用于处理常见的数据集合。 您自己的函数和 F# 核心库（或其他库）中的函数的组成是常规惯用 F# 编程的一部分。 通常，如果能够用更少的代码行来表达问题的解决方案，其他开发人员（或您未来的自我）将非常感激。 强烈建议您使用 FSharp.Core、F# 运行[的庞大 .NET 库](../../../api/index.md)等库，或者当您需要执行一项不平凡的任务时，使用[NuGet](https://www.nuget.org/)上的第三方包。

2. **好的 F# 代码是可互操作的**

    互操作可以采取多种形式，包括使用不同语言的代码。 其他调用方互操作的代码边界是正确获取的关键部分，即使调用方也位于 F#中也是如此。 编写 F#时，应始终考虑如何将其他代码调用您编写的代码，包括它们是否从其他语言（如 C#）调用。 [F# 组件设计指南](component-design-guidelines.md)详细介绍了互操作性。

3. **好的 F# 代码使用对象编程，而不是面向对象**

    F# 完全支持使用 .NET 中的对象进行编程，包括[类](../language-reference/classes.md)、[接口](../language-reference/interfaces.md)、[访问修改器](../language-reference/access-control.md)、[抽象类](../language-reference/abstract-classes.md)等。 对于更复杂的功能代码（如必须具有上下文感知功能的函数），对象可以轻松地以函数无法的方式封装上下文信息。 [可选参数](../language-reference/members/methods.md#optional-arguments)和谨慎使用[重载](../language-reference/members/methods.md#overloaded-methods)等功能可以使调用方更轻松地使用此功能。

4. **良好的 F# 代码在未暴露突变的情况下表现良好**

    编写高性能代码，必须使用突变，这已不为人有。 毕竟，这是计算机的工作原理。 此类代码通常容易出错，难以正确。 避免向呼叫者公开突变。 相反，[构建一个功能接口，在性能至关重要时隐藏基于突变的实现](conventions.md#performance)。

5. **好的 F# 代码是可工具的**

    工具对于在大型代码库中工作非常宝贵，您可以编写 F# 代码，以便可以更有效地将其用于 F# 语言工具。 一个例子是确保您不会使用无点编程样式过度使用，以便可以使用调试器检查中间值。 另一个示例是使用[XML 文档注释](../language-reference/xml-documentation.md)来描述构造，以便编辑器中的工具提示可以在调用站点显示这些注释。 始终思考如何被其他程序员使用他们的工具读取、导航、调试和操作代码。

## <a name="next-steps"></a>后续步骤

[F# 代码格式设置指南](formatting.md)提供有关如何设置代码格式以便易于阅读的指导。

[F# 编码约定](conventions.md)为 F# 编程习惯用语提供指导，这将有助于对较大的 F# 代码库进行长期维护。

[F# 组件设计指南](component-design-guidelines.md)为编写 F# 组件（如库）提供了指南。
