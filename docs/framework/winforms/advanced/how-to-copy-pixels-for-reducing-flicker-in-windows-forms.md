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
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>如何：在 Windows 窗体中复制像素以减少闪烁
当您对一个简单的图形进行动画处理时，用户有时可能会遇到闪烁或其他不需要的视觉效果。 限制此问题的一种方法是在图形上使用 "bitblt" 进程。 Bitblt 是颜色数据的 "位块传输"，它将像素的源矩形转换为像素的目标矩形。  
  
 使用 Windows 窗体，可以使用 <xref:System.Drawing.Graphics> 类的 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 方法来实现 bitblt。 在方法的参数中，指定源和目标（如点）、要复制的区域的大小以及用于绘制新形状的图形对象。  
  
 在下面的示例中，在窗体的 <xref:System.Windows.Forms.Control.Paint> 事件处理程序中绘制形状。 然后，使用 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 方法来复制形状。  
  
> [!NOTE]
> 将窗体的 <xref:System.Windows.Forms.Control.DoubleBuffered%2A> 属性设置为 `true` 会使 <xref:System.Windows.Forms.Control.Paint> 事件中基于图形的代码双缓冲。 当使用下面的代码时，这将不会有任何明显的性能提升，而是在使用更复杂的图形操作代码时需要注意的事项。  
  
## <a name="example"></a>示例  
  
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
  
## <a name="compiling-the-code"></a>编译代码  
 上面的代码在窗体的 <xref:System.Windows.Forms.Control.Paint> 事件处理程序中运行，以便在重绘窗体时保持图形。 因此，请不要在 <xref:System.Windows.Forms.Form.Load> 事件处理程序中调用与图形相关的方法，因为当窗体调整或被其他窗体遮住时，不会重新绘制所绘制的内容。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
- [使用笔绘制直线和形状](using-a-pen-to-draw-lines-and-shapes.md)
