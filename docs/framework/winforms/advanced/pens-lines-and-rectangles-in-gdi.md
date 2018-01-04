---
title: "GDI+ 中的笔、直线和矩形"
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
- lines
- GDI+, lines
- drawing [Windows Forms], rectangles
- rectangles
- drawing [Windows Forms], lines
- GDI+, pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- GDI+, rectangles
- examples [Windows Forms], GDI+
- lines [Windows Forms], dashed
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7f21564c800dd960a96dfc024fa2cccc6b27780f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="pens-lines-and-rectangles-in-gdi"></a>GDI+ 中的笔、直线和矩形
若要使用绘制直线[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]你需要创建<xref:System.Drawing.Graphics>对象和一个<xref:System.Drawing.Pen>对象。 <xref:System.Drawing.Graphics>对象提供实际完成绘图，方法与<xref:System.Drawing.Pen>对象存储属性，例如线条颜色、 宽度和样式。  
  
## <a name="drawing-a-line"></a>绘制线条  
 若要绘制线条，调用<xref:System.Drawing.Graphics.DrawLine%2A>方法<xref:System.Drawing.Graphics>对象。 <xref:System.Drawing.Pen>对象作为一个自变量传递<xref:System.Drawing.Graphics.DrawLine%2A>方法。 下面的示例绘制 （4，2） 的点到点 （12、 6） 的行：  
  
 [!code-csharp[LinesCurvesAndShapes#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <xref:System.Drawing.Graphics.DrawLine%2A>属于重载的方法的<xref:System.Drawing.Graphics>类，因此有几种方法，你可以向其提供自变量。 例如，构造两个<xref:System.Drawing.Point>对象并传入<xref:System.Drawing.Point>对象作为自变量<xref:System.Drawing.Graphics.DrawLine%2A>方法：  
  
 [!code-csharp[LinesCurvesAndShapes#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a>构造笔  
 在构造时，可以指定某些属性<xref:System.Drawing.Pen>对象。 例如，一个`Pen`构造函数，可指定颜色和宽度。 下面的示例绘制一条蓝线的宽度 2 从 （0，0） 到 （60，30）：  
  
 [!code-csharp[LinesCurvesAndShapes#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a>虚线和线帽  
 <xref:System.Drawing.Pen>对象还公开属性，如<xref:System.Drawing.Pen.DashStyle%2A>，可用于指定的行的功能。 下面的示例绘制的虚线从 （100，50） 到 （300，80）：  
  
 [!code-csharp[LinesCurvesAndShapes#44](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 你可以使用的属性<xref:System.Drawing.Pen>对象以设置更多特性的行。 <xref:System.Drawing.Pen.StartCap%2A>和<xref:System.Drawing.Pen.EndCap%2A>属性指定的行末尾的外观; 在结束可以平面、 正方形、 圆角、 三角形，或自定义形状。 <xref:System.Drawing.Pen.LineJoin%2A>属性，可以指定是否连接的直线斜接 （具有尖锐角联接）、 倾斜、 舍入，或剪切。 下图显示了各种的线帽和联接样式的行。  
  
 ![行](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art04.gif "Aboutgdip02_art04")  
  
## <a name="drawing-a-rectangle"></a>绘制矩形  
 绘制矩形与[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]类似于绘制线条。 若要绘制一个矩形，你需要<xref:System.Drawing.Graphics>对象和一个<xref:System.Drawing.Pen>对象。 <xref:System.Drawing.Graphics>对象提供<xref:System.Drawing.Graphics.DrawRectangle%2A>方法，与<xref:System.Drawing.Pen>对象存储特性，如线条宽度和颜色。 <xref:System.Drawing.Pen>对象作为一个自变量传递<xref:System.Drawing.Graphics.DrawRectangle%2A>方法。 下面的示例绘制一个具有在其左上角的矩形 （100，50），宽度为 80，和高度为 40:  
  
 [!code-csharp[LinesCurvesAndShapes#45](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <xref:System.Drawing.Graphics.DrawRectangle%2A>属于重载的方法的<xref:System.Drawing.Graphics>类，因此有几种方法，你可以向其提供自变量。 例如，可以构造<xref:System.Drawing.Rectangle>对象并将传递<xref:System.Drawing.Rectangle>对象传递给<xref:System.Drawing.Graphics.DrawRectangle%2A>作为自变量的方法：  
  
 [!code-csharp[LinesCurvesAndShapes#46](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 A<xref:System.Drawing.Rectangle>对象具有方法和属性用于操作和收集有关该矩形的信息。 例如，<xref:System.Drawing.Rectangle.Inflate%2A>和<xref:System.Drawing.Rectangle.Offset%2A>方法更改的大小和位置的矩形。 <xref:System.Drawing.Rectangle.IntersectsWith%2A>方法告诉你该矩形是否与另一个给定矩形，和<xref:System.Drawing.Rectangle.Contains%2A>方法告诉你给定的点是否在该矩形内。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Rectangle?displayProperty=nameWithType>  
 [如何：创建笔](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [如何：在 Windows 窗体上绘制直线](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)  
 [如何：绘制显示边框的形状](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
