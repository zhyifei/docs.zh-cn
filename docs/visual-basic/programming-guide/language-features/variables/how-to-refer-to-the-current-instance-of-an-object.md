---
title: 如何：引用的对象 (Visual Basic 中) 的当前实例
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: d166ce62a2bb0522d1ca7011aeff7afe076c2d8e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542192"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="4248f-102">如何：引用的对象 (Visual Basic 中) 的当前实例</span><span class="sxs-lookup"><span data-stu-id="4248f-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="4248f-103">*当前实例*的对象是当前正在其中执行代码的实例。</span><span class="sxs-lookup"><span data-stu-id="4248f-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="4248f-104">您使用`Me`关键字来引用当前实例。</span><span class="sxs-lookup"><span data-stu-id="4248f-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="4248f-105">若要引用的当前实例</span><span class="sxs-lookup"><span data-stu-id="4248f-105">To refer to the current instance</span></span>  
  
-   <span data-ttu-id="4248f-106">使用`Me`关键字，通常会使用对象变量的名称。</span><span class="sxs-lookup"><span data-stu-id="4248f-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="4248f-107">尽管`Me`的行为类似于对象变量时，不能将其声明或向其分配的任何内容。</span><span class="sxs-lookup"><span data-stu-id="4248f-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="4248f-108">`Me` 始终引用当前实例。</span><span class="sxs-lookup"><span data-stu-id="4248f-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4248f-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="4248f-109">See also</span></span>
- [<span data-ttu-id="4248f-110">对象变量</span><span class="sxs-lookup"><span data-stu-id="4248f-110">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="4248f-111">对象变量赋值</span><span class="sxs-lookup"><span data-stu-id="4248f-111">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="4248f-112">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="4248f-112">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
