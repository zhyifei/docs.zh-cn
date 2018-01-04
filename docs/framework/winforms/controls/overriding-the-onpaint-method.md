---
title: "重写 OnPaint 方法"
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
- Paint event [Windows Forms], handling in Windows Forms custom control
- OnPaint method [Windows Forms], overriding in Windows Forms custom controls
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d9012d1a31eeaf50560b6166d32ac58662c5aa4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="overriding-the-onpaint-method"></a><span data-ttu-id="0070e-102">重写 OnPaint 方法</span><span class="sxs-lookup"><span data-stu-id="0070e-102">Overriding the OnPaint Method</span></span>
<span data-ttu-id="0070e-103">重写中定义的任何事件的基本步骤[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]相同，并且以下列表中汇总。</span><span class="sxs-lookup"><span data-stu-id="0070e-103">The basic steps for overriding any event defined in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] are identical and are summarized in the following list.</span></span>  
  
#### <a name="to-override-an-inherited-event"></a><span data-ttu-id="0070e-104">若要重写继承的事件</span><span class="sxs-lookup"><span data-stu-id="0070e-104">To override an inherited event</span></span>  
  
1.  <span data-ttu-id="0070e-105">重写受保护`On` *EventName*方法。</span><span class="sxs-lookup"><span data-stu-id="0070e-105">Override the protected `On`*EventName* method.</span></span>  
  
2.  <span data-ttu-id="0070e-106">调用`On` *EventName*从重写基类方法的`On` *EventName*方法，以便已注册的委托对事件进行接收。</span><span class="sxs-lookup"><span data-stu-id="0070e-106">Call the `On`*EventName* method of the base class from the overridden `On`*EventName* method, so that registered delegates receive the event.</span></span>  
  
 <span data-ttu-id="0070e-107"><xref:System.Windows.Forms.Control.Paint>此处详细地讨论事件，因为每个 Windows 窗体控件必须重写<xref:System.Windows.Forms.Control.Paint>从它继承的事件<xref:System.Windows.Forms.Control>。</span><span class="sxs-lookup"><span data-stu-id="0070e-107">The <xref:System.Windows.Forms.Control.Paint> event is discussed in detail here because every Windows Forms control must override the <xref:System.Windows.Forms.Control.Paint> event that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="0070e-108">基<xref:System.Windows.Forms.Control>类不知道如何派生的控件需要绘制，而不提供中的任何绘制逻辑<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="0070e-108">The base <xref:System.Windows.Forms.Control> class does not know how a derived control needs to be drawn and does not provide any painting logic in the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="0070e-109"><xref:System.Windows.Forms.Control.OnPaint%2A>方法<xref:System.Windows.Forms.Control>只需将调度<xref:System.Windows.Forms.Control.Paint>到已注册的事件接收器的事件。</span><span class="sxs-lookup"><span data-stu-id="0070e-109">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of <xref:System.Windows.Forms.Control> simply dispatches the <xref:System.Windows.Forms.Control.Paint> event to registered event receivers.</span></span>  
  
 <span data-ttu-id="0070e-110">如果你通过中的示例过[如何： 开发简单的 Windows 窗体控件](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)，你已经看到举例说明重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="0070e-110">If you worked through the sample in [How to: Develop a Simple Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md), you have seen an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="0070e-111">下面的代码片段取自该示例。</span><span class="sxs-lookup"><span data-stu-id="0070e-111">The following code fragment is taken from that sample.</span></span>  
  
```vb  
Public Class FirstControl  
   Inherits Control  
  
   Public Sub New()  
   End Sub  
  
   Protected Overrides Sub OnPaint(e As PaintEventArgs)  
      ' Call the OnPaint method of the base class.  
      MyBase.OnPaint(e)  
      ' Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, New SolidBrush(ForeColor), RectangleF.op_Implicit(ClientRectangle))  
   End Sub  
End Class   
```  
  
```csharp  
public class FirstControl : Control{  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }   
}   
```  
  
 <span data-ttu-id="0070e-112"><xref:System.Windows.Forms.PaintEventArgs>类包含的数据的<xref:System.Windows.Forms.Control.Paint>事件。</span><span class="sxs-lookup"><span data-stu-id="0070e-112">The <xref:System.Windows.Forms.PaintEventArgs> class contains data for the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="0070e-113">它具有两个属性，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="0070e-113">It has two properties, as shown in the following code.</span></span>  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   ...  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property   
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs {  
...  
    public System.Drawing.Rectangle ClipRectangle {}  
    public System.Drawing.Graphics Graphics {}  
...  
}  
```  
  
 <span data-ttu-id="0070e-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>是要绘制的矩形和<xref:System.Windows.Forms.PaintEventArgs.Graphics%2A>属性是指<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="0070e-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is the rectangle to be painted, and the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property refers to a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="0070e-115">中的类<xref:System.Drawing?displayProperty=nameWithType>管理命名空间提供功能的访问的类[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，新的 Windows 图形库。</span><span class="sxs-lookup"><span data-stu-id="0070e-115">The classes in the <xref:System.Drawing?displayProperty=nameWithType> namespace are managed classes that provide access to the functionality of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], the new Windows graphics library.</span></span> <span data-ttu-id="0070e-116"><xref:System.Drawing.Graphics>对象具有方法来绘制点、 字符串、 线条、 弧、 省略号，以及许多其他形状。</span><span class="sxs-lookup"><span data-stu-id="0070e-116">The <xref:System.Drawing.Graphics> object has methods to draw points, strings, lines, arcs, ellipses, and many other shapes.</span></span>  
  
 <span data-ttu-id="0070e-117">一个控件时，将调用其<xref:System.Windows.Forms.Control.OnPaint%2A>方法需要更改其可视显示时。</span><span class="sxs-lookup"><span data-stu-id="0070e-117">A control invokes its <xref:System.Windows.Forms.Control.OnPaint%2A> method whenever it needs to change its visual display.</span></span> <span data-ttu-id="0070e-118">此方法将依次引发<xref:System.Windows.Forms.Control.Paint>事件。</span><span class="sxs-lookup"><span data-stu-id="0070e-118">This method in turn raises the <xref:System.Windows.Forms.Control.Paint> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0070e-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="0070e-119">See Also</span></span>  
 [<span data-ttu-id="0070e-120">事件</span><span class="sxs-lookup"><span data-stu-id="0070e-120">Events</span></span>](../../../../docs/standard/events/index.md)  
 [<span data-ttu-id="0070e-121">呈现 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="0070e-121">Rendering a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 [<span data-ttu-id="0070e-122">定义事件</span><span class="sxs-lookup"><span data-stu-id="0070e-122">Defining an Event</span></span>](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)
