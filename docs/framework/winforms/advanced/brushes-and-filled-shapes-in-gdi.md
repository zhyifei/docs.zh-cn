---
title: GDI+ 中的画笔和实心形状
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [Windows Forms], GDI+
- filled shapes [Windows Forms], GDI+
- shapes [Windows Forms], GDI+
- GDI+, brushes
- GDI+, filled shapes
- gradient brushes
- brushes [Windows Forms], gradient
ms.assetid: e863e2a7-0294-4130-99b6-f1ea3201e7cd
ms.openlocfilehash: 9475518a5f0422e0eac1ec521088071bb4d1c885
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518987"
---
# <a name="brushes-and-filled-shapes-in-gdi"></a>GDI+ 中的画笔和实心形状
闭合的形状，如矩形或椭圆由概述和内部组成。 使用钢笔绘制轮廓和使用画笔填充其内部。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 提供了几个画笔类填充的闭合形状的内部： <xref:System.Drawing.SolidBrush>， <xref:System.Drawing.Drawing2D.HatchBrush>， <xref:System.Drawing.TextureBrush>， <xref:System.Drawing.Drawing2D.LinearGradientBrush>，和<xref:System.Drawing.Drawing2D.PathGradientBrush>。 这些类都继承自<xref:System.Drawing.Brush>类。 下图显示用纯色画笔填充的矩形和椭圆用阴影画笔填充。  
  
 ![填充形状](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.gif "Aboutgdip02_art17")  
  
## <a name="solid-brushes"></a>实心画笔  
 若要填充的闭合的形状，你需要的实例<xref:System.Drawing.Graphics>类和一个<xref:System.Drawing.Brush>。 实例<xref:System.Drawing.Graphics>类提供了方法，如<xref:System.Drawing.Graphics.FillRectangle%2A>和<xref:System.Drawing.Graphics.FillEllipse%2A>，和<xref:System.Drawing.Brush>存储填充，如颜色和模式的特性。 <xref:System.Drawing.Brush>作为一个参数传递给填充方法。 下面的代码示例演示如何用红色纯色填充椭圆。  
  
 [!code-csharp[LinesCurvesAndShapes#121](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  在前面的示例中，画笔属于类型<xref:System.Drawing.SolidBrush>，它继承自<xref:System.Drawing.Brush>。  
  
## <a name="hatch-brushes"></a>阴影画笔  
 当使用阴影画笔填充形状时，指定前景颜色、 背景色和阴影样式。 前景色为阴影的颜色。  
  
 [!code-csharp[LinesCurvesAndShapes#122](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 提供 50 多台的阴影样式;下图中所示的三个样式<xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>， <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>，和<xref:System.Drawing.Drawing2D.HatchStyle.Cross>。  
  
 ![填充形状](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.gif "Aboutgdip02_art18")  
  
## <a name="texture-brushes"></a>纹理画笔  
 使用纹理画笔，你可以用位图中存储的图案填充形状。 例如，假设以下图片存储在名为磁盘文件`MyTexture.bmp`。  
  
 ![填充形状](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.gif "Aboutgdip02_Art19")  
  
 下面的代码示例演示如何通过重复图片存储在填充椭圆`MyTexture.bmp`。  
  
 [!code-csharp[LinesCurvesAndShapes#123](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 下图显示实心的椭圆。  
  
 ![填充形状](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.gif "AboutGdip02_Art20")  
  
## <a name="gradient-brushes"></a>渐变画刷  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 提供两种类型的渐变画刷： 线性和路径。 可以使用线性渐变画笔填充形状更改逐渐水平、 垂直移过图形或对角线方向的颜色。 下面的代码示例演示如何用从蓝绿色到移动时改变距左边缘的椭圆的右边缘的水平渐变画笔填充椭圆。  
  
 [!code-csharp[LinesCurvesAndShapes#124](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 下图显示实心的椭圆。  
  
 ![填充形状](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.gif "AboutGdip02_Art21")  
  
 路径渐变画笔可以配置为当您从边缘形状的中心移动更改颜色。  
  
 ![填充形状](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.gif "AboutGdip02_Art22")  
  
 路径渐变画刷是非常灵活。 渐变画笔用于填充逐渐从在中心的红色对每个顶点处的三种不同颜色的以下图更改中的三角形。  
  
 ![填充形状](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.gif "AboutGdip02_Art23")  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 [直线、曲线和形状](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [如何：在 Windows 窗体上绘制填充矩形](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-rectangle-on-a-windows-form.md)  
 [如何：在 Windows 窗体上绘制填充椭圆形](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-ellipse-on-a-windows-form.md)
