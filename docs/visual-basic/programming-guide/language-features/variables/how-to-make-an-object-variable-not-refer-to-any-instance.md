---
title: 如何：使对象变量不引用任何实例
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 320dadb61c12f3339c5328dcef31c41503892c56
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352886"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>如何：使对象变量不引用任何实例 (Visual Basic)
您可以通过将对象变量设置为 "[无](../../../../visual-basic/language-reference/nothing.md)" 来解除对象变量与任何对象实例的关联。  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>断开对象变量与任何对象实例的关联  
  
- 在赋值语句中，将变量设置为 `Nothing`。  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>可靠的编程  
 如果你的代码尝试访问已设置为 `Nothing`的对象变量的成员，则会发生 <xref:System.NullReferenceException>。 如果将某个对象变量设置为经常 `Nothing`，或者变量未初始化，则最好将成员访问包含在 `Try...Catch...Finally` 块中。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 如果对包含机密数据或敏感数据的对象使用对象变量，则在不主动处理这些对象之一时，可以将变量设置为 `Nothing`。 这减少了恶意代码访问数据的可能性。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.NullReferenceException>
- [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [对象变量赋值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Try...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
