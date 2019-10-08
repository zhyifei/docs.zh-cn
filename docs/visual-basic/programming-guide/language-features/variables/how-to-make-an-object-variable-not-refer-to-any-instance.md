---
title: 如何：使对象变量不引用任何实例（Visual Basic）
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: e647f2f891b06aa1767faac49b01df98ea31ec1c
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004913"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>如何：使对象变量不引用任何实例（Visual Basic）
您可以通过将对象变量设置为 "[无](../../../../visual-basic/language-reference/nothing.md)" 来解除对象变量与任何对象实例的关联。  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>断开对象变量与任何对象实例的关联  
  
- 在赋值语句中，将变量设置为 `Nothing`。  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>可靠编程  
 如果你的代码尝试访问已设置为 `Nothing` 的对象变量的成员，则会发生 @no__t。 如果将一个对象变量设置为经常 @no__t 0，或者如果可能该变量未初始化，则最好将成员访问包含在 @no__t 1 块中。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 如果对包含机密数据或敏感数据的对象使用对象变量，则在不主动处理其中一个对象时，可以将变量设置为 `Nothing`。 这减少了恶意代码访问数据的可能性。  
  
## <a name="see-also"></a>请参阅

- <xref:System.NullReferenceException>
- [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [对象变量赋值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Try...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
