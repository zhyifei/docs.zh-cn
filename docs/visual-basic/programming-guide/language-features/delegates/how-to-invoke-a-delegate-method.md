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
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="86606-102">如何：调用委托方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86606-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>
<span data-ttu-id="86606-103">此示例演示如何将一种方法的委托相关联，然后通过调用该方法的委托。</span><span class="sxs-lookup"><span data-stu-id="86606-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="86606-104">创建的委托和匹配的过程</span><span class="sxs-lookup"><span data-stu-id="86606-104">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="86606-105">创建名为的委托`MySubDelegate`。</span><span class="sxs-lookup"><span data-stu-id="86606-105">Create a delegate named `MySubDelegate`.</span></span>  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  <span data-ttu-id="86606-106">声明一个类，包含具有相同的签名与委托的方法。</span><span class="sxs-lookup"><span data-stu-id="86606-106">Declare a class that contains a method with the same signature as the delegate.</span></span>  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  <span data-ttu-id="86606-107">定义一个方法创建委托的一个实例，并通过调用内置关联与委托的方法时，将调用`Invoke`方法。</span><span class="sxs-lookup"><span data-stu-id="86606-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="86606-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="86606-108">See Also</span></span>  
 [<span data-ttu-id="86606-109">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="86606-109">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="86606-110">委托</span><span class="sxs-lookup"><span data-stu-id="86606-110">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="86606-111">事件</span><span class="sxs-lookup"><span data-stu-id="86606-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="86606-112">多线程应用程序</span><span class="sxs-lookup"><span data-stu-id="86606-112">Multithreaded Applications</span></span>](http://msdn.microsoft.com/library/a06a1a56-dd16-44e8-bc01-2c2255511bc6)
