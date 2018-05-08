---
title: B&#233;zier GDI + 中样条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
ms.openlocfilehash: 2e247ec2bcd57c2fb2f5c32f61d38a2e7a267ff1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="b233zier-splines-in-gdi"></a>B&#233;zier GDI + 中样条
贝塞尔样条是由四个点指定的曲线： 两个终结点 （p1 和 p2） 和两个控点 （c1 和 c2）。 曲线开始于 p1 和 p2 结束。 曲线不会遍历控点，但控制点的作用像磁铁一样，在某些方向上拉拽曲线和影响曲线弯曲的方式。 下图显示其终结点和控制点的贝塞尔曲线。  
  
 ![贝塞尔曲线样条](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")  
  
 曲线开始 p1、 抵达控件点 c1。 为在 p1 曲线切线是从 p1 到 c1 绘制的行。 终结点 p2 处的切线是从 c2 绘制到 p2 的行。  
  
## <a name="drawing-bzier-splines"></a>绘制贝塞尔样条  
 若要绘制的贝塞尔样条，你需要的实例<xref:System.Drawing.Graphics>类和一个<xref:System.Drawing.Pen>。 实例<xref:System.Drawing.Graphics>类提供<xref:System.Drawing.Graphics.DrawBezier%2A>方法，与<xref:System.Drawing.Pen>存储特性，如宽度和用于呈现曲线的线条颜色。 <xref:System.Drawing.Pen>作为一个自变量传递<xref:System.Drawing.Graphics.DrawBezier%2A>方法。 其余的自变量传递给<xref:System.Drawing.Graphics.DrawBezier%2A>方法是终结点和的控制点。 下面的示例绘制的起始点 （0，0） 的贝塞尔样条控制点 （40，20） 和 （80、 150） 和结束点 （100，10）：  
  
 [!code-csharp[LinesCurvesAndShapes#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 下图显示曲线、 控点、 和两条切线。  
  
 ![贝塞尔曲线样条](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art12.gif "Aboutgdip02_art12")  
  
 贝塞尔样条最初已由圣皮埃尔贝塞尔汽车行业中用于设计开发。 它们证明了可在许多类型的计算机辅助设计和也用于定义字体的轮廓。 贝塞尔样条可以产生各种形状，其中一些下面的图中所示。  
  
 ![路径](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art13.gif "Aboutgdip02_art13")  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [直线、曲线和形状](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [构造并绘制曲线](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)  
 [如何：创建用于绘制的图形对象](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [如何：创建笔](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
