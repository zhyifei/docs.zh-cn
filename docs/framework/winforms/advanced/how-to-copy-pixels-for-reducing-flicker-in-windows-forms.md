---
title: 如何：在 Windows 窗体中复制像素以减少闪烁
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
ms.openlocfilehash: 65428132c885191b62c3b4a76c8937bf8f3f6732
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522039"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>如何：在 Windows 窗体中复制像素以减少闪烁
当你进行动画处理的简单图形时，用户可以有时会出现闪烁或其他不良的视觉效果。 限制此问题的一种方法是使用在图形上的"bitblt"过程。 Bitblt 是"位块传输"颜色数据从像素组成的源矩形向目标矩形的像素为单位。  
  
 用 Windows 窗体 bitblt 通过<xref:System.Drawing.Graphics.CopyFromScreen%2A>方法<xref:System.Drawing.Graphics>类。 在该方法的参数中，你可以指定源和目标 （以磅为单位）、 要复制的区域的大小和用于绘制新形状的图形对象。  
  
 在下面的示例中，在窗体上绘制一个形状其<xref:System.Windows.Forms.Control.Paint>事件处理程序。 然后，<xref:System.Drawing.Graphics.CopyFromScreen%2A>方法用于复制了该形状。  
  
> [!NOTE]
>  设置窗体的<xref:System.Windows.Forms.Control.DoubleBuffered%2A>属性`true`将使基于图形的代码中<xref:System.Windows.Forms.Control.Paint>事件是双缓冲。 而使用下面的代码时，这将不具有任何明显的性能提升，它是使用更复杂的图形操作代码时，需要注意。  
  
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
 在窗体的中运行上面的代码<xref:System.Windows.Forms.Control.Paint>事件处理程序，以便在重绘窗体时，持久保存图形。 在这种情况下，不要调用与图形相关的方法<xref:System.Windows.Forms.Form.Load>事件处理程序，因为所绘制的内容将不会重绘如果窗体调整大小或另一种形式被遮盖。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.CopyPixelOperation>  
 <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>  
 [Windows 窗体中的图形和绘制](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [使用笔绘制直线和形状](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
