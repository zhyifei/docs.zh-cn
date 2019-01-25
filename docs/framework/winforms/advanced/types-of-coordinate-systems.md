---
title: 坐标系类型
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], page
- unit of measure
- world coordinate system
- page coordinate system
- page transformation
- device coordinate system
- world transformation
- coordinate systems
- transformations [Windows Forms], world
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
ms.openlocfilehash: 783e258f64633a4ddf7f3bbad858d6633256b97e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590367"
---
# <a name="types-of-coordinate-systems"></a><span data-ttu-id="78bbd-102">坐标系类型</span><span class="sxs-lookup"><span data-stu-id="78bbd-102">Types of Coordinate Systems</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="78bbd-103">使用三个坐标空间： 世界、 页和设备。</span><span class="sxs-lookup"><span data-stu-id="78bbd-103">uses three coordinate spaces: world, page, and device.</span></span> <span data-ttu-id="78bbd-104">用于建模对特定图形世界坐标世界坐标，将传递给.NET Framework 中的方法的坐标。</span><span class="sxs-lookup"><span data-stu-id="78bbd-104">World coordinates are the coordinates used to model a particular graphic world and are the coordinates you pass to methods in the .NET Framework.</span></span> <span data-ttu-id="78bbd-105">页坐标是指由绘图图面，如窗体或控件使用的坐标系统。</span><span class="sxs-lookup"><span data-stu-id="78bbd-105">Page coordinates refer to the coordinate system used by a drawing surface, such as a form or control.</span></span> <span data-ttu-id="78bbd-106">设备坐标是由物理设备上，如屏幕或纸张进行绘制的坐标。</span><span class="sxs-lookup"><span data-stu-id="78bbd-106">Device coordinates are the coordinates used by the physical device being drawn on, such as a screen or sheet of paper.</span></span> <span data-ttu-id="78bbd-107">进行调用时`myGraphics.DrawLine(myPen, 0, 0, 160, 80)`，将传递给点<xref:System.Drawing.Graphics.DrawLine%2A>方法 —`(0, 0)`和`(160, 80)`— 世界坐标空间中。</span><span class="sxs-lookup"><span data-stu-id="78bbd-107">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, the points that you pass to the <xref:System.Drawing.Graphics.DrawLine%2A> method—`(0, 0)` and `(160, 80)`—are in the world coordinate space.</span></span> <span data-ttu-id="78bbd-108">之前[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]可以在屏幕上绘制行中，通过一系列的转换传递的坐标。</span><span class="sxs-lookup"><span data-stu-id="78bbd-108">Before [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can draw the line on the screen, the coordinates pass through a sequence of transformations.</span></span> <span data-ttu-id="78bbd-109">一个转换，名为世界转换中，将世界坐标转换为页面坐标和另一个转换，调用页转换，将页面坐标转换为设备坐标。</span><span class="sxs-lookup"><span data-stu-id="78bbd-109">One transformation, called the world transformation, converts world coordinates to page coordinates, and another transformation, called the page transformation, converts page coordinates to device coordinates.</span></span>  
  
## <a name="transforms-and-coordinate-systems"></a><span data-ttu-id="78bbd-110">转换和坐标系</span><span class="sxs-lookup"><span data-stu-id="78bbd-110">Transforms and Coordinate Systems</span></span>  
 <span data-ttu-id="78bbd-111">假设你想要使用的工作区而不是左上角的正文中原点的坐标系。</span><span class="sxs-lookup"><span data-stu-id="78bbd-111">Suppose you want to work with a coordinate system that has its origin in the body of the client area rather than the upper-left corner.</span></span> <span data-ttu-id="78bbd-112">例如，假设你需要为 100 像素从工作区左边缘和从客户端区域的顶部 50 像素的原点。</span><span class="sxs-lookup"><span data-stu-id="78bbd-112">Say, for example, that you want the origin to be 100 pixels from the left edge of the client area and 50 pixels from the top of the client area.</span></span> <span data-ttu-id="78bbd-113">下图显示了这样的坐标系统。</span><span class="sxs-lookup"><span data-stu-id="78bbd-113">The following illustration shows such a coordinate system.</span></span>  
  
 <span data-ttu-id="78bbd-114">![坐标系](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art01.gif "AboutGdip05_art01")</span><span class="sxs-lookup"><span data-stu-id="78bbd-114">![Coordinate System](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art01.gif "AboutGdip05_art01")</span></span>  
  
 <span data-ttu-id="78bbd-115">进行调用时`myGraphics.DrawLine(myPen, 0, 0, 160, 80)`，获取显示在下图中的行。</span><span class="sxs-lookup"><span data-stu-id="78bbd-115">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, you get the line shown in the following illustration.</span></span>  
  
 <span data-ttu-id="78bbd-116">![Coordinate System](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art02.gif "AboutGdip05_art02")</span><span class="sxs-lookup"><span data-stu-id="78bbd-116">![Coordinate System](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art02.gif "AboutGdip05_art02")</span></span>  
  
 <span data-ttu-id="78bbd-117">您在三个坐标空间中的终结点的坐标是行的按如下所示：</span><span class="sxs-lookup"><span data-stu-id="78bbd-117">The coordinates of the endpoints of your line in the three coordinate spaces are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="78bbd-118">世界</span><span class="sxs-lookup"><span data-stu-id="78bbd-118">World</span></span>|<span data-ttu-id="78bbd-119">（0，0） 到 （160，80）</span><span class="sxs-lookup"><span data-stu-id="78bbd-119">(0, 0) to (160, 80)</span></span>|  
|<span data-ttu-id="78bbd-120">页</span><span class="sxs-lookup"><span data-stu-id="78bbd-120">Page</span></span>|<span data-ttu-id="78bbd-121">（100，50） 到 （260、 130）</span><span class="sxs-lookup"><span data-stu-id="78bbd-121">(100, 50) to (260, 130)</span></span>|  
|<span data-ttu-id="78bbd-122">设备</span><span class="sxs-lookup"><span data-stu-id="78bbd-122">Device</span></span>|<span data-ttu-id="78bbd-123">（100，50） 到 （260、 130）</span><span class="sxs-lookup"><span data-stu-id="78bbd-123">(100, 50) to (260, 130)</span></span>|  
  
 <span data-ttu-id="78bbd-124">请注意页面坐标空间的客户端区域，则左上角的原点此属性始终为这种情况。</span><span class="sxs-lookup"><span data-stu-id="78bbd-124">Note that the page coordinate space has its origin at the upper-left corner of the client area; this will always be the case.</span></span> <span data-ttu-id="78bbd-125">此外请注意，因为度量值的单位是像素，设备坐标相同的页坐标。</span><span class="sxs-lookup"><span data-stu-id="78bbd-125">Also note that because the unit of measure is the pixel, the device coordinates are the same as the page coordinates.</span></span> <span data-ttu-id="78bbd-126">如果您设置的度量单位为像素 （例如，英寸为单位） 以外，设备坐标将不同于页坐标。</span><span class="sxs-lookup"><span data-stu-id="78bbd-126">If you set the unit of measure to something other than pixels (for example, inches), then the device coordinates will be different from the page coordinates.</span></span>  
  
 <span data-ttu-id="78bbd-127">世界转换，将世界坐标映射到页坐标，会保留在<xref:System.Drawing.Graphics.Transform%2A>属性的<xref:System.Drawing.Graphics>类。</span><span class="sxs-lookup"><span data-stu-id="78bbd-127">The world transformation, which maps world coordinates to page coordinates, is held in the <xref:System.Drawing.Graphics.Transform%2A> property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="78bbd-128">在上述示例中，世界转换是沿 x 方向平移 100 个单位，50 个单位，在 y 方向。</span><span class="sxs-lookup"><span data-stu-id="78bbd-128">In the preceding example, the world transformation is a translation 100 units in the x direction and 50 units in the y direction.</span></span> <span data-ttu-id="78bbd-129">下面的示例设置的世界转换<xref:System.Drawing.Graphics>对象，然后使用该<xref:System.Drawing.Graphics>对象来绘制在上图中显示的行：</span><span class="sxs-lookup"><span data-stu-id="78bbd-129">The following example sets the world transformation of a <xref:System.Drawing.Graphics> object and then uses that <xref:System.Drawing.Graphics> object to draw the line shown in the preceding figure:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 <span data-ttu-id="78bbd-130">页转换将页坐标映射到设备坐标。</span><span class="sxs-lookup"><span data-stu-id="78bbd-130">The page transformation maps page coordinates to device coordinates.</span></span> <span data-ttu-id="78bbd-131"><xref:System.Drawing.Graphics>类提供了<xref:System.Drawing.Graphics.PageUnit%2A>和<xref:System.Drawing.Graphics.PageScale%2A>操作页转换的属性。</span><span class="sxs-lookup"><span data-stu-id="78bbd-131">The <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.PageUnit%2A> and <xref:System.Drawing.Graphics.PageScale%2A> properties for manipulating the page transformation.</span></span> <span data-ttu-id="78bbd-132"><xref:System.Drawing.Graphics>类还提供了两个只读属性，<xref:System.Drawing.Graphics.DpiX%2A>和<xref:System.Drawing.Graphics.DpiY%2A>，用于检查每英寸点数的显示设备的水平和垂直点。</span><span class="sxs-lookup"><span data-stu-id="78bbd-132">The <xref:System.Drawing.Graphics> class also provides two read-only properties, <xref:System.Drawing.Graphics.DpiX%2A> and <xref:System.Drawing.Graphics.DpiY%2A>, for examining the horizontal and vertical dots per inch of the display device.</span></span>  
  
 <span data-ttu-id="78bbd-133">可以使用<xref:System.Drawing.Graphics.PageUnit%2A>属性的<xref:System.Drawing.Graphics>类，以指定的像素以外的度量单位。</span><span class="sxs-lookup"><span data-stu-id="78bbd-133">You can use the <xref:System.Drawing.Graphics.PageUnit%2A> property of the <xref:System.Drawing.Graphics> class to specify a unit of measure other than the pixel.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78bbd-134">不能设置<xref:System.Drawing.Graphics.PageUnit%2A>属性设置为<xref:System.Drawing.GraphicsUnit.World>，因为这不是物理单元，将导致异常。</span><span class="sxs-lookup"><span data-stu-id="78bbd-134">You cannot set the <xref:System.Drawing.Graphics.PageUnit%2A> property to <xref:System.Drawing.GraphicsUnit.World>, as this is not a physical unit and will cause an exception.</span></span>  
  
 <span data-ttu-id="78bbd-135">下面的示例绘制一条线从 （0，0） 到 （2，1），其中的点 （2，1） 为 2 英寸向右和向下从点 （0，0） 的 1 英寸：</span><span class="sxs-lookup"><span data-stu-id="78bbd-135">The following example draws a line from (0, 0) to (2, 1), where the point (2, 1) is 2 inches to the right and 1 inch down from the point (0, 0):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  <span data-ttu-id="78bbd-136">如果未指定笔的宽度，在构造笔时，前面的示例将绘制一英寸宽的线条。</span><span class="sxs-lookup"><span data-stu-id="78bbd-136">If you don't specify a pen width when you construct your pen, the preceding example will draw a line that is one inch wide.</span></span> <span data-ttu-id="78bbd-137">可以在第二个参数中指定钢笔的宽度<xref:System.Drawing.Pen>构造函数：</span><span class="sxs-lookup"><span data-stu-id="78bbd-137">You can specify the pen width in the second argument to the <xref:System.Drawing.Pen> constructor:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 <span data-ttu-id="78bbd-138">如果我们假设显示设备的 96 点 / 英寸沿水平方向和垂直方向中每英寸 96 点，前面示例中的行的终结点将具有三个坐标空间中的以下坐标：</span><span class="sxs-lookup"><span data-stu-id="78bbd-138">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="78bbd-139">世界</span><span class="sxs-lookup"><span data-stu-id="78bbd-139">World</span></span>|<span data-ttu-id="78bbd-140">（0，0） 到 （2，1）</span><span class="sxs-lookup"><span data-stu-id="78bbd-140">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="78bbd-141">页</span><span class="sxs-lookup"><span data-stu-id="78bbd-141">Page</span></span>|<span data-ttu-id="78bbd-142">（0，0） 到 （2，1）</span><span class="sxs-lookup"><span data-stu-id="78bbd-142">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="78bbd-143">设备</span><span class="sxs-lookup"><span data-stu-id="78bbd-143">Device</span></span>|<span data-ttu-id="78bbd-144">(0，0，为 （192，96）</span><span class="sxs-lookup"><span data-stu-id="78bbd-144">(0, 0, to (192, 96)</span></span>|  
  
 <span data-ttu-id="78bbd-145">请注意，因为世界坐标系原点位于工作区的左上角，页面坐标与世界坐标相同。</span><span class="sxs-lookup"><span data-stu-id="78bbd-145">Note that because the origin of the world coordinate space is at the upper-left corner of the client area, the page coordinates are the same as the world coordinates.</span></span>  
  
 <span data-ttu-id="78bbd-146">你可以组合的世界和页转换，以实现各种效果。</span><span class="sxs-lookup"><span data-stu-id="78bbd-146">You can combine the world and page transformations to achieve a variety of effects.</span></span> <span data-ttu-id="78bbd-147">例如，假设你想要使用英寸作为度量单位和所需的坐标系统为 2 英寸距左边缘的工作区和从客户端区域顶部的 1/2 英寸的来源。</span><span class="sxs-lookup"><span data-stu-id="78bbd-147">For example, suppose you want to use inches as the unit of measure and you want the origin of your coordinate system to be 2 inches from the left edge of the client area and 1/2 inch from the top of the client area.</span></span> <span data-ttu-id="78bbd-148">下面的示例设置的世界和页转换<xref:System.Drawing.Graphics>对象，然后绘制行从 （0，0） 到 （2，1）：</span><span class="sxs-lookup"><span data-stu-id="78bbd-148">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object and then draws a line from (0, 0) to (2, 1):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 <span data-ttu-id="78bbd-149">下图显示的行和坐标系统。</span><span class="sxs-lookup"><span data-stu-id="78bbd-149">The following illustration shows the line and coordinate system.</span></span>  
  
 <span data-ttu-id="78bbd-150">![Coordinate System](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art03.gif "AboutGdip05_art03")</span><span class="sxs-lookup"><span data-stu-id="78bbd-150">![Coordinate System](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art03.gif "AboutGdip05_art03")</span></span>  
  
 <span data-ttu-id="78bbd-151">如果我们假设显示设备的 96 点 / 英寸沿水平方向和垂直方向中每英寸 96 点，前面示例中的行的终结点将具有三个坐标空间中的以下坐标：</span><span class="sxs-lookup"><span data-stu-id="78bbd-151">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="78bbd-152">世界</span><span class="sxs-lookup"><span data-stu-id="78bbd-152">World</span></span>|<span data-ttu-id="78bbd-153">（0，0） 到 （2，1）</span><span class="sxs-lookup"><span data-stu-id="78bbd-153">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="78bbd-154">页</span><span class="sxs-lookup"><span data-stu-id="78bbd-154">Page</span></span>|<span data-ttu-id="78bbd-155">（2，0.5） 到 （4，1.5）</span><span class="sxs-lookup"><span data-stu-id="78bbd-155">(2, 0.5) to (4, 1.5)</span></span>|  
|<span data-ttu-id="78bbd-156">设备</span><span class="sxs-lookup"><span data-stu-id="78bbd-156">Device</span></span>|<span data-ttu-id="78bbd-157">（192，48） 到 （384，第 144）</span><span class="sxs-lookup"><span data-stu-id="78bbd-157">(192, 48) to (384, 144)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78bbd-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="78bbd-158">See also</span></span>
- [<span data-ttu-id="78bbd-159">坐标系统和转换</span><span class="sxs-lookup"><span data-stu-id="78bbd-159">Coordinate Systems and Transformations</span></span>](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)
- [<span data-ttu-id="78bbd-160">转换的矩阵表示形式</span><span class="sxs-lookup"><span data-stu-id="78bbd-160">Matrix Representation of Transformations</span></span>](../../../../docs/framework/winforms/advanced/matrix-representation-of-transformations.md)
