---
title: GDI+ 中的图形路径
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
ms.openlocfilehash: 8e06032d145eb8c1aaf9bfcd1f205f8c6583634a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64581378"
---
# <a name="graphics-paths-in-gdi"></a><span data-ttu-id="73117-102">GDI+ 中的图形路径</span><span class="sxs-lookup"><span data-stu-id="73117-102">Graphics Paths in GDI+</span></span>
<span data-ttu-id="73117-103">路径是通过将线条、 矩形和简单的曲线相结合形成的。</span><span class="sxs-lookup"><span data-stu-id="73117-103">Paths are formed by combining lines, rectangles, and simple curves.</span></span> <span data-ttu-id="73117-104">还记得[向量图形概述](vector-graphics-overview.md)以下基本构建基块已证明是最适用于绘制图片：</span><span class="sxs-lookup"><span data-stu-id="73117-104">Recall from the [Vector Graphics Overview](vector-graphics-overview.md) that the following basic building blocks have proven to be the most useful for drawing pictures:</span></span>  
  
- <span data-ttu-id="73117-105">直线</span><span class="sxs-lookup"><span data-stu-id="73117-105">Lines</span></span>  
  
- <span data-ttu-id="73117-106">矩形</span><span class="sxs-lookup"><span data-stu-id="73117-106">Rectangles</span></span>  
  
- <span data-ttu-id="73117-107">省略号</span><span class="sxs-lookup"><span data-stu-id="73117-107">Ellipses</span></span>  
  
- <span data-ttu-id="73117-108">Arcs</span><span class="sxs-lookup"><span data-stu-id="73117-108">Arcs</span></span>  
  
- <span data-ttu-id="73117-109">多边形</span><span class="sxs-lookup"><span data-stu-id="73117-109">Polygons</span></span>  
  
- <span data-ttu-id="73117-110">基数样条</span><span class="sxs-lookup"><span data-stu-id="73117-110">Cardinal splines</span></span>  
  
- <span data-ttu-id="73117-111">贝塞尔自由绘制曲线</span><span class="sxs-lookup"><span data-stu-id="73117-111">Bézier splines</span></span>  
  
 <span data-ttu-id="73117-112">在 GDI + 中，<xref:System.Drawing.Drawing2D.GraphicsPath>对象允许你收集到单个单元的一系列这些构建基块。</span><span class="sxs-lookup"><span data-stu-id="73117-112">In GDI+, the <xref:System.Drawing.Drawing2D.GraphicsPath> object allows you to collect a sequence of these building blocks into a single unit.</span></span> <span data-ttu-id="73117-113">然后可调用一次绘制线条、 矩形、 多边形和曲线的整个序列<xref:System.Drawing.Graphics.DrawPath%2A>方法的<xref:System.Drawing.Graphics>类。</span><span class="sxs-lookup"><span data-stu-id="73117-113">The entire sequence of lines, rectangles, polygons, and curves can then be drawn with one call to the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="73117-114">下图显示了通过结合一行、 一段弧线、 贝塞尔样条和的基数样条创建的路径。</span><span class="sxs-lookup"><span data-stu-id="73117-114">The following illustration shows a path created by combining a line, an arc, a Bézier spline, and a cardinal spline.</span></span>  
  
 <span data-ttu-id="73117-115">![Path](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span><span class="sxs-lookup"><span data-stu-id="73117-115">![Path](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span></span>  
  
## <a name="using-a-path"></a><span data-ttu-id="73117-116">使用路径</span><span class="sxs-lookup"><span data-stu-id="73117-116">Using a Path</span></span>  
 <span data-ttu-id="73117-117"><xref:System.Drawing.Drawing2D.GraphicsPath>类提供了用于创建一系列要绘制的项的以下方法： <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>， <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>， <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>， <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>， <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>， <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> （对于基本样条），和<xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>。</span><span class="sxs-lookup"><span data-stu-id="73117-117">The <xref:System.Drawing.Drawing2D.GraphicsPath> class provides the following methods for creating a sequence of items to be drawn: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (for cardinal splines), and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span></span> <span data-ttu-id="73117-118">每种方法将重载;也就是说，每个方法支持多个不同的参数列表。</span><span class="sxs-lookup"><span data-stu-id="73117-118">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="73117-119">例如，一种<xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>方法将收到四个整数和的另一种变体<xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>方法接收两个<xref:System.Drawing.Point>对象。</span><span class="sxs-lookup"><span data-stu-id="73117-119">For example, one variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives four integers, and another variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="73117-120">添加到路径的线条、 矩形和贝塞尔自由绘制曲线的方法具有复数形式的伴随方法，可将多个项添加到单个调用中的路径： <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>， <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>，和<xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>。</span><span class="sxs-lookup"><span data-stu-id="73117-120">The methods for adding lines, rectangles, and Bézier splines to a path have plural companion methods that add several items to the path in a single call: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span></span> <span data-ttu-id="73117-121">此外，<xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>并<xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>方法有伴随方法<xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A>和<xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>，将闭合的曲线或饼图添加到路径。</span><span class="sxs-lookup"><span data-stu-id="73117-121">Also, the <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> methods have companion methods, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, that add a closed curve or pie to the path.</span></span>  
  
 <span data-ttu-id="73117-122">若要绘制的路径，你需要<xref:System.Drawing.Graphics>对象，<xref:System.Drawing.Pen>对象，和一个<xref:System.Drawing.Drawing2D.GraphicsPath>对象。</span><span class="sxs-lookup"><span data-stu-id="73117-122">To draw a path, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="73117-123"><xref:System.Drawing.Graphics>对象提供<xref:System.Drawing.Graphics.DrawPath%2A>方法，和<xref:System.Drawing.Pen>对象将存储属性，例如宽度和用于呈现路径的线条颜色。</span><span class="sxs-lookup"><span data-stu-id="73117-123">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPath%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the path.</span></span> <span data-ttu-id="73117-124"><xref:System.Drawing.Drawing2D.GraphicsPath>对象将存储的一系列直线和曲线构成的路径。</span><span class="sxs-lookup"><span data-stu-id="73117-124">The <xref:System.Drawing.Drawing2D.GraphicsPath> object stores the sequence of lines and curves that make up the path.</span></span> <span data-ttu-id="73117-125"><xref:System.Drawing.Pen>对象和<xref:System.Drawing.Drawing2D.GraphicsPath>对象将作为参数传递给<xref:System.Drawing.Graphics.DrawPath%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="73117-125">The <xref:System.Drawing.Pen> object and the <xref:System.Drawing.Drawing2D.GraphicsPath> object are passed as arguments to the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="73117-126">下面的示例绘制线条、 椭圆和的贝塞尔样条组成的路径：</span><span class="sxs-lookup"><span data-stu-id="73117-126">The following example draws a path that consists of a line, an ellipse, and a Bézier spline:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#101](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 <span data-ttu-id="73117-127">下图显示的路径。</span><span class="sxs-lookup"><span data-stu-id="73117-127">The following illustration shows the path.</span></span>  
  
 <span data-ttu-id="73117-128">![Path](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span><span class="sxs-lookup"><span data-stu-id="73117-128">![Path](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span></span>  
  
 <span data-ttu-id="73117-129">除了添加线条、 矩形和曲线的路径，可以将路径添加到路径。</span><span class="sxs-lookup"><span data-stu-id="73117-129">In addition to adding lines, rectangles, and curves to a path, you can add paths to a path.</span></span> <span data-ttu-id="73117-130">这可以合并现有路径以形成复杂的长路径。</span><span class="sxs-lookup"><span data-stu-id="73117-130">This allows you to combine existing paths to form large, complex paths.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#102](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 <span data-ttu-id="73117-131">有两个可以向路径添加其他项： 字符串和饼图。</span><span class="sxs-lookup"><span data-stu-id="73117-131">There are two other items you can add to a path: strings and pies.</span></span> <span data-ttu-id="73117-132">饼图是内部的椭圆的一部分。</span><span class="sxs-lookup"><span data-stu-id="73117-132">A pie is a portion of the interior of an ellipse.</span></span> <span data-ttu-id="73117-133">下面的示例创建一个路径，从一段弧线、 基数样条、 字符串和饼图：</span><span class="sxs-lookup"><span data-stu-id="73117-133">The following example creates a path from an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#103](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 <span data-ttu-id="73117-134">下图显示的路径。</span><span class="sxs-lookup"><span data-stu-id="73117-134">The following illustration shows the path.</span></span> <span data-ttu-id="73117-135">请注意，路径不需要连接;分隔弧线、 基数样条、 字符串和饼图。</span><span class="sxs-lookup"><span data-stu-id="73117-135">Note that a path does not have to be connected; the arc, cardinal spline, string, and pie are separated.</span></span>  
  
 <span data-ttu-id="73117-136">![Paths](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span><span class="sxs-lookup"><span data-stu-id="73117-136">![Paths](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73117-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="73117-137">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [<span data-ttu-id="73117-138">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="73117-138">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="73117-139">如何：创建用于绘制图形对象</span><span class="sxs-lookup"><span data-stu-id="73117-139">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="73117-140">构造并绘制路径</span><span class="sxs-lookup"><span data-stu-id="73117-140">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
