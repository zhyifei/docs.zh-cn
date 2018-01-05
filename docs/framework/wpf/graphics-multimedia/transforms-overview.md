---
title: "变换概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transformations [WPF], about transformations
- classes [WPF], 2-D transform
- transform classes [WPF], 2-D
- 2-D transform classes
- FrameworkElement objects [WPF], rotating
- FrameworkElement objects [WPF], skewing
- FrameworkElement objects [WPF], translating
- Transforms [WPF], about Transforms
- FrameworkElement objects [WPF], scaling
ms.assetid: 8f153d5e-ed61-4aa5-a7cd-286f0c427a13
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4992b5be4243d8d29b6075c0ad746494dc2eb168
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="transforms-overview"></a>变换概述
本主题介绍如何使用[!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)]<xref:System.Windows.Media.Transform>类才能旋转、 缩放、 移动 （转换），和扭曲<xref:System.Windows.FrameworkElement>对象。  
  
  
<a name="whatIsATransformSection"></a>   
## <a name="what-is-a-transform"></a>什么是 Transform？  
 A<xref:System.Windows.Media.Transform>定义如何映射，或转换从一个坐标空间指向另一个坐标空间。 此映射描述转换<xref:System.Windows.Media.Matrix>，它是包含三个列的三个行的集合<xref:System.Double>值。  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 使用行优先矩阵。 矢量表示为行矢量，而非列矢量。  
  
 下表显示了 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 矩阵的结构。  
  
### <a name="a-2-d-transformation-matrix"></a>2-D 转换矩阵  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> 默认值：1.0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> 默认值：0.0|0.0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> 默认值：0.0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> 默认值：1.0|0.0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> 默认值：0.0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> 默认值：0.0|1.0|  
  
 通过操作矩阵值，可以旋转、缩放、倾斜和移动（转换）对象。 例如，如果你更改第三行的第一列中的值 (<xref:System.Windows.Media.Matrix.OffsetX%2A>值) 为 100，你可以使用它将沿 x 轴对象 100 单位。 如果将第二行第二列中的值更改为 3，可使用它来将对象的当前高度拉伸三倍。 如果同时更改这两个值，将使对象沿 x 轴移动 100 个单位，并将其高度拉伸 3 倍。 由于 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 仅支持仿射转换，因此右边列中的值始终为 0, 0, 1。  
  
 尽管[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]让您以直接操作矩阵值，它还提供了许多<xref:System.Windows.Media.Transform>使你无需知道基础的矩阵结构的配置方式变换对象类。 例如，<xref:System.Windows.Media.ScaleTransform>类使你能够通过设置缩放对象其<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>和<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>属性，而不是操作的转换矩阵。 同样，<xref:System.Windows.Media.RotateTransform>类使你能够旋转对象只需通过设置其<xref:System.Windows.Media.RotateTransform.Angle%2A>属性。  
  
<a name="transformClassesSection"></a>   
## <a name="transform-classes"></a>转换类  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]提供了以下[!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)]<xref:System.Windows.Media.Transform>对常见的转换操作的类：  
  
|类|描述|示例|图示|  
|-----------|-----------------|-------------|------------------|  
|<xref:System.Windows.Media.RotateTransform>|将元素旋转指定<xref:System.Windows.Media.RotateTransform.Angle%2A>。|[旋转对象](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object.md)|![旋转图](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-thumbnails-rotate.png "graphicsmm_thumbnails_rotate")|  
|<xref:System.Windows.Media.ScaleTransform>|指定按比例缩放元素<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>和<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>金额。|[缩放元素](../../../../docs/framework/wpf/graphics-multimedia/how-to-scale-an-element.md)|![缩放图](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-thumbnails-scale.png "graphicsmm_thumbnails_scale")|  
|<xref:System.Windows.Media.SkewTransform>|通过指定扭曲元素<xref:System.Windows.Media.SkewTransform.AngleX%2A>和<xref:System.Windows.Media.SkewTransform.AngleY%2A>金额。|[倾斜元素](../../../../docs/framework/wpf/graphics-multimedia/how-to-skew-an-element.md)|![倾斜图](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-thumbnails-skew.png "graphicsmm_thumbnails_skew")|  
|<xref:System.Windows.Media.TranslateTransform>|将移动 （转换） 由指定的元素<xref:System.Windows.Media.TranslateTransform.X%2A>和<xref:System.Windows.Media.TranslateTransform.Y%2A>金额。|[转换元素](../../../../docs/framework/wpf/graphics-multimedia/how-to-translate-an-element.md)|![转换图](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-thumbnails-translate.png "graphicsmm_thumbnails_translate")|  
  
 为了创建更复杂的转换，[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 提供了以下两个类：  
  
|类|描述|示例|  
|-----------|-----------------|-------------|  
|<xref:System.Windows.Media.TransformGroup>|组合多个<xref:System.Windows.Media.TransformGroup>到单个对象<xref:System.Windows.Media.Transform>，你可以随后应用于转换属性。|[将多个转换应用到对象](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|创建自定义的转换不提供由其他<xref:System.Windows.Media.Transform>类。 当你使用<xref:System.Windows.Media.MatrixTransform>，直接处理矩阵。|[使用 MatrixTransform 创建自定义转换](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 也提供 [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] 转换。 有关更多信息，请参见 <xref:System.Windows.Media.Media3D.Transform3D> 类。  
  
<a name="transformationproperties"></a>   
## <a name="common-transformation-properties"></a>常见转换属性  
 若要转换的对象的一种方法是声明适当<xref:System.Windows.Media.Transform>键入和将其应用于对象的转换属性。 对象类型不同，转换属性的类型也会不同。 下表列出了几种常用 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 类型及其转换属性。  
  
|类型|转换属性|  
|----------|-------------------------------|  
|<xref:System.Windows.Media.Brush>|<xref:System.Windows.Media.Brush.Transform%2A>, <xref:System.Windows.Media.Brush.RelativeTransform%2A>|  
|<xref:System.Windows.Media.ContainerVisual>|<xref:System.Windows.Media.ContainerVisual.Transform%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|  
|<xref:System.Windows.FrameworkElement>|<xref:System.Windows.UIElement.RenderTransform%2A>, <xref:System.Windows.FrameworkElement.LayoutTransform%2A>|  
|<xref:System.Windows.Media.Geometry>|<xref:System.Windows.Media.Geometry.Transform%2A>|  
|<xref:System.Windows.Media.TextEffect>|<xref:System.Windows.Media.TextEffect.Transform%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.RenderTransform%2A>|  
  
<a name="transformcenter"></a>   
## <a name="transformations-and-coordinate-systems"></a>转换和坐标系  
 转换对象时，不只是转换对象，还会转换该对象所在的坐标空间。 默认情况下，转换基于目标对象坐标系的原点 (0,0) 居中。 唯一的例外是<xref:System.Windows.Media.TranslateTransform>;<xref:System.Windows.Media.TranslateTransform>没有 center 属性可供设置，因为转换效果都是而不考虑它处于居中位置相同。  
  
 下面的示例使用<xref:System.Windows.Media.RotateTransform>旋转<xref:System.Windows.Shapes.Rectangle>元素中，一种<xref:System.Windows.FrameworkElement>，旋转 45 度围绕其默认中心，（0，0）。 下图显示了旋转效果。  
  
 ![有关旋转 45 度的 FrameworkElement & #40; 0，0 & #41;] (../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm_FE_rotated_about_upperleft_corner")  
围绕点 (0,0) 旋转 45 度的矩形元素  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 默认情况下，元素会围绕其左上角 (0, 0) 旋转。 <xref:System.Windows.Media.RotateTransform>， <xref:System.Windows.Media.ScaleTransform>，和<xref:System.Windows.Media.SkewTransform>类提供 CenterX 和 CenterY 使您能够指定在其应用转换的点的属性。  
  
 下一个示例还使用<xref:System.Windows.Media.RotateTransform>旋转<xref:System.Windows.Shapes.Rectangle>元素旋转 45 度; 但是，这一次<xref:System.Windows.Media.RotateTransform.CenterX%2A>和<xref:System.Windows.Media.RotateTransform.CenterY%2A>设置属性以便<xref:System.Windows.Media.RotateTransform>具有的中心 （25，25）。 下图显示了旋转效果。  
  
 ![有关的 45 度 & #40; 旋转的几何图形 25，25 & #41;] (../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-fe-rotated-about-center.png "graphicsmm_FE_rotated_about_center")  
围绕点 (25, 25) 旋转 45 度矩形元素  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>   
## <a name="transforming-a-frameworkelement"></a>转换 FrameworkElement  
 若要应用到的转换<xref:System.Windows.FrameworkElement>，创建<xref:System.Windows.Media.Transform>并将其应用到这两个属性之一，<xref:System.Windows.FrameworkElement>类提供：  
  
-   <xref:System.Windows.FrameworkElement.LayoutTransform%2A>– 在布局过程前应用了一种转换。 转换应用后，布局系统处理元素转换后的大小和位置。  
  
-   <xref:System.Windows.UIElement.RenderTransform%2A>– 修改元素的外观，但在布局处理过程完成后应用一种转换。 通过使用<xref:System.Windows.UIElement.RenderTransform%2A>属性而不是<xref:System.Windows.FrameworkElement.LayoutTransform%2A>属性，您可以获得性能优势。  
  
 应使用哪个属性？ 它提供的性能优势，由于使用<xref:System.Windows.UIElement.RenderTransform%2A>属性可能，尤其是当你使用动画时<xref:System.Windows.Media.Transform>对象。 使用<xref:System.Windows.FrameworkElement.LayoutTransform%2A>时缩放、 旋转或扭曲的属性，并且需要为已转换元素的大小调整元素的父级。 请注意，如果它们用于<xref:System.Windows.FrameworkElement.LayoutTransform%2A>属性，<xref:System.Windows.Media.TranslateTransform>对象似乎不起作用的元素上。 这是因为布局系统将转换后的元素返回到其原始位置作为其处理的一部分。  
  
 有关 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中布局的其他信息，请参阅[布局](../../../../docs/framework/wpf/advanced/layout.md)概述。  
  
<a name="exampleRotateAnElement45degSection"></a>   
## <a name="example-rotate-a-frameworkelement-45-degrees"></a>示例：将 FrameworkElement 旋转 45 度  
 下面的示例使用<xref:System.Windows.Media.RotateTransform>若要将按钮顺时针旋转 45 度。 中包含按钮<xref:System.Windows.Controls.StackPanel>具有两个其他按钮。  
  
 默认情况下，<xref:System.Windows.Media.RotateTransform>有关点 （0，0） 旋转。 由于示例未指定中心点值，按钮将围绕点 (0, 0) 旋转，即其左上角。 <xref:System.Windows.Media.RotateTransform>应用于<xref:System.Windows.UIElement.RenderTransform%2A>属性。 下图显示转换的结果。  
  
 ![使用 rendertransform 变换的按钮](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
从左上角顺时针旋转 45 度  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 下一个示例还使用<xref:System.Windows.Media.RotateTransform>旋转 45 度顺时针旋转，一个按钮，但它还设置<xref:System.Windows.UIElement.RenderTransformOrigin%2A>的按钮为 （0.5，0.5）。 值<xref:System.Windows.UIElement.RenderTransformOrigin%2A>属性是相对于该按钮的大小。 因此，该旋转应用到按钮的中心，而非左上角。 下图显示转换的结果。  
  
 ![围绕中心变换的按钮](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
围绕中心顺时针旋转 45 度  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 下面的示例使用<xref:System.Windows.FrameworkElement.LayoutTransform%2A>属性而不是<xref:System.Windows.UIElement.RenderTransform%2A>属性来旋转按钮。  这将导致转换影响按钮的布局，从而触发布局系统的整个处理过程。 因此，按钮在旋转后重新定位，因为它的大小已更改。 下图显示转换的结果。  
  
 ![使用 layouttransform 变换的按钮](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-layouttransform.png "graphicsmm_LayoutTransform")  
用于旋转按钮的 LayoutTransform  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>   
## <a name="animating-transformations"></a>对转换进行动画处理  
 因为它们从其继承<xref:System.Windows.Media.Animation.Animatable>类，<xref:System.Windows.Media.Transform>类可以进行动画处理。 要进行动画处理<xref:System.Windows.Media.Transform>，将兼容类型的动画应用到你想要进行动画处理的属性。  
  
 下面的示例使用<xref:System.Windows.Media.Animation.Storyboard>和<xref:System.Windows.Media.Animation.DoubleAnimation>与<xref:System.Windows.Media.RotateTransform>以便<xref:System.Windows.Controls.Button>数值调节钮在单击时其位置。  
  
 [!code-xaml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 有关完整示例，请参阅 [2D 转换示例](http://go.microsoft.com/fwlink/?LinkID=158252)。 有关动画的详细信息，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Freezable 功能  
 因为它继承自<xref:System.Windows.Freezable>类，<xref:System.Windows.Media.Transform>类提供几个特殊功能：<xref:System.Windows.Media.Transform>对象可声明为[资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)、 多个对象，进行只读的以提高之间共享性能，克隆，并进行线程安全。 有关不同功能提供的详细信息<xref:System.Windows.Freezable>对象，请参阅[可冻结对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.Matrix>  
 [帮助主题](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)  
 [2D 转换示例](http://go.microsoft.com/fwlink/?LinkID=158252)
