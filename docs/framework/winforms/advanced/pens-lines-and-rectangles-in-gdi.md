---
title: GDI+ 中的笔、直线和矩形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines
- GDI+, lines
- drawing [Windows Forms], rectangles
- rectangles
- drawing [Windows Forms], lines
- GDI+, pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- GDI+, rectangles
- examples [Windows Forms], GDI+
- lines [Windows Forms], dashed
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
ms.openlocfilehash: 91f41fb4acf5ec174bd76498a70aed3dcda076f9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705735"
---
# <a name="pens-lines-and-rectangles-in-gdi"></a><span data-ttu-id="5b3a0-102">GDI+ 中的笔、直线和矩形</span><span class="sxs-lookup"><span data-stu-id="5b3a0-102">Pens, Lines, and Rectangles in GDI+</span></span>
<span data-ttu-id="5b3a0-103">若要绘制的线条[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]你需要创建<xref:System.Drawing.Graphics>对象和一个<xref:System.Drawing.Pen>对象。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-103">To draw lines with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] you need to create a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="5b3a0-104"><xref:System.Drawing.Graphics>对象提供的实际执行绘制操作的方法和<xref:System.Drawing.Pen>对象将存储属性，例如线条颜色、 宽度和样式。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-104">The <xref:System.Drawing.Graphics> object provides the methods that actually do the drawing, and the <xref:System.Drawing.Pen> object stores attributes, such as line color, width, and style.</span></span>  
  
## <a name="drawing-a-line"></a><span data-ttu-id="5b3a0-105">绘制一条线</span><span class="sxs-lookup"><span data-stu-id="5b3a0-105">Drawing a Line</span></span>  
 <span data-ttu-id="5b3a0-106">若要绘制一条线，请调用<xref:System.Drawing.Graphics.DrawLine%2A>方法的<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-106">To draw a line, call the <xref:System.Drawing.Graphics.DrawLine%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="5b3a0-107"><xref:System.Drawing.Pen>对象作为一个自变量传递<xref:System.Drawing.Graphics.DrawLine%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method.</span></span> <span data-ttu-id="5b3a0-108">下面的示例将行从点 （4，2） 绘制到点 （12，6）：</span><span class="sxs-lookup"><span data-stu-id="5b3a0-108">The following example draws a line from the point (4, 2) to the point (12, 6):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#41](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <span data-ttu-id="5b3a0-109"><xref:System.Drawing.Graphics.DrawLine%2A> 是一种重载的方法<xref:System.Drawing.Graphics>类，因此有几种方法可以提供该文件使用的参数。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-109"><xref:System.Drawing.Graphics.DrawLine%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="5b3a0-110">例如，构造两个<xref:System.Drawing.Point>对象并传递<xref:System.Drawing.Point>对象作为自变量到<xref:System.Drawing.Graphics.DrawLine%2A>方法：</span><span class="sxs-lookup"><span data-stu-id="5b3a0-110">For example, you can construct two <xref:System.Drawing.Point> objects and pass the <xref:System.Drawing.Point> objects as arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#42](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a><span data-ttu-id="5b3a0-111">构造笔</span><span class="sxs-lookup"><span data-stu-id="5b3a0-111">Constructing a Pen</span></span>  
 <span data-ttu-id="5b3a0-112">在构造时，可以指定某些属性<xref:System.Drawing.Pen>对象。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-112">You can specify certain attributes when you construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="5b3a0-113">例如，一个`Pen`构造函数允许您指定颜色和宽度。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-113">For example, one `Pen` constructor allows you to specify color and width.</span></span> <span data-ttu-id="5b3a0-114">下面的示例绘制一条蓝线的宽度为 2 从 （0，0） 到 （60，30）：</span><span class="sxs-lookup"><span data-stu-id="5b3a0-114">The following example draws a blue line of width 2 from (0, 0) to (60, 30):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#43](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a><span data-ttu-id="5b3a0-115">虚线和线帽</span><span class="sxs-lookup"><span data-stu-id="5b3a0-115">Dashed Lines and Line Caps</span></span>  
 <span data-ttu-id="5b3a0-116"><xref:System.Drawing.Pen>对象还公开属性，如<xref:System.Drawing.Pen.DashStyle%2A>，可用于指定行的功能。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-116">The <xref:System.Drawing.Pen> object also exposes properties, such as <xref:System.Drawing.Pen.DashStyle%2A>, that you can use to specify features of the line.</span></span> <span data-ttu-id="5b3a0-117">下面的示例绘制虚线从 （100，50） 到 （300，80）：</span><span class="sxs-lookup"><span data-stu-id="5b3a0-117">The following example draws a dashed line from (100, 50) to (300, 80):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#44](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 <span data-ttu-id="5b3a0-118">可以使用的属性<xref:System.Drawing.Pen>对象，以设置行的更多属性。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-118">You can use the properties of the <xref:System.Drawing.Pen> object to set many more attributes of the line.</span></span> <span data-ttu-id="5b3a0-119"><xref:System.Drawing.Pen.StartCap%2A>和<xref:System.Drawing.Pen.EndCap%2A>属性指定线条的端点的外观; 平面、 方形、 向上舍入、 三角形，可以是在结束或自定义形状。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-119">The <xref:System.Drawing.Pen.StartCap%2A> and <xref:System.Drawing.Pen.EndCap%2A> properties specify the appearance of the ends of the line; the ends can be flat, square, rounded, triangular, or a custom shape.</span></span> <span data-ttu-id="5b3a0-120"><xref:System.Drawing.Pen.LineJoin%2A>属性，可以指定连接的直线是斜 （联接以尖角）、 倾斜、 舍入，还是剪裁。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-120">The <xref:System.Drawing.Pen.LineJoin%2A> property lets you specify whether connected lines are mitered (joined with sharp corners), beveled, rounded, or clipped.</span></span> <span data-ttu-id="5b3a0-121">下图显示了具有线帽和联接的各种样式的行。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-121">The following illustration shows lines with various cap and join styles.</span></span>  
  
 <span data-ttu-id="5b3a0-122">![Lines](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span><span class="sxs-lookup"><span data-stu-id="5b3a0-122">![Lines](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span></span>  
  
## <a name="drawing-a-rectangle"></a><span data-ttu-id="5b3a0-123">绘制一个矩形</span><span class="sxs-lookup"><span data-stu-id="5b3a0-123">Drawing a Rectangle</span></span>  
 <span data-ttu-id="5b3a0-124">绘制矩形[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]类似于绘制线条。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-124">Drawing rectangles with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is similar to drawing lines.</span></span> <span data-ttu-id="5b3a0-125">若要绘制一个矩形，需要<xref:System.Drawing.Graphics>对象和一个<xref:System.Drawing.Pen>对象。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-125">To draw a rectangle, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="5b3a0-126"><xref:System.Drawing.Graphics>对象提供<xref:System.Drawing.Graphics.DrawRectangle%2A>方法，和<xref:System.Drawing.Pen>对象将存储属性，例如线条宽度和颜色。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-126">The <xref:System.Drawing.Graphics> object provides a <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as line width and color.</span></span> <span data-ttu-id="5b3a0-127"><xref:System.Drawing.Pen>对象作为一个自变量传递<xref:System.Drawing.Graphics.DrawRectangle%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-127">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method.</span></span> <span data-ttu-id="5b3a0-128">下面的示例绘制一个具有在其左上角的矩形 （100，50），宽度为 80，和高度为 40:</span><span class="sxs-lookup"><span data-stu-id="5b3a0-128">The following example draws a rectangle with its upper-left corner at (100, 50), a width of 80, and a height of 40:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#45](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <span data-ttu-id="5b3a0-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> 是一种重载的方法<xref:System.Drawing.Graphics>类，因此有几种方法可以提供该文件使用的参数。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="5b3a0-130">例如，可以构造<xref:System.Drawing.Rectangle>对象并将传递<xref:System.Drawing.Rectangle>对象传递给<xref:System.Drawing.Graphics.DrawRectangle%2A>作为参数的方法：</span><span class="sxs-lookup"><span data-stu-id="5b3a0-130">For example, you can construct a <xref:System.Drawing.Rectangle> object and pass the <xref:System.Drawing.Rectangle> object to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#46](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 <span data-ttu-id="5b3a0-131">一个<xref:System.Drawing.Rectangle>对象有方法和属性用于操作和收集有关该矩形的信息。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-131">A <xref:System.Drawing.Rectangle> object has methods and properties for manipulating and gathering information about the rectangle.</span></span> <span data-ttu-id="5b3a0-132">例如，<xref:System.Drawing.Rectangle.Inflate%2A>和<xref:System.Drawing.Rectangle.Offset%2A>方法更改的大小和位置的矩形。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-132">For example, the <xref:System.Drawing.Rectangle.Inflate%2A> and <xref:System.Drawing.Rectangle.Offset%2A> methods change the size and position of the rectangle.</span></span> <span data-ttu-id="5b3a0-133"><xref:System.Drawing.Rectangle.IntersectsWith%2A>方法指示矩形是否与另一个给定矩形和<xref:System.Drawing.Rectangle.Contains%2A>方法告诉您给定时的点是位于矩形内。</span><span class="sxs-lookup"><span data-stu-id="5b3a0-133">The <xref:System.Drawing.Rectangle.IntersectsWith%2A> method tells you whether the rectangle intersects another given rectangle, and the <xref:System.Drawing.Rectangle.Contains%2A> method tells you whether a given point is inside the rectangle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b3a0-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b3a0-134">See also</span></span>
- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- [<span data-ttu-id="5b3a0-135">如何：创建钢笔</span><span class="sxs-lookup"><span data-stu-id="5b3a0-135">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="5b3a0-136">如何：Windows 窗体上绘制线条</span><span class="sxs-lookup"><span data-stu-id="5b3a0-136">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)
- [<span data-ttu-id="5b3a0-137">如何：绘制空心的形状</span><span class="sxs-lookup"><span data-stu-id="5b3a0-137">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)
