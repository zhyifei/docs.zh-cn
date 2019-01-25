---
title: 没有鼠标滚轮
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoWheelIsPresent
ms.assetid: e924ffba-4af1-4247-9a6f-d19a03738f62
ms.openlocfilehash: 61c8f3aa48bb5dd8b02ee8f6327fbde1f55bfe1a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595300"
---
# <a name="no-mouse-wheel-is-present"></a><span data-ttu-id="dd177-102">没有鼠标滚轮</span><span class="sxs-lookup"><span data-stu-id="dd177-102">No mouse wheel is present</span></span>
<span data-ttu-id="dd177-103">调用了 `My.Computer.Mouse.WheelScrollLines` 属性，但鼠标没有滚轮。</span><span class="sxs-lookup"><span data-stu-id="dd177-103">The `My.Computer.Mouse.WheelScrollLines` property was called, but the mouse has no scroll wheel.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dd177-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="dd177-104">To correct this error</span></span>  
  
-   <span data-ttu-id="dd177-105">检查 `My.Computer.Mouse.WheelExists` 属性，以查看鼠标是否有滚轮，然后再调用 `My.Computer.Mouse.WheelScrollLines` 属性。</span><span class="sxs-lookup"><span data-stu-id="dd177-105">Check the `My.Computer.Mouse.WheelExists` property to see if the mouse has a scroll wheel before calling the `My.Computer.Mouse.WheelScrollLines` property.</span></span>  
  
     <span data-ttu-id="dd177-106">或</span><span class="sxs-lookup"><span data-stu-id="dd177-106">-or-</span></span>  
  
-   <span data-ttu-id="dd177-107">在计算机上安装带滚轮的鼠标。</span><span class="sxs-lookup"><span data-stu-id="dd177-107">Install a mouse with a scroll wheel on the computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd177-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd177-108">See also</span></span>
- [<span data-ttu-id="dd177-109">My.Computer.Mouse.WheelScrollLines</span><span class="sxs-lookup"><span data-stu-id="dd177-109">My.Computer.Mouse.WheelScrollLines</span></span>](xref:Microsoft.VisualBasic.Devices.Mouse.WheelScrollLines)
- [<span data-ttu-id="dd177-110">My.Computer.Mouse.WheelExists</span><span class="sxs-lookup"><span data-stu-id="dd177-110">My.Computer.Mouse.WheelExists</span></span>](xref:Microsoft.VisualBasic.Devices.Mouse.WheelExists)
- [<span data-ttu-id="dd177-111">Visual Basic 中的异常与错误处理</span><span class="sxs-lookup"><span data-stu-id="dd177-111">Exception and Error Handling in Visual Basic</span></span>](https://msdn.microsoft.com/library/3e351e73-cf23-40ab-8b60-05794160529e)
