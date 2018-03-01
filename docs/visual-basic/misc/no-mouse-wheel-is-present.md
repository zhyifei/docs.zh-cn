---
title: "没有鼠标滚轮"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrMouse_NoWheelIsPresent
ms.assetid: e924ffba-4af1-4247-9a6f-d19a03738f62
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7caf2e24bcbd86ad2b6175d593bd218a9bb4689d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
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
 [异常和 Visual Basic 中的错误处理](http://msdn.microsoft.com/library/3e351e73-cf23-40ab-8b60-05794160529e)
