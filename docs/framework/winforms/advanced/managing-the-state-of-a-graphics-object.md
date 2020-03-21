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
ms.openlocfilehash: d1e7e6eac775ca779fb68605adcc9bc2b9915e49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182457"
---
# <a name="managing-the-state-of-a-graphics-object"></a><span data-ttu-id="84e83-102">管理 Graphics 对象的状态</span><span class="sxs-lookup"><span data-stu-id="84e83-102">Managing the State of a Graphics Object</span></span>
<span data-ttu-id="84e83-103">该<xref:System.Drawing.Graphics>课程是 GDI® 的核心。</span><span class="sxs-lookup"><span data-stu-id="84e83-103">The <xref:System.Drawing.Graphics> class is at the heart of GDI+.</span></span> <span data-ttu-id="84e83-104">要绘制任何内容，请获取<xref:System.Drawing.Graphics>对象、设置其属性并调用其方法<xref:System.Drawing.Graphics.DrawLine%2A>、、<xref:System.Drawing.Graphics.DrawString%2A><xref:System.Drawing.Graphics.DrawImage%2A>等。</span><span class="sxs-lookup"><span data-stu-id="84e83-104">To draw anything, you obtain a <xref:System.Drawing.Graphics> object, set its properties, and call its methods <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, and the like).</span></span>  
  
 <span data-ttu-id="84e83-105">下面的示例调用<xref:System.Drawing.Graphics.DrawRectangle%2A><xref:System.Drawing.Graphics>对象的方法。</span><span class="sxs-lookup"><span data-stu-id="84e83-105">The following example calls the <xref:System.Drawing.Graphics.DrawRectangle%2A> method of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="84e83-106">传递给<xref:System.Drawing.Graphics.DrawRectangle%2A>方法的第一个参数是对象<xref:System.Drawing.Pen>。</span><span class="sxs-lookup"><span data-stu-id="84e83-106">The first argument passed to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method is a <xref:System.Drawing.Pen> object.</span></span>  
  
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
  
## <a name="graphics-state"></a><span data-ttu-id="84e83-107">图形状态</span><span class="sxs-lookup"><span data-stu-id="84e83-107">Graphics State</span></span>  
 <span data-ttu-id="84e83-108">对象<xref:System.Drawing.Graphics>的作用不仅仅是提供绘图方法，如<xref:System.Drawing.Graphics.DrawLine%2A>和<xref:System.Drawing.Graphics.DrawRectangle%2A>。</span><span class="sxs-lookup"><span data-stu-id="84e83-108">A <xref:System.Drawing.Graphics> object does more than provide drawing methods, such as <xref:System.Drawing.Graphics.DrawLine%2A> and <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span></span> <span data-ttu-id="84e83-109">对象<xref:System.Drawing.Graphics>还维护图形状态，可以分为以下几类：</span><span class="sxs-lookup"><span data-stu-id="84e83-109">A <xref:System.Drawing.Graphics> object also maintains graphics state, which can be divided into the following categories:</span></span>  
  
- <span data-ttu-id="84e83-110">质量设置</span><span class="sxs-lookup"><span data-stu-id="84e83-110">Quality settings</span></span>  
  
- <span data-ttu-id="84e83-111">转换</span><span class="sxs-lookup"><span data-stu-id="84e83-111">Transformations</span></span>  
  
- <span data-ttu-id="84e83-112">剪切区域</span><span class="sxs-lookup"><span data-stu-id="84e83-112">Clipping region</span></span>  
  
### <a name="quality-settings"></a><span data-ttu-id="84e83-113">质量设置</span><span class="sxs-lookup"><span data-stu-id="84e83-113">Quality Settings</span></span>  
 <span data-ttu-id="84e83-114">对象<xref:System.Drawing.Graphics>具有多个属性，这些属性会影响所绘制的项的质量。</span><span class="sxs-lookup"><span data-stu-id="84e83-114">A <xref:System.Drawing.Graphics> object has several properties that influence the quality of the items that are drawn.</span></span> <span data-ttu-id="84e83-115">例如，<xref:System.Drawing.Graphics.TextRenderingHint%2A>可以将 属性设置为指定应用于文本的反锯齿类型（如果有）。</span><span class="sxs-lookup"><span data-stu-id="84e83-115">For example, you can set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property to specify the type of antialiasing (if any) applied to text.</span></span> <span data-ttu-id="84e83-116">影响质量<xref:System.Drawing.Graphics.SmoothingMode%2A>的其他属性是 、<xref:System.Drawing.Graphics.CompositingMode%2A><xref:System.Drawing.Graphics.CompositingQuality%2A>和<xref:System.Drawing.Graphics.InterpolationMode%2A>。</span><span class="sxs-lookup"><span data-stu-id="84e83-116">Other properties that influence quality are <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, and <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span></span>  
  
 <span data-ttu-id="84e83-117">下面的示例绘制两个椭圆，一个设置为平滑模式<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>，另一个将平滑模式设置为 ： <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed></span><span class="sxs-lookup"><span data-stu-id="84e83-117">The following example draws two ellipses, one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> and one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span></span>  
  
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
  
### <a name="transformations"></a><span data-ttu-id="84e83-118">转换</span><span class="sxs-lookup"><span data-stu-id="84e83-118">Transformations</span></span>  
 <span data-ttu-id="84e83-119">对象<xref:System.Drawing.Graphics>维护应用于该<xref:System.Drawing.Graphics>对象绘制的所有项的两个转换（世界和页面）。</span><span class="sxs-lookup"><span data-stu-id="84e83-119">A <xref:System.Drawing.Graphics> object maintains two transformations (world and page) that are applied to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="84e83-120">任何仿冒变换都可以储存在世界变换中。</span><span class="sxs-lookup"><span data-stu-id="84e83-120">Any affine transformation can be stored in the world transformation.</span></span> <span data-ttu-id="84e83-121">仿法变换包括缩放、旋转、反射、倾斜和平移。</span><span class="sxs-lookup"><span data-stu-id="84e83-121">Affine transformations include scaling, rotating, reflecting, skewing, and translating.</span></span> <span data-ttu-id="84e83-122">页面转换可用于缩放和更改单位（例如，像素到英寸）。</span><span class="sxs-lookup"><span data-stu-id="84e83-122">The page transformation can be used for scaling and for changing units (for example, pixels to inches).</span></span> <span data-ttu-id="84e83-123">有关详细信息，请参阅[坐标系和变换](coordinate-systems-and-transformations.md)。</span><span class="sxs-lookup"><span data-stu-id="84e83-123">For more information, see [Coordinate Systems and Transformations](coordinate-systems-and-transformations.md).</span></span>  
  
 <span data-ttu-id="84e83-124">下面的示例设置<xref:System.Drawing.Graphics>对象的世界和页面转换。</span><span class="sxs-lookup"><span data-stu-id="84e83-124">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="84e83-125">世界转型设置为 30 度旋转。</span><span class="sxs-lookup"><span data-stu-id="84e83-125">The world transformation is set to a 30-degree rotation.</span></span> <span data-ttu-id="84e83-126">设置页面变换，以便传递给第二<xref:System.Drawing.Graphics.DrawEllipse%2A>个坐标将被视为毫米而不是像素。</span><span class="sxs-lookup"><span data-stu-id="84e83-126">The page transformation is set so that the coordinates passed to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> will be treated as millimeters instead of pixels.</span></span> <span data-ttu-id="84e83-127">代码对<xref:System.Drawing.Graphics.DrawEllipse%2A>该方法进行两个相同的调用。</span><span class="sxs-lookup"><span data-stu-id="84e83-127">The code makes two identical calls to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="84e83-128">世界转换应用于第一个<xref:System.Drawing.Graphics.DrawEllipse%2A>调用，并且两个转换（世界和页面）都应用于第二个<xref:System.Drawing.Graphics.DrawEllipse%2A>调用。</span><span class="sxs-lookup"><span data-stu-id="84e83-128">The world transformation is applied to the first <xref:System.Drawing.Graphics.DrawEllipse%2A> call, and both transformations (world and page) are applied to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> call.</span></span>  
  
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
  
 <span data-ttu-id="84e83-129">下图显示了两个椭圆。</span><span class="sxs-lookup"><span data-stu-id="84e83-129">The following illustration shows the two ellipses.</span></span> <span data-ttu-id="84e83-130">请注意，30 度旋转是关于坐标系的原点（工作区的左上角），而不是椭圆的中心。</span><span class="sxs-lookup"><span data-stu-id="84e83-130">Note that the 30-degree rotation is about the origin of the coordinate system (upper-left corner of the client area), not about the centers of the ellipses.</span></span> <span data-ttu-id="84e83-131">另请注意，笔宽度 1 表示第一个椭圆的 1 像素，第二个椭圆的笔宽度为 1 毫米。</span><span class="sxs-lookup"><span data-stu-id="84e83-131">Also note that the pen width of 1 means 1 pixel for the first ellipse and 1 millimeter for the second ellipse.</span></span>  
  
 ![显示两个椭圆的插图：旋转和笔宽度。](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a><span data-ttu-id="84e83-133">剪切区域</span><span class="sxs-lookup"><span data-stu-id="84e83-133">Clipping Region</span></span>  
 <span data-ttu-id="84e83-134">对象<xref:System.Drawing.Graphics>维护一个裁剪区域，该区域适用于该<xref:System.Drawing.Graphics>对象绘制的所有项目。</span><span class="sxs-lookup"><span data-stu-id="84e83-134">A <xref:System.Drawing.Graphics> object maintains a clipping region that applies to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="84e83-135">您可以通过调用<xref:System.Drawing.Graphics.SetClip%2A>方法来设置裁剪区域。</span><span class="sxs-lookup"><span data-stu-id="84e83-135">You can set the clipping region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
 <span data-ttu-id="84e83-136">下面的示例通过形成两个矩形的合并来创建一个加形区域。</span><span class="sxs-lookup"><span data-stu-id="84e83-136">The following example creates a plus-shaped region by forming the union of two rectangles.</span></span> <span data-ttu-id="84e83-137">该区域被指定为<xref:System.Drawing.Graphics>对象的剪切区域。</span><span class="sxs-lookup"><span data-stu-id="84e83-137">That region is designated as the clipping region of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="84e83-138">然后，代码绘制两行，这些行仅限于裁剪区域的内部。</span><span class="sxs-lookup"><span data-stu-id="84e83-138">Then the code draws two lines that are restricted to the interior of the clipping region.</span></span>  
  
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
  
 <span data-ttu-id="84e83-139">下图显示了剪切的线条：</span><span class="sxs-lookup"><span data-stu-id="84e83-139">The following illustration shows the clipped lines:</span></span>  
  
 ![显示有限剪辑区域的图表。](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a><span data-ttu-id="84e83-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84e83-141">See also</span></span>

- [<span data-ttu-id="84e83-142">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="84e83-142">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="84e83-143">使用嵌套的 Graphics 容器</span><span class="sxs-lookup"><span data-stu-id="84e83-143">Using Nested Graphics Containers</span></span>](using-nested-graphics-containers.md)
