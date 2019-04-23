---
title: 向量图形概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inclusive-inclusive endpoints
- coordinate systems
- graphics [Windows Forms], vector graphics
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
ms.openlocfilehash: d424254839db6c403bafe779f475c0e344918a5e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59087958"
---
# <a name="vector-graphics-overview"></a><span data-ttu-id="38266-102">向量图形概述</span><span class="sxs-lookup"><span data-stu-id="38266-102">Vector Graphics Overview</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="38266-103">绘制线条、 矩形和其他形状的坐标系统上。</span><span class="sxs-lookup"><span data-stu-id="38266-103">draws lines, rectangles, and other shapes on a coordinate system.</span></span> <span data-ttu-id="38266-104">可以选择使用不同的坐标系统，但默认坐标系统中都具有原点左上角具有 x 轴指向右，y 轴指向下方。</span><span class="sxs-lookup"><span data-stu-id="38266-104">You can choose from a variety of coordinate systems, but the default coordinate system has the origin in the upper-left corner with the x-axis pointing to the right and the y-axis pointing down.</span></span> <span data-ttu-id="38266-105">默认坐标系统中的度量单位为像素。</span><span class="sxs-lookup"><span data-stu-id="38266-105">The unit of measure in the default coordinate system is the pixel.</span></span>  
  
## <a name="the-building-blocks-of-gdi"></a><span data-ttu-id="38266-106">GDI + 的构建基块</span><span class="sxs-lookup"><span data-stu-id="38266-106">The Building Blocks of GDI+</span></span>  
 <span data-ttu-id="38266-107">![矢量图形](./media/aboutgdip02-art01.gif "AboutGdip02_Art01")</span><span class="sxs-lookup"><span data-stu-id="38266-107">![Vector graphic](./media/aboutgdip02-art01.gif "AboutGdip02_Art01")</span></span>  
  
 <span data-ttu-id="38266-108">计算机监视器上点称为图片元素或像素的矩形数组创建其显示。</span><span class="sxs-lookup"><span data-stu-id="38266-108">A computer monitor creates its display on a rectangular array of dots called picture elements or pixels.</span></span> <span data-ttu-id="38266-109">有所不同到下一步，一台监视器显示在屏幕的像素数，并显示在单个监视器的像素数通常可某种程度上由用户。</span><span class="sxs-lookup"><span data-stu-id="38266-109">The number of pixels that appear on the screen varies from one monitor to the next, and the number of pixels that appear on an individual monitor can usually be configured to some extent by the user.</span></span>  
  
 <span data-ttu-id="38266-110">![矢量图形](./media/aboutgdip02-art02.gif "AboutGdip02_Art02")</span><span class="sxs-lookup"><span data-stu-id="38266-110">![Vector graphic](./media/aboutgdip02-art02.gif "AboutGdip02_Art02")</span></span>  
  
 <span data-ttu-id="38266-111">当你使用[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]若要绘制线条、 矩形或曲线，提供有关要绘制的项的某些关键信息。</span><span class="sxs-lookup"><span data-stu-id="38266-111">When you use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to draw a line, rectangle, or curve, you provide certain key information about the item to be drawn.</span></span> <span data-ttu-id="38266-112">例如，可以通过提供两个点，指定的行，并可以通过提供一个点、 高度和宽度指定矩形。</span><span class="sxs-lookup"><span data-stu-id="38266-112">For example, you can specify a line by providing two points, and you can specify a rectangle by providing a point, a height, and a width.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="38266-113">显示驱动程序软件，以确定哪些像素必须打开以显示行、 矩形或曲线结合工作。</span><span class="sxs-lookup"><span data-stu-id="38266-113">works in conjunction with the display driver software to determine which pixels must be turned on to show the line, rectangle, or curve.</span></span> <span data-ttu-id="38266-114">下图显示了已打开，可以显示行的 （4，2） 的点到点 （12、 8） 的像素。</span><span class="sxs-lookup"><span data-stu-id="38266-114">The following illustration shows the pixels that are turned on to display a line from the point (4, 2) to the point (12, 8).</span></span>  
  
 <span data-ttu-id="38266-115">![矢量图形](./media/aboutgdip02-art03.gif "AboutGdip02_Art03")</span><span class="sxs-lookup"><span data-stu-id="38266-115">![Vector graphic](./media/aboutgdip02-art03.gif "AboutGdip02_Art03")</span></span>  
  
 <span data-ttu-id="38266-116">随着时间推移，某些基本构造块已被证明是最适用于创建二维图片。</span><span class="sxs-lookup"><span data-stu-id="38266-116">Over time, certain basic building blocks have proven to be the most useful for creating two-dimensional pictures.</span></span> <span data-ttu-id="38266-117">这些构建基块，支持的[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，给出了下面的列表：</span><span class="sxs-lookup"><span data-stu-id="38266-117">These building blocks, which are all supported by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], are given in the following list:</span></span>  
  
-   <span data-ttu-id="38266-118">直线</span><span class="sxs-lookup"><span data-stu-id="38266-118">Lines</span></span>  
  
-   <span data-ttu-id="38266-119">矩形</span><span class="sxs-lookup"><span data-stu-id="38266-119">Rectangles</span></span>  
  
-   <span data-ttu-id="38266-120">省略号</span><span class="sxs-lookup"><span data-stu-id="38266-120">Ellipses</span></span>  
  
-   <span data-ttu-id="38266-121">Arcs</span><span class="sxs-lookup"><span data-stu-id="38266-121">Arcs</span></span>  
  
-   <span data-ttu-id="38266-122">多边形</span><span class="sxs-lookup"><span data-stu-id="38266-122">Polygons</span></span>  
  
-   <span data-ttu-id="38266-123">基数样条</span><span class="sxs-lookup"><span data-stu-id="38266-123">Cardinal splines</span></span>  
  
-   <span data-ttu-id="38266-124">贝塞尔曲线样条</span><span class="sxs-lookup"><span data-stu-id="38266-124">Bezier splines</span></span>  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a><span data-ttu-id="38266-125">进行绘制的图形对象的方法</span><span class="sxs-lookup"><span data-stu-id="38266-125">Methods For Drawing with a Graphics Object</span></span>  
 <span data-ttu-id="38266-126"><xref:System.Drawing.Graphics>类中[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]提供了用于绘制的项前面的列表中的以下方法： <xref:System.Drawing.Graphics.DrawLine%2A>， <xref:System.Drawing.Graphics.DrawRectangle%2A>， <xref:System.Drawing.Graphics.DrawEllipse%2A>， <xref:System.Drawing.Graphics.DrawPolygon%2A>， <xref:System.Drawing.Graphics.DrawArc%2A>， <xref:System.Drawing.Graphics.DrawCurve%2A> （适用于基本样条），并<xref:System.Drawing.Graphics.DrawBezier%2A>.</span><span class="sxs-lookup"><span data-stu-id="38266-126">The <xref:System.Drawing.Graphics> class in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] provides the following methods for drawing the items in the previous list: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (for cardinal splines), and <xref:System.Drawing.Graphics.DrawBezier%2A>.</span></span> <span data-ttu-id="38266-127">每种方法将重载;也就是说，每个方法支持多个不同的参数列表。</span><span class="sxs-lookup"><span data-stu-id="38266-127">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="38266-128">例如，一种<xref:System.Drawing.Graphics.DrawLine%2A>方法接收<xref:System.Drawing.Pen>对象和四个整数，而另一个变体<xref:System.Drawing.Graphics.DrawLine%2A>方法接收<xref:System.Drawing.Pen>对象和两个<xref:System.Drawing.Point>对象。</span><span class="sxs-lookup"><span data-stu-id="38266-128">For example, one variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and four integers, while another variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="38266-129">绘制线条、 矩形和贝塞尔自由绘制曲线的方法具有复数形式的伴随方法，可在单个调用中绘制多个项： <xref:System.Drawing.Graphics.DrawLines%2A>， <xref:System.Drawing.Graphics.DrawRectangles%2A>，和<xref:System.Drawing.Graphics.DrawBeziers%2A>。</span><span class="sxs-lookup"><span data-stu-id="38266-129">The methods for drawing lines, rectangles, and Bézier splines have plural companion methods that draw several items in a single call: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, and <xref:System.Drawing.Graphics.DrawBeziers%2A>.</span></span> <span data-ttu-id="38266-130">此外，<xref:System.Drawing.Graphics.DrawCurve%2A>方法有一个随附方法<xref:System.Drawing.Graphics.DrawClosedCurve%2A>、，关闭曲线的曲线的结束点连接到的起始点。</span><span class="sxs-lookup"><span data-stu-id="38266-130">Also, the <xref:System.Drawing.Graphics.DrawCurve%2A> method has a companion method, <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, that closes a curve by connecting the ending point of the curve to the starting point.</span></span>  
  
 <span data-ttu-id="38266-131">绘制方法的所有<xref:System.Drawing.Graphics>类结合工作<xref:System.Drawing.Pen>对象。</span><span class="sxs-lookup"><span data-stu-id="38266-131">All of the drawing methods of the <xref:System.Drawing.Graphics> class work in conjunction with a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="38266-132">若要绘制任何内容，必须创建至少两个对象：<xref:System.Drawing.Graphics>对象和一个<xref:System.Drawing.Pen>对象。</span><span class="sxs-lookup"><span data-stu-id="38266-132">To draw anything, you must create at least two objects: a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="38266-133"><xref:System.Drawing.Pen>对象将存储属性，例如线条宽度和颜色，要绘制的项。</span><span class="sxs-lookup"><span data-stu-id="38266-133">The <xref:System.Drawing.Pen> object stores attributes, such as line width and color, of the item to be drawn.</span></span> <span data-ttu-id="38266-134"><xref:System.Drawing.Pen>对象作为一个参数传递给绘图的方法。</span><span class="sxs-lookup"><span data-stu-id="38266-134">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the drawing method.</span></span> <span data-ttu-id="38266-135">例如，一种<xref:System.Drawing.Graphics.DrawLine%2A>方法接收<xref:System.Drawing.Pen>对象，如下面的示例绘制一个宽度为 100，高度为 50 到左上角的矩形中所示的四个整数 （20、 10）：</span><span class="sxs-lookup"><span data-stu-id="38266-135">For example, one variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and four integers as shown in the following example, which draws a rectangle with a width of 100, a height of 50 and an upper-left corner of (20, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#11](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="38266-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="38266-136">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="38266-137">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="38266-137">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="38266-138">如何：创建用于绘制图形对象</span><span class="sxs-lookup"><span data-stu-id="38266-138">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
