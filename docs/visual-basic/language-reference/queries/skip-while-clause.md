---
title: Skip While 子句
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: 47703e445865435f5bf5312c3fe41833ac21aa3f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333146"
---
# <a name="skip-while-clause-visual-basic"></a>Skip While 子句 (Visual Basic)
跳过集合中指定条件为 `true` 的任何元素，然后返回剩余元素。  
  
## <a name="syntax"></a>语法  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`expression`|必须的。 An expression that represents a condition to test elements for. The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.|  
  
## <a name="remarks"></a>备注  
 The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`. After `expression` returns `false`, the query returns all the remaining elements. The `expression` is ignored for the remaining results.  
  
 The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition. The `Skip While` clause excludes elements only until the first time that the condition is not satisfied. The `Skip While` clause is most useful when you are working with an ordered query result.  
  
 You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.  
  
## <a name="example"></a>示例  
 The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [查询](../../../visual-basic/language-reference/queries/index.md)
- [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)
- [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)
- [Skip 子句](../../../visual-basic/language-reference/queries/skip-clause.md)
- [Take While 子句](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)
