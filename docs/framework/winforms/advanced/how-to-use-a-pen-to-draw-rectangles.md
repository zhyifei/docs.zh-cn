---
title: "如何：使用钢笔绘制矩形"
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
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 032f53ffe3bccd329b3e2eea4fbf13949f35c3cd
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a><span data-ttu-id="4ae40-102">如何：使用钢笔绘制矩形</span><span class="sxs-lookup"><span data-stu-id="4ae40-102">How to: Use a Pen to Draw Rectangles</span></span>
<span data-ttu-id="4ae40-103">若要绘制的矩形，你需要<xref:System.Drawing.Graphics>对象和一个<xref:System.Drawing.Pen>对象。</span><span class="sxs-lookup"><span data-stu-id="4ae40-103">To draw rectangles, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="4ae40-104"><xref:System.Drawing.Graphics>对象提供<xref:System.Drawing.Graphics.DrawRectangle%2A>方法，与<xref:System.Drawing.Pen>对象存储在行中，如颜色和宽度的功能。</span><span class="sxs-lookup"><span data-stu-id="4ae40-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ae40-105">示例</span><span class="sxs-lookup"><span data-stu-id="4ae40-105">Example</span></span>  
 <span data-ttu-id="4ae40-106">下面的示例绘制一个具有在其左上角的矩形 （10，10）。</span><span class="sxs-lookup"><span data-stu-id="4ae40-106">The following example draws a rectangle with its upper-left corner at (10, 10).</span></span> <span data-ttu-id="4ae40-107">矩形的宽度为 100，50 的高度。</span><span class="sxs-lookup"><span data-stu-id="4ae40-107">The rectangle has a width of 100 and a height of 50.</span></span> <span data-ttu-id="4ae40-108">第二个参数传递给<xref:System.Drawing.Pen.%23ctor%2A>构造函数指示钢笔的宽度为 5 个像素。</span><span class="sxs-lookup"><span data-stu-id="4ae40-108">The second argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor indicates that the pen width is 5 pixels.</span></span>  
  
 <span data-ttu-id="4ae40-109">当绘制矩形时，触笔上居中显示矩形的边界。</span><span class="sxs-lookup"><span data-stu-id="4ae40-109">When the rectangle is drawn, the pen is centered on the rectangle's boundary.</span></span> <span data-ttu-id="4ae40-110">因为钢笔的宽度为 5，在该矩形两端均为绘制的 5 个像素宽，因此绘制 1 个像素在边界本身，2 个像素绘制内，和 2 个像素绘制在外部。</span><span class="sxs-lookup"><span data-stu-id="4ae40-110">Because the pen width is 5, the sides of the rectangle are drawn 5 pixels wide, such that 1 pixel is drawn on the boundary itself, 2 pixels are drawn on the inside, and 2 pixels are drawn on the outside.</span></span> <span data-ttu-id="4ae40-111">钢笔对齐方式的更多详细信息，请参阅[如何： 设置钢笔的宽度和对齐方式](../../../../docs/framework/winforms/advanced/how-to-set-pen-width-and-alignment.md)。</span><span class="sxs-lookup"><span data-stu-id="4ae40-111">For more details on pen alignment, see [How to: Set Pen Width and Alignment](../../../../docs/framework/winforms/advanced/how-to-set-pen-width-and-alignment.md).</span></span>  
  
 <span data-ttu-id="4ae40-112">下图显示生成的矩形。</span><span class="sxs-lookup"><span data-stu-id="4ae40-112">The following illustration shows the resulting rectangle.</span></span> <span data-ttu-id="4ae40-113">虚线显示其中矩形将绘制如果钢笔的宽度过一个像素。</span><span class="sxs-lookup"><span data-stu-id="4ae40-113">The dotted lines show where the rectangle would have been drawn if the pen width had been one pixel.</span></span> <span data-ttu-id="4ae40-114">矩形的左上角的放大的视图显示密集的黑色线条位于这些虚线。</span><span class="sxs-lookup"><span data-stu-id="4ae40-114">The enlarged view of the upper-left corner of the rectangle shows that the thick black lines are centered on those dotted lines.</span></span>  
  
 <span data-ttu-id="4ae40-115">![钢笔](../../../../docs/framework/winforms/advanced/media/pens1.gif "pens1")</span><span class="sxs-lookup"><span data-stu-id="4ae40-115">![Pens](../../../../docs/framework/winforms/advanced/media/pens1.gif "pens1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4ae40-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="4ae40-116">Compiling the Code</span></span>  
 <span data-ttu-id="4ae40-117">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="4ae40-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ae40-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ae40-118">See Also</span></span>  
 [<span data-ttu-id="4ae40-119">使用笔绘制直线和形状</span><span class="sxs-lookup"><span data-stu-id="4ae40-119">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
