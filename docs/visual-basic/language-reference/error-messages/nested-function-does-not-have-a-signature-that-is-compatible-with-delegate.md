---
title: 嵌套的函数没有与委托 &#39; 兼容的签名&lt;delegatename&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 60cf15343023110561da3e3fcf202bd00394127a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-39ltdelegatenamegt39"></a>嵌套的函数没有与委托 &#39; 兼容的签名&lt;delegatename&gt;&#39;
Lambda 表达式具有已分配给委托具有不兼容的签名。 例如，在下面的代码中，委托`Del`具有两个整数参数。  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 如果一个自变量的 lambda 表达式声明为类型引发该错误`Del`:  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 **错误 ID:** BC36532  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   调整的委派定义或已分配的 lambda 表达式，以便签名是兼容。  
  
## <a name="see-also"></a>另请参阅  
 [宽松委托转换](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
