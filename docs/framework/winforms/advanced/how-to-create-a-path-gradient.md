---
title: 如何：创建路径渐变
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- path gradients [Windows Forms], creating
- gradients [Windows Forms], creating path
- graphics paths [Windows Forms], creating gradient
ms.assetid: 1948e834-e104-481c-b71d-d8aa9e4d106e
ms.openlocfilehash: cf4dc558c008fb8adfc327a6a894a428e985df03
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182630"
---
# <a name="how-to-create-a-path-gradient"></a>如何：创建路径渐变
该<xref:System.Drawing.Drawing2D.PathGradientBrush>类允许您自定义使用逐渐更改的颜色填充形状的方式。 例如，可以为路径的中心指定一种颜色，为路径的边界指定另一种颜色。 您还可以为路径边界上的多个点指定单独的颜色。  
  
> [!NOTE]
> 在 GDI+中，路径是由<xref:System.Drawing.Drawing2D.GraphicsPath>对象维护的线和曲线序列。 有关 GDI+ 路径的详细信息，请参阅[GDI+ 中的图形路径](graphics-paths-in-gdi.md)以及[构造和绘图路径](constructing-and-drawing-paths.md)。  

本文中的示例是从控件<xref:System.Windows.Forms.Control.Paint>的事件处理程序调用的方法。  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>用路径渐变填充椭圆  
  
- 下面的示例使用路径渐变画笔填充椭圆。 中心颜色设置为蓝色，边界颜色设置为水色。 下图显示了填充的椭圆。  
  
     ![渐变路径填充椭圆。](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     默认情况下，路径渐变画笔不会扩展到路径的边界之外。 如果使用路径渐变画笔填充超出路径边界的图形，则不会填充路径外部的屏幕区域。  
  
     下图显示了如果将以下代码中的<xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType>调用更改为`e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`：  
  
     ![渐变路径超出路径的边界。](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     前面的代码示例设计用于 Windows 窗体，它要求<xref:System.Windows.Forms.PaintEventArgs>e，这是 的<xref:System.Windows.Forms.PaintEventHandler>参数。  
  
### <a name="to-specify-points-on-the-boundary"></a>指定边界上的点  
  
- 下面的示例从星形路径构造路径渐变画笔。 代码设置属性<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A>，该属性将星形的质心处的颜色设置为红色。 然后，代码设置属性<xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A>以在`points`数组中的单个点指定各种颜色`colors`（存储在数组中）。 最后的代码语句使用路径渐变画笔填充星形路径。  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
- 下面的示例绘制一个路径渐变，没有<xref:System.Drawing.Drawing2D.GraphicsPath>代码中的对象。 示例中的特定<xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A>构造函数接收点数组，但不需要<xref:System.Drawing.Drawing2D.GraphicsPath>对象。 此外，请注意，<xref:System.Drawing.Drawing2D.PathGradientBrush>用于填充矩形，而不是路径。 矩形大于用于定义画笔的封闭路径，因此某些矩形不是由画笔绘制的。 下图显示了矩形（虚线）和由路径渐变画笔绘制的矩形部分：
  
     ![由路径渐变画笔绘制的渐变部分。](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>自定义路径渐变  
  
- 自定义路径渐变画笔的一种方法是设置其<xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A>属性。 焦点比例指定位于主路径内的内路径。 中心颜色显示在该内部路径的任何地方，而不仅仅是中心点。  
  
     下面的示例基于椭圆路径创建路径渐变画笔。 代码将边界颜色设置为蓝色，将中心颜色设置为水族，然后使用路径渐变画笔填充椭圆路径。  
  
     接下来，代码设置路径渐变画笔的焦点比例。 x 焦点比例设置为 0.3，y 焦点比例设置为 0.8。 代码调用<xref:System.Drawing.Graphics.TranslateTransform%2A><xref:System.Drawing.Graphics>对象的方法，以便后续调用以<xref:System.Drawing.Graphics.FillPath%2A>填充位于第一个椭圆右侧的椭圆。  
  
     要查看焦点缩放的效果，想象一个与主椭圆共享中心的小椭圆。 小椭圆是水平缩放（大约其中心）的主椭圆，由 0.3 倍和垂直 0.8 倍数垂直缩放。 当您从外部椭圆的边界移动到内部椭圆的边界时，颜色会逐渐从蓝色变为浅绿色。 当您从内部椭圆的边界移动到共享中心时，颜色将保持浅色。  
  
     下图显示以下代码的输出。 左侧的椭圆仅在中心点处是水族。 右边的椭圆在内路内随处可见。  
  
 ![焦点尺度的渐变效果](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>使用插值进行自定义  
  
- 自定义路径渐变画笔的另一种方法是指定插值颜色数组和插值位置数组。  
  
     下面的示例基于三角形创建路径渐变画笔。 代码设置路径渐变<xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A>画笔的属性以指定插值颜色数组（深绿色、水彩、蓝色）和插值位置数组（0、0.25、1）。 当您从三角形的边界移动到中心点时，颜色逐渐从深绿色变为浅绿色，然后从浅绿色变为蓝色。 从深绿色到浅绿色的变化发生在从深绿色到蓝色25%的距离。  
  
     下图显示了使用自定义路径渐变画笔填充的三角形。  
  
     ![用自定义路径渐变画笔填充的三角形。](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>设置中心点  
  
- 默认情况下，路径渐变画笔的中心点位于用于构造画笔的路径的质心。 您可以通过设置<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A><xref:System.Drawing.Drawing2D.PathGradientBrush>类的属性来更改中心点的位置。  
  
     下面的示例基于椭圆创建路径渐变画笔。 椭圆的中心位于 （70， 35），但路径渐变画笔的中心点设置为 （120， 40）。  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     下图显示了填充椭圆和路径渐变画笔的中心点：  
  
     ![具有填充椭圆和中心点的渐变路径。](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
- 您可以将路径渐变画笔的中心点设置为用于构造画笔的路径外部的位置。 下面的示例替换调用以在前面的代码中设置<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A>属性。  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     下图显示了此更改的输出：  
  
     ![路径外部中心点的渐变路径。](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     在前面的图中，椭圆最右边的点不是纯蓝色（尽管它们非常接近）。 渐变中的颜色定位如下填充到达该点 （145， 35），其中颜色为纯蓝色 （0，0，255）。 但填充永远不会达到 （145， 35），因为路径渐变画笔只在其路径内绘制。  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例设计用于 Windows 窗体，它们需要<xref:System.Windows.Forms.PaintEventArgs>`e`，这是事件处理程序的<xref:System.Windows.Forms.Control.Paint>参数。  
  
## <a name="see-also"></a>另请参阅

- [使用渐变画笔填充形状](using-a-gradient-brush-to-fill-shapes.md)
