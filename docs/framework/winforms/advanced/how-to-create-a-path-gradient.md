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
# <a name="how-to-create-a-path-gradient"></a><span data-ttu-id="17a61-102">如何：创建路径渐变</span><span class="sxs-lookup"><span data-stu-id="17a61-102">How to: Create a Path Gradient</span></span>
<span data-ttu-id="17a61-103">该<xref:System.Drawing.Drawing2D.PathGradientBrush>类允许您自定义使用逐渐更改的颜色填充形状的方式。</span><span class="sxs-lookup"><span data-stu-id="17a61-103">The <xref:System.Drawing.Drawing2D.PathGradientBrush> class allows you to customize the way you fill a shape with gradually changing colors.</span></span> <span data-ttu-id="17a61-104">例如，可以为路径的中心指定一种颜色，为路径的边界指定另一种颜色。</span><span class="sxs-lookup"><span data-stu-id="17a61-104">For example, you can specify one color for the center of a path and another color for the boundary of a path.</span></span> <span data-ttu-id="17a61-105">您还可以为路径边界上的多个点指定单独的颜色。</span><span class="sxs-lookup"><span data-stu-id="17a61-105">You can also specify separate colors for each of several points along the boundary of a path.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="17a61-106">在 GDI+中，路径是由<xref:System.Drawing.Drawing2D.GraphicsPath>对象维护的线和曲线序列。</span><span class="sxs-lookup"><span data-stu-id="17a61-106">In GDI+, a path is a sequence of lines and curves maintained by a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="17a61-107">有关 GDI+ 路径的详细信息，请参阅[GDI+ 中的图形路径](graphics-paths-in-gdi.md)以及[构造和绘图路径](constructing-and-drawing-paths.md)。</span><span class="sxs-lookup"><span data-stu-id="17a61-107">For more information about GDI+ paths, see [Graphics Paths in GDI+](graphics-paths-in-gdi.md) and [Constructing and Drawing Paths](constructing-and-drawing-paths.md).</span></span>  

<span data-ttu-id="17a61-108">本文中的示例是从控件<xref:System.Windows.Forms.Control.Paint>的事件处理程序调用的方法。</span><span class="sxs-lookup"><span data-stu-id="17a61-108">The examples in this article are methods that are called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a><span data-ttu-id="17a61-109">用路径渐变填充椭圆</span><span class="sxs-lookup"><span data-stu-id="17a61-109">To fill an ellipse with a path gradient</span></span>  
  
- <span data-ttu-id="17a61-110">下面的示例使用路径渐变画笔填充椭圆。</span><span class="sxs-lookup"><span data-stu-id="17a61-110">The following example fills an ellipse with a path gradient brush.</span></span> <span data-ttu-id="17a61-111">中心颜色设置为蓝色，边界颜色设置为水色。</span><span class="sxs-lookup"><span data-stu-id="17a61-111">The center color is set to blue and the boundary color is set to aqua.</span></span> <span data-ttu-id="17a61-112">下图显示了填充的椭圆。</span><span class="sxs-lookup"><span data-stu-id="17a61-112">The following illustration shows the filled ellipse.</span></span>  
  
     ![渐变路径填充椭圆。](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     <span data-ttu-id="17a61-114">默认情况下，路径渐变画笔不会扩展到路径的边界之外。</span><span class="sxs-lookup"><span data-stu-id="17a61-114">By default, a path gradient brush does not extend outside the boundary of the path.</span></span> <span data-ttu-id="17a61-115">如果使用路径渐变画笔填充超出路径边界的图形，则不会填充路径外部的屏幕区域。</span><span class="sxs-lookup"><span data-stu-id="17a61-115">If you use the path gradient brush to fill a figure that extends beyond the boundary of the path, the area of the screen outside the path will not be filled.</span></span>  
  
     <span data-ttu-id="17a61-116">下图显示了如果将以下代码中的<xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType>调用更改为`e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`：</span><span class="sxs-lookup"><span data-stu-id="17a61-116">The following illustration shows what happens if you change the <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> call in the following code to `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`:</span></span>  
  
     ![渐变路径超出路径的边界。](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     <span data-ttu-id="17a61-118">前面的代码示例设计用于 Windows 窗体，它要求<xref:System.Windows.Forms.PaintEventArgs>e，这是 的<xref:System.Windows.Forms.PaintEventHandler>参数。</span><span class="sxs-lookup"><span data-stu-id="17a61-118">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs> e, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
### <a name="to-specify-points-on-the-boundary"></a><span data-ttu-id="17a61-119">指定边界上的点</span><span class="sxs-lookup"><span data-stu-id="17a61-119">To specify points on the boundary</span></span>  
  
- <span data-ttu-id="17a61-120">下面的示例从星形路径构造路径渐变画笔。</span><span class="sxs-lookup"><span data-stu-id="17a61-120">The following example constructs a path gradient brush from a star-shaped path.</span></span> <span data-ttu-id="17a61-121">代码设置属性<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A>，该属性将星形的质心处的颜色设置为红色。</span><span class="sxs-lookup"><span data-stu-id="17a61-121">The code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> property, which sets the color at the centroid of the star to red.</span></span> <span data-ttu-id="17a61-122">然后，代码设置属性<xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A>以在`points`数组中的单个点指定各种颜色`colors`（存储在数组中）。</span><span class="sxs-lookup"><span data-stu-id="17a61-122">Then the code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> property to specify various colors (stored in the `colors` array) at the individual points in the `points` array.</span></span> <span data-ttu-id="17a61-123">最后的代码语句使用路径渐变画笔填充星形路径。</span><span class="sxs-lookup"><span data-stu-id="17a61-123">The final code statement fills the star-shaped path with the path gradient brush.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
- <span data-ttu-id="17a61-124">下面的示例绘制一个路径渐变，没有<xref:System.Drawing.Drawing2D.GraphicsPath>代码中的对象。</span><span class="sxs-lookup"><span data-stu-id="17a61-124">The following example draws a path gradient without a <xref:System.Drawing.Drawing2D.GraphicsPath> object in the code.</span></span> <span data-ttu-id="17a61-125">示例中的特定<xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A>构造函数接收点数组，但不需要<xref:System.Drawing.Drawing2D.GraphicsPath>对象。</span><span class="sxs-lookup"><span data-stu-id="17a61-125">The particular <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> constructor in the example receives an array of points but does not require a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="17a61-126">此外，请注意，<xref:System.Drawing.Drawing2D.PathGradientBrush>用于填充矩形，而不是路径。</span><span class="sxs-lookup"><span data-stu-id="17a61-126">Also, note that the <xref:System.Drawing.Drawing2D.PathGradientBrush> is used to fill a rectangle, not a path.</span></span> <span data-ttu-id="17a61-127">矩形大于用于定义画笔的封闭路径，因此某些矩形不是由画笔绘制的。</span><span class="sxs-lookup"><span data-stu-id="17a61-127">The rectangle is larger than the closed path used to define the brush, so some of the rectangle is not painted by the brush.</span></span> <span data-ttu-id="17a61-128">下图显示了矩形（虚线）和由路径渐变画笔绘制的矩形部分：</span><span class="sxs-lookup"><span data-stu-id="17a61-128">The following illustration shows the rectangle (dotted line) and the portion of the rectangle painted by the path gradient brush:</span></span>
  
     ![由路径渐变画笔绘制的渐变部分。](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a><span data-ttu-id="17a61-130">自定义路径渐变</span><span class="sxs-lookup"><span data-stu-id="17a61-130">To customize a path gradient</span></span>  
  
- <span data-ttu-id="17a61-131">自定义路径渐变画笔的一种方法是设置其<xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="17a61-131">One way to customize a path gradient brush is to set its <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> property.</span></span> <span data-ttu-id="17a61-132">焦点比例指定位于主路径内的内路径。</span><span class="sxs-lookup"><span data-stu-id="17a61-132">The focus scales specify an inner path that lies inside the main path.</span></span> <span data-ttu-id="17a61-133">中心颜色显示在该内部路径的任何地方，而不仅仅是中心点。</span><span class="sxs-lookup"><span data-stu-id="17a61-133">The center color is displayed everywhere inside that inner path rather than only at the center point.</span></span>  
  
     <span data-ttu-id="17a61-134">下面的示例基于椭圆路径创建路径渐变画笔。</span><span class="sxs-lookup"><span data-stu-id="17a61-134">The following example creates a path gradient brush based on an elliptical path.</span></span> <span data-ttu-id="17a61-135">代码将边界颜色设置为蓝色，将中心颜色设置为水族，然后使用路径渐变画笔填充椭圆路径。</span><span class="sxs-lookup"><span data-stu-id="17a61-135">The code sets the boundary color to blue, sets the center color to aqua, and then uses the path gradient brush to fill the elliptical path.</span></span>  
  
     <span data-ttu-id="17a61-136">接下来，代码设置路径渐变画笔的焦点比例。</span><span class="sxs-lookup"><span data-stu-id="17a61-136">Next, the code sets the focus scales of the path gradient brush.</span></span> <span data-ttu-id="17a61-137">x 焦点比例设置为 0.3，y 焦点比例设置为 0.8。</span><span class="sxs-lookup"><span data-stu-id="17a61-137">The x focus scale is set to 0.3, and the y focus scale is set to 0.8.</span></span> <span data-ttu-id="17a61-138">代码调用<xref:System.Drawing.Graphics.TranslateTransform%2A><xref:System.Drawing.Graphics>对象的方法，以便后续调用以<xref:System.Drawing.Graphics.FillPath%2A>填充位于第一个椭圆右侧的椭圆。</span><span class="sxs-lookup"><span data-stu-id="17a61-138">The code calls the <xref:System.Drawing.Graphics.TranslateTransform%2A> method of a <xref:System.Drawing.Graphics> object so that the subsequent call to <xref:System.Drawing.Graphics.FillPath%2A> fills an ellipse that sits to the right of the first ellipse.</span></span>  
  
     <span data-ttu-id="17a61-139">要查看焦点缩放的效果，想象一个与主椭圆共享中心的小椭圆。</span><span class="sxs-lookup"><span data-stu-id="17a61-139">To see the effect of the focus scales, imagine a small ellipse that shares its center with the main ellipse.</span></span> <span data-ttu-id="17a61-140">小椭圆是水平缩放（大约其中心）的主椭圆，由 0.3 倍和垂直 0.8 倍数垂直缩放。</span><span class="sxs-lookup"><span data-stu-id="17a61-140">The small (inner) ellipse is the main ellipse scaled (about its center) horizontally by a factor of 0.3 and vertically by a factor of 0.8.</span></span> <span data-ttu-id="17a61-141">当您从外部椭圆的边界移动到内部椭圆的边界时，颜色会逐渐从蓝色变为浅绿色。</span><span class="sxs-lookup"><span data-stu-id="17a61-141">As you move from the boundary of the outer ellipse to the boundary of the inner ellipse, the color changes gradually from blue to aqua.</span></span> <span data-ttu-id="17a61-142">当您从内部椭圆的边界移动到共享中心时，颜色将保持浅色。</span><span class="sxs-lookup"><span data-stu-id="17a61-142">As you move from the boundary of the inner ellipse to the shared center, the color remains aqua.</span></span>  
  
     <span data-ttu-id="17a61-143">下图显示以下代码的输出。</span><span class="sxs-lookup"><span data-stu-id="17a61-143">The following illustration shows the output of the following code.</span></span> <span data-ttu-id="17a61-144">左侧的椭圆仅在中心点处是水族。</span><span class="sxs-lookup"><span data-stu-id="17a61-144">The ellipse on the left is aqua only at the center point.</span></span> <span data-ttu-id="17a61-145">右边的椭圆在内路内随处可见。</span><span class="sxs-lookup"><span data-stu-id="17a61-145">The ellipse on the right is aqua everywhere inside the inner path.</span></span>  
  
 ![焦点尺度的渐变效果](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a><span data-ttu-id="17a61-147">使用插值进行自定义</span><span class="sxs-lookup"><span data-stu-id="17a61-147">To customize with interpolation</span></span>  
  
- <span data-ttu-id="17a61-148">自定义路径渐变画笔的另一种方法是指定插值颜色数组和插值位置数组。</span><span class="sxs-lookup"><span data-stu-id="17a61-148">Another way to customize a path gradient brush is to specify an array of interpolation colors and an array of interpolation positions.</span></span>  
  
     <span data-ttu-id="17a61-149">下面的示例基于三角形创建路径渐变画笔。</span><span class="sxs-lookup"><span data-stu-id="17a61-149">The following example creates a path gradient brush based on a triangle.</span></span> <span data-ttu-id="17a61-150">代码设置路径渐变<xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A>画笔的属性以指定插值颜色数组（深绿色、水彩、蓝色）和插值位置数组（0、0.25、1）。</span><span class="sxs-lookup"><span data-stu-id="17a61-150">The code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> property of the path gradient brush to specify an array of interpolation colors (dark green, aqua, blue) and an array of interpolation positions (0, 0.25, 1).</span></span> <span data-ttu-id="17a61-151">当您从三角形的边界移动到中心点时，颜色逐渐从深绿色变为浅绿色，然后从浅绿色变为蓝色。</span><span class="sxs-lookup"><span data-stu-id="17a61-151">As you move from the boundary of the triangle to the center point, the color changes gradually from dark green to aqua and then from aqua to blue.</span></span> <span data-ttu-id="17a61-152">从深绿色到浅绿色的变化发生在从深绿色到蓝色25%的距离。</span><span class="sxs-lookup"><span data-stu-id="17a61-152">The change from dark green to aqua happens in 25 percent of the distance from dark green to blue.</span></span>  
  
     <span data-ttu-id="17a61-153">下图显示了使用自定义路径渐变画笔填充的三角形。</span><span class="sxs-lookup"><span data-stu-id="17a61-153">The following illustration shows the triangle filled with the custom path gradient brush.</span></span>  
  
     ![用自定义路径渐变画笔填充的三角形。](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a><span data-ttu-id="17a61-155">设置中心点</span><span class="sxs-lookup"><span data-stu-id="17a61-155">To set the center point</span></span>  
  
- <span data-ttu-id="17a61-156">默认情况下，路径渐变画笔的中心点位于用于构造画笔的路径的质心。</span><span class="sxs-lookup"><span data-stu-id="17a61-156">By default, the center point of a path gradient brush is at the centroid of the path used to construct the brush.</span></span> <span data-ttu-id="17a61-157">您可以通过设置<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A><xref:System.Drawing.Drawing2D.PathGradientBrush>类的属性来更改中心点的位置。</span><span class="sxs-lookup"><span data-stu-id="17a61-157">You can change the location of the center point by setting the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> property of the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
     <span data-ttu-id="17a61-158">下面的示例基于椭圆创建路径渐变画笔。</span><span class="sxs-lookup"><span data-stu-id="17a61-158">The following example creates a path gradient brush based on an ellipse.</span></span> <span data-ttu-id="17a61-159">椭圆的中心位于 （70， 35），但路径渐变画笔的中心点设置为 （120， 40）。</span><span class="sxs-lookup"><span data-stu-id="17a61-159">The center of the ellipse is at (70, 35), but the center point of the path gradient brush is set to (120, 40).</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     <span data-ttu-id="17a61-160">下图显示了填充椭圆和路径渐变画笔的中心点：</span><span class="sxs-lookup"><span data-stu-id="17a61-160">The following illustration shows the filled ellipse and the center point of the path gradient brush:</span></span>  
  
     ![具有填充椭圆和中心点的渐变路径。](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
- <span data-ttu-id="17a61-162">您可以将路径渐变画笔的中心点设置为用于构造画笔的路径外部的位置。</span><span class="sxs-lookup"><span data-stu-id="17a61-162">You can set the center point of a path gradient brush to a location outside the path that was used to construct the brush.</span></span> <span data-ttu-id="17a61-163">下面的示例替换调用以在前面的代码中设置<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="17a61-163">The following example replaces the call to set the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> property in the preceding code.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     <span data-ttu-id="17a61-164">下图显示了此更改的输出：</span><span class="sxs-lookup"><span data-stu-id="17a61-164">The following illustration shows the output with this change:</span></span>  
  
     ![路径外部中心点的渐变路径。](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     <span data-ttu-id="17a61-166">在前面的图中，椭圆最右边的点不是纯蓝色（尽管它们非常接近）。</span><span class="sxs-lookup"><span data-stu-id="17a61-166">In the preceding illustration, the points at the far right of the ellipse are not pure blue (although they are very close).</span></span> <span data-ttu-id="17a61-167">渐变中的颜色定位如下填充到达该点 （145， 35），其中颜色为纯蓝色 （0，0，255）。</span><span class="sxs-lookup"><span data-stu-id="17a61-167">The colors in the gradient are positioned as if the fill reached the point (145, 35) where the color would be pure blue (0, 0, 255).</span></span> <span data-ttu-id="17a61-168">但填充永远不会达到 （145， 35），因为路径渐变画笔只在其路径内绘制。</span><span class="sxs-lookup"><span data-stu-id="17a61-168">But the fill never reaches (145, 35) because a path gradient brush paints only inside its path.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="17a61-169">编译代码</span><span class="sxs-lookup"><span data-stu-id="17a61-169">Compiling the Code</span></span>  
 <span data-ttu-id="17a61-170">前面的示例设计用于 Windows 窗体，它们需要<xref:System.Windows.Forms.PaintEventArgs>`e`，这是事件处理程序的<xref:System.Windows.Forms.Control.Paint>参数。</span><span class="sxs-lookup"><span data-stu-id="17a61-170">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17a61-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17a61-171">See also</span></span>

- [<span data-ttu-id="17a61-172">使用渐变画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="17a61-172">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
