---
title: "&#39; IsNot &#39;类型 &#39; typename &#39; 操作数仅可以相比 &#39;执行任何操作 &#39;，因为 &#39; typename &#39;为 null 的类型"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords: BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ec0ae1561bfbee998e7c65f6023012c0f982a8a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a>&#39; IsNot &#39;类型 &#39; typename &#39; 操作数仅可以相比 &#39;执行任何操作 &#39;，因为 &#39; typename &#39;为 null 的类型
声明为可以为 null 的变量进行了比较表达式以外`Nothing`使用`IsNot`运算符。  
  
 **错误 ID:** BC32128  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  要比较表达式为 null 的类型以外`Nothing`使用`IsNot`运算符，请调用`GetType`可以为 null 的类型和比较结果与表达式，如下面的示例中所示的方法。  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a>另请参阅  
 [可以为 null 的值类型](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [IsNot 运算符](../../../visual-basic/language-reference/operators/isnot-operator.md)
