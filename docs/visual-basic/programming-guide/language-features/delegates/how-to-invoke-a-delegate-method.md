---
title: 如何：调用委托方法 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: 9fea3ddbc9fb553041671713a64e4b866ee38b50
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43392433"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="2ea2b-102">如何：调用委托方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ea2b-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>
<span data-ttu-id="2ea2b-103">此示例演示如何将一种方法与委托相关联，然后调用该方法通过委托。</span><span class="sxs-lookup"><span data-stu-id="2ea2b-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="2ea2b-104">创建委托和匹配过程</span><span class="sxs-lookup"><span data-stu-id="2ea2b-104">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="2ea2b-105">创建名为的委托`MySubDelegate`。</span><span class="sxs-lookup"><span data-stu-id="2ea2b-105">Create a delegate named `MySubDelegate`.</span></span>  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  <span data-ttu-id="2ea2b-106">声明一个类，包含具有相同的签名与委托的方法。</span><span class="sxs-lookup"><span data-stu-id="2ea2b-106">Declare a class that contains a method with the same signature as the delegate.</span></span>  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  <span data-ttu-id="2ea2b-107">定义一个方法，创建委托的实例并调用该方法通过调用内置与委托相关联`Invoke`方法。</span><span class="sxs-lookup"><span data-stu-id="2ea2b-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2ea2b-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ea2b-108">See Also</span></span>  
 [<span data-ttu-id="2ea2b-109">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="2ea2b-109">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="2ea2b-110">委托</span><span class="sxs-lookup"><span data-stu-id="2ea2b-110">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="2ea2b-111">事件</span><span class="sxs-lookup"><span data-stu-id="2ea2b-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="2ea2b-112">多线程应用程序</span><span class="sxs-lookup"><span data-stu-id="2ea2b-112">Multithreaded Applications</span></span>](https://msdn.microsoft.com/library/a06a1a56-dd16-44e8-bc01-2c2255511bc6)
