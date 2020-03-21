---
title: 变换概述
ms.date: 03/30/2017
helpviewer_keywords:
- transformations [WPF], about transformations
- classes [WPF], 2D transform
- transform classes [WPF], 2D
- 2D transform classes
- FrameworkElement objects [WPF], rotating
- FrameworkElement objects [WPF], skewing
- FrameworkElement objects [WPF], translating
- Transforms [WPF], about Transforms
- FrameworkElement objects [WPF], scaling
ms.assetid: 8f153d5e-ed61-4aa5-a7cd-286f0c427a13
ms.openlocfilehash: c5f29404a301eb023ff24b2890531dede6440ec4
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111954"
---
# <a name="transforms-overview"></a>变换概述
本主题介绍如何使用 2D<xref:System.Windows.Media.Transform>类旋转、缩放、移动（平移）和倾斜<xref:System.Windows.FrameworkElement>对象。  

<a name="whatIsATransformSection"></a>
## <a name="what-is-a-transform"></a>什么是 Transform？  
 定义<xref:System.Windows.Media.Transform>如何映射或转换从一个坐标空间到另一个坐标空间的点。 此映射由转换描述，该<xref:System.Windows.Media.Matrix>转换是包含三列值的<xref:System.Double>三行的集合。  
  
> [!NOTE]
> Windows 演示基础 （WPF） 使用行主矩阵。 矢量表示为行矢量，而非列矢量。  
  
 下表显示了 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 矩阵的结构。  
  
### <a name="a-2d-transformation-matrix"></a>二维变换矩阵  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> 默认值：1.0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> 默认值：0.0|0.0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> 默认值：0.0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> 默认值：1.0|0.0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> 默认值：0.0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> 默认值：0.0|1.0|  
  
 通过操作矩阵值，可以旋转、缩放、倾斜和移动（转换）对象。 例如，如果将第三行（<xref:System.Windows.Media.Matrix.OffsetX%2A>值）第一列中的值更改为 100，则可以使用该值沿 x 轴移动对象 100 个单位。 如果将第二行第二列中的值更改为 3，可使用它来将对象的当前高度拉伸三倍。 如果同时更改这两个值，将使对象沿 x 轴移动 100 个单位，并将其高度拉伸 3 倍。 由于 Windows 演示文稿基础 （WPF） 仅支持仿外转换，因此右列中的值始终为 0、0、1。  
  
 尽管 Windows 演示文稿基础 （WPF） 使您能够直接操作矩阵值，但它也提供了<xref:System.Windows.Media.Transform>多个类，使您能够转换对象而无需知道基础矩阵结构的配置方式。 例如，<xref:System.Windows.Media.ScaleTransform>类使您能够通过设置对象<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>和<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>属性来缩放对象，而不是操作转换矩阵。 同样，<xref:System.Windows.Media.RotateTransform>类使您能够通过设置对象的属性来旋转对象<xref:System.Windows.Media.RotateTransform.Angle%2A>。  
  
<a name="transformClassesSection"></a>
## <a name="transform-classes"></a>转换类  
 Windows 演示基础 （WPF） 为常见<xref:System.Windows.Media.Transform>转换操作提供以下 2D 类：  
  
|类|说明|示例|图示|  
|-----------|-----------------|-------------|------------------|  
|<xref:System.Windows.Media.RotateTransform>|按指定的<xref:System.Windows.Media.RotateTransform.Angle%2A>旋转元素。|[旋转对象](how-to-rotate-an-object.md)|![旋转图](./media/graphicsmm-thumbnails-rotate.png "graphicsmm_thumbnails_rotate")|  
|<xref:System.Windows.Media.ScaleTransform>|按指定<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>和<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>数量缩放元素。|[缩放元素](how-to-scale-an-element.md)|![缩放图](./media/graphicsmm-thumbnails-scale.png "graphicsmm_thumbnails_scale")|  
|<xref:System.Windows.Media.SkewTransform>|按指定<xref:System.Windows.Media.SkewTransform.AngleX%2A>和<xref:System.Windows.Media.SkewTransform.AngleY%2A>数量倾斜元素。|[倾斜元素](how-to-skew-an-element.md)|![扭曲图](./media/graphicsmm-thumbnails-skew.png "graphicsmm_thumbnails_skew")|  
|<xref:System.Windows.Media.TranslateTransform>|按指定<xref:System.Windows.Media.TranslateTransform.X%2A>和<xref:System.Windows.Media.TranslateTransform.Y%2A>数量移动（翻译）元素。|[转换元素](how-to-translate-an-element.md)|![平移图](./media/graphicsmm-thumbnails-translate.png "graphicsmm_thumbnails_translate")|  
  
 对于创建更复杂的转换，Windows 演示文稿基础 （WPF） 提供以下两个类：  
  
|类|说明|示例|  
|-----------|-----------------|-------------|  
|<xref:System.Windows.Media.TransformGroup>|将多个<xref:System.Windows.Media.TransformGroup>对象分组为单个<xref:System.Windows.Media.Transform>对象，然后可以应用于转换属性。|[向一个对象应用多个转换](how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|创建其他<xref:System.Windows.Media.Transform>类未提供的自定义转换。 使用 时<xref:System.Windows.Media.MatrixTransform>，将直接操作矩阵。|[使用 MatrixTransform 创建自定义转换](how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 Windows 演示基础 （WPF） 还提供 3D 转换。 有关更多信息，请参见 <xref:System.Windows.Media.Media3D.Transform3D> 类。  
  
<a name="transformationproperties"></a>
## <a name="common-transformation-properties"></a>常见转换属性  
 转换对象的一种方法是声明适当的<xref:System.Windows.Media.Transform>类型并将其应用于对象的转换属性。 对象类型不同，转换属性的类型也会不同。 下表列出了几种常用的 Windows 演示文稿基础 （WPF） 类型及其转换属性。  
  
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
 转换对象时，不只是转换对象，还会转换该对象所在的坐标空间。 默认情况下，转换基于目标对象坐标系的原点 (0,0) 居中。 唯一的例外<xref:System.Windows.Media.TranslateTransform>是;<xref:System.Windows.Media.TranslateTransform> a 没有要设置的中心属性，因为转换效果是相同的，无论它居中。  
  
 下面的示例使用<xref:System.Windows.Media.RotateTransform>将<xref:System.Windows.Shapes.Rectangle>元素（一种类型为<xref:System.Windows.FrameworkElement>的 ）在其默认中心 （0， 0） 上旋转 45 度。 下图显示了旋转效果。  
  
 ![围绕 (0,0) 旋转 45 度的 FrameworkElement](./media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm_FE_rotated_about_upperleft_corner")  
围绕点 (0,0) 旋转 45 度的矩形元素  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 默认情况下，元素会围绕其左上角 (0, 0) 旋转。 <xref:System.Windows.Media.ScaleTransform><xref:System.Windows.Media.SkewTransform>和<xref:System.Windows.Media.RotateTransform>类提供 CenterX 和 CenterY 属性，使您能够指定应用转换的点。  
  
 下一个示例还使用<xref:System.Windows.Media.RotateTransform>将<xref:System.Windows.Shapes.Rectangle>元素旋转 45 度;如果将 元素旋转 45 度。但是，这一次<xref:System.Windows.Media.RotateTransform.CenterX%2A><xref:System.Windows.Media.RotateTransform.CenterY%2A>的 和 属性被<xref:System.Windows.Media.RotateTransform>设置，以便 具有一个中心 （25， 25）。 下图显示了旋转效果。  
  
 ![围绕 (25, 25) 旋转 45 度的几何](./media/graphicsmm-fe-rotated-about-center.png "graphicsmm_FE_rotated_about_center")  
围绕点 (25, 25) 旋转 45 度矩形元素  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>
## <a name="transforming-a-frameworkelement"></a>转换 FrameworkElement  
 要将转换应用于 ，<xref:System.Windows.FrameworkElement>创建<xref:System.Windows.Media.Transform>并将其应用于<xref:System.Windows.FrameworkElement>类提供的两个属性之一：  
  
- <xref:System.Windows.FrameworkElement.LayoutTransform%2A>• 在布局通过之前应用的转换。 转换应用后，布局系统处理元素转换后的大小和位置。  
  
- <xref:System.Windows.UIElement.RenderTransform%2A>• 修改元素外观但在布局传递完成后应用的转换。 通过使用 属性<xref:System.Windows.UIElement.RenderTransform%2A>而不是 属性，<xref:System.Windows.FrameworkElement.LayoutTransform%2A>可以获得性能优势。  
  
 应使用哪个属性？ 由于它提供的性能优势，因此尽可能使用 该<xref:System.Windows.UIElement.RenderTransform%2A>属性，尤其是在使用动画<xref:System.Windows.Media.Transform>对象时。 缩放、<xref:System.Windows.FrameworkElement.LayoutTransform%2A>旋转或倾斜时使用 该属性，您需要元素的父级以调整到元素的转换大小。 请注意，当对象与<xref:System.Windows.FrameworkElement.LayoutTransform%2A>属性一起使用时，<xref:System.Windows.Media.TranslateTransform>对象似乎对元素没有影响。 这是因为布局系统将转换后的元素返回到其原始位置作为其处理的一部分。  
  
 有关 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中布局的其他信息，请参阅[布局](../advanced/layout.md)概述。  
  
<a name="exampleRotateAnElement45degSection"></a>
## <a name="example-rotate-a-frameworkelement-45-degrees"></a>示例：将 FrameworkElement 旋转 45 度  
 下面的示例使用<xref:System.Windows.Media.RotateTransform>沿时针旋转按钮 45 度。 该按钮包含在具有两个<xref:System.Windows.Controls.StackPanel>其他按钮的 中。  
  
 默认情况下，a<xref:System.Windows.Media.RotateTransform>围绕点旋转 （0， 0）。 由于示例未指定中心点值，按钮将围绕点 (0, 0) 旋转，即其左上角。 <xref:System.Windows.Media.RotateTransform>应用于 属性<xref:System.Windows.UIElement.RenderTransform%2A>。 下图显示转换的结果。  
  
 ![使用 RenderTransform 转换后的按钮](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
从左上角顺时针旋转 45 度  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 下一个示例还使用<xref:System.Windows.Media.RotateTransform>顺时针旋转按钮 45 度，但它也将按钮<xref:System.Windows.UIElement.RenderTransformOrigin%2A>的将设置为 （0.5， 0.5）。 <xref:System.Windows.UIElement.RenderTransformOrigin%2A>属性的值与按钮的大小相关。 因此，该旋转应用到按钮的中心，而非左上角。 下图显示转换的结果。  
  
 ![围绕中心转换后的按钮](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
围绕中心顺时针旋转 45 度  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 下面的示例使用 属性<xref:System.Windows.FrameworkElement.LayoutTransform%2A>而不是 属性<xref:System.Windows.UIElement.RenderTransform%2A>来旋转按钮。  这将导致转换影响按钮的布局，从而触发布局系统的整个处理过程。 因此，按钮在旋转后重新定位，因为它的大小已更改。 下图显示转换的结果。  
  
 ![使用 LayoutTransform 转换后的按钮](./media/graphicsmm-layouttransform.png "graphicsmm_LayoutTransform")  
用于旋转按钮的 LayoutTransform  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample3](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>
## <a name="animating-transformations"></a>对转换进行动画处理  
 因为它们从<xref:System.Windows.Media.Animation.Animatable>类继承，<xref:System.Windows.Media.Transform>因此类可以进行动画处理。 要为<xref:System.Windows.Media.Transform>动画，请将兼容类型的动画应用于要设置动画的属性。  
  
 下面的<xref:System.Windows.Media.Animation.Storyboard>示例使用 和 a，<xref:System.Windows.Media.Animation.DoubleAnimation><xref:System.Windows.Media.RotateTransform><xref:System.Windows.Controls.Button>在单击时进行旋转。  
  
 [!code-xaml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 有关完整示例，请参阅[2D 变换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。 有关动画的详细信息，请参阅[动画概述](animation-overview.md)。  
  
<a name="freezable_features"></a>
## <a name="freezable-features"></a>Freezable 功能  
 <xref:System.Windows.Freezable>由于该<xref:System.Windows.Media.Transform>类从类继承，因此提供了几个特殊功能：<xref:System.Windows.Media.Transform>对象可以声明为[资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)，在多个对象之间共享，使只读以提高性能，克隆，使线程安全。 有关<xref:System.Windows.Freezable>对象提供的不同要素的详细信息，请参阅[可冻结对象概述](../advanced/freezable-objects-overview.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Matrix>
- [如何使用主题](transformations-how-to-topics.md)
- [2D 变换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)
