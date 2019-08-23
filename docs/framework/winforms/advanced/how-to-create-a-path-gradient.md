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
ms.openlocfilehash: 8399a56fca87704e10456a4cf8109d7c80d4db45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964407"
---
# <a name="how-to-create-a-path-gradient"></a><span data-ttu-id="73fd5-102">如何：创建路径渐变</span><span class="sxs-lookup"><span data-stu-id="73fd5-102">How to: Create a Path Gradient</span></span>
<span data-ttu-id="73fd5-103">利用<xref:System.Drawing.Drawing2D.PathGradientBrush>类, 您可以自定义使用渐变颜色填充形状的方式。</span><span class="sxs-lookup"><span data-stu-id="73fd5-103">The <xref:System.Drawing.Drawing2D.PathGradientBrush> class allows you to customize the way you fill a shape with gradually changing colors.</span></span> <span data-ttu-id="73fd5-104">例如, 可以为路径中心指定一种颜色, 并为路径边界指定另一种颜色。</span><span class="sxs-lookup"><span data-stu-id="73fd5-104">For example, you can specify one color for the center of a path and another color for the boundary of a path.</span></span> <span data-ttu-id="73fd5-105">还可以为路径边界上多个点的每个点指定单独的颜色。</span><span class="sxs-lookup"><span data-stu-id="73fd5-105">You can also specify separate colors for each of several points along the boundary of a path.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="73fd5-106">在 gdi + 中, 路径是由<xref:System.Drawing.Drawing2D.GraphicsPath>对象维护的一系列直线和曲线。</span><span class="sxs-lookup"><span data-stu-id="73fd5-106">In GDI+, a path is a sequence of lines and curves maintained by a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="73fd5-107">有关 GDI + 路径的详细信息, 请参阅[GDI + 中的图形路径](graphics-paths-in-gdi.md)和[构造和绘制路径](constructing-and-drawing-paths.md)。</span><span class="sxs-lookup"><span data-stu-id="73fd5-107">For more information about GDI+ paths, see [Graphics Paths in GDI+](graphics-paths-in-gdi.md) and [Constructing and Drawing Paths](constructing-and-drawing-paths.md).</span></span>  

<span data-ttu-id="73fd5-108">本文中的示例是从控件的<xref:System.Windows.Forms.Control.Paint>事件处理程序调用的方法。</span><span class="sxs-lookup"><span data-stu-id="73fd5-108">The examples in this article are methods that are called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a><span data-ttu-id="73fd5-109">使用路径渐变填充椭圆</span><span class="sxs-lookup"><span data-stu-id="73fd5-109">To fill an ellipse with a path gradient</span></span>  
  
- <span data-ttu-id="73fd5-110">下面的示例使用路径渐变画笔填充椭圆。</span><span class="sxs-lookup"><span data-stu-id="73fd5-110">The following example fills an ellipse with a path gradient brush.</span></span> <span data-ttu-id="73fd5-111">中心颜色设置为蓝色, 边界颜色设置为浅绿色。</span><span class="sxs-lookup"><span data-stu-id="73fd5-111">The center color is set to blue and the boundary color is set to aqua.</span></span> <span data-ttu-id="73fd5-112">下图显示了实心椭圆。</span><span class="sxs-lookup"><span data-stu-id="73fd5-112">The following illustration shows the filled ellipse.</span></span>  
  
     ![渐变路径填充椭圆。](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     <span data-ttu-id="73fd5-114">默认情况下, 路径渐变画笔不会延伸到路径边界之外。</span><span class="sxs-lookup"><span data-stu-id="73fd5-114">By default, a path gradient brush does not extend outside the boundary of the path.</span></span> <span data-ttu-id="73fd5-115">如果使用路径渐变画笔来填充超出路径边界的图形, 则不会填充路径之外的屏幕区域。</span><span class="sxs-lookup"><span data-stu-id="73fd5-115">If you use the path gradient brush to fill a figure that extends beyond the boundary of the path, the area of the screen outside the path will not be filled.</span></span>  
  
     <span data-ttu-id="73fd5-116">下图显示了将以下代码中的<xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType>调用更改为`e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`时所发生的情况:</span><span class="sxs-lookup"><span data-stu-id="73fd5-116">The following illustration shows what happens if you change the <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> call in the following code to `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`:</span></span>  
  
     ![超出路径边界的渐变路径已扩展。](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     <span data-ttu-id="73fd5-118">前面的代码示例旨在与 Windows 窗体一起使用, 并且它需要<xref:System.Windows.Forms.PaintEventArgs> e, 后者是的<xref:System.Windows.Forms.PaintEventHandler>参数。</span><span class="sxs-lookup"><span data-stu-id="73fd5-118">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs> e, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
### <a name="to-specify-points-on-the-boundary"></a><span data-ttu-id="73fd5-119">指定边界上的点</span><span class="sxs-lookup"><span data-stu-id="73fd5-119">To specify points on the boundary</span></span>  
  
- <span data-ttu-id="73fd5-120">下面的示例从星形路径构造路径渐变画笔。</span><span class="sxs-lookup"><span data-stu-id="73fd5-120">The following example constructs a path gradient brush from a star-shaped path.</span></span> <span data-ttu-id="73fd5-121">该代码设置<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A>属性, 该属性将星形质心的颜色设置为红色。</span><span class="sxs-lookup"><span data-stu-id="73fd5-121">The code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> property, which sets the color at the centroid of the star to red.</span></span> <span data-ttu-id="73fd5-122">然后, 该代码设置<xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A>属性, 以指定`points`数组中各个点的`colors`各种颜色 (存储在数组中)。</span><span class="sxs-lookup"><span data-stu-id="73fd5-122">Then the code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> property to specify various colors (stored in the `colors` array) at the individual points in the `points` array.</span></span> <span data-ttu-id="73fd5-123">最后一个代码语句用路径渐变画笔填充星形路径。</span><span class="sxs-lookup"><span data-stu-id="73fd5-123">The final code statement fills the star-shaped path with the path gradient brush.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
- <span data-ttu-id="73fd5-124">下面的示例在代码中绘制路径渐变<xref:System.Drawing.Drawing2D.GraphicsPath> , 而不包含对象。</span><span class="sxs-lookup"><span data-stu-id="73fd5-124">The following example draws a path gradient without a <xref:System.Drawing.Drawing2D.GraphicsPath> object in the code.</span></span> <span data-ttu-id="73fd5-125">该示例<xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A>中的特定构造函数接收一个点数组, 但不<xref:System.Drawing.Drawing2D.GraphicsPath>需要对象。</span><span class="sxs-lookup"><span data-stu-id="73fd5-125">The particular <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> constructor in the example receives an array of points but does not require a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="73fd5-126">另请注意<xref:System.Drawing.Drawing2D.PathGradientBrush> , 用于填充矩形, 而不是路径。</span><span class="sxs-lookup"><span data-stu-id="73fd5-126">Also, note that the <xref:System.Drawing.Drawing2D.PathGradientBrush> is used to fill a rectangle, not a path.</span></span> <span data-ttu-id="73fd5-127">该矩形大于用于定义画笔的闭合路径, 因此画笔不绘制其中的某些矩形。</span><span class="sxs-lookup"><span data-stu-id="73fd5-127">The rectangle is larger than the closed path used to define the brush, so some of the rectangle is not painted by the brush.</span></span> <span data-ttu-id="73fd5-128">下图显示了矩形 (点线) 和路径渐变画笔绘制的矩形部分:</span><span class="sxs-lookup"><span data-stu-id="73fd5-128">The following illustration shows the rectangle (dotted line) and the portion of the rectangle painted by the path gradient brush:</span></span> 
  
     ![由路径渐变画笔绘制的渐变部分。](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a><span data-ttu-id="73fd5-130">自定义路径渐变</span><span class="sxs-lookup"><span data-stu-id="73fd5-130">To customize a path gradient</span></span>  
  
- <span data-ttu-id="73fd5-131">自定义路径渐变画笔的一种方法是设置其<xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="73fd5-131">One way to customize a path gradient brush is to set its <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> property.</span></span> <span data-ttu-id="73fd5-132">焦点缩放指定位于主路径内的内部路径。</span><span class="sxs-lookup"><span data-stu-id="73fd5-132">The focus scales specify an inner path that lies inside the main path.</span></span> <span data-ttu-id="73fd5-133">中心颜色在内部路径内的任何位置显示, 而不是仅在中心点显示。</span><span class="sxs-lookup"><span data-stu-id="73fd5-133">The center color is displayed everywhere inside that inner path rather than only at the center point.</span></span>  
  
     <span data-ttu-id="73fd5-134">下面的示例基于椭圆形路径创建路径渐变画笔。</span><span class="sxs-lookup"><span data-stu-id="73fd5-134">The following example creates a path gradient brush based on an elliptical path.</span></span> <span data-ttu-id="73fd5-135">该代码将边界颜色设置为蓝色, 将中心颜色设置为浅绿色, 然后使用路径渐变画笔填充椭圆路径。</span><span class="sxs-lookup"><span data-stu-id="73fd5-135">The code sets the boundary color to blue, sets the center color to aqua, and then uses the path gradient brush to fill the elliptical path.</span></span>  
  
     <span data-ttu-id="73fd5-136">接下来, 代码设置路径渐变画笔的聚焦缩放。</span><span class="sxs-lookup"><span data-stu-id="73fd5-136">Next, the code sets the focus scales of the path gradient brush.</span></span> <span data-ttu-id="73fd5-137">X 焦点刻度设置为 0.3, 而 y 焦点刻度设置为0.8。</span><span class="sxs-lookup"><span data-stu-id="73fd5-137">The x focus scale is set to 0.3, and the y focus scale is set to 0.8.</span></span> <span data-ttu-id="73fd5-138">此代码将调用<xref:System.Drawing.Graphics.TranslateTransform%2A> <xref:System.Drawing.Graphics>对象的方法, 以便随后调用以<xref:System.Drawing.Graphics.FillPath%2A>填充位于第一个椭圆右侧的椭圆。</span><span class="sxs-lookup"><span data-stu-id="73fd5-138">The code calls the <xref:System.Drawing.Graphics.TranslateTransform%2A> method of a <xref:System.Drawing.Graphics> object so that the subsequent call to <xref:System.Drawing.Graphics.FillPath%2A> fills an ellipse that sits to the right of the first ellipse.</span></span>  
  
     <span data-ttu-id="73fd5-139">若要查看焦点刻度的效果, 请设想一个小椭圆与主椭圆共享其中心。</span><span class="sxs-lookup"><span data-stu-id="73fd5-139">To see the effect of the focus scales, imagine a small ellipse that shares its center with the main ellipse.</span></span> <span data-ttu-id="73fd5-140">小型 (内部) 椭圆是主要椭圆, 其水平方向为 0.3, 垂直方向为0.8。</span><span class="sxs-lookup"><span data-stu-id="73fd5-140">The small (inner) ellipse is the main ellipse scaled (about its center) horizontally by a factor of 0.3 and vertically by a factor of 0.8.</span></span> <span data-ttu-id="73fd5-141">从外部椭圆的边界移到内部椭圆的边界时, 颜色将从蓝色逐渐变为浅绿色。</span><span class="sxs-lookup"><span data-stu-id="73fd5-141">As you move from the boundary of the outer ellipse to the boundary of the inner ellipse, the color changes gradually from blue to aqua.</span></span> <span data-ttu-id="73fd5-142">从内部椭圆的边界移到共享中心时, 颜色将保持浅绿色。</span><span class="sxs-lookup"><span data-stu-id="73fd5-142">As you move from the boundary of the inner ellipse to the shared center, the color remains aqua.</span></span>  
  
     <span data-ttu-id="73fd5-143">下图显示以下代码的输出。</span><span class="sxs-lookup"><span data-stu-id="73fd5-143">The following illustration shows the output of the following code.</span></span> <span data-ttu-id="73fd5-144">左侧的椭圆仅在中心点处为浅绿色。</span><span class="sxs-lookup"><span data-stu-id="73fd5-144">The ellipse on the left is aqua only at the center point.</span></span> <span data-ttu-id="73fd5-145">右侧的椭圆在内部路径内的任何位置都为浅绿色。</span><span class="sxs-lookup"><span data-stu-id="73fd5-145">The ellipse on the right is aqua everywhere inside the inner path.</span></span>  
  
 ![焦点刻度的渐变效果](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a><span data-ttu-id="73fd5-147">自定义内插</span><span class="sxs-lookup"><span data-stu-id="73fd5-147">To customize with interpolation</span></span>  
  
- <span data-ttu-id="73fd5-148">自定义路径渐变画笔的另一种方法是指定插值颜色数组和内插位置数组。</span><span class="sxs-lookup"><span data-stu-id="73fd5-148">Another way to customize a path gradient brush is to specify an array of interpolation colors and an array of interpolation positions.</span></span>  
  
     <span data-ttu-id="73fd5-149">下面的示例基于三角形创建路径渐变画笔。</span><span class="sxs-lookup"><span data-stu-id="73fd5-149">The following example creates a path gradient brush based on a triangle.</span></span> <span data-ttu-id="73fd5-150">此代码将路径<xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A>渐变画笔的属性设置为指定插值色数组 (深绿色、浅绿色、蓝色) 和内插位置数组 (0, 0.25, 1)。</span><span class="sxs-lookup"><span data-stu-id="73fd5-150">The code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> property of the path gradient brush to specify an array of interpolation colors (dark green, aqua, blue) and an array of interpolation positions (0, 0.25, 1).</span></span> <span data-ttu-id="73fd5-151">从三角形的边界向中心点移动时, 颜色将从深绿色逐渐变为浅绿色, 然后从浅绿色变为蓝色。</span><span class="sxs-lookup"><span data-stu-id="73fd5-151">As you move from the boundary of the triangle to the center point, the color changes gradually from dark green to aqua and then from aqua to blue.</span></span> <span data-ttu-id="73fd5-152">从深绿色到浅绿色的更改发生在从深绿色到蓝色的距离的 25%。</span><span class="sxs-lookup"><span data-stu-id="73fd5-152">The change from dark green to aqua happens in 25 percent of the distance from dark green to blue.</span></span>  
  
     <span data-ttu-id="73fd5-153">下图显示了用自定义路径渐变画笔填充的三角形。</span><span class="sxs-lookup"><span data-stu-id="73fd5-153">The following illustration shows the triangle filled with the custom path gradient brush.</span></span>  
  
     ![用自定义路径渐变画笔填充的三角形。](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a><span data-ttu-id="73fd5-155">设置中心点</span><span class="sxs-lookup"><span data-stu-id="73fd5-155">To set the center point</span></span>  
  
- <span data-ttu-id="73fd5-156">默认情况下, 路径渐变画笔的中心点位于用于构造画笔的路径的质心上。</span><span class="sxs-lookup"><span data-stu-id="73fd5-156">By default, the center point of a path gradient brush is at the centroid of the path used to construct the brush.</span></span> <span data-ttu-id="73fd5-157">您可以通过设置<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> <xref:System.Drawing.Drawing2D.PathGradientBrush>类的属性来更改中心点的位置。</span><span class="sxs-lookup"><span data-stu-id="73fd5-157">You can change the location of the center point by setting the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> property of the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
     <span data-ttu-id="73fd5-158">下面的示例基于椭圆创建路径渐变画笔。</span><span class="sxs-lookup"><span data-stu-id="73fd5-158">The following example creates a path gradient brush based on an ellipse.</span></span> <span data-ttu-id="73fd5-159">椭圆的中心位于 (70, 35), 但路径渐变画笔的中心点设置为 (120, 40)。</span><span class="sxs-lookup"><span data-stu-id="73fd5-159">The center of the ellipse is at (70, 35), but the center point of the path gradient brush is set to (120, 40).</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     <span data-ttu-id="73fd5-160">下图显示了轨迹渐变画笔的实心椭圆和中心点:</span><span class="sxs-lookup"><span data-stu-id="73fd5-160">The following illustration shows the filled ellipse and the center point of the path gradient brush:</span></span>  
  
     ![带有填充椭圆和中心点的渐变路径。](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
- <span data-ttu-id="73fd5-162">可以将路径渐变画笔的中心点设置为用于构造画笔的路径之外的位置。</span><span class="sxs-lookup"><span data-stu-id="73fd5-162">You can set the center point of a path gradient brush to a location outside the path that was used to construct the brush.</span></span> <span data-ttu-id="73fd5-163">下面的示例将替换调用以在前面<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A>的代码中设置属性。</span><span class="sxs-lookup"><span data-stu-id="73fd5-163">The following example replaces the call to set the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> property in the preceding code.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     <span data-ttu-id="73fd5-164">下图显示了此更改的输出:</span><span class="sxs-lookup"><span data-stu-id="73fd5-164">The following illustration shows the output with this change:</span></span>  
  
     ![中心点在路径外的渐变路径。](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     <span data-ttu-id="73fd5-166">在上图中, 椭圆最右侧的点不是纯蓝色 (尽管它们非常接近)。</span><span class="sxs-lookup"><span data-stu-id="73fd5-166">In the preceding illustration, the points at the far right of the ellipse are not pure blue (although they are very close).</span></span> <span data-ttu-id="73fd5-167">渐变中的颜色的定位方式与填充已达到该点 (145, 35), 其中的颜色将为纯蓝色 (0, 0, 255)。</span><span class="sxs-lookup"><span data-stu-id="73fd5-167">The colors in the gradient are positioned as if the fill reached the point (145, 35) where the color would be pure blue (0, 0, 255).</span></span> <span data-ttu-id="73fd5-168">但填充从不达到 (145, 35), 因为路径渐变画笔仅在其路径内绘制。</span><span class="sxs-lookup"><span data-stu-id="73fd5-168">But the fill never reaches (145, 35) because a path gradient brush paints only inside its path.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="73fd5-169">编译代码</span><span class="sxs-lookup"><span data-stu-id="73fd5-169">Compiling the Code</span></span>  
 <span data-ttu-id="73fd5-170">前面的示例旨在与 Windows 窗体一起使用, 并且它们需要<xref:System.Windows.Forms.PaintEventArgs> `e`作为<xref:System.Windows.Forms.Control.Paint>事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="73fd5-170">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73fd5-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="73fd5-171">See also</span></span>

- [<span data-ttu-id="73fd5-172">使用渐变画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="73fd5-172">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
