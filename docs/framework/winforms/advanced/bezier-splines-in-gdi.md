---
title: "B &#233; zier GDI + 中样条"
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
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 52cead578ad03052b5734c5b7a5b5a897dd48732
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="b233zier-splines-in-gdi"></a><span data-ttu-id="0747d-102">B &#233; zier GDI + 中样条</span><span class="sxs-lookup"><span data-stu-id="0747d-102">B&#233;zier Splines in GDI+</span></span>
<span data-ttu-id="0747d-103">贝塞尔样条是由四个点指定的曲线： 两个终结点 （p1 和 p2） 和两个控点 （c1 和 c2）。</span><span class="sxs-lookup"><span data-stu-id="0747d-103">A Bézier spline is a curve specified by four points: two end points (p1 and p2) and two control points (c1 and c2).</span></span> <span data-ttu-id="0747d-104">曲线开始于 p1 和 p2 结束。</span><span class="sxs-lookup"><span data-stu-id="0747d-104">The curve begins at p1 and ends at p2.</span></span> <span data-ttu-id="0747d-105">曲线不会遍历控点，但控制点的作用像磁铁一样，在某些方向上拉拽曲线和影响曲线弯曲的方式。</span><span class="sxs-lookup"><span data-stu-id="0747d-105">The curve does not pass through the control points, but the control points act as magnets, pulling the curve in certain directions and influencing the way the curve bends.</span></span> <span data-ttu-id="0747d-106">下图显示其终结点和控制点的贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="0747d-106">The following illustration shows a Bézier curve along with its endpoints and control points.</span></span>  
  
 <span data-ttu-id="0747d-107">![贝塞尔曲线样条](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span><span class="sxs-lookup"><span data-stu-id="0747d-107">![Bezier Splines](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span></span>  
  
 <span data-ttu-id="0747d-108">曲线开始 p1、 抵达控件点 c1。</span><span class="sxs-lookup"><span data-stu-id="0747d-108">The curve starts at p1 and moves toward the control point c1.</span></span> <span data-ttu-id="0747d-109">为在 p1 曲线切线是从 p1 到 c1 绘制的行。</span><span class="sxs-lookup"><span data-stu-id="0747d-109">The tangent line to the curve at p1 is the line drawn from p1 to c1.</span></span> <span data-ttu-id="0747d-110">终结点 p2 处的切线是从 c2 绘制到 p2 的行。</span><span class="sxs-lookup"><span data-stu-id="0747d-110">The tangent line at the endpoint p2 is the line drawn from c2 to p2.</span></span>  
  
## <a name="drawing-bzier-splines"></a><span data-ttu-id="0747d-111">绘制贝塞尔样条</span><span class="sxs-lookup"><span data-stu-id="0747d-111">Drawing Bézier Splines</span></span>  
 <span data-ttu-id="0747d-112">若要绘制的贝塞尔样条，你需要的实例<xref:System.Drawing.Graphics>类和一个<xref:System.Drawing.Pen>。</span><span class="sxs-lookup"><span data-stu-id="0747d-112">To draw a Bézier spline, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Pen>.</span></span> <span data-ttu-id="0747d-113">实例<xref:System.Drawing.Graphics>类提供<xref:System.Drawing.Graphics.DrawBezier%2A>方法，与<xref:System.Drawing.Pen>存储特性，如宽度和用于呈现曲线的线条颜色。</span><span class="sxs-lookup"><span data-stu-id="0747d-113">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawBezier%2A> method, and the <xref:System.Drawing.Pen> stores attributes, such as width and color, of the line used to render the curve.</span></span> <span data-ttu-id="0747d-114"><xref:System.Drawing.Pen>作为一个自变量传递<xref:System.Drawing.Graphics.DrawBezier%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="0747d-114">The <xref:System.Drawing.Pen> is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawBezier%2A> method.</span></span> <span data-ttu-id="0747d-115">其余的自变量传递给<xref:System.Drawing.Graphics.DrawBezier%2A>方法是终结点和的控制点。</span><span class="sxs-lookup"><span data-stu-id="0747d-115">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawBezier%2A> method are the endpoints and the control points.</span></span> <span data-ttu-id="0747d-116">下面的示例绘制的起始点 （0，0） 的贝塞尔样条控制点 （40，20） 和 （80、 150） 和结束点 （100，10）：</span><span class="sxs-lookup"><span data-stu-id="0747d-116">The following example draws a Bézier spline with starting point (0, 0), control points (40, 20) and (80, 150), and ending point (100, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 <span data-ttu-id="0747d-117">下图显示曲线、 控点、 和两条切线。</span><span class="sxs-lookup"><span data-stu-id="0747d-117">The following illustration shows the curve, the control points, and two tangent lines.</span></span>  
  
 <span data-ttu-id="0747d-118">![贝塞尔曲线样条](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span><span class="sxs-lookup"><span data-stu-id="0747d-118">![Bezier Splines](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span></span>  
  
 <span data-ttu-id="0747d-119">贝塞尔样条最初已由圣皮埃尔贝塞尔汽车行业中用于设计开发。</span><span class="sxs-lookup"><span data-stu-id="0747d-119">Bézier splines were originally developed by Pierre Bézier for design in the automotive industry.</span></span> <span data-ttu-id="0747d-120">它们证明了可在许多类型的计算机辅助设计和也用于定义字体的轮廓。</span><span class="sxs-lookup"><span data-stu-id="0747d-120">They have since proven to be useful in many types of computer-aided design and are also used to define the outlines of fonts.</span></span> <span data-ttu-id="0747d-121">贝塞尔样条可以产生各种形状，其中一些下面的图中所示。</span><span class="sxs-lookup"><span data-stu-id="0747d-121">Bézier splines can yield a wide variety of shapes, some of which are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="0747d-122">![路径](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span><span class="sxs-lookup"><span data-stu-id="0747d-122">![Paths](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0747d-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0747d-123">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [<span data-ttu-id="0747d-124">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="0747d-124">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="0747d-125">构造并绘制曲线</span><span class="sxs-lookup"><span data-stu-id="0747d-125">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)  
 [<span data-ttu-id="0747d-126">如何：创建用于绘制的图形对象</span><span class="sxs-lookup"><span data-stu-id="0747d-126">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="0747d-127">如何：创建笔</span><span class="sxs-lookup"><span data-stu-id="0747d-127">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
