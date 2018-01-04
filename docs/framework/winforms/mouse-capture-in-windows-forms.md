---
title: "Windows 窗体中的鼠标捕获"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7cc62780579c852aaa637a3ccc13ce2929423868
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="mouse-capture-in-windows-forms"></a><span data-ttu-id="583f0-102">Windows 窗体中的鼠标捕获</span><span class="sxs-lookup"><span data-stu-id="583f0-102">Mouse Capture in Windows Forms</span></span>
<span data-ttu-id="583f0-103">*鼠标捕获*指控制所采用的所有鼠标输入的命令。</span><span class="sxs-lookup"><span data-stu-id="583f0-103">*Mouse capture* refers to when a control takes command of all mouse input.</span></span> <span data-ttu-id="583f0-104">当控件已捕获鼠标时，它会接收鼠标输入，指示在其边框内为指针。</span><span class="sxs-lookup"><span data-stu-id="583f0-104">When a control has captured the mouse, it receives mouse input whether or not the pointer is within its borders.</span></span>  
  
## <a name="setting-mouse-capture"></a><span data-ttu-id="583f0-105">设置鼠标捕获</span><span class="sxs-lookup"><span data-stu-id="583f0-105">Setting Mouse Capture</span></span>  
 <span data-ttu-id="583f0-106">Windows 窗体中捕获了鼠标是由该控件在用户按鼠标按钮控件，并当用户释放鼠标按钮时由该控件中释放鼠标时。</span><span class="sxs-lookup"><span data-stu-id="583f0-106">In Windows Forms the mouse is captured by the control when the user presses a mouse button on a control, and the mouse is released by the control when the user releases the mouse button.</span></span>  
  
 <span data-ttu-id="583f0-107"><xref:System.Windows.Forms.Control.Capture%2A>属性<xref:System.Windows.Forms.Control>类指定控件是否已捕获鼠标。</span><span class="sxs-lookup"><span data-stu-id="583f0-107">The <xref:System.Windows.Forms.Control.Capture%2A> property of the <xref:System.Windows.Forms.Control> class specifies whether a control has captured the mouse.</span></span> <span data-ttu-id="583f0-108">若要确定当控件失去鼠标捕获，处理<xref:System.Windows.Forms.Control.MouseCaptureChanged>事件。</span><span class="sxs-lookup"><span data-stu-id="583f0-108">To determine when a control loses mouse capture, handle the <xref:System.Windows.Forms.Control.MouseCaptureChanged> event.</span></span>  
  
 <span data-ttu-id="583f0-109">只有前台窗口可以捕获鼠标。</span><span class="sxs-lookup"><span data-stu-id="583f0-109">Only the foreground window can capture the mouse.</span></span> <span data-ttu-id="583f0-110">当后台窗口尝试捕获鼠标时，窗口只接收的消息时发生鼠标指针位于窗口的可见部分的鼠标事件。</span><span class="sxs-lookup"><span data-stu-id="583f0-110">When a background window attempts to capture the mouse, the window receives messages only for mouse events that occur when the mouse pointer is within the visible portion of the window.</span></span> <span data-ttu-id="583f0-111">此外，即使前景窗口已捕获鼠标，用户仍可以单击另一个窗口，使其变为前台。</span><span class="sxs-lookup"><span data-stu-id="583f0-111">Also, even if the foreground window has captured the mouse, the user can still click another window, bringing it to the foreground.</span></span> <span data-ttu-id="583f0-112">当将鼠标捕获时，键盘快捷方式执行操作无法工作。</span><span class="sxs-lookup"><span data-stu-id="583f0-112">When the mouse is captured, shortcut keys do not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="583f0-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="583f0-113">See Also</span></span>  
 [<span data-ttu-id="583f0-114">Windows 窗体应用程序中的鼠标输入</span><span class="sxs-lookup"><span data-stu-id="583f0-114">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
