---
title: 没有鼠标滚轮
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoWheelIsPresent
ms.assetid: e924ffba-4af1-4247-9a6f-d19a03738f62
ms.openlocfilehash: 0273b9838ef77c83818a8af01613a58662f37a93
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610737"
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
