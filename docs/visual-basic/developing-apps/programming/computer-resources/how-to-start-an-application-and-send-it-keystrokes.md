---
title: "如何：启动应用程序并向其发送击键 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8bf92a74bc1b60ea3213d80e4df373936c65d89e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a><span data-ttu-id="49c77-102">如何：启动应用程序并向其发送击键 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49c77-102">How to: Start an Application and Send it Keystrokes (Visual Basic)</span></span>
<span data-ttu-id="49c77-103">此示例使用 `Shell` 函数启动计算器应用程序，然后使用 `My.Computer.Keyboard.SendKeys` 方法发送击键来将两个数字相乘。</span><span class="sxs-lookup"><span data-stu-id="49c77-103">This example uses the `Shell` function to start the calculator application and then multiplies two numbers by sending keystrokes using the `My.Computer.Keyboard.SendKeys` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49c77-104">示例</span><span class="sxs-lookup"><span data-stu-id="49c77-104">Example</span></span>  
 [!code-vb[VbVbalrMyComputer#25](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-start-an-application-and-send-it-keystrokes_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="49c77-105">可靠编程</span><span class="sxs-lookup"><span data-stu-id="49c77-105">Robust Programming</span></span>  
 <span data-ttu-id="49c77-106">如果找不到具有请求的进程标识符的应用程序，则会引发 <xref:System.ArgumentException> 异常。</span><span class="sxs-lookup"><span data-stu-id="49c77-106">A <xref:System.ArgumentException> exception is raised if an application with the requested process identifier cannot be found.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="49c77-107">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="49c77-107">.NET Framework Security</span></span>  
 <span data-ttu-id="49c77-108">对 `Shell` 函数的调用需要完全信任（<xref:System.Security.SecurityException> 类）。</span><span class="sxs-lookup"><span data-stu-id="49c77-108">The call to the `Shell` function requires full trust (<xref:System.Security.SecurityException> class).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49c77-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49c77-109">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>  
 <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
