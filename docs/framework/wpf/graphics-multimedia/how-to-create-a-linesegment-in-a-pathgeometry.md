---
title: "如何：在 PathGeometry 中创建 LineSegment"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- line segments [WPF], creating
- graphics [WPF], line segments
ms.assetid: 0155ed47-a20d-49a7-a306-186d8e07fbc4
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96ad746edc45e7482ac7e8d36a8bb881923c0f04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-linesegment-in-a-pathgeometry"></a><span data-ttu-id="5c090-102">如何：在 PathGeometry 中创建 LineSegment</span><span class="sxs-lookup"><span data-stu-id="5c090-102">How to: Create a LineSegment in a PathGeometry</span></span>
<span data-ttu-id="5c090-103">此示例演示如何创建一条线段。</span><span class="sxs-lookup"><span data-stu-id="5c090-103">This example shows how to create a line segment.</span></span> <span data-ttu-id="5c090-104">若要创建一条直线段，使用<xref:System.Windows.Media.PathGeometry>， <xref:System.Windows.Media.PathFigure>，和<xref:System.Windows.Media.LineSegment>类。</span><span class="sxs-lookup"><span data-stu-id="5c090-104">To create a line segment, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.LineSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c090-105">示例</span><span class="sxs-lookup"><span data-stu-id="5c090-105">Example</span></span>  
 <span data-ttu-id="5c090-106">下面的示例绘制<xref:System.Windows.Media.LineSegment>从 （10，50） 到 （200，70）。</span><span class="sxs-lookup"><span data-stu-id="5c090-106">The following examples draw a <xref:System.Windows.Media.LineSegment> from (10, 50) to (200, 70).</span></span> <span data-ttu-id="5c090-107">下图显示得到的<xref:System.Windows.Media.LineSegment>; 已添加了网格背景以显示坐标系统。</span><span class="sxs-lookup"><span data-stu-id="5c090-107">The following illustration shows the resulting <xref:System.Windows.Media.LineSegment>; a grid background was added to show the coordinate system.</span></span>  
  
 <span data-ttu-id="5c090-108">![Pathfigure 中的一个 Linesegment](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment")</span><span class="sxs-lookup"><span data-stu-id="5c090-108">![A LineSegment in a PathFigure](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment")</span></span>  
<span data-ttu-id="5c090-109">从 (10,50) 绘制到 (200,70) 的 LineSegment</span><span class="sxs-lookup"><span data-stu-id="5c090-109">A LineSegment drawn from (10,50) to (200,70)</span></span>  
  
 <span data-ttu-id="5c090-110">[xaml]</span><span class="sxs-lookup"><span data-stu-id="5c090-110">[xaml]</span></span>  
  
 <span data-ttu-id="5c090-111">在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 中，可以使用属性语法来描述路径。</span><span class="sxs-lookup"><span data-stu-id="5c090-111">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use attribute syntax to describe a path.</span></span>  
  
```xaml  
<Path Stroke="Black" StrokeThickness="1"    
  Data="M 10,50 L 200,70" />  
```  
  
 <span data-ttu-id="5c090-112">[xaml]</span><span class="sxs-lookup"><span data-stu-id="5c090-112">[xaml]</span></span>  
  
 <span data-ttu-id="5c090-113">(请注意，此特性语法实际创建<xref:System.Windows.Media.StreamGeometry>的轻量版本<xref:System.Windows.Media.PathGeometry>。</span><span class="sxs-lookup"><span data-stu-id="5c090-113">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="5c090-114">有关详细信息，请参阅[路径标记语法](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)页。）</span><span class="sxs-lookup"><span data-stu-id="5c090-114">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="5c090-115">在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中，还可以使用对象元素语法来绘制线段。</span><span class="sxs-lookup"><span data-stu-id="5c090-115">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a line segment by using object element syntax.</span></span> <span data-ttu-id="5c090-116">以下内容等效于之前的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="5c090-116">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
```xaml  
<Path Stroke="Black" StrokeThickness="1">  
  <Path.Data>  
    <PathGeometry>  
      <PathFigure StartPoint="10,50">  
        <LineSegment Point="200,70" />  
      </PathFigure>  
    </PathGeometry>  
  </Path.Data>  
</Path>  
```  
  
```csharp  
PathFigure myPathFigure = new PathFigure();  
myPathFigure.StartPoint = new Point(10, 50);  
  
LineSegment myLineSegment = new LineSegment();  
myLineSegment.Point = new Point(200, 70);  
  
PathSegmentCollection myPathSegmentCollection = new PathSegmentCollection();  
myPathSegmentCollection.Add(myLineSegment);  
  
myPathFigure.Segments = myPathSegmentCollection;  
  
PathFigureCollection myPathFigureCollection = new PathFigureCollection();  
myPathFigureCollection.Add(myPathFigure);  
  
PathGeometry myPathGeometry = new PathGeometry();  
myPathGeometry.Figures = myPathFigureCollection;  
  
Path myPath = new Path();  
myPath.Stroke = Brushes.Black;  
myPath.StrokeThickness = 1;  
myPath.Data = myPathGeometry;  
```  
  
```vb  
Dim myPathFigure As New PathFigure()  
            myPathFigure.StartPoint = New Point(10, 50)  
  
            Dim myLineSegment As New LineSegment()  
            myLineSegment.Point = New Point(200, 70)  
  
            Dim myPathSegmentCollection As New PathSegmentCollection()  
            myPathSegmentCollection.Add(myLineSegment)  
  
            myPathFigure.Segments = myPathSegmentCollection  
  
            Dim myPathFigureCollection As New PathFigureCollection()  
            myPathFigureCollection.Add(myPathFigure)  
  
            Dim myPathGeometry As New PathGeometry()  
            myPathGeometry.Figures = myPathFigureCollection  
  
            Dim myPath As New Path()  
            myPath.Stroke = Brushes.Black  
            myPath.StrokeThickness = 1  
            myPath.Data = myPathGeometry  
```  
  
 <span data-ttu-id="5c090-117">此示例是更大示例的组成部分；有关完整示例，请参阅[几何图形示例](http://go.microsoft.com/fwlink/?LinkID=159989)。</span><span class="sxs-lookup"><span data-stu-id="5c090-117">This example is part of larger sample; for the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c090-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c090-118">See Also</span></span>  
 <xref:System.Windows.Media.PathFigure>  
 <xref:System.Windows.Media.PathGeometry>  
 <xref:System.Windows.Media.GeometryDrawing>  
 <xref:System.Windows.Shapes.Path>  
 [<span data-ttu-id="5c090-119">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="5c090-119">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
