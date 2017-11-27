---
title: "如何：重写面板的 OnRender 方法"
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
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 774c612b09d5cb0ffdf36024a7e6a543f407cf67
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-override-the-panel-onrender-method"></a><span data-ttu-id="2269c-102">如何：重写面板的 OnRender 方法</span><span class="sxs-lookup"><span data-stu-id="2269c-102">How to: Override the Panel OnRender Method</span></span>
<span data-ttu-id="2269c-103">此示例演示如何重写<xref:System.Windows.Controls.Panel.OnRender%2A>方法<xref:System.Windows.Controls.Panel>以便将自定义图形效果添加到布局元素。</span><span class="sxs-lookup"><span data-stu-id="2269c-103">This example shows how to override the <xref:System.Windows.Controls.Panel.OnRender%2A> method of <xref:System.Windows.Controls.Panel> in order to add custom graphical effects to a layout element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2269c-104">示例</span><span class="sxs-lookup"><span data-stu-id="2269c-104">Example</span></span>  
 <span data-ttu-id="2269c-105">使用<xref:System.Windows.Controls.Panel.OnRender%2A>方法，以将图形效果添加到呈现的面板元素。</span><span class="sxs-lookup"><span data-stu-id="2269c-105">Use the <xref:System.Windows.Controls.Panel.OnRender%2A> method in order to add graphical effects to a rendered panel element.</span></span> <span data-ttu-id="2269c-106">例如，此方法可用于添加自定义边框或背景效果。</span><span class="sxs-lookup"><span data-stu-id="2269c-106">For example, you can use this method to add custom border or background effects.</span></span> <span data-ttu-id="2269c-107">A<xref:System.Windows.Media.DrawingContext>对象作为参数，它提供绘制形状、 文本、 图像或视频方法传递。</span><span class="sxs-lookup"><span data-stu-id="2269c-107">A <xref:System.Windows.Media.DrawingContext> object is passed as an argument, which provides methods for drawing shapes, text, images, or videos.</span></span> <span data-ttu-id="2269c-108">因此，此方法很有用的面板对象自定义项。</span><span class="sxs-lookup"><span data-stu-id="2269c-108">As a result, this method is useful for customization of a panel object.</span></span>  
  
 [!code-csharp[LightWeightCustomPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2269c-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2269c-109">See Also</span></span>  
 <xref:System.Windows.Controls.Panel>  
 [<span data-ttu-id="2269c-110">面板概述</span><span class="sxs-lookup"><span data-stu-id="2269c-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="2269c-111">自定义径向面板示例</span><span class="sxs-lookup"><span data-stu-id="2269c-111">Custom Radial Panel Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159982)  
 [<span data-ttu-id="2269c-112">操作说明主题</span><span class="sxs-lookup"><span data-stu-id="2269c-112">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/panel-how-to-topics.md)
