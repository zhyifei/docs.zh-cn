---
title: 如何：将文本绘制到 Visual 中
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
ms.openlocfilehash: bc7a4f989137ec2b021d27a6e112ff1aebd99d07
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523238"
---
# <a name="how-to-draw-text-to-a-visual"></a><span data-ttu-id="c51da-102">如何：将文本绘制到 Visual 中</span><span class="sxs-lookup"><span data-stu-id="c51da-102">How to: Draw Text to a Visual</span></span>
<span data-ttu-id="c51da-103">下面的示例演示如何绘制到的文本<xref:System.Windows.Media.DrawingVisual>使用<xref:System.Windows.Media.DrawingContext>对象。</span><span class="sxs-lookup"><span data-stu-id="c51da-103">The following example shows how to draw text to a <xref:System.Windows.Media.DrawingVisual> using a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="c51da-104">绘图上下文返回通过调用<xref:System.Windows.Media.DrawingVisual.RenderOpen%2A>方法的<xref:System.Windows.Media.DrawingVisual>对象。</span><span class="sxs-lookup"><span data-stu-id="c51da-104">A drawing context is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span> <span data-ttu-id="c51da-105">您可以绘制图形和文本到绘图上下文。</span><span class="sxs-lookup"><span data-stu-id="c51da-105">You can draw graphics and text into a drawing context.</span></span>  
  
 <span data-ttu-id="c51da-106">若要绘制文本到绘图上下文，请使用<xref:System.Windows.Media.DrawingContext.DrawText%2A>方法的<xref:System.Windows.Media.DrawingContext>对象。</span><span class="sxs-lookup"><span data-stu-id="c51da-106">To draw text into the drawing context, use the <xref:System.Windows.Media.DrawingContext.DrawText%2A> method of a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="c51da-107">在完成到绘图上下文绘制内容，请调用<xref:System.Windows.Media.DrawingContext.Close%2A>方法来关闭绘图上下文并保留的内容。</span><span class="sxs-lookup"><span data-stu-id="c51da-107">When you are finished drawing content into the drawing context, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the drawing context and persist the content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c51da-108">示例</span><span class="sxs-lookup"><span data-stu-id="c51da-108">Example</span></span>  
 [!code-csharp[DrawingVisualSample#110](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  <span data-ttu-id="c51da-109">有关从中提取上述代码示例的完整代码示例，请参阅[使用 DrawingVisual 的命中测试示例](https://go.microsoft.com/fwlink/?LinkID=159994)。</span><span class="sxs-lookup"><span data-stu-id="c51da-109">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](https://go.microsoft.com/fwlink/?LinkID=159994).</span></span>
