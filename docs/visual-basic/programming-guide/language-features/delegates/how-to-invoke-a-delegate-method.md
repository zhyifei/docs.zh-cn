---
title: 如何：调用委托方法 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: aca87dd9fa1990d44c99aab7753f2fd7d508adc1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646947"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>如何：调用委托方法 (Visual Basic)
此示例演示如何将一种方法的委托相关联，然后通过调用该方法的委托。  
  
### <a name="create-the-delegate-and-matching-procedures"></a>创建的委托和匹配的过程  
  
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
  
3.  定义一个方法创建委托的一个实例，并通过调用内置关联与委托的方法时，将调用`Invoke`方法。  
  
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
 [Delegate 语句](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [委托](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [事件](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [多线程应用程序](http://msdn.microsoft.com/library/a06a1a56-dd16-44e8-bc01-2c2255511bc6)
