---
title: "如何：对 Popup 进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 276c1a54cfdddcde84c0702f4e84f1dc6174bbda
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-popup"></a><span data-ttu-id="2087a-102">如何：对 Popup 进行动画处理</span><span class="sxs-lookup"><span data-stu-id="2087a-102">How to: Animate a Popup</span></span>
<span data-ttu-id="2087a-103">此示例演示两种方式进行动画处理<xref:System.Windows.Controls.Primitives.Popup>控件。</span><span class="sxs-lookup"><span data-stu-id="2087a-103">This example shows two ways to animate a <xref:System.Windows.Controls.Primitives.Popup> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2087a-104">示例</span><span class="sxs-lookup"><span data-stu-id="2087a-104">Example</span></span>  
 <span data-ttu-id="2087a-105">下面的示例设置<xref:System.Windows.Controls.Primitives.PopupAnimation>属性的值的<xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>，这将导致<xref:System.Windows.Controls.Primitives.Popup>以"滑入式"时出现。</span><span class="sxs-lookup"><span data-stu-id="2087a-105">The following example sets the <xref:System.Windows.Controls.Primitives.PopupAnimation> property to a value of <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, which causes the <xref:System.Windows.Controls.Primitives.Popup> to "slide-in" when it appears.</span></span>  
  
 <span data-ttu-id="2087a-106">若要旋转<xref:System.Windows.Controls.Primitives.Popup>，此示例将分配<xref:System.Windows.Media.RotateTransform>到<xref:System.Windows.UIElement.RenderTransform%2A>属性<xref:System.Windows.Controls.Canvas>，即的子元素<xref:System.Windows.Controls.Primitives.Popup>。</span><span class="sxs-lookup"><span data-stu-id="2087a-106">In order to rotate the <xref:System.Windows.Controls.Primitives.Popup>, this example assigns a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property on the <xref:System.Windows.Controls.Canvas>, which is the child element of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  
  
 <span data-ttu-id="2087a-107">对于要正常工作的转换，则必须设置<xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="2087a-107">For the transform to work correctly, the example must set the <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> property to `true`.</span></span> <span data-ttu-id="2087a-108">此外，<xref:System.Windows.FrameworkElement.Margin%2A>上<xref:System.Windows.Controls.Canvas>内容必须指定足够的空间<xref:System.Windows.Controls.Primitives.Popup>旋转。</span><span class="sxs-lookup"><span data-stu-id="2087a-108">In addition, the <xref:System.Windows.FrameworkElement.Margin%2A> on the <xref:System.Windows.Controls.Canvas> content must specify enough space for the <xref:System.Windows.Controls.Primitives.Popup> to rotate.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 <span data-ttu-id="2087a-109">下面的示例演示如何<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件发生时<xref:System.Windows.Controls.Button>单击后，触发器<xref:System.Windows.Media.Animation.Storyboard>启动动画。</span><span class="sxs-lookup"><span data-stu-id="2087a-109">The following example shows how a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which occurs when a <xref:System.Windows.Controls.Button> is clicked, triggers the <xref:System.Windows.Media.Animation.Storyboard> that starts the animation.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a><span data-ttu-id="2087a-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2087a-110">See Also</span></span>  
 <xref:System.Windows.UIElement.RenderTransform%2A>  
 <xref:System.Windows.Controls.Primitives.BulletDecorator>  
 <xref:System.Windows.Media.RotateTransform>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [<span data-ttu-id="2087a-111">操作说明主题</span><span class="sxs-lookup"><span data-stu-id="2087a-111">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)  
 [<span data-ttu-id="2087a-112">Popup 概述</span><span class="sxs-lookup"><span data-stu-id="2087a-112">Popup Overview</span></span>](../../../../docs/framework/wpf/controls/popup-overview.md)
