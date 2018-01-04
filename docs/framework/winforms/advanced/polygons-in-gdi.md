---
title: "GDI+ 中的多边形"
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
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26068ab72473a541b1f16aeb2a1f0d43ec7a7313
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="polygons-in-gdi"></a><span data-ttu-id="1ab17-102">GDI+ 中的多边形</span><span class="sxs-lookup"><span data-stu-id="1ab17-102">Polygons in GDI+</span></span>
<span data-ttu-id="1ab17-103">多边形是有三个或多个直条边的闭合的形状。</span><span class="sxs-lookup"><span data-stu-id="1ab17-103">A polygon is a closed shape with three or more straight sides.</span></span> <span data-ttu-id="1ab17-104">例如，一个三角形是有三条边的多边形、 矩形是有四条边的多边形和形是有五条边的多边形。</span><span class="sxs-lookup"><span data-stu-id="1ab17-104">For example, a triangle is a polygon with three sides, a rectangle is a polygon with four sides, and a pentagon is a polygon with five sides.</span></span> <span data-ttu-id="1ab17-105">下图显示了几个多边形。</span><span class="sxs-lookup"><span data-stu-id="1ab17-105">The following illustration shows several polygons.</span></span>  
  
 <span data-ttu-id="1ab17-106">![多边形](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span><span class="sxs-lookup"><span data-stu-id="1ab17-106">![Polygons](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span></span>  
  
## <a name="drawing-a-polygon"></a><span data-ttu-id="1ab17-107">绘制多边形</span><span class="sxs-lookup"><span data-stu-id="1ab17-107">Drawing a Polygon</span></span>  
 <span data-ttu-id="1ab17-108">若要绘制多边形，你需要<xref:System.Drawing.Graphics>对象，<xref:System.Drawing.Pen>对象和数组的<xref:System.Drawing.Point>(或<xref:System.Drawing.PointF>) 对象。</span><span class="sxs-lookup"><span data-stu-id="1ab17-108">To draw a polygon, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and an array of <xref:System.Drawing.Point> (or <xref:System.Drawing.PointF>) objects.</span></span> <span data-ttu-id="1ab17-109"><xref:System.Drawing.Graphics>对象提供<xref:System.Drawing.Graphics.DrawPolygon%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="1ab17-109">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="1ab17-110"><xref:System.Drawing.Pen>对象存储特性，如宽度和用于呈现多边形、 和的数组的线条的颜色，<xref:System.Drawing.Point>对象将存储要由直线连接的点。</span><span class="sxs-lookup"><span data-stu-id="1ab17-110">The <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the polygon, and the array of <xref:System.Drawing.Point> objects stores the points to be connected by straight lines.</span></span> <span data-ttu-id="1ab17-111"><xref:System.Drawing.Pen>对象和数组<xref:System.Drawing.Point>对象作为参数传递给<xref:System.Drawing.Graphics.DrawPolygon%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="1ab17-111">The <xref:System.Drawing.Pen> object and the array of <xref:System.Drawing.Point> objects are passed as arguments to the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="1ab17-112">下面的示例绘制三双侧多边形。</span><span class="sxs-lookup"><span data-stu-id="1ab17-112">The following example draws a three-sided polygon.</span></span> <span data-ttu-id="1ab17-113">请注意，有中的只有三个点`myPointArray`: （0，0），（50、 30） 和 （30、 60）。</span><span class="sxs-lookup"><span data-stu-id="1ab17-113">Note that there are only three points in `myPointArray`: (0, 0), (50, 30), and (30, 60).</span></span> <span data-ttu-id="1ab17-114"><xref:System.Drawing.Graphics.DrawPolygon%2A>方法会自动关闭多边形通过绘制中的一行 （30、 60） 返回到起始点 （0，0）。</span><span class="sxs-lookup"><span data-stu-id="1ab17-114">The <xref:System.Drawing.Graphics.DrawPolygon%2A> method automatically closes the polygon by drawing a line from (30, 60) back to the starting point (0, 0).</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 <span data-ttu-id="1ab17-115">下图显示多边形。</span><span class="sxs-lookup"><span data-stu-id="1ab17-115">The following illustration shows the polygon.</span></span>  
  
 <span data-ttu-id="1ab17-116">![多边形](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span><span class="sxs-lookup"><span data-stu-id="1ab17-116">![Polygon](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ab17-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ab17-117">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [<span data-ttu-id="1ab17-118">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="1ab17-118">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="1ab17-119">如何：创建笔</span><span class="sxs-lookup"><span data-stu-id="1ab17-119">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
