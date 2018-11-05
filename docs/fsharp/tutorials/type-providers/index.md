---
title: 类型提供程序
description: 了解如何提供类型、 属性和方法在您的程序中使用的组件的 F# 类型提供程序。
ms.date: 04/02/2018
ms.openlocfilehash: 5fa9de229caa2ec3ba4a248ca5cd1c8aa5adb230
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "46697758"
---
# <a name="type-providers"></a>类型提供程序

F# 类型提供程序是提供在程序中使用的类型、属性和方法的组件。 类型提供程序生成所谓**提供类型**，它由 F# 编译器生成并基于外部数据源。

例如，F# 类型提供程序的 SQL 可以生成表示关系数据库中表和列的类型。 实际上，这是什么[SQLProvider](https://fsprojects.github.io/SQLProvider/)类型提供程序执行。

提供类型取决于输入参数类型提供程序。 此类输入可以是示例数据源 （如 JSON 架构中的文件），直接指向外部服务时或数据源的连接字符串的 URL。 类型提供程序还可确保按需; 的用户仅能展开类型组也就是说，它们会展开如果你的程序实际上引用的类型。 这允许以强类型的方式直接按需集成大型信息空间（如联机数据市场）。

## <a name="generative-and-erased-type-providers"></a>生成和清除类型提供程序

类型提供程序有两种形式： 生成和清除。

生成类型提供程序生成可在生成的程序集写入为.NET 类型的类型。 这使他们能够从其他程序集中的代码使用。 这意味着数据源的类型化表示形式通常必须是一个可行表示，并将.NET 类型。

擦除类型提供程序生成仅可以在程序集或从生成的项目中使用的类型。 类型是临时;也就是说，它们不会写入到程序集和其他程序集中的代码不能使用。 它们可以包含*延迟*成员，从而可以使用提供的类型从可能的无限信息空间。 它们可用于使用大型和相互关联的数据源的一小部分。

## <a name="commonly-used-type-providers"></a>常用类型提供程序

以下广泛使用的库包含用于不同用途的类型提供程序：

- [FSharp.Data](https://fsharp.github.io/FSharp.Data/)包括 JSON、 XML、 CSV 和 HTML 文档的格式和资源类型提供程序。
- [SQLProvider](https://fsprojects.github.io/SQLProvider/)提供强类型化访问关系数据库，通过对象映射和 F# LINQ 查询对这些数据源。
- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/)的编译时类型提供程序的一组已检查的 T-SQL 的 F# 中嵌入内容。
- [Azure 存储类型提供程序](https://fsprojects.github.io/AzureStorageTypeProvider/)提供用于 Azure Blob、 表和队列，您可以访问这些资源，而无需指定资源名称作为字符串在整个程序的类型。
- [FSharp.Data.GraphQL](https://fsprojects.github.io/FSharp.Data.GraphQL/index.html)包含**GraphQLProvider**，其中提供了基于 GraphQL server URL 指定的类型。

必要时，你可以[创建自定义类型提供程序](creating-a-type-provider.md)，或引用已由其他人创建的类型提供程序。 例如，假定你的组织具有一种数据服务，该服务提供了数量不断增长的命名数据集，每个数据集都有其自己的稳定数据架构。 你可选择创建一种类型提供程序，该程序不仅读取架构，还以强类型方式将最新的可用数据集提供给程序员。

## <a name="see-also"></a>请参阅

- [教程： 创建类型提供程序](creating-a-type-provider.md)
- [F# 语言参考](../../language-reference/index.md)
- [Visual F#](../../index.md)
