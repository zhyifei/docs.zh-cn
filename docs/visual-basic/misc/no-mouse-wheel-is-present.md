---
title: 没有鼠标滚轮
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoWheelIsPresent
ms.assetid: e924ffba-4af1-4247-9a6f-d19a03738f62
ms.openlocfilehash: 073d086931d70508b176bf00773b030a55c272ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944919"
---
# <a name="no-mouse-wheel-is-present"></a>没有鼠标滚轮
调用了 `My.Computer.Mouse.WheelScrollLines` 属性，但鼠标没有滚轮。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 检查 `My.Computer.Mouse.WheelExists` 属性，以查看鼠标是否有滚轮，然后再调用 `My.Computer.Mouse.WheelScrollLines` 属性。  
  
     或  
  
- 在计算机上安装带滚轮的鼠标。  
  
## <a name="see-also"></a>请参阅

- [My.Computer.Mouse.WheelScrollLines](xref:Microsoft.VisualBasic.Devices.Mouse.WheelScrollLines)
- [My.Computer.Mouse.WheelExists](xref:Microsoft.VisualBasic.Devices.Mouse.WheelExists)
- [在 .NET 中处理和引发异常](../../standard/exceptions/index.md)
