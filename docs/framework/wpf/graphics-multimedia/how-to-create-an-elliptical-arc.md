---
title: 如何：创建椭圆弧
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: 7ca7d06aa25f8dfae648d8c54c8b95cc277ffbf9
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087432"
---
# <a name="how-to-create-an-elliptical-arc"></a><span data-ttu-id="f7945-102">如何：创建椭圆弧</span><span class="sxs-lookup"><span data-stu-id="f7945-102">How to: Create an Elliptical Arc</span></span>
<span data-ttu-id="f7945-103">此示例显示了如何绘制椭圆弧。若要创建椭圆弧，使用<xref:System.Windows.Media.PathGeometry>， <xref:System.Windows.Media.PathFigure>，和<xref:System.Windows.Media.ArcSegment>类。</span><span class="sxs-lookup"><span data-stu-id="f7945-103">This example shows how to draw an elliptical arc. To create an elliptical arc, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.ArcSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7945-104">示例</span><span class="sxs-lookup"><span data-stu-id="f7945-104">Example</span></span>  
 <span data-ttu-id="f7945-105">在以下示例中，从 (10100) 到 (200100) 绘制椭圆弧。</span><span class="sxs-lookup"><span data-stu-id="f7945-105">In the following examples, an elliptical arc is drawn from (10,100) to (200,100).</span></span> <span data-ttu-id="f7945-106">该弧<xref:System.Windows.Media.ArcSegment.Size%2A>100 通过 50 独立于设备的像素为单位的<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>的 45 度<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>的设置`true`，和一个<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>的<xref:System.Windows.Media.SweepDirection.Counterclockwise>。</span><span class="sxs-lookup"><span data-stu-id="f7945-106">The arc has a <xref:System.Windows.Media.ArcSegment.Size%2A> of 100 by 50 device-independent pixels, a <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> of 45 degrees, an <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> setting of `true`, and a <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> of <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span></span>  
  
 <span data-ttu-id="f7945-107">[xaml]</span><span class="sxs-lookup"><span data-stu-id="f7945-107">[xaml]</span></span>  
  
 <span data-ttu-id="f7945-108">在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，可以使用特性语法来描述路径。</span><span class="sxs-lookup"><span data-stu-id="f7945-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#56](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 <span data-ttu-id="f7945-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="f7945-109">[xaml]</span></span>  
  
 <span data-ttu-id="f7945-110">(请注意，此属性语法实际上创建了<xref:System.Windows.Media.StreamGeometry>的轻量版本<xref:System.Windows.Media.PathGeometry>。</span><span class="sxs-lookup"><span data-stu-id="f7945-110">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="f7945-111">有关详细信息，请参阅[路径标记语法](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)页。）</span><span class="sxs-lookup"><span data-stu-id="f7945-111">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="f7945-112">在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，还可以通过显式使用对象标记绘制椭圆弧。</span><span class="sxs-lookup"><span data-stu-id="f7945-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw an elliptical arc by explicitly using object tags.</span></span> <span data-ttu-id="f7945-113">以下是等效于上述[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]标记。</span><span class="sxs-lookup"><span data-stu-id="f7945-113">The following is equivalent to the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[GeometrySample#36](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 <span data-ttu-id="f7945-114">此示例摘自一个更大的示例。</span><span class="sxs-lookup"><span data-stu-id="f7945-114">This example is part of a larger sample.</span></span> <span data-ttu-id="f7945-115">有关完整示例，请参阅[几何图形示例](https://go.microsoft.com/fwlink/?LinkID=159989)。</span><span class="sxs-lookup"><span data-stu-id="f7945-115">For the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7945-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7945-116">See Also</span></span>  
 [<span data-ttu-id="f7945-117">创建二次贝塞尔曲线</span><span class="sxs-lookup"><span data-stu-id="f7945-117">Create a Quadratic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)  
 [<span data-ttu-id="f7945-118">创建三次方贝塞尔曲线</span><span class="sxs-lookup"><span data-stu-id="f7945-118">Create a Cubic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)
