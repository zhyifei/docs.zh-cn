---
title: "Skip While 子句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f447a6d9b2eb58fa546ced6c96b987caf68fb3e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="skip-while-clause-visual-basic"></a>Skip While 子句 (Visual Basic)
跳过集合中指定条件为 `true` 的任何元素，然后返回剩余元素。  
  
## <a name="syntax"></a>语法  
  
```  
Skip While expression  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`expression`|必需。 一个表示要测试的元素的条件的表达式。 该表达式必须返回`Boolean`值或等效的功能，如`Integer`作为计算`Boolean`。|  
  
## <a name="remarks"></a>备注  
 `Skip While`子句跳过任何元素，直到所提供的查询结果从头`expression`返回`false`。 后`expression`返回`false`，查询返回所有剩余的元素。 `expression`对于剩余的结果，将忽略。  
  
 `Skip While`子句不同于`Where`中的子句`Where`子句可用来从不满足特定条件的查询中排除的所有元素。 `Skip While`子句仅在未满足的条件的第一个时间排除元素。 `Skip While`子句在你正在使用排序的查询结果时最有用。  
  
 可以通过使用绕过特定数目的结果从开始处的查询结果`Skip`子句。  
  
## <a name="example"></a>示例  
 下面的代码示例使用`Skip While`子句以跳过的结果，直到找到第一个客户从美国。  
  
 [!code-vb[VbSimpleQuerySamples#3](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-while-clause_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [查询](../../../visual-basic/language-reference/queries/queries.md)  
 [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Skip 子句](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [Take While 子句](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)
