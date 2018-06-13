---
title: 如何： 绘制序列的 B&#233;zier 样条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
ms.openlocfilehash: 8439e08109630b9a59c8e0359aa4d18e5241412c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521402"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a><span data-ttu-id="4dc5e-102">如何： 绘制序列的 B&#233;zier 样条</span><span class="sxs-lookup"><span data-stu-id="4dc5e-102">How to: Draw a Sequence of B&#233;zier Splines</span></span>
<span data-ttu-id="4dc5e-103">你可以使用<xref:System.Drawing.Graphics.DrawBeziers%2A>方法<xref:System.Drawing.Graphics>类绘制一系列连接贝塞尔样条。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-103">You can use the <xref:System.Drawing.Graphics.DrawBeziers%2A> method of the <xref:System.Drawing.Graphics> class to draw a sequence of connected Bézier splines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4dc5e-104">示例</span><span class="sxs-lookup"><span data-stu-id="4dc5e-104">Example</span></span>  
 <span data-ttu-id="4dc5e-105">下面的示例绘制包含两个连接的贝塞尔样条曲线。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-105">The following example draws a curve that consists of two connected Bézier splines.</span></span> <span data-ttu-id="4dc5e-106">第一个贝塞尔样条的终结点是第二个贝塞尔样条的起始点。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-106">The endpoint of the first Bézier spline is the start point of the second Bézier spline.</span></span>  
  
 <span data-ttu-id="4dc5e-107">下图显示以及七个点相连的样条。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-107">The following illustration shows the connected splines along with the seven points.</span></span>  
  
 <span data-ttu-id="4dc5e-108">![贝塞尔样条](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")</span><span class="sxs-lookup"><span data-stu-id="4dc5e-108">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4dc5e-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="4dc5e-109">Compiling the Code</span></span>  
 <span data-ttu-id="4dc5e-110">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-110">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dc5e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="4dc5e-111">See Also</span></span>  
 [<span data-ttu-id="4dc5e-112">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="4dc5e-112">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="4dc5e-113">GDI+ 中的贝塞尔自由绘制曲线</span><span class="sxs-lookup"><span data-stu-id="4dc5e-113">Bézier Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [<span data-ttu-id="4dc5e-114">构造并绘制曲线</span><span class="sxs-lookup"><span data-stu-id="4dc5e-114">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
