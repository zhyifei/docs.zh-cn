---
title: "属性更改事件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad22d77043f00ab0caaa6d8b08b6b0a9eef1fed5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="property-changed-events"></a><span data-ttu-id="4382c-102">属性更改事件</span><span class="sxs-lookup"><span data-stu-id="4382c-102">Property-Changed Events</span></span>
<span data-ttu-id="4382c-103">如果您希望控件名为的属性时发送通知*PropertyName*更改，定义一个名为*PropertyName* `Changed`和一个名为方法`On` *PropertyName* `Changed`引发事件。</span><span class="sxs-lookup"><span data-stu-id="4382c-103">If you want your control to send notifications when a property named *PropertyName* changes, define an event named *PropertyName*`Changed` and a method named `On`*PropertyName*`Changed` that raises the event.</span></span> <span data-ttu-id="4382c-104">Windows 窗体中的命名约定是追加单词*Changed*到属性的名称。</span><span class="sxs-lookup"><span data-stu-id="4382c-104">The naming convention in Windows Forms is to append the word *Changed* to the name of the property.</span></span> <span data-ttu-id="4382c-105">属性更改事件的关联的事件委托类型是<xref:System.EventHandler>，是事件数据类型<xref:System.EventArgs>。</span><span class="sxs-lookup"><span data-stu-id="4382c-105">The associated event delegate type for property-changed events is <xref:System.EventHandler>, and the event data type is <xref:System.EventArgs>.</span></span> <span data-ttu-id="4382c-106">基类<xref:System.Windows.Forms.Control>定义很多属性更改事件，如<xref:System.Windows.Forms.Control.BackColorChanged>， <xref:System.Windows.Forms.Control.BackgroundImageChanged>， <xref:System.Windows.Forms.Control.FontChanged>， <xref:System.Windows.Forms.Control.LocationChanged>，和其他人。</span><span class="sxs-lookup"><span data-stu-id="4382c-106">The base class <xref:System.Windows.Forms.Control> defines many property-changed events, such as <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>, and others.</span></span> <span data-ttu-id="4382c-107">有关事件的背景信息，请参阅[事件](../../../../docs/standard/events/index.md)和[Windows 窗体控件中的事件](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="4382c-107">For background information about events, see [Events](../../../../docs/standard/events/index.md) and [Events in Windows Forms Controls](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="4382c-108">属性更改事件非常有用，因为它们允许使用者的控件附加对更改做出响应的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="4382c-108">Property-changed events are useful because they allow consumers of a control to attach event handlers that respond to the change.</span></span> <span data-ttu-id="4382c-109">如果你的控件需要响应它引发属性更改事件，重写相应`On` *PropertyName* `Changed`而不是将委托附加到事件的方法。</span><span class="sxs-lookup"><span data-stu-id="4382c-109">If your control needs to respond to a property-changed event that it raises, override the corresponding `On`*PropertyName*`Changed` method instead of attaching a delegate to the event.</span></span> <span data-ttu-id="4382c-110">通过更新其他属性或重新绘制的部分或全部其绘图图面，控件通常响应属性更改事件。</span><span class="sxs-lookup"><span data-stu-id="4382c-110">A control typically responds to a property-changed event by updating other properties or by redrawing some or all of its drawing surface.</span></span>  
  
 <span data-ttu-id="4382c-111">下面的示例演示如何`FlashTrackBar`自定义控件的响应它继承自属性更改事件的某些<xref:System.Windows.Forms.Control>。</span><span class="sxs-lookup"><span data-stu-id="4382c-111">The following example shows how the `FlashTrackBar` custom control responds to some of the property-changed events that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="4382c-112">有关完整的示例，请参阅[如何： 创建 Windows 窗体控件，显示进度](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)。</span><span class="sxs-lookup"><span data-stu-id="4382c-112">For the complete sample, see [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="4382c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="4382c-113">See Also</span></span>  
 [<span data-ttu-id="4382c-114">事件</span><span class="sxs-lookup"><span data-stu-id="4382c-114">Events</span></span>](../../../../docs/standard/events/index.md)  
 [<span data-ttu-id="4382c-115">Windows 窗体控件中的事件</span><span class="sxs-lookup"><span data-stu-id="4382c-115">Events in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [<span data-ttu-id="4382c-116">Windows 窗体控件中的属性</span><span class="sxs-lookup"><span data-stu-id="4382c-116">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
