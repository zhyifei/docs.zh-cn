---
title: "如何：在事件发生时向元素应用变换"
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
- graphics [WPF], transformations as event responses
- properties [WPF], LayoutTransform
- transformations as event responses [WPF]
- properties [WPF], RenderTransform
- LayoutTransform property [WPF]
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e58e49ecc852b87d03d4112208354e608248984
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a><span data-ttu-id="c24a1-102">如何：在事件发生时向元素应用变换</span><span class="sxs-lookup"><span data-stu-id="c24a1-102">How to: Apply a Transform to an Element When an Event Occurs</span></span>
<span data-ttu-id="c24a1-103">此示例演示如何将应用<xref:System.Windows.Media.ScaleTransform>事件发生时。</span><span class="sxs-lookup"><span data-stu-id="c24a1-103">This example shows how to apply a <xref:System.Windows.Media.ScaleTransform> when an event occurs.</span></span> <span data-ttu-id="c24a1-104">此处说明的概念与用于应用其他类型的转换的概念相同。</span><span class="sxs-lookup"><span data-stu-id="c24a1-104">The concept that is shown here is the same that you use for applying other types of transformations.</span></span> <span data-ttu-id="c24a1-105">有关可用类型的转换的详细信息，请参阅<xref:System.Windows.Media.Transform>类或[转换概述](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c24a1-105">For more information about the available types of transformations, see the <xref:System.Windows.Media.Transform> class or [Transforms Overview](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).</span></span>  
  
 <span data-ttu-id="c24a1-106">可以通过以下两种方式之一向元素应用转换：</span><span class="sxs-lookup"><span data-stu-id="c24a1-106">You can apply a transform to an element in either of these two ways:</span></span>  
  
-   <span data-ttu-id="c24a1-107">如果这样做*不*想要将影响布局，请使用的转换<xref:System.Windows.UIElement.RenderTransform%2A>元素的属性。</span><span class="sxs-lookup"><span data-stu-id="c24a1-107">If you do *not* want the transform to affect layout, use the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
-   <span data-ttu-id="c24a1-108">如果你确实想要将影响布局的转换，使用<xref:System.Windows.FrameworkElement.LayoutTransform%2A>元素的属性。</span><span class="sxs-lookup"><span data-stu-id="c24a1-108">If you do want the transform to affect layout, use the <xref:System.Windows.FrameworkElement.LayoutTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="c24a1-109">下面的示例应用<xref:System.Windows.Media.ScaleTransform>到<xref:System.Windows.UIElement.RenderTransform%2A>的按钮的属性。</span><span class="sxs-lookup"><span data-stu-id="c24a1-109">The following example applies a <xref:System.Windows.Media.ScaleTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a button.</span></span> <span data-ttu-id="c24a1-110">当鼠标移到按钮时,<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>和<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>属性<xref:System.Windows.Media.ScaleTransform>设置为`2`，这将导致按钮变得更大。</span><span class="sxs-lookup"><span data-stu-id="c24a1-110">When the mouse moves over the button, the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties of the <xref:System.Windows.Media.ScaleTransform> are set to `2`, which causes the button to become larger.</span></span> <span data-ttu-id="c24a1-111">当鼠标离开该按钮，<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>和<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>设置为`1`，这将导致按钮以返回到其原始大小。</span><span class="sxs-lookup"><span data-stu-id="c24a1-111">When the mouse moves off the button, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> are set to `1`, which causes the button to return to its original size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c24a1-112">示例</span><span class="sxs-lookup"><span data-stu-id="c24a1-112">Example</span></span>  
 [!code-xaml[ButtonTransform#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a><span data-ttu-id="c24a1-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c24a1-113">See Also</span></span>  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.ScaleTransform>  
 [<span data-ttu-id="c24a1-114">转换概述</span><span class="sxs-lookup"><span data-stu-id="c24a1-114">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="c24a1-115">帮助主题</span><span class="sxs-lookup"><span data-stu-id="c24a1-115">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)  
 [<span data-ttu-id="c24a1-116">路由事件概述</span><span class="sxs-lookup"><span data-stu-id="c24a1-116">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
