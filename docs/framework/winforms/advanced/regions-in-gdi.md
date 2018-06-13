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
ms.openlocfilehash: dc7f10571163d447802c90cd61d71b11d0e695d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524578"
---
# <a name="regions-in-gdi"></a><span data-ttu-id="ace38-102">GDI+ 中的区域</span><span class="sxs-lookup"><span data-stu-id="ace38-102">Regions in GDI+</span></span>
<span data-ttu-id="ace38-103">区域是输出设备的显示区域的一部分。</span><span class="sxs-lookup"><span data-stu-id="ace38-103">A region is a portion of the display area of an output device.</span></span> <span data-ttu-id="ace38-104">区域可以是简单 （单个矩形） 或复杂 （多边形和闭合的曲线的组合）。</span><span class="sxs-lookup"><span data-stu-id="ace38-104">Regions can be simple (a single rectangle) or complex (a combination of polygons and closed curves).</span></span> <span data-ttu-id="ace38-105">下图显示了两个区域： 一个从一个矩形、 构造和路径中的其他构造。</span><span class="sxs-lookup"><span data-stu-id="ace38-105">The following illustration shows two regions: one constructed from a rectangle, and the other constructed from a path.</span></span>  
  
 <span data-ttu-id="ace38-106">![区域](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span><span class="sxs-lookup"><span data-stu-id="ace38-106">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span></span>  
  
## <a name="using-regions"></a><span data-ttu-id="ace38-107">使用区域</span><span class="sxs-lookup"><span data-stu-id="ace38-107">Using Regions</span></span>  
 <span data-ttu-id="ace38-108">区域通常用于剪辑和命中测试。</span><span class="sxs-lookup"><span data-stu-id="ace38-108">Regions are often used for clipping and hit testing.</span></span> <span data-ttu-id="ace38-109">剪辑涉及将绘制限制到特定区域的显示区域中，通常需要更新的部分。</span><span class="sxs-lookup"><span data-stu-id="ace38-109">Clipping involves restricting drawing to a certain region of the display area, usually the portion that needs to be updated.</span></span> <span data-ttu-id="ace38-110">命中测试包括检查以确定指示光标是否屏幕的某些区域中按下鼠标按钮时发生。</span><span class="sxs-lookup"><span data-stu-id="ace38-110">Hit testing involves checking to determine whether the cursor is in a certain region of the screen when a mouse button is pressed.</span></span>  
  
 <span data-ttu-id="ace38-111">您可以构造从矩形或路径的区域。</span><span class="sxs-lookup"><span data-stu-id="ace38-111">You can construct a region from a rectangle or a path.</span></span> <span data-ttu-id="ace38-112">你还可以通过组合现有区域创建复杂的区域。</span><span class="sxs-lookup"><span data-stu-id="ace38-112">You can also create complex regions by combining existing regions.</span></span> <span data-ttu-id="ace38-113"><xref:System.Drawing.Region>类提供了以下方法将组合区域： <xref:System.Drawing.Region.Intersect%2A>， <xref:System.Drawing.Region.Union%2A>， <xref:System.Drawing.Region.Xor%2A>， <xref:System.Drawing.Region.Exclude%2A>，和<xref:System.Drawing.Region.Complement%2A>。</span><span class="sxs-lookup"><span data-stu-id="ace38-113">The <xref:System.Drawing.Region> class provides the following methods for combining regions: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, and <xref:System.Drawing.Region.Complement%2A>.</span></span>  
  
 <span data-ttu-id="ace38-114">两个区域的交集是属于两个区域的所有点的集合。</span><span class="sxs-lookup"><span data-stu-id="ace38-114">The intersection of two regions is the set of all points belonging to both regions.</span></span> <span data-ttu-id="ace38-115">联合是组属于一个或另一个或两个区域的所有点。</span><span class="sxs-lookup"><span data-stu-id="ace38-115">The union is the set of all points belonging to one or the other or both regions.</span></span> <span data-ttu-id="ace38-116">区域的补集是一套不在区域的所有点。</span><span class="sxs-lookup"><span data-stu-id="ace38-116">The complement of a region is the set of all points that are not in the region.</span></span> <span data-ttu-id="ace38-117">下图显示了交集和在上图中所示的两个区域的联合。</span><span class="sxs-lookup"><span data-stu-id="ace38-117">The following illustration shows the intersection and union of the two regions shown in the preceding illustration.</span></span>  
  
 <span data-ttu-id="ace38-118">![区域](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span><span class="sxs-lookup"><span data-stu-id="ace38-118">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span></span>  
  
 <span data-ttu-id="ace38-119"><xref:System.Drawing.Region.Xor%2A>方法应用于一对区域，可生成，包含所有属于一个区域或另一个，而不是两个数据点的区域。</span><span class="sxs-lookup"><span data-stu-id="ace38-119">The <xref:System.Drawing.Region.Xor%2A> method, applied to a pair of regions, produces a region that contains all points that belong to one region or the other, but not both.</span></span> <span data-ttu-id="ace38-120"><xref:System.Drawing.Region.Exclude%2A>方法应用于一对区域，可生成，包含中的第一个区域不在第二个区域的所有点的区域。</span><span class="sxs-lookup"><span data-stu-id="ace38-120">The <xref:System.Drawing.Region.Exclude%2A> method, applied to a pair of regions, produces a region that contains all points in the first region that are not in the second region.</span></span> <span data-ttu-id="ace38-121">下图显示来自应用的区域<xref:System.Drawing.Region.Xor%2A>和<xref:System.Drawing.Region.Exclude%2A>到本主题开头的两个区域的方法。</span><span class="sxs-lookup"><span data-stu-id="ace38-121">The following illustration shows the regions that result from applying the <xref:System.Drawing.Region.Xor%2A> and <xref:System.Drawing.Region.Exclude%2A> methods to the two regions shown at the beginning of this topic.</span></span>  
  
 <span data-ttu-id="ace38-122">![区域](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span><span class="sxs-lookup"><span data-stu-id="ace38-122">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span></span>  
  
 <span data-ttu-id="ace38-123">若要填充区域，你需要<xref:System.Drawing.Graphics>对象，<xref:System.Drawing.Brush>对象，和一个<xref:System.Drawing.Region>对象。</span><span class="sxs-lookup"><span data-stu-id="ace38-123">To fill a region, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Brush> object, and a <xref:System.Drawing.Region> object.</span></span> <span data-ttu-id="ace38-124"><xref:System.Drawing.Graphics>对象提供<xref:System.Drawing.Graphics.FillRegion%2A>方法，与<xref:System.Drawing.Brush>对象存储填充，如颜色或图案的特性。</span><span class="sxs-lookup"><span data-stu-id="ace38-124">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.FillRegion%2A> method, and the <xref:System.Drawing.Brush> object stores attributes of the fill, such as color or pattern.</span></span> <span data-ttu-id="ace38-125">下面的示例填充具有纯色的区域。</span><span class="sxs-lookup"><span data-stu-id="ace38-125">The following example fills a region with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="ace38-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="ace38-126">See Also</span></span>  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [<span data-ttu-id="ace38-127">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="ace38-127">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="ace38-128">使用区域</span><span class="sxs-lookup"><span data-stu-id="ace38-128">Using Regions</span></span>](../../../../docs/framework/winforms/advanced/using-regions.md)
