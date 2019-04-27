---
title: 如何：使用 LineGeometry 创建直线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
ms.openlocfilehash: f8c334a54f78aec7af91064a447fd18f23dcfbdc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905198"
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a><span data-ttu-id="8cb70-102">如何：使用 LineGeometry 创建直线</span><span class="sxs-lookup"><span data-stu-id="8cb70-102">How to: Create a Line Using a LineGeometry</span></span>
<span data-ttu-id="8cb70-103">此示例演示如何使用<xref:System.Windows.Media.LineGeometry>类，用于描述一个行。</span><span class="sxs-lookup"><span data-stu-id="8cb70-103">This example shows how to use the <xref:System.Windows.Media.LineGeometry> class to describe a line.</span></span> <span data-ttu-id="8cb70-104">一个<xref:System.Windows.Media.LineGeometry>由其起点和终点定义。</span><span class="sxs-lookup"><span data-stu-id="8cb70-104">A <xref:System.Windows.Media.LineGeometry> is defined by its start and end points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cb70-105">示例</span><span class="sxs-lookup"><span data-stu-id="8cb70-105">Example</span></span>  
 <span data-ttu-id="8cb70-106">下面的示例演示如何创建和呈现<xref:System.Windows.Media.LineGeometry>。</span><span class="sxs-lookup"><span data-stu-id="8cb70-106">The following example shows how to create and render a <xref:System.Windows.Media.LineGeometry>.</span></span>  <span data-ttu-id="8cb70-107">一个<xref:System.Windows.Shapes.Path>使用元素来呈现直线。</span><span class="sxs-lookup"><span data-stu-id="8cb70-107">A <xref:System.Windows.Shapes.Path> element is used to render the line.</span></span>  <span data-ttu-id="8cb70-108">行不包含区域，因为<xref:System.Windows.Shapes.Path>对象的<xref:System.Windows.Shapes.Shape.Fill%2A>未指定; 而是<xref:System.Windows.Shapes.Shape.Stroke%2A>和<xref:System.Windows.Shapes.Shape.StrokeThickness%2A>使用属性。</span><span class="sxs-lookup"><span data-stu-id="8cb70-108">Since a line has no area, the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Shape.Fill%2A> is not specified; instead the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties are used.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 <span data-ttu-id="8cb70-109">![一个 LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")</span><span class="sxs-lookup"><span data-stu-id="8cb70-109">![A LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")</span></span>  
<span data-ttu-id="8cb70-110">从 (10,20) 绘制到 (100,130) 的 LineGeometry</span><span class="sxs-lookup"><span data-stu-id="8cb70-110">A LineGeometry drawn from (10,20) to (100,130)</span></span>  
  
 <span data-ttu-id="8cb70-111">其他简单的几何类包括<xref:System.Windows.Media.LineGeometry>和<xref:System.Windows.Media.EllipseGeometry>。</span><span class="sxs-lookup"><span data-stu-id="8cb70-111">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="8cb70-112">这些几何形状，以及更复杂的也可以创建使用<xref:System.Windows.Media.PathGeometry>或<xref:System.Windows.Media.StreamGeometry>。</span><span class="sxs-lookup"><span data-stu-id="8cb70-112">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span> <span data-ttu-id="8cb70-113">有关详细信息，请参阅[几何概述](geometry-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8cb70-113">For more information, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cb70-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="8cb70-114">See also</span></span>

- [<span data-ttu-id="8cb70-115">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="8cb70-115">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="8cb70-116">创建复合形状</span><span class="sxs-lookup"><span data-stu-id="8cb70-116">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="8cb70-117">使用 PathGeometry 创建形状</span><span class="sxs-lookup"><span data-stu-id="8cb70-117">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
