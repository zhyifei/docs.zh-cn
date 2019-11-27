---
title: Group Join 子句
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupJoinIn
- vb.QueryGroupJoinOn
- vb.QueryGroupJoin
- vb.QueryGroupJoinInto
helpviewer_keywords:
- Group Join clause [Visual Basic]
- Group Join statement [Visual Basic]
- queries [Visual Basic], Group Join
ms.assetid: 37dbf79c-7b5c-421b-bbb7-dadfd2b92a1c
ms.openlocfilehash: 0546c86322663ce6c56a89e63311d0f02f88cfe4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346842"
---
# <a name="group-join-clause-visual-basic"></a>Group Join 子句 (Visual Basic)
将两个集合合并为单个分层集合。 联接运算基于匹配键。  
  
## <a name="syntax"></a>语法  
  
```vb  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a>部件  
  
|术语|Definition|  
|---|---|  
|`element`|必需。 要联接的集合的控件变量。|  
|`type`|可选。 `element` 的类型。 如果未指定 `type`，则 `element` 的类型将从 `collection`推断。|  
|`collection`|必需。 要与位于 `Group Join` 运算符左侧的集合组合的集合。 `Group Join` 子句可以嵌套在 `Join` 子句中，也可以嵌套在另一个 `Group Join` 子句中。|  
|`key1` `Equals` `key2`|必需。 标识要联接的集合的键。 必须使用 `Equals` 运算符来比较要联接的集合中的键。 可以通过使用 `And` 运算符来标识多个键，从而组合联接条件。 `key1` 参数必须来自 `Join` 运算符左侧的集合。 `key2` 参数必须来自 `Join` 运算符右侧的集合。<br /><br /> 联接条件中使用的键可以是包含集合中多个项的表达式。 但是，每个键表达式只能包含其各自集合中的项。|  
|`expressionList`|必需。 一个或多个表达式，用于标识集合中的元素组的聚合方式。 若要标识分组结果的成员名称，请使用 `Group` 关键字（`<alias> = Group`）。 还可以包含聚合函数以将其应用于该组。|  
  
## <a name="remarks"></a>备注  
 `Group Join` 子句基于要联接的集合中的匹配键值合并两个集合。 生成的集合可以包含一个成员，该成员引用第二个集合中与第一个集合中的键值相匹配的元素的集合。 还可以指定要应用于第二个集合中的分组元素的聚合函数。 有关聚合函数的信息，请参阅[Aggregate 子句](../../../visual-basic/language-reference/queries/aggregate-clause.md)。  
  
 例如，考虑一个经理集合和一组雇员。 这两个集合中的元素都具有 ManagerID 属性，该属性标识向特定经理报告的员工。 联接操作的结果将包含具有匹配的 ManagerID 值的每个经理和员工的结果。 `Group Join` 操作的结果将包含管理器的完整列表。 每个管理器结果都有一个成员，该成员引用了与特定经理匹配的员工列表。  
  
 由 `Group Join` 操作产生的集合可以包含 `From` 子句中标识的集合中的任何值组合和 `Group Join` 子句的 `Into` 子句中标识的表达式。 有关 `Into` 子句的有效表达式的详细信息，请参阅[Aggregate 子句](../../../visual-basic/language-reference/queries/aggregate-clause.md)。  
  
 `Group Join` 操作将从 `Group Join` 运算符左侧标识的集合中返回所有结果。 即使要联接的集合中没有匹配项，也是如此。 这类似于 SQL 中的 `LEFT OUTER JOIN`。  
  
 您可以使用 `Join` 子句将集合合并为单个集合。 这等效于 SQL 中的 `INNER JOIN`。  
  
## <a name="example"></a>示例  
 下面的代码示例使用 `Group Join` 子句联接两个集合。  
  
 [!code-vb[VbSimpleQuerySamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#14)]  
  
## <a name="see-also"></a>另请参阅

- [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [查询](../../../visual-basic/language-reference/queries/index.md)
- [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)
- [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)
- [Join 子句](../../../visual-basic/language-reference/queries/join-clause.md)
- [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)
- [Group By 子句](../../../visual-basic/language-reference/queries/group-by-clause.md)
