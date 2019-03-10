---
title: 如何：绘制单个 B&#233;zier 样条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: 6fc4e12bb7532019a0571095263b5447e4b0d1ed
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702511"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="a033e-102">如何：绘制单个 B&#233;zier 样条</span><span class="sxs-lookup"><span data-stu-id="a033e-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="a033e-103">由四个点定义的贝塞尔样条： 一个起点，这两个控制点和终结点。</span><span class="sxs-lookup"><span data-stu-id="a033e-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a033e-104">示例</span><span class="sxs-lookup"><span data-stu-id="a033e-104">Example</span></span>  
 <span data-ttu-id="a033e-105">下面的示例绘制使用 （10，100） 的起始点和终结点 （200，100） 的贝塞尔样条。</span><span class="sxs-lookup"><span data-stu-id="a033e-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="a033e-106">两个控制点为 （100，10） 和 （150，150）。</span><span class="sxs-lookup"><span data-stu-id="a033e-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="a033e-107">下图显示了生成的贝塞尔样条以及其开始点、 控点和终结点。</span><span class="sxs-lookup"><span data-stu-id="a033e-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="a033e-108">该插图还显示自由绘制曲线的凸包，这是通过使用直线连接四个点而形成的多边形。</span><span class="sxs-lookup"><span data-stu-id="a033e-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 <span data-ttu-id="a033e-109">![Bezier Spline](./media/bezierspline1.png "BezierSpline1")</span><span class="sxs-lookup"><span data-stu-id="a033e-109">![Bezier Spline](./media/bezierspline1.png "BezierSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a033e-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="a033e-110">Compiling the Code</span></span>  
 <span data-ttu-id="a033e-111">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="a033e-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a033e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="a033e-112">See also</span></span>
- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [<span data-ttu-id="a033e-113">GDI+ 中的贝塞尔自由绘制曲线</span><span class="sxs-lookup"><span data-stu-id="a033e-113">Bézier Splines in GDI+</span></span>](bezier-splines-in-gdi.md)
- [<span data-ttu-id="a033e-114">如何：绘制一系列贝塞尔自由绘制曲线</span><span class="sxs-lookup"><span data-stu-id="a033e-114">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)
