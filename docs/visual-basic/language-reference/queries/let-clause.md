---
title: Let 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 88166a040823cfefe623f672e556c364d652a7fc
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004725"
---
# <a name="let-clause-visual-basic"></a>Let 子句 (Visual Basic)
计算值并将其分配给查询中的新变量。  
  
## <a name="syntax"></a>语法  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`variable`|必需。 可用于引用所提供表达式的结果的别名。|  
|`expression`|必需。 将进行计算并分配给指定变量的表达式。|  
  
## <a name="remarks"></a>备注  
 使用 `Let` 子句可以计算每个查询结果的值，并使用别名引用这些值。 别名可用于其他子句，如 `Where` 子句。 @No__t-0 子句使你能够创建更易于阅读的查询语句，因为你可以为查询中包括的 expression 子句指定一个别名，并在每次使用 expression 子句时替换该别名。  
  
 可在 `Let` 子句中包含任意数量的 @no__t 0 和 @no__t。 使用逗号（，）分隔每个赋值。  
  
## <a name="example"></a>示例  
 下面的代码示例使用 `Let` 子句来计算产品 10% 的折扣。  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [查询](../../../visual-basic/language-reference/queries/index.md)
- [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)
- [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)
- [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)
