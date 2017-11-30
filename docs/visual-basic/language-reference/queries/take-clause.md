---
title: "Take 子句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ee289a24c15226126a526af116ed53b4a9055b35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="take-clause-visual-basic"></a>Take 子句 (Visual Basic)
从集合的开头返回指定数量的连续元素。  
  
## <a name="syntax"></a>语法  
  
```  
Take count  
```  
  
## <a name="parts"></a>部件  
 `count`  
 必需。 一个值或表达式计算结果为要返回的序列的元素的数目。  
  
## <a name="remarks"></a>备注  
 `Take`子句将使查询以包含指定的数量的结果列表的开始的连续元素。 指定要包括的元素数`count`参数。  
  
 你可以使用`Take`子句`Skip`子句从查询的任何段返回的数据范围。 若要执行此操作，将传递到范围的第一个元素的索引`Skip`子句和的范围的大小`Take`子句。 在这种情况下，`Take`子句必须指定后`Skip`子句。  
  
 当你使用`Take`子句在查询中的，你可能还需要确保，将启用顺序返回的结果`Take`子句，以包括预期的结果。 有关对查询结果进行排序的详细信息，请参阅[Order By 子句](../../../visual-basic/language-reference/queries/order-by-clause.md)。  
  
 你可以使用`TakeWhile`子句，以指定只有某些元素可返回，具体取决于提供的条件。  
  
## <a name="example"></a>示例  
 下面的代码示例使用`Take`连同子句`Skip`子句，以从页中的某个查询返回数据。 GetCustomers 函数使用`Skip`子句以跳过列表中的客户，直到提供的起始索引值，并使用`Take`子句返回客户从该索引值开始页。  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [查询](../../../visual-basic/language-reference/queries/queries.md)  
 [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Order By 子句](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Take While 子句](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [Skip 子句](../../../visual-basic/language-reference/queries/skip-clause.md)
