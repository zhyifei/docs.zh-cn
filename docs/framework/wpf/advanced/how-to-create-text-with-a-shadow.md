---
title: 如何：创建具有阴影的文本
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: 4d200aa980e8f2e6d22291669dfb07db54a5f0c0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370666"
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="d3eb7-102">如何：创建具有阴影的文本</span><span class="sxs-lookup"><span data-stu-id="d3eb7-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="d3eb7-103">本节中的示例演示如何为所显示的文本创建阴影效果。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3eb7-104">示例</span><span class="sxs-lookup"><span data-stu-id="d3eb7-104">Example</span></span>  
 <span data-ttu-id="d3eb7-105"><xref:System.Windows.Media.Effects.DropShadowEffect>对象允许你创建的阴影效果的各种[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]对象。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="d3eb7-106">以下示例显示了应用于文本的投影效果。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="d3eb7-107">在本例中，阴影是柔和阴影，这意味着阴影颜色模糊化。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 <span data-ttu-id="d3eb7-108">![文本阴影的柔和度&#61;0.25](./media/shadowtext01.jpg "ShadowText01")</span><span class="sxs-lookup"><span data-stu-id="d3eb7-108">![Text shadow with Softness &#61; 0.25](./media/shadowtext01.jpg "ShadowText01")</span></span>  
<span data-ttu-id="d3eb7-109">具有柔和阴影的文本的示例</span><span class="sxs-lookup"><span data-stu-id="d3eb7-109">Example of text with a soft shadow</span></span>  
  
 <span data-ttu-id="d3eb7-110">您可以通过设置来控制阴影的宽度<xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-110">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="d3eb7-111">值为`4.0`指示阴影宽度为 4 个像素。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-111">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="d3eb7-112">您可以控制柔和度，或通过修改阴影的模糊<xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-112">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="d3eb7-113">值为`0.0`指示无模糊。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-113">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="d3eb7-114">以下代码示例演示如何创建柔和阴影。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-114">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  <span data-ttu-id="d3eb7-115">这些柔和效果不会[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]文本呈现管道。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-115">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="d3eb7-116">因此，在使用这些效果时，将禁用 ClearType。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-116">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="d3eb7-117">以下示例显示了应用于文本的硬投影效果。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-117">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="d3eb7-118">在此例中，阴影不模糊。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-118">In this case, the shadow is not blurred.</span></span>  
  
 <span data-ttu-id="d3eb7-119">![文本阴影的柔和度&#61;0](./media/shadowtext02.jpg "ShadowText02")</span><span class="sxs-lookup"><span data-stu-id="d3eb7-119">![Text shadow with Softness &#61; 0](./media/shadowtext02.jpg "ShadowText02")</span></span>  
<span data-ttu-id="d3eb7-120">具有硬阴影的文本的示例</span><span class="sxs-lookup"><span data-stu-id="d3eb7-120">Example of text with a hard shadow</span></span>  
  
 <span data-ttu-id="d3eb7-121">可以通过设置创建硬阴影<xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A>属性设置为`0.0`，指示使用无模糊。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-121">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="d3eb7-122">可以通过修改控制阴影的方向<xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-122">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="d3eb7-123">设置此属性的方向值为之间的度数`0`和`360`。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-123">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="d3eb7-124">下图显示了的方向值<xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>属性设置。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-124">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 <span data-ttu-id="d3eb7-125">![阴影的 DropShadow 程度设置](./media/shadowtext08.png "ShadowText08")</span><span class="sxs-lookup"><span data-stu-id="d3eb7-125">![DropShadow degree setting of shadow](./media/shadowtext08.png "ShadowText08")</span></span>  
<span data-ttu-id="d3eb7-126">DropShadow 方向示意图</span><span class="sxs-lookup"><span data-stu-id="d3eb7-126">DropShadow Direction diagram</span></span>  
  
 <span data-ttu-id="d3eb7-127">以下代码示例演示如何创建硬阴影。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-127">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="d3eb7-128">使用模糊效果</span><span class="sxs-lookup"><span data-stu-id="d3eb7-128">Using a Blur Effect</span></span>  
 <span data-ttu-id="d3eb7-129">一个<xref:System.Windows.Media.Effects.BlurBitmapEffect>可用于创建可放置在文本对象之后的类似于阴影的效果。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-129">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="d3eb7-130">应用于文本的模糊位图效果在各个方向上均匀地对文本进行模糊化。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-130">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="d3eb7-131">以下示例显示了应用于文本的模糊效果。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-131">The following example shows a blur effect applied to text.</span></span>  
  
 <span data-ttu-id="d3eb7-132">![使用 BlurBitmapEffect 的文本阴影](./media/shadowtext06.jpg "ShadowText06")</span><span class="sxs-lookup"><span data-stu-id="d3eb7-132">![Text shadow using a BlurBitmapEffect](./media/shadowtext06.jpg "ShadowText06")</span></span>  
<span data-ttu-id="d3eb7-133">具有模糊效果的文本的示例</span><span class="sxs-lookup"><span data-stu-id="d3eb7-133">Example of text with a blur effect</span></span>  
  
 <span data-ttu-id="d3eb7-134">以下代码示例演示如何创建模糊效果。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-134">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="d3eb7-135">使用转换变换</span><span class="sxs-lookup"><span data-stu-id="d3eb7-135">Using a Translate Transform</span></span>  
 <span data-ttu-id="d3eb7-136">一个<xref:System.Windows.Media.TranslateTransform>可用于创建可放置在文本对象之后的类似于阴影的效果。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-136">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="d3eb7-137">下面的代码示例使用<xref:System.Windows.Media.TranslateTransform>来偏移文本。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-137">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="d3eb7-138">在本示例中，主要文本下方略微偏移的文本副本营造出了阴影效果。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-138">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 <span data-ttu-id="d3eb7-139">![使用 TranslateTransform 的文本阴影](./media/shadowtext07.jpg "ShadowText07")</span><span class="sxs-lookup"><span data-stu-id="d3eb7-139">![Text shadow using a TranslateTransform](./media/shadowtext07.jpg "ShadowText07")</span></span>  
<span data-ttu-id="d3eb7-140">使用转换功能实现阴影效果的文本的示例</span><span class="sxs-lookup"><span data-stu-id="d3eb7-140">Example of text using a transform for a shadow effect</span></span>  
  
 <span data-ttu-id="d3eb7-141">以下代码示例演示如何创建转换以实现阴影效果。</span><span class="sxs-lookup"><span data-stu-id="d3eb7-141">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
