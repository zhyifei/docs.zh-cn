---
title: 如何：创建线性渐变
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
ms.openlocfilehash: 540b6d422be5d5c0898f019592a755258145d14d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125016"
---
# <a name="how-to-create-a-linear-gradient"></a><span data-ttu-id="a2d8f-102">如何：创建线性渐变</span><span class="sxs-lookup"><span data-stu-id="a2d8f-102">How to: Create a Linear Gradient</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="a2d8f-103">提供了水平、 垂直，和对角线线性渐变。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-103">provides horizontal, vertical, and diagonal linear gradients.</span></span> <span data-ttu-id="a2d8f-104">默认情况下，线性渐变中的颜色均匀地变化。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-104">By default, the color in a linear gradient changes uniformly.</span></span> <span data-ttu-id="a2d8f-105">以便以非均匀方式将颜色更改，但是，可以自定义线性渐变。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-105">However, you can customize a linear gradient so that the color changes in a non-uniform fashion.</span></span>  
  
 <span data-ttu-id="a2d8f-106">下面的示例填充直线、 椭圆和水平线性渐变画笔的矩形。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-106">The following example fills a line, an ellipse, and a rectangle with a horizontal linear gradient brush.</span></span>  
  
 <span data-ttu-id="a2d8f-107"><xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A>构造函数接收四个参数： 两个点和两种颜色。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-107">The <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor receives four arguments: two points and two colors.</span></span> <span data-ttu-id="a2d8f-108">第一个点 （0，10） 程序与第一种颜色 （红色），并且第二个点 （200，10） 与第二种颜色 （蓝色） 相关联。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-108">The first point (0, 10) is associated with the first color (red), and the second point (200, 10) is associated with the second color (blue).</span></span> <span data-ttu-id="a2d8f-109">如您所料的从绘制的线条 （0，10） 到 （200，10） 由红色变为蓝色逐渐更改。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-109">As you would expect, the line drawn from (0, 10) to (200, 10) changes gradually from red to blue.</span></span>  
  
 <span data-ttu-id="a2d8f-110">中的点 （50，10） 和 （200，10） 10 秒并不重要。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-110">The 10s in the points (50, 10) and (200, 10) are not important.</span></span> <span data-ttu-id="a2d8f-111">重要的是，两个点的第二个坐标相同 — 连接二者的线是水平。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-111">What is important is that the two points have the same second coordinate — the line connecting them is horizontal.</span></span> <span data-ttu-id="a2d8f-112">椭圆和矩形也逐渐更改由红色变为蓝色因为是由从 0 到 200 的水平坐标。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-112">The ellipse and the rectangle also change gradually from red to blue as the horizontal coordinate goes from 0 to 200.</span></span>  
  
 <span data-ttu-id="a2d8f-113">下图显示线条、 椭圆和矩形。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-113">The following illustration shows the line, the ellipse, and the rectangle.</span></span> <span data-ttu-id="a2d8f-114">请注意，图的颜色渐变本身可根据重复的水平坐标增加到 200 以上。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-114">Note that the color gradient repeats itself as the horizontal coordinate increases beyond 200.</span></span>  
  
 <span data-ttu-id="a2d8f-115">![线性渐变](./media/cslineargradient1.png "cslineargradient1")</span><span class="sxs-lookup"><span data-stu-id="a2d8f-115">![Linear Gradient](./media/cslineargradient1.png "cslineargradient1")</span></span>  
  
### <a name="to-use-horizontal-linear-gradients"></a><span data-ttu-id="a2d8f-116">若要使用水平线性渐变</span><span class="sxs-lookup"><span data-stu-id="a2d8f-116">To use horizontal linear gradients</span></span>  
  
-   <span data-ttu-id="a2d8f-117">将不透明红色和不透明蓝色分别作为第三个和第四个参数传递。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-117">Pass in the opaque red and opaque blue as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 <span data-ttu-id="a2d8f-118">在前面的示例中，颜色组件以线性方式更改为 0 的水平坐标从移动到 200 的水平坐标。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-118">In the preceding example, the color components change linearly as you move from a horizontal coordinate of 0 to a horizontal coordinate of 200.</span></span> <span data-ttu-id="a2d8f-119">例如，其第一个坐标是 0 到 200 之间的中间位置的点将有一个介于 0 和 255 之间的中间位置的蓝色组件。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-119">For example, a point whose first coordinate is halfway between 0 and 200 will have a blue component that is halfway between 0 and 255.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="a2d8f-120">可以调整一种颜色在某条边的渐变的其他不同的方式。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-120">allows you to adjust the way a color varies from one edge of a gradient to the other.</span></span> <span data-ttu-id="a2d8f-121">假设你想要创建从黑色更改为根据下表的红色渐变画笔。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-121">Suppose you want to create a gradient brush that changes from black to red according to the following table.</span></span>  
  
|<span data-ttu-id="a2d8f-122">水平坐标</span><span class="sxs-lookup"><span data-stu-id="a2d8f-122">Horizontal coordinate</span></span>|<span data-ttu-id="a2d8f-123">RGB 组件</span><span class="sxs-lookup"><span data-stu-id="a2d8f-123">RGB components</span></span>|  
|---------------------------|--------------------|  
|<span data-ttu-id="a2d8f-124">0</span><span class="sxs-lookup"><span data-stu-id="a2d8f-124">0</span></span>|<span data-ttu-id="a2d8f-125">(0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="a2d8f-125">(0, 0, 0)</span></span>|  
|<span data-ttu-id="a2d8f-126">40</span><span class="sxs-lookup"><span data-stu-id="a2d8f-126">40</span></span>|<span data-ttu-id="a2d8f-127">(128, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="a2d8f-127">(128, 0, 0)</span></span>|  
|<span data-ttu-id="a2d8f-128">200</span><span class="sxs-lookup"><span data-stu-id="a2d8f-128">200</span></span>|<span data-ttu-id="a2d8f-129">(255, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="a2d8f-129">(255, 0, 0)</span></span>|  
  
 <span data-ttu-id="a2d8f-130">请注意，红色组件以半强度时，水平坐标是只有 20%的从 0 到 200 的方法。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-130">Note that the red component is at half intensity when the horizontal coordinate is only 20 percent of the way from 0 to 200.</span></span>  
  
 <span data-ttu-id="a2d8f-131">下面的示例设置<xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A>属性的<xref:System.Drawing.Drawing2D.LinearGradientBrush>将三个相对亮度与三个相对位置相关联的对象。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-131">The following example sets the <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> property of a <xref:System.Drawing.Drawing2D.LinearGradientBrush> object to associate three relative intensities with three relative positions.</span></span> <span data-ttu-id="a2d8f-132">如前面的表中所示相对强度是 0.5 的与 0.2 的相对位置相关联。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-132">As in the preceding table, a relative intensity of 0.5 is associated with a relative position of 0.2.</span></span> <span data-ttu-id="a2d8f-133">该代码填充椭圆和矩形使用渐变画笔。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-133">The code fills an ellipse and a rectangle with the gradient brush.</span></span>  
  
 <span data-ttu-id="a2d8f-134">下图显示得到的椭圆和矩形。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-134">The following illustration shows the resulting ellipse and rectangle.</span></span>  
  
 <span data-ttu-id="a2d8f-135">![线性渐变](./media/cslineargradient2.png "cslineargradient2")</span><span class="sxs-lookup"><span data-stu-id="a2d8f-135">![Linear Gradient](./media/cslineargradient2.png "cslineargradient2")</span></span>  
  
### <a name="to-customize-linear-gradients"></a><span data-ttu-id="a2d8f-136">若要自定义线性渐变</span><span class="sxs-lookup"><span data-stu-id="a2d8f-136">To customize linear gradients</span></span>  
  
-   <span data-ttu-id="a2d8f-137">将不透明的黑色和不透明红色分别作为第三个和第四个参数传递。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-137">Pass in the opaque black and opaque red as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 <span data-ttu-id="a2d8f-138">在上述示例中的渐变的方向是水平;也就是说，颜色逐渐变化沿任意水平行移动。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-138">The gradients in the preceding examples have been horizontal; that is, the color changes gradually as you move along any horizontal line.</span></span> <span data-ttu-id="a2d8f-139">此外可以定义垂直渐变和对角线渐变。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-139">You can also define vertical gradients and diagonal gradients.</span></span>  
  
 <span data-ttu-id="a2d8f-140">下面的示例将点 （0，0） 和 （200，100） 传递给<xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A>构造函数。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-140">The following example passes the points (0, 0) and (200, 100) to a <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="a2d8f-141">与之关联的颜色蓝色 （0，0），并与之关联的绿色 （200，100）。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-141">The color blue is associated with (0, 0), and the color green is associated with (200, 100).</span></span> <span data-ttu-id="a2d8f-142">使用线性渐变画笔填充行 （使用笔宽度为 10） 和一个椭圆。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-142">A line (with pen width 10) and an ellipse are filled with the linear gradient brush.</span></span>  
  
 <span data-ttu-id="a2d8f-143">下图显示了在行和椭圆。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-143">The following illustration shows the line and the ellipse.</span></span> <span data-ttu-id="a2d8f-144">请注意，在椭圆更改颜色逐渐沿任意移动行的是并行的行通过传递到 （0，0） 和 （200，100）。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-144">Note that the color in the ellipse changes gradually as you move along any line that is parallel to the line passing through (0, 0) and (200, 100).</span></span>  
  
 <span data-ttu-id="a2d8f-145">![线性渐变](./media/cslineargradient3.png "cslineargradient3")</span><span class="sxs-lookup"><span data-stu-id="a2d8f-145">![Linear Gradient](./media/cslineargradient3.png "cslineargradient3")</span></span>  
  
### <a name="to-create-diagonal-linear-gradients"></a><span data-ttu-id="a2d8f-146">若要创建对角线线性渐变</span><span class="sxs-lookup"><span data-stu-id="a2d8f-146">To create diagonal linear gradients</span></span>  
  
-   <span data-ttu-id="a2d8f-147">传入的不透明的蓝色和不透明绿色作为第三个和第四个参数，分别。</span><span class="sxs-lookup"><span data-stu-id="a2d8f-147">Pass in the opaque blue and opaque green as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="a2d8f-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2d8f-148">See also</span></span>

- [<span data-ttu-id="a2d8f-149">使用渐变画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="a2d8f-149">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
- [<span data-ttu-id="a2d8f-150">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="a2d8f-150">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
