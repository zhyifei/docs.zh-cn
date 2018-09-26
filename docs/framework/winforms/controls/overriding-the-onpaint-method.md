---
title: 重写 OnPaint 方法
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Paint event [Windows Forms], handling in Windows Forms custom control
- OnPaint method [Windows Forms], overriding in Windows Forms custom controls
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
ms.openlocfilehash: fbc0a82f82afcc59384246b58437d521d56d708b
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47208349"
---
# <a name="overriding-the-onpaint-method"></a><span data-ttu-id="26739-102">重写 OnPaint 方法</span><span class="sxs-lookup"><span data-stu-id="26739-102">Overriding the OnPaint Method</span></span>
<span data-ttu-id="26739-103">重写中定义任何事件的基本步骤[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]相同，并且在以下列表总结了。</span><span class="sxs-lookup"><span data-stu-id="26739-103">The basic steps for overriding any event defined in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] are identical and are summarized in the following list.</span></span>  
  
#### <a name="to-override-an-inherited-event"></a><span data-ttu-id="26739-104">若要重写继承的事件</span><span class="sxs-lookup"><span data-stu-id="26739-104">To override an inherited event</span></span>  
  
1.  <span data-ttu-id="26739-105">重写受保护`On` *EventName*方法。</span><span class="sxs-lookup"><span data-stu-id="26739-105">Override the protected `On`*EventName* method.</span></span>  
  
2.  <span data-ttu-id="26739-106">调用`On` *EventName*方法重写从基类`On` *EventName*方法，因此已注册的委托接收事件。</span><span class="sxs-lookup"><span data-stu-id="26739-106">Call the `On`*EventName* method of the base class from the overridden `On`*EventName* method, so that registered delegates receive the event.</span></span>  
  
 <span data-ttu-id="26739-107"><xref:System.Windows.Forms.Control.Paint>在此处详细论述事件，因为每个 Windows 窗体控件必须重写<xref:System.Windows.Forms.Control.Paint>它所继承的事件<xref:System.Windows.Forms.Control>。</span><span class="sxs-lookup"><span data-stu-id="26739-107">The <xref:System.Windows.Forms.Control.Paint> event is discussed in detail here because every Windows Forms control must override the <xref:System.Windows.Forms.Control.Paint> event that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="26739-108">基<xref:System.Windows.Forms.Control>类不知道如何派生的控件需要绘制时，它不提供任何绘制逻辑中的<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="26739-108">The base <xref:System.Windows.Forms.Control> class does not know how a derived control needs to be drawn and does not provide any painting logic in the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="26739-109"><xref:System.Windows.Forms.Control.OnPaint%2A>方法<xref:System.Windows.Forms.Control>只需将调度<xref:System.Windows.Forms.Control.Paint>到已注册的事件接收器的事件。</span><span class="sxs-lookup"><span data-stu-id="26739-109">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of <xref:System.Windows.Forms.Control> simply dispatches the <xref:System.Windows.Forms.Control.Paint> event to registered event receivers.</span></span>  
  
 <span data-ttu-id="26739-110">如果您已完成中的示例[如何： 开发简单的 Windows 窗体控件](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)，你已了解的重写示例<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="26739-110">If you worked through the sample in [How to: Develop a Simple Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md), you have seen an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="26739-111">下面的代码片段摘自该示例。</span><span class="sxs-lookup"><span data-stu-id="26739-111">The following code fragment is taken from that sample.</span></span>  
  
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
public class FirstControl : Control {  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }   
}   
```  
  
 <span data-ttu-id="26739-112"><xref:System.Windows.Forms.PaintEventArgs>类包含用于数据<xref:System.Windows.Forms.Control.Paint>事件。</span><span class="sxs-lookup"><span data-stu-id="26739-112">The <xref:System.Windows.Forms.PaintEventArgs> class contains data for the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="26739-113">它具有两个属性，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="26739-113">It has two properties, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="26739-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 是否要绘制的矩形和<xref:System.Windows.Forms.PaintEventArgs.Graphics%2A>属性是指<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="26739-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is the rectangle to be painted, and the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property refers to a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="26739-115">中的类<xref:System.Drawing?displayProperty=nameWithType>管理命名空间提供的功能的访问的类[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，新的 Windows 图形库。</span><span class="sxs-lookup"><span data-stu-id="26739-115">The classes in the <xref:System.Drawing?displayProperty=nameWithType> namespace are managed classes that provide access to the functionality of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], the new Windows graphics library.</span></span> <span data-ttu-id="26739-116"><xref:System.Drawing.Graphics>对象具有用于绘制点、 字符串、 线条、 弧线、 椭圆和许多其他形状的方法。</span><span class="sxs-lookup"><span data-stu-id="26739-116">The <xref:System.Drawing.Graphics> object has methods to draw points, strings, lines, arcs, ellipses, and many other shapes.</span></span>  
  
 <span data-ttu-id="26739-117">控件调用其<xref:System.Windows.Forms.Control.OnPaint%2A>方法需要更改其可视显示时。</span><span class="sxs-lookup"><span data-stu-id="26739-117">A control invokes its <xref:System.Windows.Forms.Control.OnPaint%2A> method whenever it needs to change its visual display.</span></span> <span data-ttu-id="26739-118">此方法反过来引发<xref:System.Windows.Forms.Control.Paint>事件。</span><span class="sxs-lookup"><span data-stu-id="26739-118">This method in turn raises the <xref:System.Windows.Forms.Control.Paint> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26739-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="26739-119">See Also</span></span>  
 [<span data-ttu-id="26739-120">事件</span><span class="sxs-lookup"><span data-stu-id="26739-120">Events</span></span>](../../../../docs/standard/events/index.md)  
 [<span data-ttu-id="26739-121">呈现 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="26739-121">Rendering a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 [<span data-ttu-id="26739-122">定义事件</span><span class="sxs-lookup"><span data-stu-id="26739-122">Defining an Event</span></span>](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)
