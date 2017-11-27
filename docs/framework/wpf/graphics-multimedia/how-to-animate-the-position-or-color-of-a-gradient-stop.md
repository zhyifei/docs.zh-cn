---
title: "如何：对渐变停止点的位置或颜色进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 968d285d8a3345da9810f0ba4797bf8b2e33d36e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a><span data-ttu-id="fa395-102">如何：对渐变停止点的位置或颜色进行动画处理</span><span class="sxs-lookup"><span data-stu-id="fa395-102">How to: Animate the Position or Color of a Gradient Stop</span></span>
<span data-ttu-id="fa395-103">此示例演示如何进行动画处理<xref:System.Windows.Media.GradientStop.Color%2A>和<xref:System.Windows.Media.GradientStop.Offset%2A>的<xref:System.Windows.Media.GradientStop>对象。</span><span class="sxs-lookup"><span data-stu-id="fa395-103">This example shows how to animate the <xref:System.Windows.Media.GradientStop.Color%2A> and <xref:System.Windows.Media.GradientStop.Offset%2A> of <xref:System.Windows.Media.GradientStop> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa395-104">示例</span><span class="sxs-lookup"><span data-stu-id="fa395-104">Example</span></span>  
 <span data-ttu-id="fa395-105">下面的示例进行动画处理内的三个梯度停止点<xref:System.Windows.Media.LinearGradientBrush>。</span><span class="sxs-lookup"><span data-stu-id="fa395-105">The following example animates three gradient stops inside a <xref:System.Windows.Media.LinearGradientBrush>.</span></span> <span data-ttu-id="fa395-106">该示例使用三个动画，其中每个进行动画处理不同的渐变停止点：</span><span class="sxs-lookup"><span data-stu-id="fa395-106">The example uses three animations, each of which animates a different gradient stop:</span></span>  
  
-   <span data-ttu-id="fa395-107">第一个动画， <xref:System.Windows.Media.Animation.DoubleAnimation>，进行动画处理对第一个渐变停止点的<xref:System.Windows.Media.GradientStop.Offset%2A>从 0.0 到 1.0，然后再为 0.0。</span><span class="sxs-lookup"><span data-stu-id="fa395-107">The first animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, animates the first gradient stop's <xref:System.Windows.Media.GradientStop.Offset%2A> from 0.0 to 1.0 and then back to 0.0.</span></span> <span data-ttu-id="fa395-108">因此，第一个中，渐变将在从左边算矩形的右侧颜色，然后再返回到左侧。</span><span class="sxs-lookup"><span data-stu-id="fa395-108">As a result, the first color in the gradient shifts from the left side to the right side of the rectangle and then back to the left side.</span></span>  
  
-   <span data-ttu-id="fa395-109">第二个动画， <xref:System.Windows.Media.Animation.ColorAnimation>，进行动画处理对第二个渐变停止点的<xref:System.Windows.Media.GradientStop.Color%2A>从<xref:System.Windows.Media.Colors.Purple%2A>到<xref:System.Windows.Media.Colors.Yellow%2A>和再转回<xref:System.Windows.Media.Colors.Purple%2A>。</span><span class="sxs-lookup"><span data-stu-id="fa395-109">The second animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, animates the second gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> from <xref:System.Windows.Media.Colors.Purple%2A> to <xref:System.Windows.Media.Colors.Yellow%2A> and then back to <xref:System.Windows.Media.Colors.Purple%2A>.</span></span> <span data-ttu-id="fa395-110">因此，为黄色，并返回到紫色，从紫色将更改渐变中的中间颜色。</span><span class="sxs-lookup"><span data-stu-id="fa395-110">As a result, the middle color in the gradient changes from purple to yellow and back to purple.</span></span>  
  
-   <span data-ttu-id="fa395-111">第三个动画，另一个<xref:System.Windows.Media.Animation.ColorAnimation>，进行动画处理的第三个渐变停止点的不透明度<xref:System.Windows.Media.GradientStop.Color%2A>乘以-1，然后再设置。</span><span class="sxs-lookup"><span data-stu-id="fa395-111">The third animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, animates the opacity of the third gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> by -1 and then back.</span></span> <span data-ttu-id="fa395-112">因此，渐变中的第三个颜色淡出，然后再次变得不透明。</span><span class="sxs-lookup"><span data-stu-id="fa395-112">As a result, the third color in the gradient fades away and then becomes opaque again.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 <span data-ttu-id="fa395-113">虽然此示例使用<xref:System.Windows.Media.LinearGradientBrush>，过程是相同进行动画处理<xref:System.Windows.Media.GradientStop>对象内<xref:System.Windows.Media.RadialGradientBrush>。</span><span class="sxs-lookup"><span data-stu-id="fa395-113">Although this example uses a <xref:System.Windows.Media.LinearGradientBrush>, the process is the same for animating <xref:System.Windows.Media.GradientStop> objects inside a <xref:System.Windows.Media.RadialGradientBrush>.</span></span>  
  
 <span data-ttu-id="fa395-114">有关其他示例，请参阅[画笔示例](http://go.microsoft.com/fwlink/?LinkID=159973)。</span><span class="sxs-lookup"><span data-stu-id="fa395-114">For additional examples, see the [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa395-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa395-115">See Also</span></span>  
 <xref:System.Windows.Media.GradientStop>  
 [<span data-ttu-id="fa395-116">动画概述</span><span class="sxs-lookup"><span data-stu-id="fa395-116">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="fa395-117">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="fa395-117">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
