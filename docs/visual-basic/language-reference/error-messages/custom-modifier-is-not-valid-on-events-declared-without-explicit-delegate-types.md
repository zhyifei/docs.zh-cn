---
title: '&#39;自定义&#39;修饰符声明而无需显式委托类型的事件上无效'
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 3f08bbbbbac4a01dfbac8d15cf9285c01262618a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>&#39;自定义&#39;修饰符声明而无需显式委托类型的事件上无效
与不同的非自定义事件，`Custom Event`声明要求`As`子句之后显式指定事件的委托类型的事件名称。  
  
 非自定义事件可以是定义使用`As`子句和显式委托类型，或一个参数列表立即在事件名称。  
  
 **错误 ID:** BC31122  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  定义为自定义事件的委托，它具有相同的参数列表。  
  
     例如，如果`Custom Event`定义了`Custom Event Test(ByVal sender As Object, ByVal i As Integer)`，则对应的委托将如下所示。  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  具有自定义事件的参数列表替换`As`子句，用于指定委托类型。  
  
     继续执行本示例中，`Custom Event`声明将被重写，如下所示。  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a>示例  
 此示例声明`Custom Event`，并指定所需`As`用的委托类型的子句。  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a>请参阅  
 [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Delegate 语句](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [事件](../../../visual-basic/programming-guide/language-features/events/index.md)
