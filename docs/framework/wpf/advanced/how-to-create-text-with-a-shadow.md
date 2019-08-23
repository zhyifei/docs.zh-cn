---
title: 如何：创建有阴影的文本
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: 0fe64e4e9e7aadbd30a38743647251f9fa49ba95
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960445"
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="905c0-102">如何：创建有阴影的文本</span><span class="sxs-lookup"><span data-stu-id="905c0-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="905c0-103">本节中的示例演示如何为所显示的文本创建阴影效果。</span><span class="sxs-lookup"><span data-stu-id="905c0-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="905c0-104">示例</span><span class="sxs-lookup"><span data-stu-id="905c0-104">Example</span></span>  
 <span data-ttu-id="905c0-105">对象允许您为[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]对象创建各种投影效果。 <xref:System.Windows.Media.Effects.DropShadowEffect></span><span class="sxs-lookup"><span data-stu-id="905c0-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="905c0-106">以下示例显示了应用于文本的投影效果。</span><span class="sxs-lookup"><span data-stu-id="905c0-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="905c0-107">在本例中，阴影是柔和阴影，这意味着阴影颜色模糊化。</span><span class="sxs-lookup"><span data-stu-id="905c0-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 ![柔和度&#61;为0.25 的文本阴影](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg) 
  
 <span data-ttu-id="905c0-109">可以通过设置<xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A>属性来控制阴影的宽度。</span><span class="sxs-lookup"><span data-stu-id="905c0-109">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="905c0-110">值`4.0`指示阴影宽度为4像素。</span><span class="sxs-lookup"><span data-stu-id="905c0-110">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="905c0-111">您可以通过修改<xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A>属性来控制阴影的柔和度或模糊度。</span><span class="sxs-lookup"><span data-stu-id="905c0-111">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="905c0-112">值为`0.0`指示不进行模糊处理。</span><span class="sxs-lookup"><span data-stu-id="905c0-112">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="905c0-113">以下代码示例演示如何创建柔和阴影。</span><span class="sxs-lookup"><span data-stu-id="905c0-113">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
> <span data-ttu-id="905c0-114">这些阴影效果不会经历[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]文本呈现管道。</span><span class="sxs-lookup"><span data-stu-id="905c0-114">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="905c0-115">因此，在使用这些效果时，将禁用 ClearType。</span><span class="sxs-lookup"><span data-stu-id="905c0-115">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="905c0-116">以下示例显示了应用于文本的硬投影效果。</span><span class="sxs-lookup"><span data-stu-id="905c0-116">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="905c0-117">在此例中，阴影不模糊。</span><span class="sxs-lookup"><span data-stu-id="905c0-117">In this case, the shadow is not blurred.</span></span>  
  
 ![柔和度&#61; 0 的文本阴影](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg) 
  
 <span data-ttu-id="905c0-119">可以通过将<xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A>属性设置为来`0.0`创建硬阴影, 这表示不使用模糊处理。</span><span class="sxs-lookup"><span data-stu-id="905c0-119">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="905c0-120">您可以通过修改<xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>属性来控制阴影的方向。</span><span class="sxs-lookup"><span data-stu-id="905c0-120">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="905c0-121">将此属性的方向值设置为介于和`0` `360`之间的度数。</span><span class="sxs-lookup"><span data-stu-id="905c0-121">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="905c0-122">下图显示了<xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>属性设置的方向值。</span><span class="sxs-lookup"><span data-stu-id="905c0-122">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 ![阴影的 DropShadow 程度设置](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 <span data-ttu-id="905c0-124">以下代码示例演示如何创建硬阴影。</span><span class="sxs-lookup"><span data-stu-id="905c0-124">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="905c0-125">使用模糊效果</span><span class="sxs-lookup"><span data-stu-id="905c0-125">Using a Blur Effect</span></span>  
 <span data-ttu-id="905c0-126"><xref:System.Windows.Media.Effects.BlurBitmapEffect>可用于创建可放置在文本对象之后的类似于阴影的效果。</span><span class="sxs-lookup"><span data-stu-id="905c0-126">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="905c0-127">应用于文本的模糊位图效果在各个方向上均匀地对文本进行模糊化。</span><span class="sxs-lookup"><span data-stu-id="905c0-127">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="905c0-128">以下示例显示了应用于文本的模糊效果。</span><span class="sxs-lookup"><span data-stu-id="905c0-128">The following example shows a blur effect applied to text.</span></span>  
  
 ![使用 BlurBitmapEffect 的文本阴影](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 <span data-ttu-id="905c0-130">以下代码示例演示如何创建模糊效果。</span><span class="sxs-lookup"><span data-stu-id="905c0-130">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="905c0-131">使用转换变换</span><span class="sxs-lookup"><span data-stu-id="905c0-131">Using a Translate Transform</span></span>  
 <span data-ttu-id="905c0-132"><xref:System.Windows.Media.TranslateTransform>可用于创建可放置在文本对象之后的类似于阴影的效果。</span><span class="sxs-lookup"><span data-stu-id="905c0-132">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="905c0-133">下面的代码示例使用<xref:System.Windows.Media.TranslateTransform>来偏移文本。</span><span class="sxs-lookup"><span data-stu-id="905c0-133">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="905c0-134">在本示例中，主要文本下方略微偏移的文本副本营造出了阴影效果。</span><span class="sxs-lookup"><span data-stu-id="905c0-134">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 ![使用 TranslateTransform 的文本阴影](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)    
  
 <span data-ttu-id="905c0-136">以下代码示例演示如何创建转换以实现阴影效果。</span><span class="sxs-lookup"><span data-stu-id="905c0-136">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
