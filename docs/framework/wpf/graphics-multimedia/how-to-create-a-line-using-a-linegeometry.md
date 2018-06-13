---
title: 如何：使用 LineGeometry 创建线条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
ms.openlocfilehash: 8db33fc5c611dcbcae50c71ada1c6b6f9fd9bd29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560464"
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a><span data-ttu-id="fe03d-102">如何：使用 LineGeometry 创建线条</span><span class="sxs-lookup"><span data-stu-id="fe03d-102">How to: Create a Line Using a LineGeometry</span></span>
<span data-ttu-id="fe03d-103">此示例演示如何使用<xref:System.Windows.Media.LineGeometry>类描述一个行。</span><span class="sxs-lookup"><span data-stu-id="fe03d-103">This example shows how to use the <xref:System.Windows.Media.LineGeometry> class to describe a line.</span></span> <span data-ttu-id="fe03d-104">A<xref:System.Windows.Media.LineGeometry>定义的其起点和终点。</span><span class="sxs-lookup"><span data-stu-id="fe03d-104">A <xref:System.Windows.Media.LineGeometry> is defined by its start and end points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe03d-105">示例</span><span class="sxs-lookup"><span data-stu-id="fe03d-105">Example</span></span>  
 <span data-ttu-id="fe03d-106">下面的示例演示如何创建和呈现<xref:System.Windows.Media.LineGeometry>。</span><span class="sxs-lookup"><span data-stu-id="fe03d-106">The following example shows how to create and render a <xref:System.Windows.Media.LineGeometry>.</span></span>  <span data-ttu-id="fe03d-107">A<xref:System.Windows.Shapes.Path>元素用于呈现行。</span><span class="sxs-lookup"><span data-stu-id="fe03d-107">A <xref:System.Windows.Shapes.Path> element is used to render the line.</span></span>  <span data-ttu-id="fe03d-108">因为行都有没有区域<xref:System.Windows.Shapes.Path>对象的<xref:System.Windows.Shapes.Shape.Fill%2A>未指定; 改为<xref:System.Windows.Shapes.Shape.Stroke%2A>和<xref:System.Windows.Shapes.Shape.StrokeThickness%2A>使用属性。</span><span class="sxs-lookup"><span data-stu-id="fe03d-108">Since a line has no area, the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Shape.Fill%2A> is not specified; instead the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties are used.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 <span data-ttu-id="fe03d-109">![一个 LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")</span><span class="sxs-lookup"><span data-stu-id="fe03d-109">![A LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")</span></span>  
<span data-ttu-id="fe03d-110">从 (10,20) 绘制到 (100,130) 的 LineGeometry</span><span class="sxs-lookup"><span data-stu-id="fe03d-110">A LineGeometry drawn from (10,20) to (100,130)</span></span>  
  
 <span data-ttu-id="fe03d-111">简单的几何图形的其他类包括<xref:System.Windows.Media.LineGeometry>和<xref:System.Windows.Media.EllipseGeometry>。</span><span class="sxs-lookup"><span data-stu-id="fe03d-111">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="fe03d-112">这些几何图形，以及更复杂的也可以创建使用<xref:System.Windows.Media.PathGeometry>或<xref:System.Windows.Media.StreamGeometry>。</span><span class="sxs-lookup"><span data-stu-id="fe03d-112">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span> <span data-ttu-id="fe03d-113">有关详细信息，请参阅[几何图形概述](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="fe03d-113">For more information, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe03d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe03d-114">See Also</span></span>  
 [<span data-ttu-id="fe03d-115">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="fe03d-115">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="fe03d-116">创建复合形状</span><span class="sxs-lookup"><span data-stu-id="fe03d-116">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [<span data-ttu-id="fe03d-117">使用 PathGeometry 创建形状</span><span class="sxs-lookup"><span data-stu-id="fe03d-117">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
