---
title: "没有鼠标滚轮"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrMouse_NoWheelIsPresent
ms.assetid: e924ffba-4af1-4247-9a6f-d19a03738f62
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c96f6efed793cfcd4a1a23099e2bba1f01e53437
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="no-mouse-wheel-is-present"></a><span data-ttu-id="14322-102">没有鼠标滚轮</span><span class="sxs-lookup"><span data-stu-id="14322-102">No mouse wheel is present</span></span>
<span data-ttu-id="14322-103">调用了 `My.Computer.Mouse.WheelScrollLines` 属性，但鼠标没有滚轮。</span><span class="sxs-lookup"><span data-stu-id="14322-103">The `My.Computer.Mouse.WheelScrollLines` property was called, but the mouse has no scroll wheel.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="14322-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="14322-104">To correct this error</span></span>  
  
-   <span data-ttu-id="14322-105">检查 `My.Computer.Mouse.WheelExists` 属性，以查看鼠标是否有滚轮，然后再调用 `My.Computer.Mouse.WheelScrollLines` 属性。</span><span class="sxs-lookup"><span data-stu-id="14322-105">Check the `My.Computer.Mouse.WheelExists` property to see if the mouse has a scroll wheel before calling the `My.Computer.Mouse.WheelScrollLines` property.</span></span>  
  
     <span data-ttu-id="14322-106">- 或 -</span><span class="sxs-lookup"><span data-stu-id="14322-106">-or-</span></span>  
  
-   <span data-ttu-id="14322-107">在计算机上安装带滚轮的鼠标。</span><span class="sxs-lookup"><span data-stu-id="14322-107">Install a mouse with a scroll wheel on the computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14322-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="14322-108">See Also</span></span>  
 [<span data-ttu-id="14322-109">My.Computer.Mouse.WheelScrollLines</span><span class="sxs-lookup"><span data-stu-id="14322-109">My.Computer.Mouse.WheelScrollLines</span></span>](xref:Microsoft.VisualBasic.Devices.Mouse.WheelScrollLines)  
 [<span data-ttu-id="14322-110">My.Computer.Mouse.WheelExists</span><span class="sxs-lookup"><span data-stu-id="14322-110">My.Computer.Mouse.WheelExists</span></span>](xref:Microsoft.VisualBasic.Devices.Mouse.WheelExists)  
 [<span data-ttu-id="14322-111">异常和 Visual Basic 中的错误处理</span><span class="sxs-lookup"><span data-stu-id="14322-111">Exception and Error Handling in Visual Basic</span></span>](http://msdn.microsoft.com/en-us/3e351e73-cf23-40ab-8b60-05794160529e)
