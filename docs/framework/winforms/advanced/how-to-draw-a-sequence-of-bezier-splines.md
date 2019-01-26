---
title: 如何：绘制序列的 B&#233;zier 自由绘制曲线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
ms.openlocfilehash: 45e56113334be4c384ef6f615d3062ed7f098ad1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572885"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a>如何：绘制序列的 B&#233;zier 自由绘制曲线
可以使用<xref:System.Drawing.Graphics.DrawBeziers%2A>方法的<xref:System.Drawing.Graphics>类要绘制一系列连接贝塞尔自由绘制曲线。  
  
## <a name="example"></a>示例  
 下面的示例绘制包含两个已连接的贝塞尔样条曲线。 第一个贝塞尔样条的终结点是第二个贝塞尔自由绘制曲线的起始点。  
  
 下图显示了七个点以及已连接的自由绘制曲线。  
  
 ![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>请参阅
- [Windows 窗体中的图形和绘制](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [GDI+ 中的贝塞尔自由绘制曲线](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)
- [构造并绘制曲线](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
