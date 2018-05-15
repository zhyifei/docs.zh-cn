---
title: 管理 Graphics 对象的状态
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
ms.openlocfilehash: b81c3c8b25f13ac5791b5d2116b8536575f9ebcf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="managing-the-state-of-a-graphics-object"></a><span data-ttu-id="781fc-102">管理 Graphics 对象的状态</span><span class="sxs-lookup"><span data-stu-id="781fc-102">Managing the State of a Graphics Object</span></span>
<span data-ttu-id="781fc-103"><xref:System.Drawing.Graphics>类的核心是[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="781fc-103">The <xref:System.Drawing.Graphics> class is at the heart of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="781fc-104">若要绘制任何内容，你可以获取<xref:System.Drawing.Graphics>对象、 设置其属性，并调用其方法<xref:System.Drawing.Graphics.DrawLine%2A>， <xref:System.Drawing.Graphics.DrawImage%2A>， <xref:System.Drawing.Graphics.DrawString%2A>，以及类似的内容)。</span><span class="sxs-lookup"><span data-stu-id="781fc-104">To draw anything, you obtain a <xref:System.Drawing.Graphics> object, set its properties, and call its methods <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, and the like).</span></span>  
  
 <span data-ttu-id="781fc-105">下面的示例调用<xref:System.Drawing.Graphics.DrawRectangle%2A>方法<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="781fc-105">The following example calls the <xref:System.Drawing.Graphics.DrawRectangle%2A> method of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="781fc-106">第一个自变量传递给<xref:System.Drawing.Graphics.DrawRectangle%2A>方法是<xref:System.Drawing.Pen>对象。</span><span class="sxs-lookup"><span data-stu-id="781fc-106">The first argument passed to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method is a <xref:System.Drawing.Pen> object.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue) ' Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  // Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100);  
```  
  
## <a name="graphics-state"></a><span data-ttu-id="781fc-107">图形状态</span><span class="sxs-lookup"><span data-stu-id="781fc-107">Graphics State</span></span>  
 <span data-ttu-id="781fc-108">A<xref:System.Drawing.Graphics>对象不仅仅提供绘制方法，如<xref:System.Drawing.Graphics.DrawLine%2A>和<xref:System.Drawing.Graphics.DrawRectangle%2A>。</span><span class="sxs-lookup"><span data-stu-id="781fc-108">A <xref:System.Drawing.Graphics> object does more than provide drawing methods, such as <xref:System.Drawing.Graphics.DrawLine%2A> and <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span></span> <span data-ttu-id="781fc-109">A<xref:System.Drawing.Graphics>对象还维护图形状态，可以划分为以下类别：</span><span class="sxs-lookup"><span data-stu-id="781fc-109">A <xref:System.Drawing.Graphics> object also maintains graphics state, which can be divided into the following categories:</span></span>  
  
-   <span data-ttu-id="781fc-110">质量设置</span><span class="sxs-lookup"><span data-stu-id="781fc-110">Quality settings</span></span>  
  
-   <span data-ttu-id="781fc-111">转换</span><span class="sxs-lookup"><span data-stu-id="781fc-111">Transformations</span></span>  
  
-   <span data-ttu-id="781fc-112">剪辑区域</span><span class="sxs-lookup"><span data-stu-id="781fc-112">Clipping region</span></span>  
  
### <a name="quality-settings"></a><span data-ttu-id="781fc-113">质量设置</span><span class="sxs-lookup"><span data-stu-id="781fc-113">Quality Settings</span></span>  
 <span data-ttu-id="781fc-114">A<xref:System.Drawing.Graphics>对象具有多个属性影响绘制的项的质量。</span><span class="sxs-lookup"><span data-stu-id="781fc-114">A <xref:System.Drawing.Graphics> object has several properties that influence the quality of the items that are drawn.</span></span> <span data-ttu-id="781fc-115">例如，你可以设置<xref:System.Drawing.Graphics.TextRenderingHint%2A>属性指定应用于文本消除锯齿 （如果有） 的类型。</span><span class="sxs-lookup"><span data-stu-id="781fc-115">For example, you can set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property to specify the type of antialiasing (if any) applied to text.</span></span> <span data-ttu-id="781fc-116">影响质量其他属性都是<xref:System.Drawing.Graphics.SmoothingMode%2A>， <xref:System.Drawing.Graphics.CompositingMode%2A>， <xref:System.Drawing.Graphics.CompositingQuality%2A>，和<xref:System.Drawing.Graphics.InterpolationMode%2A>。</span><span class="sxs-lookup"><span data-stu-id="781fc-116">Other properties that influence quality are <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, and <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span></span>  
  
 <span data-ttu-id="781fc-117">下面的示例绘制两个椭圆，另一个使用平滑模式设置为<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>另一个使用平滑模式设置为<xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span><span class="sxs-lookup"><span data-stu-id="781fc-117">The following example draws two ellipses, one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> and one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue)  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias  
graphics.DrawEllipse(pen, 0, 0, 200, 100)  
graphics.SmoothingMode = SmoothingMode.HighSpeed  
graphics.DrawEllipse(pen, 0, 150, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias;  
graphics.DrawEllipse(pen, 0, 0, 200, 100);  
graphics.SmoothingMode = SmoothingMode.HighSpeed;  
graphics.DrawEllipse(pen, 0, 150, 200, 100);  
```  
  
### <a name="transformations"></a><span data-ttu-id="781fc-118">转换</span><span class="sxs-lookup"><span data-stu-id="781fc-118">Transformations</span></span>  
 <span data-ttu-id="781fc-119">A<xref:System.Drawing.Graphics>对象维护应用于由该绘制的所有项的两种转换 （world 和页）<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="781fc-119">A <xref:System.Drawing.Graphics> object maintains two transformations (world and page) that are applied to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="781fc-120">任何仿射转换可以存储在世界变换。</span><span class="sxs-lookup"><span data-stu-id="781fc-120">Any affine transformation can be stored in the world transformation.</span></span> <span data-ttu-id="781fc-121">仿射转换包括缩放、 旋转、 反射、 倾斜和转换。</span><span class="sxs-lookup"><span data-stu-id="781fc-121">Affine transformations include scaling, rotating, reflecting, skewing, and translating.</span></span> <span data-ttu-id="781fc-122">可以使用页转换，缩放和更改单位 （例如，为英寸的像素）。</span><span class="sxs-lookup"><span data-stu-id="781fc-122">The page transformation can be used for scaling and for changing units (for example, pixels to inches).</span></span> <span data-ttu-id="781fc-123">有关详细信息，请参阅[坐标系和坐标转换](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)。</span><span class="sxs-lookup"><span data-stu-id="781fc-123">For more information, see [Coordinate Systems and Transformations](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).</span></span>  
  
 <span data-ttu-id="781fc-124">下面的示例设置世界变换和页变换的<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="781fc-124">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="781fc-125">世界转换设置为 30 度旋转。</span><span class="sxs-lookup"><span data-stu-id="781fc-125">The world transformation is set to a 30-degree rotation.</span></span> <span data-ttu-id="781fc-126">页转换设置以便坐标传递到第二个<xref:System.Drawing.Graphics.DrawEllipse%2A>将被视为毫米等，而不是像素。</span><span class="sxs-lookup"><span data-stu-id="781fc-126">The page transformation is set so that the coordinates passed to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> will be treated as millimeters instead of pixels.</span></span> <span data-ttu-id="781fc-127">这段代码将两个相同调用<xref:System.Drawing.Graphics.DrawEllipse%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="781fc-127">The code makes two identical calls to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="781fc-128">世界转换应用于第一个<xref:System.Drawing.Graphics.DrawEllipse%2A>调用，而且这两种转换 （world 和页） 应用到第二个<xref:System.Drawing.Graphics.DrawEllipse%2A>调用。</span><span class="sxs-lookup"><span data-stu-id="781fc-128">The world transformation is applied to the first <xref:System.Drawing.Graphics.DrawEllipse%2A> call, and both transformations (world and page) are applied to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> call.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Red)  
  
graphics.ResetTransform()  
graphics.RotateTransform(30) ' world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
graphics.PageUnit = GraphicsUnit.Millimeter ' page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Red);   
  
graphics.ResetTransform();  
graphics.RotateTransform(30);                    // world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
graphics.PageUnit = GraphicsUnit.Millimeter;     // page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
```  
  
 <span data-ttu-id="781fc-129">下图显示两个椭圆。</span><span class="sxs-lookup"><span data-stu-id="781fc-129">The following illustration shows the two ellipses.</span></span> <span data-ttu-id="781fc-130">请注意，30 度旋转有关的源的坐标系统 （客户端区域的左上角），而不省略号的中心。</span><span class="sxs-lookup"><span data-stu-id="781fc-130">Note that the 30-degree rotation is about the origin of the coordinate system (upper-left corner of the client area), not about the centers of the ellipses.</span></span> <span data-ttu-id="781fc-131">另请注意钢笔的宽度为 1 的第二个椭圆意味着在第一个椭圆和 1 毫米 1 个像素。</span><span class="sxs-lookup"><span data-stu-id="781fc-131">Also note that the pen width of 1 means 1 pixel for the first ellipse and 1 millimeter for the second ellipse.</span></span>  
  
 <span data-ttu-id="781fc-132">![椭圆](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")</span><span class="sxs-lookup"><span data-stu-id="781fc-132">![Ovals](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")</span></span>  
  
### <a name="clipping-region"></a><span data-ttu-id="781fc-133">剪辑区域</span><span class="sxs-lookup"><span data-stu-id="781fc-133">Clipping Region</span></span>  
 <span data-ttu-id="781fc-134">A<xref:System.Drawing.Graphics>对象维护适用于由该绘制的所有项的剪辑区域<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="781fc-134">A <xref:System.Drawing.Graphics> object maintains a clipping region that applies to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="781fc-135">你可以通过调用设置的剪辑区域<xref:System.Drawing.Graphics.SetClip%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="781fc-135">You can set the clipping region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
 <span data-ttu-id="781fc-136">下面的示例通过两个矩形的并集创建形 plus 区域。</span><span class="sxs-lookup"><span data-stu-id="781fc-136">The following example creates a plus-shaped region by forming the union of two rectangles.</span></span> <span data-ttu-id="781fc-137">该区域指定的剪辑区域为<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="781fc-137">That region is designated as the clipping region of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="781fc-138">然后的代码绘制仅限于的剪辑区域的内部的两行。</span><span class="sxs-lookup"><span data-stu-id="781fc-138">Then the code draws two lines that are restricted to the interior of the clipping region.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](New Rectangle(50, 0, 50, 150))  
[region].Union(New Rectangle(0, 50, 150, 50))  
graphics.FillRegion(brush, [region])  
  
' Set the clipping region.  
graphics.SetClip([region], CombineMode.Replace)  
  
' Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160)  
graphics.DrawLine(pen, 40, 20, 190, 150)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
  
// Opaque red, width 5  
Pen pen = new Pen(Color.Red, 5);    
  
// Opaque aqua  
SolidBrush brush = new SolidBrush(Color.FromArgb(255, 180, 255, 255));    
  
// Create a plus-shaped region by forming the union of two rectangles.  
Region region = new Region(new Rectangle(50, 0, 50, 150));  
region.Union(new Rectangle(0, 50, 150, 50));  
graphics.FillRegion(brush, region);  
  
// Set the clipping region.  
graphics.SetClip(region, CombineMode.Replace);  
  
// Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160);  
graphics.DrawLine(pen, 40, 20, 190, 150);  
```  
  
 <span data-ttu-id="781fc-139">下图显示裁剪后的行。</span><span class="sxs-lookup"><span data-stu-id="781fc-139">The following illustration shows the clipped lines.</span></span>  
  
 <span data-ttu-id="781fc-140">![有限的剪辑区域](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")</span><span class="sxs-lookup"><span data-stu-id="781fc-140">![Limited Clip Region](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="781fc-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="781fc-141">See Also</span></span>  
 [<span data-ttu-id="781fc-142">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="781fc-142">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="781fc-143">使用嵌套的图形容器</span><span class="sxs-lookup"><span data-stu-id="781fc-143">Using Nested Graphics Containers</span></span>](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)
