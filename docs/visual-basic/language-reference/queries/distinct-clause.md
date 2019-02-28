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
ms.openlocfilehash: 00a2e52bd6669869bb2e25bc2857f1598da5763f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971229"
---
# <a name="distinct-clause-visual-basic"></a>Distinct 子句 (Visual Basic)
将当前的范围变量，以消除重复值在后续查询子句中的值限制。  
  
## <a name="syntax"></a>语法  
  
```  
Distinct  
```  
  
## <a name="remarks"></a>备注  
 可以使用`Distinct`子句返回唯一项的列表。 `Distinct`子句会使查询以忽略重复的查询结果。 `Distinct`子句应用到重复的值的所有返回指定的字段`Select`子句。 如果没有`Select`指定子句，则`Distinct`子句应用于查询中标识的范围变量`From`子句。 如果范围变量不是不可变类型，查询将只会忽略查询结果，如果该类型的所有成员都匹配现有的查询结果。  
  
## <a name="example"></a>示例  
 下面的查询表达式联接客户列表和客户订单的列表。 `Distinct`子句是包括在内，以返回的唯一客户名称列表，并且订单日期。  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a>请参阅
- [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [查询](../../../visual-basic/language-reference/queries/index.md)
- [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)
- [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)
- [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)
