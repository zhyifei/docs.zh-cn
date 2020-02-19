---
title: Brush 变换概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], transformation properties
- properties [WPF], transformation
- transformation properties of brushes [WPF]
ms.assetid: 8b9bfc09-12fd-4cd5-b445-99949f27bc39
ms.openlocfilehash: 1d3a56014e0975f3616b7f90021b4290ced5daab
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453125"
---
# <a name="brush-transformation-overview"></a>Brush 变换概述
Brush 类提供两个转换属性： <xref:System.Windows.Media.Brush.Transform%2A> 和 <xref:System.Windows.Media.Brush.RelativeTransform%2A>。 使用这些属性，可以旋转、缩放、倾斜和转换画笔的内容。 本主题介绍这两个属性之间的区别，并提供有关它们的用法示例。  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>先决条件  
 若要了解本主题，应了解要转换的画笔的功能。 有关 <xref:System.Windows.Media.LinearGradientBrush> 和 <xref:System.Windows.Media.RadialGradientBrush>，请参阅[利用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)。 有关 <xref:System.Windows.Media.ImageBrush>、<xref:System.Windows.Media.DrawingBrush>或 <xref:System.Windows.Media.VisualBrush>，请参阅[利用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)。 还应当熟悉[转换概述](transforms-overview.md)中所述的 2D 转换。  
  
<a name="transformversusrelativetransform"></a>   
## <a name="differences-between-the-transform-and-relativetransform-properties"></a>Transform 和 RelativeTransform 属性之间的区别  
 将转换应用于画笔的 <xref:System.Windows.Media.Brush.Transform%2A> 属性时，如果想要变换画笔内容的中心，则需要知道已绘制区域的大小。 假设已绘制区域的宽度为 200 个与设备无关的像素，高度为 150。  如果使用 <xref:System.Windows.Media.RotateTransform> 来围绕中心旋转画笔的输出45度，则应将 <xref:System.Windows.Media.RotateTransform> 的 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 为100，并将 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 指定为75。  
  
 将转换应用于画笔的 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 属性时，该转换将应用于画笔，然后将其输出映射到绘制的区域。 以下列表介绍处理和转换画笔内容的顺序。  
  
1. 处理画笔的内容。 对于 <xref:System.Windows.Media.GradientBrush>，这意味着要确定渐变区域。 对于 <xref:System.Windows.Media.TileBrush>，<xref:System.Windows.Media.TileBrush.Viewbox%2A> 映射到 <xref:System.Windows.Media.TileBrush.Viewport%2A>。 这成为画笔的输出。  
  
2. 将画笔的输出投影到 1 x 1 的转换矩形上。  
  
3. 应用画笔的 <xref:System.Windows.Media.Brush.RelativeTransform%2A>（如果有）。  
  
4. 将转换后的输出投影到要绘制的区域上。  
  
5. 应用画笔的 <xref:System.Windows.Media.Transform>（如果有）。  
  
 因为当画笔的输出映射到 1 x 1 矩形时应用 <xref:System.Windows.Media.Brush.RelativeTransform%2A>，因此，变换中心和偏移值将显示为相对值。 例如，如果使用 <xref:System.Windows.Media.RotateTransform> 来围绕中心旋转画笔的输出45度，则会为 <xref:System.Windows.Media.RotateTransform> 提供 0.5 <xref:System.Windows.Media.RotateTransform.CenterX%2A>，并 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 0.5。  
  
 下图显示了多个画笔的输出，这些画笔使用 "<xref:System.Windows.Media.Brush.RelativeTransform%2A>" 和 "<xref:System.Windows.Media.Brush.Transform%2A>" 属性旋转了45度。  
  
 ![RelativeTransform 和 Transform 属性](./media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm_brushrelativetransform_transform_small")  
  
<a name="relativetransformandtilebrush"></a>   
## <a name="using-relativetransform-with-a-tilebrush"></a>将 RelativeTransform 用于 TileBrush  
 由于平铺画笔比其他画笔更复杂，因此向其中应用 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 可能会产生意外的结果。 例如以下图像。  
  
 ![源图像](./media/graphicsmm-reltransform-1-original-image.jpg "graphicsmm_reltransform_1_original_image")  
  
 下面的示例使用 <xref:System.Windows.Media.ImageBrush> 绘制带有前面图像的矩形区域。 它将 <xref:System.Windows.Media.RotateTransform> 应用到 <xref:System.Windows.Media.ImageBrush> 对象的 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 属性，并将其 <xref:System.Windows.Media.TileBrush.Stretch%2A> 属性设置为 <xref:System.Windows.Media.Stretch.UniformToFill>，这应在延伸以完全填充矩形时保留图像的纵横比。  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 该示例产生下面的输出：  
  
 ![转换后的输出](./media/graphicsmm-reltransform-6-output.png "graphicsmm_reltransform_6_output")  
  
 请注意，即使画笔的 <xref:System.Windows.Media.TileBrush.Stretch%2A> 设置为 <xref:System.Windows.Media.Stretch.UniformToFill>，图像也会扭曲。 这是因为，在画笔的 <xref:System.Windows.Media.TileBrush.Viewbox%2A> 映射到其 <xref:System.Windows.Media.TileBrush.Viewport%2A>之后，会应用相对转换。 以下列表介绍该过程的每个步骤：  
  
1. 使用画笔的 <xref:System.Windows.Media.TileBrush.Stretch%2A> 设置，将画笔的内容（<xref:System.Windows.Media.TileBrush.Viewbox%2A>）投影到其基本图块（<xref:System.Windows.Media.TileBrush.Viewport%2A>）上。  
  
     ![拉伸 Viewbox 以适合视区](./media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm_reltransform_2_viewbox_to_viewport")  
  
2. 将基本图块投影到 1 x 1 的转换矩形上。  
  
     ![将视区映射到转换矩形](./media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm_reltransform_3_output_to_transform")  
  
3. 应用 <xref:System.Windows.Media.RotateTransform>。  
  
     ![应用相对转换](./media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm_reltransform_4_transform_rotate")  
  
4. 将转换后的基本图块投影到要绘制的区域上。  
  
     ![将转换后的画笔投影到输出区域](./media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm_reltransform_5_transform_to_output")  
  
<a name="rotateexample"></a>   
## <a name="example-rotate-an-imagebrush-45-degrees"></a>示例：将 ImageBrush 旋转 45 度  
 下面的示例将 <xref:System.Windows.Media.RotateTransform> 应用到 <xref:System.Windows.Media.ImageBrush>的 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 属性。 <xref:System.Windows.Media.RotateTransform> 对象的 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 和 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 属性都设置为0.5，即内容中心点的相对坐标。 因此，画笔的内容围绕其中心旋转。  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 下一个示例还将 <xref:System.Windows.Media.RotateTransform> 应用到 <xref:System.Windows.Media.ImageBrush>，但使用 <xref:System.Windows.Media.Brush.Transform%2A> 属性，而不是 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 属性。 若要围绕中心旋转画笔，则 <xref:System.Windows.Media.RotateTransform> 对象的 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 和 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 必须设置为绝对坐标。 由于画笔要绘制的矩形为 175 x 90 像素，因此它的中心点为 (87.5, 45)。  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 下图显示了不带转换的画笔，将转换应用于 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 属性，将转换应用于 <xref:System.Windows.Media.Brush.Transform%2A> 属性。  
  
 ![画笔 RelativeTransform 和转换设置](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
 此示例摘自一个更大的示例。 有关完整示例，请参阅[画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)。 有关画笔的详细信息，请参阅 [WPF 画笔概述](wpf-brushes-overview.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Brush.Transform%2A>
- <xref:System.Windows.Media.Brush.RelativeTransform%2A>
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Brush>
- [使用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)
- [使用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)
- [转换概述](transforms-overview.md)
