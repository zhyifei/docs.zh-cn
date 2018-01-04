---
title: "如何：向文本应用动画"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d44565907904509a1b8f670453db5d7aa4e2583
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-animations-to-text"></a><span data-ttu-id="54d04-102">如何：向文本应用动画</span><span class="sxs-lookup"><span data-stu-id="54d04-102">How to: Apply Animations to Text</span></span>
<span data-ttu-id="54d04-103">动画可以更改应用程序中文本的显示和外观。</span><span class="sxs-lookup"><span data-stu-id="54d04-103">Animations can alter the display and appearance of text in your application.</span></span> <span data-ttu-id="54d04-104">下面的示例使用不同类型的动画来影响中的文本显示<xref:System.Windows.Controls.TextBlock>控件。</span><span class="sxs-lookup"><span data-stu-id="54d04-104">The following examples use different types of animations to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54d04-105">示例</span><span class="sxs-lookup"><span data-stu-id="54d04-105">Example</span></span>  
 <span data-ttu-id="54d04-106">下面的示例使用<xref:System.Windows.Media.Animation.DoubleAnimation>要进行动画处理的文本块宽度。</span><span class="sxs-lookup"><span data-stu-id="54d04-106">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the width of the text block.</span></span> <span data-ttu-id="54d04-107">宽度值从文本块的宽度更改为 0，持续时间为 10 秒，然后再改回其宽度值并继续。</span><span class="sxs-lookup"><span data-stu-id="54d04-107">The width value changes from the width of the text block to 0 over a duration of 10 seconds, and then reverses the width values and continues.</span></span> <span data-ttu-id="54d04-108">这种动画会创建一个擦除效果。</span><span class="sxs-lookup"><span data-stu-id="54d04-108">This type of animation creates a wipe effect.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 <span data-ttu-id="54d04-109">下面的示例使用<xref:System.Windows.Media.Animation.DoubleAnimation>要进行动画处理的文本块的不透明度。</span><span class="sxs-lookup"><span data-stu-id="54d04-109">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the opacity of the text block.</span></span> <span data-ttu-id="54d04-110">不透明度值从 1.0 更改为 0，持续时间为 5 秒，然后再改回其不透明度值并继续。</span><span class="sxs-lookup"><span data-stu-id="54d04-110">The opacity value changes from 1.0 to 0 over a duration of 5 seconds, and then reverses the opacity values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 <span data-ttu-id="54d04-111">下图显示的效果<xref:System.Windows.Controls.TextBlock>控件从其不透明度`1.00`到`0.00`定义的 5 秒间隔期间<xref:System.Windows.Media.Animation.Timeline.Duration%2A>。</span><span class="sxs-lookup"><span data-stu-id="54d04-111">The following diagram shows the effect of the <xref:System.Windows.Controls.TextBlock> control changing its opacity from `1.00` to `0.00` during the 5-second interval defined by the <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.</span></span>  
  
 <span data-ttu-id="54d04-112">![文本不透明度从 1.00 改为 0.00](../../../../docs/framework/wpf/advanced/media/fadedtext01.png "FadedText01")</span><span class="sxs-lookup"><span data-stu-id="54d04-112">![Text changing opacity from 1.00 to 0.00](../../../../docs/framework/wpf/advanced/media/fadedtext01.png "FadedText01")</span></span>  
<span data-ttu-id="54d04-113">文本不透明度从 1.00 改为 0.00</span><span class="sxs-lookup"><span data-stu-id="54d04-113">Text Opacity changing from 1.00 to 0.00</span></span>  
  
 <span data-ttu-id="54d04-114">下面的示例使用<xref:System.Windows.Media.Animation.ColorAnimation>要进行动画处理的文本块的前景色。</span><span class="sxs-lookup"><span data-stu-id="54d04-114">The following example uses a <xref:System.Windows.Media.Animation.ColorAnimation> to animate the foreground color of the text block.</span></span> <span data-ttu-id="54d04-115">前景色值从一种颜色更改为另一种颜色，持续时间为 5 秒，然后返回到原来的颜色值并继续。</span><span class="sxs-lookup"><span data-stu-id="54d04-115">The foreground color value changes from one color to a second color over a duration of 5 seconds, and then reverses the color values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 <span data-ttu-id="54d04-116">下面的示例使用<xref:System.Windows.Media.Animation.DoubleAnimation>旋转文本块。</span><span class="sxs-lookup"><span data-stu-id="54d04-116">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to rotate the text block.</span></span> <span data-ttu-id="54d04-117">文本块旋转一圈，持续时间为 20 秒，然后继续重复该旋转。</span><span class="sxs-lookup"><span data-stu-id="54d04-117">The text block performs a full rotation over a duration of 20 seconds, and then continues to repeat the rotation.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a><span data-ttu-id="54d04-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="54d04-118">See Also</span></span>  
 [<span data-ttu-id="54d04-119">动画概述</span><span class="sxs-lookup"><span data-stu-id="54d04-119">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
