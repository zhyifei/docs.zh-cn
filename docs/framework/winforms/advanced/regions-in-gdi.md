---
title: GDI+ 中的区域
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
ms.openlocfilehash: 33d4f4ecca7b9d777fa4eab5b6d031de10f03ccc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956768"
---
# <a name="regions-in-gdi"></a><span data-ttu-id="27ef7-102">GDI+ 中的区域</span><span class="sxs-lookup"><span data-stu-id="27ef7-102">Regions in GDI+</span></span>
<span data-ttu-id="27ef7-103">区域是输出设备的显示区域的一部分。</span><span class="sxs-lookup"><span data-stu-id="27ef7-103">A region is a portion of the display area of an output device.</span></span> <span data-ttu-id="27ef7-104">区域可以是简单 （一个矩形） 或复杂 （多边形和闭合的曲线的组合）。</span><span class="sxs-lookup"><span data-stu-id="27ef7-104">Regions can be simple (a single rectangle) or complex (a combination of polygons and closed curves).</span></span> <span data-ttu-id="27ef7-105">下图显示了两个区域： 一个从一个矩形、 构造和路径中的其他构造。</span><span class="sxs-lookup"><span data-stu-id="27ef7-105">The following illustration shows two regions: one constructed from a rectangle, and the other constructed from a path.</span></span>  
  
 <span data-ttu-id="27ef7-106">![Regions](./media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span><span class="sxs-lookup"><span data-stu-id="27ef7-106">![Regions](./media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span></span>  
  
## <a name="using-regions"></a><span data-ttu-id="27ef7-107">使用区域</span><span class="sxs-lookup"><span data-stu-id="27ef7-107">Using Regions</span></span>  
 <span data-ttu-id="27ef7-108">区域通常用于剪辑和命中测试。</span><span class="sxs-lookup"><span data-stu-id="27ef7-108">Regions are often used for clipping and hit testing.</span></span> <span data-ttu-id="27ef7-109">剪辑涉及到将绘制限制到特定的区域的显示区域中，通常需要更新的部分。</span><span class="sxs-lookup"><span data-stu-id="27ef7-109">Clipping involves restricting drawing to a certain region of the display area, usually the portion that needs to be updated.</span></span> <span data-ttu-id="27ef7-110">命中测试涉及到检查以确定光标是否在某些区域中的屏幕时按下鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="27ef7-110">Hit testing involves checking to determine whether the cursor is in a certain region of the screen when a mouse button is pressed.</span></span>  
  
 <span data-ttu-id="27ef7-111">您可以构造从一个矩形或路径的区域。</span><span class="sxs-lookup"><span data-stu-id="27ef7-111">You can construct a region from a rectangle or a path.</span></span> <span data-ttu-id="27ef7-112">此外可以通过合并现有的区域来创建复杂的区域。</span><span class="sxs-lookup"><span data-stu-id="27ef7-112">You can also create complex regions by combining existing regions.</span></span> <span data-ttu-id="27ef7-113"><xref:System.Drawing.Region>类提供了以下用于组合区域的方法： <xref:System.Drawing.Region.Intersect%2A>， <xref:System.Drawing.Region.Union%2A>， <xref:System.Drawing.Region.Xor%2A>， <xref:System.Drawing.Region.Exclude%2A>，并<xref:System.Drawing.Region.Complement%2A>。</span><span class="sxs-lookup"><span data-stu-id="27ef7-113">The <xref:System.Drawing.Region> class provides the following methods for combining regions: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, and <xref:System.Drawing.Region.Complement%2A>.</span></span>  
  
 <span data-ttu-id="27ef7-114">两个区域的交集是属于这两个区域的所有点的集合。</span><span class="sxs-lookup"><span data-stu-id="27ef7-114">The intersection of two regions is the set of all points belonging to both regions.</span></span> <span data-ttu-id="27ef7-115">联合是属于一个或另一个或两个区域中的所有点的集合。</span><span class="sxs-lookup"><span data-stu-id="27ef7-115">The union is the set of all points belonging to one or the other or both regions.</span></span> <span data-ttu-id="27ef7-116">区域的补数是不在区域中的所有点的集合。</span><span class="sxs-lookup"><span data-stu-id="27ef7-116">The complement of a region is the set of all points that are not in the region.</span></span> <span data-ttu-id="27ef7-117">下图显示了上图中所示的两个区域的并集和相交处。</span><span class="sxs-lookup"><span data-stu-id="27ef7-117">The following illustration shows the intersection and union of the two regions shown in the preceding illustration.</span></span>  
  
 <span data-ttu-id="27ef7-118">![Regions](./media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span><span class="sxs-lookup"><span data-stu-id="27ef7-118">![Regions](./media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span></span>  
  
 <span data-ttu-id="27ef7-119"><xref:System.Drawing.Region.Xor%2A>方法，适用于一对区域，会生成包含对一个区域或另一个，但不是能同时属于的所有点的区域。</span><span class="sxs-lookup"><span data-stu-id="27ef7-119">The <xref:System.Drawing.Region.Xor%2A> method, applied to a pair of regions, produces a region that contains all points that belong to one region or the other, but not both.</span></span> <span data-ttu-id="27ef7-120"><xref:System.Drawing.Region.Exclude%2A>方法，适用于一对区域，会生成包含不在第二个区域中的第一个区域中的所有点的区域。</span><span class="sxs-lookup"><span data-stu-id="27ef7-120">The <xref:System.Drawing.Region.Exclude%2A> method, applied to a pair of regions, produces a region that contains all points in the first region that are not in the second region.</span></span> <span data-ttu-id="27ef7-121">下图显示了通过应用生成的区域<xref:System.Drawing.Region.Xor%2A>和<xref:System.Drawing.Region.Exclude%2A>本主题开头所示的两个区域的方法。</span><span class="sxs-lookup"><span data-stu-id="27ef7-121">The following illustration shows the regions that result from applying the <xref:System.Drawing.Region.Xor%2A> and <xref:System.Drawing.Region.Exclude%2A> methods to the two regions shown at the beginning of this topic.</span></span>  
  
 <span data-ttu-id="27ef7-122">![Regions](./media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span><span class="sxs-lookup"><span data-stu-id="27ef7-122">![Regions](./media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span></span>  
  
 <span data-ttu-id="27ef7-123">若要填充一个区域，需要<xref:System.Drawing.Graphics>对象，<xref:System.Drawing.Brush>对象，和一个<xref:System.Drawing.Region>对象。</span><span class="sxs-lookup"><span data-stu-id="27ef7-123">To fill a region, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Brush> object, and a <xref:System.Drawing.Region> object.</span></span> <span data-ttu-id="27ef7-124"><xref:System.Drawing.Graphics>对象提供<xref:System.Drawing.Graphics.FillRegion%2A>方法，和<xref:System.Drawing.Brush>对象将存储的填充，如颜色或图案的特性。</span><span class="sxs-lookup"><span data-stu-id="27ef7-124">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.FillRegion%2A> method, and the <xref:System.Drawing.Brush> object stores attributes of the fill, such as color or pattern.</span></span> <span data-ttu-id="27ef7-125">下面的示例填充用一种颜色的区域。</span><span class="sxs-lookup"><span data-stu-id="27ef7-125">The following example fills a region with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#61](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="27ef7-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="27ef7-126">See also</span></span>

- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [<span data-ttu-id="27ef7-127">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="27ef7-127">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="27ef7-128">使用区域</span><span class="sxs-lookup"><span data-stu-id="27ef7-128">Using Regions</span></span>](using-regions.md)
