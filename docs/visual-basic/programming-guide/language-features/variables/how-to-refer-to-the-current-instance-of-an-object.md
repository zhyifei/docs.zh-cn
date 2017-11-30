---
title: "如何：引用对象的当前实例 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 33ea612253b00e12f47258189da4ac7d8d98ade5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="1da47-102">如何：引用对象的当前实例 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1da47-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="1da47-103">*当前实例*对象是当前在其中执行代码的实例。</span><span class="sxs-lookup"><span data-stu-id="1da47-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="1da47-104">你使用`Me`关键字来引用当前实例。</span><span class="sxs-lookup"><span data-stu-id="1da47-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="1da47-105">若要引用的当前实例</span><span class="sxs-lookup"><span data-stu-id="1da47-105">To refer to the current instance</span></span>  
  
-   <span data-ttu-id="1da47-106">使用`Me`通常应使用对象变量的名称的关键字。</span><span class="sxs-lookup"><span data-stu-id="1da47-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="1da47-107">尽管`Me`行为类似对象变量，你不能将其声明或向它分配任何内容。</span><span class="sxs-lookup"><span data-stu-id="1da47-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="1da47-108">`Me`始终引用当前实例。</span><span class="sxs-lookup"><span data-stu-id="1da47-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1da47-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1da47-109">See Also</span></span>  
 [<span data-ttu-id="1da47-110">对象变量</span><span class="sxs-lookup"><span data-stu-id="1da47-110">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="1da47-111">对象变量赋值</span><span class="sxs-lookup"><span data-stu-id="1da47-111">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="1da47-112">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="1da47-112">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
