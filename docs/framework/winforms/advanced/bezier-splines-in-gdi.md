---
title: B&#233;zier GDI + 中的样条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
ms.openlocfilehash: 7648f7f9da72abea4bfc87603eea290614294eff
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707256"
---
# <a name="b233zier-splines-in-gdi"></a><span data-ttu-id="e525d-102">B&#233;zier GDI + 中的样条</span><span class="sxs-lookup"><span data-stu-id="e525d-102">B&#233;zier Splines in GDI+</span></span>
<span data-ttu-id="e525d-103">贝塞尔样条是由四个点指定的曲线： 两个终结点 （p1 和 p2） 和两个控点 （c1 和 c2）。</span><span class="sxs-lookup"><span data-stu-id="e525d-103">A Bézier spline is a curve specified by four points: two end points (p1 and p2) and two control points (c1 and c2).</span></span> <span data-ttu-id="e525d-104">曲线开始于 p1 和 p2 结束。</span><span class="sxs-lookup"><span data-stu-id="e525d-104">The curve begins at p1 and ends at p2.</span></span> <span data-ttu-id="e525d-105">曲线不会经历的控点，但控制点的作用像磁铁一样，在某些方向上拉拽曲线并影响曲线弯曲的方式。</span><span class="sxs-lookup"><span data-stu-id="e525d-105">The curve does not pass through the control points, but the control points act as magnets, pulling the curve in certain directions and influencing the way the curve bends.</span></span> <span data-ttu-id="e525d-106">下图显示了其终结点和控制点一个贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="e525d-106">The following illustration shows a Bézier curve along with its endpoints and control points.</span></span>  
  
 <span data-ttu-id="e525d-107">![贝塞尔自由绘制曲线](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span><span class="sxs-lookup"><span data-stu-id="e525d-107">![Bezier Splines](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span></span>  
  
 <span data-ttu-id="e525d-108">曲线开始 p1，会向管理点 c1 移动。</span><span class="sxs-lookup"><span data-stu-id="e525d-108">The curve starts at p1 and moves toward the control point c1.</span></span> <span data-ttu-id="e525d-109">为在 p1 曲线的切线是从 p1 到 c1 绘制的行。</span><span class="sxs-lookup"><span data-stu-id="e525d-109">The tangent line to the curve at p1 is the line drawn from p1 to c1.</span></span> <span data-ttu-id="e525d-110">终结点 p2 处的切线是从 c2 到 p2 绘制的行。</span><span class="sxs-lookup"><span data-stu-id="e525d-110">The tangent line at the endpoint p2 is the line drawn from c2 to p2.</span></span>  
  
## <a name="drawing-bzier-splines"></a><span data-ttu-id="e525d-111">绘制贝塞尔自由绘制曲线</span><span class="sxs-lookup"><span data-stu-id="e525d-111">Drawing Bézier Splines</span></span>  
 <span data-ttu-id="e525d-112">若要绘制的贝塞尔样条，您需要的实例<xref:System.Drawing.Graphics>类和一个<xref:System.Drawing.Pen>。</span><span class="sxs-lookup"><span data-stu-id="e525d-112">To draw a Bézier spline, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Pen>.</span></span> <span data-ttu-id="e525d-113">实例<xref:System.Drawing.Graphics>类提供了<xref:System.Drawing.Graphics.DrawBezier%2A>方法，和<xref:System.Drawing.Pen>存储属性，例如宽度和颜色，用来呈现曲线的行。</span><span class="sxs-lookup"><span data-stu-id="e525d-113">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawBezier%2A> method, and the <xref:System.Drawing.Pen> stores attributes, such as width and color, of the line used to render the curve.</span></span> <span data-ttu-id="e525d-114"><xref:System.Drawing.Pen>作为自变量之一传递<xref:System.Drawing.Graphics.DrawBezier%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="e525d-114">The <xref:System.Drawing.Pen> is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawBezier%2A> method.</span></span> <span data-ttu-id="e525d-115">其余的参数传递给<xref:System.Drawing.Graphics.DrawBezier%2A>方法是将终结点与管理点。</span><span class="sxs-lookup"><span data-stu-id="e525d-115">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawBezier%2A> method are the endpoints and the control points.</span></span> <span data-ttu-id="e525d-116">下面的示例绘制的起始点 （0，0） 的贝塞尔样条控制点 （40，20） 和 （80、 150） 和结束点 （10）：</span><span class="sxs-lookup"><span data-stu-id="e525d-116">The following example draws a Bézier spline with starting point (0, 0), control points (40, 20) and (80, 150), and ending point (100, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#71](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 <span data-ttu-id="e525d-117">下图显示了曲线、 控制点和两条切线。</span><span class="sxs-lookup"><span data-stu-id="e525d-117">The following illustration shows the curve, the control points, and two tangent lines.</span></span>  
  
 <span data-ttu-id="e525d-118">![贝塞尔自由绘制曲线](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span><span class="sxs-lookup"><span data-stu-id="e525d-118">![Bezier Splines](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span></span>  
  
 <span data-ttu-id="e525d-119">贝塞尔自由绘制曲线最初开发通过圣皮埃尔贝塞尔汽车行业中的设计。</span><span class="sxs-lookup"><span data-stu-id="e525d-119">Bézier splines were originally developed by Pierre Bézier for design in the automotive industry.</span></span> <span data-ttu-id="e525d-120">它们已被公认为许多类型的计算机辅助设计中很有用，也用于定义字体的大纲。</span><span class="sxs-lookup"><span data-stu-id="e525d-120">They have since proven to be useful in many types of computer-aided design and are also used to define the outlines of fonts.</span></span> <span data-ttu-id="e525d-121">贝塞尔样条可以产生各种形状，其中一些在下图中所示。</span><span class="sxs-lookup"><span data-stu-id="e525d-121">Bézier splines can yield a wide variety of shapes, some of which are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="e525d-122">![Paths](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span><span class="sxs-lookup"><span data-stu-id="e525d-122">![Paths](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e525d-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="e525d-123">See also</span></span>
- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="e525d-124">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="e525d-124">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="e525d-125">构造并绘制曲线</span><span class="sxs-lookup"><span data-stu-id="e525d-125">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
- [<span data-ttu-id="e525d-126">如何：创建用于绘制图形对象</span><span class="sxs-lookup"><span data-stu-id="e525d-126">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="e525d-127">如何：创建钢笔</span><span class="sxs-lookup"><span data-stu-id="e525d-127">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
