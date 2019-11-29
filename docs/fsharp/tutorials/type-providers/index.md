---
title: 类型提供程序
description: 了解F#类型提供程序如何提供在程序中使用的类型、属性和方法的组件。
ms.date: 04/02/2018
ms.openlocfilehash: 7fa0ff6b5f2b0bc978df2988f22b2042acc22320
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552920"
---
# <a name="type-providers"></a>类型提供程序

F# 类型提供程序是提供在程序中使用的类型、属性和方法的组件。 类型提供程序生成称为所**提供类型**的类型，这些类型由F#编译器生成，并且基于外部数据源。

例如，SQL F#类型提供程序可以生成表示关系数据库中的表和列的类型。 事实上，这是[SQLProvider](https://fsprojects.github.io/SQLProvider/)类型提供程序所执行的操作。

提供的类型依赖于类型提供程序的输入参数。 此类输入可以是示例数据源（如 JSON 架构文件）、直接指向外部服务的 URL 或数据源的连接字符串。 类型提供程序还可确保仅按需展开类型组;也就是说，如果类型实际上是由你的程序引用的，则将扩展它们。 这允许以强类型的方式直接按需集成大型信息空间（如联机数据市场）。

## <a name="generative-and-erased-type-providers"></a>生成和已擦除的类型提供程序

类型提供程序采用两种形式：生成和已清除。

生成类型提供程序生成可作为 .NET 类型写入到生成它们的程序集中的类型。 这使它们可以从其他程序集中的代码使用。 这意味着数据源的类型化表示形式通常必须是可与 .NET 类型一起表示的类型化表示形式。

擦除类型提供程序生成只能在生成它们的程序集或项目中使用的类型。 类型是暂时的;也就是说，它们不会写入程序集，也不能由其他程序集中的代码使用。 它们可以包含*延迟*成员，使你可以使用提供的类型，这些类型可能会无限的信息空间。 它们对于使用大型和互连数据源的一小部分很有用。

## <a name="commonly-used-type-providers"></a>常用类型提供程序

以下广泛使用的库包含用于不同用途的类型提供程序：

- [Fsharp.core](https://fsharp.github.io/FSharp.Data/)包括适用于 JSON、XML、CSV 和 HTML 文档格式和资源的类型提供程序。
- [SQLProvider](https://fsprojects.github.io/SQLProvider/)通过对象映射以及针对这些数据源的 LINQ 查询， F#提供对关系数据库的强类型访问。
- [Fsharp.core](https://fsprojects.github.io/FSharp.Data.SqlClient/)包含一组类型提供程序，用于在中F#对 t-sql 进行编译时检查。
- [Azure 存储类型提供程序](https://fsprojects.github.io/AzureStorageTypeProvider/)提供 azure Blob、表和队列的类型，使你可以访问这些资源，而无需在整个程序中将资源名称指定为字符串。
- [Fsharp.core](https://fsprojects.github.io/FSharp.Data.GraphQL/index.html)包含**GraphQLProvider**，它基于 URL 指定的 GraphQL 服务器提供类型。

如果需要，你可以[创建自己的自定义类型提供程序](creating-a-type-provider.md)，或引用其他人创建的类型提供程序。 例如，假定你的组织具有一种数据服务，该服务提供了数量不断增长的命名数据集，每个数据集都有其自己的稳定数据架构。 你可选择创建一种类型提供程序，该程序不仅读取架构，还以强类型方式将最新的可用数据集提供给程序员。

## <a name="see-also"></a>另请参阅

- [教程：创建类型提供程序](creating-a-type-provider.md)
- [F# 语言参考](../../language-reference/index.md)
