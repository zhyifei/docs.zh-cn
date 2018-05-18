---
title: 如何：启动应用程序并向其发送击键 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
ms.openlocfilehash: 716c88153ad01c7b225f31948c8aaaa2694dc512
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a>如何：启动应用程序并向其发送击键 (Visual Basic)
此示例使用 `Shell` 函数启动计算器应用程序，然后使用 `My.Computer.Keyboard.SendKeys` 方法发送击键来将两个数字相乘。  
  
## <a name="example"></a>示例  
 [!code-vb[VbVbalrMyComputer#25](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-start-an-application-and-send-it-keystrokes_1.vb)]  
  
## <a name="robust-programming"></a>可靠编程  
 如果找不到具有请求的进程标识符的应用程序，则会引发 <xref:System.ArgumentException> 异常。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 对 `Shell` 函数的调用需要完全信任（<xref:System.Security.SecurityException> 类）。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>  
 <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
