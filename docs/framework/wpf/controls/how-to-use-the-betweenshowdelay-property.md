---
title: "如何：使用 BetweenShowDelay 属性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dfd4bb4c9e26361e5b8f573d06449b090497acd6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-betweenshowdelay-property"></a><span data-ttu-id="62721-102">如何：使用 BetweenShowDelay 属性</span><span class="sxs-lookup"><span data-stu-id="62721-102">How to: Use the BetweenShowDelay Property</span></span>
<span data-ttu-id="62721-103">此示例演示如何使用<xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>时间属性，以便快速显示工具提示-且很少或没有延迟-当用户将移动鼠标指针从一个工具提示直接到另一个。</span><span class="sxs-lookup"><span data-stu-id="62721-103">This example shows how to use the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> time property so that tooltips appear quickly—with little or no delay—when a user moves the mouse pointer from one tooltip directly to another.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62721-104">示例</span><span class="sxs-lookup"><span data-stu-id="62721-104">Example</span></span>  
 <span data-ttu-id="62721-105">在下面的示例中，<xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>属性设置为 1 秒 （1000年毫秒为单位） 和<xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>设置为 2 秒 （2000年毫秒） 的工具提示<xref:System.Windows.Shapes.Ellipse>控件。</span><span class="sxs-lookup"><span data-stu-id="62721-105">In the following example, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> property is set to one second (1000 milliseconds) and the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> is set to two seconds (2000 milliseconds) for the tooltips of both <xref:System.Windows.Shapes.Ellipse> controls.</span></span> <span data-ttu-id="62721-106">如果显示一个省略号的工具提示，然后将鼠标指针移动到另一个椭圆在两个秒和暂停在其上时，第二个椭圆的工具提示将立即显示。</span><span class="sxs-lookup"><span data-stu-id="62721-106">If you display the tooltip for one of the ellipses and then move the mouse pointer to another ellipse within two seconds and pause on it, the tooltip of the second ellipse displays immediately.</span></span>  
  
 <span data-ttu-id="62721-107">在以下情况下，任一<xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>适用，这将导致产生要等待一秒才会出现的第二个椭圆的工具提示：</span><span class="sxs-lookup"><span data-stu-id="62721-107">In either of the following scenarios, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> applies, which causes the tooltip for the second ellipse to wait one second before it appears:</span></span>  
  
-   <span data-ttu-id="62721-108">如果的时间将移到第二个按钮将为多个两秒。</span><span class="sxs-lookup"><span data-stu-id="62721-108">If the time it takes to move to the second button is more than two seconds.</span></span>  
  
-   <span data-ttu-id="62721-109">如果工具提示的第一个椭圆的时间间隔开始时不可见。</span><span class="sxs-lookup"><span data-stu-id="62721-109">If the tooltip is not visible at the beginning of the time interval for the first ellipse.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a><span data-ttu-id="62721-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="62721-110">See Also</span></span>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [<span data-ttu-id="62721-111">帮助主题</span><span class="sxs-lookup"><span data-stu-id="62721-111">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [<span data-ttu-id="62721-112">ToolTip 概述</span><span class="sxs-lookup"><span data-stu-id="62721-112">ToolTip Overview</span></span>](../../../../docs/framework/wpf/controls/tooltip-overview.md)
