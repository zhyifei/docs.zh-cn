---
title: Aggregate 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryAggregateIn
- vb.QueryAggregate
- vb.QueryAggregateInto
helpviewer_keywords:
- Aggregate clause [Visual Basic]
- Aggregate statement [Visual Basic]
- queries [Visual Basic], Aggregate
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
ms.openlocfilehash: 1db4b7fdcf9c8a38c2c49eca9d874eccea90ab1d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604895"
---
# <a name="aggregate-clause-visual-basic"></a>Aggregate 子句 (Visual Basic)
向集合应用一个或多个聚合函数。  
  
## <a name="syntax"></a>语法  
  
```  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`element`|必须的。 用于循环访问集合的元素的变量。|  
|`type`|可选。 `element` 的类型。 如果指定没有类型，则的一种`element`从推断`collection`。|  
|`collection`|必须的。 引用集合上进行操作。|  
|`clause`|可选。 一个或多个查询子句，如`Where`子句，以优化要向其应用聚合子句的查询结果。|  
|`expressionList`|必须的。 一个或多个以逗号分隔表达式，标识要将应用于集合的聚合函数。 你可以应用到聚合函数来指定查询结果的成员名称的别名。 如果不提供别名，则使用聚合函数的名称。 有关示例，请参阅有关本主题中后面的聚合函数的部分。|  
  
## <a name="remarks"></a>备注  
 `Aggregate`子句可用来在你查询中包含聚合函数。 聚合函数通过一组值执行检查和计算并返回单个值。 你可以通过使用查询结果类型的成员访问计算的值。 你可以使用标准聚合函数是`All`， `Any`， `Average`， `Count`， `LongCount`， `Max`， `Min`，和`Sum`函数。 这些函数对于熟悉的开发人员熟悉 SQL 中的聚合。 它们是本主题的以下部分中所述。  
  
 聚合函数的结果会附在查询结果作为查询的结果类型的字段。 你可以提供要指定将保存的聚合值的查询结果类型的成员的名称的聚合函数结果的别名。 如果不提供别名，则使用聚合函数的名称。  
  
 `Aggregate`子句可以开始查询，也可以是作为查询中的其他子句包括。 如果`Aggregate`子句开始查询，则结果为单个值的中指定的聚合函数的结果`Into`子句。 如果在中指定多个聚合函数`Into`子句，查询会返回单个类型使用单独的属性可引用中每个聚合函数的结果`Into`子句。 如果`Aggregate`子句是作为查询中的其他子句包含，查询集合中返回的类型都具有一个单独的属性，可引用中每个聚合函数的结果`Into`子句。  
  
## <a name="aggregate-functions"></a>聚合函数  
 以下列表介绍了可与使用标准聚合函数`Aggregate`子句。  
  
|函数|描述|  
|---|---|  
|`All`|返回`true`如果集合中的所有元素均都满足指定的条件; 否则返回`false`。 下面是一个示例：<br /><br /> [!code-vb[VbSimpleQuerySamples#5](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_1.vb)]|  
|`Any`|返回`true`在集合中的有元素满足指定的条件; 否则返回`false`。 下面是一个示例：<br /><br /> [!code-vb[VbSimpleQuerySamples#6](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_2.vb)]|  
|`Average`|计算的集合或提供的计算表达式的集合中的所有元素中的所有元素的平均值。 下面是一个示例：<br /><br /> [!code-vb[VbSimpleQuerySamples#7](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_3.vb)]|  
|`Count`|对集合中的元素数进行计数。 你可以提供一个可选`Boolean`表达式来计算仅满足条件的集合中的元素数目。 下面是一个示例：<br /><br /> [!code-vb[VbSimpleQuerySamples#8](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_4.vb)]|  
|`Group`|引用的结果进行分组的查询结果`Group By`或`Group Join`子句。 `Group`函数是仅在中有效`Into`子句`Group By`或`Group Join`子句。 有关详细信息和示例，请参阅[组 By 子句](../../../visual-basic/language-reference/queries/group-by-clause.md)和[Group Join 子句](../../../visual-basic/language-reference/queries/group-join-clause.md)。|  
|`LongCount`|对集合中的元素数进行计数。 你可以提供一个可选`Boolean`表达式来计算仅满足条件的集合中的元素数目。 将结果作为返回`Long`。 有关示例，请参阅`Count`聚合函数。|  
|`Max`|集合中的属性的最大值或计算的集合中的所有元素提供的表达式。 下面是一个示例：<br /><br /> [!code-vb[VbSimpleQuerySamples#9](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_5.vb)]|  
|`Min`|集合中的属性的最小值或计算的集合中的所有元素提供的表达式。 下面是一个示例：<br /><br /> [!code-vb[VbSimpleQuerySamples#10](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_6.vb)]|  
|`Sum`|在集合中，所有元素的总和或计算的集合中的所有元素提供的表达式。 下面是一个示例：<br /><br /> [!code-vb[VbSimpleQuerySamples#15](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_7.vb)]|  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何使用`Aggregate`子句将聚合函数应用于查询结果。  
  
 [!code-vb[VbSimpleQuerySamples#4](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_8.vb)]  
  
## <a name="creating-user-defined-aggregate-functions"></a>创建用户定义聚合函数  
 可以通过添加到扩展方法在查询表达式中包括你自己的自定义聚合函数<xref:System.Collections.Generic.IEnumerable%601>类型。 计算或聚合函数引用的可枚举集合的操作，然后可以执行自定义方法。 有关扩展方法的详细信息，请参阅[扩展方法](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)。  
  
 例如，下面的代码示例演示计算中间值的数字集合的自定义聚合函数。 有两种重载的`Median`扩展方法。 第一个重载接受，作为输入，类型的集合`IEnumerable(Of Double)`。 如果`Median`聚合函数调用为类型的查询字段`Double`，将调用此方法。 第二个重载`Median`方法可以传递任何泛型类型。 泛型重载`Median`方法采用一个引用的第二个参数`Func(Of T, Double)`lambda 表达式，以便为相应的值类型的项目 （从集合） 类型的值`Double`。 它然后委托到的其他重载的中值的计算`Median`方法。 有关 lambda 表达式的详细信息，请参阅 [Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。  
  
 [!code-vb[VbSimpleQuerySamples#18](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_9.vb)]  
  
 下面的代码示例演示了示例查询，用于调用`Median`聚合函数的集合的类型`Integer`，和类型的集合`Double`。 调用的查询`Median`聚合函数类型的集合`Double`调用的重载`Median`接受，作为输入，类型的集合的方法`Double`。 调用的查询`Median`聚合函数类型的集合`Integer`调用的泛型重载`Median`方法。  
  
 [!code-vb[VbSimpleQuerySamples#19](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_10.vb)]  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [查询](../../../visual-basic/language-reference/queries/queries.md)  
 [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Group By 子句](../../../visual-basic/language-reference/queries/group-by-clause.md)
