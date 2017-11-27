---
title: "如何：加速访问具有长限定路径的对象 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5d91eeaeb034a4c8b4fefcffdf2fdebe72127d66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="07b4c-102">如何：加速访问具有长限定路径的对象 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07b4c-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>
<span data-ttu-id="07b4c-103">如果你经常访问的对象需要多个方法和属性的限定路径，可以通过不重复限定路径来加快你的代码。</span><span class="sxs-lookup"><span data-stu-id="07b4c-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>  
  
 <span data-ttu-id="07b4c-104">有两种方法可以避免重复限定路径。</span><span class="sxs-lookup"><span data-stu-id="07b4c-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="07b4c-105">你可以将对象分配给一个变量，或者可以使用它在`With`...`End With`块。</span><span class="sxs-lookup"><span data-stu-id="07b4c-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="07b4c-106">为了加快访问对很大程度限定对象为其分配给一个变量</span><span class="sxs-lookup"><span data-stu-id="07b4c-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>  
  
1.  <span data-ttu-id="07b4c-107">声明要经常访问的对象类型的变量。</span><span class="sxs-lookup"><span data-stu-id="07b4c-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="07b4c-108">在声明的初始化部分中指定限定路径。</span><span class="sxs-lookup"><span data-stu-id="07b4c-108">Specify the qualification path in the initialization part of the declaration.</span></span>  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="07b4c-109">使用变量来访问该对象的成员。</span><span class="sxs-lookup"><span data-stu-id="07b4c-109">Use the variable to access the object's members.</span></span>  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="07b4c-110">为了加快访问对很大程度限定对象通过使用 With...End With 块</span><span class="sxs-lookup"><span data-stu-id="07b4c-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>  
  
1.  <span data-ttu-id="07b4c-111">置于限定路径`With`语句。</span><span class="sxs-lookup"><span data-stu-id="07b4c-111">Put the qualification path in a `With` statement.</span></span>  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="07b4c-112">访问内的对象的成员`With`阻止，之前`End With`语句。</span><span class="sxs-lookup"><span data-stu-id="07b4c-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="07b4c-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07b4c-113">See Also</span></span>  
 [<span data-ttu-id="07b4c-114">对象变量</span><span class="sxs-lookup"><span data-stu-id="07b4c-114">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="07b4c-115">With...End With 语句</span><span class="sxs-lookup"><span data-stu-id="07b4c-115">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
