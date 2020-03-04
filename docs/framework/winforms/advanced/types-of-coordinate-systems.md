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
ms.openlocfilehash: bbb0d4908d4a281499336d262c653d7b72f3ccdc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159801"
---
# <a name="types-of-coordinate-systems"></a><span data-ttu-id="39ced-102">坐标系类型</span><span class="sxs-lookup"><span data-stu-id="39ced-102">Types of Coordinate Systems</span></span>
<span data-ttu-id="39ced-103">GDI + 使用三个坐标空间： "世界"、"页面" 和 "设备"。</span><span class="sxs-lookup"><span data-stu-id="39ced-103">GDI+ uses three coordinate spaces: world, page, and device.</span></span> <span data-ttu-id="39ced-104">世界坐标是用于对特定图形世界进行建模的坐标，是您传递到 .NET Framework 中的方法的坐标。</span><span class="sxs-lookup"><span data-stu-id="39ced-104">World coordinates are the coordinates used to model a particular graphic world and are the coordinates you pass to methods in the .NET Framework.</span></span> <span data-ttu-id="39ced-105">页面坐标指的是绘图图面的坐标系统，如窗体或控件。</span><span class="sxs-lookup"><span data-stu-id="39ced-105">Page coordinates refer to the coordinate system used by a drawing surface, such as a form or control.</span></span> <span data-ttu-id="39ced-106">设备坐标是在其上绘制的物理设备（如屏幕或纸张）所使用的坐标。</span><span class="sxs-lookup"><span data-stu-id="39ced-106">Device coordinates are the coordinates used by the physical device being drawn on, such as a screen or sheet of paper.</span></span> <span data-ttu-id="39ced-107">`myGraphics.DrawLine(myPen, 0, 0, 160, 80)`调用时，传递给 <xref:System.Drawing.Graphics.DrawLine%2A> 方法的点（`(0, 0)` 和 `(160, 80)`）都在世界坐标空间中。</span><span class="sxs-lookup"><span data-stu-id="39ced-107">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, the points that you pass to the <xref:System.Drawing.Graphics.DrawLine%2A> method—`(0, 0)` and `(160, 80)`—are in the world coordinate space.</span></span> <span data-ttu-id="39ced-108">在 GDI + 可以在屏幕上绘制线条之前，坐标会经过一系列转换。</span><span class="sxs-lookup"><span data-stu-id="39ced-108">Before GDI+ can draw the line on the screen, the coordinates pass through a sequence of transformations.</span></span> <span data-ttu-id="39ced-109">一种称为 "世界转换" 的转换，将世界坐标转换为页面坐标，另一个称为 "页面转换" 的转换将页面坐标转换为设备坐标。</span><span class="sxs-lookup"><span data-stu-id="39ced-109">One transformation, called the world transformation, converts world coordinates to page coordinates, and another transformation, called the page transformation, converts page coordinates to device coordinates.</span></span>  
  
## <a name="transforms-and-coordinate-systems"></a><span data-ttu-id="39ced-110">转换和协调系统</span><span class="sxs-lookup"><span data-stu-id="39ced-110">Transforms and Coordinate Systems</span></span>  
 <span data-ttu-id="39ced-111">假设您想要使用的坐标系统的原点在客户端区域的主体中，而不是左上角。</span><span class="sxs-lookup"><span data-stu-id="39ced-111">Suppose you want to work with a coordinate system that has its origin in the body of the client area rather than the upper-left corner.</span></span> <span data-ttu-id="39ced-112">例如，您希望原点为从工作区左边缘100像素，而从工作区顶部开始50像素。</span><span class="sxs-lookup"><span data-stu-id="39ced-112">Say, for example, that you want the origin to be 100 pixels from the left edge of the client area and 50 pixels from the top of the client area.</span></span> <span data-ttu-id="39ced-113">下图显示了此类坐标系统。</span><span class="sxs-lookup"><span data-stu-id="39ced-113">The following illustration shows such a coordinate system.</span></span>  
  
 <span data-ttu-id="39ced-114">![坐标系统](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span><span class="sxs-lookup"><span data-stu-id="39ced-114">![Coordinate System](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span></span>  
  
 <span data-ttu-id="39ced-115">当你 `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`调用时，你将收到下图所示的行。</span><span class="sxs-lookup"><span data-stu-id="39ced-115">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, you get the line shown in the following illustration.</span></span>  
  
 <span data-ttu-id="39ced-116">![坐标系统](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span><span class="sxs-lookup"><span data-stu-id="39ced-116">![Coordinate System](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span></span>  
  
 <span data-ttu-id="39ced-117">三个坐标空间中线条的端点坐标如下：</span><span class="sxs-lookup"><span data-stu-id="39ced-117">The coordinates of the endpoints of your line in the three coordinate spaces are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39ced-118">世界</span><span class="sxs-lookup"><span data-stu-id="39ced-118">World</span></span>|<span data-ttu-id="39ced-119">（0，0）到（160，80）</span><span class="sxs-lookup"><span data-stu-id="39ced-119">(0, 0) to (160, 80)</span></span>|  
|<span data-ttu-id="39ced-120">页面</span><span class="sxs-lookup"><span data-stu-id="39ced-120">Page</span></span>|<span data-ttu-id="39ced-121">（100，50）到（260，130）</span><span class="sxs-lookup"><span data-stu-id="39ced-121">(100, 50) to (260, 130)</span></span>|  
|<span data-ttu-id="39ced-122">设备</span><span class="sxs-lookup"><span data-stu-id="39ced-122">Device</span></span>|<span data-ttu-id="39ced-123">（100，50）到（260，130）</span><span class="sxs-lookup"><span data-stu-id="39ced-123">(100, 50) to (260, 130)</span></span>|  
  
 <span data-ttu-id="39ced-124">请注意，页面坐标空间的原点在工作区的左上角;这种情况总是如此。</span><span class="sxs-lookup"><span data-stu-id="39ced-124">Note that the page coordinate space has its origin at the upper-left corner of the client area; this will always be the case.</span></span> <span data-ttu-id="39ced-125">另请注意，由于度量单位是像素，因此设备坐标与页坐标相同。</span><span class="sxs-lookup"><span data-stu-id="39ced-125">Also note that because the unit of measure is the pixel, the device coordinates are the same as the page coordinates.</span></span> <span data-ttu-id="39ced-126">如果将度量单位设置为像素（如英寸）以外的值，则设备坐标将不同于页面坐标。</span><span class="sxs-lookup"><span data-stu-id="39ced-126">If you set the unit of measure to something other than pixels (for example, inches), then the device coordinates will be different from the page coordinates.</span></span>  
  
 <span data-ttu-id="39ced-127">将世界坐标映射到页面坐标的世界转换保存在 <xref:System.Drawing.Graphics> 类的 <xref:System.Drawing.Graphics.Transform%2A> 属性中。</span><span class="sxs-lookup"><span data-stu-id="39ced-127">The world transformation, which maps world coordinates to page coordinates, is held in the <xref:System.Drawing.Graphics.Transform%2A> property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="39ced-128">在前面的示例中，世界变换是在 x 方向上转换100单位，在 y 方向上为50单位。</span><span class="sxs-lookup"><span data-stu-id="39ced-128">In the preceding example, the world transformation is a translation 100 units in the x direction and 50 units in the y direction.</span></span> <span data-ttu-id="39ced-129">下面的示例将 <xref:System.Drawing.Graphics> 对象的世界转换设置为，然后使用该 <xref:System.Drawing.Graphics> 对象绘制上图中显示的行：</span><span class="sxs-lookup"><span data-stu-id="39ced-129">The following example sets the world transformation of a <xref:System.Drawing.Graphics> object and then uses that <xref:System.Drawing.Graphics> object to draw the line shown in the preceding figure:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 <span data-ttu-id="39ced-130">页面转换将页面坐标映射到设备坐标。</span><span class="sxs-lookup"><span data-stu-id="39ced-130">The page transformation maps page coordinates to device coordinates.</span></span> <span data-ttu-id="39ced-131"><xref:System.Drawing.Graphics> 类提供用于操作页转换的 <xref:System.Drawing.Graphics.PageUnit%2A> 和 <xref:System.Drawing.Graphics.PageScale%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="39ced-131">The <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.PageUnit%2A> and <xref:System.Drawing.Graphics.PageScale%2A> properties for manipulating the page transformation.</span></span> <span data-ttu-id="39ced-132"><xref:System.Drawing.Graphics> 类还提供了两个只读属性，<xref:System.Drawing.Graphics.DpiX%2A> 和 <xref:System.Drawing.Graphics.DpiY%2A>，用于检查显示设备每英寸的水平和垂直点。</span><span class="sxs-lookup"><span data-stu-id="39ced-132">The <xref:System.Drawing.Graphics> class also provides two read-only properties, <xref:System.Drawing.Graphics.DpiX%2A> and <xref:System.Drawing.Graphics.DpiY%2A>, for examining the horizontal and vertical dots per inch of the display device.</span></span>  
  
 <span data-ttu-id="39ced-133">您可以使用 <xref:System.Drawing.Graphics> 类的 <xref:System.Drawing.Graphics.PageUnit%2A> 属性来指定除像素以外的度量单位。</span><span class="sxs-lookup"><span data-stu-id="39ced-133">You can use the <xref:System.Drawing.Graphics.PageUnit%2A> property of the <xref:System.Drawing.Graphics> class to specify a unit of measure other than the pixel.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="39ced-134">不能将 <xref:System.Drawing.Graphics.PageUnit%2A> 属性设置为 <xref:System.Drawing.GraphicsUnit.World>，因为这不是一个物理单元，将导致异常。</span><span class="sxs-lookup"><span data-stu-id="39ced-134">You cannot set the <xref:System.Drawing.Graphics.PageUnit%2A> property to <xref:System.Drawing.GraphicsUnit.World>, as this is not a physical unit and will cause an exception.</span></span>  
  
 <span data-ttu-id="39ced-135">下面的示例从（0，0）到（2，1）绘制一条直线，其中，点（2，1）从点（0，0）向下移动2英寸和1英寸：</span><span class="sxs-lookup"><span data-stu-id="39ced-135">The following example draws a line from (0, 0) to (2, 1), where the point (2, 1) is 2 inches to the right and 1 inch down from the point (0, 0):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
> <span data-ttu-id="39ced-136">如果在构造笔时未指定笔宽，则前面的示例将绘制一条宽一英寸的线条。</span><span class="sxs-lookup"><span data-stu-id="39ced-136">If you don't specify a pen width when you construct your pen, the preceding example will draw a line that is one inch wide.</span></span> <span data-ttu-id="39ced-137">可以在 <xref:System.Drawing.Pen> 构造函数的第二个参数中指定笔宽：</span><span class="sxs-lookup"><span data-stu-id="39ced-137">You can specify the pen width in the second argument to the <xref:System.Drawing.Pen> constructor:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 <span data-ttu-id="39ced-138">如果我们假定显示设备在水平方向上每英寸96点，垂直方向每英寸96点，则上一示例中线条的端点在三个坐标空间中具有以下坐标：</span><span class="sxs-lookup"><span data-stu-id="39ced-138">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39ced-139">世界</span><span class="sxs-lookup"><span data-stu-id="39ced-139">World</span></span>|<span data-ttu-id="39ced-140">（0，0）到（2，1）</span><span class="sxs-lookup"><span data-stu-id="39ced-140">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="39ced-141">页面</span><span class="sxs-lookup"><span data-stu-id="39ced-141">Page</span></span>|<span data-ttu-id="39ced-142">（0，0）到（2，1）</span><span class="sxs-lookup"><span data-stu-id="39ced-142">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="39ced-143">设备</span><span class="sxs-lookup"><span data-stu-id="39ced-143">Device</span></span>|<span data-ttu-id="39ced-144">（0，0）到（192，96）</span><span class="sxs-lookup"><span data-stu-id="39ced-144">(0, 0) to (192, 96)</span></span>|  
  
 <span data-ttu-id="39ced-145">请注意，因为世界坐标空间的原点位于工作区的左上角，所以页面坐标与世界坐标相同。</span><span class="sxs-lookup"><span data-stu-id="39ced-145">Note that because the origin of the world coordinate space is at the upper-left corner of the client area, the page coordinates are the same as the world coordinates.</span></span>  
  
 <span data-ttu-id="39ced-146">可以结合世界转换和页面转换来实现各种效果。</span><span class="sxs-lookup"><span data-stu-id="39ced-146">You can combine the world and page transformations to achieve a variety of effects.</span></span> <span data-ttu-id="39ced-147">例如，假设您想要使用英寸作为度量单位，并且您希望坐标系统的原点从工作区左边缘2英寸，从工作区顶部开始1/2 英寸。</span><span class="sxs-lookup"><span data-stu-id="39ced-147">For example, suppose you want to use inches as the unit of measure and you want the origin of your coordinate system to be 2 inches from the left edge of the client area and 1/2 inch from the top of the client area.</span></span> <span data-ttu-id="39ced-148">下面的示例设置了一个 <xref:System.Drawing.Graphics> 对象的世界转换和页面转换，然后将一条从（0，0）到（2，1）的线绘制：</span><span class="sxs-lookup"><span data-stu-id="39ced-148">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object and then draws a line from (0, 0) to (2, 1):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 <span data-ttu-id="39ced-149">下图显示了线条和坐标系统。</span><span class="sxs-lookup"><span data-stu-id="39ced-149">The following illustration shows the line and coordinate system.</span></span>  
  
 <span data-ttu-id="39ced-150">![坐标系统](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span><span class="sxs-lookup"><span data-stu-id="39ced-150">![Coordinate System](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span></span>  
  
 <span data-ttu-id="39ced-151">如果我们假定显示设备在水平方向上每英寸96点，垂直方向每英寸96点，则上一示例中线条的端点在三个坐标空间中具有以下坐标：</span><span class="sxs-lookup"><span data-stu-id="39ced-151">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39ced-152">世界</span><span class="sxs-lookup"><span data-stu-id="39ced-152">World</span></span>|<span data-ttu-id="39ced-153">（0，0）到（2，1）</span><span class="sxs-lookup"><span data-stu-id="39ced-153">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="39ced-154">页面</span><span class="sxs-lookup"><span data-stu-id="39ced-154">Page</span></span>|<span data-ttu-id="39ced-155">（2，0.5）到（4，1.5）</span><span class="sxs-lookup"><span data-stu-id="39ced-155">(2, 0.5) to (4, 1.5)</span></span>|  
|<span data-ttu-id="39ced-156">设备</span><span class="sxs-lookup"><span data-stu-id="39ced-156">Device</span></span>|<span data-ttu-id="39ced-157">（192，48）到（384，144）</span><span class="sxs-lookup"><span data-stu-id="39ced-157">(192, 48) to (384, 144)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39ced-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39ced-158">See also</span></span>

- [<span data-ttu-id="39ced-159">坐标系统和转换</span><span class="sxs-lookup"><span data-stu-id="39ced-159">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="39ced-160">转换的矩阵表示形式</span><span class="sxs-lookup"><span data-stu-id="39ced-160">Matrix Representation of Transformations</span></span>](matrix-representation-of-transformations.md)
