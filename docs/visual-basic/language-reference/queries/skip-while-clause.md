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
ms.openlocfilehash: 7f37a6fa1c9ba7fdf7978ac6853e4c2985bf72e7
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004707"
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
|`expression`|必需。 表示要为其测试元素的条件的表达式。 表达式必须返回 @no__t 0 值或函数等效项，例如，要将 `Integer` 计算为 `Boolean`。|  
  
## <a name="remarks"></a>备注  
 @No__t-0 子句会绕过查询结果开头的元素，直到提供的 @no__t 返回 `false`。 @No__t 返回 `false` 后，查询将返回所有剩余元素。 对于剩余的结果，将忽略 `expression`。  
  
 @No__t-0 子句与 @no__t 子句不同，因为 `Where` 子句可用于从查询中排除不满足特定条件的所有元素。 @No__t-0 子句仅排除元素，直到第一次未满足条件。 当使用排序的查询结果时，`Skip While` 子句最有用。  
  
 您可以通过使用 `Skip` 子句，绕过查询结果开头的特定数目的结果。  
  
## <a name="example"></a>示例  
 下面的代码示例使用 `Skip While` 子句来绕过美国中的第一个客户。  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [查询](../../../visual-basic/language-reference/queries/index.md)
- [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)
- [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)
- [Skip 子句](../../../visual-basic/language-reference/queries/skip-clause.md)
- [Take While 子句](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)
