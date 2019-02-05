---
title: 如何：使对象变量不引用任何实例 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: ceee1b47fb66cfb8e24b6871af3be6475031504f
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2019
ms.locfileid: "55738872"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>如何：使对象变量不引用任何实例 (Visual Basic)
您可以通过将其设置为解除关联，从任何对象实例的对象变量[Nothing](../../../../visual-basic/language-reference/nothing.md)。  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>若要解除关联从任何对象实例的对象变量  
  
-   将变量设置为`Nothing`在赋值语句中。  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>可靠编程  
 如果你的代码尝试访问已被设置为对象变量的成员`Nothing`、<xref:System.NullReferenceException>时发生。 如果对象变量设置为`Nothing`频繁，或者它是否可以将变量未初始化，它是一个好办法将中的成员访问`Try...Catch...Finally`块。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 如果使用包含机密或敏感数据的对象的对象变量，可以将变量设置为`Nothing`当您在不主动处理这些对象之一。 这将减少恶意代码获得对数据的访问的可能性。  
  
## <a name="see-also"></a>请参阅
- <xref:System.NullReferenceException>
- [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [对象变量赋值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Try...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
