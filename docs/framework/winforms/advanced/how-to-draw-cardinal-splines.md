---
title: 如何：绘制基数样条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
ms.openlocfilehash: 9f2fd0f54c95ff2185c1a1d17785d300c97f7f4f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739795"
---
# <a name="how-to-draw-cardinal-splines"></a>如何：绘制基数样条
基数样条是平滑地通过一组给定的点的曲线。 若要绘制的基数样条，创建<xref:System.Drawing.Graphics>对象并将传递指向数组的地址<xref:System.Drawing.Graphics.DrawCurve%2A>方法。  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a>绘制钟形基数样条  
  
-   下面的示例绘制的钟形基数样条通过五个指定点。 下图显示了曲线和五个点。  
  
     ![基数样条曲线](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a>绘制闭合的基数样条  
  
-   使用<xref:System.Drawing.Graphics.DrawClosedCurve%2A>方法的<xref:System.Drawing.Graphics>类来绘制闭合基数样条。 闭合的基数样条曲线持续到数组中的最后一个点并向数组中的第一个点连接。 下面的示例绘制通过六个指定点的闭合基数样条。 下图显示了已关闭的样条曲线和六个点。  
  
 ![基数样条曲线](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a>更改基数样条曲线的弯曲  
  
-   更改的基数样条弯曲的张力自变量表示通过方式<xref:System.Drawing.Graphics.DrawCurve%2A>方法。 下面的示例绘制三个传递一组相同的点的基数样条。 下图显示了其张力值以及三个自由绘制曲线。 请注意张力为 0 时, 点由直线连接。  
  
 ![基数样条曲线](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例设计为使用 Windows 窗体，它们需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。  
  
## <a name="see-also"></a>请参阅
- [直线、曲线和形状](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)
- [构造并绘制曲线](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
