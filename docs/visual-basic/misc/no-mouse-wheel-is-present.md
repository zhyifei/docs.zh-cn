---
title: 没有鼠标滚轮
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoWheelIsPresent
ms.assetid: e924ffba-4af1-4247-9a6f-d19a03738f62
ms.openlocfilehash: bfb8ea0d5d7a22bd66f477216129ff834023f4ba
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43463666"
---
# <a name="no-mouse-wheel-is-present"></a>没有鼠标滚轮
调用了 `My.Computer.Mouse.WheelScrollLines` 属性，但鼠标没有滚轮。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   检查 `My.Computer.Mouse.WheelExists` 属性，以查看鼠标是否有滚轮，然后再调用 `My.Computer.Mouse.WheelScrollLines` 属性。  
  
     或  
  
-   在计算机上安装带滚轮的鼠标。  
  
## <a name="see-also"></a>请参阅  
 [My.Computer.Mouse.WheelScrollLines](xref:Microsoft.VisualBasic.Devices.Mouse.WheelScrollLines)  
 [My.Computer.Mouse.WheelExists](xref:Microsoft.VisualBasic.Devices.Mouse.WheelExists)  
 [异常和 Visual Basic 中的错误处理](https://msdn.microsoft.com/library/3e351e73-cf23-40ab-8b60-05794160529e)
