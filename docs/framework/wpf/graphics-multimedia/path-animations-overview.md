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
ms.openlocfilehash: 466e22a5b40ddb4f3674422ac7620832b44be51d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="path-animations-overview"></a>路径动画概述
<a name="introduction"></a>本主题介绍了路径动画，使你能够使用几何路径来生成输出值。 路径动画可用于沿着复杂路径移动和旋转对象。  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>系统必备  
 若要了解本主题，你应熟悉[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]动画功能。 动画功能的简介，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。  
  
 因为你使用<xref:System.Windows.Media.PathGeometry>对象以定义路径动画，您还应熟悉<xref:System.Windows.Media.PathGeometry>和不同类型的<xref:System.Windows.Media.PathSegment>对象。 有关详细信息，请参阅[几何图形概述](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)。  
  
<a name="what_is_a_path_animation"></a>   
## <a name="what-is-a-path-animation"></a>什么是路径动画？  
 路径动画，则一种<xref:System.Windows.Media.Animation.AnimationTimeline>使用<xref:System.Windows.Media.PathGeometry>作为其输入。 而不是，设置 From、 或属性 (像对 From/To/By 动画) 或使用关键帧 （与您用于关键帧动画），定义的几何路径并使用它来设置`PathGeometry`路径动画的属性。 路径动画运行时，会从路径中读取 x、y 和角度信息并使用该信息生成其输出。  
  
 路径动画对沿着复杂路径的对象进行动画处理非常有用。 一种方法将沿着路径对对象是使用<xref:System.Windows.Media.MatrixTransform>和<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>转换沿复杂路径的对象。 下面的示例演示此技术，通过使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>对象要进行动画处理<xref:System.Windows.Media.MatrixTransform.Matrix%2A>属性<xref:System.Windows.Media.MatrixTransform>。 <xref:System.Windows.Media.MatrixTransform>应用于一个按钮并使其将沿曲线的路径。 因为<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A>属性设置为`true`，矩形沿该路径的切线旋转。  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 有关详细信息中使用的路径语法[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]示例中，请参阅[路径标记语法](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)概述。 有关完整的示例，请参阅[路径动画示例](http://go.microsoft.com/fwlink/?LinkID=160028)。  
  
 你可以使用的路径动画应用到属性<xref:System.Windows.Media.Animation.Storyboard>中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]和代码，或通过使用<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>代码中的方法。 你还可以使用路径动画创建<xref:System.Windows.Media.Animation.AnimationClock>并将其应用到一个或多个属性。 有关应用动画的不同方法的详细信息，请参阅[属性动画技术概述](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)。  
  
<a name="animation_types"></a>   
## <a name="path-animation-types"></a>路径动画类型  
 由于动画会生成属性值，因此不同的属性类型具有不同的动画类型。 要进行动画处理的属性<xref:System.Double>(如<xref:System.Windows.Media.TranslateTransform.X%2A>属性<xref:System.Windows.Media.TranslateTransform>)，使用动画生成<xref:System.Double>值。 要进行动画处理的属性<xref:System.Windows.Point>，使用动画生成<xref:System.Windows.Point>值，等等。  
  
 路径动画类属于<xref:System.Windows.Media.Animation>命名空间并使用以下命名约定：  
  
 *\<Type>* `AnimationUsingPath`  
  
 其中 *\<Type>* 为该类进行动画处理的值的类型。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供以下路径动画类。  
  
|属性类型|相应的路径动画类|示例|  
|-------------------|----------------------------------------|-------------|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|[沿着路径针对对象进行动画处理（双重动画）](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-double-animation.md)|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>|[沿着路径针对对象进行动画处理（矩阵动画）](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md)|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|[沿着路径针对对象进行动画处理（点动画）](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-point-animation.md)|  
  
 A<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>生成<xref:System.Windows.Media.Matrix>值从其<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.PathGeometry%2A>。 如果用于<xref:System.Windows.Media.MatrixTransform>、<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>可以移动沿路径对象。 如果你设置<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A>属性<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>到`true`，它还会沿着路径的曲线的对象。  
  
 A<xref:System.Windows.Media.Animation.PointAnimationUsingPath>生成<xref:System.Windows.Point>值从 x 坐标和 y 坐标的其<xref:System.Windows.Media.Animation.PointAnimationUsingPath.PathGeometry%2A>。 通过使用<xref:System.Windows.Media.Animation.PointAnimationUsingPath>采用属性进行动画处理<xref:System.Windows.Point>值，可以移动沿路径对象。 A<xref:System.Windows.Media.Animation.PointAnimationUsingPath>无法旋转对象。  
  
 A<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>生成<xref:System.Double>值从其<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>。 通过设置<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.Source%2A>属性，你可以指定是否<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>使用作为其输出的 x 坐标，y 坐标或路径的角度。 你可以使用<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>旋转对象或将其移沿 x 轴或 y 轴。  
  
<a name="pathanimationinput"></a>   
## <a name="path-animation-input"></a>路径动画输入  
 每个路径动画类提供<xref:System.Windows.Media.PathGeometry>指定其输入的属性。 路径动画使用<xref:System.Windows.Media.PathGeometry>来生成其输出值。 <xref:System.Windows.Media.PathGeometry>类允许您描述组成弧、 曲线和行的多个复杂的图形。  
  
 核心<xref:System.Windows.Media.PathGeometry>是一套<xref:System.Windows.Media.PathFigure>对象; 这些对象这样命名是因为每个图描述了中的一个离散形状<xref:System.Windows.Media.PathGeometry>。 每个<xref:System.Windows.Media.PathFigure>组成一个或多个<xref:System.Windows.Media.PathSegment>对象，其中每个描述图一段。  
  
 有多种类型的线段。  
  
|线段类型|描述|  
|------------------|-----------------|  
|<xref:System.Windows.Media.ArcSegment>|创建两个点之间的椭圆弧。|  
|<xref:System.Windows.Media.BezierSegment>|创建两个点之间的三次方贝塞尔曲线。|  
|<xref:System.Windows.Media.LineSegment>|创建两个点之间的直线。|  
|<xref:System.Windows.Media.PolyBezierSegment>|创建一系列三次方贝塞尔曲线。|  
|<xref:System.Windows.Media.PolyLineSegment>|创建一系列直线。|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|创建一系列的二次贝塞尔曲线。|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|创建一条二次贝塞尔曲线。|  
  
 中的段<xref:System.Windows.Media.PathFigure>合并成单一的几何形状，使用作为下一段的起始点的线段的终点。 <xref:System.Windows.Media.PathFigure.StartPoint%2A>属性<xref:System.Windows.Media.PathFigure>指定从中提取第一条线段的点。 每个后续线段都从上一线段的终点开始。 例如，从竖线`10,50`到`10,150`可以通过设置定义<xref:System.Windows.Media.PathFigure.StartPoint%2A>属性`10,50`和创建<xref:System.Windows.Media.LineSegment>与<xref:System.Windows.Media.LineSegment.Point%2A>属性设置的`10,150`。  
  
 有关详细信息<xref:System.Windows.Media.PathGeometry>对象，请参阅[几何图形概述](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)。  
  
 在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，还可以使用特殊的缩写的语法设置<xref:System.Windows.Media.PathGeometry.Figures%2A>属性<xref:System.Windows.Media.PathGeometry>。 有关详细信息，请参阅[路径标记语法](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)概述。  
  
 有关详细信息中使用的路径语法[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]示例中，请参阅[路径标记语法](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)概述。  
  
## <a name="see-also"></a>请参阅  
 [路径动画示例](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [路径标记语法](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)  
 [路径动画操作说明主题](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [属性动画技术概述](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
