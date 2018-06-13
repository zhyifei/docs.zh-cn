---
title: Group Join 子句 (Visual Basic)
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
ms.openlocfilehash: 094281b0afb34451ae8539e4eb967043b21d379c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604752"
---
# <a name="group-join-clause-visual-basic"></a>Group Join 子句 (Visual Basic)
将两个集合合并为单个分层集合。 联接操作基于匹配键对。  
  
## <a name="syntax"></a>语法  
  
```  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`element`|必须的。 一个被联接集合控制变量。|  
|`type`|可选。 `element` 的类型。 如果没有`type`指定的一种`element`从推断`collection`。|  
|`collection`|必须的。 集合以与位于左侧的内容的集合进行组合`Group Join`运算符。 A`Group Join`子句可以嵌套在`Join`子句或另一个`Group Join`子句。|  
|`key1` `Equals` `key2`|必须的。 标识被联接集合的键。 必须使用`Equals`运算符从被联接集合的键进行比较。 你可以通过使用组合联接条件`And`运算符来标识多个密钥。 `key1`参数必须是从左侧的内容的集合`Join`运算符。 `key2`参数必须是从右侧的集合`Join`运算符。<br /><br /> 联接条件中使用的密钥可以是包含集合中的多个项的表达式。 但是，每个键的表达式可以包含仅其各自的集合中的项。|  
|`expressionList`|必须的。 标识如何聚合该集合中元素的组的一个或多个表达式。 若要标识分组结果的成员名称，使用`Group`关键字 (`<alias> = Group`)。 还可以包含聚合函数以将其应用于该组。|  
  
## <a name="remarks"></a>备注  
 `Group Join`子句将基于匹配被联接集合中的键值对的两个集合合并。 生成的集合可以包含从第二个匹配从第一个集合的密钥值的集合引用的元素集合的成员。 你还可以指定要应用到分组元素从第二个集合的聚合函数。 有关聚合函数的信息，请参阅[Aggregate 子句](../../../visual-basic/language-reference/queries/aggregate-clause.md)。  
  
 例如，考虑，经理的集合和员工的集合。 从这两个集合的元素具有标识向特定的经理报告的员工的 ManagerID 属性。 联接运算的结果将包含针对每个经理和员工具有匹配 ManagerID 值的结果。 从结果`Group Join`操作将包含管理器的完整列表。 每个管理器结果都将包含引用的是特定的管理器的匹配项的员工列表的成员。  
  
 产生的集合`Group Join`操作可以包含值从集合中标识的任意组合`From`子句和中标识的表达式`Into`子句`Group Join`子句。 有关有效表达式的详细信息`Into`子句，请参阅[Aggregate 子句](../../../visual-basic/language-reference/queries/aggregate-clause.md)。  
  
 A`Group Join`操作将从左侧的标识的集合中返回所有结果`Group Join`运算符。 即使有一个被联接集合中的没有匹配项，也是如此。 这就像`LEFT OUTER JOIN`SQL 中。  
  
 你可以使用`Join`子句来组合成单个集合的集合。 这相当于`INNER JOIN`SQL 中。  
  
## <a name="example"></a>示例  
 下面的代码示例通过使用联接两个集合`Group Join`子句。  
  
 [!code-vb[VbSimpleQuerySamples#14](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-join-clause_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [查询](../../../visual-basic/language-reference/queries/queries.md)  
 [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Join 子句](../../../visual-basic/language-reference/queries/join-clause.md)  
 [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Group By 子句](../../../visual-basic/language-reference/queries/group-by-clause.md)
