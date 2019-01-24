---
title: 如何：绘制基数样条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
ms.openlocfilehash: 9f2fd0f54c95ff2185c1a1d17785d300c97f7f4f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739795"
---
# <a name="how-to-draw-cardinal-splines"></a><span data-ttu-id="2a78f-102">如何：绘制基数样条</span><span class="sxs-lookup"><span data-stu-id="2a78f-102">How to: Draw Cardinal Splines</span></span>
<span data-ttu-id="2a78f-103">基数样条是平滑地通过一组给定的点的曲线。</span><span class="sxs-lookup"><span data-stu-id="2a78f-103">A cardinal spline is a curve that passes smoothly through a given set of points.</span></span> <span data-ttu-id="2a78f-104">若要绘制的基数样条，创建<xref:System.Drawing.Graphics>对象并将传递指向数组的地址<xref:System.Drawing.Graphics.DrawCurve%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="2a78f-104">To draw a cardinal spline, create a <xref:System.Drawing.Graphics> object and pass the address of an array of points to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span>  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a><span data-ttu-id="2a78f-105">绘制钟形基数样条</span><span class="sxs-lookup"><span data-stu-id="2a78f-105">Drawing a Bell-Shaped Cardinal Spline</span></span>  
  
-   <span data-ttu-id="2a78f-106">下面的示例绘制的钟形基数样条通过五个指定点。</span><span class="sxs-lookup"><span data-stu-id="2a78f-106">The following example draws a bell-shaped cardinal spline that passes through five designated points.</span></span> <span data-ttu-id="2a78f-107">下图显示了曲线和五个点。</span><span class="sxs-lookup"><span data-stu-id="2a78f-107">The following illustration shows the curve and five points.</span></span>  
  
     <span data-ttu-id="2a78f-108">![基数样条曲线](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")</span><span class="sxs-lookup"><span data-stu-id="2a78f-108">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a><span data-ttu-id="2a78f-109">绘制闭合的基数样条</span><span class="sxs-lookup"><span data-stu-id="2a78f-109">Drawing a Closed Cardinal Spline</span></span>  
  
-   <span data-ttu-id="2a78f-110">使用<xref:System.Drawing.Graphics.DrawClosedCurve%2A>方法的<xref:System.Drawing.Graphics>类来绘制闭合基数样条。</span><span class="sxs-lookup"><span data-stu-id="2a78f-110">Use the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method of the <xref:System.Drawing.Graphics> class to draw a closed cardinal spline.</span></span> <span data-ttu-id="2a78f-111">闭合的基数样条曲线持续到数组中的最后一个点并向数组中的第一个点连接。</span><span class="sxs-lookup"><span data-stu-id="2a78f-111">In a closed cardinal spline, the curve continues through the last point in the array and connects with the first point in the array.</span></span> <span data-ttu-id="2a78f-112">下面的示例绘制通过六个指定点的闭合基数样条。</span><span class="sxs-lookup"><span data-stu-id="2a78f-112">The following example draws a closed cardinal spline that passes through six designated points.</span></span> <span data-ttu-id="2a78f-113">下图显示了已关闭的样条曲线和六个点。</span><span class="sxs-lookup"><span data-stu-id="2a78f-113">The following illustration shows the closed spline along with the six points.</span></span>  
  
 <span data-ttu-id="2a78f-114">![基数样条曲线](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")</span><span class="sxs-lookup"><span data-stu-id="2a78f-114">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a><span data-ttu-id="2a78f-115">更改基数样条曲线的弯曲</span><span class="sxs-lookup"><span data-stu-id="2a78f-115">Changing the Bend of a Cardinal Spline</span></span>  
  
-   <span data-ttu-id="2a78f-116">更改的基数样条弯曲的张力自变量表示通过方式<xref:System.Drawing.Graphics.DrawCurve%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="2a78f-116">Change the way a cardinal spline bends by passing a tension argument to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span> <span data-ttu-id="2a78f-117">下面的示例绘制三个传递一组相同的点的基数样条。</span><span class="sxs-lookup"><span data-stu-id="2a78f-117">The following example draws three cardinal splines that pass through the same set of points.</span></span> <span data-ttu-id="2a78f-118">下图显示了其张力值以及三个自由绘制曲线。</span><span class="sxs-lookup"><span data-stu-id="2a78f-118">The following illustration shows the three splines along with their tension values.</span></span> <span data-ttu-id="2a78f-119">请注意张力为 0 时, 点由直线连接。</span><span class="sxs-lookup"><span data-stu-id="2a78f-119">Note that when the tension is 0, the points are connected by straight lines.</span></span>  
  
 <span data-ttu-id="2a78f-120">![基数样条曲线](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")</span><span class="sxs-lookup"><span data-stu-id="2a78f-120">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2a78f-121">编译代码</span><span class="sxs-lookup"><span data-stu-id="2a78f-121">Compiling the Code</span></span>  
 <span data-ttu-id="2a78f-122">前面的示例设计为使用 Windows 窗体，它们需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="2a78f-122">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a78f-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a78f-123">See also</span></span>
- [<span data-ttu-id="2a78f-124">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="2a78f-124">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)
- [<span data-ttu-id="2a78f-125">构造并绘制曲线</span><span class="sxs-lookup"><span data-stu-id="2a78f-125">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
