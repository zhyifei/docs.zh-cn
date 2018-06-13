---
title: 如何：在 PathGeometry 内部创建多个子路径
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: 5b129b1bacb5dc2cba87376e8df70e115a5ebd72
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559314"
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a><span data-ttu-id="b9902-102">如何：在 PathGeometry 内部创建多个子路径</span><span class="sxs-lookup"><span data-stu-id="b9902-102">How to: Create Multiple Subpaths Within a PathGeometry</span></span>
<span data-ttu-id="b9902-103">此示例演示如何创建在多个子路径<xref:System.Windows.Media.PathGeometry>。</span><span class="sxs-lookup"><span data-stu-id="b9902-103">This example shows how to create multiple subpaths in a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="b9902-104">若要创建多个子路径，你可以创建<xref:System.Windows.Media.PathFigure>每一子路径。</span><span class="sxs-lookup"><span data-stu-id="b9902-104">To create multiple subpaths, you create a <xref:System.Windows.Media.PathFigure> for each subpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9902-105">示例</span><span class="sxs-lookup"><span data-stu-id="b9902-105">Example</span></span>  
 <span data-ttu-id="b9902-106">下面的示例创建两个路径，每个三角形。</span><span class="sxs-lookup"><span data-stu-id="b9902-106">The following example creates two subpaths, each one a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 <span data-ttu-id="b9902-107">下面的示例演示如何通过创建多个子路径<xref:System.Windows.Shapes.Path>和[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]属性语法。</span><span class="sxs-lookup"><span data-stu-id="b9902-107">The following example shows how to create multiple subpaths by using a <xref:System.Windows.Shapes.Path> and [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attribute syntax.</span></span> <span data-ttu-id="b9902-108">每个`M`创建新的子路径，以便该示例创建一个三角形的两个子路径。</span><span class="sxs-lookup"><span data-stu-id="b9902-108">Each `M` creates a new subpath so that the example creates two subpaths that each draw a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 <span data-ttu-id="b9902-109">(请注意，此特性语法实际创建<xref:System.Windows.Media.StreamGeometry>的轻量版本<xref:System.Windows.Media.PathGeometry>。</span><span class="sxs-lookup"><span data-stu-id="b9902-109">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="b9902-110">有关详细信息，请参阅[路径标记语法](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)页。）</span><span class="sxs-lookup"><span data-stu-id="b9902-110">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9902-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9902-111">See Also</span></span>  
 [<span data-ttu-id="b9902-112">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="b9902-112">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
