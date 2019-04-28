---
title: 属性更改事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
ms.openlocfilehash: cabfd9e799288a332a0b2f96140f5f1cc328508b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755423"
---
# <a name="property-changed-events"></a><span data-ttu-id="beb4b-102">属性更改事件</span><span class="sxs-lookup"><span data-stu-id="beb4b-102">Property-Changed Events</span></span>
<span data-ttu-id="beb4b-103">如果您希望控件名为的属性时发送通知*PropertyName*的更改，定义一个名为*PropertyName* `Changed`和一个名为方法`On` *PropertyName* `Changed`引发事件。</span><span class="sxs-lookup"><span data-stu-id="beb4b-103">If you want your control to send notifications when a property named *PropertyName* changes, define an event named *PropertyName*`Changed` and a method named `On`*PropertyName*`Changed` that raises the event.</span></span> <span data-ttu-id="beb4b-104">在 Windows 窗体中的命名约定是追加单词*Changed*到属性的名称。</span><span class="sxs-lookup"><span data-stu-id="beb4b-104">The naming convention in Windows Forms is to append the word *Changed* to the name of the property.</span></span> <span data-ttu-id="beb4b-105">属性更改事件的关联的事件委托类型是<xref:System.EventHandler>，并且事件数据类型为<xref:System.EventArgs>。</span><span class="sxs-lookup"><span data-stu-id="beb4b-105">The associated event delegate type for property-changed events is <xref:System.EventHandler>, and the event data type is <xref:System.EventArgs>.</span></span> <span data-ttu-id="beb4b-106">类的基类<xref:System.Windows.Forms.Control>定义多个属性更改事件，例如<xref:System.Windows.Forms.Control.BackColorChanged>， <xref:System.Windows.Forms.Control.BackgroundImageChanged>， <xref:System.Windows.Forms.Control.FontChanged>， <xref:System.Windows.Forms.Control.LocationChanged>，等等。</span><span class="sxs-lookup"><span data-stu-id="beb4b-106">The base class <xref:System.Windows.Forms.Control> defines many property-changed events, such as <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>, and others.</span></span> <span data-ttu-id="beb4b-107">有关事件的背景信息，请参阅[事件](../../../standard/events/index.md)并[Windows 窗体控件中的事件](events-in-windows-forms-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="beb4b-107">For background information about events, see [Events](../../../standard/events/index.md) and [Events in Windows Forms Controls](events-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="beb4b-108">属性更改事件非常有用，因为它们允许使用者控件的附加事件处理程序对更改做出响应。</span><span class="sxs-lookup"><span data-stu-id="beb4b-108">Property-changed events are useful because they allow consumers of a control to attach event handlers that respond to the change.</span></span> <span data-ttu-id="beb4b-109">如果您的控件需要以响应，它会发出属性更改事件，重写相应`On` *PropertyName* `Changed`而不是将委托附加到该事件的方法。</span><span class="sxs-lookup"><span data-stu-id="beb4b-109">If your control needs to respond to a property-changed event that it raises, override the corresponding `On`*PropertyName*`Changed` method instead of attaching a delegate to the event.</span></span> <span data-ttu-id="beb4b-110">通过更新其他属性或重新绘制的部分或所有其绘图图面，控件通常响应属性更改事件。</span><span class="sxs-lookup"><span data-stu-id="beb4b-110">A control typically responds to a property-changed event by updating other properties or by redrawing some or all of its drawing surface.</span></span>  
  
 <span data-ttu-id="beb4b-111">下面的示例演示如何`FlashTrackBar`自定义控件对一些它所继承的属性更改事件的响应<xref:System.Windows.Forms.Control>。</span><span class="sxs-lookup"><span data-stu-id="beb4b-111">The following example shows how the `FlashTrackBar` custom control responds to some of the property-changed events that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="beb4b-112">有关完整示例，请参阅[如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)。</span><span class="sxs-lookup"><span data-stu-id="beb4b-112">For the complete sample, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="beb4b-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="beb4b-113">See also</span></span>

- [<span data-ttu-id="beb4b-114">事件</span><span class="sxs-lookup"><span data-stu-id="beb4b-114">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="beb4b-115">Windows 窗体控件中的事件</span><span class="sxs-lookup"><span data-stu-id="beb4b-115">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="beb4b-116">Windows 窗体控件中的属性</span><span class="sxs-lookup"><span data-stu-id="beb4b-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
