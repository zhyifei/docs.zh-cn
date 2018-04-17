---
title: 类型提供程序
description: '了解如何提供类型、 属性和方法，在程序中的使用方法的组件的 F # 类型提供程序。'
author: cartermp
ms.author: phcart
ms.date: 04/02/2018
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 25697ef6-465e-4248-9de5-1d199d4a8b59
ms.openlocfilehash: 248fb2db2364cdad53e701603fd2cada33498701
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="type-providers"></a>类型提供程序

F# 类型提供程序是提供在程序中使用的类型、属性和方法的组件。 类型提供程序生成所谓的**提供类型**，它由 F # 编译器生成并基于外部数据源。

例如，SQL 的 F # 类型提供可以生成表示表和关系数据库中的列的类型。 事实上，这是什么[SQLProvider](https://fsprojects.github.io/SQLProvider/)类型提供程序执行。

提供类型取决于输入参数类型提供程序。 此类输入可以是示例数据源 （如 JSON 架构中的文件），直接指向外部服务或数据源的连接字符串的 URL。 类型提供程序还可确保按需; 的用户仅能展开类型组也就是说，则将其展开如果类型实际上由你的程序引用。 这允许以强类型的方式直接按需集成大型信息空间（如联机数据市场）。

## <a name="generative-and-erased-type-providers"></a>生成和已擦除的类型提供程序

类型提供程序有两种形式： 生成和清除。

生成的类型提供程序生成可以在生成的程序集到编写为.NET 类型的类型。 这使它们可以从其他程序集中的代码使用。 这意味着，数据源的类型化的表示都必须以通常是一个可以使用.NET 类型表示。

擦除的类型提供程序生成只能在程序集或从生成的项目中使用的类型。 类型是暂时;即它们不会写入到程序集，并且不能供其他程序集中的代码。 它们可以包含*延迟*成员，从可能无限的信息空间允许你以供使用提供的类型。 它们可用于使用大型和相互连接的数据源的一个小子集。

## <a name="commonly-used-type-providers"></a>常用类型提供程序

以下的广泛使用的库包含不同用途的类型提供程序：

- [FSharp.Data](https://fsharp.github.io/FSharp.Data/)的 JSON、 XML、 CSV 和 HTML 文档格式和资源包括类型提供程序。
- [SQLProvider](https://fsprojects.github.io/SQLProvider/)提供对这些数据源的查询的强类型访问通过对象映射和 F # LINQ 的关系数据库。
- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/)编译时的类型提供程序的一组已选中 T-SQL 的 F # 中的嵌入。
- [Azure 存储类型提供程序](https://fsprojects.github.io/AzureStorageTypeProvider/)提供了 Azure Blob、 表和队列，从而可以访问这些资源，而无需将资源名称指定为在整个程序的字符串的类型。
- [FSharp.Data.GraphQL](https://fsprojects.github.io/FSharp.Data.GraphQL/index.html)包含**GraphQLProvider**，该属性提供基于 GraphQL server URL 指定的类型。

根据需要，你可以[创建你自己的自定义类型提供程序](creating-a-type-provider.md)，或引用已由其他人创建的类型提供程序。 例如，假定你的组织具有一种数据服务，该服务提供了数量不断增长的命名数据集，每个数据集都有其自己的稳定数据架构。 你可选择创建一种类型提供程序，该程序不仅读取架构，还以强类型方式将最新的可用数据集提供给程序员。

## <a name="see-also"></a>另请参阅
[教程： 创建类型提供程序](creating-a-type-provider.md)

[F# 语言参考](../../language-reference/index.md)

[Visual F#](../../index.md)
