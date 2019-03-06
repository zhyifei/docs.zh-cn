---
title: 如何：在 PathGeometry 内部创建多个子路径
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: 0b57d0441c1aa9d5972af1f1c6b989aacba7f87f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353358"
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a><span data-ttu-id="ce4ef-102">如何：在 PathGeometry 内部创建多个子路径</span><span class="sxs-lookup"><span data-stu-id="ce4ef-102">How to: Create Multiple Subpaths Within a PathGeometry</span></span>
<span data-ttu-id="ce4ef-103">此示例演示如何创建在多个子路径<xref:System.Windows.Media.PathGeometry>。</span><span class="sxs-lookup"><span data-stu-id="ce4ef-103">This example shows how to create multiple subpaths in a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="ce4ef-104">若要创建多个子路径，您创建<xref:System.Windows.Media.PathFigure>每一子路径。</span><span class="sxs-lookup"><span data-stu-id="ce4ef-104">To create multiple subpaths, you create a <xref:System.Windows.Media.PathFigure> for each subpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce4ef-105">示例</span><span class="sxs-lookup"><span data-stu-id="ce4ef-105">Example</span></span>  
 <span data-ttu-id="ce4ef-106">以下示例创建两个子路径，每个三角形。</span><span class="sxs-lookup"><span data-stu-id="ce4ef-106">The following example creates two subpaths, each one a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#38](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 <span data-ttu-id="ce4ef-107">下面的示例演示如何使用创建多个子路径<xref:System.Windows.Shapes.Path>和[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]特性语法。</span><span class="sxs-lookup"><span data-stu-id="ce4ef-107">The following example shows how to create multiple subpaths by using a <xref:System.Windows.Shapes.Path> and [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attribute syntax.</span></span> <span data-ttu-id="ce4ef-108">每个`M`，以便此示例将创建一个三角形的两个子路径创建一个新的子路径。</span><span class="sxs-lookup"><span data-stu-id="ce4ef-108">Each `M` creates a new subpath so that the example creates two subpaths that each draw a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#58](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 <span data-ttu-id="ce4ef-109">(请注意，此属性语法实际上创建了<xref:System.Windows.Media.StreamGeometry>的轻量版本<xref:System.Windows.Media.PathGeometry>。</span><span class="sxs-lookup"><span data-stu-id="ce4ef-109">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="ce4ef-110">有关详细信息，请参阅[路径标记语法](path-markup-syntax.md)页。）</span><span class="sxs-lookup"><span data-stu-id="ce4ef-110">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce4ef-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce4ef-111">See also</span></span>
- [<span data-ttu-id="ce4ef-112">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="ce4ef-112">Geometry Overview</span></span>](geometry-overview.md)
