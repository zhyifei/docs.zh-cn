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
ms.openlocfilehash: 6484da5329c8240735b7c35f506637dd01cbeda4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604466"
---
# <a name="let-clause-visual-basic"></a>Let 子句 (Visual Basic)
计算一个值，并将其分配给查询中的新变量。  
  
## <a name="syntax"></a>语法  
  
```  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`variable`|必须的。 可以用于引用提供表达式的结果的别名。|  
|`expression`|必须的。 一个表达式，将进行计算并分配到指定的变量。|  
  
## <a name="remarks"></a>备注  
 `Let`子句可用于计算值为每个查询结果，通过使用别名引用它们。 别名可在其他子句，如`Where`子句。 `Let`子句可用于创建可以更轻松地读取，因为可以指定包含在查询表达式子句的别名，还可以用该别名替代每次使用该表达式子句的查询语句。  
  
 可以包含任意数量的`variable`和`expression`中的赋值`Let`子句。 用逗号 （，） 分隔每个分配。  
  
## <a name="example"></a>示例  
 下面的代码示例使用`Let`子句来计算产品 10%的折扣。  
  
 [!code-vb[VbSimpleQuerySamples#16](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/let-clause_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [查询](../../../visual-basic/language-reference/queries/queries.md)  
 [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)
