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
ms.openlocfilehash: d52d13feb0f85065c0623b5937f558b841c036dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650194"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="76ace-102">如何：加速访问具有长限定路径的对象 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="76ace-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>
<span data-ttu-id="76ace-103">如果你经常访问的对象需要多个方法和属性的限定路径，可以通过不重复限定路径来加快你的代码。</span><span class="sxs-lookup"><span data-stu-id="76ace-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>  
  
 <span data-ttu-id="76ace-104">有两种方法可以避免重复限定路径。</span><span class="sxs-lookup"><span data-stu-id="76ace-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="76ace-105">你可以将对象分配给一个变量，或者可以使用它在`With`...`End With`块。</span><span class="sxs-lookup"><span data-stu-id="76ace-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="76ace-106">为了加快访问对很大程度限定对象为其分配给一个变量</span><span class="sxs-lookup"><span data-stu-id="76ace-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>  
  
1.  <span data-ttu-id="76ace-107">声明要经常访问的对象类型的变量。</span><span class="sxs-lookup"><span data-stu-id="76ace-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="76ace-108">在声明的初始化部分中指定限定路径。</span><span class="sxs-lookup"><span data-stu-id="76ace-108">Specify the qualification path in the initialization part of the declaration.</span></span>  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="76ace-109">使用变量来访问该对象的成员。</span><span class="sxs-lookup"><span data-stu-id="76ace-109">Use the variable to access the object's members.</span></span>  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="76ace-110">为了加快访问对很大程度限定对象通过使用 With...End With 块</span><span class="sxs-lookup"><span data-stu-id="76ace-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>  
  
1.  <span data-ttu-id="76ace-111">置于限定路径`With`语句。</span><span class="sxs-lookup"><span data-stu-id="76ace-111">Put the qualification path in a `With` statement.</span></span>  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="76ace-112">访问内的对象的成员`With`阻止，之前`End With`语句。</span><span class="sxs-lookup"><span data-stu-id="76ace-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="76ace-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="76ace-113">See Also</span></span>  
 [<span data-ttu-id="76ace-114">对象变量</span><span class="sxs-lookup"><span data-stu-id="76ace-114">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="76ace-115">With...End With 语句</span><span class="sxs-lookup"><span data-stu-id="76ace-115">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
