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
ms.openlocfilehash: e8d3e38261a04c4d29faab351d24d6710413b09a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004791"
---
# <a name="distinct-clause-visual-basic"></a>Distinct 子句 (Visual Basic)
限制当前范围变量的值，以消除后面的查询子句中的重复值。  
  
## <a name="syntax"></a>语法  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a>备注  
 您可以使用 `Distinct` 子句返回唯一项的列表。 @No__t-0 子句使查询忽略重复的查询结果。 @No__t-0 子句适用于 @no__t 子句指定的所有返回字段的重复值。 如果未指定 `Select` 子句，则 @no__t 子句将应用到 `From` 子句中标识的查询的范围变量。 如果范围变量不是不可变类型，则当该类型的所有成员均与现有查询结果匹配时，该查询将忽略查询结果。  
  
## <a name="example"></a>示例  
 下面的查询表达式将联接列表和客户订单列表。 包含 `Distinct` 子句以返回唯一客户名称和订单日期的列表。  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [查询](../../../visual-basic/language-reference/queries/index.md)
- [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)
- [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)
- [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)
