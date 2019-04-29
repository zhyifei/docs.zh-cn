---
title: 如何：重写面板的 OnRender 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: c4539847368c1a5789e99ec92106d17077ed5943
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770833"
---
# <a name="how-to-override-the-panel-onrender-method"></a><span data-ttu-id="bc6ba-102">如何：重写面板的 OnRender 方法</span><span class="sxs-lookup"><span data-stu-id="bc6ba-102">How to: Override the Panel OnRender Method</span></span>
<span data-ttu-id="bc6ba-103">此示例演示如何重写<xref:System.Windows.Controls.Panel.OnRender%2A>方法的<xref:System.Windows.Controls.Panel>以便将自定义图形效果添加到布局元素。</span><span class="sxs-lookup"><span data-stu-id="bc6ba-103">This example shows how to override the <xref:System.Windows.Controls.Panel.OnRender%2A> method of <xref:System.Windows.Controls.Panel> in order to add custom graphical effects to a layout element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc6ba-104">示例</span><span class="sxs-lookup"><span data-stu-id="bc6ba-104">Example</span></span>  
 <span data-ttu-id="bc6ba-105">使用<xref:System.Windows.Controls.Panel.OnRender%2A>方法，以将图形效果添加到呈现的面板元素。</span><span class="sxs-lookup"><span data-stu-id="bc6ba-105">Use the <xref:System.Windows.Controls.Panel.OnRender%2A> method in order to add graphical effects to a rendered panel element.</span></span> <span data-ttu-id="bc6ba-106">例如，可以使用此方法添加自定义边框或背景效果。</span><span class="sxs-lookup"><span data-stu-id="bc6ba-106">For example, you can use this method to add custom border or background effects.</span></span> <span data-ttu-id="bc6ba-107">一个<xref:System.Windows.Media.DrawingContext>对象作为参数，它提供用于绘制形状、 文本、 图像或视频的方法传递。</span><span class="sxs-lookup"><span data-stu-id="bc6ba-107">A <xref:System.Windows.Media.DrawingContext> object is passed as an argument, which provides methods for drawing shapes, text, images, or videos.</span></span> <span data-ttu-id="bc6ba-108">因此，此方法很有用的面板对象自定义项。</span><span class="sxs-lookup"><span data-stu-id="bc6ba-108">As a result, this method is useful for customization of a panel object.</span></span>  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="bc6ba-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc6ba-109">See also</span></span>

- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="bc6ba-110">面板概述</span><span class="sxs-lookup"><span data-stu-id="bc6ba-110">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="bc6ba-111">自定义径向面板示例</span><span class="sxs-lookup"><span data-stu-id="bc6ba-111">Custom Radial Panel Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159982)
- [<span data-ttu-id="bc6ba-112">帮助主题</span><span class="sxs-lookup"><span data-stu-id="bc6ba-112">How-to Topics</span></span>](panel-how-to-topics.md)
