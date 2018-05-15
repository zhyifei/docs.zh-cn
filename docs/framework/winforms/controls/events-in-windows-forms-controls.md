---
title: Windows 窗体控件中的事件
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: 5d51b6a71bffb546c85ba253181453f6deecfa64
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="events-in-windows-forms-controls"></a><span data-ttu-id="d93c4-102">Windows 窗体控件中的事件</span><span class="sxs-lookup"><span data-stu-id="d93c4-102">Events in Windows Forms Controls</span></span>
<span data-ttu-id="d93c4-103">Windows 窗体控件继承来自多个六十事件<xref:System.Windows.Forms.Control?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="d93c4-103">A Windows Forms control inherits more than sixty events from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d93c4-104">其中包括<xref:System.Windows.Forms.Control.Paint>事件，这会导致要绘制的控件，如显示一个窗口，与相关的事件<xref:System.Windows.Forms.Control.Resize>和<xref:System.Windows.Forms.Control.Layout>事件和低级别的鼠标和键盘事件。</span><span class="sxs-lookup"><span data-stu-id="d93c4-104">These include the <xref:System.Windows.Forms.Control.Paint> event, which causes a control to be drawn, events related to displaying a window, such as the <xref:System.Windows.Forms.Control.Resize> and <xref:System.Windows.Forms.Control.Layout> events, and low-level mouse and keyboard events.</span></span> <span data-ttu-id="d93c4-105">某些低级别事件合成通过<xref:System.Windows.Forms.Control>到语义事件<xref:System.Windows.Forms.Control.Click>和<xref:System.Windows.Forms.Control.DoubleClick>。</span><span class="sxs-lookup"><span data-stu-id="d93c4-105">Some low-level events are synthesized by <xref:System.Windows.Forms.Control> into semantic events such as <xref:System.Windows.Forms.Control.Click> and <xref:System.Windows.Forms.Control.DoubleClick>.</span></span> <span data-ttu-id="d93c4-106">有关继承的事件的详细信息，请参阅<xref:System.Windows.Forms.Control>。</span><span class="sxs-lookup"><span data-stu-id="d93c4-106">For details about inherited events, see <xref:System.Windows.Forms.Control>.</span></span>  
  
 <span data-ttu-id="d93c4-107">如果自定义控件需要重写继承事件功能，请重写继承的 `On`*EventName* 方法，而不附加委托。</span><span class="sxs-lookup"><span data-stu-id="d93c4-107">If your custom control needs to override inherited event functionality, override the inherited `On`*EventName* method instead of attaching a delegate.</span></span> <span data-ttu-id="d93c4-108">如果不熟悉 .NET Framework 中的事件模型，请参阅[从组件引发事件](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0)。</span><span class="sxs-lookup"><span data-stu-id="d93c4-108">If you are not familiar with the event model in the .NET Framework, see [Raising Events from a Component](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d93c4-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="d93c4-109">See Also</span></span>  
 [<span data-ttu-id="d93c4-110">重写 OnPaint 方法</span><span class="sxs-lookup"><span data-stu-id="d93c4-110">Overriding the OnPaint Method</span></span>](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)  
 [<span data-ttu-id="d93c4-111">处理用户输入</span><span class="sxs-lookup"><span data-stu-id="d93c4-111">Handling User Input</span></span>](../../../../docs/framework/winforms/controls/handling-user-input.md)  
 [<span data-ttu-id="d93c4-112">定义事件</span><span class="sxs-lookup"><span data-stu-id="d93c4-112">Defining an Event</span></span>](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [<span data-ttu-id="d93c4-113">事件</span><span class="sxs-lookup"><span data-stu-id="d93c4-113">Events</span></span>](../../../../docs/standard/events/index.md)
