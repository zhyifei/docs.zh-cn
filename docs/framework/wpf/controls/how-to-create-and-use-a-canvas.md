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
ms.openlocfilehash: 13ed32195621350284530da78544e026ed341658
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360376"
---
# <a name="how-to-create-and-use-a-canvas"></a><span data-ttu-id="e6439-102">如何：创建和使用画布</span><span class="sxs-lookup"><span data-stu-id="e6439-102">How to: Create and Use a Canvas</span></span>
<span data-ttu-id="e6439-103">此示例演示如何创建和使用的实例<xref:System.Windows.Controls.Canvas>。</span><span class="sxs-lookup"><span data-stu-id="e6439-103">This example shows how to create and use an instance of <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6439-104">示例</span><span class="sxs-lookup"><span data-stu-id="e6439-104">Example</span></span>  
 <span data-ttu-id="e6439-105">下面的示例显式定位两<xref:System.Windows.Controls.TextBlock>通过使用元素<xref:System.Windows.Controls.Canvas.SetTop%2A>并<xref:System.Windows.Controls.Canvas.SetLeft%2A>方法的<xref:System.Windows.Controls.Canvas>。</span><span class="sxs-lookup"><span data-stu-id="e6439-105">The following example explicitly positions two <xref:System.Windows.Controls.TextBlock> elements by using the <xref:System.Windows.Controls.Canvas.SetTop%2A> and <xref:System.Windows.Controls.Canvas.SetLeft%2A> methods of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="e6439-106">该示例还将分配<xref:System.Windows.Controls.Control.Background%2A>色`LightSteelBlue`到<xref:System.Windows.Controls.Canvas>。</span><span class="sxs-lookup"><span data-stu-id="e6439-106">The example also assigns a <xref:System.Windows.Controls.Control.Background%2A> color of `LightSteelBlue` to the <xref:System.Windows.Controls.Canvas>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6439-107">当你使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]到位置<xref:System.Windows.Controls.TextBlock>元素，使用<xref:System.Windows.Controls.Canvas.Top%2A>和<xref:System.Windows.Controls.Canvas.Left%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="e6439-107">When you use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to position <xref:System.Windows.Controls.TextBlock> elements, use the <xref:System.Windows.Controls.Canvas.Top%2A> and <xref:System.Windows.Controls.Canvas.Left%2A> properties.</span></span>  
  
 [!code-csharp[CanvasCode#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e6439-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6439-108">See also</span></span>
- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.TextBlock>
- <xref:System.Windows.Controls.Canvas.SetTop%2A>
- <xref:System.Windows.Controls.Canvas.SetLeft%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- [<span data-ttu-id="e6439-109">面板概述</span><span class="sxs-lookup"><span data-stu-id="e6439-109">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="e6439-110">帮助主题</span><span class="sxs-lookup"><span data-stu-id="e6439-110">How-to Topics</span></span>](canvas-how-to-topics.md)
