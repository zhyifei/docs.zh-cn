---
title: "如何： 绘制单个 B &#233; zier 样条"
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
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0ebdba9e01824cc764a6ab759da049add180ba83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="cfa5e-102">如何： 绘制单个 B &#233; zier 样条</span><span class="sxs-lookup"><span data-stu-id="cfa5e-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="cfa5e-103">由四个点定义的贝塞尔样条： 起始点，这两个控制点，终结点。</span><span class="sxs-lookup"><span data-stu-id="cfa5e-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfa5e-104">示例</span><span class="sxs-lookup"><span data-stu-id="cfa5e-104">Example</span></span>  
 <span data-ttu-id="cfa5e-105">下面的示例绘制与 （10，100） 的起始点和终结点 （200，100） 的贝塞尔样条。</span><span class="sxs-lookup"><span data-stu-id="cfa5e-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="cfa5e-106">两个控制点 （100、 10） 和 （150，150）。</span><span class="sxs-lookup"><span data-stu-id="cfa5e-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="cfa5e-107">下图显示以及其起始点、 控点和终结点生成的贝塞尔样条。</span><span class="sxs-lookup"><span data-stu-id="cfa5e-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="cfa5e-108">该插图还显示样条的凸包，这是通过使用直线连接四个点而形成的多边形。</span><span class="sxs-lookup"><span data-stu-id="cfa5e-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 <span data-ttu-id="cfa5e-109">![贝塞尔样条](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span><span class="sxs-lookup"><span data-stu-id="cfa5e-109">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cfa5e-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="cfa5e-110">Compiling the Code</span></span>  
 <span data-ttu-id="cfa5e-111">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="cfa5e-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfa5e-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cfa5e-112">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawBezier%2A>  
 [<span data-ttu-id="cfa5e-113">GDI+ 中的贝塞尔自由绘制曲线</span><span class="sxs-lookup"><span data-stu-id="cfa5e-113">Bézier Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [<span data-ttu-id="cfa5e-114">如何：绘制一系列贝塞尔自由绘制曲线</span><span class="sxs-lookup"><span data-stu-id="cfa5e-114">How to: Draw a Sequence of Bézier Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)
