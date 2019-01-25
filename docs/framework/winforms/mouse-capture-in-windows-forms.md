---
title: Windows 窗体中的鼠标捕获
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: ca16d2fa2339f8d9110bb748a687f90e093598fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690317"
---
# <a name="mouse-capture-in-windows-forms"></a><span data-ttu-id="8bbbf-102">Windows 窗体中的鼠标捕获</span><span class="sxs-lookup"><span data-stu-id="8bbbf-102">Mouse Capture in Windows Forms</span></span>
<span data-ttu-id="8bbbf-103">*鼠标捕获*指何时控件执行的所有鼠标输入的命令。</span><span class="sxs-lookup"><span data-stu-id="8bbbf-103">*Mouse capture* refers to when a control takes command of all mouse input.</span></span> <span data-ttu-id="8bbbf-104">当控件已捕获鼠标时，它接收鼠标输入，指示在其边框内为指针。</span><span class="sxs-lookup"><span data-stu-id="8bbbf-104">When a control has captured the mouse, it receives mouse input whether or not the pointer is within its borders.</span></span>  
  
## <a name="setting-mouse-capture"></a><span data-ttu-id="8bbbf-105">设置鼠标捕获</span><span class="sxs-lookup"><span data-stu-id="8bbbf-105">Setting Mouse Capture</span></span>  
 <span data-ttu-id="8bbbf-106">在 Windows 窗体中鼠标用户按鼠标按钮上一个控件，, 并在用户释放鼠标按钮时由控件中释放鼠标时由该控件捕获。</span><span class="sxs-lookup"><span data-stu-id="8bbbf-106">In Windows Forms the mouse is captured by the control when the user presses a mouse button on a control, and the mouse is released by the control when the user releases the mouse button.</span></span>  
  
 <span data-ttu-id="8bbbf-107"><xref:System.Windows.Forms.Control.Capture%2A>属性的<xref:System.Windows.Forms.Control>类指定控件是否已捕获鼠标。</span><span class="sxs-lookup"><span data-stu-id="8bbbf-107">The <xref:System.Windows.Forms.Control.Capture%2A> property of the <xref:System.Windows.Forms.Control> class specifies whether a control has captured the mouse.</span></span> <span data-ttu-id="8bbbf-108">若要确定当控件失去鼠标捕获，请处理<xref:System.Windows.Forms.Control.MouseCaptureChanged>事件。</span><span class="sxs-lookup"><span data-stu-id="8bbbf-108">To determine when a control loses mouse capture, handle the <xref:System.Windows.Forms.Control.MouseCaptureChanged> event.</span></span>  
  
 <span data-ttu-id="8bbbf-109">仅在前台窗口可以捕获鼠标。</span><span class="sxs-lookup"><span data-stu-id="8bbbf-109">Only the foreground window can capture the mouse.</span></span> <span data-ttu-id="8bbbf-110">当后台窗口尝试捕获鼠标时，窗口接收鼠标事件时鼠标指针位于该窗口的可见部分发生的消息。</span><span class="sxs-lookup"><span data-stu-id="8bbbf-110">When a background window attempts to capture the mouse, the window receives messages only for mouse events that occur when the mouse pointer is within the visible portion of the window.</span></span> <span data-ttu-id="8bbbf-111">此外，即使前景窗口已捕获鼠标，用户仍可以单击另一个窗口，将其带到前台。</span><span class="sxs-lookup"><span data-stu-id="8bbbf-111">Also, even if the foreground window has captured the mouse, the user can still click another window, bringing it to the foreground.</span></span> <span data-ttu-id="8bbbf-112">时捕获鼠标、 键盘快捷方式执行操作不起作用。</span><span class="sxs-lookup"><span data-stu-id="8bbbf-112">When the mouse is captured, shortcut keys do not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bbbf-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="8bbbf-113">See also</span></span>
- [<span data-ttu-id="8bbbf-114">Windows 窗体应用程序中的鼠标输入</span><span class="sxs-lookup"><span data-stu-id="8bbbf-114">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
