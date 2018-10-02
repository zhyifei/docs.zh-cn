---
title: 如何：调用委托方法 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: c50a32d300aaf52efe0c55cef69d5793a98305ac
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44204599"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>如何：调用委托方法 (Visual Basic)
此示例演示如何将一种方法与委托相关联，然后调用该方法通过委托。  
  
### <a name="create-the-delegate-and-matching-procedures"></a>创建委托和匹配过程  
  
1.  创建名为的委托`MySubDelegate`。  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  声明一个类，包含具有相同的签名与委托的方法。  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  定义一个方法，创建委托的实例并调用该方法通过调用内置与委托相关联`Invoke`方法。  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a>请参阅

- [Delegate 语句](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
- [委托](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
- [事件](../../../../visual-basic/programming-guide/language-features/events/index.md)  
- [多线程应用程序](../../../../standard/threading/using-threads-and-threading.md)
