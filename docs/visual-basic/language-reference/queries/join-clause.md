---
title: Join 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: 2186954ab6536988271629c4feba0a40563bfc3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603907"
---
# <a name="join-clause-visual-basic"></a>Join 子句 (Visual Basic)
将两个集合合并为单个集合。 联接操作基于匹配键对，使用`Equals`运算符。  
  
## <a name="syntax"></a>语法  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a>部件  
 `element`  
 必须的。 一个被联接集合控制变量。  
  
 `collection`  
 必须的。 集合以与在左侧的标识的集合进行组合`Join`运算符。 A`Join`子句可以嵌套在另一个`Join`子句，或在`Group Join`子句。  
  
 `joinClause`  
 可选。 一个或多个其他`Join`进一步限制查询。  
  
 `groupJoinClause`  
 可选。 一个或多个其他`Group Join`进一步限制查询。  
  
 `key1` `Equals` `key2`  
 必须的。 标识被联接集合的键。 必须使用`Equals`运算符从被联接集合的键进行比较。 你可以通过使用组合联接条件`And`运算符来标识多个密钥。 `key1` 必须从左侧的内容的集合`Join`运算符。 `key2` 必须从右侧的集合`Join`运算符。  
  
 联接条件中使用的密钥可以是包含集合中的多个项的表达式。 但是，每个键的表达式可以包含仅其各自的集合中的项。  
  
## <a name="remarks"></a>备注  
 `Join`子句将基于匹配被联接集合中的键值对的两个集合合并。 生成的集合可以包含标识的左侧的集合中的值的任意组合`Join`运算符和中标识的集合`Join`子句。 该查询将返回仅为其指定的条件的结果`Equals`满足运算符。 这相当于`INNER JOIN`SQL 中。  
  
 你可以使用多个`Join`中要联接成单个集合的两个或多个集合的查询子句。  
  
 你可以执行隐式联接来组合而无需集合`Join`子句。 若要执行此操作，包括多个`In`中的子句你`From`子句并指定`Where`子句，它标识你想要用于联接的键。  
  
 你可以使用`Group Join`子句来组合为单个分层集合的集合。 这就像`LEFT OUTER JOIN`SQL 中。  
  
## <a name="example"></a>示例  
 下面的代码示例执行隐式联接与其订单与合并的客户的列表。  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## <a name="example"></a>示例  
 下面的代码示例通过使用联接两个集合`Join`子句。  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 此示例将生成类似于下面的输出：  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a>示例  
 下面的代码示例通过使用联接两个集合`Join`子句的两个键列。  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 此示例将生成类似于下面的输出：  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [查询](../../../visual-basic/language-reference/queries/queries.md)  
 [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Group Join 子句](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)
