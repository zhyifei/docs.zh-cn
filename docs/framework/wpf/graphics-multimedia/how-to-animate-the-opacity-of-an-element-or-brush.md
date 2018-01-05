---
title: "如何：对元素或画笔的不透明度进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c3b750e6ee21c8347d3896ec290f0ff564cc0a2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a><span data-ttu-id="66dee-102">如何：对元素或画笔的不透明度进行动画处理</span><span class="sxs-lookup"><span data-stu-id="66dee-102">How to: Animate the Opacity of an Element or Brush</span></span>
<span data-ttu-id="66dee-103">若要使淡入淡出的视图内外的框架元素，可以动态显示其<xref:System.Windows.UIElement.Opacity%2A>属性也可以进行动画处理<xref:System.Windows.Media.Brush.Opacity%2A>属性<xref:System.Windows.Media.Brush>（或画笔） 用来绘制它。</span><span class="sxs-lookup"><span data-stu-id="66dee-103">To make a framework element fade in and out of view, you can animate its <xref:System.Windows.UIElement.Opacity%2A> property or you can animate the <xref:System.Windows.Media.Brush.Opacity%2A> property of the <xref:System.Windows.Media.Brush> (or brushes) used to paint it.</span></span> <span data-ttu-id="66dee-104">对进行动画处理的元素的不透明度能并其子淡入和移出视图中，但对进行动画处理的画笔用于绘制元素使您可以更选择性有关元素的哪些部分淡。</span><span class="sxs-lookup"><span data-stu-id="66dee-104">Animating the element's opacity makes it and its children fade in and out of view, but animating the brush used to paint the element enables you to be more selective about which portion of the element fades.</span></span> <span data-ttu-id="66dee-105">例如，您可以创建动画用于绘制按钮的背景的画笔的不透明度。</span><span class="sxs-lookup"><span data-stu-id="66dee-105">For example, you could animate the opacity of a brush used to paint a button's background.</span></span> <span data-ttu-id="66dee-106">这将导致该按钮的背景以淡入淡出视图，同时使其文本完全不透明。</span><span class="sxs-lookup"><span data-stu-id="66dee-106">This would cause the button's background to fade in and out of view, while leaving its text fully opaque.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66dee-107">对进行动画处理<xref:System.Windows.Media.Brush.Opacity%2A>的<xref:System.Windows.Media.Brush>基础上进行动画处理提供了性能优势<xref:System.Windows.UIElement.Opacity%2A>元素的属性。</span><span class="sxs-lookup"><span data-stu-id="66dee-107">Animating the <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.Brush> provides performance benefits over animating the <xref:System.Windows.UIElement.Opacity%2A> property of an element.</span></span>  
  
 <span data-ttu-id="66dee-108">在下面的示例中，两个按钮进行动画处理，以便它们淡入淡出视野。</span><span class="sxs-lookup"><span data-stu-id="66dee-108">In the following example, two buttons are animated so that they fade in and out of view.</span></span> <span data-ttu-id="66dee-109">第一个的不透明度<xref:System.Windows.Controls.Button>以动画形式从`1.0`到`0.0`通过<xref:System.Windows.Media.Animation.Timeline.Duration%2A>5 秒。</span><span class="sxs-lookup"><span data-stu-id="66dee-109">The Opacity of the first <xref:System.Windows.Controls.Button> is animated from `1.0` to `0.0` over a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> of five seconds.</span></span> <span data-ttu-id="66dee-110">第二个按钮还进行动画处理，但 SolidColorBrush 的不透明度用于绘制其<xref:System.Windows.Controls.Control.Background%2A>动画处理的而不是整个按钮的不透明度。</span><span class="sxs-lookup"><span data-stu-id="66dee-110">The second button is also animated, but the Opacity of the SolidColorBrush used to paint its <xref:System.Windows.Controls.Control.Background%2A> is animated rather than the opacity of the entire button.</span></span> <span data-ttu-id="66dee-111">当运行示例时，第一个按钮完全淡入淡出视图中，仅第二个按钮的背景淡入淡出视图时。</span><span class="sxs-lookup"><span data-stu-id="66dee-111">When the example is run, the first button completely fades in and out of view, while only the background of the second button fades in and out of view.</span></span> <span data-ttu-id="66dee-112">其文本和边框保持完全不透明。</span><span class="sxs-lookup"><span data-stu-id="66dee-112">Its text and border remain fully opaque.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66dee-113">示例</span><span class="sxs-lookup"><span data-stu-id="66dee-113">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 <span data-ttu-id="66dee-114">此示例中，代码已被省略。</span><span class="sxs-lookup"><span data-stu-id="66dee-114">Code has been omitted from this example.</span></span> <span data-ttu-id="66dee-115">完整示例还演示如何进行动画处理的不透明度<xref:System.Windows.Media.Color>内<xref:System.Windows.Media.LinearGradientBrush>。</span><span class="sxs-lookup"><span data-stu-id="66dee-115">The full sample also shows how to animate the opacity of a <xref:System.Windows.Media.Color> within a <xref:System.Windows.Media.LinearGradientBrush>.</span></span>  <span data-ttu-id="66dee-116">有关完整示例，请参阅[进行动画处理的元素示例不透明度](http://go.microsoft.com/fwlink/?LinkID=159968)。</span><span class="sxs-lookup"><span data-stu-id="66dee-116">For the full sample, see the [Animating the Opacity of an Element Sample](http://go.microsoft.com/fwlink/?LinkID=159968).</span></span>
