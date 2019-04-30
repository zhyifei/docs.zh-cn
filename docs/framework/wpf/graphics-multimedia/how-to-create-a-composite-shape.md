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
ms.openlocfilehash: de9f7972c7a51ea623c3630fe62bb48f6109317e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052893"
---
# <a name="how-to-create-a-composite-shape"></a><span data-ttu-id="d2c97-102">如何：创建复合形状</span><span class="sxs-lookup"><span data-stu-id="d2c97-102">How to: Create a Composite Shape</span></span>
<span data-ttu-id="d2c97-103">此示例演示如何创建使用复合形状<xref:System.Windows.Media.Geometry>对象并将其显示使用<xref:System.Windows.Shapes.Path>元素。</span><span class="sxs-lookup"><span data-stu-id="d2c97-103">This example shows how to create composite shapes using <xref:System.Windows.Media.Geometry> objects and display them using a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="d2c97-104">在以下示例中， <xref:System.Windows.Media.LineGeometry>， <xref:System.Windows.Media.EllipseGeometry>，和一个<xref:System.Windows.Media.RectangleGeometry>与一起使用<xref:System.Windows.Media.GeometryGroup>创建复合形状。</span><span class="sxs-lookup"><span data-stu-id="d2c97-104">In the following example, a <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>, and a <xref:System.Windows.Media.RectangleGeometry> are used with a <xref:System.Windows.Media.GeometryGroup> to create a composite shape.</span></span> <span data-ttu-id="d2c97-105">然后使用绘制几何图形的<xref:System.Windows.Shapes.Path>元素。</span><span class="sxs-lookup"><span data-stu-id="d2c97-105">The geometries are then drawn using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2c97-106">示例</span><span class="sxs-lookup"><span data-stu-id="d2c97-106">Example</span></span>  
 [!code-xaml[GeometrySample#19](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 <span data-ttu-id="d2c97-107">下图显示在上一个示例中创建的形状。</span><span class="sxs-lookup"><span data-stu-id="d2c97-107">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="d2c97-108">![使用 GeometryGroup 创建的复合几何图形](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span><span class="sxs-lookup"><span data-stu-id="d2c97-108">![A composite geometry created using a GeometryGroup](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span></span>  
<span data-ttu-id="d2c97-109">复合几何图形</span><span class="sxs-lookup"><span data-stu-id="d2c97-109">Composite Geometry</span></span>  
  
 <span data-ttu-id="d2c97-110">可以使用创建更复杂的形状的多边形和形状使用曲线段，如<xref:System.Windows.Media.PathGeometry>。</span><span class="sxs-lookup"><span data-stu-id="d2c97-110">More complex shapes, such as polygons and shapes with curved segments, may be created using a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="d2c97-111">有关示例显示了如何使用创建形状<xref:System.Windows.Media.PathGeometry>，请参阅[使用 PathGeometry 创建形状](how-to-create-a-shape-by-using-a-pathgeometry.md)。</span><span class="sxs-lookup"><span data-stu-id="d2c97-111">For an example showing how to create a shape using a <xref:System.Windows.Media.PathGeometry>, see [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  <span data-ttu-id="d2c97-112">虽然此示例的呈现到屏幕使用形状<xref:System.Windows.Shapes.Path>元素中，<xref:System.Windows.Media.Geometry>也可能会使用对象来描述的内容<xref:System.Windows.Media.GeometryDrawing>或<xref:System.Windows.Media.DrawingContext>。</span><span class="sxs-lookup"><span data-stu-id="d2c97-112">Although this example renders a shape to the screen using a <xref:System.Windows.Shapes.Path> element, <xref:System.Windows.Media.Geometry> objects may also be used to describe the contents of a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="d2c97-113">此外可用于剪辑和命中测试它们。</span><span class="sxs-lookup"><span data-stu-id="d2c97-113">They may also be used for clipping and hit-testing.</span></span>  
  
 <span data-ttu-id="d2c97-114">此示例是更大示例的组成部分；有关完整示例，请参阅[几何图形示例](https://go.microsoft.com/fwlink/?LinkID=159989)。</span><span class="sxs-lookup"><span data-stu-id="d2c97-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>
