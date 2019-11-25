---
title: 如何：调用委托方法
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: 520bacfbe6103490e0459cd5af149c1d55a8fce4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345256"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="1f627-102">如何：调用委托方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f627-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>

<span data-ttu-id="1f627-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span><span class="sxs-lookup"><span data-stu-id="1f627-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>

### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="1f627-104">Create the delegate and matching procedures</span><span class="sxs-lookup"><span data-stu-id="1f627-104">Create the delegate and matching procedures</span></span>

1. <span data-ttu-id="1f627-105">Create a delegate named `MySubDelegate`.</span><span class="sxs-lookup"><span data-stu-id="1f627-105">Create a delegate named `MySubDelegate`.</span></span>

    ```vb
    Delegate Sub MySubDelegate(ByVal x As Integer)
    ```

2. <span data-ttu-id="1f627-106">Declare a class that contains a method with the same signature as the delegate.</span><span class="sxs-lookup"><span data-stu-id="1f627-106">Declare a class that contains a method with the same signature as the delegate.</span></span>

    ```vb
    Class class1
        Sub Sub1(ByVal x As Integer)
            MsgBox("The value of x is: " & CStr(x))
        End Sub
    End Class
    ```

3. <span data-ttu-id="1f627-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span><span class="sxs-lookup"><span data-stu-id="1f627-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>

    ```vb
    Protected Sub DelegateTest()
        Dim c1 As New class1
        ' Create an instance of the delegate.
        Dim msd As MySubDelegate = AddressOf c1.Sub1
        ' Call the method.
        msd.Invoke(10)
    End Sub
    ```

## <a name="see-also"></a><span data-ttu-id="1f627-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f627-108">See also</span></span>

- [<span data-ttu-id="1f627-109">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="1f627-109">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="1f627-110">委托</span><span class="sxs-lookup"><span data-stu-id="1f627-110">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="1f627-111">事件</span><span class="sxs-lookup"><span data-stu-id="1f627-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="1f627-112">多线程应用程序</span><span class="sxs-lookup"><span data-stu-id="1f627-112">Multithreaded Applications</span></span>](../../../../standard/threading/using-threads-and-threading.md)
