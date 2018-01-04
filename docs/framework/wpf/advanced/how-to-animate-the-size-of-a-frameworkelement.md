---
title: "如何：对 FrameworkElement 的大小进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], FrameworkElement size
- FrameworkElement [WPF], animating size of
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cf31fa1a10748c3c2f6d239d041c72c57a148e1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-size-of-a-frameworkelement"></a><span data-ttu-id="608a1-102">如何：对 FrameworkElement 的大小进行动画处理</span><span class="sxs-lookup"><span data-stu-id="608a1-102">How to: Animate the Size of a FrameworkElement</span></span>
<span data-ttu-id="608a1-103">要进行动画处理的大小<xref:System.Windows.FrameworkElement>，你可以对其<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>属性或使用经过动画处理的<xref:System.Windows.Media.ScaleTransform>。</span><span class="sxs-lookup"><span data-stu-id="608a1-103">To animate the size of a <xref:System.Windows.FrameworkElement>, you can either animate its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties or use an animated <xref:System.Windows.Media.ScaleTransform>.</span></span>  
  
 <span data-ttu-id="608a1-104">在下面的示例以进行动画处理使用这两种方法的两个按钮的大小。</span><span class="sxs-lookup"><span data-stu-id="608a1-104">In the following example animates the size of two buttons using these two approaches.</span></span> <span data-ttu-id="608a1-105">通过对进行动画处理调整一个按钮的大小及其<xref:System.Windows.FrameworkElement.Width%2A>通过进行动画处理调整大小属性，另一个<xref:System.Windows.Media.ScaleTransform>应用于其<xref:System.Windows.UIElement.RenderTransform%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="608a1-105">One button is resized by animating its <xref:System.Windows.FrameworkElement.Width%2A> property and another is resized by animating a <xref:System.Windows.Media.ScaleTransform> applied to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span> <span data-ttu-id="608a1-106">每个按钮包含一些文本。</span><span class="sxs-lookup"><span data-stu-id="608a1-106">Each button contains some text.</span></span> <span data-ttu-id="608a1-107">最初，则将显示文本中两个按钮相同，但按钮是调整大小时，在第二个按钮的文本会显得失真。</span><span class="sxs-lookup"><span data-stu-id="608a1-107">Initially, the text appears the same in both buttons, but as the buttons are resized, the text in the second button becomes distorted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="608a1-108">示例</span><span class="sxs-lookup"><span data-stu-id="608a1-108">Example</span></span>  
 [!code-xaml[transformanimations_snip#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 <span data-ttu-id="608a1-109">当你转换元素时, 转换整个元素和其内容。</span><span class="sxs-lookup"><span data-stu-id="608a1-109">When you transform an element, the entire element and its contents are transformed.</span></span> <span data-ttu-id="608a1-110">当您直接改变元素，如下所示的第一个按钮，这种情况的大小除非其大小和位置取决于其父元素的大小无法调整大小的元素的内容。</span><span class="sxs-lookup"><span data-stu-id="608a1-110">When you directly alter the size of an element, as in the case of the first button, the element's contents are not resized unless their size and position depend on the size of their parent element.</span></span>  
  
 <span data-ttu-id="608a1-111">通过应用到动画的转换对元素的大小进行动画处理其<xref:System.Windows.UIElement.RenderTransform%2A>属性提供更好的性能不是动画处理其<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>直接，因为<xref:System.Windows.UIElement.RenderTransform%2A>属性不会触发了布局过程。</span><span class="sxs-lookup"><span data-stu-id="608a1-111">Animating the size of an element by applying an animated transform to its <xref:System.Windows.UIElement.RenderTransform%2A> property provides better performance than animated its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> directly, because the <xref:System.Windows.UIElement.RenderTransform%2A> property does not trigger a layout pass.</span></span>  
  
 <span data-ttu-id="608a1-112">有关对属性进行动画处理的详细信息，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="608a1-112">For more information about animating properties, see the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span> <span data-ttu-id="608a1-113">有关转换的详细信息，请参阅[转换概述](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="608a1-113">For more information about transforms, see the [Transforms Overview](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).</span></span>
