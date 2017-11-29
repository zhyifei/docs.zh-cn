---
title: "如何：将文本绘制到 Visual 中"
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
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 735a84a034587b1433403a45edc7c2f459340273
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-draw-text-to-a-visual"></a><span data-ttu-id="3c477-102">如何：将文本绘制到 Visual 中</span><span class="sxs-lookup"><span data-stu-id="3c477-102">How to: Draw Text to a Visual</span></span>
<span data-ttu-id="3c477-103">下面的示例演示如何绘制到文本<xref:System.Windows.Media.DrawingVisual>使用<xref:System.Windows.Media.DrawingContext>对象。</span><span class="sxs-lookup"><span data-stu-id="3c477-103">The following example shows how to draw text to a <xref:System.Windows.Media.DrawingVisual> using a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="3c477-104">绘制上下文返回通过调用<xref:System.Windows.Media.DrawingVisual.RenderOpen%2A>方法<xref:System.Windows.Media.DrawingVisual>对象。</span><span class="sxs-lookup"><span data-stu-id="3c477-104">A drawing context is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span> <span data-ttu-id="3c477-105">您可以绘制到绘制上下文的图形和文本。</span><span class="sxs-lookup"><span data-stu-id="3c477-105">You can draw graphics and text into a drawing context.</span></span>  
  
 <span data-ttu-id="3c477-106">若要绘制文本绘图上下文中，使用<xref:System.Windows.Media.DrawingContext.DrawText%2A>方法<xref:System.Windows.Media.DrawingContext>对象。</span><span class="sxs-lookup"><span data-stu-id="3c477-106">To draw text into the drawing context, use the <xref:System.Windows.Media.DrawingContext.DrawText%2A> method of a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="3c477-107">完成绘制绘图上下文中的内容，请调用<xref:System.Windows.Media.DrawingContext.Close%2A>方法来关闭绘图上下文并保留的内容。</span><span class="sxs-lookup"><span data-stu-id="3c477-107">When you are finished drawing content into the drawing context, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the drawing context and persist the content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c477-108">示例</span><span class="sxs-lookup"><span data-stu-id="3c477-108">Example</span></span>  
 [!code-csharp[DrawingVisualSample#110](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  <span data-ttu-id="3c477-109">有关从中提取上述代码示例的完整代码示例，请参阅[使用 DrawingVisual 的命中测试示例](http://go.microsoft.com/fwlink/?LinkID=159994)。</span><span class="sxs-lookup"><span data-stu-id="3c477-109">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](http://go.microsoft.com/fwlink/?LinkID=159994).</span></span>
