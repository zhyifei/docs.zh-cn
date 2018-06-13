---
title: 委托类&#39; &lt;classname&gt; &#39;有没有 Invoke 方法，因此此类型的表达式不能为方法调用的目标
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: cc1abba46224772e733780800dd104dfc7ebe9ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588825"
---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>委托类&#39; &lt;classname&gt; &#39;有没有 Invoke 方法，因此此类型的表达式不能为方法调用的目标
调用`Invoke`通过委托已失败，因为`Invoke`上委托类未实现。  
  
 **错误 ID:** BC30220  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  确保委托类的实例，已创建具有`Dim`语句和是否委托实例分配了一个过程`AddressOf`运算符。  
  
2.  找到实现委托类的代码，并确保它实现`Invoke`过程。  
  
## <a name="see-also"></a>请参阅  
 [委托](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Delegate 语句](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [AddressOf 运算符](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)
