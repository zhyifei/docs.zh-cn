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
ms.openlocfilehash: 2457bdb794d81e7c482f735cad4ade34564328e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559313"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a><span data-ttu-id="ac389-102">如何：对 SolidColorBrush 的颜色或不透明度进行动画处理</span><span class="sxs-lookup"><span data-stu-id="ac389-102">How to: Animate the Color or Opacity of a SolidColorBrush</span></span>
<span data-ttu-id="ac389-103">此示例演示如何进行动画处理<xref:System.Windows.Media.SolidColorBrush.Color%2A>和<xref:System.Windows.Media.Brush.Opacity%2A>的<xref:System.Windows.Media.SolidColorBrush>。</span><span class="sxs-lookup"><span data-stu-id="ac389-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac389-104">示例</span><span class="sxs-lookup"><span data-stu-id="ac389-104">Example</span></span>  
 <span data-ttu-id="ac389-105">下面的示例使用三个动画要进行动画处理<xref:System.Windows.Media.SolidColorBrush.Color%2A>和<xref:System.Windows.Media.Brush.Opacity%2A>的<xref:System.Windows.Media.SolidColorBrush>。</span><span class="sxs-lookup"><span data-stu-id="ac389-105">The following example uses three animations to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
-   <span data-ttu-id="ac389-106">第一个动画， <xref:System.Windows.Media.Animation.ColorAnimation>，更改到画笔的颜色<xref:System.Windows.Media.Colors.Gray%2A>当鼠标进入矩形。</span><span class="sxs-lookup"><span data-stu-id="ac389-106">The first animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Gray%2A> when the mouse enters the rectangle.</span></span>  
  
-   <span data-ttu-id="ac389-107">下一步的动画，另一个<xref:System.Windows.Media.Animation.ColorAnimation>，更改到画笔的颜色<xref:System.Windows.Media.Colors.Orange%2A>当鼠标离开矩形。</span><span class="sxs-lookup"><span data-stu-id="ac389-107">The next animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Orange%2A> when the mouse leaves the rectangle.</span></span>  
  
-   <span data-ttu-id="ac389-108">最后一个动画， <xref:System.Windows.Media.Animation.DoubleAnimation>，当按下鼠标左键时，更改画笔的不透明度为 0.0。</span><span class="sxs-lookup"><span data-stu-id="ac389-108">The final animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, changes the brush's opacity to 0.0 when the left mouse button is pressed.</span></span>  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 <span data-ttu-id="ac389-109">有关更完整示例中，其中说明了如何进行动画处理不同类型的画笔，请参阅[画笔示例](http://go.microsoft.com/fwlink/?LinkID=159973)。</span><span class="sxs-lookup"><span data-stu-id="ac389-109">For a more complete sample, which shows how to animate different types of brushes, see the [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="ac389-110">有关动画的详细信息，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="ac389-110">For more information about animation, see the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span>  
  
 <span data-ttu-id="ac389-111">与其他动画示例保持一致，对于此示例的代码版本使用<xref:System.Windows.Media.Animation.Storyboard>要应用它们的动画对象。</span><span class="sxs-lookup"><span data-stu-id="ac389-111">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply their animations.</span></span> <span data-ttu-id="ac389-112">但是，当应用单个动画在代码中的，这是使用简单得多<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法而不是使用<xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="ac389-112">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="ac389-113">有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)。</span><span class="sxs-lookup"><span data-stu-id="ac389-113">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac389-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac389-114">See Also</span></span>  
 [<span data-ttu-id="ac389-115">动画概述</span><span class="sxs-lookup"><span data-stu-id="ac389-115">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="ac389-116">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="ac389-116">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [<span data-ttu-id="ac389-117">画笔示例</span><span class="sxs-lookup"><span data-stu-id="ac389-117">Brushes Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159973)
