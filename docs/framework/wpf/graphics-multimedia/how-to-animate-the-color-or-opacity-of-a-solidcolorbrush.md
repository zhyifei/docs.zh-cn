---
title: 如何：对 SolidColorBrush 的颜色或不透明度进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 194f01d3d5aa4c2b5a08a6c3fdb3dc195b0e9e3e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43392222"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a><span data-ttu-id="cf1d2-102">如何：对 SolidColorBrush 的颜色或不透明度进行动画处理</span><span class="sxs-lookup"><span data-stu-id="cf1d2-102">How to: Animate the Color or Opacity of a SolidColorBrush</span></span>
<span data-ttu-id="cf1d2-103">此示例演示如何进行动画处理<xref:System.Windows.Media.SolidColorBrush.Color%2A>并<xref:System.Windows.Media.Brush.Opacity%2A>的<xref:System.Windows.Media.SolidColorBrush>。</span><span class="sxs-lookup"><span data-stu-id="cf1d2-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf1d2-104">示例</span><span class="sxs-lookup"><span data-stu-id="cf1d2-104">Example</span></span>  
 <span data-ttu-id="cf1d2-105">下面的示例使用三个动画进行动画处理<xref:System.Windows.Media.SolidColorBrush.Color%2A>并<xref:System.Windows.Media.Brush.Opacity%2A>的<xref:System.Windows.Media.SolidColorBrush>。</span><span class="sxs-lookup"><span data-stu-id="cf1d2-105">The following example uses three animations to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
-   <span data-ttu-id="cf1d2-106">第一个动画<xref:System.Windows.Media.Animation.ColorAnimation>，会将画笔的颜色改<xref:System.Windows.Media.Colors.Gray%2A>当鼠标进入矩形。</span><span class="sxs-lookup"><span data-stu-id="cf1d2-106">The first animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Gray%2A> when the mouse enters the rectangle.</span></span>  
  
-   <span data-ttu-id="cf1d2-107">下一步的动画，另一个<xref:System.Windows.Media.Animation.ColorAnimation>，会将画笔的颜色改<xref:System.Windows.Media.Colors.Orange%2A>当鼠标离开矩形。</span><span class="sxs-lookup"><span data-stu-id="cf1d2-107">The next animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Orange%2A> when the mouse leaves the rectangle.</span></span>  
  
-   <span data-ttu-id="cf1d2-108">最后一个动画， <xref:System.Windows.Media.Animation.DoubleAnimation>，当按下鼠标左键时更改画笔的不透明度为 0.0。</span><span class="sxs-lookup"><span data-stu-id="cf1d2-108">The final animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, changes the brush's opacity to 0.0 when the left mouse button is pressed.</span></span>  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 <span data-ttu-id="cf1d2-109">有关更完整示例，其中说明了如何对不同类型的画笔进行动画处理，请参阅[画笔示例](https://go.microsoft.com/fwlink/?LinkID=159973)。</span><span class="sxs-lookup"><span data-stu-id="cf1d2-109">For a more complete sample, which shows how to animate different types of brushes, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="cf1d2-110">有关动画的详细信息，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="cf1d2-110">For more information about animation, see the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span>  
  
 <span data-ttu-id="cf1d2-111">与其他动画示例保持一致，对于此示例中的代码版本使用<xref:System.Windows.Media.Animation.Storyboard>对象来应用它们的动画。</span><span class="sxs-lookup"><span data-stu-id="cf1d2-111">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply their animations.</span></span> <span data-ttu-id="cf1d2-112">但是，当应用单个动画在代码中的，它是使用更加简便<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法而不是使用<xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="cf1d2-112">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="cf1d2-113">有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)。</span><span class="sxs-lookup"><span data-stu-id="cf1d2-113">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf1d2-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf1d2-114">See Also</span></span>  
 [<span data-ttu-id="cf1d2-115">动画概述</span><span class="sxs-lookup"><span data-stu-id="cf1d2-115">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="cf1d2-116">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="cf1d2-116">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [<span data-ttu-id="cf1d2-117">画笔示例</span><span class="sxs-lookup"><span data-stu-id="cf1d2-117">Brushes Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159973)
