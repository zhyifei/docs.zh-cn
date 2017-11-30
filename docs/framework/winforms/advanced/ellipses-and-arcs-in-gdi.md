---
title: "GDI+ 中的椭圆和弧线"
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
- arcs
- GDI+, arcs
- drawing [Windows Forms], ellipses
- GDI+, ellipses
- ellipses
- drawing [Windows Forms], arcs
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5ebeae1d076a0ebcf36d52dee1af0c0ad5f04fdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ellipses-and-arcs-in-gdi"></a><span data-ttu-id="b55dc-102">GDI+ 中的椭圆和弧线</span><span class="sxs-lookup"><span data-stu-id="b55dc-102">Ellipses and Arcs in GDI+</span></span>
<span data-ttu-id="b55dc-103">您可以轻松地绘制椭圆和弧使用<xref:System.Drawing.Graphics.DrawEllipse%2A>和<xref:System.Drawing.Graphics.DrawArc%2A>方法<xref:System.Drawing.Graphics>类。</span><span class="sxs-lookup"><span data-stu-id="b55dc-103">You can easily draw ellipses and arcs using the <xref:System.Drawing.Graphics.DrawEllipse%2A> and <xref:System.Drawing.Graphics.DrawArc%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="drawing-an-ellipse"></a><span data-ttu-id="b55dc-104">绘制椭圆</span><span class="sxs-lookup"><span data-stu-id="b55dc-104">Drawing an Ellipse</span></span>  
 <span data-ttu-id="b55dc-105">若要绘制一个椭圆，你需要<xref:System.Drawing.Graphics>对象和一个<xref:System.Drawing.Pen>对象。</span><span class="sxs-lookup"><span data-stu-id="b55dc-105">To draw an ellipse, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="b55dc-106"><xref:System.Drawing.Graphics>对象提供<xref:System.Drawing.Graphics.DrawEllipse%2A>方法，与<xref:System.Drawing.Pen>对象存储特性，如宽度和用于呈现椭圆的线条颜色。</span><span class="sxs-lookup"><span data-stu-id="b55dc-106">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the ellipse.</span></span> <span data-ttu-id="b55dc-107"><xref:System.Drawing.Pen>对象作为一个自变量传递<xref:System.Drawing.Graphics.DrawEllipse%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="b55dc-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="b55dc-108">其余的自变量传递给<xref:System.Drawing.Graphics.DrawEllipse%2A>方法指定椭圆的边框。</span><span class="sxs-lookup"><span data-stu-id="b55dc-108">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method specify the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="b55dc-109">下图显示以及其边界的矩形的椭圆。</span><span class="sxs-lookup"><span data-stu-id="b55dc-109">The following illustration shows an ellipse along with its bounding rectangle.</span></span>  
  
 <span data-ttu-id="b55dc-110">![椭圆和弧](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span><span class="sxs-lookup"><span data-stu-id="b55dc-110">![Ellipses and arcs](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span></span>  
  
 <span data-ttu-id="b55dc-111">下面的示例绘制一个椭圆;边界的矩形的宽度为 80，高度为 40 和的左上角都 （100，50）：</span><span class="sxs-lookup"><span data-stu-id="b55dc-111">The following example draws an ellipse; the bounding rectangle has a width of 80, a height of 40, and an upper-left corner of (100, 50):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <span data-ttu-id="b55dc-112"><xref:System.Drawing.Graphics.DrawEllipse%2A>属于重载的方法的<xref:System.Drawing.Graphics>类，因此有几种方法，你可以向其提供自变量。</span><span class="sxs-lookup"><span data-stu-id="b55dc-112"><xref:System.Drawing.Graphics.DrawEllipse%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="b55dc-113">例如，可以构造<xref:System.Drawing.Rectangle>并将传递<xref:System.Drawing.Rectangle>到<xref:System.Drawing.Graphics.DrawEllipse%2A>作为自变量的方法：</span><span class="sxs-lookup"><span data-stu-id="b55dc-113">For example, you can construct a <xref:System.Drawing.Rectangle> and pass the <xref:System.Drawing.Rectangle> to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#52](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a><span data-ttu-id="b55dc-114">绘制一段弧线，</span><span class="sxs-lookup"><span data-stu-id="b55dc-114">Drawing an Arc</span></span>  
 <span data-ttu-id="b55dc-115">一段弧线，是椭圆的的一部分。</span><span class="sxs-lookup"><span data-stu-id="b55dc-115">An arc is a portion of an ellipse.</span></span> <span data-ttu-id="b55dc-116">若要绘制一段弧线，请调用<xref:System.Drawing.Graphics.DrawArc%2A>方法<xref:System.Drawing.Graphics>类。</span><span class="sxs-lookup"><span data-stu-id="b55dc-116">To draw an arc, you call the <xref:System.Drawing.Graphics.DrawArc%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="b55dc-117">参数<xref:System.Drawing.Graphics.DrawArc%2A>方法都是相同的参数作为<xref:System.Drawing.Graphics.DrawEllipse%2A>方法，只不过<xref:System.Drawing.Graphics.DrawArc%2A>需要起始角度和扫描角度。</span><span class="sxs-lookup"><span data-stu-id="b55dc-117">The parameters of the <xref:System.Drawing.Graphics.DrawArc%2A> method are the same as the parameters of the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, except that <xref:System.Drawing.Graphics.DrawArc%2A> requires a starting angle and sweep angle.</span></span> <span data-ttu-id="b55dc-118">下面的示例绘制一段弧线，使用 30 度起始角度和扫描角度为 180 度：</span><span class="sxs-lookup"><span data-stu-id="b55dc-118">The following example draws an arc with a starting angle of 30 degrees and a sweep angle of 180 degrees:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#53](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 <span data-ttu-id="b55dc-119">下图显示弧、 椭圆和的边框。</span><span class="sxs-lookup"><span data-stu-id="b55dc-119">The following illustration shows the arc, the ellipse, and the bounding rectangle.</span></span>  
  
 <span data-ttu-id="b55dc-120">![椭圆和弧](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span><span class="sxs-lookup"><span data-stu-id="b55dc-120">![Ellipses and arcs](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b55dc-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b55dc-121">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [<span data-ttu-id="b55dc-122">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="b55dc-122">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="b55dc-123">如何：创建用于绘制的图形对象</span><span class="sxs-lookup"><span data-stu-id="b55dc-123">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="b55dc-124">如何：创建笔</span><span class="sxs-lookup"><span data-stu-id="b55dc-124">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [<span data-ttu-id="b55dc-125">如何：绘制显示边框的形状</span><span class="sxs-lookup"><span data-stu-id="b55dc-125">How to: Draw an Outlined Shape</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
