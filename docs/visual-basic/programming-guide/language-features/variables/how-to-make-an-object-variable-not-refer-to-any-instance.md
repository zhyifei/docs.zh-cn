---
title: 如何：使对象变量不引用任何实例 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: bf918b762261e1dd1fc4161a10203f3d0067e454
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>如何：使对象变量不引用任何实例 (Visual Basic)
你可以通过将它设置为解除关联，从任何对象实例的对象变量[执行任何操作](../../../../visual-basic/language-reference/nothing.md)。  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>若要解除关联从任何对象实例的对象变量  
  
-   将变量设置为`Nothing`在赋值语句中。  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>可靠编程  
 如果你的代码尝试访问已被设置为对象变量的成员`Nothing`、<xref:System.NullReferenceException>时发生。 如果对象变量设置为`Nothing`频繁，或者如果可能未初始化变量，则最好将中的成员访问包含`Try...Catch...Finally`块。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 如果你用于包含机密或敏感数据的对象使用的对象变量，可以将变量设置为`Nothing`时你不主动处理的那些对象之一。 这可以减少访问数据的恶意代码的机会。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.NullReferenceException>  
 [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [对象变量赋值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Nothing](../../../../visual-basic/language-reference/nothing.md)  
 [Try...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [异常疑难解答：System.NullReferenceException](http://msdn.microsoft.com/library/4822b0b4-8105-43fb-887a-3cc51ff02899)
