---
title: Skip 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: 1810bf4a6573c6fa36f1d8149bf341d45cfd6f52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602822"
---
# <a name="skip-clause-visual-basic"></a>Skip 子句 (Visual Basic)
绕过集合中指定数量的元素，然后返回剩余的元素。  
  
## <a name="syntax"></a>语法  
  
```  
Skip count  
```  
  
## <a name="parts"></a>部件  
 `count`  
 必须的。 一个值或表达式计算结果为要跳过的序列的元素的数目。  
  
## <a name="remarks"></a>备注  
 `Skip`子句将使查询以绕过结果列表的开头处的元素，并返回剩余元素。 要跳过的元素数由`count`参数。  
  
 你可以使用`Skip`子句`Take`子句从查询的任何段返回的数据范围。 若要执行此操作，将传递到范围的第一个元素的索引`Skip`子句和的范围的大小`Take`子句。  
  
 当你使用`Skip`子句在查询中的，你可能还需要确保，将启用顺序返回的结果`Skip`子句，以绕过预期的结果。 有关对查询结果进行排序的详细信息，请参阅[Order By 子句](../../../visual-basic/language-reference/queries/order-by-clause.md)。  
  
 你可以使用`SkipWhile`子句来指定，只有某些元素将被忽略，具体取决于提供的条件。  
  
## <a name="example"></a>示例  
 下面的代码示例使用`Skip`连同子句`Take`子句，以从页中的某个查询返回数据。 `GetCustomers`函数使用`Skip`子句以跳过列表中的客户，直到提供的起始索引值，并使用`Take`子句返回客户从该索引值开始页。  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-clause_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [查询](../../../visual-basic/language-reference/queries/queries.md)  
 [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Order By 子句](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Skip While 子句](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Take 子句](../../../visual-basic/language-reference/queries/take-clause.md)
