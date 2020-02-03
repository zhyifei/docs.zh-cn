---
title: 如何：复制像素以减少闪烁
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitblt
- graphics [Windows Forms], copying
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing flicker
- pixels [Windows Forms], copying
- flicker
- bit-block transfer
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
ms.openlocfilehash: 299041e7038d5bd5b9824d668b3f47d842030ac7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746482"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a><span data-ttu-id="8e3b8-102">如何：在 Windows 窗体中复制像素以减少闪烁</span><span class="sxs-lookup"><span data-stu-id="8e3b8-102">How to: Copy Pixels for Reducing Flicker in Windows Forms</span></span>
<span data-ttu-id="8e3b8-103">当您对一个简单的图形进行动画处理时，用户有时可能会遇到闪烁或其他不需要的视觉效果。</span><span class="sxs-lookup"><span data-stu-id="8e3b8-103">When you animate a simple graphic, users can sometimes encounter flicker or other undesirable visual effects.</span></span> <span data-ttu-id="8e3b8-104">限制此问题的一种方法是在图形上使用 "bitblt" 进程。</span><span class="sxs-lookup"><span data-stu-id="8e3b8-104">One way to limit this problem is to use a "bitblt" process on the graphic.</span></span> <span data-ttu-id="8e3b8-105">Bitblt 是颜色数据的 "位块传输"，它将像素的源矩形转换为像素的目标矩形。</span><span class="sxs-lookup"><span data-stu-id="8e3b8-105">Bitblt is the "bit-block transfer" of the color data from an origin rectangle of pixels to a destination rectangle of pixels.</span></span>  
  
 <span data-ttu-id="8e3b8-106">使用 Windows 窗体，可以使用 <xref:System.Drawing.Graphics> 类的 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 方法来实现 bitblt。</span><span class="sxs-lookup"><span data-stu-id="8e3b8-106">With Windows Forms, bitblt is accomplished using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="8e3b8-107">在方法的参数中，指定源和目标（如点）、要复制的区域的大小以及用于绘制新形状的图形对象。</span><span class="sxs-lookup"><span data-stu-id="8e3b8-107">In the parameters of the method, you specify the source and destination (as points), the size of the area to be copied, and the graphics object used to draw the new shape.</span></span>  
  
 <span data-ttu-id="8e3b8-108">在下面的示例中，在窗体的 <xref:System.Windows.Forms.Control.Paint> 事件处理程序中绘制形状。</span><span class="sxs-lookup"><span data-stu-id="8e3b8-108">In the example below, a shape is drawn on the form in its <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="8e3b8-109">然后，使用 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 方法来复制形状。</span><span class="sxs-lookup"><span data-stu-id="8e3b8-109">Then, the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method is used to duplicate the shape.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e3b8-110">将窗体的 <xref:System.Windows.Forms.Control.DoubleBuffered%2A> 属性设置为 `true` 会使 <xref:System.Windows.Forms.Control.Paint> 事件中基于图形的代码双缓冲。</span><span class="sxs-lookup"><span data-stu-id="8e3b8-110">Setting the form's <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true` will make graphics-based code in the <xref:System.Windows.Forms.Control.Paint> event be double-buffered.</span></span> <span data-ttu-id="8e3b8-111">当使用下面的代码时，这将不会有任何明显的性能提升，而是在使用更复杂的图形操作代码时需要注意的事项。</span><span class="sxs-lookup"><span data-stu-id="8e3b8-111">While this will not have any discernible performance gains when using the code below, it is something to keep in mind when working with more complex graphics-manipulation code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e3b8-112">示例</span><span class="sxs-lookup"><span data-stu-id="8e3b8-112">Example</span></span>  
  
```vb  
Private Sub Form1_Paint(ByVal sender As Object, ByVal e As _  
    System.Windows.Forms.PaintEventArgs) Handles MyBase.Paint  
    ' Draw a circle with a bar on top.  
        e.Graphics.FillEllipse(Brushes.DarkBlue, New Rectangle _  
             (10, 10, 60, 60))  
        e.Graphics.FillRectangle(Brushes.Khaki, New Rectangle _  
             (20, 30, 60, 10))  
    ' Copy the graphic to a new location.  
        e.Graphics.CopyFromScreen(New Point(10, 10), New Point _  
             (100, 100), New Size(70, 70))  
End Sub  
```  
  
```csharp  
private void Form1_Paint(System.Object sender,  
    System.Windows.Forms.PaintEventArgs e)  
        {  
        e.Graphics.FillEllipse(Brushes.DarkBlue, new  
            Rectangle(10,10,60,60));  
        e.Graphics.FillRectangle(Brushes.Khaki, new  
            Rectangle(20,30,60,10));  
        e.Graphics.CopyFromScreen(new Point(10, 10), new Point(100, 100),   
            new Size(70, 70));  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8e3b8-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="8e3b8-113">Compiling the Code</span></span>  
 <span data-ttu-id="8e3b8-114">上面的代码在窗体的 <xref:System.Windows.Forms.Control.Paint> 事件处理程序中运行，以便在重绘窗体时保持图形。</span><span class="sxs-lookup"><span data-stu-id="8e3b8-114">The code above is run in the form's <xref:System.Windows.Forms.Control.Paint> event handler so that the graphics persist when the form is redrawn.</span></span> <span data-ttu-id="8e3b8-115">因此，请不要在 <xref:System.Windows.Forms.Form.Load> 事件处理程序中调用与图形相关的方法，因为当窗体调整或被其他窗体遮住时，不会重新绘制所绘制的内容。</span><span class="sxs-lookup"><span data-stu-id="8e3b8-115">As such, do not call graphics-related methods in the <xref:System.Windows.Forms.Form.Load> event handler, because the drawn content will not be redrawn if the form is resized or obscured by another form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e3b8-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e3b8-116">See also</span></span>

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8e3b8-117">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="8e3b8-117">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="8e3b8-118">使用笔绘制直线和形状</span><span class="sxs-lookup"><span data-stu-id="8e3b8-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
