---
title: Windows 窗体控件中的事件
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: 41ad95de7a65dbd0cb3a0d1af8f5c8cb00c1ccdd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971970"
---
# <a name="events-in-windows-forms-controls"></a><span data-ttu-id="c9200-102">Windows 窗体控件中的事件</span><span class="sxs-lookup"><span data-stu-id="c9200-102">Events in Windows Forms Controls</span></span>
<span data-ttu-id="c9200-103">Windows 窗体控件继承六十多个事件从<xref:System.Windows.Forms.Control?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="c9200-103">A Windows Forms control inherits more than sixty events from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c9200-104">其中包括<xref:System.Windows.Forms.Control.Paint>事件，这会导致要绘制的控件、 事件与显示一个窗口，如相关<xref:System.Windows.Forms.Control.Resize>和<xref:System.Windows.Forms.Control.Layout>事件和低级别的鼠标和键盘事件。</span><span class="sxs-lookup"><span data-stu-id="c9200-104">These include the <xref:System.Windows.Forms.Control.Paint> event, which causes a control to be drawn, events related to displaying a window, such as the <xref:System.Windows.Forms.Control.Resize> and <xref:System.Windows.Forms.Control.Layout> events, and low-level mouse and keyboard events.</span></span> <span data-ttu-id="c9200-105">某些低级别事件通过合成<xref:System.Windows.Forms.Control>到语义事件，如<xref:System.Windows.Forms.Control.Click>和<xref:System.Windows.Forms.Control.DoubleClick>。</span><span class="sxs-lookup"><span data-stu-id="c9200-105">Some low-level events are synthesized by <xref:System.Windows.Forms.Control> into semantic events such as <xref:System.Windows.Forms.Control.Click> and <xref:System.Windows.Forms.Control.DoubleClick>.</span></span> <span data-ttu-id="c9200-106">有关继承事件的详细信息，请参阅<xref:System.Windows.Forms.Control>。</span><span class="sxs-lookup"><span data-stu-id="c9200-106">For details about inherited events, see <xref:System.Windows.Forms.Control>.</span></span>  
  
 <span data-ttu-id="c9200-107">如果自定义控件需要重写继承事件功能，请重写继承的 `On`*EventName* 方法，而不附加委托。</span><span class="sxs-lookup"><span data-stu-id="c9200-107">If your custom control needs to override inherited event functionality, override the inherited `On`*EventName* method instead of attaching a delegate.</span></span> <span data-ttu-id="c9200-108">如果不熟悉 .NET Framework 中的事件模型，请参阅[从组件引发事件](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="c9200-108">If you are not familiar with the event model in the .NET Framework, see [Raising Events from a Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9200-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9200-109">See also</span></span>

- [<span data-ttu-id="c9200-110">重写 OnPaint 方法</span><span class="sxs-lookup"><span data-stu-id="c9200-110">Overriding the OnPaint Method</span></span>](overriding-the-onpaint-method.md)
- [<span data-ttu-id="c9200-111">处理用户输入</span><span class="sxs-lookup"><span data-stu-id="c9200-111">Handling User Input</span></span>](handling-user-input.md)
- [<span data-ttu-id="c9200-112">定义事件</span><span class="sxs-lookup"><span data-stu-id="c9200-112">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
- [<span data-ttu-id="c9200-113">事件</span><span class="sxs-lookup"><span data-stu-id="c9200-113">Events</span></span>](../../../standard/events/index.md)
