---
title: 如何在样式 (WPF) 中进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
ms.openlocfilehash: 5fb18a2d927746c3437ec01d2a19327be373cae3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373954"
---
# <a name="how-to-animate-in-a-style"></a><span data-ttu-id="45337-102">如何在样式中进行动画处理</span><span class="sxs-lookup"><span data-stu-id="45337-102">How to animate in a style</span></span>

<span data-ttu-id="45337-103">此示例演示如何在样式中的属性进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="45337-103">This example shows how to animate properties within a style.</span></span> <span data-ttu-id="45337-104">时样式中进行动画处理，可以直接针对为其定义样式的框架元素。</span><span class="sxs-lookup"><span data-stu-id="45337-104">When animating within a style, only the framework element for which the style is defined can be targeted directly.</span></span> <span data-ttu-id="45337-105">若要针对 freezable 对象，您必须"dot 向下"从带样式的元素的属性。</span><span class="sxs-lookup"><span data-stu-id="45337-105">To target a freezable object, you must "dot down" from a property of the styled element.</span></span>

<span data-ttu-id="45337-106">在以下示例中，在样式中定义并应用于多个动画<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="45337-106">In the following example, several animations are defined within a style and applied to a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="45337-107">当用户将鼠标移到按钮上方时，它淡出从不透明为部分透明和后端再次、 重复。</span><span class="sxs-lookup"><span data-stu-id="45337-107">When the user moves the mouse over the button, it fades from opaque to partially translucent and back again, repeatedly.</span></span> <span data-ttu-id="45337-108">当用户移动鼠标按钮关闭时，它将成为完全不透明。</span><span class="sxs-lookup"><span data-stu-id="45337-108">When the user moves the mouse off the button, it becomes completely opaque.</span></span> <span data-ttu-id="45337-109">单击该按钮，将从橙色为白色，并再次更改其背景色。</span><span class="sxs-lookup"><span data-stu-id="45337-109">When the button is clicked, its background color changes from orange to white and back again.</span></span> <span data-ttu-id="45337-110">因为<xref:System.Windows.Media.SolidColorBrush>用于绘制按钮不能直接目标，从按钮的向下对访问<xref:System.Windows.Controls.Control.Background%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="45337-110">Because the <xref:System.Windows.Media.SolidColorBrush> used to paint the button can't be targeted directly, it is accessed by dotting down from the button's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="45337-111">示例</span><span class="sxs-lookup"><span data-stu-id="45337-111">Example</span></span>

[!code-xaml[timingbehaviors_snip#21](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]

<span data-ttu-id="45337-112">请注意，当在样式中进行动画处理，可能对不存在的目标对象。</span><span class="sxs-lookup"><span data-stu-id="45337-112">Note that when animating within a style, it's possible to target objects that don't exist.</span></span> <span data-ttu-id="45337-113">例如，假设您的方式使用<xref:System.Windows.Media.SolidColorBrush>来设置按钮的 background 属性，但在某一时刻样式重写，并且使用设置按钮的背景<xref:System.Windows.Media.LinearGradientBrush>。</span><span class="sxs-lookup"><span data-stu-id="45337-113">For example, suppose your style uses a <xref:System.Windows.Media.SolidColorBrush> to set a Button's background property, but at some point the style is overridden and the button's background is set with a <xref:System.Windows.Media.LinearGradientBrush>.</span></span>  <span data-ttu-id="45337-114">尝试进行动画处理<xref:System.Windows.Media.SolidColorBrush>不会引发异常，则动画将以静默方式失败。</span><span class="sxs-lookup"><span data-stu-id="45337-114">Trying to animate the <xref:System.Windows.Media.SolidColorBrush> won't throw an exception; the animation will simply fail silently.</span></span>

<span data-ttu-id="45337-115">有关情节提要目标语法的详细信息，请参阅[情节提要概述](storyboards-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="45337-115">For more information about storyboard targeting syntax, see the [Storyboards Overview](storyboards-overview.md).</span></span> <span data-ttu-id="45337-116">有关动画的详细信息，请参阅[动画概述](animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="45337-116">For more information about animation, see the [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="45337-117">有关样式的详细信息，请参阅[样式和模板化](../controls/styling-and-templating.md)。</span><span class="sxs-lookup"><span data-stu-id="45337-117">For more information about styles, see the [Styling and Templating](../controls/styling-and-templating.md).</span></span>
