---
title: 如何：创建椭圆弧
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: bb4b4d99aab9daef70f446af176bb462b0661d54
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354344"
---
# <a name="how-to-create-an-elliptical-arc"></a><span data-ttu-id="ae14f-102">如何：创建椭圆弧</span><span class="sxs-lookup"><span data-stu-id="ae14f-102">How to: Create an Elliptical Arc</span></span>
<span data-ttu-id="ae14f-103">此示例显示了如何绘制椭圆弧。若要创建椭圆弧，使用<xref:System.Windows.Media.PathGeometry>， <xref:System.Windows.Media.PathFigure>，和<xref:System.Windows.Media.ArcSegment>类。</span><span class="sxs-lookup"><span data-stu-id="ae14f-103">This example shows how to draw an elliptical arc. To create an elliptical arc, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.ArcSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae14f-104">示例</span><span class="sxs-lookup"><span data-stu-id="ae14f-104">Example</span></span>  
 <span data-ttu-id="ae14f-105">在以下示例中，从 (10100) 到 (200100) 绘制椭圆弧。</span><span class="sxs-lookup"><span data-stu-id="ae14f-105">In the following examples, an elliptical arc is drawn from (10,100) to (200,100).</span></span> <span data-ttu-id="ae14f-106">该弧<xref:System.Windows.Media.ArcSegment.Size%2A>100 通过 50 独立于设备的像素为单位的<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>的 45 度<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>的设置`true`，和一个<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>的<xref:System.Windows.Media.SweepDirection.Counterclockwise>。</span><span class="sxs-lookup"><span data-stu-id="ae14f-106">The arc has a <xref:System.Windows.Media.ArcSegment.Size%2A> of 100 by 50 device-independent pixels, a <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> of 45 degrees, an <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> setting of `true`, and a <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> of <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span></span>  
  
 <span data-ttu-id="ae14f-107">[xaml]</span><span class="sxs-lookup"><span data-stu-id="ae14f-107">[xaml]</span></span>  
  
 <span data-ttu-id="ae14f-108">在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，可以使用特性语法来描述路径。</span><span class="sxs-lookup"><span data-stu-id="ae14f-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 <span data-ttu-id="ae14f-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="ae14f-109">[xaml]</span></span>  
  
 <span data-ttu-id="ae14f-110">(请注意，此属性语法实际上创建了<xref:System.Windows.Media.StreamGeometry>的轻量版本<xref:System.Windows.Media.PathGeometry>。</span><span class="sxs-lookup"><span data-stu-id="ae14f-110">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="ae14f-111">有关详细信息，请参阅[路径标记语法](path-markup-syntax.md)页。）</span><span class="sxs-lookup"><span data-stu-id="ae14f-111">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="ae14f-112">在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，还可以通过显式使用对象标记绘制椭圆弧。</span><span class="sxs-lookup"><span data-stu-id="ae14f-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw an elliptical arc by explicitly using object tags.</span></span> <span data-ttu-id="ae14f-113">以下是等效于上述[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]标记。</span><span class="sxs-lookup"><span data-stu-id="ae14f-113">The following is equivalent to the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 <span data-ttu-id="ae14f-114">此示例摘自一个更大的示例。</span><span class="sxs-lookup"><span data-stu-id="ae14f-114">This example is part of a larger sample.</span></span> <span data-ttu-id="ae14f-115">有关完整示例，请参阅[几何图形示例](https://go.microsoft.com/fwlink/?LinkID=159989)。</span><span class="sxs-lookup"><span data-stu-id="ae14f-115">For the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae14f-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae14f-116">See also</span></span>
- [<span data-ttu-id="ae14f-117">创建二次贝塞尔曲线</span><span class="sxs-lookup"><span data-stu-id="ae14f-117">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
- [<span data-ttu-id="ae14f-118">创建三次方贝塞尔曲线</span><span class="sxs-lookup"><span data-stu-id="ae14f-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
