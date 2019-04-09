---
title: 如何：在属性值更改时触发动画
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
ms.openlocfilehash: 7e3eecedf7d464eeb8e4f60f2f05fa06d2e23e09
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080704"
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a><span data-ttu-id="75dd2-102">如何：在属性值更改时触发动画</span><span class="sxs-lookup"><span data-stu-id="75dd2-102">How to: Trigger an Animation When a Property Value Changes</span></span>
<span data-ttu-id="75dd2-103">此示例演示如何使用<xref:System.Windows.Trigger>以启动<xref:System.Windows.Media.Animation.Storyboard>属性值更改时。</span><span class="sxs-lookup"><span data-stu-id="75dd2-103">This example shows how to use a <xref:System.Windows.Trigger> to start a <xref:System.Windows.Media.Animation.Storyboard> when a property value changes.</span></span> <span data-ttu-id="75dd2-104">可以使用<xref:System.Windows.Trigger>内<xref:System.Windows.Style>， <xref:System.Windows.Controls.ControlTemplate>，或<xref:System.Windows.DataTemplate>。</span><span class="sxs-lookup"><span data-stu-id="75dd2-104">You can use a <xref:System.Windows.Trigger> inside a <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, or <xref:System.Windows.DataTemplate>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75dd2-105">示例</span><span class="sxs-lookup"><span data-stu-id="75dd2-105">Example</span></span>  
 <span data-ttu-id="75dd2-106">下面的示例使用<xref:System.Windows.Trigger>进行动画处理<xref:System.Windows.UIElement.Opacity%2A>的<xref:System.Windows.Controls.Button>时其<xref:System.Windows.UIElement.IsMouseOver%2A>属性将成为`true`。</span><span class="sxs-lookup"><span data-stu-id="75dd2-106">The following example uses a <xref:System.Windows.Trigger> to animate the <xref:System.Windows.UIElement.Opacity%2A> of a <xref:System.Windows.Controls.Button> when its <xref:System.Windows.UIElement.IsMouseOver%2A> property becomes `true`.</span></span>  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 <span data-ttu-id="75dd2-107">应用属性的动画<xref:System.Windows.Trigger>对象的行为以更复杂的方式比<xref:System.Windows.EventTrigger>动画开始使用<xref:System.Windows.Media.Animation.Storyboard>方法。</span><span class="sxs-lookup"><span data-stu-id="75dd2-107">Animations applied by property <xref:System.Windows.Trigger> objects behave in a more complex fashion than <xref:System.Windows.EventTrigger> animations or animations started using <xref:System.Windows.Media.Animation.Storyboard> methods.</span></span>  <span data-ttu-id="75dd2-108">在"切换"时使用动画定义由其他<xref:System.Windows.Trigger>对象，但是在编写使用<xref:System.Windows.EventTrigger>和方法触发的动画。</span><span class="sxs-lookup"><span data-stu-id="75dd2-108">They "handoff" with animations defined by other <xref:System.Windows.Trigger> objects, but compose with <xref:System.Windows.EventTrigger> and method-triggered animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75dd2-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="75dd2-109">See also</span></span>

- <xref:System.Windows.Trigger>
- [<span data-ttu-id="75dd2-110">属性动画技术概述</span><span class="sxs-lookup"><span data-stu-id="75dd2-110">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
- [<span data-ttu-id="75dd2-111">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="75dd2-111">Storyboards Overview</span></span>](storyboards-overview.md)
