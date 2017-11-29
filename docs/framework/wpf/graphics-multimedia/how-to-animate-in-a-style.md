---
title: "如何：在样式中进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 10cd243c633e7a7e458d2026fc5e3d91d2996427
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-animate-in-a-style"></a><span data-ttu-id="bd633-102">如何：在样式中进行动画处理</span><span class="sxs-lookup"><span data-stu-id="bd633-102">How to: Animate in a Style</span></span>
<span data-ttu-id="bd633-103">此示例演示如何在样式中的属性进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="bd633-103">This example shows how to animate properties within a style.</span></span> <span data-ttu-id="bd633-104">在样式中进行动画处理时, 可以直接针对为其定义样式的框架元素。</span><span class="sxs-lookup"><span data-stu-id="bd633-104">When animating within a style, only the framework element for which the style is defined can be targeted directly.</span></span> <span data-ttu-id="bd633-105">若要针对可冻结对象，你必须"dot 向下"从应用了样式元素的属性。</span><span class="sxs-lookup"><span data-stu-id="bd633-105">To target a freezable object, you must "dot down" from a property of the styled element.</span></span>  
  
 <span data-ttu-id="bd633-106">在下面的示例中，在样式中定义并应用于多个动画<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="bd633-106">In the following example, several animations are defined within a style and applied to a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="bd633-107">当用户将鼠标移到按钮上方时，它淡出从不透明为部分半透明和后反复。</span><span class="sxs-lookup"><span data-stu-id="bd633-107">When the user moves the mouse over the button, it fades from opaque to partially translucent and back again, repeatedly.</span></span> <span data-ttu-id="bd633-108">当用户移动鼠标按钮关闭时，它将成为完全不透明。</span><span class="sxs-lookup"><span data-stu-id="bd633-108">When the user moves the mouse off the button, it becomes completely opaque.</span></span> <span data-ttu-id="bd633-109">当单击按钮时，它的背景色更改从橙色改为白色，然后再返回。</span><span class="sxs-lookup"><span data-stu-id="bd633-109">When the button is clicked, its background color changes from orange to white and back again.</span></span> <span data-ttu-id="bd633-110">因为<xref:System.Windows.Media.SolidColorBrush>用于绘制按钮不能直接目标，它可通过向下按钮的从散布<xref:System.Windows.Controls.Control.Background%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="bd633-110">Because the <xref:System.Windows.Media.SolidColorBrush> used to paint the button can't be targeted directly, it is accessed by dotting down from the button's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd633-111">示例</span><span class="sxs-lookup"><span data-stu-id="bd633-111">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]  
  
 <span data-ttu-id="bd633-112">请注意，在样式中进行动画处理时, 可能不存在的目标对象。</span><span class="sxs-lookup"><span data-stu-id="bd633-112">Note that when animating within a style, it's possible to target objects that don't exist.</span></span> <span data-ttu-id="bd633-113">例如，假设您的方式使用<xref:System.Windows.Media.SolidColorBrush>设置按钮的背景属性，但在某些点，该样式被重写且按钮的背景设置用<xref:System.Windows.Media.LinearGradientBrush>。</span><span class="sxs-lookup"><span data-stu-id="bd633-113">For example, suppose your style uses a <xref:System.Windows.Media.SolidColorBrush> to set a Button's background property, but at some point the style is overridden and the button's background is set with a <xref:System.Windows.Media.LinearGradientBrush>.</span></span>  <span data-ttu-id="bd633-114">尝试进行动画处理<xref:System.Windows.Media.SolidColorBrush>不会引发异常; 动画将只需以静默方式失败。</span><span class="sxs-lookup"><span data-stu-id="bd633-114">Trying to animate the <xref:System.Windows.Media.SolidColorBrush> won't throw an exception; the animation will simply fail silently.</span></span>  
  
 <span data-ttu-id="bd633-115">有关演示图板目标设定语法的详细信息，请参阅[情节提要概述](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="bd633-115">Fore more information about storyboard targeting syntax, see the [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span> <span data-ttu-id="bd633-116">有关动画的详细信息，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="bd633-116">For more information about animation, see the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span> <span data-ttu-id="bd633-117">有关样式的详细信息，请参阅[样式和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)。</span><span class="sxs-lookup"><span data-stu-id="bd633-117">For more information about styles, see the [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span>
