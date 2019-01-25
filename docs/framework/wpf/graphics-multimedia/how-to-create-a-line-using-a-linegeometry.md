---
title: 如何：使用 LineGeometry 创建线条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
ms.openlocfilehash: fbf44f627ede0fe3bdf7e629728a1e3b858fd30e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690561"
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a><span data-ttu-id="4db1c-102">如何：使用 LineGeometry 创建线条</span><span class="sxs-lookup"><span data-stu-id="4db1c-102">How to: Create a Line Using a LineGeometry</span></span>
<span data-ttu-id="4db1c-103">此示例演示如何使用<xref:System.Windows.Media.LineGeometry>类，用于描述一个行。</span><span class="sxs-lookup"><span data-stu-id="4db1c-103">This example shows how to use the <xref:System.Windows.Media.LineGeometry> class to describe a line.</span></span> <span data-ttu-id="4db1c-104">一个<xref:System.Windows.Media.LineGeometry>由其起点和终点定义。</span><span class="sxs-lookup"><span data-stu-id="4db1c-104">A <xref:System.Windows.Media.LineGeometry> is defined by its start and end points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4db1c-105">示例</span><span class="sxs-lookup"><span data-stu-id="4db1c-105">Example</span></span>  
 <span data-ttu-id="4db1c-106">下面的示例演示如何创建和呈现<xref:System.Windows.Media.LineGeometry>。</span><span class="sxs-lookup"><span data-stu-id="4db1c-106">The following example shows how to create and render a <xref:System.Windows.Media.LineGeometry>.</span></span>  <span data-ttu-id="4db1c-107">一个<xref:System.Windows.Shapes.Path>使用元素来呈现直线。</span><span class="sxs-lookup"><span data-stu-id="4db1c-107">A <xref:System.Windows.Shapes.Path> element is used to render the line.</span></span>  <span data-ttu-id="4db1c-108">行不包含区域，因为<xref:System.Windows.Shapes.Path>对象的<xref:System.Windows.Shapes.Shape.Fill%2A>未指定; 而是<xref:System.Windows.Shapes.Shape.Stroke%2A>和<xref:System.Windows.Shapes.Shape.StrokeThickness%2A>使用属性。</span><span class="sxs-lookup"><span data-stu-id="4db1c-108">Since a line has no area, the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Shape.Fill%2A> is not specified; instead the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties are used.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 <span data-ttu-id="4db1c-109">![一个 LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")</span><span class="sxs-lookup"><span data-stu-id="4db1c-109">![A LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")</span></span>  
<span data-ttu-id="4db1c-110">从 (10,20) 绘制到 (100,130) 的 LineGeometry</span><span class="sxs-lookup"><span data-stu-id="4db1c-110">A LineGeometry drawn from (10,20) to (100,130)</span></span>  
  
 <span data-ttu-id="4db1c-111">其他简单的几何类包括<xref:System.Windows.Media.LineGeometry>和<xref:System.Windows.Media.EllipseGeometry>。</span><span class="sxs-lookup"><span data-stu-id="4db1c-111">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="4db1c-112">这些几何形状，以及更复杂的也可以创建使用<xref:System.Windows.Media.PathGeometry>或<xref:System.Windows.Media.StreamGeometry>。</span><span class="sxs-lookup"><span data-stu-id="4db1c-112">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span> <span data-ttu-id="4db1c-113">有关详细信息，请参阅[几何概述](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4db1c-113">For more information, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4db1c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="4db1c-114">See also</span></span>
- [<span data-ttu-id="4db1c-115">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="4db1c-115">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
- [<span data-ttu-id="4db1c-116">创建复合形状</span><span class="sxs-lookup"><span data-stu-id="4db1c-116">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)
- [<span data-ttu-id="4db1c-117">使用 PathGeometry 创建形状</span><span class="sxs-lookup"><span data-stu-id="4db1c-117">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
