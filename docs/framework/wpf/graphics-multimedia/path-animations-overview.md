---
title: 路径动画概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], paths
- path animations [WPF]
ms.assetid: 979c732c-df74-47a6-be96-8e07b3707d53
ms.openlocfilehash: 07628d26c8222c7c01f58826a36a15e13dc31ff4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181864"
---
# <a name="path-animations-overview"></a>路径动画概述
<a name="introduction"></a>本主题介绍了路径动画，使你能够使用几何路径来生成输出值。 路径动画可用于沿着复杂路径移动和旋转对象。  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>系统必备  
 要理解本主题，您应该熟悉[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]动画功能。 有关动画功能的简介，请参阅[动画概述](animation-overview.md)。  
  
 由于使用<xref:System.Windows.Media.PathGeometry>对象定义路径动画，因此还应熟悉<xref:System.Windows.Media.PathGeometry>和不同类型的<xref:System.Windows.Media.PathSegment>对象。 有关详细信息，请参阅[几何概述](geometry-overview.md)。  
  
<a name="what_is_a_path_animation"></a>
## <a name="what-is-a-path-animation"></a>什么是路径动画？  
 路径动画是使用 的<xref:System.Windows.Media.Animation.AnimationTimeline>一<xref:System.Windows.Media.PathGeometry>种类型，用作其输入。 而不是设置"从"、"到"或"按"属性（如对 From/To/By 动画执行）或使用关键帧（如用于关键帧动画），而是定义几何路径并使用它来设置路径动画`PathGeometry`的属性。 路径动画运行时，会从路径中读取 x、y 和角度信息并使用该信息生成其输出。  
  
 路径动画对沿着复杂路径的对象进行动画处理非常有用。 沿路径移动对象的一种方法是使用<xref:System.Windows.Media.MatrixTransform>和<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>沿复杂路径转换对象。 下面的示例演示了此技术，<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>方法是使用 对象为<xref:System.Windows.Media.MatrixTransform.Matrix%2A>属性设置动画<xref:System.Windows.Media.MatrixTransform>。 <xref:System.Windows.Media.MatrixTransform>应用于按钮，使其沿曲线路径移动。 由于<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A>属性设置为`true`，矩形沿路径的切线旋转。  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 有关[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]示例中使用的路径语法的详细信息，请参阅[路径标记语法](path-markup-syntax.md)概述。 有关完整示例，请参阅[路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)。  
  
 可以使用<xref:System.Windows.Media.Animation.Storyboard>in[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]和 代码或在代码中使用 方法将<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>路径动画应用于属性。 您还可以使用路径动画创建 ，<xref:System.Windows.Media.Animation.AnimationClock>并将其应用于一个或多个属性。 有关应用动画的不同方法的详细信息，请参阅[属性动画技术概述](property-animation-techniques-overview.md)。  
  
<a name="animation_types"></a>
## <a name="path-animation-types"></a>路径动画类型  
 由于动画会生成属性值，因此不同的属性类型具有不同的动画类型。 要为<xref:System.Double>采用 （如<xref:System.Windows.Media.TranslateTransform.X%2A>属性<xref:System.Windows.Media.TranslateTransform>） 的属性设置动画，请使用生成<xref:System.Double>值的动画。 要为采用<xref:System.Windows.Point>的属性设置动画，请使用生成<xref:System.Windows.Point>值的动画，等等。  
  
 路径动画类属于命名空间<xref:System.Windows.Media.Animation>，并使用以下命名约定：  
  
 *\<键入>*`AnimationUsingPath`  
  
 *\<类型>* 是类动画的值类型。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供以下路径动画类。  
  
|属性类型|相应的路径动画类|示例|  
|-------------------|----------------------------------------|-------------|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|[沿着路径针对对象进行动画处理（双精度动画）](how-to-animate-an-object-along-a-path-double-animation.md)|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>|[沿着路径针对对象进行动画处理（矩阵动画）](how-to-animate-an-object-along-a-path-matrix-animation.md)|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|[沿着路径针对对象进行动画处理（点动画）](how-to-animate-an-object-along-a-path-point-animation.md)|  
  
 从<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath><xref:System.Windows.Media.Matrix>生成值从<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.PathGeometry%2A>其 。 当 与<xref:System.Windows.Media.MatrixTransform>中使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>时，可以沿路径移动对象。 如果将 的属性<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A><xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>设置为`true`，它还会沿路径的曲线旋转对象。  
  
 A <xref:System.Windows.Media.Animation.PointAnimationUsingPath> <xref:System.Windows.Point>从 其<xref:System.Windows.Media.Animation.PointAnimationUsingPath.PathGeometry%2A>的 x 坐标和 y 坐标生成值。 通过使用<xref:System.Windows.Media.Animation.PointAnimationUsingPath>对获取<xref:System.Windows.Point>值的属性设置动画，可以沿路径移动对象。 无法<xref:System.Windows.Media.Animation.PointAnimationUsingPath>旋转对象。  
  
 从<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath><xref:System.Double>生成值从<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>其 。 通过设置属性<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.Source%2A>，可以指定<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>路径的 x 坐标、y 坐标还是角度作为其输出。 可以使用<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>旋转对象或沿 x 轴或 y 轴移动对象。  
  
<a name="pathanimationinput"></a>
## <a name="path-animation-input"></a>路径动画输入  
 每个路径动画类都提供了<xref:System.Windows.Media.PathGeometry>用于指定其输入的属性。 路径动画使用<xref:System.Windows.Media.PathGeometry>生成其输出值。 该<xref:System.Windows.Media.PathGeometry>类允许您描述由弧、曲线和线组成的多个复杂图形。  
  
 在 的核心是<xref:System.Windows.Media.PathGeometry><xref:System.Windows.Media.PathFigure>对象的集合;这些对象之所以如此命名，是因为每个图形都描述了 中的<xref:System.Windows.Media.PathGeometry>离散形状。 每个<xref:System.Windows.Media.PathFigure>对象由一个或多个<xref:System.Windows.Media.PathSegment>对象组成，每个对象都描述了图形的一段。  
  
 有多种类型的线段。  
  
|线段类型|说明|  
|------------------|-----------------|  
|<xref:System.Windows.Media.ArcSegment>|在两点之间创建一条椭圆弧。|  
|<xref:System.Windows.Media.BezierSegment>|在两点之间创建一个三次方贝塞尔曲线。|  
|<xref:System.Windows.Media.LineSegment>|创建两个点之间的直线。|  
|<xref:System.Windows.Media.PolyBezierSegment>|创建一系列三次方贝塞尔曲线。|  
|<xref:System.Windows.Media.PolyLineSegment>|创建一系列直线。|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|创建一系列二次贝塞尔曲线。|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|创建二次贝塞尔曲线。|  
  
 中的线段<xref:System.Windows.Media.PathFigure>合并为单个几何形状，该形状使用线段的端点作为下一个段的起点。 的属性<xref:System.Windows.Media.PathFigure.StartPoint%2A><xref:System.Windows.Media.PathFigure>指定从中绘制第一个段的点。 每个后续段都从上一段的终点开始。 例如，`10,50``10,150`可以通过将<xref:System.Windows.Media.PathFigure.StartPoint%2A>属性设置为 和`10,50`创建<xref:System.Windows.Media.LineSegment>属性<xref:System.Windows.Media.LineSegment.Point%2A>设置为 的`10,150`  
  
 有关<xref:System.Windows.Media.PathGeometry>对象的详细信息，请参阅[几何概述](geometry-overview.md)。  
  
 在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中，还可以使用特殊的缩写语法来设置<xref:System.Windows.Media.PathGeometry.Figures%2A>的属性。 <xref:System.Windows.Media.PathGeometry> 有关详细信息，请参阅[路径标记语法](path-markup-syntax.md)概述。  
  
 有关[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]示例中使用的路径语法的详细信息，请参阅[路径标记语法](path-markup-syntax.md)概述。  
  
## <a name="see-also"></a>另请参阅

- [路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [路径标记语法](path-markup-syntax.md)
- [路径动画帮助主题](path-animation-how-to-topics.md)
- [动画概述](animation-overview.md)
- [属性动画技术概述](property-animation-techniques-overview.md)
