---
title: 控件中的事件
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: c60713917b9c84aa7fad50fb1c81fc9252149ad6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745752"
---
# <a name="events-in-windows-forms-controls"></a><span data-ttu-id="c06c5-102">Windows 窗体控件中的事件</span><span class="sxs-lookup"><span data-stu-id="c06c5-102">Events in Windows Forms Controls</span></span>
<span data-ttu-id="c06c5-103">Windows 窗体控件从 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>继承了60多个事件。</span><span class="sxs-lookup"><span data-stu-id="c06c5-103">A Windows Forms control inherits more than sixty events from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c06c5-104">其中包括 <xref:System.Windows.Forms.Control.Paint> 事件，该事件将导致控件绘制，与显示窗口相关的事件，如 <xref:System.Windows.Forms.Control.Resize> 和 <xref:System.Windows.Forms.Control.Layout> 事件以及低级别鼠标和键盘事件。</span><span class="sxs-lookup"><span data-stu-id="c06c5-104">These include the <xref:System.Windows.Forms.Control.Paint> event, which causes a control to be drawn, events related to displaying a window, such as the <xref:System.Windows.Forms.Control.Resize> and <xref:System.Windows.Forms.Control.Layout> events, and low-level mouse and keyboard events.</span></span> <span data-ttu-id="c06c5-105">某些低级别的事件通过 <xref:System.Windows.Forms.Control> 到语义事件（如 <xref:System.Windows.Forms.Control.Click> 和 <xref:System.Windows.Forms.Control.DoubleClick>）合成。</span><span class="sxs-lookup"><span data-stu-id="c06c5-105">Some low-level events are synthesized by <xref:System.Windows.Forms.Control> into semantic events such as <xref:System.Windows.Forms.Control.Click> and <xref:System.Windows.Forms.Control.DoubleClick>.</span></span> <span data-ttu-id="c06c5-106">有关继承事件的详细信息，请参阅 <xref:System.Windows.Forms.Control>。</span><span class="sxs-lookup"><span data-stu-id="c06c5-106">For details about inherited events, see <xref:System.Windows.Forms.Control>.</span></span>  
  
 <span data-ttu-id="c06c5-107">如果自定义控件需要重写继承事件功能，请重写继承的 `On`*EventName* 方法，而不附加委托。</span><span class="sxs-lookup"><span data-stu-id="c06c5-107">If your custom control needs to override inherited event functionality, override the inherited `On`*EventName* method instead of attaching a delegate.</span></span> <span data-ttu-id="c06c5-108">如果不熟悉 .NET Framework 中的事件模型，请参阅[从组件引发事件](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="c06c5-108">If you are not familiar with the event model in the .NET Framework, see [Raising Events from a Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c06c5-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c06c5-109">See also</span></span>

- [<span data-ttu-id="c06c5-110">重写 OnPaint 方法</span><span class="sxs-lookup"><span data-stu-id="c06c5-110">Overriding the OnPaint Method</span></span>](overriding-the-onpaint-method.md)
- [<span data-ttu-id="c06c5-111">处理用户输入</span><span class="sxs-lookup"><span data-stu-id="c06c5-111">Handling User Input</span></span>](handling-user-input.md)
- [<span data-ttu-id="c06c5-112">定义事件</span><span class="sxs-lookup"><span data-stu-id="c06c5-112">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
- [<span data-ttu-id="c06c5-113">事件</span><span class="sxs-lookup"><span data-stu-id="c06c5-113">Events</span></span>](../../../standard/events/index.md)
