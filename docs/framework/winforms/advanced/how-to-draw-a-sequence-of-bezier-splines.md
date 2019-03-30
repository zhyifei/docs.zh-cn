---
title: 如何：绘制序列的 B&#233;zier 自由绘制曲线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
ms.openlocfilehash: 2b74b03137d5a450fb1e436a514877d1a17229ad
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "58654245"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a><span data-ttu-id="f80c1-102">如何：绘制序列的 B&#233;zier 自由绘制曲线</span><span class="sxs-lookup"><span data-stu-id="f80c1-102">How to: Draw a Sequence of B&#233;zier Splines</span></span>
<span data-ttu-id="f80c1-103">可以使用<xref:System.Drawing.Graphics.DrawBeziers%2A>方法的<xref:System.Drawing.Graphics>类要绘制一系列连接贝塞尔自由绘制曲线。</span><span class="sxs-lookup"><span data-stu-id="f80c1-103">You can use the <xref:System.Drawing.Graphics.DrawBeziers%2A> method of the <xref:System.Drawing.Graphics> class to draw a sequence of connected Bézier splines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f80c1-104">示例</span><span class="sxs-lookup"><span data-stu-id="f80c1-104">Example</span></span>  
 <span data-ttu-id="f80c1-105">下面的示例绘制包含两个已连接的贝塞尔样条曲线。</span><span class="sxs-lookup"><span data-stu-id="f80c1-105">The following example draws a curve that consists of two connected Bézier splines.</span></span> <span data-ttu-id="f80c1-106">第一个贝塞尔样条的终结点是第二个贝塞尔自由绘制曲线的起始点。</span><span class="sxs-lookup"><span data-stu-id="f80c1-106">The endpoint of the first Bézier spline is the start point of the second Bézier spline.</span></span>  
  
 <span data-ttu-id="f80c1-107">下图显示了七个点以及已连接的自由绘制曲线：</span><span class="sxs-lookup"><span data-stu-id="f80c1-107">The following illustration shows the connected splines along with the seven points:</span></span>  
  
 ![图形的显示七个点以及已连接的样条。](./media/how-to-draw-a-sequence-of-bezier-splines/bezier-spline-seven-points.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f80c1-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="f80c1-109">Compiling the Code</span></span>  
 <span data-ttu-id="f80c1-110">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="f80c1-110">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f80c1-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="f80c1-111">See also</span></span>
- [<span data-ttu-id="f80c1-112">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="f80c1-112">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="f80c1-113">GDI+ 中的贝塞尔自由绘制曲线</span><span class="sxs-lookup"><span data-stu-id="f80c1-113">Bézier Splines in GDI+</span></span>](bezier-splines-in-gdi.md)
- [<span data-ttu-id="f80c1-114">构造并绘制曲线</span><span class="sxs-lookup"><span data-stu-id="f80c1-114">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
