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
# <a name="how-to-create-a-path-gradient"></a><span data-ttu-id="8e474-102">如何：创建路径渐变</span><span class="sxs-lookup"><span data-stu-id="8e474-102">How to: Create a Path Gradient</span></span>
<span data-ttu-id="8e474-103"><xref:System.Drawing.Drawing2D.PathGradientBrush>类允许您自定义用渐变颜色填充形状的方式。</span><span class="sxs-lookup"><span data-stu-id="8e474-103">The <xref:System.Drawing.Drawing2D.PathGradientBrush> class allows you to customize the way you fill a shape with gradually changing colors.</span></span> <span data-ttu-id="8e474-104">例如，你可以指定路径的中心的一种颜色和路径的边界的另一种颜色。</span><span class="sxs-lookup"><span data-stu-id="8e474-104">For example, you can specify one color for the center of a path and another color for the boundary of a path.</span></span> <span data-ttu-id="8e474-105">此外可以为每个几个点沿边界路径的指定单独的颜色。</span><span class="sxs-lookup"><span data-stu-id="8e474-105">You can also specify separate colors for each of several points along the boundary of a path.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e474-106">在[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，路径是一系列的直线和曲线由维护<xref:System.Drawing.Drawing2D.GraphicsPath>对象。</span><span class="sxs-lookup"><span data-stu-id="8e474-106">In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], a path is a sequence of lines and curves maintained by a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="8e474-107">有关详细信息[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]路径，请参阅[GDI + 中的图形路径](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)和[Constructing 和绘制路径](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)。</span><span class="sxs-lookup"><span data-stu-id="8e474-107">For more information about [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] paths, see [Graphics Paths in GDI+](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md) and [Constructing and Drawing Paths](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md).</span></span>  
  
### <a name="to-fill-an-ellipse-with-a-path-gradient"></a><span data-ttu-id="8e474-108">若要用路径渐变填充椭圆</span><span class="sxs-lookup"><span data-stu-id="8e474-108">To fill an ellipse with a path gradient</span></span>  
  
-   <span data-ttu-id="8e474-109">下面的示例用填充椭圆路径渐变画笔。</span><span class="sxs-lookup"><span data-stu-id="8e474-109">The following example fills an ellipse with a path gradient brush.</span></span> <span data-ttu-id="8e474-110">中间颜色设置为蓝色，边界颜色设置为浅绿色。</span><span class="sxs-lookup"><span data-stu-id="8e474-110">The center color is set to blue and the boundary color is set to aqua.</span></span> <span data-ttu-id="8e474-111">下图显示实心的椭圆。</span><span class="sxs-lookup"><span data-stu-id="8e474-111">The following illustration shows the filled ellipse.</span></span>  
  
     <span data-ttu-id="8e474-112">![渐变路径](../../../../docs/framework/winforms/advanced/media/pathgradient1.png "pathgradient1")</span><span class="sxs-lookup"><span data-stu-id="8e474-112">![Gradient Path](../../../../docs/framework/winforms/advanced/media/pathgradient1.png "pathgradient1")</span></span>  
  
     <span data-ttu-id="8e474-113">默认情况下，路径渐变画笔不会扩展边界之外的路径。</span><span class="sxs-lookup"><span data-stu-id="8e474-113">By default, a path gradient brush does not extend outside the boundary of the path.</span></span> <span data-ttu-id="8e474-114">如果路径渐变画笔用于填充一个图，它超出了路径的边界，则不会填充在路径外屏幕的区域。</span><span class="sxs-lookup"><span data-stu-id="8e474-114">If you use the path gradient brush to fill a figure that extends beyond the boundary of the path, the area of the screen outside the path will not be filled.</span></span>  
  
     <span data-ttu-id="8e474-115">如果更改会发生什么情况如下图所示<xref:System.Drawing.Graphics.FillEllipse%2A>到下面的代码中调用`e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`。</span><span class="sxs-lookup"><span data-stu-id="8e474-115">The following illustration shows what happens if you change the <xref:System.Drawing.Graphics.FillEllipse%2A> call in the following code to `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`.</span></span>  
  
     <span data-ttu-id="8e474-116">![渐变路径](../../../../docs/framework/winforms/advanced/media/pathgradient2.png "pathgradient2")</span><span class="sxs-lookup"><span data-stu-id="8e474-116">![Gradient Path](../../../../docs/framework/winforms/advanced/media/pathgradient2.png "pathgradient2")</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     <span data-ttu-id="8e474-117">前面的代码示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs>e，这是参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="8e474-117">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs> e, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
### <a name="to-specify-points-on-the-boundary"></a><span data-ttu-id="8e474-118">若要指定点的边界上</span><span class="sxs-lookup"><span data-stu-id="8e474-118">To specify points on the boundary</span></span>  
  
-   <span data-ttu-id="8e474-119">下面的示例构造路径渐变画笔从星形的路径。</span><span class="sxs-lookup"><span data-stu-id="8e474-119">The following example constructs a path gradient brush from a star-shaped path.</span></span> <span data-ttu-id="8e474-120">该代码设置<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A>属性，用于设置在为红色星号的质心的颜色。</span><span class="sxs-lookup"><span data-stu-id="8e474-120">The code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> property, which sets the color at the centroid of the star to red.</span></span> <span data-ttu-id="8e474-121">然后代码集<xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A>属性来指定不同的颜色 (存储在`colors`数组) 中的各个点处`points`数组。</span><span class="sxs-lookup"><span data-stu-id="8e474-121">Then the code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> property to specify various colors (stored in the `colors` array) at the individual points in the `points` array.</span></span> <span data-ttu-id="8e474-122">最后一个代码语句填充路径渐变画笔的星形路径。</span><span class="sxs-lookup"><span data-stu-id="8e474-122">The final code statement fills the star-shaped path with the path gradient brush.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
-   <span data-ttu-id="8e474-123">下面的示例绘制路径渐变而无需<xref:System.Drawing.Drawing2D.GraphicsPath>在代码中的对象。</span><span class="sxs-lookup"><span data-stu-id="8e474-123">The following example draws a path gradient without a <xref:System.Drawing.Drawing2D.GraphicsPath> object in the code.</span></span> <span data-ttu-id="8e474-124">特定<xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A>在示例中的构造函数接收的点数组，但不需要<xref:System.Drawing.Drawing2D.GraphicsPath>对象。</span><span class="sxs-lookup"><span data-stu-id="8e474-124">The particular <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> constructor in the example receives an array of points but does not require a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="8e474-125">另请注意，<xref:System.Drawing.Drawing2D.PathGradientBrush>用来填充的矩形，而不是路径。</span><span class="sxs-lookup"><span data-stu-id="8e474-125">Also, note that the <xref:System.Drawing.Drawing2D.PathGradientBrush> is used to fill a rectangle, not a path.</span></span> <span data-ttu-id="8e474-126">矩形大于用于定义画笔，使画笔不绘制矩形的某些部分的已关闭路径。</span><span class="sxs-lookup"><span data-stu-id="8e474-126">The rectangle is larger than the closed path used to define the brush, so some of the rectangle is not painted by the brush.</span></span> <span data-ttu-id="8e474-127">下图显示矩形 （虚线） 和路径渐变画笔绘制的矩形的部分。</span><span class="sxs-lookup"><span data-stu-id="8e474-127">The following illustration shows the rectangle (dotted line) and the portion of the rectangle painted by the path gradient brush.</span></span>  
  
     <span data-ttu-id="8e474-128">![渐变](../../../../docs/framework/winforms/advanced/media/gradient4.png "gradient4")</span><span class="sxs-lookup"><span data-stu-id="8e474-128">![Gradient](../../../../docs/framework/winforms/advanced/media/gradient4.png "gradient4")</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a><span data-ttu-id="8e474-129">若要自定义路径渐变</span><span class="sxs-lookup"><span data-stu-id="8e474-129">To customize a path gradient</span></span>  
  
-   <span data-ttu-id="8e474-130">自定义路径渐变画笔的一种方法是将设置其<xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="8e474-130">One way to customize a path gradient brush is to set its <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> property.</span></span> <span data-ttu-id="8e474-131">聚焦缩放指定位于内部的主路径的内部路径。</span><span class="sxs-lookup"><span data-stu-id="8e474-131">The focus scales specify an inner path that lies inside the main path.</span></span> <span data-ttu-id="8e474-132">在内部轨迹中而不是仅在中心点无处不在显示中间颜色。</span><span class="sxs-lookup"><span data-stu-id="8e474-132">The center color is displayed everywhere inside that inner path rather than only at the center point.</span></span>  
  
     <span data-ttu-id="8e474-133">下面的示例创建路径渐变画笔基于椭圆的路径。</span><span class="sxs-lookup"><span data-stu-id="8e474-133">The following example creates a path gradient brush based on an elliptical path.</span></span> <span data-ttu-id="8e474-134">该代码设置为蓝色的边界颜色、 中间颜色设置为浅绿色，然后使用路径渐变画笔填充椭圆路径。</span><span class="sxs-lookup"><span data-stu-id="8e474-134">The code sets the boundary color to blue, sets the center color to aqua, and then uses the path gradient brush to fill the elliptical path.</span></span>  
  
     <span data-ttu-id="8e474-135">接下来，代码将设置路径渐变画笔的焦点刻度。</span><span class="sxs-lookup"><span data-stu-id="8e474-135">Next, the code sets the focus scales of the path gradient brush.</span></span> <span data-ttu-id="8e474-136">X 聚焦缩放被设置为 0.3，并且 y 焦点缩放比例设置为 0.8。</span><span class="sxs-lookup"><span data-stu-id="8e474-136">The x focus scale is set to 0.3, and the y focus scale is set to 0.8.</span></span> <span data-ttu-id="8e474-137">该代码调用<xref:System.Drawing.Graphics.TranslateTransform%2A>方法<xref:System.Drawing.Graphics>对象，以便后续调用<xref:System.Drawing.Graphics.FillPath%2A>填充椭圆位于右侧的第一个椭圆。</span><span class="sxs-lookup"><span data-stu-id="8e474-137">The code calls the <xref:System.Drawing.Graphics.TranslateTransform%2A> method of a <xref:System.Drawing.Graphics> object so that the subsequent call to <xref:System.Drawing.Graphics.FillPath%2A> fills an ellipse that sits to the right of the first ellipse.</span></span>  
  
     <span data-ttu-id="8e474-138">若要查看聚焦缩放的效果，假设与主椭圆共享其中心一个小椭圆。</span><span class="sxs-lookup"><span data-stu-id="8e474-138">To see the effect of the focus scales, imagine a small ellipse that shares its center with the main ellipse.</span></span> <span data-ttu-id="8e474-139">小型 （内部） 椭圆是 0.8 的 0.3 的主要椭圆 （围绕中心） 横向扩展倍和垂直倍。</span><span class="sxs-lookup"><span data-stu-id="8e474-139">The small (inner) ellipse is the main ellipse scaled (about its center) horizontally by a factor of 0.3 and vertically by a factor of 0.8.</span></span> <span data-ttu-id="8e474-140">当从外部的椭圆的边界移动到内部椭圆的边界时，颜色逐渐从变为蓝色浅绿色。</span><span class="sxs-lookup"><span data-stu-id="8e474-140">As you move from the boundary of the outer ellipse to the boundary of the inner ellipse, the color changes gradually from blue to aqua.</span></span> <span data-ttu-id="8e474-141">当您移动到共享的中心，颜色保持浅绿色从内部椭圆的边界。</span><span class="sxs-lookup"><span data-stu-id="8e474-141">As you move from the boundary of the inner ellipse to the shared center, the color remains aqua.</span></span>  
  
     <span data-ttu-id="8e474-142">下图显示以下代码的输出。</span><span class="sxs-lookup"><span data-stu-id="8e474-142">The following illustration shows the output of the following code.</span></span> <span data-ttu-id="8e474-143">在左侧椭圆是只能在中心点的浅绿色。</span><span class="sxs-lookup"><span data-stu-id="8e474-143">The ellipse on the left is aqua only at the center point.</span></span> <span data-ttu-id="8e474-144">在右侧的省略号为浅绿色无处不在内部路径内。</span><span class="sxs-lookup"><span data-stu-id="8e474-144">The ellipse on the right is aqua everywhere inside the inner path.</span></span>  
  
 <span data-ttu-id="8e474-145">![渐变](../../../../docs/framework/winforms/advanced/media/focusscales1nogamma.png "focusscales1NoGamma")</span><span class="sxs-lookup"><span data-stu-id="8e474-145">![Gradient](../../../../docs/framework/winforms/advanced/media/focusscales1nogamma.png "focusscales1NoGamma")</span></span>  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a><span data-ttu-id="8e474-146">使用插值自定义</span><span class="sxs-lookup"><span data-stu-id="8e474-146">To customize with interpolation</span></span>  
  
-   <span data-ttu-id="8e474-147">自定义路径渐变画笔另一种方法是指定的内插颜色数组和数组的内插位置。</span><span class="sxs-lookup"><span data-stu-id="8e474-147">Another way to customize a path gradient brush is to specify an array of interpolation colors and an array of interpolation positions.</span></span>  
  
     <span data-ttu-id="8e474-148">下面的示例创建路径渐变画笔基于一个三角形。</span><span class="sxs-lookup"><span data-stu-id="8e474-148">The following example creates a path gradient brush based on a triangle.</span></span> <span data-ttu-id="8e474-149">该代码设置<xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A>路径的渐变画笔指定内插颜色深绿色，浅绿色 （蓝色） 的数组和数组的内插位置 （0，0.25，1） 的属性。</span><span class="sxs-lookup"><span data-stu-id="8e474-149">The code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> property of the path gradient brush to specify an array of interpolation colors (dark green, aqua, blue) and an array of interpolation positions (0, 0.25, 1).</span></span> <span data-ttu-id="8e474-150">当您移动到中心点从的三角形边界的颜色更改逐渐从深绿色为浅绿色，然后从浅绿色为蓝色。</span><span class="sxs-lookup"><span data-stu-id="8e474-150">As you move from the boundary of the triangle to the center point, the color changes gradually from dark green to aqua and then from aqua to blue.</span></span> <span data-ttu-id="8e474-151">为浅绿色从深绿色更改发生在 25%的深绿色为蓝色的距离。</span><span class="sxs-lookup"><span data-stu-id="8e474-151">The change from dark green to aqua happens in 25 percent of the distance from dark green to blue.</span></span>  
  
     <span data-ttu-id="8e474-152">下图显示用自定义路径渐变画笔填充的三角形。</span><span class="sxs-lookup"><span data-stu-id="8e474-152">The following illustration shows the triangle filled with the custom path gradient brush.</span></span>  
  
     <span data-ttu-id="8e474-153">![渐变路径](../../../../docs/framework/winforms/advanced/media/pathgradient4.png "pathgradient4")</span><span class="sxs-lookup"><span data-stu-id="8e474-153">![Gradient Path](../../../../docs/framework/winforms/advanced/media/pathgradient4.png "pathgradient4")</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a><span data-ttu-id="8e474-154">若要设置的中心点</span><span class="sxs-lookup"><span data-stu-id="8e474-154">To set the center point</span></span>  
  
-   <span data-ttu-id="8e474-155">默认情况下，路径渐变画笔的中心点为中心的用来构造画笔的路径。</span><span class="sxs-lookup"><span data-stu-id="8e474-155">By default, the center point of a path gradient brush is at the centroid of the path used to construct the brush.</span></span> <span data-ttu-id="8e474-156">你可以通过设置更改的中心点的位置<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A>属性<xref:System.Drawing.Drawing2D.PathGradientBrush>类。</span><span class="sxs-lookup"><span data-stu-id="8e474-156">You can change the location of the center point by setting the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> property of the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
     <span data-ttu-id="8e474-157">下面的示例创建路径渐变画笔基于椭圆。</span><span class="sxs-lookup"><span data-stu-id="8e474-157">The following example creates a path gradient brush based on an ellipse.</span></span> <span data-ttu-id="8e474-158">椭圆的中心位于 70 (35），但路径渐变画笔的中心点设置为 120 (40）。</span><span class="sxs-lookup"><span data-stu-id="8e474-158">The center of the ellipse is at (70, 35), but the center point of the path gradient brush is set to (120, 40).</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     <span data-ttu-id="8e474-159">下图显示实心的椭圆和路径渐变画笔的中心点。</span><span class="sxs-lookup"><span data-stu-id="8e474-159">The following illustration shows the filled ellipse and the center point of the path gradient brush.</span></span>  
  
     <span data-ttu-id="8e474-160">![渐变路径](../../../../docs/framework/winforms/advanced/media/pathgradient5.png "pathgradient5")</span><span class="sxs-lookup"><span data-stu-id="8e474-160">![Gradient Path](../../../../docs/framework/winforms/advanced/media/pathgradient5.png "pathgradient5")</span></span>  
  
-   <span data-ttu-id="8e474-161">可以将路径渐变画笔的中心点设置为用于构造画笔的路径之外的位置。</span><span class="sxs-lookup"><span data-stu-id="8e474-161">You can set the center point of a path gradient brush to a location outside the path that was used to construct the brush.</span></span> <span data-ttu-id="8e474-162">下面的示例替换用于设置的调用<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A>在前面的代码的属性。</span><span class="sxs-lookup"><span data-stu-id="8e474-162">The following example replaces the call to set the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> property in the preceding code.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     <span data-ttu-id="8e474-163">下图显示进行此更改后的输出。</span><span class="sxs-lookup"><span data-stu-id="8e474-163">The following illustration shows the output with this change.</span></span>  
  
     <span data-ttu-id="8e474-164">![渐变路径](../../../../docs/framework/winforms/advanced/media/pathgradient6.png "pathgradient6")</span><span class="sxs-lookup"><span data-stu-id="8e474-164">![Gradient Path](../../../../docs/framework/winforms/advanced/media/pathgradient6.png "pathgradient6")</span></span>  
  
     <span data-ttu-id="8e474-165">在上图中，在最右侧的点的椭圆不是纯蓝色 （尽管它们是非常接近）。</span><span class="sxs-lookup"><span data-stu-id="8e474-165">In the preceding illustration, the points at the far right of the ellipse are not pure blue (although they are very close).</span></span> <span data-ttu-id="8e474-166">渐变中的颜色位于就像是填充到颜色将纯蓝色 （0、 0、 255） 的点 （145，35）。</span><span class="sxs-lookup"><span data-stu-id="8e474-166">The colors in the gradient are positioned as if the fill reached the point (145, 35) where the color would be pure blue (0, 0, 255).</span></span> <span data-ttu-id="8e474-167">但并未填充到 （145，35） 因为路径渐变画笔绘制仅在其路径内。</span><span class="sxs-lookup"><span data-stu-id="8e474-167">But the fill never reaches (145, 35) because a path gradient brush paints only inside its path.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8e474-168">编译代码</span><span class="sxs-lookup"><span data-stu-id="8e474-168">Compiling the Code</span></span>  
 <span data-ttu-id="8e474-169">前面的示例专用于 Windows 窗体，并且它们要求<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="8e474-169">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e474-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e474-170">See Also</span></span>  
 [<span data-ttu-id="8e474-171">使用渐变画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="8e474-171">Using a Gradient Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)
