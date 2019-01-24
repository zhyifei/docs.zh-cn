---
title: GDI+ 中的椭圆和弧线
ms.date: 03/30/2017
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
ms.openlocfilehash: 93f82d35449c42772e9fbd1b7454364885b38769
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54697200"
---
# <a name="ellipses-and-arcs-in-gdi"></a><span data-ttu-id="fe87c-102">GDI+ 中的椭圆和弧线</span><span class="sxs-lookup"><span data-stu-id="fe87c-102">Ellipses and Arcs in GDI+</span></span>
<span data-ttu-id="fe87c-103">您可以轻松地绘制椭圆和弧线使用<xref:System.Drawing.Graphics.DrawEllipse%2A>并<xref:System.Drawing.Graphics.DrawArc%2A>方法的<xref:System.Drawing.Graphics>类。</span><span class="sxs-lookup"><span data-stu-id="fe87c-103">You can easily draw ellipses and arcs using the <xref:System.Drawing.Graphics.DrawEllipse%2A> and <xref:System.Drawing.Graphics.DrawArc%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="drawing-an-ellipse"></a><span data-ttu-id="fe87c-104">绘制椭圆</span><span class="sxs-lookup"><span data-stu-id="fe87c-104">Drawing an Ellipse</span></span>  
 <span data-ttu-id="fe87c-105">若要绘制一个椭圆，需要<xref:System.Drawing.Graphics>对象和一个<xref:System.Drawing.Pen>对象。</span><span class="sxs-lookup"><span data-stu-id="fe87c-105">To draw an ellipse, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="fe87c-106"><xref:System.Drawing.Graphics>对象提供<xref:System.Drawing.Graphics.DrawEllipse%2A>方法，和<xref:System.Drawing.Pen>对象将存储属性，例如宽度和颜色，用来呈现椭圆的行。</span><span class="sxs-lookup"><span data-stu-id="fe87c-106">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the ellipse.</span></span> <span data-ttu-id="fe87c-107"><xref:System.Drawing.Pen>对象作为一个自变量传递<xref:System.Drawing.Graphics.DrawEllipse%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="fe87c-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="fe87c-108">其余的参数传递给<xref:System.Drawing.Graphics.DrawEllipse%2A>方法指定角的椭圆的边框。</span><span class="sxs-lookup"><span data-stu-id="fe87c-108">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method specify the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="fe87c-109">下图显示一个椭圆，以及其边界的矩形。</span><span class="sxs-lookup"><span data-stu-id="fe87c-109">The following illustration shows an ellipse along with its bounding rectangle.</span></span>  
  
 <span data-ttu-id="fe87c-110">![椭圆和弧线](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span><span class="sxs-lookup"><span data-stu-id="fe87c-110">![Ellipses and arcs](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span></span>  
  
 <span data-ttu-id="fe87c-111">下面的示例绘制一个椭圆;边界矩形具有宽度为 80，高度为 40 和的左上角 （100，50）：</span><span class="sxs-lookup"><span data-stu-id="fe87c-111">The following example draws an ellipse; the bounding rectangle has a width of 80, a height of 40, and an upper-left corner of (100, 50):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <span data-ttu-id="fe87c-112"><xref:System.Drawing.Graphics.DrawEllipse%2A> 是一种重载的方法<xref:System.Drawing.Graphics>类，因此有几种方法可以提供该文件使用的参数。</span><span class="sxs-lookup"><span data-stu-id="fe87c-112"><xref:System.Drawing.Graphics.DrawEllipse%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="fe87c-113">例如，可以构造<xref:System.Drawing.Rectangle>并传递<xref:System.Drawing.Rectangle>到<xref:System.Drawing.Graphics.DrawEllipse%2A>作为参数的方法：</span><span class="sxs-lookup"><span data-stu-id="fe87c-113">For example, you can construct a <xref:System.Drawing.Rectangle> and pass the <xref:System.Drawing.Rectangle> to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#52](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a><span data-ttu-id="fe87c-114">绘制一段弧线，</span><span class="sxs-lookup"><span data-stu-id="fe87c-114">Drawing an Arc</span></span>  
 <span data-ttu-id="fe87c-115">一段弧线的椭圆的一部分。</span><span class="sxs-lookup"><span data-stu-id="fe87c-115">An arc is a portion of an ellipse.</span></span> <span data-ttu-id="fe87c-116">若要绘制一段弧线，则调用<xref:System.Drawing.Graphics.DrawArc%2A>方法的<xref:System.Drawing.Graphics>类。</span><span class="sxs-lookup"><span data-stu-id="fe87c-116">To draw an arc, you call the <xref:System.Drawing.Graphics.DrawArc%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="fe87c-117">参数<xref:System.Drawing.Graphics.DrawArc%2A>方法将与参数的相同<xref:System.Drawing.Graphics.DrawEllipse%2A>方法，不同之处在于<xref:System.Drawing.Graphics.DrawArc%2A>需要起始角度和扫描角度。</span><span class="sxs-lookup"><span data-stu-id="fe87c-117">The parameters of the <xref:System.Drawing.Graphics.DrawArc%2A> method are the same as the parameters of the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, except that <xref:System.Drawing.Graphics.DrawArc%2A> requires a starting angle and sweep angle.</span></span> <span data-ttu-id="fe87c-118">下面的示例绘制一段弧线，使用 30 度的起始角度和扫描角度为 180 度：</span><span class="sxs-lookup"><span data-stu-id="fe87c-118">The following example draws an arc with a starting angle of 30 degrees and a sweep angle of 180 degrees:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#53](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 <span data-ttu-id="fe87c-119">下图显示了弧线、 椭圆和边界的矩形。</span><span class="sxs-lookup"><span data-stu-id="fe87c-119">The following illustration shows the arc, the ellipse, and the bounding rectangle.</span></span>  
  
 <span data-ttu-id="fe87c-120">![椭圆和弧线](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span><span class="sxs-lookup"><span data-stu-id="fe87c-120">![Ellipses and arcs](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe87c-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe87c-121">See also</span></span>
- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="fe87c-122">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="fe87c-122">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)
- [<span data-ttu-id="fe87c-123">如何：创建用于绘制图形对象</span><span class="sxs-lookup"><span data-stu-id="fe87c-123">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="fe87c-124">如何：创建钢笔</span><span class="sxs-lookup"><span data-stu-id="fe87c-124">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
- [<span data-ttu-id="fe87c-125">如何：绘制空心的形状</span><span class="sxs-lookup"><span data-stu-id="fe87c-125">How to: Draw an Outlined Shape</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
