---
title: 如何：使用 StreamGeometry 创建形状
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], shapes
- shapes [WPF], creating with StreamGeometry class
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
ms.openlocfilehash: 54819f62b262227017e12b2066a0747107b68900
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560358"
---
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a><span data-ttu-id="9438b-102">如何：使用 StreamGeometry 创建形状</span><span class="sxs-lookup"><span data-stu-id="9438b-102">How to: Create a Shape Using a StreamGeometry</span></span>
<span data-ttu-id="9438b-103"><xref:System.Windows.Media.StreamGeometry> 是轻量替代<xref:System.Windows.Media.PathGeometry>用于创建几何形状。</span><span class="sxs-lookup"><span data-stu-id="9438b-103"><xref:System.Windows.Media.StreamGeometry> is light-weight alternative to <xref:System.Windows.Media.PathGeometry> for creating geometric shapes.</span></span> <span data-ttu-id="9438b-104">使用<xref:System.Windows.Media.StreamGeometry>需要来描述复杂的几何图形，但不是希望支持数据绑定、 动画或修改的开销。</span><span class="sxs-lookup"><span data-stu-id="9438b-104">Use a <xref:System.Windows.Media.StreamGeometry> when you need to describe a complex geometry but do not want the overhead of supporting data binding, animation, or modification.</span></span> <span data-ttu-id="9438b-105">例如，由于其效率，<xref:System.Windows.Media.StreamGeometry>类是一个不错的选择，用于描述装饰器。</span><span class="sxs-lookup"><span data-stu-id="9438b-105">For example, because of its efficiency, the <xref:System.Windows.Media.StreamGeometry> class is a good choice for describing adorners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9438b-106">示例</span><span class="sxs-lookup"><span data-stu-id="9438b-106">Example</span></span>  
 <span data-ttu-id="9438b-107">下面的示例使用的特性语法创建一个三角形<xref:System.Windows.Media.StreamGeometry>中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9438b-107">The following example uses attribute syntax to create a triangular <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 <span data-ttu-id="9438b-108">有关详细信息<xref:System.Windows.Media.StreamGeometry>属性语法，请参阅[路径标记语法](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)页。</span><span class="sxs-lookup"><span data-stu-id="9438b-108">For more information about <xref:System.Windows.Media.StreamGeometry> attribute syntax, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9438b-109">示例</span><span class="sxs-lookup"><span data-stu-id="9438b-109">Example</span></span>  
 <span data-ttu-id="9438b-110">下一个示例使用<xref:System.Windows.Media.StreamGeometry>若要在代码中定义一个三角形。</span><span class="sxs-lookup"><span data-stu-id="9438b-110">The next example uses a <xref:System.Windows.Media.StreamGeometry> to define a triangle in code.</span></span> <span data-ttu-id="9438b-111">首先，该示例创建<xref:System.Windows.Media.StreamGeometry>，然后获取<xref:System.Windows.Media.StreamGeometryContext>并使用它来描绘三角形。</span><span class="sxs-lookup"><span data-stu-id="9438b-111">First, the example creates a <xref:System.Windows.Media.StreamGeometry>, then obtains a <xref:System.Windows.Media.StreamGeometryContext> and uses it to describe the triangle.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="9438b-112">示例</span><span class="sxs-lookup"><span data-stu-id="9438b-112">Example</span></span>  
 <span data-ttu-id="9438b-113">下一个示例创建一个使用方法<xref:System.Windows.Media.StreamGeometry>和<xref:System.Windows.Media.StreamGeometryContext>定义几何形状基于指定的参数。</span><span class="sxs-lookup"><span data-stu-id="9438b-113">The next example creates a method that uses a <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.StreamGeometryContext> to define a geometric shape based on specified parameters.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="9438b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="9438b-114">See Also</span></span>  
 <xref:System.Windows.Media.PathGeometry>  
 <xref:System.Windows.Media.StreamGeometry>  
 <xref:System.Windows.Media.StreamGeometryContext>  
 [<span data-ttu-id="9438b-115">使用 PathGeometry 创建形状</span><span class="sxs-lookup"><span data-stu-id="9438b-115">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)  
 [<span data-ttu-id="9438b-116">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="9438b-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
