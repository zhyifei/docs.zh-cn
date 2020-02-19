---
title: 如何：创建椭圆弧
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: d0fffbb25f3c5aaceb2cd80af4f1093e44111200
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453060"
---
# <a name="how-to-create-an-elliptical-arc"></a><span data-ttu-id="94956-102">如何：创建椭圆弧</span><span class="sxs-lookup"><span data-stu-id="94956-102">How to: Create an Elliptical Arc</span></span>
<span data-ttu-id="94956-103">此示例演示如何绘制椭圆弧。若要创建椭圆弧，请使用 <xref:System.Windows.Media.PathGeometry>、<xref:System.Windows.Media.PathFigure>和 <xref:System.Windows.Media.ArcSegment> 类。</span><span class="sxs-lookup"><span data-stu-id="94956-103">This example shows how to draw an elliptical arc. To create an elliptical arc, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.ArcSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94956-104">示例</span><span class="sxs-lookup"><span data-stu-id="94956-104">Example</span></span>  
 <span data-ttu-id="94956-105">在下面的示例中，椭圆弧从（10100）绘制到（200100）。</span><span class="sxs-lookup"><span data-stu-id="94956-105">In the following examples, an elliptical arc is drawn from (10,100) to (200,100).</span></span> <span data-ttu-id="94956-106">Arc 的 <xref:System.Windows.Media.ArcSegment.Size%2A> 为 100 x 50 与设备无关的像素、<xref:System.Windows.Media.ArcSegment.RotationAngle%2A> 45 度、`true`<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> 设置和 <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> <xref:System.Windows.Media.SweepDirection.Counterclockwise>。</span><span class="sxs-lookup"><span data-stu-id="94956-106">The arc has a <xref:System.Windows.Media.ArcSegment.Size%2A> of 100 by 50 device-independent pixels, a <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> of 45 degrees, an <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> setting of `true`, and a <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> of <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span></span>  
  
 <span data-ttu-id="94956-107">[xaml]</span><span class="sxs-lookup"><span data-stu-id="94956-107">[xaml]</span></span>  
  
 <span data-ttu-id="94956-108">在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中，可以使用属性语法来描述路径。</span><span class="sxs-lookup"><span data-stu-id="94956-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 <span data-ttu-id="94956-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="94956-109">[xaml]</span></span>  
  
 <span data-ttu-id="94956-110">（请注意，此属性语法实际上会创建一个 <xref:System.Windows.Media.StreamGeometry>，这是一个 <xref:System.Windows.Media.PathGeometry>的轻型版本。</span><span class="sxs-lookup"><span data-stu-id="94956-110">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="94956-111">有关详细信息，请参阅[路径标记语法](path-markup-syntax.md)页。）</span><span class="sxs-lookup"><span data-stu-id="94956-111">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="94956-112">在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中，还可以通过显式使用对象标记来绘制椭圆弧。</span><span class="sxs-lookup"><span data-stu-id="94956-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw an elliptical arc by explicitly using object tags.</span></span> <span data-ttu-id="94956-113">以下与前面 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 标记等效。</span><span class="sxs-lookup"><span data-stu-id="94956-113">The following is equivalent to the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 <span data-ttu-id="94956-114">此示例摘自一个更大的示例。</span><span class="sxs-lookup"><span data-stu-id="94956-114">This example is part of a larger sample.</span></span> <span data-ttu-id="94956-115">有关完整示例，请参阅[几何图形示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)。</span><span class="sxs-lookup"><span data-stu-id="94956-115">For the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94956-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94956-116">See also</span></span>

- [<span data-ttu-id="94956-117">创建二次贝塞尔曲线</span><span class="sxs-lookup"><span data-stu-id="94956-117">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
- [<span data-ttu-id="94956-118">创建三次方贝塞尔曲线</span><span class="sxs-lookup"><span data-stu-id="94956-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
