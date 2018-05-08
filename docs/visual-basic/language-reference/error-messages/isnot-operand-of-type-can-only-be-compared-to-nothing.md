---
title: '&#39;IsNot&#39;类型的操作数&#39;typename&#39;仅可以相比&#39;执行任何操作&#39;，这是因为&#39;typename&#39;为 null 的类型'
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 44cc17c73b476e5e322b9b58b021bc7bcd63167f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a>&#39;IsNot&#39;类型的操作数&#39;typename&#39;仅可以相比&#39;执行任何操作&#39;，这是因为&#39;typename&#39;为 null 的类型
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
  
## <a name="see-also"></a>请参阅  
 [可以为 null 的值类型](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [IsNot 运算符](../../../visual-basic/language-reference/operators/isnot-operator.md)
