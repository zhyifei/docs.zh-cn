---
title: 如何：创建三次方贝塞尔曲线
ms.date: 03/30/2017
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
ms.openlocfilehash: 36544abc774b7fe82c2ff47483cfedd6fb13e344
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115565"
---
# <a name="how-to-create-a-cubic-bezier-curve"></a><span data-ttu-id="828a7-102">如何：创建三次方贝塞尔曲线</span><span class="sxs-lookup"><span data-stu-id="828a7-102">How to: Create a Cubic Bezier Curve</span></span>
<span data-ttu-id="828a7-103">此示例演示如何创建三次方贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="828a7-103">This example shows how to create a cubic Bezier curve.</span></span> <span data-ttu-id="828a7-104">若要创建三次方贝塞尔曲线，使用<xref:System.Windows.Media.PathGeometry>， <xref:System.Windows.Media.PathFigure>，和<xref:System.Windows.Media.BezierSegment>类。</span><span class="sxs-lookup"><span data-stu-id="828a7-104">To create a cubic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.BezierSegment> classes.</span></span>  <span data-ttu-id="828a7-105">若要显示所生成的几何图形，请使用<xref:System.Windows.Shapes.Path>元素，或将其用于<xref:System.Windows.Media.GeometryDrawing>或<xref:System.Windows.Media.DrawingContext>。</span><span class="sxs-lookup"><span data-stu-id="828a7-105">To display the resulting geometry, use a <xref:System.Windows.Shapes.Path> element, or use it with a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="828a7-106">在以下示例中，三次方贝塞尔曲线绘制从 （10，100） 到 （300，100）。</span><span class="sxs-lookup"><span data-stu-id="828a7-106">In the following examples, a cubic Bezier curve is drawn from (10, 100) to (300, 100).</span></span> <span data-ttu-id="828a7-107">曲线的控制点为 （100，0） 和 （200，200）。</span><span class="sxs-lookup"><span data-stu-id="828a7-107">The curve has control points of (100, 0) and (200, 200).</span></span>  
  
## <a name="example"></a><span data-ttu-id="828a7-108">示例</span><span class="sxs-lookup"><span data-stu-id="828a7-108">Example</span></span>  
 <span data-ttu-id="828a7-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="828a7-109">[xaml]</span></span>  
  
 <span data-ttu-id="828a7-110">在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，可以使用缩写的标记语法来描述路径。</span><span class="sxs-lookup"><span data-stu-id="828a7-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use abbreviated markup syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 <span data-ttu-id="828a7-111">[xaml]</span><span class="sxs-lookup"><span data-stu-id="828a7-111">[xaml]</span></span>  
  
 <span data-ttu-id="828a7-112">在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，还可以绘制使用对象标记的三次方贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="828a7-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw a cubic Bezier curve using object tags.</span></span> <span data-ttu-id="828a7-113">以下内容等效于之前的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="828a7-113">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#33](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 <span data-ttu-id="828a7-114">此示例是更大示例的组成部分；有关完整示例，请参阅[几何图形示例](https://go.microsoft.com/fwlink/?LinkID=159989)。</span><span class="sxs-lookup"><span data-stu-id="828a7-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="828a7-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="828a7-115">See also</span></span>

- [<span data-ttu-id="828a7-116">创建椭圆弧</span><span class="sxs-lookup"><span data-stu-id="828a7-116">Create an Elliptical Arc</span></span>](how-to-create-an-elliptical-arc.md)
- [<span data-ttu-id="828a7-117">在 PathGeometry 中创建 LineSegment</span><span class="sxs-lookup"><span data-stu-id="828a7-117">Create a LineSegment in a PathGeometry</span></span>](how-to-create-a-linesegment-in-a-pathgeometry.md)
- [<span data-ttu-id="828a7-118">创建三次方贝塞尔曲线</span><span class="sxs-lookup"><span data-stu-id="828a7-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
- [<span data-ttu-id="828a7-119">创建二次贝塞尔曲线</span><span class="sxs-lookup"><span data-stu-id="828a7-119">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
