---
title: "如何：创建二次贝塞尔曲线"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Bezier curves [WPF], creating
- quadratic Bezier curves [WPF], creating
- graphics [WPF], quadratic Bezier curves
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3cd349ae11a76acda81e44652ca5463b18e1dda8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-quadratic-bezier-curve"></a><span data-ttu-id="f0f98-102">如何：创建二次贝塞尔曲线</span><span class="sxs-lookup"><span data-stu-id="f0f98-102">How to: Create a Quadratic Bezier Curve</span></span>
<span data-ttu-id="f0f98-103">此示例演示如何创建二次贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="f0f98-103">This example shows how to create a quadratic Bezier curve.</span></span>  <span data-ttu-id="f0f98-104">若要创建二次贝塞尔曲线，使用<xref:System.Windows.Media.PathGeometry>， <xref:System.Windows.Media.PathFigure>，和<xref:System.Windows.Media.QuadraticBezierSegment>类。</span><span class="sxs-lookup"><span data-stu-id="f0f98-104">To create a quadratic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.QuadraticBezierSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0f98-105">示例</span><span class="sxs-lookup"><span data-stu-id="f0f98-105">Example</span></span>  
 <span data-ttu-id="f0f98-106">在以下示例中，从 (10100) 到 (300100) 绘制二次贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="f0f98-106">In the following examples, a quadratic Bezier curve is drawn from (10,100) to (300,100).</span></span> <span data-ttu-id="f0f98-107">曲线具有 (200200) 的控制点。</span><span class="sxs-lookup"><span data-stu-id="f0f98-107">The curve has a control point of (200,200).</span></span>  
  
 <span data-ttu-id="f0f98-108">[xaml]</span><span class="sxs-lookup"><span data-stu-id="f0f98-108">[xaml]</span></span>  
  
 <span data-ttu-id="f0f98-109">在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，你可以使用的特性语法来描述的路径。</span><span class="sxs-lookup"><span data-stu-id="f0f98-109">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#54](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 <span data-ttu-id="f0f98-110">[xaml]</span><span class="sxs-lookup"><span data-stu-id="f0f98-110">[xaml]</span></span>  
  
 <span data-ttu-id="f0f98-111">(请注意，此特性语法实际创建<xref:System.Windows.Media.StreamGeometry>的轻量版本<xref:System.Windows.Media.PathGeometry>。</span><span class="sxs-lookup"><span data-stu-id="f0f98-111">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="f0f98-112">有关详细信息，请参阅[路径标记语法](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)页。）</span><span class="sxs-lookup"><span data-stu-id="f0f98-112">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="f0f98-113">在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，还可以绘制使用对象元素语法二次贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="f0f98-113">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a quadratic Bezier curve using object element syntax.</span></span> <span data-ttu-id="f0f98-114">以下内容等效于之前的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="f0f98-114">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="f0f98-115">此示例是更大示例的组成部分；有关完整示例，请参阅[几何图形示例](http://go.microsoft.com/fwlink/?LinkID=159989)。</span><span class="sxs-lookup"><span data-stu-id="f0f98-115">This example is part of larger sample; for the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0f98-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0f98-116">See Also</span></span>  
 [<span data-ttu-id="f0f98-117">创建椭圆弧</span><span class="sxs-lookup"><span data-stu-id="f0f98-117">Create an Elliptical Arc</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)  
 [<span data-ttu-id="f0f98-118">创建三次方贝塞尔曲线</span><span class="sxs-lookup"><span data-stu-id="f0f98-118">Create a Cubic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)
