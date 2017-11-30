---
title: "只能根据不带自变量的简单名称或限定名称推断范围变量名称"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords: BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5c986fcf188482c526c53ddf3019cec5163d0b62
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>只能根据不带自变量的简单名称或限定名称推断范围变量名称
采用一个或多个自变量的编程元素包含在 LINQ 查询。 编译器不能推断范围变量从该编程元素。  
  
 **错误 ID:** BC36599  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  提供编程元素中，一个显式变量名称，如下面的代码中所示：  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)
