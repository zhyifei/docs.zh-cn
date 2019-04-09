---
title: GDI+ 中的多边形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
ms.openlocfilehash: 2b1e3d387e4d056d9187c54dcef560544206c370
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132621"
---
# <a name="polygons-in-gdi"></a><span data-ttu-id="17e62-102">GDI+ 中的多边形</span><span class="sxs-lookup"><span data-stu-id="17e62-102">Polygons in GDI+</span></span>
<span data-ttu-id="17e62-103">多边形是闭合的形状有三个或多个直条边。</span><span class="sxs-lookup"><span data-stu-id="17e62-103">A polygon is a closed shape with three or more straight sides.</span></span> <span data-ttu-id="17e62-104">例如，一个三角形是利用三边的多边形、 矩形是具有四个边的多边形和一个五边形是有五条边的多边形。</span><span class="sxs-lookup"><span data-stu-id="17e62-104">For example, a triangle is a polygon with three sides, a rectangle is a polygon with four sides, and a pentagon is a polygon with five sides.</span></span> <span data-ttu-id="17e62-105">下图显示了几个多边形。</span><span class="sxs-lookup"><span data-stu-id="17e62-105">The following illustration shows several polygons.</span></span>  
  
 <span data-ttu-id="17e62-106">![Polygons](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span><span class="sxs-lookup"><span data-stu-id="17e62-106">![Polygons](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span></span>  
  
## <a name="drawing-a-polygon"></a><span data-ttu-id="17e62-107">绘制多边形</span><span class="sxs-lookup"><span data-stu-id="17e62-107">Drawing a Polygon</span></span>  
 <span data-ttu-id="17e62-108">若要绘制多边形，需要<xref:System.Drawing.Graphics>对象，<xref:System.Drawing.Pen>对象和数组<xref:System.Drawing.Point>(或<xref:System.Drawing.PointF>) 对象。</span><span class="sxs-lookup"><span data-stu-id="17e62-108">To draw a polygon, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and an array of <xref:System.Drawing.Point> (or <xref:System.Drawing.PointF>) objects.</span></span> <span data-ttu-id="17e62-109"><xref:System.Drawing.Graphics>对象提供<xref:System.Drawing.Graphics.DrawPolygon%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="17e62-109">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="17e62-110"><xref:System.Drawing.Pen>对象将存储属性，例如宽度和颜色，用来呈现多边形、 和的数组的行<xref:System.Drawing.Point>对象将存储要由直线连接的点。</span><span class="sxs-lookup"><span data-stu-id="17e62-110">The <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the polygon, and the array of <xref:System.Drawing.Point> objects stores the points to be connected by straight lines.</span></span> <span data-ttu-id="17e62-111"><xref:System.Drawing.Pen>对象和数组<xref:System.Drawing.Point>对象将作为参数传递给<xref:System.Drawing.Graphics.DrawPolygon%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="17e62-111">The <xref:System.Drawing.Pen> object and the array of <xref:System.Drawing.Point> objects are passed as arguments to the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="17e62-112">下面的示例绘制三边的多边形。</span><span class="sxs-lookup"><span data-stu-id="17e62-112">The following example draws a three-sided polygon.</span></span> <span data-ttu-id="17e62-113">请注意，只有三个点中的`myPointArray`:（0，0） （50，30） 和 （30、 60）。</span><span class="sxs-lookup"><span data-stu-id="17e62-113">Note that there are only three points in `myPointArray`: (0, 0), (50, 30), and (30, 60).</span></span> <span data-ttu-id="17e62-114"><xref:System.Drawing.Graphics.DrawPolygon%2A>方法会自动关闭多边形通过绘制中的一行 （30、 60） 返回到起始点 （0，0）。</span><span class="sxs-lookup"><span data-stu-id="17e62-114">The <xref:System.Drawing.Graphics.DrawPolygon%2A> method automatically closes the polygon by drawing a line from (30, 60) back to the starting point (0, 0).</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#111](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 <span data-ttu-id="17e62-115">下图显示了多边形。</span><span class="sxs-lookup"><span data-stu-id="17e62-115">The following illustration shows the polygon.</span></span>  
  
 <span data-ttu-id="17e62-116">![Polygon](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span><span class="sxs-lookup"><span data-stu-id="17e62-116">![Polygon](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17e62-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="17e62-117">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="17e62-118">直线、曲线和图形</span><span class="sxs-lookup"><span data-stu-id="17e62-118">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="17e62-119">如何：创建钢笔</span><span class="sxs-lookup"><span data-stu-id="17e62-119">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
