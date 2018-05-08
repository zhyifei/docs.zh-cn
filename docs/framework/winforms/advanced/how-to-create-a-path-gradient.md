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
ms.openlocfilehash: a3a23d382e199b7ec70a8605041f7e464d1bffe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-path-gradient"></a>如何：创建路径渐变
<xref:System.Drawing.Drawing2D.PathGradientBrush>类允许您自定义用渐变颜色填充形状的方式。 例如，你可以指定路径的中心的一种颜色和路径的边界的另一种颜色。 此外可以为每个几个点沿边界路径的指定单独的颜色。  
  
> [!NOTE]
>  在[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，路径是一系列的直线和曲线由维护<xref:System.Drawing.Drawing2D.GraphicsPath>对象。 有关详细信息[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]路径，请参阅[GDI + 中的图形路径](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)和[Constructing 和绘制路径](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)。  
  
### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>若要用路径渐变填充椭圆  
  
-   下面的示例用填充椭圆路径渐变画笔。 中间颜色设置为蓝色，边界颜色设置为浅绿色。 下图显示实心的椭圆。  
  
     ![渐变路径](../../../../docs/framework/winforms/advanced/media/pathgradient1.png "pathgradient1")  
  
     默认情况下，路径渐变画笔不会扩展边界之外的路径。 如果路径渐变画笔用于填充一个图，它超出了路径的边界，则不会填充在路径外屏幕的区域。  
  
     如果更改会发生什么情况如下图所示<xref:System.Drawing.Graphics.FillEllipse%2A>到下面的代码中调用`e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`。  
  
     ![渐变路径](../../../../docs/framework/winforms/advanced/media/pathgradient2.png "pathgradient2")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     前面的代码示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs>e，这是参数的<xref:System.Windows.Forms.PaintEventHandler>。  
  
### <a name="to-specify-points-on-the-boundary"></a>若要指定点的边界上  
  
-   下面的示例构造路径渐变画笔从星形的路径。 该代码设置<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A>属性，用于设置在为红色星号的质心的颜色。 然后代码集<xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A>属性来指定不同的颜色 (存储在`colors`数组) 中的各个点处`points`数组。 最后一个代码语句填充路径渐变画笔的星形路径。  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
-   下面的示例绘制路径渐变而无需<xref:System.Drawing.Drawing2D.GraphicsPath>在代码中的对象。 特定<xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A>在示例中的构造函数接收的点数组，但不需要<xref:System.Drawing.Drawing2D.GraphicsPath>对象。 另请注意，<xref:System.Drawing.Drawing2D.PathGradientBrush>用来填充的矩形，而不是路径。 矩形大于用于定义画笔，使画笔不绘制矩形的某些部分的已关闭路径。 下图显示矩形 （虚线） 和路径渐变画笔绘制的矩形的部分。  
  
     ![渐变](../../../../docs/framework/winforms/advanced/media/gradient4.png "gradient4")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>若要自定义路径渐变  
  
-   自定义路径渐变画笔的一种方法是将设置其<xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A>属性。 聚焦缩放指定位于内部的主路径的内部路径。 在内部轨迹中而不是仅在中心点无处不在显示中间颜色。  
  
     下面的示例创建路径渐变画笔基于椭圆的路径。 该代码设置为蓝色的边界颜色、 中间颜色设置为浅绿色，然后使用路径渐变画笔填充椭圆路径。  
  
     接下来，代码将设置路径渐变画笔的焦点刻度。 X 聚焦缩放被设置为 0.3，并且 y 焦点缩放比例设置为 0.8。 该代码调用<xref:System.Drawing.Graphics.TranslateTransform%2A>方法<xref:System.Drawing.Graphics>对象，以便后续调用<xref:System.Drawing.Graphics.FillPath%2A>填充椭圆位于右侧的第一个椭圆。  
  
     若要查看聚焦缩放的效果，假设与主椭圆共享其中心一个小椭圆。 小型 （内部） 椭圆是 0.8 的 0.3 的主要椭圆 （围绕中心） 横向扩展倍和垂直倍。 当从外部的椭圆的边界移动到内部椭圆的边界时，颜色逐渐从变为蓝色浅绿色。 当您移动到共享的中心，颜色保持浅绿色从内部椭圆的边界。  
  
     下图显示以下代码的输出。 在左侧椭圆是只能在中心点的浅绿色。 在右侧的省略号为浅绿色无处不在内部路径内。  
  
 ![渐变](../../../../docs/framework/winforms/advanced/media/focusscales1nogamma.png "focusscales1NoGamma")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>使用插值自定义  
  
-   自定义路径渐变画笔另一种方法是指定的内插颜色数组和数组的内插位置。  
  
     下面的示例创建路径渐变画笔基于一个三角形。 该代码设置<xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A>路径的渐变画笔指定内插颜色深绿色，浅绿色 （蓝色） 的数组和数组的内插位置 （0，0.25，1） 的属性。 当您移动到中心点从的三角形边界的颜色更改逐渐从深绿色为浅绿色，然后从浅绿色为蓝色。 为浅绿色从深绿色更改发生在 25%的深绿色为蓝色的距离。  
  
     下图显示用自定义路径渐变画笔填充的三角形。  
  
     ![渐变路径](../../../../docs/framework/winforms/advanced/media/pathgradient4.png "pathgradient4")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>若要设置的中心点  
  
-   默认情况下，路径渐变画笔的中心点为中心的用来构造画笔的路径。 你可以通过设置更改的中心点的位置<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A>属性<xref:System.Drawing.Drawing2D.PathGradientBrush>类。  
  
     下面的示例创建路径渐变画笔基于椭圆。 椭圆的中心位于 70 (35），但路径渐变画笔的中心点设置为 120 (40）。  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     下图显示实心的椭圆和路径渐变画笔的中心点。  
  
     ![渐变路径](../../../../docs/framework/winforms/advanced/media/pathgradient5.png "pathgradient5")  
  
-   可以将路径渐变画笔的中心点设置为用于构造画笔的路径之外的位置。 下面的示例替换用于设置的调用<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A>在前面的代码的属性。  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     下图显示进行此更改后的输出。  
  
     ![渐变路径](../../../../docs/framework/winforms/advanced/media/pathgradient6.png "pathgradient6")  
  
     在上图中，在最右侧的点的椭圆不是纯蓝色 （尽管它们是非常接近）。 渐变中的颜色位于就像是填充到颜色将纯蓝色 （0、 0、 255） 的点 （145，35）。 但并未填充到 （145，35） 因为路径渐变画笔绘制仅在其路径内。  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，并且它们要求<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。  
  
## <a name="see-also"></a>请参阅  
 [使用渐变画笔填充形状](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)
