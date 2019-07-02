---
title: GDI+ 中的开放曲线和闭合曲线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- curves [Windows Forms], filling
- GDI+, curves
- curves [Windows Forms], drawing
- curves
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
ms.openlocfilehash: 06afdc4549f7c3c9b0636e5c7052dcca87a153f1
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505450"
---
# <a name="open-and-closed-curves-in-gdi"></a><span data-ttu-id="ba3c7-102">GDI+ 中的开放曲线和闭合曲线</span><span class="sxs-lookup"><span data-stu-id="ba3c7-102">Open and Closed Curves in GDI+</span></span>
<span data-ttu-id="ba3c7-103">下图显示了两条曲线： 一个打开和关闭。</span><span class="sxs-lookup"><span data-stu-id="ba3c7-103">The following illustration shows two curves: one open and one closed.</span></span>  
  
 <span data-ttu-id="ba3c7-104">![开放曲线和闭合曲线](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span><span class="sxs-lookup"><span data-stu-id="ba3c7-104">![Open & Closed curves](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span></span>  
  
## <a name="managed-interface-for-curves"></a><span data-ttu-id="ba3c7-105">曲线的管理的界面</span><span class="sxs-lookup"><span data-stu-id="ba3c7-105">Managed Interface for Curves</span></span>  
 <span data-ttu-id="ba3c7-106">已关闭的曲线具有内部，因此可以使用画笔填充。</span><span class="sxs-lookup"><span data-stu-id="ba3c7-106">Closed curves have an interior and therefore can be filled with a brush.</span></span> <span data-ttu-id="ba3c7-107"><xref:System.Drawing.Graphics> GDI + 中的类提供了用于填充绘制闭合的形状和曲线的以下方法： <xref:System.Drawing.Graphics.FillRectangle%2A>， <xref:System.Drawing.Graphics.FillEllipse%2A>， <xref:System.Drawing.Graphics.FillPie%2A>， <xref:System.Drawing.Graphics.FillPolygon%2A>， <xref:System.Drawing.Graphics.FillClosedCurve%2A>， <xref:System.Drawing.Graphics.FillPath%2A>，和<xref:System.Drawing.Graphics.FillRegion%2A>。</span><span class="sxs-lookup"><span data-stu-id="ba3c7-107">The <xref:System.Drawing.Graphics> class in GDI+ provides the following methods for filling closed shapes and curves: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, and <xref:System.Drawing.Graphics.FillRegion%2A>.</span></span> <span data-ttu-id="ba3c7-108">无论您调用下列方法之一，您必须通过一个特定的画笔类型 (<xref:System.Drawing.SolidBrush>， <xref:System.Drawing.Drawing2D.HatchBrush>， <xref:System.Drawing.TextureBrush>， <xref:System.Drawing.Drawing2D.LinearGradientBrush>，或<xref:System.Drawing.Drawing2D.PathGradientBrush>) 作为参数。</span><span class="sxs-lookup"><span data-stu-id="ba3c7-108">Whenever you call one of these methods, you must pass one of the specific brush types (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, or <xref:System.Drawing.Drawing2D.PathGradientBrush>) as an argument.</span></span>  
  
 <span data-ttu-id="ba3c7-109"><xref:System.Drawing.Graphics.FillPie%2A>方法是一起提供<xref:System.Drawing.Graphics.DrawArc%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="ba3c7-109">The <xref:System.Drawing.Graphics.FillPie%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawArc%2A> method.</span></span> <span data-ttu-id="ba3c7-110">就像<xref:System.Drawing.Graphics.DrawArc%2A>方法绘制的椭圆的边框的一部分<xref:System.Drawing.Graphics.FillPie%2A>方法填充的椭圆的内部的一部分。</span><span class="sxs-lookup"><span data-stu-id="ba3c7-110">Just as the <xref:System.Drawing.Graphics.DrawArc%2A> method draws a portion of the outline of an ellipse, the <xref:System.Drawing.Graphics.FillPie%2A> method fills a portion of the interior of an ellipse.</span></span> <span data-ttu-id="ba3c7-111">下面的示例绘制一段弧线，并填充椭圆的内部的相应部分：</span><span class="sxs-lookup"><span data-stu-id="ba3c7-111">The following example draws an arc and fills the corresponding portion of the interior of the ellipse:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#21](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 <span data-ttu-id="ba3c7-112">下图显示了弧线和已填充的饼图。</span><span class="sxs-lookup"><span data-stu-id="ba3c7-112">The following illustration shows the arc and the filled pie.</span></span>  
  
 <span data-ttu-id="ba3c7-113">![开放曲线和闭合曲线](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span><span class="sxs-lookup"><span data-stu-id="ba3c7-113">![Open & Closed curves](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span></span>  
  
 <span data-ttu-id="ba3c7-114"><xref:System.Drawing.Graphics.FillClosedCurve%2A>方法是一起提供<xref:System.Drawing.Graphics.DrawClosedCurve%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="ba3c7-114">The <xref:System.Drawing.Graphics.FillClosedCurve%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method.</span></span> <span data-ttu-id="ba3c7-115">这两种方法会自动通过连接到的起始点的结束点闭合曲线。</span><span class="sxs-lookup"><span data-stu-id="ba3c7-115">Both methods automatically close the curve by connecting the ending point to the starting point.</span></span> <span data-ttu-id="ba3c7-116">下面的示例绘制传递一条曲线 （0，0） （60，20） 和 （40、 50）。</span><span class="sxs-lookup"><span data-stu-id="ba3c7-116">The following example draws a curve that passes through (0, 0), (60, 20), and (40, 50).</span></span> <span data-ttu-id="ba3c7-117">然后，通过连接自动关闭曲线 （40、 50） 到起始点 （0，0），并使用纯色填充其内部。</span><span class="sxs-lookup"><span data-stu-id="ba3c7-117">Then, the curve is automatically closed by connecting (40, 50) to the starting point (0, 0), and the interior is filled with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#22](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 <span data-ttu-id="ba3c7-118"><xref:System.Drawing.Graphics.FillPath%2A>方法填充的路径的不同部分的内部。</span><span class="sxs-lookup"><span data-stu-id="ba3c7-118">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the interiors of the separate pieces of a path.</span></span> <span data-ttu-id="ba3c7-119">如果路径的一段不会形成闭合的曲线或形状，<xref:System.Drawing.Graphics.FillPath%2A>方法会自动填充它之前关闭该路径的段。</span><span class="sxs-lookup"><span data-stu-id="ba3c7-119">If a piece of a path doesn't form a closed curve or shape, the <xref:System.Drawing.Graphics.FillPath%2A> method automatically closes that piece of the path before filling it.</span></span> <span data-ttu-id="ba3c7-120">下面的示例绘制并填充一段弧线、 基数样条、 字符串和饼图组成的路径：</span><span class="sxs-lookup"><span data-stu-id="ba3c7-120">The following example draws and fills a path that consists of an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#23](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 <span data-ttu-id="ba3c7-121">下图显示使用和不使用纯色填充的路径。</span><span class="sxs-lookup"><span data-stu-id="ba3c7-121">The following illustration shows the path with and without the solid fill.</span></span> <span data-ttu-id="ba3c7-122">请注意，在字符串中的文本是所述，但未填充，由<xref:System.Drawing.Graphics.DrawPath%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="ba3c7-122">Note that the text in the string is outlined, but not filled, by the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="ba3c7-123">它是<xref:System.Drawing.Graphics.FillPath%2A>绘制的字符串中字符的内部的方法。</span><span class="sxs-lookup"><span data-stu-id="ba3c7-123">It is the <xref:System.Drawing.Graphics.FillPath%2A> method that paints the interiors of the characters in the string.</span></span>  
  
 <span data-ttu-id="ba3c7-124">![在路径中的字符串](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span><span class="sxs-lookup"><span data-stu-id="ba3c7-124">![String in a path](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba3c7-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba3c7-125">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [<span data-ttu-id="ba3c7-126">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="ba3c7-126">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="ba3c7-127">如何：创建用于绘制图形对象</span><span class="sxs-lookup"><span data-stu-id="ba3c7-127">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="ba3c7-128">构造并绘制路径</span><span class="sxs-lookup"><span data-stu-id="ba3c7-128">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
