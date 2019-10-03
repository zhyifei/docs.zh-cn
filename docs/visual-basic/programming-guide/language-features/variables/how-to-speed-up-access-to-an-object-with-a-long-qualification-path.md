---
title: 如何：加速访问具有长限定路径的对象 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: a8e50a2ed04037b48091321dc0c9ac2ea1db35f4
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631094"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="792d7-102">如何：加速访问具有长限定路径的对象 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="792d7-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>

<span data-ttu-id="792d7-103">如果经常访问的对象需要多个方法和属性的限定路径, 则可以通过不重复限定路径来加快代码的速度。</span><span class="sxs-lookup"><span data-stu-id="792d7-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>

<span data-ttu-id="792d7-104">可以通过两种方法来避免重复限定路径。</span><span class="sxs-lookup"><span data-stu-id="792d7-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="792d7-105">可以将对象分配给一个变量, 也可以将其`With`用于 ...`End With`块。</span><span class="sxs-lookup"><span data-stu-id="792d7-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="792d7-106">通过将严重限定对象赋给变量来加快对该对象的访问速度</span><span class="sxs-lookup"><span data-stu-id="792d7-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>

1. <span data-ttu-id="792d7-107">声明经常访问的对象类型的变量。</span><span class="sxs-lookup"><span data-stu-id="792d7-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="792d7-108">指定声明的初始化部分中的限定路径。</span><span class="sxs-lookup"><span data-stu-id="792d7-108">Specify the qualification path in the initialization part of the declaration.</span></span>

    ```vb
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl
    ```

2. <span data-ttu-id="792d7-109">使用变量访问对象的成员。</span><span class="sxs-lookup"><span data-stu-id="792d7-109">Use the variable to access the object's members.</span></span>

    ```vb
    ctrlActv.Text = "Test"
    ctrlActv.Location = New Point(100, 100)
    ctrlActv.Show()
    ```

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="792d7-110">若要通过使用 With, 加速对严重限定对象的访问结尾为块</span><span class="sxs-lookup"><span data-stu-id="792d7-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>

1. <span data-ttu-id="792d7-111">将限定路径放在`With`语句中。</span><span class="sxs-lookup"><span data-stu-id="792d7-111">Put the qualification path in a `With` statement.</span></span>

    ```vb
    With someForm.ActiveForm.ActiveControl
    ```

2. <span data-ttu-id="792d7-112">在`With` 语句`End With`前面的块内访问对象的成员。</span><span class="sxs-lookup"><span data-stu-id="792d7-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>

    ```vb
        .Text = "Test"
        .Location = New Point(100, 100)
        .Show()
    End With
    ```

## <a name="see-also"></a><span data-ttu-id="792d7-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="792d7-113">See also</span></span>

- [<span data-ttu-id="792d7-114">对象变量</span><span class="sxs-lookup"><span data-stu-id="792d7-114">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="792d7-115">With...End With 语句</span><span class="sxs-lookup"><span data-stu-id="792d7-115">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
