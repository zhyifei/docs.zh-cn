---
title: 位图效果概述
ms.date: 03/30/2017
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
ms.openlocfilehash: 4a5e73f21d4ce4988f56c139d13038dca902b5b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186996"
---
# <a name="bitmap-effects-overview"></a>位图效果概述
位图效果使设计人员和开发人员能够将视觉效果应用于渲染的 Windows 演示文稿基础 （WPF） 内容。 例如，位图效果允许您轻松地将<xref:System.Windows.Media.Effects.DropShadowBitmapEffect>效果或模糊效果应用于图像或按钮。  
  
> [!IMPORTANT]
> 在 .NET 框架 4 或<xref:System.Windows.Media.Effects.BitmapEffect>更高版本中，类已过时。 如果尝试使用 类，<xref:System.Windows.Media.Effects.BitmapEffect>将获取过时的异常。 <xref:System.Windows.Media.Effects.BitmapEffect>类的非过时的替代方法是类<xref:System.Windows.Media.Effects.Effect>。 在大多数情况下，<xref:System.Windows.Media.Effects.Effect>类明显更快。  

<a name="wpf_effects"></a>
## <a name="wpf-bitmap-effects"></a>WPF 位图效果  
 位图效果（<xref:System.Windows.Media.Effects.BitmapEffect>对象）是简单的像素处理操作。 位图效果将 用作<xref:System.Windows.Media.Imaging.BitmapSource>输入，并在应用效果后生成<xref:System.Windows.Media.Imaging.BitmapSource>新的效果，如模糊或投影。 每个位图效果公开可以控制筛选属性的属性，例如<xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A>。 <xref:System.Windows.Media.Effects.BlurBitmapEffect>  
  
 作为特殊情况，在 中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]可以将 效果设置为活动<xref:System.Windows.Media.Visual>对象的属性，例如 或<xref:System.Windows.Controls.Button><xref:System.Windows.Controls.TextBox>。 像素处理在运行时应用并呈现。 在这种情况下，在渲染时，将自动<xref:System.Windows.Media.Visual>转换为等效项<xref:System.Windows.Media.Imaging.BitmapSource>，并作为输入馈入 。 <xref:System.Windows.Media.Effects.BitmapEffect> 输出将替换<xref:System.Windows.Media.Visual>对象的默认呈现行为。 这就是为什么<xref:System.Windows.Media.Effects.BitmapEffect>对象强制视觉对象仅在软件中渲染，即应用效果时，视觉对象上没有硬件加速。  
  
- <xref:System.Windows.Media.Effects.BlurBitmapEffect>模拟显示焦点外的对象。  
  
- <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect>在对象周长周围创建颜色光晕。  
  
- <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>在对象后面创建阴影。  
  
- <xref:System.Windows.Media.Effects.BevelBitmapEffect>创建一个斜面，根据指定的曲线提升图像的表面。  
  
- <xref:System.Windows.Media.Effects.EmbossBitmapEffect>创建 的<xref:System.Windows.Media.Visual>凹凸贴图，以便从人工光源给人以深度和纹理的印象。  
  
> [!NOTE]
> WPF 位图效果在软件模式下呈现。 应用效果的任何对象也都将以软件形式呈现。 在大型视觉对象上使用位图效果或对位图效果的属性进行动画处理时，性能的下降幅度最大。 这并不表示完全不应该以这种方式使用位图效果，而是应谨慎使用，并进行全面测试以确保用户得到预期的体验。  
  
> [!NOTE]
> WPF 位映射效果不支持部分信任执行。 应用程序必须具有完全信任权限才能使用位图效果。  
  
<a name="applyeffects"></a>
## <a name="how-to-apply-an-effect"></a>如何应用效果  
 <xref:System.Windows.Media.Effects.BitmapEffect>是 上的<xref:System.Windows.Media.Visual>属性。 因此，将效果应用于 Visuals，如<xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Image>、、<xref:System.Windows.Media.DrawingVisual>或<xref:System.Windows.UIElement>，与设置属性一样简单。 <xref:System.Windows.UIElement.BitmapEffect%2A>可以设置为单个<xref:System.Windows.Media.Effects.BitmapEffect>对象，也可以使用 该<xref:System.Windows.Media.Effects.BitmapEffectGroup>对象链接多个效果。  
  
 下面的示例演示如何<xref:System.Windows.Media.Effects.BitmapEffect>在 中[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]应用 。  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 下面的示例演示如何在代码中应用<xref:System.Windows.Media.Effects.BitmapEffect>。  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
> <xref:System.Windows.Media.Effects.BitmapEffect>当 应用于布局容器（如<xref:System.Windows.Controls.DockPanel>或<xref:System.Windows.Controls.Canvas>）时，效果将应用于元素或视觉对象（包括其所有子元素）的可视化树。  
  
<a name="customeffects"></a>
## <a name="creating-custom-effects"></a>创建自定义效果  
 WPF 还提供非托管接口，以创建可用于托管 WPF 应用程序的自定义效果。 有关创建自定义位图效果的其他参考资料，请参阅[非托管 WPF 位图效果](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh)文档。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Effects.BitmapEffectGroup>
- <xref:System.Windows.Media.Effects.BitmapEffectInput>
- <xref:System.Windows.Media.Effects.BitmapEffectCollection>
- [非托管 WPF 位图效果](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh)
- [图像处理概述](imaging-overview.md)
- [安全性](../security-wpf.md)
- [WPF 图形呈现概述](wpf-graphics-rendering-overview.md)
- [2D 图形和图像处理](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
