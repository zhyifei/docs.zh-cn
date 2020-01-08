---
title: 位图效果概述
ms.date: 03/30/2017
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
ms.openlocfilehash: 4a5c304363efe7d0e9bd9e14ff916f8d852ab3a8
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636011"
---
# <a name="bitmap-effects-overview"></a>位图效果概述
使用位图效果，设计人员和开发人员可以将视觉效果应用于呈现的 Windows Presentation Foundation （WPF）内容。 例如，位图效果允许您轻松地将 <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> 效果或模糊效果应用于图像或按钮。  
  
> [!IMPORTANT]
> 在 .NET Framework 4 或更高版本中，<xref:System.Windows.Media.Effects.BitmapEffect> 类已过时。 如果尝试使用 <xref:System.Windows.Media.Effects.BitmapEffect> 类，将会收到过时的异常。 <xref:System.Windows.Media.Effects.BitmapEffect> 类的未过时替代项是 <xref:System.Windows.Media.Effects.Effect> 类。 在大多数情况下，<xref:System.Windows.Media.Effects.Effect> 类的速度要快得多。  

<a name="wpf_effects"></a>   
## <a name="wpf-bitmap-effects"></a>WPF 位图效果  
 位图效果（<xref:System.Windows.Media.Effects.BitmapEffect> 对象）是简单的像素处理操作。 位图效果会将 <xref:System.Windows.Media.Imaging.BitmapSource> 作为输入，并在应用效果后生成新 <xref:System.Windows.Media.Imaging.BitmapSource>，如模糊或投影。 每个位图效果都公开了可控制筛选属性的属性，如 <xref:System.Windows.Media.Effects.BlurBitmapEffect>的 <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A>。  
  
 作为一种特殊情况，在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中，可以将效果设置为实时 <xref:System.Windows.Media.Visual> 对象（如 <xref:System.Windows.Controls.Button> 或 <xref:System.Windows.Controls.TextBox>）的属性。 像素处理在运行时应用并呈现。 在这种情况下，在呈现时，<xref:System.Windows.Media.Visual> 会自动转换为其 <xref:System.Windows.Media.Imaging.BitmapSource> 等效项，并作为输入送进 <xref:System.Windows.Media.Effects.BitmapEffect>。 输出替换 <xref:System.Windows.Media.Visual> 对象的默认呈现行为。 这就是 <xref:System.Windows.Media.Effects.BitmapEffect> 对象强制仅在软件中呈现视觉对象的原因，即，在应用效果时不会对视觉对象进行硬件加速。  
  
- <xref:System.Windows.Media.Effects.BlurBitmapEffect> 模拟显得不到焦点的对象。  
  
- <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect> 在对象的周围创建颜色光环。  
  
- <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> 在对象后面创建阴影。  
  
- <xref:System.Windows.Media.Effects.BevelBitmapEffect> 创建一个斜角，它根据指定的曲线提升图像表面。  
  
- <xref:System.Windows.Media.Effects.EmbossBitmapEffect> 创建一个 <xref:System.Windows.Media.Visual> 的凹凸映射，以获得来自人工光源的深度和纹理。  
  
> [!NOTE]
> WPF 位图效果在软件模式下呈现。 应用效果的任何对象也都将以软件形式呈现。 在大型视觉对象上使用位图效果或对位图效果的属性进行动画处理时，性能的下降幅度最大。 这并不表示完全不应该以这种方式使用位图效果，而是应谨慎使用，并进行全面测试以确保用户得到预期的体验。  
  
> [!NOTE]
> WPF 位图效果不支持部分信任的执行。 应用程序必须具有完全信任权限才能使用位图效果。  
  
<a name="applyeffects"></a>   
## <a name="how-to-apply-an-effect"></a>如何应用效果  
 <xref:System.Windows.Media.Effects.BitmapEffect> 是 <xref:System.Windows.Media.Visual>上的一个属性。 因此，将效果应用到视觉对象（例如 <xref:System.Windows.Controls.Button>、<xref:System.Windows.Controls.Image>、<xref:System.Windows.Media.DrawingVisual>或 <xref:System.Windows.UIElement>）非常简单，只需设置属性即可。 <xref:System.Windows.UIElement.BitmapEffect%2A> 可以设置为单个 <xref:System.Windows.Media.Effects.BitmapEffect> 对象，也可以使用 <xref:System.Windows.Media.Effects.BitmapEffectGroup> 对象链接多个效果。  
  
 下面的示例演示如何在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中应用 <xref:System.Windows.Media.Effects.BitmapEffect>。  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 下面的示例演示如何在代码中应用 <xref:System.Windows.Media.Effects.BitmapEffect>。  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
> 将 <xref:System.Windows.Media.Effects.BitmapEffect> 应用于布局容器（如 <xref:System.Windows.Controls.DockPanel> 或 <xref:System.Windows.Controls.Canvas>）时，会将效果应用到元素或视觉对象的可视化树，包括其所有子元素。  
  
<a name="customeffects"></a>   
## <a name="creating-custom-effects"></a>创建自定义效果  
 WPF 还提供非托管接口，以创建可在托管 WPF 应用程序中使用的自定义效果。 有关创建自定义位图效果的其他参考资料，请参阅[非托管 WPF 位图效果](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh)文档。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Effects.BitmapEffectGroup>
- <xref:System.Windows.Media.Effects.BitmapEffectInput>
- <xref:System.Windows.Media.Effects.BitmapEffectCollection>
- [非托管 WPF 位图效果](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh)
- [图像处理概述](imaging-overview.md)
- [安全](../security-wpf.md)
- [WPF 图形呈现概述](wpf-graphics-rendering-overview.md)
- [2D 图形和图像处理](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
