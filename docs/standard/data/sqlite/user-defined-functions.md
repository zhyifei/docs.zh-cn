---
title: 用户定义的函数
ms.date: 12/13/2019
description: 了解如何创建用户定义的标量函数和聚合函数。
ms.openlocfilehash: 9ee3fbac73215353c8dc82199203b0d25e580cdb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450410"
---
# <a name="user-defined-functions"></a>用户定义的函数

大多数数据库都具有 SQL 的过程方言，可用于定义自己的函数。 但是，在应用程序的进程内运行。 无需学习新的 SQL 方言，只需使用应用的编程语言即可。

## <a name="scalar-functions"></a>标量函数

标量函数为查询中的每行返回单个标量值。 定义新的标量函数，并使用 <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>覆盖内置的函数。

有关支持的参数和返回类型的列表，请参阅[数据类型](types.md)`func` 参数。

指定 `state` 参数会将该值传递给函数的每个调用。 使用此来避免闭包。

如果函数具有确定性，则指定 `isDeterministic`，以便在编译查询时允许 SQLite 使用其他优化。

下面的示例演示如何添加标量函数以计算圆柱体的半径。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ScalarFunctionSample/Program.cs?name=snippet_CreateFunction)]

## <a name="operators"></a>运算符

以下 SQLite 运算符是通过相应的标量函数实现的。 在应用程序中定义这些标量函数将覆盖这些运算符的行为。

| 运算符          | 函数      |
| ----------------- | ------------- |
| X GLOB Y          | glob （Y，X）    |
| X 像 Y          | like （Y，X）    |
| X 像 Y ESCAPE Z | like （Y，X，Z） |
| X 匹配 Y         | match （Y，X）   |
| X REGEXP Y        | regexp （Y，X）  |

下面的示例演示如何定义 regexp 函数以启用其相应的运算符。 SQLite 不包括 regexp 函数的默认实现。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/RegularExpressionSample/Program.cs?name=snippet_Regex)]

## <a name="aggregate-functions"></a>聚合函数

聚合函数返回查询中所有行的单个聚合值。 使用 <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>定义和重写聚合函数。

`seed` 参数指定上下文的初始状态。 使用此来避免同时出现闭包。

每行调用一次 `func` 参数。 使用上下文积累最终结果。 返回上下文。 此模式允许上下文是值类型或不可变的。

如果未指定 `resultSelector`，上下文的最终状态将用作结果。 这可以简化函数（如 sum 和 count）的定义，这些函数只需递增每行的数字并返回它。

指定 `resultSelector` 以在遍历所有行后计算上下文中的最终结果。

有关 `resultSelector`的 `func` 参数和返回类型的支持参数类型的列表，请参阅[数据类型](types.md)。

如果函数是确定性的，则指定在编译查询时允许 SQLite 使用其他优化的 `isDeterministic`。

下面的示例定义了一个聚合函数，用于计算列的标准偏差。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AggregateFunctionSample/Program.cs?name=snippet_CreateAggregate)]

## <a name="errors"></a>错误

如果用户定义函数引发异常，则该消息将返回到 SQLite。 然后，SQLite 将引发错误，并且 SqliteException 将引发一个错误。 有关详细信息，请参阅[数据库错误](database-errors.md)。

默认情况下，错误 SQLite 错误代码将 SQLITE_ERROR （或1）。 但是，可以通过在函数中引发 <xref:Microsoft.Data.Sqlite.SqliteException> 并指定所需 <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> 来更改它。

## <a name="debugging"></a>调试

SQLite 直接调用实现。 这样，便可以添加在 SQLite 计算查询时触发的断点。 完整的 .NET 调试体验可帮助您创建用户定义函数。

## <a name="see-also"></a>另请参阅

* [数据类型](types.md)
* [SQLite 核心函数](https://www.sqlite.org/lang_corefunc.html)
* [SQLite 聚合函数](https://www.sqlite.org/lang_aggfunc.html)
