---
title: 该上下文中不支持可以为 null 的类型推理
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e7a5450d812260d3916296dff56abee27b3d586c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a>该上下文中不支持可以为 null 的类型推理
可以将值类型和结构声明可以为 null。  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 但是，不能与类型推理结合使用可以为 null 的声明。 下面的示例会导致此错误。  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **错误 ID:** BC36629  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   使用`As`子句来声明作为可以为 null 的变量。  
  
## <a name="see-also"></a>另请参阅  
 [可以为 null 的值类型](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
