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
ms.openlocfilehash: cc97fda98badfc27e8b92a0dde6d5e419575ac6c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379557"
---
# <a name="graphics-and-multimedia"></a><span data-ttu-id="615a5-102">图形和多媒体</span><span class="sxs-lookup"><span data-stu-id="615a5-102">Graphics and Multimedia</span></span>
<a name="introduction"></a>
<span data-ttu-id="615a5-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 为多媒体、 矢量图形、 动画和内容复合，便于开发人员能够生成有趣的用户界面和内容提供支持。</span><span class="sxs-lookup"><span data-stu-id="615a5-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] provides support for multimedia, vector graphics, animation, and content composition, making it easy for developers to build interesting user interfaces and content.</span></span> <span data-ttu-id="615a5-104">使用 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]，可以创建矢量图形或复杂动画，并将媒体集成到应用程序中。</span><span class="sxs-lookup"><span data-stu-id="615a5-104">Using [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], you can create vector graphics or complex animations and integrate media into your applications.</span></span>  
  
 <span data-ttu-id="615a5-105">本主题介绍 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的图形、动画和媒体功能，可用于向应用程序添加图形、转换效果、声音和视频。</span><span class="sxs-lookup"><span data-stu-id="615a5-105">This topic introduces the graphics, animation, and media features of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], which enable you to add graphics, transition effects, sound, and video to your applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="615a5-106">强烈建议不要在 Windows 服务中使用 WPF 类型。</span><span class="sxs-lookup"><span data-stu-id="615a5-106">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="615a5-107">如果尝试在 Windows 服务中使用 WPF 类型，该服务可能无法按预期工作。</span><span class="sxs-lookup"><span data-stu-id="615a5-107">If you attempt to use WPF types in a Windows service, the service may not work as expected.</span></span>   
  
<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>   
## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a><span data-ttu-id="615a5-108">WPF 4 中的图形和多媒体新增功能</span><span class="sxs-lookup"><span data-stu-id="615a5-108">What's New with Graphics and Multimedia in WPF 4</span></span>  
 <span data-ttu-id="615a5-109">进行了与图形和动画相关的多项更改。</span><span class="sxs-lookup"><span data-stu-id="615a5-109">Several changes have been made related to graphics and animations.</span></span>  
  
-   <span data-ttu-id="615a5-110">布局舍入</span><span class="sxs-lookup"><span data-stu-id="615a5-110">Layout Rounding</span></span>  
  
     <span data-ttu-id="615a5-111">当对象边缘落在像素设备中间位置时，与 DPI 无关的图形系统可以创建呈现项目，如模糊或半透明边缘。</span><span class="sxs-lookup"><span data-stu-id="615a5-111">When an object edge falls in the middle of a pixel device, the DPI-independent graphics system can create rendering artifacts, such as blurry or semi-transparent edges.</span></span> <span data-ttu-id="615a5-112">WPF 的以前版本包含像素捕捉以帮助处理这种情况。</span><span class="sxs-lookup"><span data-stu-id="615a5-112">Previous versions of WPF included pixel snapping to help handle this case.</span></span> <span data-ttu-id="615a5-113">Silverlight 2 引入了布局舍入，这是移动元素以使边缘落在整个像素边界上的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="615a5-113">Silverlight 2 introduced layout rounding, which is another way to move elements so that edges fall on whole pixel boundaries.</span></span> <span data-ttu-id="615a5-114">WPF 现在支持与舍入的布局<xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>附加属性上<xref:System.Windows.FrameworkElement>。</span><span class="sxs-lookup"><span data-stu-id="615a5-114">WPF now supports layout rounding with the <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> attached property on <xref:System.Windows.FrameworkElement>.</span></span>  
  
-   <span data-ttu-id="615a5-115">缓存复合</span><span class="sxs-lookup"><span data-stu-id="615a5-115">Cached Composition</span></span>  
  
     <span data-ttu-id="615a5-116">使用新的<xref:System.Windows.Media.BitmapCache>和<xref:System.Windows.Media.BitmapCacheBrush>类，可以缓存为位图的可视化树的复杂部分并大幅缩短呈现时间。</span><span class="sxs-lookup"><span data-stu-id="615a5-116">By using the new <xref:System.Windows.Media.BitmapCache> and <xref:System.Windows.Media.BitmapCacheBrush> classes, you can cache a complex part of the visual tree as a bitmap and greatly improve rendering time.</span></span> <span data-ttu-id="615a5-117">位图仍然能够响应用户输入（如鼠标单击），并且可以像任何画笔一样将其绘制到其他元素上。</span><span class="sxs-lookup"><span data-stu-id="615a5-117">The bitmap remains responsive to user input, such as mouse clicks, and you can paint it onto other elements just like any brush.</span></span>  
  
-   <span data-ttu-id="615a5-118">像素着色器 3 支持</span><span class="sxs-lookup"><span data-stu-id="615a5-118">Pixel Shader 3 Support</span></span>  
  
     <span data-ttu-id="615a5-119">WPF 4 生成的<xref:System.Windows.Media.Effects.ShaderEffect>WPF 3.5 SP1 中引入应用程序使用像素着色器 (PS) 版本 3.0 写入效果，从而支持。</span><span class="sxs-lookup"><span data-stu-id="615a5-119">WPF 4 builds on top of the <xref:System.Windows.Media.Effects.ShaderEffect> support introduced in WPF 3.5 SP1 by allowing applications to write effects by using Pixel Shader (PS) version 3.0.</span></span> <span data-ttu-id="615a5-120">PS 3.0 着色器模型比 PS 2.0 更复杂，从而允许在支持的硬件上使用更多效果。</span><span class="sxs-lookup"><span data-stu-id="615a5-120">The PS 3.0 shader model is more sophisticated than PS 2.0, which allows for even more effects on supported hardware.</span></span>  
  
-   <span data-ttu-id="615a5-121">缓动函数</span><span class="sxs-lookup"><span data-stu-id="615a5-121">Easing Functions</span></span>  
  
     <span data-ttu-id="615a5-122">可以使用缓动函数增强动画，从而提供对动画行为的额外控制。</span><span class="sxs-lookup"><span data-stu-id="615a5-122">You can enhance animations with easing functions, which give you additional control over the behavior of animations.</span></span> <span data-ttu-id="615a5-123">例如，可以应用<xref:System.Windows.Media.Animation.ElasticEase>到动画，以提供类似弹簧的行为的动画。</span><span class="sxs-lookup"><span data-stu-id="615a5-123">For example, you can apply an <xref:System.Windows.Media.Animation.ElasticEase> to an animation to give the animation a springy behavior.</span></span> <span data-ttu-id="615a5-124">有关详细信息，请参阅中的缓动类型<xref:System.Windows.Media.Animation>命名空间。</span><span class="sxs-lookup"><span data-stu-id="615a5-124">For more information, see the easing types in the <xref:System.Windows.Media.Animation> namespace.</span></span>  
  
<a name="graphics_and_rendering"></a>   
## <a name="graphics-and-rendering"></a><span data-ttu-id="615a5-125">图形和呈现</span><span class="sxs-lookup"><span data-stu-id="615a5-125">Graphics and Rendering</span></span>  
 <span data-ttu-id="615a5-126">WPF 引入了对高质量 2-D 图形的支持。</span><span class="sxs-lookup"><span data-stu-id="615a5-126">WPF includes support for high quality 2-D graphics.</span></span> <span data-ttu-id="615a5-127">功能包括画笔、几何、图像、形状和转换。</span><span class="sxs-lookup"><span data-stu-id="615a5-127">The functionality includes brushes, geometries, images, shapes and transformations.</span></span> <span data-ttu-id="615a5-128">有关详细信息，请参阅[图形](graphics.md)。</span><span class="sxs-lookup"><span data-stu-id="615a5-128">For more information, see [Graphics](graphics.md).</span></span> <span data-ttu-id="615a5-129">图形元素的呈现基于<xref:System.Windows.Media.Visual>类。</span><span class="sxs-lookup"><span data-stu-id="615a5-129">The rendering of graphical elements is based on the <xref:System.Windows.Media.Visual> class.</span></span> <span data-ttu-id="615a5-130">屏幕上的视觉对象的结构由可视化树描述。</span><span class="sxs-lookup"><span data-stu-id="615a5-130">The structure of visual objects on the screen is described by the visual tree.</span></span> <span data-ttu-id="615a5-131">有关详细信息，请参阅 [WPF 图形呈现概述](wpf-graphics-rendering-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="615a5-131">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>  
  
### <a name="2-d-shapes"></a><span data-ttu-id="615a5-132">二维形状</span><span class="sxs-lookup"><span data-stu-id="615a5-132">2-D Shapes</span></span>  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="615a5-133">提供常用矢量绘制的 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 形状库，如下图中所示的矩形和椭圆形。</span><span class="sxs-lookup"><span data-stu-id="615a5-133">provides a library of commonly used, vector-drawn [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] shapes, such as rectangles and ellipses, which the following illustration shows.</span></span>  
  
 <span data-ttu-id="615a5-134">![椭圆和矩形](./media/wpfintrofigure4.PNG "WPFIntroFigure4")</span><span class="sxs-lookup"><span data-stu-id="615a5-134">![Ellipses and rectangles](./media/wpfintrofigure4.PNG "WPFIntroFigure4")</span></span>  
  
 <span data-ttu-id="615a5-135">这些内部 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 形状不仅仅是形状：它们是可编程的元素，用于实现常见控件的许多预期功能，包括键盘和鼠标输入。</span><span class="sxs-lookup"><span data-stu-id="615a5-135">These intrinsic [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] shapes are not just shapes: they are programmable elements that implement many of the features that you expect from most common controls, which include keyboard and mouse input.</span></span> <span data-ttu-id="615a5-136">下面的示例演示如何处理<xref:System.Windows.UIElement.MouseUp>通过单击引发事件<xref:System.Windows.Shapes.Ellipse>元素。</span><span class="sxs-lookup"><span data-stu-id="615a5-136">The following example shows how to handle the <xref:System.Windows.UIElement.MouseUp> event raised by clicking an <xref:System.Windows.Shapes.Ellipse> element.</span></span>  
  
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
  
 <span data-ttu-id="615a5-137">下图显示前面的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 标记和代码隐藏的输出。</span><span class="sxs-lookup"><span data-stu-id="615a5-137">The following illustration shows the output for the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind.</span></span>  
  
 <span data-ttu-id="615a5-138">![包含文本“你已单击省略号!”的窗口](./media/wpfintrofigure12.png "WPFIntroFigure12")</span><span class="sxs-lookup"><span data-stu-id="615a5-138">![A window with the text "you clicked the ellipse&#33;"](./media/wpfintrofigure12.png "WPFIntroFigure12")</span></span>  
  
 <span data-ttu-id="615a5-139">有关详细信息，请参阅 [WPF 中的形状和基本绘图概述](shapes-and-basic-drawing-in-wpf-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="615a5-139">For more information, see [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md).</span></span> <span data-ttu-id="615a5-140">有关介绍性示例，请参阅[形状元素示例](https://go.microsoft.com/fwlink/?LinkID=160037)。</span><span class="sxs-lookup"><span data-stu-id="615a5-140">For an introductory sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
### <a name="2-d-geometries"></a><span data-ttu-id="615a5-141">二维几何图形</span><span class="sxs-lookup"><span data-stu-id="615a5-141">2-D Geometries</span></span>  
 <span data-ttu-id="615a5-142">当 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 提供的 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 形状不足时，可以使用对几何和路径的 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 支持来创建自己的形状。</span><span class="sxs-lookup"><span data-stu-id="615a5-142">When the [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] shapes that [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] provides are not sufficient, you can use [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] support for geometries and paths to create your own.</span></span> <span data-ttu-id="615a5-143">下图显示如何使用几何创建形状作为图形画笔和剪裁其他 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 元素。</span><span class="sxs-lookup"><span data-stu-id="615a5-143">The following illustration shows how you can use geometries to create shapes, as a drawing brush, and to clip other [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] elements.</span></span>  
  
 <span data-ttu-id="615a5-144">![Path 的各种用法](./media/wpfintrofigure5.PNG "WPFIntroFigure5")</span><span class="sxs-lookup"><span data-stu-id="615a5-144">![Various uses of a Path](./media/wpfintrofigure5.PNG "WPFIntroFigure5")</span></span>  
  
 <span data-ttu-id="615a5-145">有关详细信息，请参阅 [Geometry 概述](geometry-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="615a5-145">For more information, see [Geometry Overview](geometry-overview.md).</span></span> <span data-ttu-id="615a5-146">有关介绍性示例，请参阅 [Geometry 示例](https://go.microsoft.com/fwlink/?LinkID=159989)。</span><span class="sxs-lookup"><span data-stu-id="615a5-146">For an introductory sample, see [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
### <a name="2-d-effects"></a><span data-ttu-id="615a5-147">二维效果</span><span class="sxs-lookup"><span data-stu-id="615a5-147">2-D Effects</span></span>  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="615a5-148">提供了 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 类的库，可用于创建各种效果。</span><span class="sxs-lookup"><span data-stu-id="615a5-148">provides a library of [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] classes that you can use to create a variety of effects.</span></span> <span data-ttu-id="615a5-149">借助 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 的 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 呈现功能，可以绘制具有渐变、位图、绘图和视频的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 元素，并且可以使用旋转、缩放和倾斜来操作它们。</span><span class="sxs-lookup"><span data-stu-id="615a5-149">The [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] rendering capability of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] provides the ability to paint [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements that have gradients, bitmaps, drawings, and videos; and to manipulate them by using rotation, scaling, and skewing.</span></span> <span data-ttu-id="615a5-150">下图演提供了可使用 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 画笔实现的许多效果的示例。</span><span class="sxs-lookup"><span data-stu-id="615a5-150">The following illustration gives an example of the many effects you can achieve by using [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] brushes.</span></span>  
  
 <span data-ttu-id="615a5-151">![不同画笔的图示](./media/wpfintrofigure6.PNG "WPFIntroFigure6")</span><span class="sxs-lookup"><span data-stu-id="615a5-151">![Illustration of different brushes](./media/wpfintrofigure6.PNG "WPFIntroFigure6")</span></span>  
  
 <span data-ttu-id="615a5-152">有关详细信息，请参阅 [WPF 画笔概述](wpf-brushes-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="615a5-152">For more information, see [WPF Brushes Overview](wpf-brushes-overview.md).</span></span> <span data-ttu-id="615a5-153">有关详细信息，请参阅[画笔示例](https://go.microsoft.com/fwlink/?LinkID=159973)。</span><span class="sxs-lookup"><span data-stu-id="615a5-153">For an introductory sample, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
<a name="rendering"></a>   
## <a name="3-d-rendering"></a><span data-ttu-id="615a5-154">三维呈现</span><span class="sxs-lookup"><span data-stu-id="615a5-154">3-D Rendering</span></span>  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="615a5-155">提供一组 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 呈现功能，这些功能与 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中的 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 图形支持集成，以便创建更精彩的布局、[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 和数据可视化。</span><span class="sxs-lookup"><span data-stu-id="615a5-155">provides a set of [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] rendering capabilities that integrate with [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] graphics support in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] in order for you to create more exciting layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], and data visualization.</span></span> <span data-ttu-id="615a5-156">另一方面，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 支持将 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 图像呈现到 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 形状的表面，下图演示了此功能。</span><span class="sxs-lookup"><span data-stu-id="615a5-156">At one end of the spectrum, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enables you to render [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] images onto the surfaces of [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] shapes, which the following illustration demonstrates.</span></span>  
  
 <span data-ttu-id="615a5-157">![Visual3D 示例屏幕快照](./media/wpfintrofigure13.png "WPFIntroFigure13")</span><span class="sxs-lookup"><span data-stu-id="615a5-157">![Visual3D sample screen shot](./media/wpfintrofigure13.png "WPFIntroFigure13")</span></span>  
  
 <span data-ttu-id="615a5-158">有关详细信息，请参阅 [三维图形概述](3-d-graphics-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="615a5-158">For more information, see [3-D Graphics Overview](3-d-graphics-overview.md).</span></span> <span data-ttu-id="615a5-159">有关介绍性示例，请参阅 [3-D 实体示例](https://go.microsoft.com/fwlink/?LinkID=159964)。</span><span class="sxs-lookup"><span data-stu-id="615a5-159">For an introductory sample, see [3-D Solids Sample](https://go.microsoft.com/fwlink/?LinkID=159964).</span></span>  
  
<a name="animation"></a>   
## <a name="animation"></a><span data-ttu-id="615a5-160">动画</span><span class="sxs-lookup"><span data-stu-id="615a5-160">Animation</span></span>  
 <span data-ttu-id="615a5-161">使用动画，可以让控件和元素变大、抖动、旋转和淡出，并创建有趣的转换等。</span><span class="sxs-lookup"><span data-stu-id="615a5-161">Use animation to make controls and elements grow, shake, spin, and fade; and to create interesting page transitions, and more.</span></span> <span data-ttu-id="615a5-162">由于 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 支持对大多数属性进行动画处理，因此，不仅可以对大多数 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 对象进行动画处理，还可以使用 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 对创建的自定义对象进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="615a5-162">Because [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enables you to animate most properties, not only can you animate most [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] objects, you can also use [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] to animate custom objects that you create.</span></span>  
  
 <span data-ttu-id="615a5-163">![具有动画多维数据集的图像](./media/wpfintrofigure7.png "WPFIntroFigure7")</span><span class="sxs-lookup"><span data-stu-id="615a5-163">![Images of an animated cube](./media/wpfintrofigure7.png "WPFIntroFigure7")</span></span>  
  
 <span data-ttu-id="615a5-164">有关详细信息，请参阅 [动画概述](animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="615a5-164">For more information, see [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="615a5-165">有关介绍性示例，请参阅[动画示例库](https://go.microsoft.com/fwlink/?LinkID=159969)。</span><span class="sxs-lookup"><span data-stu-id="615a5-165">For an introductory sample, see [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
<a name="media"></a>   
## <a name="media"></a><span data-ttu-id="615a5-166">媒体</span><span class="sxs-lookup"><span data-stu-id="615a5-166">Media</span></span>  
 <span data-ttu-id="615a5-167">图像、视频和音频是传达信息和用户体验的富媒体方法。</span><span class="sxs-lookup"><span data-stu-id="615a5-167">Images, video, and audio are media-rich ways of conveying information and user experiences.</span></span>  
  
### <a name="images"></a><span data-ttu-id="615a5-168">图像</span><span class="sxs-lookup"><span data-stu-id="615a5-168">Images</span></span>  
 <span data-ttu-id="615a5-169">图像（包括图标、背景甚至动画部分）是大部分应用程序的核心部分。</span><span class="sxs-lookup"><span data-stu-id="615a5-169">Images, which include icons, backgrounds, and even parts of animations, are a core part of most applications.</span></span> <span data-ttu-id="615a5-170">由于经常需要使用图像，因此 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 公开以各种方式处理它们的功能。</span><span class="sxs-lookup"><span data-stu-id="615a5-170">Because you frequently need to use images, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] exposes the ability to work with them in a variety of ways.</span></span> <span data-ttu-id="615a5-171">下图显示其中一种方法。</span><span class="sxs-lookup"><span data-stu-id="615a5-171">The following illustration shows just one of those ways.</span></span>  
  
 <span data-ttu-id="615a5-172">![样式设置示例屏幕截图](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span><span class="sxs-lookup"><span data-stu-id="615a5-172">![Styling sample screen shot](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span></span>  
  
 <span data-ttu-id="615a5-173">有关详细信息，请参阅 [图像概述](imaging-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="615a5-173">For more information, see [Imaging Overview](imaging-overview.md).</span></span>  
  
### <a name="video-and-audio"></a><span data-ttu-id="615a5-174">视频和音频</span><span class="sxs-lookup"><span data-stu-id="615a5-174">Video and Audio</span></span>  
 <span data-ttu-id="615a5-175">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 的图形功能的核心功能是为处理多媒体（包括视频和音频）提供本机支持。</span><span class="sxs-lookup"><span data-stu-id="615a5-175">A core feature of the graphics capabilities of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] is to provide native support for working with multimedia, which includes video and audio.</span></span> <span data-ttu-id="615a5-176">以下示例介绍如何将媒体播放器插入到应用程序中。</span><span class="sxs-lookup"><span data-stu-id="615a5-176">The following example shows how to insert a media player into an application.</span></span>  
  
```xaml  
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />  
```  
  
 <span data-ttu-id="615a5-177"><xref:System.Windows.Controls.MediaElement> 能够播放视频和音频，并且可扩展，足以允许轻松创建自定义[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="615a5-177"><xref:System.Windows.Controls.MediaElement> is capable of playing both video and audio, and is extensible enough to allow the easy creation of custom [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)].</span></span>  
  
 <span data-ttu-id="615a5-178">有关详细信息，请参阅[多媒体概述](multimedia-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="615a5-178">For more information, see the [Multimedia Overview](multimedia-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="615a5-179">请参阅</span><span class="sxs-lookup"><span data-stu-id="615a5-179">See also</span></span>
- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [<span data-ttu-id="615a5-180">2D 图形和图像处理</span><span class="sxs-lookup"><span data-stu-id="615a5-180">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="615a5-181">WPF 中的形状和基本绘图概述</span><span class="sxs-lookup"><span data-stu-id="615a5-181">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="615a5-182">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="615a5-182">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="615a5-183">使用图像、绘图和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="615a5-183">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="615a5-184">动画和计时操作指南主题</span><span class="sxs-lookup"><span data-stu-id="615a5-184">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="615a5-185">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="615a5-185">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="615a5-186">多媒体概述</span><span class="sxs-lookup"><span data-stu-id="615a5-186">Multimedia Overview</span></span>](multimedia-overview.md)
