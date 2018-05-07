---
title: Distinct 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 4b0ce12f6361d3dc6e5cc3601e96fc3a9bcf3841
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="distinct-clause-visual-basic"></a>Distinct 子句 (Visual Basic)
限制当前的范围变量，以消除后续查询子句中的重复值的值。  
  
## <a name="syntax"></a>语法  
  
```  
Distinct  
```  
  
## <a name="remarks"></a>备注  
 你可以使用`Distinct`子句返回唯一项的列表。 `Distinct`子句将使查询后，若要忽略重复的查询结果。 `Distinct`子句应用于重复的值中，所有返回指定的字段`Select`子句。 如果没有`Select`指定子句，`Distinct`子句应用于查询中标识的范围变量`From`子句。 如果范围变量不是一个不可变类型，查询将只会忽略查询结果，如果类型的所有成员都匹配现有的查询结果。  
  
## <a name="example"></a>示例  
 下面的查询表达式将联接客户的列表和客户订单的列表。 `Distinct`子句目的是为了返回唯一客户名称的列表和订单日期。  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/distinct-clause_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [查询](../../../visual-basic/language-reference/queries/queries.md)  
 [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)
