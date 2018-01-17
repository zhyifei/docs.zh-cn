---
title: "位图效果概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0f642c699a0ecf3e3cce328363f90110766002e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="bitmap-effects-overview"></a>位图效果概述
位图效果使设计者和开发者可以将视觉效果应用到呈现的 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 内容上。 例如，位图效果，可以轻松地将应用<xref:System.Windows.Media.Effects.DropShadowBitmapEffect>效果还是模糊效果为图像或按钮。  
  
> [!IMPORTANT]
>  在[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]或更高版本，<xref:System.Windows.Media.Effects.BitmapEffect>类已过时。 如果你尝试使用<xref:System.Windows.Media.Effects.BitmapEffect>类，则您将收到已过时。 未过时的替代项为<xref:System.Windows.Media.Effects.BitmapEffect>类是<xref:System.Windows.Media.Effects.Effect>类。 在大多数情况下，<xref:System.Windows.Media.Effects.Effect>类是快得多。  
  
  
  
<a name="wpf_effects"></a>   
## <a name="wpf-bitmap-effects"></a>WPF 位图效果  
 位图效果 (<xref:System.Windows.Media.Effects.BitmapEffect>对象) 是处理操作的简单像素。 位图效果将<xref:System.Windows.Media.Imaging.BitmapSource>作为输入，并生成一个新<xref:System.Windows.Media.Imaging.BitmapSource>后应用的效果，如模糊或投影。 每个位图效果公开控件的筛选的属性，如属性<xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A>的<xref:System.Windows.Media.Effects.BlurBitmapEffect>。  
  
 作为一种特殊情况，在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，效果可以设置为属性上的实时<xref:System.Windows.Media.Visual>对象，如<xref:System.Windows.Controls.Button>或<xref:System.Windows.Controls.TextBox>。 像素处理在运行时应用并呈现。 在这种情况下，在呈现时<xref:System.Windows.Media.Visual>自动转换为其<xref:System.Windows.Media.Imaging.BitmapSource>等效作为输入提供<xref:System.Windows.Media.Effects.BitmapEffect>。 输出替换<xref:System.Windows.Media.Visual>对象的默认呈现行为。 正因如此<xref:System.Windows.Media.Effects.BitmapEffect>对象强制软件中呈现仅即视觉对象上的没有硬件加速，效果应用时的视觉对象。  
  
-   <xref:System.Windows.Media.Effects.BlurBitmapEffect>模拟显示出焦点的对象的。  
  
-   <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect>创建对象周围的颜色的光环。  
  
-   <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>创建对象后的阴影。  
  
-   <xref:System.Windows.Media.Effects.BevelBitmapEffect>创建凹凸效果，将引发根据指定的曲线图像表面。  
  
-   <xref:System.Windows.Media.Effects.EmbossBitmapEffect>创建凹凸映射的<xref:System.Windows.Media.Visual>以便从人工光源的深度和纹理效果。  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 位图效果在软件模式下呈现。 应用效果的任何对象也都将以软件形式呈现。 在大型视觉对象上使用位图效果或对位图效果的属性进行动画处理时，性能的下降幅度最大。 这并不表示完全不应该以这种方式使用位图效果，而是应谨慎使用，并进行全面测试以确保用户得到预期的体验。  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 位图效果不支持部分信任执行。 应用程序必须具有完全信任权限才能使用位图效果。  
  
<a name="applyeffects"></a>   
## <a name="how-to-apply-an-effect"></a>如何应用效果  
 <xref:System.Windows.Media.Effects.BitmapEffect>位于属性<xref:System.Windows.Media.Visual>。 因此将效果应用于视觉对象，如<xref:System.Windows.Controls.Button>， <xref:System.Windows.Controls.Image>， <xref:System.Windows.Media.DrawingVisual>，或<xref:System.Windows.UIElement>，是简单地设置属性。 <xref:System.Windows.UIElement.BitmapEffect%2A>可以将设置为单个<xref:System.Windows.Media.Effects.BitmapEffect>可以通过使用链接对象或多个效果<xref:System.Windows.Media.Effects.BitmapEffectGroup>对象。  
  
 下面的示例演示如何应用<xref:System.Windows.Media.Effects.BitmapEffect>中[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 下面的示例演示如何应用<xref:System.Windows.Media.Effects.BitmapEffect>在代码中。  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
>  当<xref:System.Windows.Media.Effects.BitmapEffect>应用到布局容器中，如<xref:System.Windows.Controls.DockPanel>或<xref:System.Windows.Controls.Canvas>，效果应用于元素或视觉对象，包括所有子元素的可视化树。  
  
<a name="customeffects"></a>   
## <a name="creating-custom-effects"></a>创建自定义效果  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 还提供非托管接口，用于创建可在托管 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 应用程序中使用的自定义效果。 有关创建自定义位图效果的其他参考资料，请参阅[非托管 WPF 位图效果](https://msdn.microsoft.com/library/ms735092.aspx)文档。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.Effects.BitmapEffectGroup>  
 <xref:System.Windows.Media.Effects.BitmapEffectInput>  
 <xref:System.Windows.Media.Effects.BitmapEffectCollection>  
 [非托管的 WPF 位图效果](https://msdn.microsoft.com/library/ms735092.aspx)  
 [图像处理概述](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [安全性](../../../../docs/framework/wpf/security-wpf.md)  
 [WPF 图形呈现概述](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [2D 图形和图像处理](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)
