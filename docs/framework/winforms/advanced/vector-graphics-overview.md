---
title: "向量图形概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inclusive-inclusive endpoints
- coordinate systems
- graphics [Windows Forms], vector graphics
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 603b76c999933f177a9e48ddb819562b8e4dd8f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="vector-graphics-overview"></a><span data-ttu-id="8c173-102">向量图形概述</span><span class="sxs-lookup"><span data-stu-id="8c173-102">Vector Graphics Overview</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="8c173-103">坐标系统上绘制线条、 矩形和其他形状。</span><span class="sxs-lookup"><span data-stu-id="8c173-103"> draws lines, rectangles, and other shapes on a coordinate system.</span></span> <span data-ttu-id="8c173-104">你可以选择使用不同的坐标系统，但默认坐标系统有原点左上角 x 轴指向右和向下 y 轴。</span><span class="sxs-lookup"><span data-stu-id="8c173-104">You can choose from a variety of coordinate systems, but the default coordinate system has the origin in the upper-left corner with the x-axis pointing to the right and the y-axis pointing down.</span></span> <span data-ttu-id="8c173-105">默认坐标系统中单位是度量的像素。</span><span class="sxs-lookup"><span data-stu-id="8c173-105">The unit of measure in the default coordinate system is the pixel.</span></span>  
  
## <a name="the-building-blocks-of-gdi"></a><span data-ttu-id="8c173-106">GDI + 构建基块</span><span class="sxs-lookup"><span data-stu-id="8c173-106">The Building Blocks of GDI+</span></span>  
 <span data-ttu-id="8c173-107">![矢量图形](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.gif "AboutGdip02_Art01")</span><span class="sxs-lookup"><span data-stu-id="8c173-107">![Vector graphic](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.gif "AboutGdip02_Art01")</span></span>  
  
 <span data-ttu-id="8c173-108">计算机监视器上的点调用图片元素或像素的矩形数组创建其显示。</span><span class="sxs-lookup"><span data-stu-id="8c173-108">A computer monitor creates its display on a rectangular array of dots called picture elements or pixels.</span></span> <span data-ttu-id="8c173-109">有所不同到下一行，一个监视器的屏幕显示的像素数并且在单个监视器显示的像素数通常可以将在某种程度上由用户。</span><span class="sxs-lookup"><span data-stu-id="8c173-109">The number of pixels that appear on the screen varies from one monitor to the next, and the number of pixels that appear on an individual monitor can usually be configured to some extent by the user.</span></span>  
  
 <span data-ttu-id="8c173-110">![矢量图形](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.gif "AboutGdip02_Art02")</span><span class="sxs-lookup"><span data-stu-id="8c173-110">![Vector graphic](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.gif "AboutGdip02_Art02")</span></span>  
  
 <span data-ttu-id="8c173-111">当你使用[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]若要绘制线条、 矩形或曲线，提供有关要绘制的项的某些关键信息。</span><span class="sxs-lookup"><span data-stu-id="8c173-111">When you use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to draw a line, rectangle, or curve, you provide certain key information about the item to be drawn.</span></span> <span data-ttu-id="8c173-112">例如，你可以通过提供两个点，指定的行，并可以通过提供一个点、 高度和宽度指定矩形。</span><span class="sxs-lookup"><span data-stu-id="8c173-112">For example, you can specify a line by providing two points, and you can specify a rectangle by providing a point, a height, and a width.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="8c173-113">显示驱动程序软件，以确定哪些像素必须打开以显示行、 矩形或曲线协同工作。</span><span class="sxs-lookup"><span data-stu-id="8c173-113"> works in conjunction with the display driver software to determine which pixels must be turned on to show the line, rectangle, or curve.</span></span> <span data-ttu-id="8c173-114">下图显示已打开，可以显示一条线的 （4，2） 的点到点 （12、 8） 的像素。</span><span class="sxs-lookup"><span data-stu-id="8c173-114">The following illustration shows the pixels that are turned on to display a line from the point (4, 2) to the point (12, 8).</span></span>  
  
 <span data-ttu-id="8c173-115">![矢量图形](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.gif "AboutGdip02_Art03")</span><span class="sxs-lookup"><span data-stu-id="8c173-115">![Vector graphic](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.gif "AboutGdip02_Art03")</span></span>  
  
 <span data-ttu-id="8c173-116">随着时间推移，某些基本的构建基块已被公认为最适用于创建二维图片。</span><span class="sxs-lookup"><span data-stu-id="8c173-116">Over time, certain basic building blocks have proven to be the most useful for creating two-dimensional pictures.</span></span> <span data-ttu-id="8c173-117">这些构建基块，所有支持的[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，给定以下列表中：</span><span class="sxs-lookup"><span data-stu-id="8c173-117">These building blocks, which are all supported by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], are given in the following list:</span></span>  
  
-   <span data-ttu-id="8c173-118">直线</span><span class="sxs-lookup"><span data-stu-id="8c173-118">Lines</span></span>  
  
-   <span data-ttu-id="8c173-119">矩形</span><span class="sxs-lookup"><span data-stu-id="8c173-119">Rectangles</span></span>  
  
-   <span data-ttu-id="8c173-120">省略号</span><span class="sxs-lookup"><span data-stu-id="8c173-120">Ellipses</span></span>  
  
-   <span data-ttu-id="8c173-121">弧</span><span class="sxs-lookup"><span data-stu-id="8c173-121">Arcs</span></span>  
  
-   <span data-ttu-id="8c173-122">多边形</span><span class="sxs-lookup"><span data-stu-id="8c173-122">Polygons</span></span>  
  
-   <span data-ttu-id="8c173-123">基本样条</span><span class="sxs-lookup"><span data-stu-id="8c173-123">Cardinal splines</span></span>  
  
-   <span data-ttu-id="8c173-124">贝塞尔曲线样条</span><span class="sxs-lookup"><span data-stu-id="8c173-124">Bezier splines</span></span>  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a><span data-ttu-id="8c173-125">进行绘制与图形对象的方法</span><span class="sxs-lookup"><span data-stu-id="8c173-125">Methods For Drawing with a Graphics Object</span></span>  
 <span data-ttu-id="8c173-126"><xref:System.Drawing.Graphics>类[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]提供在前面的列表中绘制项的以下方法： <xref:System.Drawing.Graphics.DrawLine%2A>， <xref:System.Drawing.Graphics.DrawRectangle%2A>， <xref:System.Drawing.Graphics.DrawEllipse%2A>， <xref:System.Drawing.Graphics.DrawPolygon%2A>， <xref:System.Drawing.Graphics.DrawArc%2A>， <xref:System.Drawing.Graphics.DrawCurve%2A> （对于基本样条），和<xref:System.Drawing.Graphics.DrawBezier%2A>.</span><span class="sxs-lookup"><span data-stu-id="8c173-126">The <xref:System.Drawing.Graphics> class in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] provides the following methods for drawing the items in the previous list: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (for cardinal splines), and <xref:System.Drawing.Graphics.DrawBezier%2A>.</span></span> <span data-ttu-id="8c173-127">上述每种方法将重载;也就是说，每个方法都支持几个不同的参数列表。</span><span class="sxs-lookup"><span data-stu-id="8c173-127">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="8c173-128">例如，一个变体<xref:System.Drawing.Graphics.DrawLine%2A>方法接收<xref:System.Drawing.Pen>对象和四个整数，而另一个变体<xref:System.Drawing.Graphics.DrawLine%2A>方法接收<xref:System.Drawing.Pen>对象和第二个<xref:System.Drawing.Point>对象。</span><span class="sxs-lookup"><span data-stu-id="8c173-128">For example, one variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and four integers, while another variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="8c173-129">绘制线条、 矩形和贝塞尔样条的方法具有复数形式伴随方法，可在单个调用中绘制多个项： <xref:System.Drawing.Graphics.DrawLines%2A>， <xref:System.Drawing.Graphics.DrawRectangles%2A>，和<xref:System.Drawing.Graphics.DrawBeziers%2A>。</span><span class="sxs-lookup"><span data-stu-id="8c173-129">The methods for drawing lines, rectangles, and Bézier splines have plural companion methods that draw several items in a single call: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, and <xref:System.Drawing.Graphics.DrawBeziers%2A>.</span></span> <span data-ttu-id="8c173-130">此外，<xref:System.Drawing.Graphics.DrawCurve%2A>方法具有助理方法<xref:System.Drawing.Graphics.DrawClosedCurve%2A>，关闭一条曲线的曲线的结束点连接到的起始点。</span><span class="sxs-lookup"><span data-stu-id="8c173-130">Also, the <xref:System.Drawing.Graphics.DrawCurve%2A> method has a companion method, <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, that closes a curve by connecting the ending point of the curve to the starting point.</span></span>  
  
 <span data-ttu-id="8c173-131">所有的绘制方法<xref:System.Drawing.Graphics>类结合工作<xref:System.Drawing.Pen>对象。</span><span class="sxs-lookup"><span data-stu-id="8c173-131">All of the drawing methods of the <xref:System.Drawing.Graphics> class work in conjunction with a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="8c173-132">若要绘制任何内容，必须创建至少两个对象：<xref:System.Drawing.Graphics>对象和一个<xref:System.Drawing.Pen>对象。</span><span class="sxs-lookup"><span data-stu-id="8c173-132">To draw anything, you must create at least two objects: a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="8c173-133"><xref:System.Drawing.Pen>对象存储特性，如线条宽度和颜色，要绘制的项。</span><span class="sxs-lookup"><span data-stu-id="8c173-133">The <xref:System.Drawing.Pen> object stores attributes, such as line width and color, of the item to be drawn.</span></span> <span data-ttu-id="8c173-134"><xref:System.Drawing.Pen>对象作为一个参数传递给绘制的方法。</span><span class="sxs-lookup"><span data-stu-id="8c173-134">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the drawing method.</span></span> <span data-ttu-id="8c173-135">例如，一个变体<xref:System.Drawing.Graphics.DrawLine%2A>方法接收<xref:System.Drawing.Pen>对象和四个整数中绘制的矩形宽度为 100，高度为 50 到的左上角的以下示例所示 （20，10）：</span><span class="sxs-lookup"><span data-stu-id="8c173-135">For example, one variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and four integers as shown in the following example, which draws a rectangle with a width of 100, a height of 50 and an upper-left corner of (20, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="8c173-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c173-136">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [<span data-ttu-id="8c173-137">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="8c173-137">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="8c173-138">如何：创建用于绘制的图形对象</span><span class="sxs-lookup"><span data-stu-id="8c173-138">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
