---
title: Skip While 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: 9d95dc4a9f61a9ec3a50f9d594b31d673c2d3764
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="skip-while-clause-visual-basic"></a>Skip While 子句 (Visual Basic)
跳过集合中指定条件为 `true` 的任何元素，然后返回剩余元素。  
  
## <a name="syntax"></a>语法  
  
```  
Skip While expression  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`expression`|必须的。 一个表示要测试的元素的条件的表达式。 该表达式必须返回`Boolean`值或等效的功能，如`Integer`作为计算`Boolean`。|  
  
## <a name="remarks"></a>备注  
 `Skip While`子句跳过任何元素，直到所提供的查询结果从头`expression`返回`false`。 后`expression`返回`false`，查询返回所有剩余的元素。 `expression`对于剩余的结果，将忽略。  
  
 `Skip While`子句不同于`Where`中的子句`Where`子句可用来从不满足特定条件的查询中排除的所有元素。 `Skip While`子句仅在未满足的条件的第一个时间排除元素。 `Skip While`子句在你正在使用排序的查询结果时最有用。  
  
 可以通过使用绕过特定数目的结果从开始处的查询结果`Skip`子句。  
  
## <a name="example"></a>示例  
 下面的代码示例使用`Skip While`子句以跳过的结果，直到找到第一个客户从美国。  
  
 [!code-vb[VbSimpleQuerySamples#3](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-while-clause_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [查询](../../../visual-basic/language-reference/queries/queries.md)  
 [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Skip 子句](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [Take While 子句](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)
