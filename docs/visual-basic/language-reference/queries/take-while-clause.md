---
title: Take While 子句
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 23b7c84a9f896161a66059fcb1f30753d3b863d5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347101"
---
# <a name="take-while-clause-visual-basic"></a>Take While 子句 (Visual Basic)
包括集合中指定条件为 `true` 的任何元素，并绕过剩余元素。  
  
## <a name="syntax"></a>语法  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a>部件  
  
|术语|Definition|  
|---|---|  
|`expression`|必需。 表示要为其测试元素的条件的表达式。 表达式必须返回 `Boolean` 值或函数等效项，例如要作为 `Boolean`计算的 `Integer`。|  
  
## <a name="remarks"></a>备注  
 在提供的 `expression` 返回 `false`之前，`Take While` 子句包括从查询结果开始的元素。 `expression` 返回 `false`后，查询将跳过所有剩余的元素。 对于剩余的结果，将忽略 `expression`。  
  
 `Take While` 子句与 `Where` 子句不同，因为 `Where` 子句可用于包括查询中满足特定条件的所有元素。 仅在第一次未满足条件之前，`Take While` 子句包括元素。 当使用排序的查询结果时，`Take While` 子句最有用。  
  
## <a name="example"></a>示例  
 下面的代码示例使用 `Take While` 子句来检索结果，直到找到第一个不含任何订单的客户。  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a>另请参阅

- [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [查询](../../../visual-basic/language-reference/queries/index.md)
- [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)
- [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)
- [Take 子句](../../../visual-basic/language-reference/queries/take-clause.md)
- [Skip While 子句](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)
