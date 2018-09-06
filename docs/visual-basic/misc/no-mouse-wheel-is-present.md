---
title: 没有鼠标滚轮
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoWheelIsPresent
ms.assetid: e924ffba-4af1-4247-9a6f-d19a03738f62
ms.openlocfilehash: bfb8ea0d5d7a22bd66f477216129ff834023f4ba
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43738193"
---
# <a name="no-mouse-wheel-is-present"></a><span data-ttu-id="89d9f-102">没有鼠标滚轮</span><span class="sxs-lookup"><span data-stu-id="89d9f-102">No mouse wheel is present</span></span>
<span data-ttu-id="89d9f-103">调用了 `My.Computer.Mouse.WheelScrollLines` 属性，但鼠标没有滚轮。</span><span class="sxs-lookup"><span data-stu-id="89d9f-103">The `My.Computer.Mouse.WheelScrollLines` property was called, but the mouse has no scroll wheel.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="89d9f-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="89d9f-104">To correct this error</span></span>  
  
-   <span data-ttu-id="89d9f-105">检查 `My.Computer.Mouse.WheelExists` 属性，以查看鼠标是否有滚轮，然后再调用 `My.Computer.Mouse.WheelScrollLines` 属性。</span><span class="sxs-lookup"><span data-stu-id="89d9f-105">Check the `My.Computer.Mouse.WheelExists` property to see if the mouse has a scroll wheel before calling the `My.Computer.Mouse.WheelScrollLines` property.</span></span>  
  
     <span data-ttu-id="89d9f-106">或</span><span class="sxs-lookup"><span data-stu-id="89d9f-106">-or-</span></span>  
  
-   <span data-ttu-id="89d9f-107">在计算机上安装带滚轮的鼠标。</span><span class="sxs-lookup"><span data-stu-id="89d9f-107">Install a mouse with a scroll wheel on the computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89d9f-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="89d9f-108">See Also</span></span>  
 [<span data-ttu-id="89d9f-109">My.Computer.Mouse.WheelScrollLines</span><span class="sxs-lookup"><span data-stu-id="89d9f-109">My.Computer.Mouse.WheelScrollLines</span></span>](xref:Microsoft.VisualBasic.Devices.Mouse.WheelScrollLines)  
 [<span data-ttu-id="89d9f-110">My.Computer.Mouse.WheelExists</span><span class="sxs-lookup"><span data-stu-id="89d9f-110">My.Computer.Mouse.WheelExists</span></span>](xref:Microsoft.VisualBasic.Devices.Mouse.WheelExists)  
 [<span data-ttu-id="89d9f-111">异常和 Visual Basic 中的错误处理</span><span class="sxs-lookup"><span data-stu-id="89d9f-111">Exception and Error Handling in Visual Basic</span></span>](https://msdn.microsoft.com/library/3e351e73-cf23-40ab-8b60-05794160529e)
