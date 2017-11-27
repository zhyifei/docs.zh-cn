---
title: "如何：在属性值更改时触发动画"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4d722be0f0367f7e6e98ef1c8451ce58ee28fedd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a><span data-ttu-id="79ed3-102">如何：在属性值更改时触发动画</span><span class="sxs-lookup"><span data-stu-id="79ed3-102">How to: Trigger an Animation When a Property Value Changes</span></span>
<span data-ttu-id="79ed3-103">此示例演示如何使用<xref:System.Windows.Trigger>启动<xref:System.Windows.Media.Animation.Storyboard>属性值更改时。</span><span class="sxs-lookup"><span data-stu-id="79ed3-103">This example shows how to use a <xref:System.Windows.Trigger> to start a <xref:System.Windows.Media.Animation.Storyboard> when a property value changes.</span></span> <span data-ttu-id="79ed3-104">你可以使用<xref:System.Windows.Trigger>内<xref:System.Windows.Style>， <xref:System.Windows.Controls.ControlTemplate>，或<xref:System.Windows.DataTemplate>。</span><span class="sxs-lookup"><span data-stu-id="79ed3-104">You can use a <xref:System.Windows.Trigger> inside a <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, or <xref:System.Windows.DataTemplate>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79ed3-105">示例</span><span class="sxs-lookup"><span data-stu-id="79ed3-105">Example</span></span>  
 <span data-ttu-id="79ed3-106">下面的示例使用<xref:System.Windows.Trigger>要进行动画处理<xref:System.Windows.UIElement.Opacity%2A>的<xref:System.Windows.Controls.Button>时其<xref:System.Windows.UIElement.IsMouseOver%2A>属性变为`true`。</span><span class="sxs-lookup"><span data-stu-id="79ed3-106">The following example uses a <xref:System.Windows.Trigger> to animate the <xref:System.Windows.UIElement.Opacity%2A> of a <xref:System.Windows.Controls.Button> when its <xref:System.Windows.UIElement.IsMouseOver%2A> property becomes `true`.</span></span>  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 <span data-ttu-id="79ed3-107">属性应用动画<xref:System.Windows.Trigger>的对象行为比更复杂的方式<xref:System.Windows.EventTrigger>动画开始使用<xref:System.Windows.Media.Animation.Storyboard>方法。</span><span class="sxs-lookup"><span data-stu-id="79ed3-107">Animations applied by property <xref:System.Windows.Trigger> objects behave in a more complex fashion than <xref:System.Windows.EventTrigger> animations or animations started using <xref:System.Windows.Media.Animation.Storyboard> methods.</span></span>  <span data-ttu-id="79ed3-108">它们"提交"时使用动画定义由其他<xref:System.Windows.Trigger>对象，但 compose 与<xref:System.Windows.EventTrigger>和方法，触发动画。</span><span class="sxs-lookup"><span data-stu-id="79ed3-108">They "handoff" with animations defined by other <xref:System.Windows.Trigger> objects, but compose with <xref:System.Windows.EventTrigger> and method-triggered animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79ed3-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79ed3-109">See Also</span></span>  
 <xref:System.Windows.Trigger>  
 [<span data-ttu-id="79ed3-110">属性动画技术概述</span><span class="sxs-lookup"><span data-stu-id="79ed3-110">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [<span data-ttu-id="79ed3-111">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="79ed3-111">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
