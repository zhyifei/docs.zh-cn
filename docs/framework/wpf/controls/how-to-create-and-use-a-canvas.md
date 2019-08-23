---
title: 如何：创建和使用画布
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Canvas
- Canvas control [WPF], creating
- Canvas control [WPF], using
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
ms.openlocfilehash: edef660b2da2f09e0a6edbc0a87f0d1f26eb03da
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964218"
---
# <a name="how-to-create-and-use-a-canvas"></a><span data-ttu-id="79fb0-102">如何：创建和使用画布</span><span class="sxs-lookup"><span data-stu-id="79fb0-102">How to: Create and Use a Canvas</span></span>
<span data-ttu-id="79fb0-103">此示例演示如何创建和使用的<xref:System.Windows.Controls.Canvas>实例。</span><span class="sxs-lookup"><span data-stu-id="79fb0-103">This example shows how to create and use an instance of <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79fb0-104">示例</span><span class="sxs-lookup"><span data-stu-id="79fb0-104">Example</span></span>  
 <span data-ttu-id="79fb0-105"><xref:System.Windows.Controls.TextBlock>下面的示例通过<xref:System.Windows.Controls.Canvas.SetTop%2A>使用的和<xref:System.Windows.Controls.Canvas.SetLeft%2A>方法<xref:System.Windows.Controls.Canvas>显式定位两个元素。</span><span class="sxs-lookup"><span data-stu-id="79fb0-105">The following example explicitly positions two <xref:System.Windows.Controls.TextBlock> elements by using the <xref:System.Windows.Controls.Canvas.SetTop%2A> and <xref:System.Windows.Controls.Canvas.SetLeft%2A> methods of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="79fb0-106">该示例还将的<xref:System.Windows.Controls.Control.Background%2A> `LightSteelBlue`颜色分配给<xref:System.Windows.Controls.Canvas>。</span><span class="sxs-lookup"><span data-stu-id="79fb0-106">The example also assigns a <xref:System.Windows.Controls.Control.Background%2A> color of `LightSteelBlue` to the <xref:System.Windows.Controls.Canvas>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="79fb0-107">当你使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]来放置<xref:System.Windows.Controls.TextBlock>元素时, 请<xref:System.Windows.Controls.Canvas.Top%2A>使用<xref:System.Windows.Controls.Canvas.Left%2A>和属性。</span><span class="sxs-lookup"><span data-stu-id="79fb0-107">When you use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to position <xref:System.Windows.Controls.TextBlock> elements, use the <xref:System.Windows.Controls.Canvas.Top%2A> and <xref:System.Windows.Controls.Canvas.Left%2A> properties.</span></span>  
  
 [!code-csharp[CanvasCode#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="79fb0-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="79fb0-108">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.TextBlock>
- <xref:System.Windows.Controls.Canvas.SetTop%2A>
- <xref:System.Windows.Controls.Canvas.SetLeft%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- [<span data-ttu-id="79fb0-109">面板概述</span><span class="sxs-lookup"><span data-stu-id="79fb0-109">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="79fb0-110">帮助主题</span><span class="sxs-lookup"><span data-stu-id="79fb0-110">How-to Topics</span></span>](canvas-how-to-topics.md)
