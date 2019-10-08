---
title: Aggregate 子句 (Visual Basic)
ms.date: 08/28/2018
f1_keywords:
- vb.QueryAggregateIn
- vb.QueryAggregate
- vb.QueryAggregateInto
helpviewer_keywords:
- Aggregate clause [Visual Basic]
- Aggregate statement [Visual Basic]
- queries [Visual Basic], Aggregate
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
ms.openlocfilehash: 50a53cd45cc428541c90fbf82089518be2212fae
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004802"
---
# <a name="aggregate-clause-visual-basic"></a>Aggregate 子句 (Visual Basic)
将一个或多个聚合函数应用于集合。  
  
## <a name="syntax"></a>语法  
  
```vb  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`element`|必需。 用于循环访问集合中的元素的变量。|  
|`type`|可选。 `element` 的类型。 如果未指定类型，则从 @no__t 中推断出 @no__t 的类型。|  
|`collection`|必需。 引用要对其执行操作的集合。|  
|`clause`|可选。 一个或多个查询子句（如 `Where` 子句），用于优化要将聚合子句或子句应用于的查询结果。|  
|`expressionList`|必需。 一个或多个以逗号分隔的表达式，用于标识要应用于集合的聚合函数。 您可以向聚合函数应用别名，以指定查询结果的成员名称。 如果未提供别名，则使用聚合函数的名称。 有关示例，请参阅本主题后面的有关聚合函数的部分。|  
  
## <a name="remarks"></a>备注  
 @No__t-0 子句可用于在查询中包括聚合函数。 聚合函数对一组值执行检查和计算，并返回单个值。 您可以使用查询结果类型的成员访问计算值。 可使用的标准聚合函数为 `All`、`Any`、`Average`、`Count`、`LongCount`、`Max`、`Min` 和 @no__t 7 函数。 这些函数对熟悉 SQL 中聚合的开发人员非常熟悉。 本主题的下一节将对其进行介绍。  
  
 聚合函数的结果作为查询结果类型的字段包含在查询结果中。 您可以为聚合函数结果提供别名，以指定将保存聚合值的查询结果类型的成员名称。 如果未提供别名，则使用聚合函数的名称。  
  
 @No__t-0 子句可以开始查询，也可以在查询中将其作为附加子句包括在内。 如果 @no__t 0 子句开始查询，则结果为单个值，该值是在 @no__t 子句中指定的聚合函数的结果。 如果在 `Into` 子句中指定了多个聚合函数，则查询将返回单一类型，该类型具有一个单独的属性，用于在 @no__t 子句中引用每个聚合函数的结果。 如果在查询中将 `Aggregate` 子句作为附加子句包含，则在查询集合中返回的类型将具有一个单独的属性来引用 @no__t 子句中每个聚合函数的结果。  
  
## <a name="aggregate-functions"></a>聚合函数

下面是可用于 `Aggregate` 子句的标准聚合函数。  
  
### <a name="all"></a>全部

如果集合中的所有元素都满足指定的条件，则返回 `true`;否则返回 `false`。 下面是一个示例：

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a>任意

如果集合中的任何元素满足指定的条件，则返回 `true`;否则返回 `false`。 下面是一个示例：

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a>Average

计算集合中所有元素的平均值，或为集合中的所有元素计算提供的表达式。 下面是一个示例：

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a>Count

计算集合中元素的数目。 可以提供一个可选的 @no__t 0 表达式，以便仅对集合中满足条件的元素数进行计数。 下面是一个示例：

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a>Group

指作为 @no__t 或 @no__t 子句的结果进行分组的查询结果。 @No__t-0 函数仅在 @no__t 或 @no__t 子句的 `Into` 子句中有效。 有关详细信息和示例，请参阅[Group By 子句](../../../visual-basic/language-reference/queries/group-by-clause.md)和[group Join 子句](../../../visual-basic/language-reference/queries/group-join-clause.md)。

### <a name="longcount"></a>LongCount

计算集合中元素的数目。 可以提供一个可选的 @no__t 0 表达式，以便仅对集合中满足条件的元素数进行计数。 返回 @no__t 0 形式的结果。 有关示例，请参阅 `Count` 聚合函数。

### <a name="max"></a>最大值

计算集合中的最大值，或为集合中的所有元素计算提供的表达式。 下面是一个示例：

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a>最小值

计算集合中的最小值，或为集合中的所有元素计算提供的表达式。 下面是一个示例：

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a>Sum

计算集合中所有元素的和，或为集合中的所有元素计算提供的表达式。 下面是一个示例：

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a>示例  

下面的示例演示如何使用 `Aggregate` 子句将聚合函数应用于查询结果。  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a>创建用户定义聚合函数

 您可以通过将扩展方法添加到 <xref:System.Collections.Generic.IEnumerable%601> 类型，在查询表达式中包含您自己的自定义聚合函数。 然后，您的自定义方法可以对引用了聚合函数的可枚举集合执行计算或操作。 有关扩展方法的详细信息，请参阅[扩展方法](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)。  
  
 例如，下面的示例显示了一个自定义聚合函数，该函数计算数字集合的中间值。 @No__t 的扩展方法有两个重载。 第一次重载接受类型为 `IEnumerable(Of Double)` 的集合作为输入。 如果为 `Double` 类型的查询字段调用 `Median` 聚合函数，则将调用此方法。 可以将 `Median` 方法的第二个重载传递到任何泛型类型。 @No__t-0 方法的泛型重载使用第二个参数，该参数引用 @no__t 1 lambda 表达式，以便将类型（来自集合）的值投影为类型 `Double` 的对应值。 然后，它将中间值的计算委托给 `Median` 方法的另一个重载。 有关 lambda 表达式的详细信息，请参阅 [Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 下面的示例演示了在 `Integer` 类型的集合上调用 `Median` 聚合函数以及类型 `Double` 的集合的示例查询。 对类型 `Double` 的集合调用 @no__t 0 聚合函数的查询将调用接受的 `Median` 方法的重载，该方法接受作为输入的类型 `Double` 类型的集合。 对类型 `Integer` 的集合调用 @no__t 0 聚合函数的查询将调用 @no__t 2 方法的泛型重载。  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [查询](../../../visual-basic/language-reference/queries/index.md)
- [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)
- [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)
- [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)
- [Group By 子句](../../../visual-basic/language-reference/queries/group-by-clause.md)
