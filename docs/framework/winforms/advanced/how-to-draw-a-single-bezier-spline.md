---
title: 如何： 绘制单个 B&#233;zier 样条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: 9e91b63275c37fc0cdde5721fddd114e1bf2264e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-a-single-b233zier-spline"></a>如何： 绘制单个 B&#233;zier 样条
由四个点定义的贝塞尔样条： 起始点，这两个控制点，终结点。  
  
## <a name="example"></a>示例  
 下面的示例绘制与 （10，100） 的起始点和终结点 （200，100） 的贝塞尔样条。 两个控制点 （100、 10） 和 （150，150）。  
  
 下图显示以及其起始点、 控点和终结点生成的贝塞尔样条。 该插图还显示样条的凸包，这是通过使用直线连接四个点而形成的多边形。  
  
 ![贝塞尔样条](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.Graphics.DrawBezier%2A>  
 [GDI+ 中的贝塞尔自由绘制曲线](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [如何：绘制一系列贝塞尔自由绘制曲线](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)
