---
title: "如何：使用演示图板对属性进行动画处理"
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
- animation [WPF], Storyboards
- Storyboards [WPF], animation
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2129ea06e8c92b3912d2abdd3d1a63e651ac59e1
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a><span data-ttu-id="e0060-102">如何：使用演示图板对属性进行动画处理</span><span class="sxs-lookup"><span data-stu-id="e0060-102">How to: Animate a Property by Using a Storyboard</span></span>
<span data-ttu-id="e0060-103">此示例演示如何使用<xref:System.Windows.Media.Animation.Storyboard>属性进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="e0060-103">This example shows how to use a <xref:System.Windows.Media.Animation.Storyboard> to animate properties.</span></span> <span data-ttu-id="e0060-104">若要使用属性进行动画处理<xref:System.Windows.Media.Animation.Storyboard>，创建你想要进行动画处理，并且还创建每个属性动画<xref:System.Windows.Media.Animation.Storyboard>以包含动画。</span><span class="sxs-lookup"><span data-stu-id="e0060-104">To animate a property by using a <xref:System.Windows.Media.Animation.Storyboard>, create an animation for each property that you want to animate and also create a <xref:System.Windows.Media.Animation.Storyboard> to contain the animations.</span></span>  
  
 <span data-ttu-id="e0060-105">属性类型确定要使用的动画类型。</span><span class="sxs-lookup"><span data-stu-id="e0060-105">The type of property determines the type of animation to use.</span></span> <span data-ttu-id="e0060-106">例如，若要进行动画处理的属性<xref:System.Double>值，请使用<xref:System.Windows.Media.Animation.DoubleAnimation>。</span><span class="sxs-lookup"><span data-stu-id="e0060-106">For example, to animate a property that takes <xref:System.Double> values, use a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span> <span data-ttu-id="e0060-107"><xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>和<xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A>附加的属性指定的对象和向其应用动画属性。</span><span class="sxs-lookup"><span data-stu-id="e0060-107">The <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> and <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> attached properties specify the object and property to which the animation is applied.</span></span>  
  
 <span data-ttu-id="e0060-108">若要在中启动情节提要[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，使用<xref:System.Windows.Media.Animation.BeginStoryboard>操作和<xref:System.Windows.EventTrigger>。</span><span class="sxs-lookup"><span data-stu-id="e0060-108">To start a storyboard in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], use a <xref:System.Windows.Media.Animation.BeginStoryboard> action and an <xref:System.Windows.EventTrigger>.</span></span> <span data-ttu-id="e0060-109"><xref:System.Windows.EventTrigger>开始<xref:System.Windows.Media.Animation.BeginStoryboard>操作事件时指定其<xref:System.Windows.EventTrigger.RoutedEvent%2A>属性出现。</span><span class="sxs-lookup"><span data-stu-id="e0060-109">The <xref:System.Windows.EventTrigger> begins the <xref:System.Windows.Media.Animation.BeginStoryboard> action when the event that is specified by its <xref:System.Windows.EventTrigger.RoutedEvent%2A> property occurs.</span></span> <span data-ttu-id="e0060-110"><xref:System.Windows.Media.Animation.BeginStoryboard>操作将启动<xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="e0060-110">The <xref:System.Windows.Media.Animation.BeginStoryboard> action starts the <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
 <span data-ttu-id="e0060-111">下面的示例使用<xref:System.Windows.Media.Animation.Storyboard>对象要进行动画处理两个<xref:System.Windows.Controls.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="e0060-111">The following example uses <xref:System.Windows.Media.Animation.Storyboard> objects to animate two <xref:System.Windows.Controls.Button> controls.</span></span> <span data-ttu-id="e0060-112">若要创建第一个按钮的大小，更改其<xref:System.Windows.FrameworkElement.Width%2A>进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="e0060-112">To make the first button change in size, its <xref:System.Windows.FrameworkElement.Width%2A> is animated.</span></span> <span data-ttu-id="e0060-113">若要使更改颜色，第二个按钮<xref:System.Windows.Media.SolidColorBrush.Color%2A>属性<xref:System.Windows.Media.SolidColorBrush>用于设置<xref:System.Windows.Controls.Control.Background%2A>进行动画处理的按钮。</span><span class="sxs-lookup"><span data-stu-id="e0060-113">To make the second button change color, the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of the <xref:System.Windows.Media.SolidColorBrush> is used to set the <xref:System.Windows.Controls.Control.Background%2A> of the button that is animated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0060-114">示例</span><span class="sxs-lookup"><span data-stu-id="e0060-114">Example</span></span>  
 [!code-xaml[AnimatePropertyStoryboards#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
>  <span data-ttu-id="e0060-115">尽管动画可以面向同时<xref:System.Windows.FrameworkElement>对象，如<xref:System.Windows.Controls.Control>或<xref:System.Windows.Controls.Panel>，和一个<xref:System.Windows.Freezable>对象，如<xref:System.Windows.Media.Brush>或<xref:System.Windows.Media.Transform>，只有 framework 元素具有<xref:System.Windows.FrameworkElement.Name%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="e0060-115">Although animations can target both a <xref:System.Windows.FrameworkElement> object, such as a <xref:System.Windows.Controls.Control> or <xref:System.Windows.Controls.Panel>, and a <xref:System.Windows.Freezable> object, such as a <xref:System.Windows.Media.Brush> or <xref:System.Windows.Media.Transform>, only framework elements have a <xref:System.Windows.FrameworkElement.Name%2A> property.</span></span> <span data-ttu-id="e0060-116">若要向 Freezable 分配名称以便动画可以针对它，请使用 [x:Name 指令](../../../../docs/framework/xaml-services/x-name-directive.md)，如前面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="e0060-116">To assign a name to a freezable so that it can be targeted by an animation, use the [x:Name Directive](../../../../docs/framework/xaml-services/x-name-directive.md), as the previous example shows.</span></span>  
  
 <span data-ttu-id="e0060-117">如果你使用代码，则必须创建<xref:System.Windows.NameScope>为<xref:System.Windows.FrameworkElement>并注册要使用的进行动画处理的对象的名称<xref:System.Windows.FrameworkElement>。</span><span class="sxs-lookup"><span data-stu-id="e0060-117">If you use code, you must create a <xref:System.Windows.NameScope> for a <xref:System.Windows.FrameworkElement> and register the names of the objects to animate with that <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="e0060-118">若要在代码中启动动画，使用<xref:System.Windows.Media.Animation.BeginStoryboard>操作具有<xref:System.Windows.EventTrigger>。</span><span class="sxs-lookup"><span data-stu-id="e0060-118">To start the animations in code, use a <xref:System.Windows.Media.Animation.BeginStoryboard> action with an <xref:System.Windows.EventTrigger>.</span></span> <span data-ttu-id="e0060-119">或者，你可以使用事件处理程序和<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>方法<xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="e0060-119">Optionally, you can use an event handler and the <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method of <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="e0060-120">下面的示例显示如何使用 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="e0060-120">The following example shows how to use the <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method.</span></span>  
  
 [!code-csharp[AnimatePropertyStoryboards#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 <span data-ttu-id="e0060-121">有关动画和情节提要的详细信息，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e0060-121">For more information about animation and storyboards, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span>  
  
 <span data-ttu-id="e0060-122">如果你使用代码，你并不局限于使用<xref:System.Windows.Media.Animation.Storyboard>属性进行动画处理的对象。</span><span class="sxs-lookup"><span data-stu-id="e0060-122">If you use code, you are not limited to using <xref:System.Windows.Media.Animation.Storyboard> objects in order to animate properties.</span></span> <span data-ttu-id="e0060-123">有关详细信息和示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)和[使用 AnimationClock 对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md)。</span><span class="sxs-lookup"><span data-stu-id="e0060-123">For more information and examples, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md) and [Animate a Property by Using an AnimationClock](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md).</span></span>
