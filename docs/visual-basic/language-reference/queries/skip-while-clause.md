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
  
|术语|Definition|  
|---|---|  
|`expression`|必需。 表示要为其测试元素的条件的表达式。 表达式必须返回 `Boolean` 值或函数等效项，例如要作为 `Boolean`计算的 `Integer`。|  
  
## <a name="remarks"></a>备注  
 在提供的 `expression` 返回 `false`之前，`Skip While` 子句将跳过查询结果开头的元素。 `expression` 返回 `false`后，查询将返回所有剩余元素。 对于剩余的结果，将忽略 `expression`。  
  
 `Skip While` 子句与 `Where` 子句不同，因为 `Where` 子句可用于从查询中排除不满足特定条件的所有元素。 `Skip While` 子句仅排除元素，直到第一次未满足条件。 当使用排序的查询结果时，`Skip While` 子句最有用。  
  
 您可以通过使用 `Skip` 子句，绕过查询结果开头的特定数目的结果。  
  
## <a name="example"></a>示例  
 下面的代码示例使用 `Skip While` 子句来跳过结果，直到找到美国中的第一个客户。  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a>另请参阅

- [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [查询](../../../visual-basic/language-reference/queries/index.md)
- [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)
- [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)
- [Skip 子句](../../../visual-basic/language-reference/queries/skip-clause.md)
- [Take While 子句](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)
