---
title: "位图效果概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0f642c699a0ecf3e3cce328363f90110766002e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="bitmap-effects-overview"></a><span data-ttu-id="1763d-102">位图效果概述</span><span class="sxs-lookup"><span data-stu-id="1763d-102">Bitmap Effects Overview</span></span>
<span data-ttu-id="1763d-103">位图效果使设计者和开发者可以将视觉效果应用到呈现的 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 内容上。</span><span class="sxs-lookup"><span data-stu-id="1763d-103">Bitmap effects enable designers and developers to apply visual effects to rendered [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] content.</span></span> <span data-ttu-id="1763d-104">例如，位图效果，可以轻松地将应用<xref:System.Windows.Media.Effects.DropShadowBitmapEffect>效果还是模糊效果为图像或按钮。</span><span class="sxs-lookup"><span data-stu-id="1763d-104">For example, bitmap effects allow you to easily apply a <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> effect or a blur effect to an image or a button.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1763d-105">在[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]或更高版本，<xref:System.Windows.Media.Effects.BitmapEffect>类已过时。</span><span class="sxs-lookup"><span data-stu-id="1763d-105">In the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] or later, the <xref:System.Windows.Media.Effects.BitmapEffect> class is obsolete.</span></span> <span data-ttu-id="1763d-106">如果你尝试使用<xref:System.Windows.Media.Effects.BitmapEffect>类，则您将收到已过时。</span><span class="sxs-lookup"><span data-stu-id="1763d-106">If you try to use the <xref:System.Windows.Media.Effects.BitmapEffect> class, you will get an obsolete exception.</span></span> <span data-ttu-id="1763d-107">未过时的替代项为<xref:System.Windows.Media.Effects.BitmapEffect>类是<xref:System.Windows.Media.Effects.Effect>类。</span><span class="sxs-lookup"><span data-stu-id="1763d-107">The non-obsolete alternative to the <xref:System.Windows.Media.Effects.BitmapEffect> class is the <xref:System.Windows.Media.Effects.Effect> class.</span></span> <span data-ttu-id="1763d-108">在大多数情况下，<xref:System.Windows.Media.Effects.Effect>类是快得多。</span><span class="sxs-lookup"><span data-stu-id="1763d-108">In most situations, the <xref:System.Windows.Media.Effects.Effect> class is significantly faster.</span></span>  
  
  
  
<a name="wpf_effects"></a>   
## <a name="wpf-bitmap-effects"></a><span data-ttu-id="1763d-109">WPF 位图效果</span><span class="sxs-lookup"><span data-stu-id="1763d-109">WPF Bitmap Effects</span></span>  
 <span data-ttu-id="1763d-110">位图效果 (<xref:System.Windows.Media.Effects.BitmapEffect>对象) 是处理操作的简单像素。</span><span class="sxs-lookup"><span data-stu-id="1763d-110">Bitmap effects (<xref:System.Windows.Media.Effects.BitmapEffect> object) are simple pixel processing operations.</span></span> <span data-ttu-id="1763d-111">位图效果将<xref:System.Windows.Media.Imaging.BitmapSource>作为输入，并生成一个新<xref:System.Windows.Media.Imaging.BitmapSource>后应用的效果，如模糊或投影。</span><span class="sxs-lookup"><span data-stu-id="1763d-111">A bitmap effect takes a <xref:System.Windows.Media.Imaging.BitmapSource> as an input and produces a new <xref:System.Windows.Media.Imaging.BitmapSource> after applying the effect, such as a blur or drop shadow.</span></span> <span data-ttu-id="1763d-112">每个位图效果公开控件的筛选的属性，如属性<xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A>的<xref:System.Windows.Media.Effects.BlurBitmapEffect>。</span><span class="sxs-lookup"><span data-stu-id="1763d-112">Each bitmap effect exposes properties that can control the filtering properties, such as <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> of <xref:System.Windows.Media.Effects.BlurBitmapEffect>.</span></span>  
  
 <span data-ttu-id="1763d-113">作为一种特殊情况，在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，效果可以设置为属性上的实时<xref:System.Windows.Media.Visual>对象，如<xref:System.Windows.Controls.Button>或<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="1763d-113">As a special case, in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], effects can be set as properties on live <xref:System.Windows.Media.Visual> objects, such as a <xref:System.Windows.Controls.Button> or <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="1763d-114">像素处理在运行时应用并呈现。</span><span class="sxs-lookup"><span data-stu-id="1763d-114">The pixel processing is applied and rendered at run-time.</span></span> <span data-ttu-id="1763d-115">在这种情况下，在呈现时<xref:System.Windows.Media.Visual>自动转换为其<xref:System.Windows.Media.Imaging.BitmapSource>等效作为输入提供<xref:System.Windows.Media.Effects.BitmapEffect>。</span><span class="sxs-lookup"><span data-stu-id="1763d-115">In this case, at the time of rendering, a <xref:System.Windows.Media.Visual> is automatically converted to its <xref:System.Windows.Media.Imaging.BitmapSource> equivalent and is fed as input to the <xref:System.Windows.Media.Effects.BitmapEffect>.</span></span> <span data-ttu-id="1763d-116">输出替换<xref:System.Windows.Media.Visual>对象的默认呈现行为。</span><span class="sxs-lookup"><span data-stu-id="1763d-116">The output replaces the <xref:System.Windows.Media.Visual> object's default rendering behavior.</span></span> <span data-ttu-id="1763d-117">正因如此<xref:System.Windows.Media.Effects.BitmapEffect>对象强制软件中呈现仅即视觉对象上的没有硬件加速，效果应用时的视觉对象。</span><span class="sxs-lookup"><span data-stu-id="1763d-117">This is why <xref:System.Windows.Media.Effects.BitmapEffect> objects force visuals to render in software only i.e. no hardware acceleration on visuals when effects are applied.</span></span>  
  
-   <span data-ttu-id="1763d-118"><xref:System.Windows.Media.Effects.BlurBitmapEffect>模拟显示出焦点的对象的。</span><span class="sxs-lookup"><span data-stu-id="1763d-118"><xref:System.Windows.Media.Effects.BlurBitmapEffect> simulates an object that appears out-of-focus.</span></span>  
  
-   <span data-ttu-id="1763d-119"><xref:System.Windows.Media.Effects.OuterGlowBitmapEffect>创建对象周围的颜色的光环。</span><span class="sxs-lookup"><span data-stu-id="1763d-119"><xref:System.Windows.Media.Effects.OuterGlowBitmapEffect> creates a halo of color around the perimeter of an object.</span></span>  
  
-   <span data-ttu-id="1763d-120"><xref:System.Windows.Media.Effects.DropShadowBitmapEffect>创建对象后的阴影。</span><span class="sxs-lookup"><span data-stu-id="1763d-120"><xref:System.Windows.Media.Effects.DropShadowBitmapEffect> creates a shadow behind an object.</span></span>  
  
-   <span data-ttu-id="1763d-121"><xref:System.Windows.Media.Effects.BevelBitmapEffect>创建凹凸效果，将引发根据指定的曲线图像表面。</span><span class="sxs-lookup"><span data-stu-id="1763d-121"><xref:System.Windows.Media.Effects.BevelBitmapEffect> creates a bevel which raises the surface of an image according to a specified curve.</span></span>  
  
-   <span data-ttu-id="1763d-122"><xref:System.Windows.Media.Effects.EmbossBitmapEffect>创建凹凸映射的<xref:System.Windows.Media.Visual>以便从人工光源的深度和纹理效果。</span><span class="sxs-lookup"><span data-stu-id="1763d-122"><xref:System.Windows.Media.Effects.EmbossBitmapEffect> creates a bump mapping of a <xref:System.Windows.Media.Visual> to give the impression of depth and texture from an artificial light source.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="1763d-123"> 位图效果在软件模式下呈现。</span><span class="sxs-lookup"><span data-stu-id="1763d-123"> bitmap effects are rendered in software mode.</span></span> <span data-ttu-id="1763d-124">应用效果的任何对象也都将以软件形式呈现。</span><span class="sxs-lookup"><span data-stu-id="1763d-124">Any object that applies an effect will also be rendered in software.</span></span> <span data-ttu-id="1763d-125">在大型视觉对象上使用位图效果或对位图效果的属性进行动画处理时，性能的下降幅度最大。</span><span class="sxs-lookup"><span data-stu-id="1763d-125">Performance is degraded the most when using Bitmap effects on large visuals or animating properties of a Bitmap effect.</span></span> <span data-ttu-id="1763d-126">这并不表示完全不应该以这种方式使用位图效果，而是应谨慎使用，并进行全面测试以确保用户得到预期的体验。</span><span class="sxs-lookup"><span data-stu-id="1763d-126">This is not to say that you should not use Bitmap effects in this way at all, but you should use caution and test thoroughly to ensure that your users are getting the experience you expect.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="1763d-127"> 位图效果不支持部分信任执行。</span><span class="sxs-lookup"><span data-stu-id="1763d-127"> bitmap effects do not support partial trust execution.</span></span> <span data-ttu-id="1763d-128">应用程序必须具有完全信任权限才能使用位图效果。</span><span class="sxs-lookup"><span data-stu-id="1763d-128">An application must have full trust permissions to use bitmap effects.</span></span>  
  
<a name="applyeffects"></a>   
## <a name="how-to-apply-an-effect"></a><span data-ttu-id="1763d-129">如何应用效果</span><span class="sxs-lookup"><span data-stu-id="1763d-129">How to Apply an Effect</span></span>  
 <span data-ttu-id="1763d-130"><xref:System.Windows.Media.Effects.BitmapEffect>位于属性<xref:System.Windows.Media.Visual>。</span><span class="sxs-lookup"><span data-stu-id="1763d-130"><xref:System.Windows.Media.Effects.BitmapEffect> is a property on <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="1763d-131">因此将效果应用于视觉对象，如<xref:System.Windows.Controls.Button>， <xref:System.Windows.Controls.Image>， <xref:System.Windows.Media.DrawingVisual>，或<xref:System.Windows.UIElement>，是简单地设置属性。</span><span class="sxs-lookup"><span data-stu-id="1763d-131">Therefore applying effects to Visuals, such as a <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Image>, <xref:System.Windows.Media.DrawingVisual>, or <xref:System.Windows.UIElement>, is as easy as setting a property.</span></span> <span data-ttu-id="1763d-132"><xref:System.Windows.UIElement.BitmapEffect%2A>可以将设置为单个<xref:System.Windows.Media.Effects.BitmapEffect>可以通过使用链接对象或多个效果<xref:System.Windows.Media.Effects.BitmapEffectGroup>对象。</span><span class="sxs-lookup"><span data-stu-id="1763d-132"><xref:System.Windows.UIElement.BitmapEffect%2A> can be set to a single <xref:System.Windows.Media.Effects.BitmapEffect> object or multiple effects can be chained by using the <xref:System.Windows.Media.Effects.BitmapEffectGroup> object.</span></span>  
  
 <span data-ttu-id="1763d-133">下面的示例演示如何应用<xref:System.Windows.Media.Effects.BitmapEffect>中[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1763d-133">The following example demonstrates how to apply a <xref:System.Windows.Media.Effects.BitmapEffect> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 <span data-ttu-id="1763d-134">下面的示例演示如何应用<xref:System.Windows.Media.Effects.BitmapEffect>在代码中。</span><span class="sxs-lookup"><span data-stu-id="1763d-134">The following example demonstrates how to apply a <xref:System.Windows.Media.Effects.BitmapEffect> in code.</span></span>  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
>  <span data-ttu-id="1763d-135">当<xref:System.Windows.Media.Effects.BitmapEffect>应用到布局容器中，如<xref:System.Windows.Controls.DockPanel>或<xref:System.Windows.Controls.Canvas>，效果应用于元素或视觉对象，包括所有子元素的可视化树。</span><span class="sxs-lookup"><span data-stu-id="1763d-135">When a <xref:System.Windows.Media.Effects.BitmapEffect> is applied to a layout container, such as <xref:System.Windows.Controls.DockPanel> or <xref:System.Windows.Controls.Canvas>, the effect is applied to the visual tree of the element or visual, including all of its child elements.</span></span>  
  
<a name="customeffects"></a>   
## <a name="creating-custom-effects"></a><span data-ttu-id="1763d-136">创建自定义效果</span><span class="sxs-lookup"><span data-stu-id="1763d-136">Creating Custom Effects</span></span>  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="1763d-137"> 还提供非托管接口，用于创建可在托管 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 应用程序中使用的自定义效果。</span><span class="sxs-lookup"><span data-stu-id="1763d-137"> also provides unmanaged interfaces to create custom effects that can be used in managed [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications.</span></span> <span data-ttu-id="1763d-138">有关创建自定义位图效果的其他参考资料，请参阅[非托管 WPF 位图效果](https://msdn.microsoft.com/library/ms735092.aspx)文档。</span><span class="sxs-lookup"><span data-stu-id="1763d-138">For additional reference material for creating custom bitmap effects, see the [Unmanaged WPF Bitmap Effect](https://msdn.microsoft.com/library/ms735092.aspx) documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1763d-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="1763d-139">See Also</span></span>  
 <xref:System.Windows.Media.Effects.BitmapEffectGroup>  
 <xref:System.Windows.Media.Effects.BitmapEffectInput>  
 <xref:System.Windows.Media.Effects.BitmapEffectCollection>  
 [<span data-ttu-id="1763d-140">非托管的 WPF 位图效果</span><span class="sxs-lookup"><span data-stu-id="1763d-140">Unmanaged WPF Bitmap Effect</span></span>](https://msdn.microsoft.com/library/ms735092.aspx)  
 [<span data-ttu-id="1763d-141">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="1763d-141">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [<span data-ttu-id="1763d-142">安全性</span><span class="sxs-lookup"><span data-stu-id="1763d-142">Security</span></span>](../../../../docs/framework/wpf/security-wpf.md)  
 [<span data-ttu-id="1763d-143">WPF 图形呈现概述</span><span class="sxs-lookup"><span data-stu-id="1763d-143">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [<span data-ttu-id="1763d-144">2D 图形和图像处理</span><span class="sxs-lookup"><span data-stu-id="1763d-144">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)
