---
title: 如何：创建复合形状
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: c56053f2b07d6055deac5097a68fd7b80ad704ba
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452092"
---
# <a name="how-to-create-a-composite-shape"></a><span data-ttu-id="f9712-102">如何：创建复合形状</span><span class="sxs-lookup"><span data-stu-id="f9712-102">How to: Create a Composite Shape</span></span>
<span data-ttu-id="f9712-103">此示例演示如何使用 <xref:System.Windows.Media.Geometry> 对象创建复合形状，以及如何使用 <xref:System.Windows.Shapes.Path> 元素来显示它们。</span><span class="sxs-lookup"><span data-stu-id="f9712-103">This example shows how to create composite shapes using <xref:System.Windows.Media.Geometry> objects and display them using a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="f9712-104">在下面的示例中，将 <xref:System.Windows.Media.LineGeometry>、<xref:System.Windows.Media.EllipseGeometry>和 <xref:System.Windows.Media.RectangleGeometry> 与 <xref:System.Windows.Media.GeometryGroup> 一起用于创建复合形状。</span><span class="sxs-lookup"><span data-stu-id="f9712-104">In the following example, a <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>, and a <xref:System.Windows.Media.RectangleGeometry> are used with a <xref:System.Windows.Media.GeometryGroup> to create a composite shape.</span></span> <span data-ttu-id="f9712-105">然后使用 <xref:System.Windows.Shapes.Path> 元素绘制几何。</span><span class="sxs-lookup"><span data-stu-id="f9712-105">The geometries are then drawn using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9712-106">示例</span><span class="sxs-lookup"><span data-stu-id="f9712-106">Example</span></span>  
 [!code-xaml[GeometrySample#19](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 <span data-ttu-id="f9712-107">下图显示在上一个示例中创建的形状。</span><span class="sxs-lookup"><span data-stu-id="f9712-107">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="f9712-108">![使用 GeometryGroup 创建的复合几何图形](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span><span class="sxs-lookup"><span data-stu-id="f9712-108">![A composite geometry created using a GeometryGroup](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span></span>  
<span data-ttu-id="f9712-109">复合几何图形</span><span class="sxs-lookup"><span data-stu-id="f9712-109">Composite Geometry</span></span>  
  
 <span data-ttu-id="f9712-110">对于更复杂的形状（例如带有曲线段的多边形和形状），可以使用 <xref:System.Windows.Media.PathGeometry>创建。</span><span class="sxs-lookup"><span data-stu-id="f9712-110">More complex shapes, such as polygons and shapes with curved segments, may be created using a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="f9712-111">有关演示如何使用 <xref:System.Windows.Media.PathGeometry>创建形状的示例，请参阅[使用 System.windows.media.pathgeometry> 创建形状](how-to-create-a-shape-by-using-a-pathgeometry.md)。</span><span class="sxs-lookup"><span data-stu-id="f9712-111">For an example showing how to create a shape using a <xref:System.Windows.Media.PathGeometry>, see [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  <span data-ttu-id="f9712-112">虽然此示例使用 <xref:System.Windows.Shapes.Path> 元素将形状呈现到屏幕，但 <xref:System.Windows.Media.Geometry> 对象也可用于描述 <xref:System.Windows.Media.GeometryDrawing> 或 <xref:System.Windows.Media.DrawingContext>的内容。</span><span class="sxs-lookup"><span data-stu-id="f9712-112">Although this example renders a shape to the screen using a <xref:System.Windows.Shapes.Path> element, <xref:System.Windows.Media.Geometry> objects may also be used to describe the contents of a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="f9712-113">它们还可用于剪辑和命中测试。</span><span class="sxs-lookup"><span data-stu-id="f9712-113">They may also be used for clipping and hit-testing.</span></span>  
  
 <span data-ttu-id="f9712-114">此示例是更大示例的组成部分；有关完整示例，请参阅[几何图形示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)。</span><span class="sxs-lookup"><span data-stu-id="f9712-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>
