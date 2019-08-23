---
title: 不透明蒙板概述
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [WPF], opacity masks
- masks [WPF], opacity
- opacity [WPF], masks
ms.assetid: 22367fab-5f59-4583-abfd-db2bf86eaef7
ms.openlocfilehash: d0fea1aac4efb17811404ce45769615bb2e7234f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929665"
---
# <a name="opacity-masks-overview"></a>不透明蒙板概述
不透明蒙板能够使部分元素或视觉对象透明或部分透明。 若要创建不透明蒙板, 请<xref:System.Windows.Media.Brush>将应用<xref:System.Windows.UIElement.OpacityMask%2A>到元素或<xref:System.Windows.Media.Visual>的属性。  画笔映射到元素或视觉对象，并且画笔的每个像素的不透明度值用于确定生成的元素或视觉对象的每个相应像素的不透明度。  
  
<a name="prereqs"></a>   
## <a name="prerequisites"></a>系统必备  
 本概述假设你熟悉<xref:System.Windows.Media.Brush>对象。 有关使用画笔的介绍，请参阅[使用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)。 有关<xref:System.Windows.Media.ImageBrush> 和<xref:System.Windows.Media.DrawingBrush>的信息, 请参阅[利用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)。  
  
<a name="opacitymasks"></a>   
## <a name="creating-visual-effects-with-opacity-masks"></a>使用不透明蒙板创建视觉效果  
 不透明蒙板的工作原理是将其内容映射到元素或视觉对象。 画笔像素的 alpha 通道则用于确定生成的元素或视觉对象相应像素的不透明度；将忽略画笔的实际颜色。 如果画笔的指定部分是透明的，则元素或视觉对象的相应部分将变为透明。 如果画笔的指定部分是不透明的，则元素或视觉对象的相应部分未改变。 不透明蒙板指定的不透明度与元素或视觉对象呈现的任何不透明度设置相结合。 例如：如果某个元素的不透明度是 25% 并且从完全不透明过渡完全透明时应用不透明蒙板，结果是元素从 25% 的不透明过渡到完全透明。  
  
> [!NOTE]
> 尽管此概述中的示例演示了如何在 image 元素上使用不透明蒙板, 但不透明蒙板可应用<xref:System.Windows.Media.Visual>于任何元素, 包括面板和控件。  
  
 不透明蒙板用于创建有趣的视觉效果，如创建从视图淡入淡出的图像或按钮、向元素添加纹理或结合渐变产生玻璃般的图面。 以下图示演示了不透明蒙板的使用。 棋盘格的背景用于显示蒙板的透明部分。  
  
 ![具有 LinearGradientBrush 不透明蒙板的对象](./media/wcpsdk-graphicsmm-opacitymask-imageexample.png "wcpsdk_graphicsmm_opacitymask_imageexample")  
不透明蒙板示例  
  
<a name="creatingopacitymasks"></a>   
## <a name="creating-an-opacity-mask"></a>创建不透明蒙板  
 若要创建不透明蒙板, 请<xref:System.Windows.Media.Brush>创建, 并将其<xref:System.Windows.UIElement.OpacityMask%2A>应用到元素或视觉对象的属性。 您可以使用任何类型<xref:System.Windows.Media.Brush>作为不透明蒙板。  
  
- <xref:System.Windows.Media.LinearGradientBrush>、<xref:System.Windows.Media.RadialGradientBrush>：用于使元素或视觉对象从视图淡出。  
  
     下图显示了用作<xref:System.Windows.Media.LinearGradientBrush>不透明蒙板的。  
  
     ![具有 LinearGradientBrush 不透明蒙板的对象](./media/wcpsdk-graphicsmm-brushes-lineagradientopacitymasksingle.jpg "wcpsdk_graphicsmm_brushes_lineagradientopacitymasksingle")  
LinearGradientBrush 不透明蒙板示例  
  
- <xref:System.Windows.Media.ImageBrush>：用于创建纹理和软或撕裂边缘效果。  
  
     下图显示了<xref:System.Windows.Media.ImageBrush>用作不透明蒙板。  
  
     ![具有 system.windows.media.imagebrush> 不透明蒙板的对象](./media/wcpsdk-graphicsmm-brushes-imageasopacitymasksingle.jpg "wcpsdk_graphicsmm_brushes_imageasopacitymasksingle")  
LinearGradientBrush 不透明蒙板示例  
  
- <xref:System.Windows.Media.DrawingBrush>：用于从形状、图像和渐变模式创建复杂的不透明蒙板。  
  
     下图显示了用作<xref:System.Windows.Media.DrawingBrush>不透明蒙板的。  
  
     ![具有 system.windows.media.drawingbrush> 不透明蒙板的对象](./media/wcpsdk-drawingbrushasopacitymask-single.jpg "wcpsdk_drawingbrushasopacitymask_single")  
DrawingBrush 不透明蒙板示例  
  
 渐变画笔 (<xref:System.Windows.Media.LinearGradientBrush>和<xref:System.Windows.Media.RadialGradientBrush>) 特别适用于用作不透明蒙板。 由于使用统一颜色<xref:System.Windows.Media.SolidColorBrush> <xref:System.Windows.UIElement.OpacityMask%2A>填充区域, 因此它们会使不太透明蒙板; 使用等效于设置元素的或视觉对象的属性。 <xref:System.Windows.Media.SolidColorBrush>  
  
<a name="creatingopacitymaskswithgradients"></a>   
## <a name="using-a-gradient-as-an-opacity-mask"></a>将渐变用作不透明蒙板  
 要创建渐变填充，请指定两个或多个梯度停止点。 每个渐变停止点包含描述一种颜色和位置（请参阅[使用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)了解关于创建和使用渐变的更多信息）。 将渐变用作不透明蒙板时，除非不使用混合颜色，由不透明蒙板渐变混合 alpha 通道值，否则过程相同。 因此，渐变内容的实际颜色并不重要；只有 alpha 通道或每种颜色的不透明度很重要。 下面是一个示例。  
  
 [!code-xaml[OpacityMasksSnippet#LinearGradientOpacityMaskonImage](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/GradientBrushExample.xaml#lineargradientopacitymaskonimage)]  
  
<a name="specifyinggradientcolors"></a>   
## <a name="specifying-gradient-stops-for-an-opacity-mask"></a>为不透明蒙板指定梯度停止点  
 在上面的示例中, 系统定义的颜色<xref:System.Windows.Media.Colors.Black%2A>用作渐变的开始颜色。 由于<xref:System.Windows.Media.Colors>类中的所有颜色 (除了除外<xref:System.Windows.Media.Colors.Transparent%2A>) 都是完全不透明的, 因此它们可以用于简单地定义渐变不透明蒙板的开始颜色。  
  
 若要在定义不透明蒙板时对 alpha 值进行其他控制, 可以在标记中使用 ARGB 十六进制表示法或使用<xref:System.Windows.Media.Color.FromScRgb%2A?displayProperty=nameWithType>方法指定颜色的 alpha 通道。  
  
<a name="argbsyntax"></a>   
### <a name="specifying-color-opacity-in-xaml"></a>在“XAML”中指定颜色不透明度  
 在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中, 可以使用 ARGB 十六进制表示法来指定各个颜色的不透明度。 ARGB 十六进制表示法使用以下语法:  
  
 `#` **aa** *rrggbb*  
  
 上一行中的 *aa* 表示用于指定颜色不透明度的两位十六进制值。 *rr*、*gg* 和 *bb* 分别表示用于指定颜色中的红色、绿色和蓝色量的两位十六进制值。 每个十六进制数字介于 0-9 或 A-F 之间。 0 是最小值，F 是最大值。 00 的 alpha 值指定完全透明的颜色，而 FF 的 alpha 值创建完全不透明的颜色。  在下面的示例中, 使用十六进制 ARGB 表示法指定两种颜色。 第一种为完全不透明色，第二种为完全透明色。  
  
 [!code-xaml[OpacityMasksSnippet#AARRGGBBValueonOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/GradientBrushExample.xaml#aarrggbbvalueonopacitymask)]  
  
<a name="usingimageasopacitymask"></a>   
## <a name="using-an-image-as-an-opacity-mask"></a>将图像用作不透明蒙板  
 图像也可以用作不透明蒙板。 下面的图像显示了一个示例。 棋盘格的背景用于显示蒙板的透明部分。  
  
 ![具有 system.windows.media.imagebrush> 不透明蒙板的对象](./media/wcpsdk-graphicsmm-imageasopacitymask.png "wcpsdk_graphicsmm_imageasopacitymask")  
不透明蒙板示例  
  
 若要将图像用作不透明蒙板, 请<xref:System.Windows.Media.ImageBrush>使用来包含该图像。 创建用作不透明蒙板的图像时, 请以支持多个透明度级别的格式 (例如可移植网络图形 (PNG)) 保存该图像。 下面的示例显示了用于创建上图的代码。  
  
 [!code-xaml[OpacityMasksSnippet#UIElementOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/ImageBrushExample.xaml#uielementopacitymask)]  
  
<a name="tilingimageopacitymask"></a>   
### <a name="using-a-tiled-image-as-an-opacity-mask"></a>将平铺图像用作不透明蒙板  
 在下面的示例中, 同一图像与其他<xref:System.Windows.Media.ImageBrush>图像一起使用, 但画笔的平铺功能用于生成图像50像素正方形的图块。  
  
 [!code-xaml[OpacityMasksSnippet#TiledImageasOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/ImageBrushExample.xaml#tiledimageasopacitymask)]  
  
<a name="drawingbrushasopacitymask"></a>   
## <a name="creating-an-opacity-mask-from-a-drawing"></a>通过图形创建不透明蒙板  
 图形可用作不透明蒙板。 图形中包含的形状可使用渐变、纯色、图像或甚至其他图形来填充它们自己。 下面的图像显示了图形用作不透明蒙板的示例。 棋盘格的背景用于显示蒙板的透明部分。  
  
 ![具有 system.windows.media.drawingbrush> 不透明蒙板的对象](./media/wcpsdk-drawingbrushasopacitymask.png "wcpsdk_drawingbrushasopacitymask")  
DrawingBrush 不透明蒙板示例  
  
 若要将绘图用作不透明蒙板, 请<xref:System.Windows.Media.DrawingBrush>使用来包含该绘图。 下面的示例显示了用于创建上图的代码：  
  
 [!code-xaml[OpacityMasksSnippet#OpacityMaskfromDrawing](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/DrawingBrushExample.xaml#opacitymaskfromdrawing)]  
  
<a name="tileddrawingbrush"></a>   
### <a name="using-a-tiled-drawing-as-an-opacity-mask"></a>将平铺图形用作不透明蒙板  
 与类似<xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.DrawingBrush> , 可以进行平铺其绘图。 在下面的示例中，图形画笔用于创建平铺的不透明蒙板。  
  
 [!code-xaml[OpacityMasksSnippet#TiledDrawingasOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/DrawingBrushExample.xaml#tileddrawingasopacitymask)]  
  
## <a name="see-also"></a>请参阅

- [使用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)
- [使用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)
