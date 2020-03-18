---
title: 如何：启动应用程序并向其发送击键 - Visual Basic
ms.date: 10/23/2019
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
ms.openlocfilehash: 033999c07bb5839a264122b2ca330916bdf844b8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "72919393"
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a><span data-ttu-id="1d9a5-102">如何：启动应用程序并向其发送击键 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1d9a5-102">How to: start an application and send it keystrokes (Visual Basic)</span></span>

<span data-ttu-id="1d9a5-103">本示例使用 <xref:Microsoft.VisualBasic.Interaction.Shell%2A> 方法启动记事本应用程序，然后使用 [My.Computer.Keyboard.SendKeys](xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A) 方法发送击键来打印句子。</span><span class="sxs-lookup"><span data-stu-id="1d9a5-103">This example uses the <xref:Microsoft.VisualBasic.Interaction.Shell%2A> method to start the Notepad application and then prints a sentence by sending keystrokes using the [My.Computer.Keyboard.SendKeys](xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A) method.</span></span>

## <a name="example"></a><span data-ttu-id="1d9a5-104">示例</span><span class="sxs-lookup"><span data-stu-id="1d9a5-104">Example</span></span>

[!code-vb[VbVbalrMyComputer#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#25)]

## <a name="robust-programming"></a><span data-ttu-id="1d9a5-105">可靠编程</span><span class="sxs-lookup"><span data-stu-id="1d9a5-105">Robust programming</span></span>

<span data-ttu-id="1d9a5-106">如果找不到具有请求的进程标识符的应用程序，则会引发 <xref:System.ArgumentException> 异常。</span><span class="sxs-lookup"><span data-stu-id="1d9a5-106">An <xref:System.ArgumentException> exception is raised if an application with the requested process identifier cannot be found.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1d9a5-107">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="1d9a5-107">.NET Framework Security</span></span>

<span data-ttu-id="1d9a5-108">对 `Shell` 函数的调用需要完全信任（<xref:System.Security.SecurityException> 类）。</span><span class="sxs-lookup"><span data-stu-id="1d9a5-108">The call to the `Shell` function requires full trust (<xref:System.Security.SecurityException> class).</span></span>

## <a name="see-also"></a><span data-ttu-id="1d9a5-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d9a5-109">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
