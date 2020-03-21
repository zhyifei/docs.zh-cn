---
title: 图形和多媒体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- media [WPF], features
- video effects [WPF]
- sound effects [WPF]
- animation [WPF], features
- graphics features [WPF]
- transition effects [WPF]
ms.assetid: 1817d9dc-3d6c-46cb-afc8-63b0bae35e37
ms.openlocfilehash: 8636afcc5b63b71dc729812a7f3eb4945ba49494
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112032"
---
# <a name="graphics-and-multimedia"></a>图形和多媒体

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 为多媒体、矢量图形、动画和内容复合提供支持，使开发者可以轻松生成有趣的用户界面和内容。 使用 Visual Studio，您可以创建矢量图形或复杂动画，并将媒体集成到应用程序中。

本主题介绍 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的图形、动画和媒体功能，可用于向应用程序添加图形、转换效果、声音和视频。

> [!NOTE]
> 强烈建议不要在 Windows 服务中使用 WPF 类型。 如果尝试在 Windows 服务中使用 WPF 类型，该服务可能无法按预期工作。

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a>WPF 4 中的图形和多媒体新增功能

进行了与图形和动画相关的多项更改。

- 布局舍入

  当对象边缘落在像素设备中间位置时，与 DPI 无关的图形系统可以创建呈现项目，如模糊或半透明边缘。 WPF 的以前版本包含像素捕捉以帮助处理这种情况。 Silverlight 2 引入了布局舍入，这是移动元素以使边缘落在整个像素边界上的另一种方法。 WPF 现在支持布局舍入，<xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>在 上<xref:System.Windows.FrameworkElement>附加属性。

- 缓存复合

  通过使用 new<xref:System.Windows.Media.BitmapCache>和<xref:System.Windows.Media.BitmapCacheBrush>类，可以将可视化树的复杂部分缓存为位图，并极大地缩短渲染时间。 位图仍然能够响应用户输入（如鼠标单击），并且可以像任何画笔一样将其绘制到其他元素上。

- 像素着色器 3 支持

  WPF 4 基于 WPF 3.5 SP1 中引入<xref:System.Windows.Media.Effects.ShaderEffect>的支持，允许应用程序使用像素分片 （PS） 版本 3.0 写入效果。 PS 3.0 着色器模型比 PS 2.0 更复杂，从而允许在支持的硬件上使用更多效果。

- 缓动函数

  可以使用缓动函数增强动画，从而提供对动画行为的额外控制。 例如，可以将 对<xref:System.Windows.Media.Animation.ElasticEase>动画应用，为动画提供弹簧行为。 有关详细信息，请参阅命名空间中的<xref:System.Windows.Media.Animation>缓动类型。

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a>图形和呈现

WPF 支持高质量 2D 图形。 功能包括画笔、几何、图像、形状和转换。 有关详细信息，请参阅[图形](graphics.md)。 图形元素的呈现基于类<xref:System.Windows.Media.Visual>。 屏幕上的视觉对象的结构由可视化树描述。 有关详细信息，请参阅 [WPF 图形呈现概述](wpf-graphics-rendering-overview.md)。

### <a name="2d-shapes"></a>2D 形状

WPF 提供了常用的矢量绘制的 2D 形状（如矩形和椭圆）的库，下图显示了这些形状。

![显示椭圆和矩形的图表。](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

这些固有的 WPF 形状不仅仅是形状：它们是可编程元素，它们实现了您期望从最常见的控件（包括键盘和鼠标输入）中实现的许多功能。 下面的示例演示如何处理通过单击<xref:System.Windows.UIElement.MouseUp><xref:System.Windows.Shapes.Ellipse>元素引发的事件。

```xaml
<Window
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  x:Class="Window1" >
  <Ellipse Fill="LightBlue" MouseUp="ellipseButton_MouseUp" />
</Window>
```

```csharp
public partial class Window1  : Window
{
    void ellipseButton_MouseUp(object sender, MouseButtonEventArgs e)
    {
        MessageBox.Show("You clicked the ellipse!");
    }
}
```

```vb
Partial Public Class Window1
    Inherits Window
    Private Sub ellipseButton_MouseUp(ByVal sender As Object, ByVal e As MouseButtonEventArgs)
        MessageBox.Show("You clicked the ellipse!")
    End Sub
End Class
```

下图显示前面的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 标记和代码隐藏的输出。

![一个留言框，上面写着"你点击了椭圆！](./media/index/messagebox-text-output.png)

有关详细信息，请参阅 [WPF 中的形状和基本绘图概述](shapes-and-basic-drawing-in-wpf-overview.md)。 有关介绍性示例，请参阅[形状元素示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)。

### <a name="2d-geometries"></a>2D 几何

当 WPF 提供的 2D 形状不足时，可以使用 WPF 支持几何体和路径创建自己的形状和路径。 下图显示了如何使用几何图形创建形状（作为绘图画笔）和剪辑其他 WPF 元素。

![显示如何使用几何图形创建形状的屏幕截图。](./media/index/use-geometries-create-shapes.png)

有关详细信息，请参阅[几何概述](geometry-overview.md)。 有关介绍性示例，请参阅 [Geometry 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)。

### <a name="2d-effects"></a>2D 效果

WPF 提供了一个包含 2D 类的库，可用于创建各种效果。 WPF 的 2D 渲染功能提供了绘制[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]具有渐变、位图、绘图和视频的元素的功能;并使用旋转、缩放和倾斜来操作它们。 下图举例说明了使用 WPF 画笔可以实现的许多效果。

![显示不同 WPF 画笔和油漆元素的插图。](./media/index/brushes-paint-elements.png)

有关详细信息，请参阅 [WPF 画笔概述](wpf-brushes-overview.md)。 有关详细信息，请参阅[画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)。

<a name="rendering"></a>

## <a name="3d-rendering"></a>3D 渲染

WPF 提供一组 3D 渲染功能，这些功能与 WPF 中的 2D 图形支持集成，[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]以便创建更令人兴奋的布局、和数据可视化。 在频谱的一端，WPF 使您能够将 2D 图像渲染到 3D 形状的表面，下图演示了这一点。

![显示具有不同纹理的 3D 形状的示例屏幕截图。](./media/index/visual-three-dimensional-shape.png)

有关详细信息，请参阅[3D 图形概述](3-d-graphics-overview.md)。 有关介绍性示例，请参阅[3D 实体示例](https://go.microsoft.com/fwlink/?LinkID=159964)。

<a name="animation"></a>

## <a name="animation"></a>动画

使用动画，可以让控件和元素变大、抖动、旋转和淡出，并创建有趣的转换等。 由于 WPF 使您能够为大多数属性设置动画，因此不仅可以为大多数 WPF 对象设置动画，还可以使用 WPF 为创建的自定义对象设置动画。

![动画立方体的屏幕截图。](./media/index/animate-custom-objects.png)

有关详细信息，请参阅 [动画概述](animation-overview.md)。 有关介绍性示例，请参阅[动画示例库](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)。

<a name="media"></a>

## <a name="media"></a>媒体

图像、视频和音频是传达信息和用户体验的富媒体方法。

### <a name="images"></a>映像

图像（包括图标、背景甚至动画部分）是大部分应用程序的核心部分。 由于您经常需要使用图像，WPF 公开了以各种方式使用它们的能力。 下图显示其中一种方法。

![样式示例屏幕截图](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

有关详细信息，请参阅 [图像概述](imaging-overview.md)。

### <a name="video-and-audio"></a>视频和音频

WPF 图形功能的核心功能是提供用于多媒体（包括视频和音频）的本机支持。 以下示例介绍如何将媒体播放器插入到应用程序中。

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<xref:System.Windows.Controls.MediaElement>能够同时播放视频和音频，并且可扩展到足以轻松创建自定义 UIs。

有关详细信息，请参阅[多媒体概述](multimedia-overview.md)。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [2D 图形和图像处理](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [WPF 中的形状和基本绘图概述](shapes-and-basic-drawing-in-wpf-overview.md)
- [使用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)
- [使用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)
- [动画和计时帮助主题](animation-and-timing-how-to-topics.md)
- [3D 图形概述](3-d-graphics-overview.md)
- [多媒体概述](multimedia-overview.md)
