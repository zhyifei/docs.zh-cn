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
ms.openlocfilehash: ce645133af35271fe1de969621907c53183d9a54
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505590"
---
# <a name="managing-the-state-of-a-graphics-object"></a><span data-ttu-id="e9447-102">管理 Graphics 对象的状态</span><span class="sxs-lookup"><span data-stu-id="e9447-102">Managing the State of a Graphics Object</span></span>
<span data-ttu-id="e9447-103"><xref:System.Drawing.Graphics>类是 GDI + 的核心。</span><span class="sxs-lookup"><span data-stu-id="e9447-103">The <xref:System.Drawing.Graphics> class is at the heart of GDI+.</span></span> <span data-ttu-id="e9447-104">若要绘制任何内容，您可以获得<xref:System.Drawing.Graphics>对象，设置其属性，并调用其方法<xref:System.Drawing.Graphics.DrawLine%2A>， <xref:System.Drawing.Graphics.DrawImage%2A>， <xref:System.Drawing.Graphics.DrawString%2A>，等等)。</span><span class="sxs-lookup"><span data-stu-id="e9447-104">To draw anything, you obtain a <xref:System.Drawing.Graphics> object, set its properties, and call its methods <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, and the like).</span></span>  
  
 <span data-ttu-id="e9447-105">下面的示例调用<xref:System.Drawing.Graphics.DrawRectangle%2A>方法的<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="e9447-105">The following example calls the <xref:System.Drawing.Graphics.DrawRectangle%2A> method of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="e9447-106">第一个参数传递给<xref:System.Drawing.Graphics.DrawRectangle%2A>方法是<xref:System.Drawing.Pen>对象。</span><span class="sxs-lookup"><span data-stu-id="e9447-106">The first argument passed to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method is a <xref:System.Drawing.Pen> object.</span></span>  
  
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
  
## <a name="graphics-state"></a><span data-ttu-id="e9447-107">图形状态</span><span class="sxs-lookup"><span data-stu-id="e9447-107">Graphics State</span></span>  
 <span data-ttu-id="e9447-108">一个<xref:System.Drawing.Graphics>对象不仅仅提供绘制方法，如<xref:System.Drawing.Graphics.DrawLine%2A>和<xref:System.Drawing.Graphics.DrawRectangle%2A>。</span><span class="sxs-lookup"><span data-stu-id="e9447-108">A <xref:System.Drawing.Graphics> object does more than provide drawing methods, such as <xref:System.Drawing.Graphics.DrawLine%2A> and <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span></span> <span data-ttu-id="e9447-109">一个<xref:System.Drawing.Graphics>对象还维护图形状态，可以分为以下类别：</span><span class="sxs-lookup"><span data-stu-id="e9447-109">A <xref:System.Drawing.Graphics> object also maintains graphics state, which can be divided into the following categories:</span></span>  
  
- <span data-ttu-id="e9447-110">质量设置</span><span class="sxs-lookup"><span data-stu-id="e9447-110">Quality settings</span></span>  
  
- <span data-ttu-id="e9447-111">转换</span><span class="sxs-lookup"><span data-stu-id="e9447-111">Transformations</span></span>  
  
- <span data-ttu-id="e9447-112">剪辑区域</span><span class="sxs-lookup"><span data-stu-id="e9447-112">Clipping region</span></span>  
  
### <a name="quality-settings"></a><span data-ttu-id="e9447-113">质量设置</span><span class="sxs-lookup"><span data-stu-id="e9447-113">Quality Settings</span></span>  
 <span data-ttu-id="e9447-114">一个<xref:System.Drawing.Graphics>对象具有影响的项的绘制质量的多个属性。</span><span class="sxs-lookup"><span data-stu-id="e9447-114">A <xref:System.Drawing.Graphics> object has several properties that influence the quality of the items that are drawn.</span></span> <span data-ttu-id="e9447-115">例如，可以设置<xref:System.Drawing.Graphics.TextRenderingHint%2A>属性来指定应用于文本的抗锯齿 （如果有） 的类型。</span><span class="sxs-lookup"><span data-stu-id="e9447-115">For example, you can set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property to specify the type of antialiasing (if any) applied to text.</span></span> <span data-ttu-id="e9447-116">质量会影响其他属性是<xref:System.Drawing.Graphics.SmoothingMode%2A>， <xref:System.Drawing.Graphics.CompositingMode%2A>， <xref:System.Drawing.Graphics.CompositingQuality%2A>，和<xref:System.Drawing.Graphics.InterpolationMode%2A>。</span><span class="sxs-lookup"><span data-stu-id="e9447-116">Other properties that influence quality are <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, and <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span></span>  
  
 <span data-ttu-id="e9447-117">下面的示例绘制一个具有平滑模式设置为两个椭圆<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>，另一个平滑模式设置为使用<xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span><span class="sxs-lookup"><span data-stu-id="e9447-117">The following example draws two ellipses, one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> and one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span></span>  
  
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
  
### <a name="transformations"></a><span data-ttu-id="e9447-118">转换</span><span class="sxs-lookup"><span data-stu-id="e9447-118">Transformations</span></span>  
 <span data-ttu-id="e9447-119">一个<xref:System.Drawing.Graphics>对象维护应用到所有项的绘制的两种转换 （世界和页）<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="e9447-119">A <xref:System.Drawing.Graphics> object maintains two transformations (world and page) that are applied to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="e9447-120">任何仿射转换可以存储在世界转换。</span><span class="sxs-lookup"><span data-stu-id="e9447-120">Any affine transformation can be stored in the world transformation.</span></span> <span data-ttu-id="e9447-121">仿射转换包括缩放、 旋转、 反射、 倾斜和转换。</span><span class="sxs-lookup"><span data-stu-id="e9447-121">Affine transformations include scaling, rotating, reflecting, skewing, and translating.</span></span> <span data-ttu-id="e9447-122">可以使用页转换，缩放和更改单元 （例如，像素为单位为英寸）。</span><span class="sxs-lookup"><span data-stu-id="e9447-122">The page transformation can be used for scaling and for changing units (for example, pixels to inches).</span></span> <span data-ttu-id="e9447-123">有关详细信息，请参阅[坐标系和坐标转换](coordinate-systems-and-transformations.md)。</span><span class="sxs-lookup"><span data-stu-id="e9447-123">For more information, see [Coordinate Systems and Transformations](coordinate-systems-and-transformations.md).</span></span>  
  
 <span data-ttu-id="e9447-124">下面的示例设置的世界和页转换<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="e9447-124">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="e9447-125">世界转换设置为 30 度旋转。</span><span class="sxs-lookup"><span data-stu-id="e9447-125">The world transformation is set to a 30-degree rotation.</span></span> <span data-ttu-id="e9447-126">设置页转换，以便坐标传递到第二个<xref:System.Drawing.Graphics.DrawEllipse%2A>将被视为毫米为单位，而不是像素为单位。</span><span class="sxs-lookup"><span data-stu-id="e9447-126">The page transformation is set so that the coordinates passed to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> will be treated as millimeters instead of pixels.</span></span> <span data-ttu-id="e9447-127">代码会两个相同调用<xref:System.Drawing.Graphics.DrawEllipse%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="e9447-127">The code makes two identical calls to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="e9447-128">世界转换应用于第一个<xref:System.Drawing.Graphics.DrawEllipse%2A>调用时，并 （世界和页） 这两种转换应用于第二个<xref:System.Drawing.Graphics.DrawEllipse%2A>调用。</span><span class="sxs-lookup"><span data-stu-id="e9447-128">The world transformation is applied to the first <xref:System.Drawing.Graphics.DrawEllipse%2A> call, and both transformations (world and page) are applied to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> call.</span></span>  
  
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
  
 <span data-ttu-id="e9447-129">下图显示了两个椭圆。</span><span class="sxs-lookup"><span data-stu-id="e9447-129">The following illustration shows the two ellipses.</span></span> <span data-ttu-id="e9447-130">请注意，30 度旋转的坐标系统 （客户端区域的左上角） 来源，而不椭圆的中心。</span><span class="sxs-lookup"><span data-stu-id="e9447-130">Note that the 30-degree rotation is about the origin of the coordinate system (upper-left corner of the client area), not about the centers of the ellipses.</span></span> <span data-ttu-id="e9447-131">另请注意钢笔的宽度为 1 的第二个椭圆意味着 1 像素的第一个椭圆和 1 毫米。</span><span class="sxs-lookup"><span data-stu-id="e9447-131">Also note that the pen width of 1 means 1 pixel for the first ellipse and 1 millimeter for the second ellipse.</span></span>  
  
 ![显示两个椭圆的图示： 旋转和笔的宽度。](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a><span data-ttu-id="e9447-133">剪辑区域</span><span class="sxs-lookup"><span data-stu-id="e9447-133">Clipping Region</span></span>  
 <span data-ttu-id="e9447-134">一个<xref:System.Drawing.Graphics>对象维护应用于由，绘制的所有项的剪辑区域<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="e9447-134">A <xref:System.Drawing.Graphics> object maintains a clipping region that applies to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="e9447-135">可以通过调用设置的剪辑区域<xref:System.Drawing.Graphics.SetClip%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="e9447-135">You can set the clipping region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
 <span data-ttu-id="e9447-136">下面的示例通过两个矩形的并集创建 plus 形区域。</span><span class="sxs-lookup"><span data-stu-id="e9447-136">The following example creates a plus-shaped region by forming the union of two rectangles.</span></span> <span data-ttu-id="e9447-137">该区域指定的剪辑区域为<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="e9447-137">That region is designated as the clipping region of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="e9447-138">然后代码将绘制仅限于的剪辑区域内部的两行。</span><span class="sxs-lookup"><span data-stu-id="e9447-138">Then the code draws two lines that are restricted to the interior of the clipping region.</span></span>  
  
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
  
 <span data-ttu-id="e9447-139">下图显示了裁剪后的行：</span><span class="sxs-lookup"><span data-stu-id="e9447-139">The following illustration shows the clipped lines:</span></span>  
  
 ![图，显示受限的剪辑区域。](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a><span data-ttu-id="e9447-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9447-141">See also</span></span>

- [<span data-ttu-id="e9447-142">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="e9447-142">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="e9447-143">使用嵌套的图形容器</span><span class="sxs-lookup"><span data-stu-id="e9447-143">Using Nested Graphics Containers</span></span>](using-nested-graphics-containers.md)
