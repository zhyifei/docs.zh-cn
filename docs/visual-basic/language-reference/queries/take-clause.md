---
title: Take 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: 32a4c7fd7f1e2f6fe640f3f53f15579f014759d5
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004717"
---
# <a name="take-clause-visual-basic"></a>Take 子句 (Visual Basic)
从集合的开头返回指定数量的连续元素。  
  
## <a name="syntax"></a>语法  
  
```vb  
Take count  
```  
  
## <a name="parts"></a>部件  
 `count`  
 必需。 值或计算结果为要返回的序列的元素数的表达式。  
  
## <a name="remarks"></a>备注  
 @No__t-0 子句使查询包括从结果列表的开头开始的指定数量的连续元素。 要包括的元素数由 `count` 参数指定。  
  
 可以将 `Take` 子句与 `Skip` 子句一起使用，以从查询的任何段返回数据范围。 为此，请将范围的第一个元素的索引传递到 `Skip` 子句，并将范围的大小传递到 @no__t 的子句。 在这种情况下，必须在 @no__t 1 子句之后指定 `Take` 子句。  
  
 当在查询中使用 `Take` 子句时，您可能还需要确保按使 `Take` 子句包含预期结果的顺序返回结果。 有关对查询结果进行排序的详细信息，请参阅[Order By 子句](../../../visual-basic/language-reference/queries/order-by-clause.md)。  
  
 您可以使用 `TakeWhile` 子句来指定仅返回某些元素，具体取决于所提供的条件。  
  
## <a name="example"></a>示例  
 下面的代码示例将 `Take` 子句与 @no__t 子句一起使用，以便在页中从查询返回数据。 GetCustomers 函数使用 `Skip` 子句来绕过列表中的客户，直至提供起始索引值，并使用 `Take` 子句返回从该索引值开始的客户页面。  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [查询](../../../visual-basic/language-reference/queries/index.md)
- [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)
- [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)
- [Order By 子句](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Take While 子句](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [Skip 子句](../../../visual-basic/language-reference/queries/skip-clause.md)
