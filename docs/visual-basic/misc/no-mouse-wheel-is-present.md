---
title: 没有鼠标滚轮
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoWheelIsPresent
ms.assetid: e924ffba-4af1-4247-9a6f-d19a03738f62
ms.openlocfilehash: 073d086931d70508b176bf00773b030a55c272ed
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "58041357"
---
# <a name="no-mouse-wheel-is-present"></a><span data-ttu-id="4f724-102">没有鼠标滚轮</span><span class="sxs-lookup"><span data-stu-id="4f724-102">No mouse wheel is present</span></span>
<span data-ttu-id="4f724-103">调用了 `My.Computer.Mouse.WheelScrollLines` 属性，但鼠标没有滚轮。</span><span class="sxs-lookup"><span data-stu-id="4f724-103">The `My.Computer.Mouse.WheelScrollLines` property was called, but the mouse has no scroll wheel.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4f724-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="4f724-104">To correct this error</span></span>  
  
-   <span data-ttu-id="4f724-105">检查 `My.Computer.Mouse.WheelExists` 属性，以查看鼠标是否有滚轮，然后再调用 `My.Computer.Mouse.WheelScrollLines` 属性。</span><span class="sxs-lookup"><span data-stu-id="4f724-105">Check the `My.Computer.Mouse.WheelExists` property to see if the mouse has a scroll wheel before calling the `My.Computer.Mouse.WheelScrollLines` property.</span></span>  
  
     <span data-ttu-id="4f724-106">或</span><span class="sxs-lookup"><span data-stu-id="4f724-106">-or-</span></span>  
  
-   <span data-ttu-id="4f724-107">在计算机上安装带滚轮的鼠标。</span><span class="sxs-lookup"><span data-stu-id="4f724-107">Install a mouse with a scroll wheel on the computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f724-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f724-108">See also</span></span>

- [<span data-ttu-id="4f724-109">My.Computer.Mouse.WheelScrollLines</span><span class="sxs-lookup"><span data-stu-id="4f724-109">My.Computer.Mouse.WheelScrollLines</span></span>](xref:Microsoft.VisualBasic.Devices.Mouse.WheelScrollLines)
- [<span data-ttu-id="4f724-110">My.Computer.Mouse.WheelExists</span><span class="sxs-lookup"><span data-stu-id="4f724-110">My.Computer.Mouse.WheelExists</span></span>](xref:Microsoft.VisualBasic.Devices.Mouse.WheelExists)
- [<span data-ttu-id="4f724-111">在 .NET 中处理和引发异常</span><span class="sxs-lookup"><span data-stu-id="4f724-111">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
