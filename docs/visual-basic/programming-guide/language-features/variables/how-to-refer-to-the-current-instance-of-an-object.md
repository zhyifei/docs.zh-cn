---
title: 如何：引用对象的当前实例（Visual Basic）
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 6c216dbc59bcad7a9f24bb01f856c3d29c288dbb
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005665"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="a5a4c-102">如何：引用对象的当前实例（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="a5a4c-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="a5a4c-103">对象的*当前实例*是当前在其中执行代码的实例。</span><span class="sxs-lookup"><span data-stu-id="a5a4c-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="a5a4c-104">使用 @no__t 的关键字来引用当前的实例。</span><span class="sxs-lookup"><span data-stu-id="a5a4c-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="a5a4c-105">引用当前实例</span><span class="sxs-lookup"><span data-stu-id="a5a4c-105">To refer to the current instance</span></span>  
  
- <span data-ttu-id="a5a4c-106">使用 @no__t 关键字，通常使用对象变量的名称。</span><span class="sxs-lookup"><span data-stu-id="a5a4c-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="a5a4c-107">尽管 @no__t 的行为与对象变量类似，但不能对其进行声明或向其分配任何内容。</span><span class="sxs-lookup"><span data-stu-id="a5a4c-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="a5a4c-108">`Me` 始终引用当前实例。</span><span class="sxs-lookup"><span data-stu-id="a5a4c-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5a4c-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5a4c-109">See also</span></span>

- [<span data-ttu-id="a5a4c-110">对象变量</span><span class="sxs-lookup"><span data-stu-id="a5a4c-110">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="a5a4c-111">对象变量赋值</span><span class="sxs-lookup"><span data-stu-id="a5a4c-111">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="a5a4c-112">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="a5a4c-112">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
